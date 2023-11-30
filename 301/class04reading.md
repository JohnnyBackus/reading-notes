# React and Forms

Just when you thought your brain couldn't melt anymore... time to revisit forms

## How to use Forms in React

**What is a ‘Controlled Component’?**

>*A 'Controlled Component' uses the 'State' (and 'setState') to populate inputs and outputs.*

**Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.**

>*As a user, I prefer forms that update the state in real time so I can get feedback (such as whether I entered a real email address or made a typo), before I submit the form and half to scroll back to make corrections. As an developer, I presume it's easier to handle a form that waits to update the state until after submission.*

**How do we target what the user is entering if we have an event handler on an input field?**

>*`event.target.value`*

## The Conditional (Ternary) Operator Explained

**Why would we use a ternary operator?**

>*Save a bunch of keystrokes.*

**Rewrite the following statement using a ternary statement:**

```javascript
if(x===y){
  console.log(true);
} else {
  console.log(false);
}
```

>*Using a ternary statement the preceding code can be written...*

```javascript
console.log(x===y ? true : false);
```

## Things I want to know more about

>*Looks like nested ternary forms can get unwieldy and difficult to read compared to repeating if statements... I wonder what the record is for most nested ternary statements.*
