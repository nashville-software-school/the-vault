# Please Can I...

## A JavaScript Exercise

All children know the best way to get what they want is to pester their parents until they give in. The smartest children know that for the best results they should vary both their volume and the number of repetitions of their plea.

Your task is to build a web application that will help a child build their plea.

## Requirements

### Layout

1. The page should have a text box to accept the text of the child's plea. For example, "Please can I fill the tub with Mountain Dew? Please?!?!"

1. The page should have a dropdown box for selecting the number of repetitions for the plea. This dropdown should contains entries from the numbers 1 through 100.

1. The page should have an area for displaying the full text of the plea.

1. The page should have a button that when clicked should cause the text of the plea to be output to the page.

### Functionality

#### Phase One

 When the user enters text into the text box, selects a number of repetitions and clicks the button, then the page should show the text on a new line as many times as indicated by the number of repetitions.

For example, if the user enters a plea of "Gimme Candy!" and selects 5 in the repetitions dropdown, the page should display:

```html
Gimme Candy!
Gimme Candy!
Gimme Candy!
Gimme Candy!
Gimme Candy!
```

#### Phase Two

Modify your application to display every other plea in upper case.

For example:

```html
Gimme Candy!
GIMME CANDY!
Gimme Candy!
GIMME CANDY!
Gimme Candy!
```

#### Phase Three

Modify your application to display **random** pleas in upper case.

For example:

```html
GIMME CANDY!
Gimme Candy!
Gimme Candy!
GIMME CANDY!
GIMME CANDY!
```

#### Phase Four

Modify your application by adding an option to the repetitions dropdown that will cause the app to use a random number between 1 and 100 for the number of repetitions.

#### Phase Five

Style your app so that it's easy to use as well as aesthetically pleasing for a child.