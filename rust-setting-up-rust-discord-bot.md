- Add dependencies

```rust
[dependencies]
serenity = "0.8"
```

- Grab example bot from `serenity`

```rust
use std::env;

use serenity::{
    async_trait,
    model::{channel::Message, gateway::Ready},
    prelude::*,
};

struct Handler;

#[async_trait]
impl EventHandler for Handler {
    // Set a handler for the `message` event - so that whenever a new message
    // is received - the closure (or function) passed will be called.
    //
    // Event handlers are dispatched through a threadpool, and so multiple
    // events can be dispatched simultaneously.
    async fn message(&self, ctx: Context, msg: Message) {
        if msg.content == "!ping" {
            // Sending a message can fail, due to a network error, an
            // authentication error, or lack of permissions to post in the
            // channel, so log to stdout when some error happens, with a
            // description of it.
            if let Err(why) = msg.channel_id.say(&ctx.http, "Pong!").await {
                println!("Error sending message: {:?}", why);
            }
        }
    }

    // Set a handler to be called on the `ready` event. This is called when a
    // shard is booted, and a READY payload is sent by Discord. This payload
    // contains data like the current user's guild Ids, current user data,
    // private channels, and more.
    //
    // In this case, just print what the current user's username is.
    async fn ready(&self, _: Context, ready: Ready) {
        println!("{} is connected!", ready.user.name);
    }
}

#[tokio::main]
async fn main() {
    // Configure the client with your Discord bot token in the environment.
    let token = env::var("DISCORD_TOKEN")
        .expect("Expected a token in the environment");

    // Create a new instance of the Client, logging in as a bot. This will
    // automatically prepend your bot token with "Bot ", which is a requirement
    // by Discord for bot users.
    let mut client = Client::new(&token)
        .event_handler(Handler)
        .await
        .expect("Err creating client");

    // Finally, start a single shard, and start listening to events.
    //
    // Shards will automatically attempt to reconnect, and will perform
    // exponential backoff until it reconnects.
    if let Err(why) = client.start().await {
        println!("Client error: {:?}", why);
    }
}
```

- go to `discord.com/developers/applications` and log in with your Discord account
- after logging in, click "New Application" at the top right
- enter the name of your application, `rust-bot`
- click on the "OAuth2" option in the left sidebar
- select the bot scope at the bottom of the page
- select all bot permissions
- copy the generated url and paste it into your browser
- this brings you to an OAuth page that asks you to select which server to attach your bot to
	- note that in order to attach a bot to a server, you must have the "Manage Server" permissions in the server
- after you've selected the server you wish you use, click "Continue"
- this dialogue will give you the opportunity to restrict the permissions that will be granted to the bot on this server. this allows you to select the specific permissions you'd like the bot to have on this server.
- once you've selected the permissions you'd like, click "Authorize"
- you will also have to pass a reCAPTCHA 
- after all of this, the rust bot should join your server!

