html-style-guide
================

MercadoLibre HTML Style Guide


# Table of contents
[Forms](#forms)  
[Anchors](#anchors)  

## Forms

### Good practices

* Don't use form elements outside from this context

```html
<!-- DON'T -->
<body>
	<input value="someValue" type="hidden">
</body>
```

```html
<!-- DO -->
<body>
	<form>
		<input value="someValue" type="hidden">
	</form>
</body>
```

* Specify form action

```html
<!-- DON'T -->
<form>...</form>
```

```html
<!-- DO -->
<form action="form-process.php">...</form>
```

* Specify form method

```html
<!-- DON'T -->
<form action="form-process.php">...</form>
```

```html
<!-- DO -->
<form action="form-process.php" method="post">...</form>
```
_Methods_ `post get `


* Use submit input to send form data

```html
<!-- DON'T -->
<input type="button" value="Send" onclick="sendForm();">
```

```html
<!-- DO -->
<input type="submit" value="Send">
```

* Use reset input to clear form

```html
<!-- DON'T -->
<input type="button" value="Clear" onclick="resetForm();">
```

```html
<!-- DO -->
<input type="reset" value="Clear">
```

* Use *labels* to describe the role of the form element

```html
<!-- DON'T -->
name: <input type="text">
```

```html
<!-- DO -->
<label>name:</label><input type="text">
```

* Asociate a label with the corresponding field

```html
<!-- DON'T -->
<label>name:</label><input type="text">
```

```html
<!-- DO -->
<label for="name">name:</label><input id="name" type="text">
```

* Add names to fields that will be sending in the submit action

```html
<!-- DON'T -->
<input class="name" id="userName" type="text">
```

```html
<!-- DO -->
<input class="name" id="userName" name="userName" type="text">
```

* Don't add names to the fields that will not be sending in the submit action

```html
<!-- DON'T -->
<input class="pass" id="userPass" name="userPass" type="password">
```

```html
<!-- DO -->
<input class="pass" id="userPass" type="text">
```

* Separate content by context

```html
<!-- DON'T -->
<label>name:</label><input name="userName" type="text">
<label>sex:</label><input name="userSex" type="radio"><input name="userSex" type="radio">
<label>Transaction Number:</label><input name="productNumTransaction" type="text">
<label>Transaction Date:</label><input name="productDateTransaction" type="date">
```

```html
<!-- DO -->
<fieldset name="userData">
	<label>name:</label><input name="name" type="text">
	<label>sex:</label><input name="sex" type="radio"><input name="sex" type="radio">
</fieldset>
<fieldset name="productData">
	<label>Transaction Number:</label><input name="numTransaction" type="text">
	<label>Transaction Date:</label><input name="dateTransaction" type="date">
</fieldset>
```

### Generic FORM example

#### _Code_
```html
<form action="/processData.php" method="post">
	<fieldset>
		<legend>Personal information</legend>
		<div>
			<label for="firstName">First name:</label>
			<input id="firstName" name="firstname" type="text">
		</div>
		<div>
			<label for="lastName">Last name:</label>
			<input id="lastName" name="lastname" type="text">
		</div>
		<div>
			<label for="male">Sex:</label>
			<input id="male" name="sex" value="male" type="radio">
			<label for="male">Male</label>
			<input id="female" name="sex" value="female" type="radio">
			<label for="female">Female</label>
		</div>
		<div>
			<label for="birthDate">Birth date:</label>
			<input id="birthDate" name="birthdate" type="date">
		</div>
	</fieldset>
	<fieldset>
		<legend>Other Information</legend>
		<div>
			<label for="someInfo">Some info:</label>
			<input id="someInfo" name="someinfo" type="text">
		</div>
		<div>
			<label for="selectEg">Select example:</label>
			<select id="selectEg" name="selecteg">
				<option>option 1</option>
				<option>option 2</option>
				<option>option 3</option>
				<optgroup label="optgroup 1">
					<option>option 4.1</option>
					<option>option 4.2</option>
					<option>option 4.3</option>
				</optgroup>
				<option>option 5</option>
				<option>option 6</option>
				<optgroup label="optgroup 2 disabled" disabled><!-- In XHTML, attribute minimization is forbidden, and the disabled attribute must be defined as <optgroup disabled="disabled"> -->
					<option>option 7.1</option>
					<option>option 7.2</option>
					<option>option 7.3</option>
					<option>option 7.4</option>
				</optgroup>
			</select>
		</div>
		<div>
			<input id="check1" name="checkbox1" value="example1" type="checkbox">
			<label for="check1">checkbox 1:</label>
			<input id="check2" name="checkbox2" value="example2" type="checkbox">
			<label for="check2">checkbox 2:</label>
			<input id="check3" name="checkbox3" value="example4" type="checkbox">
			<label for="check3">checkbox 3:</label>
		</div>
	</fieldset>
	<fieldset>
		<legend>Action Buttons</legend>
		<input value="Send" type="submit">
		<input value="reset form" type="reset">
	</fieldset>
</form>
```


### New attibutes

* `autocomplete` - *(only if the type attr isn't `hidden` `checkbox` `radio` `file` or button type `button` `submit` `reset` `image`)*
* `pattern` - A regular expression. Validate the input content when is used with tel, search, url, and email input types
* `placeholder` - A hint to the user of what can be entered in the control
* `required` - This attribute specifies that the user must fill in a value before submitting a form. *(not apply for hidden, image, submit, reset or button types)*

__Inputs__

* `list` - The value must be the id of a `<datalist>` element in the same document
*(This attribute is ignored when the type attribute's value is hidden, checkbox, radio, file, or a button type)*
* `form` - A *String* indicating which `<form>` element this input is part of. An input can only be in one form. *(The value must be the id of a form)*
* `formmethod` - A *String* define which method (get/post) should be used when submitting. __It overrides the form method__, if defined. *(only applies for type image or submit, when the form attribute has been set)*
* `formaction` - A *String* define the URI should be used to processes the information. __It overrides the form action__, if defined. *(only applies for type image or submit, when the form attribute has been set)*

[Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Browser_compatibility)

## New attibutes values


>For `type` attr  
>`email` `date` `datetime` `number` `range` `search` `tel` `url`

>For `accept` attr *(if type attr is `file`)*  
>`audio` `image` `video`

[Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Browser_compatibility)

#### Bibliografía
*[https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/)*
*[https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms)*
*[http://www.w3.org/TR/html401/interact/forms.html](http://www.w3.org/TR/html401/interact/forms.html)*
*[http://www.tutorialspoint.com/html5/](http://www.tutorialspoint.com/html5/)*
*[http://html5doctor.com/](http://html5doctor.com/)*


## Anchors

### Description
* Defines an anchor and can be used as a link to another document, such as a marker, or both.


### Attibutes
<a href="#href">`href`</a>
<a href="#title">`title`</a>
<a href="#id">`id`</a>
<a href="#name">`name`</a>
<a href="#class">`class`</a>
<a href="#target">`target`</a>
<a href="#type">`type`</a>
<a href="#rel">`rel`</a>


### Basic implement
Specific `href` and `title` attributes
```html
<a href="https://github.com/mercadolibre/html-style-guide" title="Go to html style guide" >html-style-guide</a>
```

### Implement data attributes
```html
<a href="http://url.original" data-some-data="sting-data" title="link with data attr"></a>
```

### Good Practices
Anchors don't have auto close tag
```html
<!-- DON'T -->
<a href="url" title="title-text" />
```

```html
<!-- DO -->
<a href="url" title="title-text"></a>
```

<a name="title"></a>
Always specific a title attribute
```html
<!-- DON'T -->
<a href="url"></a>
```

```html
<!-- DO -->
<a href="url" title=""></a>
```

Never use other element if you want link any info
```html
<!-- DON'T -->
<span id="link" onclick="window.open('url')" ></span>
```

```html
<!-- DO -->
<a href="url" title="title-link" target="_blank"></a>
```

Always define a url and prevent it from javascript
```html
<!-- DON'T -->
<a href="javscript:void();" ></a>
```

```html
<!-- DO -->
<a href="http://www.url.bla" title="title-link"></a>
and prevent event on click this
```

<a name="id"></a>
Link info inside our content example
```html
<a href="#idReference" title="Go to Reference">Go to Reference</a>
(...our html content...)
<section id="idReference"></section>
```
Or
<a name="name"></a>
```html
<a href="#nameReference" title="Go to Reference">Go to Reference</a>
(...our html content...)
<a name="nameReference"></a>
<section id="reference"></section>
```


### Attibutes desription

#### Target
<span id="target"></span>

######Possible values

* `_blank` - *Open linked document in new windows or tab*
* `_self` - *It's a default, open linked document in the same context*
* `_parent` - *Open linked document in the parent frame*
* `_top` - *Open linked document in the top level of current context frame*


#### Bibliografía  
http://www.htmlquick.com/es/reference/tags/a.html
http://www.htmlquick.com/es/reference/mime-types.html
http://www.htmlquick.com/es/reference/types.html#frame-target
http://stackoverflow.com/questions/11009597/correct-implementation-of-anchor-tag
http://line25.com/articles/10-html-tag-crimes-you-really-shouldnt-commit
http://stackoverflow.com/questions/134845/href-attribute-for-javascript-links-or-javascriptvoid0
http://moz.com/learn/seo/anchor-text
http://www.w3.org/TR/html4/types.html#h-6.16
http://stackoverflow.com/questions/4964130/target-blank-vs-target-new
http://www.w3.org/html/wg/drafts/html/master/Overview.html


## Lists

Used to enumerate(list) information, which determines the type of list used.

### Types
- `<ul>` - unorderer list
- `<ol>` - orderer list
- `<dl>` - description list

#### Unorderer Lists

Used to list information that does not require a particular order.

Eg. List of payment methods.

html structure
```
<ul>
	<li>MercadoPago<li>
	<li>Efectivo<li>
	<li>Transferencia bancaria<li>
</ul>
```
Result
* MercadoPago
* Efectivo
* Transferencia bancaria


#### Orderer Lists

Used to list items that need an order.

Eg: Steps to buying.

html structure
```
<ol>
	<li>Offert<li>
	<li>Select a payment method</li>
	<li>Select a shipment method</li>
</ol>
```
Result
1. Offert
2. Select a payment method
3. Select a shipment method

#### Definition Lists

This list is recommended for use when the information has a relevant title or concept, in addition to its content.
It has a title `<dt>` and description `<dd>`.

html structure
```
<dl>
	<dt>Tipo de artículo:</dt>
		<dd>Artículo nuevo</dd>
	<dt>Vendidos:</dt>
		<dd>1 vendido</dd>
</dl>
```
Result

···· __Tipo de artículo:__

···· ···· Artículo nuevo

···· __Vendidos:__

···· ···· 1 vendido
