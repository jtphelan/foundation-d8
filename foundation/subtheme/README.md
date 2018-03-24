# README #

To view this a nicer layout visit:
[GitHub README](https://github.com/jtphelan/foundation-d8)

This is a Simple Drupal 8 Theme using Foundation 6 with the Classy Theme as a base.
[Flex Grid Documentation](http://foundation.zurb.com/sites/docs/flex-grid.html)
[Navbar Docs](http://foundation.zurb.com/sites/docs/top-bar.html)


## Foundation 6 Drupal 8 Theme ##

### Basics ###

The structure of XY grid uses `.grid-x`, `.grid-y`, and `.cell` as its base. Without defining a gutter type the cells will simply split up the space without any gutters.

```HTML
<div class="grid-x">
  <div class="cell">full width cell</div>
  <div class="cell">full width cell</div>
</div>
<div class="grid-x">
  <div class="cell small-6">6 cells</div>
  <div class="cell small-6">6 cells</div>
</div>
<div class="grid-x">
  <div class="cell medium-6 large-4">12/6/4 cells</div>
  <div class="cell medium-6 large-8">12/6/8 cells</div>
</div>
```

### Gutters ###

The defining feature of the XY grid is the ability to use margin AND padding grids in harmony. To define a grid type, simply set `.grid-margin-x` or `.grid-padding-x` on the grid.

```HTML
<div class="grid-x grid-margin-x">
  <div class="cell medium-6 large-4">12/6/4 cells</div>
  <div class="cell medium-6 large-8">12/6/8 cells</div>
</div>
<div class="grid-x grid-padding-x">
  <div class="cell medium-6 large-4">12/6/4 cells</div>
  <div class="cell medium-6 large-8">12/6/8 cells</div>
</div>
```

### Auto Sizing ###

If the class `.auto` or `.[size]-auto` is added to the cell, it will take up the remaining space. Multiple expanding cells will share the leftover space equally. A cell can also be made to shrink, by adding the `.shrink` or `.[size]-shrink` class. This means it will only take up the space its contents need.

```HTML
<div class="grid-x grid-margin-x">
  <div class="cell small-4">4 cells</div>
  <div class="cell auto">Whatever's left!</div>
</div>
<div class="grid-x grid-margin-x">
  <div class="cell small-4">4 cells</div>
  <div class="cell auto">Whatever's left!</div>
  <div class="cell auto">Whatever's left!</div>
</div>
<div class="grid-x grid-margin-x">
  <div class="cell shrink">Shrink!</div>
  <div class="cell auto">Expand!</div>
</div>
```

### Responsive Adjustments ###

To switch back to the auto behavior from a percentage or shrink behavior, use the classes `.[size]-auto` or `.[size]-shrink`. In the below example, the cells stack on small screens, and become even-width on large screens.

```HTML
<div class="grid-x">
  <div class="cell large-auto">One</div>
  <div class="cell large-auto">Two</div>
  <div class="cell large-auto">Three</div>
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

Horizontal alignment classes are applied to flex parents. Left alignment is the default, but you can use one of these classes to change this. You might be wondering what the difference between .align-justify and .align-spaced is. A justified grid (justify-content: space-between) evenly distributes the space between each column. The first and last columns pin to the edge of the grid.

A spaced grid (justify-content: space-around) evenly distributes the space around each column. This means there will always be space to the left of the first column, and to the right of the last column.

The horizontal alignment classes are shorthands for the justify-content CSS property. 

```HTML
<div class="grid-x grid-padding-x"> <!-- Aligned to the left -->
  <div class="cell small-4">Aligned to</div>
  <div class="cell small-4">the left</div>
</div>
<div class="grid-x grid-padding-x align-right"> <!-- Aligned to the right -->
  <div class="cell small-4">Aligned to</div>
  <div class="cell small-4">the right</div>
</div>
<div class="grid-x grid-padding-x align-center"> <!-- Aligned to the center -->
  <div class="cell small-4">Aligned to</div>
  <div class="cell small-4">the center</div>
</div>
<div class="grid-x grid-padding-x align-justify"> <!-- Aligned to the edges -->
  <div class="cell small-4">Aligned to</div>
  <div class="cell small-4">the edges</div>
</div>
<div class="grid-x grid-padding-x align-spaced"> <!-- Aligned to the space around -->
  <div class="cell small-4">Aligned to</div>
  <div class="cell small-4">the space around</div>
</div>
```

Vertical alignment can be applied to a flex parent—which will align all the children automatically—or to a flex child, which will align only that element.

Stretch alignment is the default. To set parent alignment, use these classes:

`.align-top`
`.align-middle`
`.align-bottom`
`.align-stretch`

```HTML
<div class="grid-x grid-padding-x align-top">
  <div class="cell small-4">I'm at the top (default)</div>
  <div class="cell small-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, tempora. Impedit eius officia possimus laudantium? Molestiae eaque, sapiente atque doloremque placeat! In sint, fugiat saepe sunt dolore tempore amet cupiditate.</div>
</div>
<div class="grid-x grid-padding-x align-middle">
  <div class="cell small-4">I'm in the middle</div>
  <div class="cell small-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, tempora. Impedit eius officia possimus laudantium? Molestiae eaque, sapiente atque doloremque placeat! In sint, fugiat saepe sunt dolore tempore amet cupiditate.</div>
</div>
<div class="grid-x grid-padding-x align-bottom">
  <div class="cell small-4">I'm at the bottom</div>
  <div class="cell small-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, tempora. Impedit eius officia possimus laudantium? Molestiae eaque, sapiente atque doloremque placeat! In sint, fugiat saepe sunt dolore tempore amet cupiditate.</div>
</div>
<div class="grid-x grid-padding-x align-stretch">
  <div class="cell small-4">These cells have the same height</div>
  <div class="cell small-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, tempora. Impedit eius officia possimus laudantium? Molestiae eaque, sapiente atque doloremque placeat! In sint, fugiat saepe sunt dolore tempore amet cupiditate.</div>
</div>
```

To align an individual child, use the below classes. They use the same alignment terms as the parent-level classes, but the classes start with `.align-self-` instead of `.align-`.

```HTML
<div class="grid-x grid-padding-x">
  <div class="cell small-3 align-self-bottom"><div class="demo">Align bottom</div></div>
  <div class="cell small-3 align-self-middle"><div class="demo">Align middle</div></div>
  <div class="cell small-3 align-self-stretch"><div class="demo">Align stretch</div></div>
  <div class="cell small-3 align-self-top"><div class="demo">Align top. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non harum laborum cum voluptate vel, eius adipisci similique dignissimos nobis at excepturi incidunt fugit molestiae quaerat, consequuntur porro temporibus. Nisi, ex?</div></div>
</div>
```
Central alignment can be applied to a flex parent, which will centrally align all children horizontally and vertically automatically. To set this to your layout, simply use the class: `.align-center-middle`.

```HTML
<div class="grid-x grid-padding-x align-center-middle text-center" style="height: 200px;">
  <div class="cell small-4">I am in the center-middle</div>
  <div class="cell small-4">I am also centrally located</div>
</div>
```

### Collapse Cells ###

The `.[size]-[gutter-type]-collapse` class lets you remove cell gutters.

There are times when you won't want each media query to be collapsed. In this case, use the media query size you want and collapse and add that to your grid element. Example shows gutters at small and no gutters on medium and up.

```HTML
<div class="grid-x grid-margin-x medium-margin-collapse">
  <div class="cell small-6">
    Gutters at small no gutters at medium.
  </div>
  <div class="cell small-6">
    Gutters at small no gutters at medium.
  </div>
</div>
```

### Offsets ###

Offsets work by applying `margin-left` (or `margin-top` for a vertical grid) to a grid.

```HTML
<div class="grid-x grid-margin-x">
  <div class="cell small-4 large-offset-2">Offset 2 on large</div>
  <div class="cell small-4">4 cells</div>
</div>
```

### Block Grids ###

To define cell widths within a direction-level, instead of the individual cell level, add the class `.[size]-up-[n]` to a `grid-x` or `grid-y`, where `[n]` is the number of cells to display per direction, and `[size]` is the breakpoint at which to apply the effect.

```HTML
<div class="grid-x grid-padding-x small-up-2 medium-up-4 large-up-6">
  <div class="cell">cell</div>
  <div class="cell">cell</div>
  <div class="cell">cell</div>
  <div class="cell">cell</div>
</div>
```

### Source Ordering ###
Flexbox supports source ordering, making it easy to rearrange columns on different screen sizes without weird relative positioning tricks. Columns within a row will be sorted by their order property. Lower numbers are placed first. If multiple columns have the same number, they're sorted in the order they appear in the HTML. We have a set of classes that make it easy to setup source ordering in your HTML. They also come in responsive flavors, allowing you to reorder a grid on different screen sizes.

```HTML
<div class="grid-x grid-padding-x">
  <div class="cell small-6 small-order-2 medium-order-1">
    This column will come second on small, and first on medium and larger.
  </div>
  <div class="cell small-6 small-order-1 medium-order-2">
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

```HTML
<div class="grid-x grid-padding-x">
  <div class="cell small-4 flex-container flex-dir-column">
    <div class="callout primary flex-child-auto">Auto</div>
    <div class="callout primary flex-child-auto">Auto</div>
    <div class="callout primary flex-child-shrink">Shrink</div>
  </div>
  <div class="cell small-4">
  </div>
  <div class="cell small-4 align-self-top">Align top. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non harum laborum cum voluptate vel, eius adipisci similique dignissimos nobis at excepturi incidunt fugit molestiae quaerat, consequuntur porro temporibus. Nisi, ex?Align top. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non harum laborum cum voluptate vel, eius adipisci similique dignissimos nobis at excepturi incidunt fugit molestiae quaerat, consequuntur porro temporibus. Nisi, ex?Align top. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non harum laborum cum voluptate vel, eius adipisci similique dignissimos nobis at excepturi incidunt fugit molestiae quaerat, consequuntur porro temporibus. Nisi, ex?</div>
</div>
```

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

### Vertical Grids ###

The XY grid also supports vertical grids. Simply apply `.grid-y` instead of `.grid-x`. The internal cells will shift automatically to provide spacing vertically rather than horizontally.

You can also apply margin or padding with `.grid-margin-y` and `.grid-padding-y` to apply spacing to the top and bottom of cells.

Please note for vertical grids to work, the grid needs a height. You can also use grid frame to create a 100 vertical height grid (or 100% height if nested).

```HTML
<div class="grid-y" style="height: 500px;">
  <div class="cell small-6 medium-8 large-2">
    6/8/2
  </div>
  <div class="cell small-6 medium-4 large-10">
    6/4/10
  </div>
</div>
```

### Grid Frame ###

The XY grid incorporates the grid frame from Foundation for Apps plus many other useful features. To start, add `.grid-frame` to the grid. This sets the grid to be 100vh (the full height of the browser window).

Please note to use `.grid-margin-x` or `.grid-margin-y` with `.grid-frame` you need to hide the overflow on the body like so: `body {overflow: hidden;}`.

```HTML
<div class="grid-y medium-grid-frame">
  <div class="cell shrink header medium-cell-block-container">
    <h1>Grid Frame Header</h1>
    <div class="grid-x grid-padding-x">
      <div class="cell medium-4">
        A medium 4 cell
      </div>
      <div class="cell medium-4 medium-cell-block">
        <p style="width:80vw;">A medium 4 cell block... on medium this content should overflow and let you horizontally scroll across... one might use this for an array of options</p>
      </div>
      <div class="cell medium-4">
        A medium 4 cell
      </div>
    </div>
  </div>
  <div class="cell medium-auto medium-cell-block-container">
    <div class="grid-x grid-padding-x">
      <div class="cell medium-4 medium-cell-block-y">
        <h2>Independent scrolling sidebar</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer lacus odio, accumsan id ullamcorper eget, varius nec erat. Nulla facilisi. Donec dui felis, euismod nec finibus vitae, dapibus quis arcu. Maecenas tempor et ipsum quis venenatis. Ut posuere sed augue sit amet efficitur. Sed imperdiet, justo id tempus rhoncus, est est viverra turpis, non vulputate magna lectus et nisl. Pellentesque ultrices porttitor vehicula. Ut aliquet efficitur ligula, a consectetur felis. Proin tristique ut augue nec luctus. Curabitur a sapien pretium, auctor elit a, efficitur erat. Donec tincidunt dui vel velit bibendum euismod. Cras vitae nibh dui. Aliquam erat volutpat. Etiam sit amet arcu a erat efficitur facilisis. Ut viverra dapibus turpis, et ornare justo. Integer in dui cursus, dignissim tortor a, hendrerit risus.</p>

        <p>Suspendisse pulvinar, massa iaculis feugiat lobortis, dolor sapien vestibulum nulla, vel cursus tellus leo in lorem. Aliquam eu placerat urna. Suspendisse sed viverra orci, ut mattis neque. Fusce non ultrices nisi. In sagittis varius mollis. Quisque dolor quam, consectetur eu lacinia ac, ullamcorper vel arcu. Nullam mattis imperdiet nulla sed ornare. Praesent tristique, est id eleifend vestibulum, neque nibh condimentum ex, nec lobortis purus justo a libero. Phasellus id ex ac nunc hendrerit hendrerit. Nullam urna ipsum, rutrum at fringilla vel, venenatis non purus. Maecenas egestas ex vitae venenatis molestie. Ut et odio egestas, accumsan neque et, viverra nisl. Sed faucibus nec nulla sed imperdiet. Fusce quis sem ac urna semper tempor a id elit. Nulla fringilla vitae sapien a vehicula.</p>

      </div>
      <div class="cell medium-8 medium-cell-block-y">
        <h2>Independent scrolling body</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer lacus odio, accumsan id ullamcorper eget, varius nec erat. Nulla facilisi. Donec dui felis, euismod nec finibus vitae, dapibus quis arcu. Maecenas tempor et ipsum quis venenatis. Ut posuere sed augue sit amet efficitur. Sed imperdiet, justo id tempus rhoncus, est est viverra turpis, non vulputate magna lectus et nisl. Pellentesque ultrices porttitor vehicula. Ut aliquet efficitur ligula, a consectetur felis. Proin tristique ut augue nec luctus. Curabitur a sapien pretium, auctor elit a, efficitur erat. Donec tincidunt dui vel velit bibendum euismod. Cras vitae nibh dui. Aliquam erat volutpat. Etiam sit amet arcu a erat efficitur facilisis. Ut viverra dapibus turpis, et ornare justo. Integer in dui cursus, dignissim tortor a, hendrerit risus.</p>
        <p>Suspendisse pulvinar, massa iaculis feugiat lobortis, dolor sapien vestibulum nulla, vel cursus tellus leo in lorem. Aliquam eu placerat urna. Suspendisse sed viverra orci, ut mattis neque. Fusce non ultrices nisi. In sagittis varius mollis. Quisque dolor quam, consectetur eu lacinia ac, ullamcorper vel arcu. Nullam mattis imperdiet nulla sed ornare. Praesent tristique, est id eleifend vestibulum, neque nibh condimentum ex, nec lobortis purus justo a libero. Phasellus id ex ac nunc hendrerit hendrerit. Nullam urna ipsum, rutrum at fringilla vel, venenatis non purus. Maecenas egestas ex vitae venenatis molestie. Ut et odio egestas, accumsan neque et, viverra nisl. Sed faucibus nec nulla sed imperdiet. Fusce quis sem ac urna semper tempor a id elit. Nulla fringilla vitae sapien a vehicula.</p>
        <p>Nullam vestibulum lorem nec lectus egestas, nec ullamcorper diam maximus. Maecenas condimentum, nibh at blandit semper, ex erat tempus magna, id maximus neque velit accumsan nibh. Aenean dignissim lorem eu nisl laoreet vestibulum. Vivamus efficitur et augue vitae tincidunt. Etiam et magna felis. Integer mattis, nisi aliquet scelerisque blandit, ex mi sodales ante, eget accumsan quam magna et ligula. Curabitur id tristique leo. Proin rutrum mi vitae enim rhoncus, at cursus neque eleifend. Integer ultrices volutpat tellus ac porta. Fusce sollicitudin venenatis lacinia. Fusce ante lorem, gravida semper varius non, pharetra non erat. Sed dapibus arcu turpis, ac sollicitudin nibh lacinia vel. Nullam at enim porta, luctus metus sit amet, rutrum odio. Cras tempor enim vel pellentesque sollicitudin. Maecenas ullamcorper, sem non accumsan volutpat, neque tortor pulvinar orci, ut ultrices ligula lorem ut risus.</p>
        <p>Aliquam facilisis, nibh eget posuere suscipit, arcu sapien iaculis odio, in molestie dolor lectus vitae sem. Cras id nunc mollis mi rutrum dapibus. Quisque rutrum a augue at scelerisque. Praesent faucibus ac enim vitae gravida. Sed et sodales elit. Duis magna lectus, interdum sit amet metus a, sagittis varius magna. Proin nibh lectus, egestas a luctus ut, dapibus et enim. Curabitur fringilla ipsum vitae nunc imperdiet consectetur eget non neque. Suspendisse ultricies odio quis lorem vulputate, ac vulputate turpis feugiat. Maecenas posuere rhoncus orci, in ornare velit suscipit tempor. Curabitur pretium nisl id lorem placerat consequat. In quis quam eros. Nam mattis elit eu quam sagittis, in varius erat tempor.</p>
        <p>Fusce felis magna, pellentesque eget mollis a, rutrum id eros. Curabitur auctor varius arcu a consequat. Phasellus quis pulvinar enim, eu ultricies justo. Pellentesque risus libero, dapibus at erat ultricies, gravida varius erat. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nulla tempus, justo ut laoreet mollis, nunc tellus convallis urna, vel pretium dui velit eget ligula. Aliquam semper sed nulla a molestie. Maecenas at egestas massa, vitae aliquam mi. Fusce nec sem egestas, pretium lacus non, tincidunt sapien. Sed tristique odio at ultricies vulputate. Integer et convallis augue, eu aliquam enim. Mauris ut faucibus diam. Donec vulputate nunc sed congue accumsan. Etiam lobortis nisi quis lacinia pharetra.</p>
      </div>
    </div>
  </div>
  <div class="cell shrink footer">
    <h3>Here's my footer</h3>
  </div>
</div>
```