# Local Storage Chatty

## Setup

One teammate create a Github repository and add the others as collaborators.

## Requirements

Check out the [simple wireframe](https://app.moqups.com/chortlehoort/uGBbLbK46Y/view/page/a3bd0c733) for this application on Moqups.com. You can make your final interface as fancy as you like, but keep the general layout similar to the wireframe.

### Navigation bar

1. Create an element to serve as the navigation bar for your application.
1. Create an element to hold the logo for your application. It can be as simple as text, but if you want to find an image, that's fine.
1. Create a input field for a user to enter in a message.
1. Add an event listener for "keypress" and detect when then return key has been pressed in the message field.
1. When return key is detected, you'll create a new message (*see details below*).
1. Create a button to clear all messages.
1. When the user clicks the clear messages button, all current chat messages should be removed from the application.
1. If there are no messages, then the clear messages button should be disabled (*see example above*).
1. The navigation bar should remain at the top of the screen, even if the contents of the page start to scroll.

### Options

1. Create two checkboxes below the message input field. One labeled "Dark theme" and the other labeled "Large text".
1. When the user clicks on the dark theme checkbox, change the background color of your application to a dark gray, and the font color for messages should be white(ish)... you pick.
1. If the user unchecks the box, the background color should change back to white with black text for messages.

### Messages

1. When the page is first loaded, you must load messages from a local storage database and pre-fill a message area `<div>` below the input field that will also hold all new messages as they get created.
1. When the user presses the return key in the message field, the new message should be inserted into the message area. Local storage should also be updated with the new message.
1. Put a timestamp on each message.
1. The message should have a button displayed after it with the text "Delete" inside of it.
1. When the delete button next to a message is clicked, only that message should be removed from the DOM.

### Local Storage

Store the following information in a local storage database.

1. Users
1. User messages
1. User preferences (theme, font size, etc.)

### Single Responsibility

Make sure you define the actors in your application. For example, one actor manages reading/writing from local storage - the `DatabaseManager` object. Create as many JavaScript files as necessary to comply with the Single Responsibility Principle.

1. Database interactions
1. Establishing event handlers
1. Manipulating DOM

etc...

## Helpful hints

### Adding listeners to dynamically created elements

When you add a DOM element to your page with JavaScript, you cannot add a listener to them directly in your code with `addEventListener`. This is because the element didn't exist when your JavaScript file got parsed and executed by the browser when it loaded. What you need to do is listen for the event on the `<body>` element, and then inspect what the target of the event is (i.e. which element the user actually performed the action on).

```js
document.querySelector("body").addEventListener("click", function(event) {
  console.log(event);

  // Handle the click event on any li
  if (event.target.tagName.toLowerCase() === "li") {
    console.log("You clicked on an <li> element");
  }

  // Handle the click event on any DOM element with a certain class
  if (event.target.className === "article-section") {
    console.log("You clicked on an `article-section` element");
  }

  // Inspect the `id` property of the event target
  if (event.target.id === "page-title") {
    console.log("You clicked on the page-title element");
  }
});
```

### Setting element attributes

You can use JavaScript to [set any attribute](https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute) on a DOM element. You've seen how to add/remove classes with `classList.add()`, `classList.remove()`, and `classList.toggle()`, but you can also add `id`, `href`, `src`, or any other attribute.

Here's an example of how to add a `disabled` attribute to a button in the DOM.

```html
<button class="clear-messages">Clear messages</button>
```

```js
// This will disable the first button with a class of "button-message"
document.getElementsByClassName("clear-messages")[0].setAttribute("disabled", true);
```

## Advanced Challenges

For you overachievers, once you've completed the basic criteria, take a stab at these.

### Editing

1. Let users edit an existing message. Add an edit button next to the delete button that, when clicked, will take the message and put it back in the message input at the top.
1. Once user edits the message and presses the return key again, the message text in the list should be updated.

### Custom themes

1. Add a button/link to the UI labeled "Change Theme".
1. Remove the existing elements for changing the theme.
1. When user click on Change Theme element, show a Bootstrap modal dialog box.
1. Inside the modal, show two color picker fields - one for background color and one for font color.
1. Add a *Save* and *Cancel* button to modal.
1. When user clicks *Save* apply the chosen colors.

### Message limit

Only show the last 20 messages.
