# HTML Forms and JS Events

Getting more input from our users.

## HTML Forms

**Why are forms so important in web development?**

>*They are a convenient way for users to provide input that can then be processed by the applicable code. Seems way better than a bunch of prompt pop-ups.*

**When designing a form, what are some key things to keep in mind when it comes to user experience?**

>*Keep it simple. Keep it as short as you can. Make it unambiguous with clear labels. Think about the last time you went to your doctor's office. Don't do that. Also keep accessibility in mind by using proper form elements.*

**List 5 form elements and explain their importance.**

>*`<form>`: this is the parent elements that contains all other form elements. Kinda like a table element contains table stuff.  `<fieldset>`: creates a "section" within a form of related items. For example, this could be an area of an order form where you select the color of an item you are purchasing. `<legend>`: this is basically a label for a fieldset. `<input>`: creates a field for the user to enter their information... this can be a text box, selector, radio button, etc. `<label>`: displays a label for different areas of the form such as the selector or input fields. Using these well is important for user accessibility tool like screen readers.*

## JS: Introduction to Events

**How would you describe events to a non-technical friend?**

>*I probably wouldn't, but if push came to shove, I would tell them that events when something happens in the program being run that is caused by something extrenal to the program itself. For example on a website, an event could be somebody submitting a form or clicking the cancel order button.

**When using the `addEventListener()` method, what 2 arguments will you need to provide?**

>*A string indicating the event being monitored and a function to execute when the even occurs.*

**Describe the event object. Why is the target within the event object useful?**

>*An event object is an item that is being manipulated to cause an event (like a button). AN event target is a parameted of that function, which causes the function to act upon the event object such as changing color, which in this case is helpful for the end user to recognize that the input has been received.*

**What is the difference between event bubbling and event capturing?**

>*This confused me a little. I get that event capturing is the reverse of event bubbling, and has to do with an event object being nested inside other elements, but I'm not sure I get hpw we use this, yet.*

## Things I want to know more about

*I'm stoked to replace prompts with forms.*
