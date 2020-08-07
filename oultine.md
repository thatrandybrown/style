# CSS

## Agenda



* CSS Object Model
* How the CSSOM is Built
    * sources
    * selectors
    * inheritance
* Reconciliation for Render Tree
* The Box Model and Sizing
* Q&A








## The CSS Object Model





* Code Tour
* The Shape of CSS









## How the CSSOM is Built

### Sources





* User Agent Styles
* User Styles
* Author Styles




*** demo: changing font sizes ***
*** `body {font-size: 10px;}` ***
*** show all ***


### Selectors

#### CSS Performance Focus



* focusing on object model build vs style reconciliation

* What is actually performance intensive for CSS?
* How to performance optimize CSS
* When to performance optimize CSS

* How to write CSS that is easy to reason about







#### type & pseudo-element

Types
* h1
* p
* section

Pseudo-elements
* ::before & ::after
* ::first-line && ::first-letter


```css
dl > dd::after {
    content: " | "
}
```

*** boxing the first letter of every paragraph ***

#### class & pseudo-class



* :first-child
* :last-child
* :focus
* :visited
* :target

```css
:target {
    color: green;
    border: thin solid cornflowerblue;
}
```

#### id







Enter Spiderman



*** ids are for more than just styles ***



#### How Selectors work:

Compare:

```css
main > section:first-of-type > p:first-of-type::first-letter {
    font-size: 3rem;
}

main:first-child > p:first-of-type::first-letter {
    font-size: 2rem;
}
```

*** selector weight is compared at each level ***

#### Are Selectors Specificity?



* inline styles
* id
* class, attribute, pseudo-class
* element and pseudo-element




***A note on `*, {+,~,>,:not}` impact on specifity score***



### Inheritance

#### How Inheritance Works

Looking at the `body > *` selector:

```css
body {
    display: grid;
}

body > * {
    padding: 0.25rem;
}
```

Why can't we combine these?

#### Where Does Inheritance Apply?






* color
* font
* other stuff




*** `body { color: green; }` ***


#### What Doesn't Inherit?




* background-color
* border
* margins
* padding
* other stuff
* @ rules



*** `body {background-color: 'yellow'}` ***
*** `body {border: 'thin red solid'}` ***


#### Changing Default Rule Behavior

##### Changing Behavior






* inherit
* initial





*** `body > * {all: inherit}` *** 

##### Changing Value





* unset: return to default value
* revert: return to previous value from parent or origin

*** a note about `all` ***





## CSS Rule Reconciliation: The Cascade

### What Actually is The Cascade







How we determine which attribute value gets assigned to a property for a given element







### How are Rules Selected




* Move down the tree
* recursively select branches with more *specific* rules




*** a note on the relationship between tree depth and specificity ***


### Cascade Factors


1. Origin
    * Author
    * User
    * User Agent
    *** a note on importance ***
    *** a note on animations and transitions ***
    *** a note on inherited and initial values ***
    *** a note on font styles ***   
2. Selector Specificity
3. Order of Appearance




## Managing Default Styles

### CSS Attribute Resets






* inherit
* initial







### What are the Browser Defaults



* CSS Spec
* Internal values
    * colors
    * borders
    * fonts
    * system settings




*** demo: show all ***



### Resetting CSS




```css
* {
    all: unset;
}
```

*** a note on effective targetting for DIY resets ***




### Industry Reset Options





* Marx
* HTML5 Reset
* typeset








### DRY, Resets, and Normalization




* The difference between reset and normalization

* Options:
    * Normalize
    * Sanitize






## The Box Model and Sizing

### Elements of the Box





* margin
* border
* padding
* content



*** a note about margin collapse ***



### Box Sizing






* content-box
* border-box








### Units of Measure

#### Static Units of Measure for Websites







An ode to the reference pixel








#### Dynamic Units of Measure

* %: dependent on container
* vh
* vw
* vmax, vmin

* em: dependent on container
* rem

```css
* > * {
    font-size: 1.1em;
}
```

#### Physical Units





* cm
* mm
* pc
* pt
* in

*** for use with print styles ***



 



#### When to Use What?



* media=print
* html font=100% to allow user settings
* px for:
    * things that shouldn't scale with screen / container size or font
    * brand identity
    * margins and padding sometimes
* vh / vw for things that should scale with the screen
* rem / em for things that should scale with font





## Q&A





* Questions
* Comments
* Thoughts
* Observations
* Ideas





