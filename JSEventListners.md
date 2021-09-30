## Event Listeners

Event Listners are generally events that can be catched by the components using JS.
There are many events in vanilla JS that can be added to a DOM element
the eventListners can be added to window, documentObject
#### NOTE: It is mandatory to remove an event whenever an eventListner is added it has to be removed else these will be events will be passed continuously even if there is no method to handle it.

#### Adding and Removing Event Listners

1. 

#### Resize:

1. This will be triggered whenever window's width is changed, it can be utilized by:

```
window.addEventListner( 'resize', handleResize )

window.removeEventListner( 'resize' )
```