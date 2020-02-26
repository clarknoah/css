# Advanced CSS Selectors
Today, we are going to learn about using advanced selectors in CSS.

## Prerequisites
In order to find the following instruction meaningful, it is important you are familiar with the following:

* Inline styling
* CSS Stylesheets
* Class, ID, and Tag Selectors

:question: What are the different types of CSS selectors we've been taught so far?

## Objectives
By the end of this instruction, you should know how to do the following:

* Know how to identify and create combinator selectors
* Know the required syntax to use all of the different types of combinator selectors

## Key Terms
Below are the concepts we will be learning about today

### Concepts
* Simple Selector
* Combinator Selector
* AND selector (Spaceless Selector)
* descendant selector (space)
* Child selector (>)
* adjacent sibling selector (+)
* general sibling selector (~)

### CLI Commands
**NONE**

### Language Syntax (CSS)
* `.selector.selector {}` (AND Selector)
* `selector selector {}` (descendant Selector)
* `selector > selector {}` (Child Selector)
* `selector + selector {}` (Adjacent Sibling Selector)
* `selector ~ selector {}` (General Sibling Selector)


## Combinator Selectors
Up until now, you've only been exposed to `simple selectors`, or selectors that only have ONE selector, such as in the example below:
```CSS
.simpleSelector {
  border: 4px solid pink;
}

#simpleSelector {
  border: 4px solid brown;
}

simpleSelector {
  border: 4px solid orange;
}

[simpleAttribute="simple"] {
  border: 4px solid green;
}
```

`Combinator selectors` are selectors which combine two or more `simple selectors` in order to create complex selection rules for elements.

#### (I Do) Demonstrate Descendant Combinator Selector
I'm going to give a quick demo of a combinator selector in action.


### AND Selector (Spaceless Selector)
The first `combinator selector` that we're going to look at I like to call an `AND selector`, because the way it works is like so:
> Select all elements that match `selector1` AND `selector2` AND `selector2`

Here is an example of just such a selector:

```CSS
andSelector#amazing[andSelector="wow"].combinee{
  border: 10px dashed teal;
  display: block;
}
```
Holey moley that is a lot of selectors **WITH NO SPACES**. This selector works fine and well if you're only dealing with a single `tag selector`, but what if I want apply this selector to multiple tags?

:question: How do we solve this problem? Does `h1h2 {}` work?

#### (We Do) Use the AND Selector to assign borders
There are four elements in the `AND Selector` section of the HTML. We are going to create an `And Selector` for each `div`, relying on the classes and IDs to user the `AND selector`.

:question: What is an `AND Selector`?

### Aggregate Selector (Comma Selector)
Aggregate selectors are quite simple. You provide a comma separated list of selectors, and whatever styling rules you add will apply to ALL elements that match ANY of the selectors.

#### (You Do) Assign all text to font
For all elements that contain text (such as `h1` and `pre`), use the aggregate selector to set the font to `arial`.


### Descendant Selector (Space Selector)
`Descendant Selectors` are used to select elements **WITHIN** other elements. For example, take the sample HTML code below:
```HTML
<div>
  <p>Hello</p>
</div>
<main>
  <p>Hi</p>
</main>
```
Lets say I want to only select the `p` elements which are within `div`, the `descendant selector` gives me the ability to do this, like so:
```css
div p {
  color: blue;
}
```
#### (We do) Use a `Descendant Selector` to select `p` and `h5` on lines 71-72
Inside our `example.html` file, let's use a `descendant selector` in order to color the `p` & `h1` elements' text to blue. We only want to select `divs` though that are contained with the element that has the id of `descendant`. The selector should look like this:

```css
#descendant div p,h1 {
  color: blue;
}
```
The first selector says:
> First, select only element that have the ID of `descendant`

The second selector says:
>Within the `id=descendant` element, select all `div` elements

The last selector says:
> Within `div` elements that are nested in `id=descendant`, apply the styling rules to all `p` elements.

The LAST selector will be used as the element in which the rule is applied.


### General Sibling Selector
Moving on to the `general sibling selector`, this selector lets us select ALL elements that are `siblings` of the provided selector. Note that this only selects siblings that are **AFTER** the initial selector. Lets see how this actually looks in real life.

```css
div ~ p {
  background-color: gray;
}
```
:question: What does this selector do?
#### (You do) Set ALL `div` elements background colors to `gray` after line `97` (within the element with id `general`)

I want YOU now to create your own selector to accomplish the above task, and then report to me once you have it working!

### Adjacent Sibling Selector
This type of selector is a more specific application of the previous one
#### (You do) Set **LAST** div to a background color of `gray`
Within the Adjacent Sibling Selector element (line 95), determine a way to select the last `div`

### Child Selector
This selector will seem quite similar to the `descendant selector`, the major difference is that the CSS rules here only apply to `direct child`, AKA, the immediate sub elements of the selector. Lets look at an example:

```CSS
div > p {
  color: red;
}
```
```html
<div>
  <p>wow
    woah
  </p>
</div>
```

#### (We Do) Applying `child selector`
We are now going to apply what we have learned, and select only the `p` element on line 113 using the `child selector`.

## Summary
Today, we have learn a lot about the six different types of combinator selectors, who can recall what some of these selectors are and how we used them in our demo?
