---
layout: post
title:      "Final Project : Book Worm"
date:       2020-01-07 19:29:55 -0500
permalink:  final_project_book_worm
---

My final project is called Book Worm. It is made with a Ruby on Rails back end and React front end.

### Back-End: Ruby On Rails
The back end of the project is made with Ruby on Rails. The controller holds the methods that allow creation and saving to the database. The views are rendered via React. CORS gem needed to be installed inorder to allow cross domain AJAX calls. The routes are namespaced. They are also nested in this case books `has_many` reviews.

### Front-End: React/Redux
The front end was composed of React and Redux. The app allows the user to keep a log of books and add reviews to the books on the list. Below are notes of what I have learned about using thunk and its advantages.
Note: Thunk was added and is used to make requests to the back end.

It is important to remember that everything in the app is not happening in the front end. Connect works in conjunction with thunk. Thunk allows the calling of dispatch from inside the action created as opposed to outside the action created. Instead of connect automatically calling dispatch.Thunk allows us to wait for the action request to finish before we dispatch anything to the reducer. 

The container should render other components and pass them data if they require data, contain other functions etc.

Thunk is allowing a thunk function (`return (dispatch)`), passing in dispatch to use as an argument inside the action creator and dispatch the responds for the request.




