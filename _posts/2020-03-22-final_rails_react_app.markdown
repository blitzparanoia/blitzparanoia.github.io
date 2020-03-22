---
layout: post
title:      "Final: Rails/React App"
date:       2020-03-22 16:06:33 -0400
permalink:  final_rails_react_app
---


I have created an employee management app. It features a rails backend working as an api. The backend is connected to a React front end with Redux. The app uses Redux to mange the store and features a combination of stateless and stateful components. Below are the notes I have taken on the functionality of each of the app files.

### Index.js

The place where the devTools for redux are set up. This is also where the ReactDOM.render defines the 'root' is going to be the displace point of the app for it to be rendered under a single div. The store is defined in a variable and created in the index.js  (via. createStore() from the redux package). The creatStore redux method takes 2 arguments, the reducer and enhancers. Enhancers refer to Middleware that is added via the applyMiddleware() method.

The entire app component is wrapped in a Provider tag, this tag takes the propery of store to allow the store to be accessed across the entire app. The app is also wrapped in Router to assist in URL restful routing.

Note: BrowserRouter is renamed to Router via the import

### App.js

The base of the app. It hold the NavBar component to be displayed throughout the entire app. It also holds the container to be displayed.

### CompaniesContainer.js

This component holds where  the company components will render. It is connected to the store to allow componentDidMount to gather the data from the backend via an action (action creator and reducer)

Route and Switch is implemented for the links. The route with exact means that only that specifc route is displayed when rendered. Note that some routes require props. The props are passed using routerProps to the component.

MapStateToProps sets the state as a key of companies and the values are taken from state.companies.

### CompanyForm.js

Component is connected to the store and is a class component because it minipulates state. This is a controlled form that  captures the input values with onChange. OnSubmit is the function that triggers the action creator to dispatch the new information and pass it the reducer then update the store/state.  

### companies.js
Stateless component that has props passed into the component via the parent. The props are the companies -> the companies are then interated over with .map and given a unique key of its company.id. Each company name is wrapped in a link tag to render that particular company on the individual company page.

### company.js
This component is responsible for rendering the company show page. Props are passed down from the parent. A variable is defined to identify the company by the id in the database using the .filter method. The name of the company is rendered taking into account that the first time it is rendered it is undefined. The EmployeeContainer is rendered here because of the relationship between the two items. An employee belongs to a company, while a company has many employees. The company is passed as props to the employee container.

### EmployeeContainer.js
Where all employee related components are kept. The form and list is imported. This is a class component because local state is being used to show/hide the EmployeeForm component. 

### EmployeeForm.js
A class component controlled form used for creating employees. 

### Actions
The action is a function. An action object is returned, the action object is dispatched to the reducer and the reducer returns the new state. A fetch request is made to the backend. `.then` is used to capture the responses and dispatch the response to the reducer. For some actions a method has to be defined, by default a request is a GET. When making a POST request headers need to be defined to alert of the type of content, the body: uses JSON method `stringify()` to convert the data into a JSON string.

### Reducer
Reducer is a function that accepts 2 arguments, the initial state and action. Switch cases with `action.type` are used to identify the action type when a case is matched it is executed and the state/redux store is updated. NOTE: the spread operator is used to make a copy of the state as to not minipulate the original state to avoid potentially causing unwanted side effects. A `default: state` is declared and refered to if a case is not matched, so there will be something returned and the app will not break. 
