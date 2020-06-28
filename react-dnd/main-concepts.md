React DnD uses Redux internally. Like Redux (or Flux) it uses data instead of the views as the source of truth.

## Backends
 
 - Built on top of the [HTML5 drag and drop API](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Drag_and_drop)
 - This API doesn't work on touch devices, and is less customizable on IE
 - There are other backends available
 - Backends are similar to React's synthetic event system
	 - **they abstract away the browser differences and process the native DOM events** 
 
## Items & Types

- When something is dragged across the screen, it isn't thought of as a component, but as an *item* of a certain *type*
	- An **item** is a JS object that describes the item being dragged
		- example for a card being dragged `{ cardId: 42 }`.
	- A **type** is a string (or symbol) that uniquely identifies a class of items in an application
		- example for kanban board: card type representing draggable cards, list type for draggable lists, etc
		- **types let you specify which drag sources and drop targets are compatible**
		- keep an enumeration of the type constants somewhere in an application, similar to an enumeration of Redux action types

## [Monitors](https://react-dnd.github.io/react-dnd/docs/overview#monitors)

- react-dnd wrappers exposing its internal state
- **Let you update the props of components in response to the drag/drop state changes**
- Each component that needs to track the drag/drop state can define a **collecting function**, which retrieves relevant pieces of that state from the monitors.

## [Connectors](https://react-dnd.github.io/react-dnd/docs/overview#connectors)