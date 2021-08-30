[wikipedia](https://en.wikipedia.org/wiki/Dig_(command))

Network admin cli for querying DNS

I used it to check whether a MX record we had tried to set up had propagated through DNS yet.

```bash
dig [server] [name] [type]
```

where `type` is the type of record to query for