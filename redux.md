# Redux Flash Cards

`react` 
  > Library used to manages user's interface. library vs framework - In framework, most of the design decisions are made by framework structure. Library you are in charge of designing the structure of your app.

`redux`
  > library that manages state of your app providing single source of state

`state`
  > to be able to interact w user we have state in our app

`view state`
  > used only for displaying to the user

`app state`
  > state that we store in our db

`state`
  > to be able to interact w user we have state in our app

`reducer`
  > function - that has State and Action as arguments and gives us NEW STATE

`action`
  > its a object that gets dispatched to state

`payload`
  > what information we want to send to state

`store`
  > final container of the state, interactions with the store are maintained

`dispatch`
  > sending actions to reducer to interact with the store

`provider`
  > react-redux concept and tag that is linking <App /> and store. Main use is to hold the store.




### Provider

* holds a store
* having only one **state** on the top of our virtual DOM tree => called *store*
* Store is the place where we have every state of our app

### Reducer
* defines APP state
* defines interaction to APP state USER => reducer => store
* it's a function(state, action)
  * action => create item, update input(cat_UPDATE)
  * action is an OBJECT literal with 
    * type: string,
    * payload: any format - action logic, if we want to increment counter by 10

    ``` javascript
    { type: 'ADD_TODO', payload: new Error(), error: true }
    ```

  * state gives us new state that goes to STORE where it gets stored

### interaction w store

* `getState` - gets state
* `dispatch` - make changes to state
* `subscribe` - subscribe changes that happen in some other reducer, listen to changes on the state and update our data

