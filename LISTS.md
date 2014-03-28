html-style-guide
================

MercadoLibre HTML Style Guide

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
