# Chat

### Level 4

Students will build a simple Message app to practice MVC separation, protocols, master-detail interfaces, table views, network services, application design, and the development process. 

Message is a mini-capstone project where students are given direction on required and optional features, it is the job of the student to turn that list of features into an application by going through market research, prototyping, designing a solution, evaluating different technologies, architecting the application, implementing the features, and submitting the project to TestFlight or the App Store.

Students will follow the [DevMountain iOS App Canvas](https://github.com/DevMountain/ios-app-canvas) to execute this project on a condensed timeline of 7-14 days.

Students who complete this project independently are able to:

### Part One - Research and Product Design

* perform market research to identify a potential need and solution
* create user personas that would have the particular problem that the application solves
* identify the key features required for a minimum viable product (MVP) that fills the particular need or use case
* backlog desired features that are beyond the scope of a minimum viable product (MVP)
* perform technical research to determine if the key features can be built, and what technologies will be used to do so

### Part Two - Development Planning

* paper prototype the view hierarchy and all views required to fit the designed solution
* iterate on paper prototypes until a simple, clear solution is found
* systematically plan out the model layer, including generated headers for each model object
* systematically plan out controller and helper classes, including generated headers for each class
* systematically plan out helper layers for persistence, backends, or other project-specific technologies, including generated headers for each class

### Part Three - Building the Application

* build out the designed view hierarchy for the project
* implement the designed model layer for the project
* implement the designed controller and helper classes for the project
* submit the application to TestFlight or the App Store


## Part One - Research and Product Design

Developers must be able to take ideas and determine if there is a product worth building. There are many ways to approach this problem, but the bare minimum should be researching the competition and talking to potential users to identify opportunities to provide real value with the idea.

When building a business, many app ideas are discarded at this stage. When building a Capstone or Group project, this stage is for practice and to help you identify ways to build a better product. Don't be afraid of competition in the App Store as long as you can identify real and valuable ways to improve on what exists.

### Idea

Settle on a more specific idea than a generic chat or messaging application. Is this a chat app for dog owners? Pokemon fans? Fans of a particular website? Is this a clone of another app? If you want users for your application, it should solve a clearly defined problem. 

This idea will evolve as you go through the rest of Part One based on market research and technical research. But it is helpful to have a place to start.

1. Write down your more specific idea on a post-it note and include it on your App Canvas

### Features

There are dozens of features that can be built into a simple chat application. Take some time to determine which are most important to building the idea you settled on. Do not let unnecessary features get in the way of completing the application, focus on your core feature set. 

1. Identify any required features you need to include in a minimum viable product version of your application
2. Identify any optional features you would like to include in your mininmum viable product
3. Simplify your list by identifying the core features and moving others to your backlog to revisit in a future version
4. Simplify, simplify, simplify

##### Required Features

The minimum viable product should include these required features.

* 1:1 chat between two users
* Group chat between multiple users

##### Optional Features

Consider 1-2 optional features you would like to include in your project. You will do particular research into _how_ to implement these features in a future step.

* Push notifications
* Photo messages
* Voice messages
* Video messages
* Stickers
* Out of app invites to bring users into the platform
* VOIP calls
* Location aware
* Other ideas you come up with

1. Identify the key features required for a minimum viable product (MVP) that fills the particular need or use case
2. Write the features down and put them in order or priority on your App Canvas

### User Personas

Identify who your ideal users are. These are called [User Personas](http://www.uxbooth.com/articles/creating-personas/), and can help you make crucial decisions as you design and implement your application. If you are unfamiliar with User Personas for UX design, spend some time researching how they can help you create a better product.

You will use your User Personas on future projects to identify who you should interview for extremely valuable input on your projects. But the User Interview is outside of the scope of this project.

1. Identify 2-3 User Personas for your product
2. Detail their demographic information, motivations, concerns, goals, and pain points as they relate to the problem your application solves
3. Refer back to these personas as you make design and feature decisions for your app

### Monetization

This is an important consideration when building an app, but it is beyond the scope of this particular project. Your monetization strategy for this particular project is to build your experience and resume so that you can get a job. Consider any other monetization a Black Diamond if you finish the rest.

### Market Research

Do some basic market research to investigate competition. There are hundreds of messaging applications, so try to narrow down your research to anything specific to your niche idea. Many developers will download and evaluate dozens of applications during this stage of development.

1. Brainstorm some key words that you would use to find similar applications
2. Search the App Store for your key words and any other related searches
3. Identify and download competing applications
4. Use the application to identify any features or implications you had not considered
5. Update your App Canvas with any changes or relevant details

Some potential apps to check out:

* Messages
* Slack
* WeChat
* Line
* Voxer
* Drop Message

### Technical Research

Identify features that you do not currently know how to build. Consider how you will build them. What iOS frameworks or features exist to perform the feature? What third party frameworks or libraries exist to perform the feature? Is the feature possible to build in the timeframe given to the project?

If there is not a great tool or clear path to implementing a particular feature, you should avoid that feature for the minimum-viable-product, Capstone projects, or Group projects. 

Example: If it is not possible to implement Push Notifications with a backend you are familiar with, consider other backends that may make that possible. Consider if you have time and capacity to learn those different tools in your given timeframe. If so, plan to use them. If not, consider dropping Push Notifications from your feature list.

1. Investigate what technologies you will use to implement each feature in your application
2. Determine whether the feature is possible given the framework or library you have identified, work to find a replacement if it cannot do what is needed
3. Update your App Canvas with any changes or relevant details


## Part Two - Development Planning

### View Hierarchy

Design how the user will navigate your application. Use paper index cards and a Sharpie for low-fidelity sketches.

1. Draw out each view you will need to include each key feature of your application
2. Determine how the user will navigate to each screen
3. Have someone who wasn't involved in drawing out the application try and navigate using your drawings like an app
4. Iterate
5. Iterate
6. Iterate
7. Post your index cards to your App Canvas

A few notes to consider:

* You probably don't need a Settings screen for a simple application

### Model Layer

Design your model layer. Consider the data you need, how you will get that data, where you will store that data, relationships between different model data, and how the data will be represented in the application. A sample `Message` object has been included below.

1. Determine what data you need to build the features for your product
2. Systematically plan out the model objects, write down each property and function as a generated header
3. Systematically plan out the persistence and backend representation of your data
4. Work with your mentor to finalize your model layer design following best practices
5. Add your Model layer to your App Canvas

Do not worry about writing any code here. This is just the planning stage.

Example `Message` struct:
```
struct Message: FirebaseType {
    
    let sender: User // the current user
    let thread: Thread // the thread the message will be posted to
    let text: String // the content of the message
    
    init(senderID: String, thread: Thread, text: String) { } // memberwise initializer

    //MARK: FirebaseType
    
    var identifier: String? // firebase auto identifier
    var jsonValue: [String: AnyObject] // dictionary representation of the object
    var endpoints: [String] // where the data should be saved, this may be an array if we want to save the message data to multiple endpoints, for example, under the user's messages, and under the thread
    
    init(json: [String: AnyObject]) { }
}
```

Example back end representation:
```
Endpoint: /(user identifier)/messages/(message identifier)/
{
    "senderID": "fdsa-fdsa-fdsa-fdsa",
    "threadID": "qwer-qwer-qwer-qwer",
    "text": "Check out this cool new messaging app I'm using!"
}
```

```
Endpoint: /(thread identifier)/messages/(message identifier)/

{
    "senderID": "fdsa-fdsa-fdsa-fdsa",
    "threadID": "qwer-qwer-qwer-qwer",
    "text": "Check out this cool new messaging app I'm using!"
}

```

### Controllers and Helper Classes

Design your controller and helper objects that will help manage data in your application.

1. Determine what Model Object Controllers you will need to manage data in your application
2. Consider the CRUD functionality of each Controller
3. Consider if each model object needs it's own controller, or if you can combine them sensibly
4. Consider any helper classes you may need on top of your model controllers
5. Detail each property or function you will need on your controller objects, write down each property and function as a generated header
6. Work with your mentor to finalize your controller design following best practices
7. Add your controller and helper classes to your App Canvas

Example `MessageController` class:

```
class MessageController {
    
    /*
        At a bare minimum, we need our MessageController to add messages, fetch messages, and observe the endpoint for a specific thread for new messages.
    */
    
    static func addMessageToThread(message: Message, thread: Thread, completion: (success: Bool) -> Void) {

    }
    
    static func currentMessagesForThread(thread: Thread, completion: (messages:[Message]) -> Void) {
        // fetch messages one time, useful for displaying a static list of messages
    }
    
    static func observeMessagesForThread(thread: Thread, updateBlock: (messages:[Message]) -> Void) {
        // should run the update block each time the data at the thread endpoint is updated
        // useful for creating a live view that updates immediately when messages for a thread update
    }

    static func endObservingMessagedForThread(thread: Thread) {
        // stops observing messages
        // useful for ending an observation for a thread that is no longer being displayed
    }
    
}
```

This sample controller is not feature complete. There are many other data points you may want to manage that would be useful to place in a MessageController type that will be specific to your app. (Ex. Latest message for all threads)


## Part Three - Building the Application

Use the App Canvas Tracker to build out the application. Following the steps in order will help you complete the application. Trust the system, it will keep you on track and help you avoid dependency issues. We've adjusted the recommended timeline to condense the project in the given time in class. You are encouraged to continue building the project after we finish in class.

This is an extremely accelerated pace. Try to stick to it in order to finish in the allotted time.

#### Research - .5-1 day

Finish your market research and development plan.

#### Prototype Key Feature - 1 day

Get a basic version of a two way chat working.

#### View Hierarchy - .5 day

Build out your Storyboard of your navigation to each view.

#### Implement Model - 1-2 days

Implement your model objects and persistence/backend layer.

#### Controllers w/ Mock Data - 1-2 days

Set up controllers to deliver data to view controllers.

#### Wire Up Views - 1 day

Set up your View Controllers to display the mock data from the controllers.

#### Submit TestFlight

Submit your build to TestFlight, even though it is not fully functional yet. After you get approved, continue pushing builds throughout the rest of the process.

#### Implement Controllers - 2 days

Implement the functionality of the controllers so that they work with live data.

#### Polish Visual Design and Features - Any Remaining Time

Make the app look good and function the way you want it to.


## Contributions

Please refer to CONTRIBUTING.md.

## Copyright

© DevMountain LLC, 2015. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.
