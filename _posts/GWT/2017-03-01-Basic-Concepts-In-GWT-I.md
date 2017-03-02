---
layout: article
categories: GWT
tags: [GWT]
image:
  teaser: gwt_logo.png
---

##### EventBus

The Event Bus is a mechanism for a) passing events and b) registering to be notified of some subset of these events.  

The post [How to use the GWT EventBus](http://stackoverflow.com/questions/6030202/how-to-use-the-gwt-eventbus) in StackOverflow gives nice brief introduction to EventBus.


> When you divide the project into logical parts (for example with *MVP*) that sometimes need to communicate.  EventBus is what you need in this case.  
To use it, you instantiate one EventBus per app which is then used by all other classes. To achieve this use static field, factory or dependency injection (GIN in case of GWT).

##### MVP

[Offcial document of GWT](http://www.gwtproject.org/articles/mvp-architecture.html) gives MVP's definition as below: 

> Model-view-presenter (MVP) architecture works best when developing GWT apps for two main reasons.   
> First the MVP model, much like other design patterns, decouples development in a way that allows multiple developers to work simultaneously.  
> Secondly, this model allows us to minimize our use of GWTTestCase, which relies on the presence of a browser, and, for the bulk of our code, write lightweight (and fast) JRE tests (which don’t require a browser).

+ **Model**: A model encompasses business objects
+ **View**: A view contains all of the UI components that make up our application. Views are responsible for the layout of the UI components and have no notion of the model. 
+ **Presenter**: A presenter contains all of the logic for our application. As a general rule, for every view you’ll want a presenter to drive the view and handle events that are sourced from the UI widgets within the view.
+ **AppController**: It is to handle logic that is not specific to any presenter and instead resides at the application layer.

The general flow is:

  1 | GWT’s bootstrap process calls onModuleLoad()  
  2 | onModuleLoad() creates the RPC service, Event Bus, and the AppController  
  3 | The AppController is passed the RootPanel instance and takes over   
  4 | From then on the AppController is in control of creating specific presenters and supplying a view that the presenter will drive.  

In order to bind the presenter and associated view together we’ll rely on interfaces that are defined within the presenter.






