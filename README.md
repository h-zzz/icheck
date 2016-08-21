<<<<<<< HEAD
# iCheck plugin v2.0 rc1
=======
# [iCheck plugin](http://fronteed.com/iCheck/) <sup>[1.0.2](#march-03-2014)</sup>
#### Highly customizable checkboxes and radio buttons for jQuery and Zepto.
>>>>>>> refs/remotes/origin/1.x

#### This is a release candidate version, you may try to use it.

<<<<<<< HEAD
Docs will be updated later, here's a short intro:
=======
**Note: [iCheck v2.0](https://github.com/fronteed/icheck/tree/2.x) is on the way**, it got a huge performance boost, many new options and methods. It's in a release candidate state, so you may try to use it. Feel free to submit an issue if you find something not working.

![Skins](http://fronteed.com/iCheck/examples.png)
>>>>>>> refs/remotes/origin/1.x

## Default options

**Notes:**

**global object**: `window.icheck = { options }`

**data attributes**: `<input data-checkedClass="mycheckedclass" type="checkbox" class="icheck">`

**init object**: `$('input').icheck({ options });`

#### These are global object options:

```
{
  // auto init on domready
  autoInit: true,

  // auto handle ajax loaded inputs (any inputs inside the HTML ajax-requests will be customized automatically)
  autoAjax: false,

  // fastclick plugin replacement, works without dependencies (removes a 300ms delay between a physical tap and the firing the changes on mobile browsers). Compatible with but doesn't require http://github.com/ftlabs/fastclick
  tap: true,

  // these are a default classnames used by icheck (# are replaced with classes.base)
  classes: {
    base: 'icheck', // classname to search for and customize
    div: '#-item', // classname to add for a styler div
    area: '#-area-', // classname to add to styler, when "area" option is used
    input: '#-input', // classname to add to original input
    label: '#-label' // classname to add to assigned labels
  },

  // global callbacks (if set to false, callback will never be fired)
  callbacks: {
    ifCreated: function() {
      // this is just an example
    }
  },
}
```

#### These options can be stored in data attributes and init object:

```
{
  // fastclick (http://github.com/ftlabs/fastclick) replacement, works without dependencies (removes a 300ms delay between a physical tap and the firing of a click event on mobile browsers)
  tap: true,

  // 'checkbox' or 'radio' to style only checkboxes or radio buttons, both by default
  handle: '',

  // base class added to customized checkboxes
  checkboxClass: 'icheckbox',

  // base class added to customized radio buttons
  radioClass: 'iradio',

  // class added on checked state (input.checked = true)
  checkedClass: 'checked',

    // if not empty, used instead of 'checkedClass' option (input type specific)
    checkedCheckboxClass: '',
    checkedRadioClass: '',

  // if not empty, added as class name on unchecked state (input.checked = false)
  uncheckedClass: '',

    // if not empty, used instead of 'uncheckedClass' option (input type specific)
    uncheckedCheckboxClass: '',
    uncheckedRadioClass: '',

  // class added on disabled state (input.disabled = true)
  disabledClass: 'disabled',

    // if not empty, used instead of 'disabledClass' option (input type specific)
    disabledCheckboxClass: '',
    disabledRadioClass: '',

  // if not empty, added as class name on enabled state (input.disabled = false)
  enabledClass: '',

    // if not empty, used instead of 'enabledClass' option (input type specific)
    enabledCheckboxClass: '',
    enabledRadioClass: '',

  // class added on indeterminate state (input.indeterminate = true)
  indeterminateClass: 'indeterminate',

    // if not empty, used instead of 'indeterminateClass' option (input type specific)
    indeterminateCheckboxClass: '',
    indeterminateRadioClass: '',

  // if not empty, added as class name on determinate state (input.indeterminate = false)
  determinateClass: '',

    // if not empty, used instead of 'determinateClass' option (input type specific)
    determinateCheckboxClass: '',
    determinateRadioClass: '',

  // class added on hover state (pointer is moved onto input)
  hoverClass: 'hover',

  // class added on focus state (input has gained focus)
  focusClass: 'focus',

  // class added on active state (pointer is pressed on input)
  activeClass: '',

  // if true, a mirror classes will be toggled between label and input tags (i.e. input is checked => checkedClass is added to input, checkedLabelClass is added to label)
  mirror: false,

  // classes to append to labels if "mirror" option is true
  checkedLabelClass: '',
  disabledLabelClass: '',
  indeterminateLabelClass: '',

  // same here
  hoverLabelClass: '',
  focusLabelClass: '',
  activeLabelClass: '',

  // true to set 'pointer' CSS cursor over enabled inputs and 'default' over disabled
  cursor: false,

  // callbacks (can't be stored in data attributes)
  callbacks: {
    ifCreated: function(node, settings) {
      // your code
    }
  },

  // comma separated attributes to inherit from the input to the wrapper div (note: input's id is prefixed with 'icheck-' (or a window.classes.base))
  inherit: '',

  // increase clickable area by given %
  area: 0,

  // add HTML code or text inside customized input
  insert: ''
}
```


## Methods

```
// checked = change input's state to 'checked'
$('input').icheck('checked', function(node) {
  // callback function will be fired for each input
  // node is the HTML node of the current input (can be used as $(node))
});

// unchecked = remove 'checked' state
$('input').icheck('unchecked', function(node) {
  // callbackfunction will be fired for each input
  // node is the HTML node of the current input (can be used as $(node))
});

// disabled = change input's state to 'disabled'
$('input').icheck('disabled', function(node) {
  // callbackfunction will be fired for each input
  // node is the HTML node of the current input (can be used as $(node))
});

// enabled = remove 'disabled' state
$('input').icheck('enabled', function(node) {
  // callbackfunction will be fired for each input
  // node is the HTML node of the current input (can be used as $(node))
});

// indeterminate = change input's state to 'indeterminate'
$('input').icheck('indeterminate', function(node) {
  // callbackfunction will be fired for each input
  // node is the HTML node of the current input (can be used as $(node))
});

// determinate = remove 'indeterminate' state
$('input').icheck('determinate', function(node) {
  // callbackfunction will be fired for each input
  // node is the HTML node of the current input (can be used as $(node))
});

// update = apply input changes, which were made outside the iCheck plugin
$('input').icheck('updated', function(node) {
  // callbackfunction will be fired for each input
  // node is the HTML node of the current input (can be used as $(node))
});

// toggle = toggle 'checked' state
$('input').icheck('toggle', function(node) {
  // callbackfunction will be fired for each input
  // node is the HTML node of the current input (can be used as $(node))
});

// destroy = remove all traces of iCheck
$('input').icheck('destroy', function(node) {
  // callbackfunction will be fired for each input
  // node is the HTML node of the current input (can be used as $(node))
});

// data = returns an object with the init settings and current states of the input
var data = $('input').icheck('data');
// data.checked, data.disabled, data.indeterminat are a cached states valuese

// styler = returns a wrapper div of the current input
var parent = $('input').icheck('styler');
// see http://git.io/cdYpdA for more info
```

## Callbacks

Note: callbacks are fired for each input. Unchecked radio buttons also receive a callbacks.

```
ifChecked = input's state is changed to "checked"
$('input').on('ifChecked', function(event) {
  // your code
});

ifUnchecked = "checked" state is removed
$('input').on('ifUnchecked', function(event) {
  // your code
});

ifDisabled = input's state is changed to "disabled"
$('input').on('ifDisabled', function(event) {
  // your code
});

ifEnabled = "disabled" state is removed
$('input').on('ifEnabled', function(event) {
  // your code
});

ifIndeterminate = input's state is changed to "indeterminate"
$('input').on('ifIndeterminate', function(event) {
  // your code
});

ifDeterminate = "indeterminate" state is removed
$('input').on('ifDeterminate', function(event) {
  // your code
});

ifChanged = input's "checked", "disabled" or "indeterminate" state is changed
$('input').on('ifChanged', function(event) {
  // your code
});

ifToggled = input's "checked" state is changed
$('input').on('ifToggled', function(event) {
  // your code
});

ifCreated = input is just customized
$('input').on('ifCreated', function(event) {
  // your code
});
Note: this callback is switched off by default, use the options like these to switch it on:
{
 callbacks: {
   ifCreated: true
 }
}

ifDestroyed = customization is just removed
$('input').on('ifDestroyed', function(event) {
  // your code
});
```
<<<<<<< HEAD
=======

Feel free to fork and submit pull-request or submit an issue if you find something not working.


Comparison
----------

iCheck is created to avoid routine of reinventing the wheel when working with checkboxes and radio buttons. It provides an expected identical result for the huge number of browsers, devices and their versions. Callbacks and methods can be used to easily handle and make changes at customized inputs.

There are some CSS3 ways available to style checkboxes and radio buttons, like [this one](http://webdesign.tutsplus.com/tutorials/htmlcss-tutorials/quick-tip-easy-css3-checkboxes-and-radio-buttons/). You have to know about some of the disadvantages of similar methods:

* inputs are keyboard inaccessible, since `display: none` or `visibility: hidden` used to hide them
* poor browser support
* multiple bugs on mobile devices
* tricky, harder to maintain CSS code
* JavaScript is still needed to fix specific issues

While CSS3 method is quite limited solution, iCheck is made to be an everyday replacement covering most of the tasks.


Browser support
---------------

iCheck is verified to work in Internet Explorer 6+, Firefox 2+, Opera 9+, Google Chrome and Safari browsers. Should also work in many others.

Mobile browsers (like Opera mini, Chrome mobile, Safari mobile, Android browser, Silk and others) are also supported. Tested on iOS (iPad, iPhone, iPod), Android, BlackBerry and Windows Phone devices.


Changelog
---------------

### March 03, 2014

* Better HiDPI screens support @ddctd143

### January 23, 2014 ([v2.0 release candidate](https://github.com/fronteed/icheck/tree/2.x))

* Three ways to set an options: global object (`window.icheck`), data attributes (`<input data-checkedClass="checked"`) and direct JavaScript object (`$(input).icheck({ options })`)
* Huge performance boost (takes less than 1s to customize 1000 inputs)
* Minimized number of function calls (some slow jQuery functions are replaced with a faster vanilla alternatives without using any dependencies)
* AMD module definition support (both for jQuery and Zepto)
* Unblocked native events - iCheck 2.x doesn't stop your newly or past binded events from being processed
* Pointer events support - full support for phones and tablets that use Windows OS (such as Lumia, HP tablets, desktops with a touch screen, etc)
* WebOS and Firefox OS support
* New methods: `$(input).icheck('data')` to get all the options were used for customization (also stores a current states values - `checked`, `disabled` and `indeterminate`), `$('input').icheck('styler')` to get a wrapper div (that's used for customization)
* Better handling of the `indeterminate` state
* Ability to set callbacks in three ways: global object, direct JavaScript object or using bind method (`$(input).on(callback)`)
* Ability to switch off some of the callbacks when you don't need them (global or per input)
* Inline styles dropped - iCheck won't add any inline styles to the elements until it's highly needed (`cursor` or `area` option)
* Fast click support - removes a 300ms click delay on mobile devices without any dependencies (iCheck compatible with the `fastclick` plugin), see the `tap` option
* Ability to ignore customization for the selected inputs using `init` option (if set to `false`) 
* Optimized event bindings - iCheck binds only a few global events for the all inputs (doesn't increase on elements addition), instead of a couple for the each customized element
* Doesn't store tons of arbitrary data (event in jQuery or Zepto cache), defines customized elements by specific classnames 
* Extra `ins` tag is dropped (less DOM modifications), iCheck wraps each input with a single `div` and doesn't use any extra markup for the any option
* Optimized reflows and repaints on init and state changes 
* Better options handling - iCheck will never run a single line of JS to process an options that are off or empty 
* Ability to auto customize the ajax loaded inputs without using any extra code (`autoAjax` option, on by default)
* Auto inits on domready using the specified selector (`autoInit` option) - searches for `.icheck` by default. Classnames can be changed using the `window.classes` object
* Memory usage optimization - uses only a few amount of memory (works well on low-memory devices)
* Betters callbacks architecture - these are fired only after changes are applied to the input
* Ability to set a mirror classes between the inputs and assigned labels using the `hoverLabelClass`, `focusLabelClass`, `activeLabelClass`, `checkedLabelClass`, `disabledLabelClass` and `indeterminateLabelClass` options (`mirror` option should be set to `true` to make this happen)
* Fixes some issues of the mobile devices
* Fixes the issues of the wrapper labels, that loose a click ability in some browsers (if no `for` attribute is set)
* Some other options and improvements
* Various bug fixes

Note: extended docs and usage examples will be available later.

### December 19, 2013

* Added Bower support
* Added to jQuery plugin registry

### December 18, 2013

* Added ARIA attributes support (for VoiceOver and others) @myfreeweb
* Added Amazon Kindle support @skinofstars
* Fixed clickable links inside labels @LeGaS
* Fixed lines separation between labels and inputs
* Merged two versions of the plugin (jQuery and Zepto) into one
* Fixed demo links
* Fixed callbacks @PepijnSenders


License
-------
iCheck plugin is released under the [MIT License](http://en.wikipedia.org/wiki/MIT_License). Feel free to use it in personal and commercial projects.
>>>>>>> refs/remotes/origin/1.x
