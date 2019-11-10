---
layout: post
title:      "React Lifecycle: Quick Notes"
date:       2019-11-10 23:18:58 +0000
permalink:  react_lifecycle_quick_notes
---


I had watched a video of an overveiw of the React Lifecycles and an explaination of how they work. There was an explaination of each point in the lifecycle in reference to React version 16 (when the video was released).
However, looking at the current React lifecycle methods on the docs, things are simplified but the core components remain intact. 


### Lifecycle of a Component
encompasses the time when it is first inserted into the DOM, when it is in the DOM and when it removed from the DOM

**NOTE: there is a unique lifecycle for every component**

This is why it is important to create components for each aspect because they each have their own unique life cycle

Components are able to each perform their own jobs independently. React is not the only framework that is able to separate or be broken into parts, but it is a factor that separates it from the rest.

### Three Major Sections

1. *Mounting *- Component is added to the DOM
2. *Updates*- component receives changes, to props or state, and when the component is being rerendered
3. *Unmounting*- Component removed from the DOM

NOTE: Any method that contain keyword *Will* is captured before the event occurs. Methods with *Did* are captured is after the event occurs

### Methods

**constructor(props)**- called when the component is created before mounting to the DOM, used to initialize state and to bind this for components methods

**componentWillMount**- executed before the component gets to the DOM, included for backwards compatibility, not recommended use anymore

**render**- appears in the browser, it exist in the DOM

**componentDidMount**- the point where AJAX request, event listeners and any set up that requires a DOM 
*NOTE: calling setState() will cause a re-render at this point of the lifecycle*

**running**- App is running


**When props are changed**

**componentWillReceiveProps(nextProps)**- triggered when the component receives new props from its parent, resetting state based on a change

**shouldComponentUpdate(nextProps, nextState)**- exists for performance improvements, *Reconciliation in the docs advance guide for more information*
receives two arguments as indicated, provides a boolean if the DOM should update


**componentWillUpdate(nextProps, nextState)**-  NOTE: that this method is not called on the initial render 


-The above three life cycle methods occur before the update render. 
*Note: changes should be made to the componentWillReceiveProps(nextProps) method *

**CHANGES ARE THEN RENDERED**
**componentDidUpdate(prevProps, prevState)**- at this point we do not get componentDidMount anymore we get  componentDidUpdate(prevProps, prevState) 


### Unmount
**componentWillUnmount**- time to get the component out of the UI, get rid of everything associated with it, possible use case…to remove an event listener when a component is taken off so they are not still waiting on the DOM after the item is not longer “living”
