# README #

To view this a nicer layout visit:
[GitHub README](https://github.com/jtphelan/foundation-d8)

This is a Simple Drupal 8 Theme using Foundation 6 with the Classy Theme as a base.
[Flex Grid Documentation](http://foundation.zurb.com/sites/docs/flex-grid.html)
[Navbar Docs](http://foundation.zurb.com/sites/docs/top-bar.html)


## Foundation 6 Drupal 8 Theme ##

### Basics ###

The structure of the flex grid is identical to that of the float grid. Rows use the class .row, and columns use the class .column (or .columns). Basic percentage-based sizing can also be done using the same grid classes you're used to: .small-6, .medium-12, and so on.

```HTML
<div class="row">
  <div class="small-6 columns">6 columns</div>
  <div class="small-6 columns">6 columns</div>
</div>
<div class="row">
  <div class="medium-6 large-4 columns">12/6/4 columns</div>
  <div class="medium-6 large-8 columns">12/6/8 columns</div>
</div>
```

### Advanced Sizing ###

If no sizing class is added to the column, it will simply expand to fill the leftover space. We call this an expand behavior.
A column can also be made to shrink, by adding the .shrink class. This means it will only take up the horizontal space its contents need.

```HTML
<div class="row">
  <div class="small-4 columns">4 columns</div>
  <div class="columns">Whatever's left!</div>
</div>

<div class="row">
  <div class="shrink columns">Shrink!</div>
  <div class="columns">Expand!</div>
</div>
```

### Responsive Adjustments ###

Columns in a flex grid will not wrap if not given an explicit size—this is what allows the magical auto-sizing to work. To make columns stack on smaller screens, add the class .small-12 manually.

To switch back to the expand behavior from a percentage or shrink behavior, use the classes .medium-expand or .large-expand. In the below example, the columns stack on small screens, and become even-width on large screens.

```HTML
<div class="row">
  <div class="small-12 large-expand columns">One</div>
  <div class="small-12 large-expand columns">Two</div>
  <div class="small-12 large-expand columns">Three</div>
</div>
```

### Automatic Stacking ###

We have a few shorthand classes for the above behavior. Use the .[size]-unstack classes to stack all columns in the row by default, and then unstack them on a larger screen size, making each one equal-width.

```HTML
<div class="row medium-unstack">
  <div class="columns">One</div>
  <div class="columns">Two</div>
  <div class="columns">Three</div>
</div>
```

### Column Alignment ###

Columns in a flex grid can be aligned across the horizontal or vertical axis of their parent row.

Columns can be aligned the same way you would align text in a paragraph. By default, all columns align to the left (or the right in RTL), but this can be overridden with by adding the .align-[dir] class to the flex row. You might be wondering what the difference between .align-justify and .align-spaced is. A justified grid (justify-content: space-between) evenly distributes the space between each column. The first and last columns pin to the edge of the grid. A spaced grid (justify-content: space-around) evenly distributes the space around each column. This means there will always be space to the left of the first column, and to the right of the last column. The horizontal alignment classes are shorthands for the justify-content CSS property.

```HTML
<div class="row">
  <div class="column small-4">Aligned to</div>
  <div class="column small-4">the left</div>
</div>
<div class="row align-right">
  <div class="column small-4">Aligned to</div>
  <div class="column small-4">the right</div>
</div>
<div class="row align-center">
  <div class="column small-4">Aligned to</div>
  <div class="column small-4">the middle</div>
</div>
<div class="row align-justify">
  <div class="column small-4">Aligned to</div>
  <div class="column small-4">the edges</div>
</div>
<div class="row align-spaced">
  <div class="column small-4">Aligned to</div>
  <div class="column small-4">the space around</div>
</div>
```

By default, all columns in a flex grid stretch to be equal height. This behavior can be changed with another set of alignment classes. That's right, middle alignment in CSS! Your options for vertical alignment are top, middle, bottom, and stretch. Note that we use the word middle for vertical alignment, and center for horizontal alignment. Applying a vertical alignment class to the flex row will affect every column directly inside it.

```HTML
<div class="row align-middle">
  <div class="columns">I'm in the middle!</div>
  <div class="columns">I am as well, but I have so much text I take up more space! Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quis facere ducimus earum minus, inventore, ratione doloremque deserunt neque perspiciatis accusamus explicabo soluta, quod provident distinctio aliquam omnis? Labore, ullam possimus.</div>
</div>
```

 Similar alignment classes can also be applied to individual columns, which use the format .align-self-* instead of .align-*.

```HTML
<div class="row">
  <div class="column align-self-bottom">Align bottom</div>
  <div class="column align-self-middle">Align middle</div>
  <div class="column align-self-top">Align top</div>
  <div class="column">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non harum laborum cum voluptate vel, eius adipisci similique dignissimos nobis at excepturi incidunt fugit molestiae quaerat, consequuntur porro temporibus. Nisi, ex?</div>
</div>
```
Central alignment can be applied to a flex parent, which will centrally align all children horizontally and vertically automatically. To set this to your layout, simply use the class: .align-center-middle.

```HTML
<div class="row align-center-middle" style="height: 200px;">
  <div class="column small-4">I am in the center-middle</div>
  <div class="column small-4">I am also centrally located</div>
</div>
```

### Collapse/Uncollapse Rows ###

The .collapse class lets you remove column gutters (padding).

There are times when you won't want each media query to be collapsed or uncollapsed. In this case, use the media query size you want and collapse or uncollapse and add that to your row element. Example shows no gutter at small media size and then adds the gutter to columns at medium. The .is-collapse-child class removes negative margins from nested row under collapsed parent.

```HTML
<div class="row small-collapse medium-uncollapse">
  <div class="small-6 columns">
    Removes gutter at small media query and adds at medium.
  </div>
  <div class="small-6 columns">
    Removes gutter at small media query and adds at medium.
  </div>
</div>
```

### Offsets ###
Offsets work identically to the float grid, by applying margin-left to a column.

```HTML
<div class="row">
  <div class="small-4 large-offset-2 columns">Offset 2 on large</div>
  <div class="small-4 columns">4 columns</div>
</div>
```

### Block Grids ###

To define column widths at the row-level, instead of the individual column level, add the class .[size]-up-[n] to a row, where [n] is the number of columns to display per row, and [size] is the breakpoint at which to apply the effect.

```HTML
<div class="row small-up-1 medium-up-2 large-up-3">
  <div class="column">1 per row on small</div>
  <div class="column">2 per row on medium</div>
  <div class="column">3 per row on large</div>
</div>
```

### Source Ordering ###
Flexbox supports source ordering, making it easy to rearrange columns on different screen sizes without weird relative positioning tricks. Columns within a row will be sorted by their order property. Lower numbers are placed first. If multiple columns have the same number, they're sorted in the order they appear in the HTML. We have a set of classes that make it easy to setup source ordering in your HTML. They also come in responsive flavors, allowing you to reorder a grid on different screen sizes.

```HTML
<div class="row">
  <div class="column small-6 small-order-2 medium-order-1">
    This column will come second on small, and first on medium and larger.
  </div>
  <div class="column small-6 small-order-1 medium-order-2">
    This column will come first on small, and second on medium and larger.
  </div>
</div>
```

### Vanilla Flexbox Helper Classes ###

Foundation also includes some helper classes for quickly applying flex container & direction attributes to elements.

To make something a flex container, simply apply

* `.flex-container`

And to change its flex direction from row to column you can use the helper classes:

* `.flex-dir-row` (default)
* `.flex-dir-row-reverse`
* `.flex-dir-column`
* `.flex-dir-column-reverse`

For children, there are 3 quick helper classes to apply the flex property. These control how the containers take up space relative to their siblings:

* `.flex-child-auto` (auto size flex child)
* `.flex-child-grow` (flex child that will grow to take up all possible space)
* `.flex-child-shrink` (flex child that will shrink to minimum possible space)

### Show by Screen Size ###

In this example, we use the .show visibility classes to show certain strings of text based on the device on which users view a page. If their browser meets the class's conditions, the element will be shown. If not, it will be hidden.

```HTML
<p>You are on a small screen or larger.</p>
<p class="show-for-medium">You are on a medium screen or larger.</p>
<p class="show-for-large">You are on a large screen or larger.</p>
```

These classes automatically hide the element on screen sizes below what's specified in the class. So `.show-for-medium` will hide the element on small, and show it on medium and larger. A separate set of classes allow you to show content only on a certain screen size. Just add `-only` to the end of the class.

```HTML
<p class="show-for-small-only">You are <em>definitely</em> on a small screen.</p>
<p class="show-for-medium-only">You are <em>definitely</em> on a medium screen.</p>
<p class="show-for-large-only">You are <em>definitely</em> on a large screen.</p>
```

### Hide by Screen Size ###

This example shows the opposite: It uses the .hide visibility classes to state which elements should disappear based on the device's screen size. There's no `.hide-for-small` class, because that would just permanently hide the element. For that, you can use the plain old `.hide` class instead.

```HTML
<p class="hide-for-medium">You are <em>not</em> on a medium screen or larger.</p>
<p class="hide-for-large">You are <em>not</em> on a large screen or larger.</p>
```

Like with .show, these classes also have -only versions.

```HTML
<p class="hide-for-small-only">You are <em>definitely not</em> on a small screen.</p>
<p class="hide-for-medium-only">You are <em>definitely not</em> on a medium screen.</p>
<p class="hide-for-large-only">You are <em>definitely not</em> on a large screen.</p>
```

### Generic Hide Classes ###

And if you really just need something hidden no matter what, there are classes for that as well. The `.hide` and `.invisible` classes respectively set `display: none` and `visibility: hidden` on an element. Note that both of these classes hide content from screen readers.

```HTML
<p class="hide">Can't touch this.</p>
<p class="invisible">Can sort of touch this.</p>
```

### Accessibility ###
Adding `display: none` to an element will prevent screen readers from reading it. However, there are techniques to hide content while still making it readable by screen readers.

#### Show for Screen Readers Only ####

To visually hide content, while still allowing assistive technology to read it, add the class `show-for-sr`.

```HTML
<p class="show-for-sr">This text can only be read by a screen reader.</p>
<p>There's a line of text above this one, you just can't see it.</p>
```

#### Hide for Screen Readers Only ####

To hide text from assistive technology, while still keeping it visible, add the attribute `aria-hidden="true"`. This doesn't affect how the element looks, but screen readers will skip over it. It's usually not a good idea to hide content from screen readers. `aria-hidden` is best used to mask purely visual elements of a page.

```HTML
<p aria-hidden="true">This text can be seen, but won't be read by a screen reader.</p>
```

### Float Left/Right ###

You can change the float behavior of an element by adding the `.float-left` or `.float-right` classes to an element. To clear floats, add the class `.clearfix` to the parent element.

```HTML
<div class="callout clearfix">
  <a class="button float-left">Left</a>
  <a class="button float-right">Right</a>
</div>
```

Okay, it's not really a float, but you can add the `.float-center` class to an element to engage the automatic margin centering trick. Note that this will only work on elements with an absolute width, which means not a percentage or auto width.

`<img src="assets/img/generic/voyager.jpg" class="float-center">`

### Text Alignment ###

You can change the text alignment of an element by adding `.text-left`, `.text-right`, `.text-center` or `.text-justify` to an element.

Adding a breakpoint to the front of a text alignment class will cause it to only be applied on that size screen or larger. For example, `.medium-text-center` will keep text left-aligned on the smallest screens, but switch to center-aligned on medium screens and larger.

```HTML
<p class="text-left"><!-- ... --></p>
<p class="text-right"><!-- ... --></p>
<p class="text-center"><!-- ... --></p>
<p class="text-justify"><!-- ... --></p>
```

### Lead Paragraph ###

A slightly-larger-than-normal block of text, useful for decks, blurbs, or other descriptive text.

`<p class="lead">What are your cats <em>really</em> dreaming about while they sleep?</p>`

### Un-bulleted List ###

In Foundation, the <ul> is a bulleted list and <ol> is a numbered list by default, but you can add the class `.no-bullet` to remove the bullets and numbers respectively.

```HTML
<ul class="no-bullet">
  <li>List item with a much longer description or more content.</li>
  <li>List item</li>
  <li>List item</li>
</ul>
```

## Buttons ##
[Button Documentation](http://foundation.zurb.com/sites/docs/button.html)

### Basics ###

A basic button can be created with minimal markup. Because buttons can be used for many purposes, it's important to use the right tag.

```HTML
<!-- Anchors (links) -->
<a href="about.html" class="button">Learn More</a>
<a href="#features" class="button">View All Features</a>

<!-- Buttons (actions) -->
<button type="button" class="success button">Save</button>
<button type="button" class="alert button">Delete</button>
```

### Sizing ###

Additional classes can be added to your button to change its size and shape.

```HTML
<a class="button tiny" href="#">So Tiny</a>
<a class="button small" href="#">So Small</a>
<a class="button" href="#">So Basic</a>
<a class="button large" href="#">So Large</a>
<a class="button expanded" href="#">Such Expand</a> <!-- Full Width -->
<a class="button small expanded" href="#">Wow, Small Expand</a>
```

### Coloring ###

Add color classes to give buttons additional meaning.

```HTML
<a class="button primary" href="#">Primary</a>
<a class="button secondary" href="#">Secondary</a>
<a class="button success" href="#">Success</a>
<a class="button alert" href="#">Alert</a>
<a class="button warning" href="#">Warning</a>
```

### Hollow Style ###

Add the `.hollow` class to a button to give it a hollow style. 

```HTML
<button class="hollow button" href="#">Primary</button>
<button class="hollow button secondary" href="#">Secondary</button>
<button class="hollow button success" href="#">Success</button>
```

### Disabled Buttons ###

The `.disabled` class will give buttons a faded appearance. The class is a purely visual style, and won't actually disable a control. For <button> elements, you can add the `disabled` attribute to both disable and style it. If you want to disable a link, you should add the `aria-disabled` attribute to mark it as disabled for assistive technology.

```HTML
<a class="button disabled" href="#" aria-disabled>Disabled</a>
<button type="button" class="button primary" disabled>Disabled</button>
<button type="button" class="button success" disabled>Disabled</button>
<button type="button" class="button alert" disabled>Disabled</button>
```

### Dropdown Arrows ###

Add a dropdown arrow to your button with the `.dropdown` class. This doesn't add dropdown functionality automatically. To do that, you can attach our Dropdown plugin.

```HTML
<button class="dropdown button tiny">Dropdown Button</button>
<button class="dropdown button small">Dropdown Button</button>
<button class="dropdown button">Dropdown Button</button>
<button class="dropdown button large">Dropdown Button</button>
<button class="dropdown button expanded">Dropdown Button</button>
```