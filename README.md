html-style-guide
================

MercadoLibre HTML Style Guide

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


## New attibutes 

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


* For `type` attr  

`email`
`date`
`datetime`
`number`
`range`
`search`  
`tel` 
`url` 

* For `accept` attr *(if type attr is `file`)*

`audio`
`image` 
`video`

[Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Browser_compatibility)





#### Bibliografía
*[https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/)*
*[https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms)*
*[http://www.w3.org/TR/html401/interact/forms.html](http://www.w3.org/TR/html401/interact/forms.html)*
*[http://www.tutorialspoint.com/html5/](http://www.tutorialspoint.com/html5/)*
*[http://html5doctor.com/](http://html5doctor.com/)*
