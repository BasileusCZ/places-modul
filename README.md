# Basileus Popup Module

A lightweight JavaScript widget that allows users to select a point and returns its `point_id` directly into your page. Integration requires just **three lines of HTML**.

---

## Table of Contents

* [Installation](#installation)
* [Usage](#usage)

  * [1. Input Field](#1-input-field)
  * [2. Open Button](#2-open-button)
  * [3. Script Include](#3-script-include)
* [Complete Example](#complete-example)

---

## Installation

Simply include the Basileus popup script before the closing `</body>` tag of your HTML page:

```html
<script src="https://popup.basileus.cz/basileus.js"></script>
```

No build tools or package managers are required.

## Usage

Integration consists of three essential HTML elements:

### 1. Input Field

Add a text input with the `class` **basileus-point**. When a user selects a point in the widget, the script will populate this field with the corresponding `point_id`.

```html
<input class="basileus-point" name="basileus_point" type="text" value="">
```

### 2. Open Button

Add a button with the `class` **basialeus-open** and `data-tag-value` **basialeus-point**. Clicking this button opens the Basileus popup widget.

```html
<button class="basialeus-open" data-tag-value="basileus-point">Basileus</button>
```

Optional settings: 

`data-type` - values:
- 0 (default) - show all pickup places and boxes
- 1 - show all pickup places
- 2 - show all pickup boxes

`data-tag-value` - class of the element that will be filled with the delivery location ID
If it is <input>, the value will be set, otherwise the internal text of the element.

`data-tag-address` - class of the element that will be filled with the delivery address
If it is <input>, the value will be set, otherwise the internal text of the element.

`data-tag-title` - class of the element that will be filled with the delivery location name
If it is <input>, the value will be set, otherwise the internal text of the element.

### 3. Script Include

Include the Basileus script so that it can attach event handlers to the above elements and manage the popup widget.

```html
<script src="https://popup.basileus.cz/basileus.js"></script>
```

## Complete Example

Below is a minimal HTML page demonstrating full integration:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Demo Basileus Module</title>
  </head>

  <body>

  <h2>Select where you want to send the shipment</h2>
  <h3>ID</h3>
  <input class="basileus-point" name="basileus_poin2t" type="text" value="">
  <h3>Název</h3>
  <input class="basileus-title" name="basileus_title2" type="text" value="">
  <h3>Adresa</h3>
  <input class="basileus-address" name="basileus_address2" type="text" value="">
  <br><br>
  <button data-type="0" data-tag-value="basileus-point" data-tag-title="basileus-title" data-tag-address="basileus-address" class="basileus-open">Deliver to
pickup point or box</button>
  <br>
  <br>
  <button data-type="1" data-tag-value="basileus-point" data-tag-title="basileus-title" data-tag-address="basileus-address" class="basileus-open">Deliver to
pickup point</button>
  <button data-type="2" data-tag-value="basileus-point" data-tag-title="basileus-title" data-tag-address="basileus-address" class="basileus-open">Deliver to
box</button>

  <script src="https://popup.basileus.cz/basileus.js"></script>     
  </body>
</html>
```

---

That's it! Once these three lines are in place, the Basileus popup will handle user interaction and return the `point_id` into your input field automatically.
