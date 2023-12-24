# Overview
This To-Do App is built using Vue.js and is organized into several components to enhance modularity and maintainability. The main components include:

`App.vue`: The main Vue component that serves as the entry point for the application. It incorporates and manages other components to create the complete To-Do App.

`summary.vue`: This component displays a summary of the to-do items. It imports and uses `summaryItem.vue` to render individual summary items.

`summaryItem.vue`: This component represents an individual to-do item within the summary. It is used by `summary.vue` to display a concise overview of each task.

`form.vue`: This component contains a form for adding new to-do items. It provides an interface for users to input task details and submit them to be added to the to-do list.

`toDoList.vue`: The main container for displaying the list of to-do items. It incorporates both ToDoItem.vue and DoneItem.vue components to display active and completed tasks.

`toDoItem.vue`: This component represents an active to-do item. It is used by ToDoList.vue to display tasks that are yet to be completed.

`doneItem.vue`: This component represents a completed to-do item. It is used by ToDoList.vue to display tasks that have been marked as done.
