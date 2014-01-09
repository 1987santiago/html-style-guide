html-style-guide
================

MercadoLibre HTML Style Guide


// Usar labels asociados a los inputs

Don't
name: <input type="text" />

Do
<label>name:</label><input type="text" />


// Asociar el label con el campo correspondiente

Don't
<label>name:</label><input type="text" />

Do
<label for="name">name;</label><input id="name" type="text" />


// Asignar names a los campos que se deseen enviar en el submit del formulario

Don't
<input class="name" id="clientName" type="text" />

Do
<input class="name" id="clientName" name="client.name" type="text" /> <!-- client.name || clientName || client-name --> ?

Don't
<input class="pass" id="clientPass" name="client.pass" type="password" /> <!-- client.pass || clientPass || client-pass --> ?

Do
<input class="pass" id="clientPass" type="text" />


// Separar el contenido seg˙n su contexto

Don't
<label for="name">name:</label><input id="name" type="text" />
<label for="sex">sex:</label><input id="female" name="sex" type="radio" /><input id="male" name="sex" type="radio" />
<label for="numDoc">Document number:</label><input id="numDoc" type="text" />
<label for="numTransaction">Transaction Number:</label><input id="numTransaction" type="text" />
<label for="dateTransaction">Transaction Date:</label><input id="dateTransaction" type="date" />

Do
<fieldset name="client.data">
	<label for="name">name:</label><input id="name" type="text" />
	<label for="sex">sex:</label><input id="female" name="sex" type="radio" /><input id="male" name="sex" type="radio" />
	<label for="numDoc">Document number:</label><input id="numDoc" type="text" />
</fieldset>
<fieldset name="product.data">
	<label for="numTransaction">Transaction Number:</label><input id="numTransaction" type="text" />
	<label for="dateTransaction">Transaction Date:</label><input id="dateTransaction" type="date" />
</fieldset>


// Especificar un action en el formulario

Don't
<form>...</form>

Do
<form action="form-process.php">...</form>


// Especificar un metodo en el formulario

Don't
<form action="form-process.php">...</form>

Do
<form action="form-process.php" method="post">...</form>


// Usar submits para el envÌo de los datos del formulario

Don't
<input type="button" value="Send" onclick="sendForm();" />

Do
<input type="submit" value="Send" />


// Usar resets para borrar el contenido del formulario

Don't
<input type="button" value="Clear" onclick="resetForm();" />

Do
<input type="reset" value="Clear" />






// BibliografÌa
https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/
https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Forms
http://www.w3.org/TR/html401/interact/forms.html
http://www.tutorialspoint.com/html5/
http://html5doctor.com/