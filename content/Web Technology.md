**3-Tier Architecture** -> A design pattern in software engineering where the system is divided into three tiers/parts and each part is responsible for a different thing.
- **Presentation** (User-Interface) -> The Client.
- **Application** (Logic) -> The Web Server.
- **Data** (DBMS) -> The Database.
## Client-Side vs Server-Side Scripting
**Scripting** (adding logic to the webpage) can be done either on the client-side or the server-side. Both approaches have their advantages and disadvantages.

| Client Side                                                                                             | Server Side                                                                                                       |
| ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Faster Reponse** <br>Data is processed directly on the client and doesn't add any load on the server. | *Slower Response* <br>Data is requested from the server where it is processed.                                    |
| **Direct Access to Client** <br>JS has a lot of freedom and access to client's machine.                 | *Indirect Access to Client* <br>PHP, Python or others are executed on server so they don't get access.            |
| *Very Insecure*<br>JS sits at the client so it is easier to get hacked.                                 | **Secure**<br>PHP sits at the server so it is much harder to get hacked.                                          |
| *Visible Code*<br>JS code is visible in the source code and hence can be plagiarized.                   | **Invisible Code**<br>PHP code is executed server side and hence only the response is present in the source code. |
<div style="page-break-after: always;"></div>

# Bootstrap
Boostrap is a **CSS and JQuery UI Library**. It is a powerful front end toolkit which can be used to set layout, styling, behaviour etc. It provides many components and utility classes which can be directly applied to the elements. To use Bootstrap, add these CDN links to the HTML document.

```html
<link rel="stylesheet" href="https: /cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css">
<script src="https: /cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bund
le.min.js" defer> /script>
```

## Grid System
Bootstrap's Layout Engine divides the page into 12 columns. We can directly specify
how much space each element takes.
We can use the `.col` class on each element with a column amount to place it on the
grid. We can attach a breakpoint like `.-md` or `.-sm` to specify the layout only for a
specific screen size.
### Examples
1. All three divs take up the same space => 4+4+4 = 12 columns
```html
<div class="container">
	<div class="col-4"> Column </div>
	<div class="col-4"> Column </div>
	<div class="col-4"> Column </div>
</div>
```

2. One div takes up double the amount => 3+3+6 = 12 columns
```html
<div class="container">
	<div class="col-3"> Column </div>
	<div class="col-3"> Column </div>
	<div class="col-6"> Column </div>
</div>
```

3. One div takes up most of the space => 10+1+1 = 12 columns
```html
<div class="container">
	<div class="col-10"> Column </div>
	<div class="col-1"> Column </div>
	<div class="col-1"> Column </div>
</div>
```

4. The `.row` class can be used to get columns to stack vertically. Here, Both rows are divided differently.
```html
<div class="container">
	<div class="row">
		<div class="col-2"> Column </div>
		<div class="col-2"> Column </div>
		<div class="col-8"> Column </div>
	</div>
	<div class="row">
		<div class="col-3"> Column </div>
		<div class="col-6"> Column </div>
		<div class="col-3"> Column </div>
	</div>
</div>
```

The `.container-fluid` class can be used instead of the `.container` class to make the container full width. In this example, it gives all three initial columns equal widths (33.3%) and then divides the first column between it's children (50%).

```html
<div class="container-fluid">
	<div class="col">
	    <div class="col"> Column </div>
	    <div class="col"> Column </div>
	</div>
	<div class="col"> Column </div>
	<div class="col"> Column </div>
</div>
```
## Breakpoints
Bootstrap's Layout Engine supports 6 responsive breakpoints. This allows us to selectively style our page depending on the window size.

| Prefix  | Name              | Breakpoint    |
| ------- | ----------------- | ------------- |
| **xs**  | Extra Small       | 0px-576px     |
| **sm**  | Small             | 576px-768px   |
| **md**  | Medium            | 768px-992px   |
| **lg**  | Large             | 992px-1200px  |
| **xl**  | Extra Large       | 1200px-1400px |
| **xxl** | Extra Extra Large | 1400px-onward |
### Example
- At medium screen size => All three divs take up the same space.
- At large screen size => One div takes up double the amount.
- At extra large screen size => One div takes up most of the space.

```html
<div class="container">
	<div class="col-md-4 col-lg-3 col-xl-10"> Column </div>
	<div class="col-md-4 col-lg-3 col-xl-1"> Column </div>
	<div class="col-md-4 col-lg-6 col-xl-1"> Column </div>
</div>
```

## Alignment
The `.align-items-start`, `.align-items-center` and `.align-items-end` classes can be used to align an element's children **vertically**.

The `.justify-content-start`, `.justify-content-center` and `.justify-content-end` classes can be used to align an element's children **horizontally**.
## Images
These bootstrap classes can be added to `<img>` elements.

- `.image-fluid` to make it responsive.
- `.image-thumbnail` to give it a rounded border look.
- `.float-start` or `.float-end` to place it at the start/end.

```html
<!-- Responsive Image which is placed at the end. -->
<img class="image-fluid float-end" />

<!-- Rounded Image which is placed at the start. -->
<img class="image-thumbnail float-start" />
```
## Tables
The `.table` class can be added to `<table>` elements to then apply bootstrap classes.

- `.table-striped-columns` -> zebra-coloured columns.
- `.table-hover` -> hovering effect.
- `.table-active` -> selecting effect.
- `.table-bordered` -> adds borders.
- `.table-borderless` -> removes borders.

The table can be placed inside a div which has the `.table-responsive` class to make it completely responsive.

## Styling
There are many different classes that can be used for styling.

1. **Contextual Prefixes** -> can be added to add predefined styles to elements.

| Prefix                 | Style         |
| ---------------------- | ------------- |
| `. -primary`           | Blue          |
| `. -secondary`         | Lighter Color |
| `. -success`           | Green         |
| `. -warning`           | Yellow        |
| `. -danger`            | Red           |
| `. -info`              | Cyan          |
| `. -light` and `.dark` | White/Black   |
So something like `.table-primary` would make the table blue.

2. **Margin** and **Padding** -> Combine 
	1. `.m` (Margin) or `.p` (Padding) with
	2. `t` (Top), `b` (Bottom), `s` (Left), `e` (Right), `x` (Left-Right), `y` (Top-Bottom)
	3. `-0` to `-5` for sizing.

3. **Text Alignment** -> `.text-start`, `.text-center`, `text-end`.

<div style="page-break-after: always;"></div>

# Javascript
*It is a loosely-typed, dynamic language that is used to add interactivity and dynamic behaviour on a website.*

**Javascript Runtime** -> The environment where Javascript code is executed.

Examples: NodeJS (Console), V8 (Chrome), Javascript (Safari)... 

In browsers, javascript is supported by default due to the built-in js runtime. This runtime is packed inside a Browser Engine like Blink (Chrome), Gecko (Firefox), WebKit (Safari).

It can be added to an HTML document in three ways.
1. Inline Javascript -> using attributes like `onclick()` and `onblur()`.
2. Internal Javascript -> using the `<script>` tag and writing inside it.
3. External Javascript -> using `<script>` tag and linking the javascript using the `src=""` attribute.
## Language Features

1. The file extension is `.js`.
2. Single Line Comment are given like this `//`.
3. Multi Line Comments are given using these `/* */`
4. Semicolons are optional but it's better to use them as the JS interpreter adds semicolons where there is a missing one.
### Variables
Data Types aren't explicitly written because they are implicitly assigned at runtime. However, Javascript has 8 primitive data types -> String, Number, BigInt, Boolean, Undefined, Null, Symbol, Object.

There are four ways of assigning variables in javascript.
1. `x = 10` without any keyword.
2. `var x = 10;` using the var keyword.
3. `let x = 10;` using the let keyword.
4. `const x = 10;` using the const keyword.
#### String Concatenation and Templating
```js
var name = "Jaish";

//String Concatenation is done using the plus symbol.
var text = "M." + name + "Khan";
console.log(text); //M. Jaish Khan

//String Templating is done using backticks.
var text = `M. ${name} Khan`;
console.log(text); //M. Jaish Khan
```

### Functions
Javascript has many many built-in functions and can access others from its modules.

We can create our own functions like this:
```js
function function_name(parameters){
	//code
}
```

`console.log()` is a common js function that is used to print to the terminal in the browser.
## Conditionals
Javascript has two types of conditionals -> `if-else` and `switch-case`.

The conditions are given using `comparison` and `logical` operators.
```js
let x = 10;

if (x == 10) {
	console.log("Ten.");
}
else if (x <= 10 && x >= 0) {
	console.log("Less than ten and positive.");
}
else if (x < 0) {
	console.log("Less than zero.");
}
else {
	console.log("More than ten.");
}
```
## Loops
Javascript has 5 types of loops -> `for`, `for-in`, `for-of`, `while` and `do-while`.

The for, do-while and while loops are exactly the same as in **C** or **Java**.
```js
Array = [2, 4, 6, 8, 10];

for (var i=1; i<=Array.length; i++) {
	console.log(Array[i]);
}

//We can use the for-of loop instead to print the array too.
for (var i of Array){
	console.log(i);
}
```

<div style="page-break-after: always;"></div>

## JS Events
Whenever something happens in the DOM, an event is generated. This event can be of many types like `click`, `keydown` or `blur`.

These events can be catched by attaching event listeners in one of two ways.
1. Using the `onevent` handlers in html. This allows us to use Javascript inside of HTML.
```html
//When we click on this h1 the text changes from "Jaish" to "Ooops".
<h1 onclick="this.innerHTML = 'Ooops';">Jaish</h1>
```

2. Using the `addEventListener` function.
```js
document.getElementById("button").addEventListener("click", function);
```

### Common JS Events

| Event           | When it occurs                                     |
| --------------- | -------------------------------------------------- |
| **click**       | When an element is clicked (mouse).                |
| **dblclick**    | When an element is double-clicked (mouse).         |
| **contextmenu** | When right-click is pressed (mouse).               |
| **drag**        | When an element is dragged (mouse).                |
| **drop**        | When an element is released from dragging (mouse). |
| **scroll**      | When the page or an element is scrolled.           |
| **keypress**    | When a key is pressed.                             |
| **blur**        | When an element loses focus.                       |
| **focus**       | When an element gets focus.                        |
| **change**      | When the content of this element is changed.       |

We can disable the right-click context menu by using this simple snippet.
```js
document.addEventListener("contextmenu", noContextMenu(e));

function noContextMenu(e){
	e.preventDefault();
}
```

<div style="page-break-after: always;"></div>

## Document Module
It is a module/extension of Javascript that allows us to interact with the HTML page.

**DOM** (Document Object Model) -> It is a tree of objects made out of the HTML page.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div class="container">
        <h1 id="heading">Jaish Khan</h1>
        <p class="text">Aspiring to become a <b class="bold">Web Dev</b></p>
    </div>
</body>
</html>
```

The DOM Tree of the above HTML code would look like:

![[DOM.excalidraw]]
### DOM Traversal Functions
They are used to interact with specific elements in the DOM Tree.

```js 
//selects the first element that matches the id "email".
var email = document.getElementById("email"); 

//selects all the elements with the class "container".
var containers = document.getElementsByClassName("container"); 

//selects the first element that matches the given selector (can be anything).
var email2 = document.querySelector("#email2"); 

//selects all the elements that match the given selector (can be anything).
var boxes = document.querySelectorAll(".box"); 
```

The `innerHTML` property can be used to select the content of an HTML element and can also be used to change it.
```js
var text = email.innerHTML; //selects the content of the selected element.
email.innerHTML = "jaishkhan771@gmail.com"; //changes the content of the element
```
### DOM Manipulation Functions
```js
document.write("<h1>Jaish Khan</h1>");
//writes onto the HTML page (also creates the h1 element). 

document.createElement(h1); //creates an h1 element.
document.appendChild(h1); //attaches the created h1 element to the document.
document.removeChild(h1); //removes the created h1 element from the document.
```

<div style="page-break-after: always;"></div>

## Window Module
Window is a Javascript module that is used to iteract with the Window containing the document.

| Property                  | Function                                                   |
| ------------------------- | ---------------------------------------------------------- |
| `window.open()`           | Opens a new blank window.                                  |
| `window.open(url)`        | Opens a new window with the given URL.                     |
| `window.alert(message)`   | Opens a window which has an OK button.                     |
| `window.confirm(message)` | Opens a window which has an OK and Confirm buttons.        |
| `window.prompt(message)`  | Opens a window which has an input, OK and confirm buttons. |
| `window.close()`          | Closes the current window.                                 |
### Location SubModule
It is used to access the properties of the network itself.

| Property                   | Function                                              |
| -------------------------- | ----------------------------------------------------- |
| `window.location.hostname` | Sets/Returns the hostname of a URL.                   |
| `window.location.port`     | Sets/Returns the port of a URL.                       |
| `window.location.host`     | Sets/Returns the hostname + port of a URL.            |
| `window.location.protocol` | Sets/Returns the protocol of a URL.                   |
| `window.location.origin`   | Sets/Returns the hostname + port + protocol of a URL. |
| `window.location.href`     | Sets/Returns the entire URL.                          |
### Navigator SubModule
It is used to access the state and properties of the client.

| Property                         | Function                                                  |
| -------------------------------- | --------------------------------------------------------- |
| `window.navigator.appName`       | Returns the name of the browser.                          |
| `window.navigator.appVersion`    | Returns the version of the browser.                       |
| `window.navigator.cookieEnabled` | Returns true if cookies are enabled.                      |
| `window.navigator.geolocation`   | Returns the location/address of the client.               |
| `window.navigator.language`      | Returns the language set in the browser                   |
| `window.navigator.onLine`        | Returns true if the browser is connected to the internet. |
| `window.navigator.platform`      | Returns the Operating System name.                        |
| `window.navigator.userAgent`     | Returns the details about the client.                     |
### History SubModule
It is used to access the browser's session history.

| Property                    | Function                                   |
| --------------------------- | ------------------------------------------ |
| `window.history.back()`     | Goes to the previous page in history.      |
| `window.history.forward()`  | Goes to the next page in history.          |
| `window.history.go(number)` | Goes to the page number that is specified. |
```js
window.history.go(-1); //goes to the previous page.
window.history.go(-2); //goes to page before the previous page.
window.history.go(1); //goes to the next page.
window.history.go(2); //goes to the page after the next page.
```

<div style="page-break-after: always;"></div>

## Form Validation
*Checking if the data that is submitted by the user is valid or not is called **Form Validation***.

We can do form validation in many ways. Doing it in HTML is very easy as we can use the `required`, `type`, `min`, `minlength`, `max`, `maxlength` and `pattern` attributes. 

```html
<!--Basic HTML Form Validation-->
<form action="valid.php" method="post">
    <div>
	    <label>FullName: </label>
        <input type="text" minlength="5" maxlength="20" required />
    </div>
    <div>
        <label>Phone No: </label>
        <input type="tel" min="10" max="10" required />
    </div>
    <div>
        <label>Password:</label>
        <input type="password" minlength="8" maxlength="16" required />
    </div>
    <button type="submit">Submit</button>
</form>
```

We can use the `:valid` and `:invalid` CSS Selectors to show validity on the inputs.

```css
input:valid {
	border: 2px solid green;
}

input:invalid {
	border: 2px solid red;
}
```

Form Validation using HTML + CSS is very fast compared to doing it in JS but it is not customizable. We can create a validate function for form validation.

The HTML looks like this
```html
<form action="test.html" method="post" id="form">
	<div>
		<label for="fname">FullName: </label>
		<input type="text" id="fname" name="fname" />
		<span id="fname_error"></span>
	</div>
	<div>
		<label for="phone">Phone No: </label>
		<input type="tel" id="phone" name="phone" />
		<span id="phone_error"></span>
	</div>
	<div>
		<label for="pass">Password:</label>
		<input type="password" id="pass" name="pass" />
		<span id="pass_error"></span>
	</div>
	<button type="submit" onclick="validate()">Submit</button>
</form>
```

First we declare some variables to hold the HTML elements.
```js
function validate() {
	//First we get the three input elements.
	let fname = document.getElementById("fname");
	let phone = document.getElementById("phone");
	let pass = document.getElementById("pass");

	//Then the three spans for writing the errors.
	let fname_error = document.getElementById("fname_error");
	let phone_error = document.getElementById("phone_error");
	let pass_error = document.getElementById("pass_error");

	//Then create three variables to track each input validation.
	let l = false;
	let m = false;
	let n = false;
}
```

Then we create an if-elseif-else block for validating each input.
```js
if (fname.value == "") {
  fname_error.innerHTML = "Name is required.";
} 
else if (fname.value.length <= 4 || fname.value.length >= 25) {
  fname_error.innerHTML = "Name should be between 4 and 25 characters.";
} 
else {
  fname_error.innerHTML = "";
  l = true;
}
```

We can then dynamically submit the form using the `submit()` function in JS.
```js
if (l === true && m === true && n === true) {
	document.getElementById("form").submit();
}
```

The form submits all the time because of the `type=submit` in the button element. We can override this behaviour using `preventDefault()` on the event.
```html
<button type="submit" onclick="validate(event)">Submit</button>
```
```js
function validate(e){
	e.preventDefault();
}
```

OR we can just make the button a normal button instead.
```html
<button type="button" onclick="validate()">Submit</button>
```
### Regex
*Regex, or Regular Expressions; used for creating a pattern which we can match against.*

It is used for either **text validation** or **searching queries**. It is available in every programming language. We mostly use it in Javascript or PHP.

The general syntax is `/pattern/modifiers`.
We can use the `test()` function in Javascript

```js
//Checks for if the phone number only contains numbers or not.
pattern = /^[0-9]+$/;

if (pattern.test(phone.value) === false) {
	phone_error.innerHTML = "Only numbers are allowed.";
}
```

<div style="page-break-after: always;"></div>

# PHP
*It is a loosely-typed, dynamic language that is used as a server-side language to fetch requests and send responses.*

A PHP file supports HTML, CSS and JS by default. The PHP code begins with the delimiter `<?php` and ends at `?>`.
## Language Features

1. The file extension is `.php`.
2. Single Line Comment are given like this `//` or `#`.
3. Multi Line Comments are given using these `/* */`.
4. Semicolons are absolutely required.
5. PHP Keywords are not case-sensitive but the Variables are case-sensitive.
6. Constants can be created using the `define()` function or the `const` keyword.
### Variables
Data Types aren't explicitly written because they are implicitly assigned at runtime. However, PHP has 8 primitive data types -> String, Integer, Float, Boolean, Array, Object, Null, Resource.

We assign variables in php using the dollar sign `$name = "Jaish"`. Both **"double quotes"** and **'single quotes'** can be used but string templating only works with double quotes.

#### String Concatenation and Templating

```php
$name = "Jaish";

//String Concatenation is done using the dot symbol.
$text = "M." . name . "Khan"
echo text //M. Jaish Khan

//String Templating is done using double quotations (doesn't work in single quotes).
$text = "M. $name Khan"
echo text //M. Jaish Khan
```

#### Arrays and Associative Arrays
Arrays are defined in PHP using the `array()` function but can also be defined in the traditional way in PHP 5.4. Arrays have **numeric indices** and Associative Arrays have **key-value pairs**.

```php
$arr = array(1, 2, 3, 4, 5);
//$arr = [1, 2, 3, 4, 5];

$assoc_arr = array("one"=>1, "two"=>2, "three"=>3, "four"=>4, "five"=>5);
//$assoc_arr = ["one"=>1, "two"=>2, "three"=>3, "four"=>4, "five"=>5];
```

### Functions
PHP has more than a 1000 functions built-in for basically every purpose.

We can create our own functions like this:
```php
function function_name(parameters){
	//code
}
```

| Common PHP Functions | What they Do                           |
| -------------------- | -------------------------------------- |
| `echo` or `echo()`   | Prints to the screen.                  |
| `print_r()`          | Prints in a more human-readable way.   |
| `phpversion()`       | Returns the version of PHP.            |
| `var_dump()`         | Returns the data type of the variable. |
| `strlen()`           | Returns the length of the string.      |
| `trim()`             | Removes whitespace.                    |
#### Type Casting
Type Casting is done using paranthesis statements -> `(int)`, `(string)` and `(float)`.

```php
$str = "10";
$num = (int) $str;

echo var_dump($str); //string
echo var_dump($num); //integer
```
### PHP foreach loop
This loop is used to loop through array elements.
```php
//Arrays
$days = array("Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday");

foreach ($days as $i) {
	echo $i . "<br>";
}

//Associative Arrays
$days = array("1"=>"Monday", "2"=>"Tuesday", "3"=>"Wednesday", "4"=>"Thursday", "5"=>"Friday", "6"=>"Saturday", "7"=>"Sunday");

foreach ($days as $x=>$i) {
	echo $x . " : " . $i . "<br>";
}
```

<div style="page-break-after: always;"></div>

## XAMPP
It is an all-in-one package used for PHP development. It stands for *Cross-Platform, Apache, MariaDB, PHP, Perl*. 

1. Download XAMPP.
2. Install XAMPP.
3. Run Apache and MySQL in XAMPP control panel.
4. Create all your files in `C:\xampp\htdocs`
5. Run `localhost\filename` in browser.

We can visit `localhost` then go to `phpmyadmin` to visually edit the database.

## MySQL
We can connect to a MySQL server using the MySQLi extension.
- `mysqli_connect()` -> used to connect to the server.
- `die()` -> stops the connection.
- `mysqli_connect_error()` -> catches connection errors.

```php
<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "myDB";

$conn = mysqli_connect($servername, $username, $password, $dbname);
if (!$conn) {
  die("Connection failed: " . mysqli_connect_error());
}
```
### Data Selection
- `mysqli_query()` -> used to pass queries to the connected server.
```php
$sql = "SELECT id, firstname, lastname FROM MyGuests";

$result  = mysqli_query($conn, $sql);
```

We can fetch data from the table using two different functions.
```php
//returns an Associative Array.
mysqli_fetch_assoc($result) 

//returns an Associative Array unless mentioned as the "result_type".
mysqli_fetch_array($result, result_type) 
```

This data can be then printed to the page into a table using `echo`.
```php
if (mysqli_num_rows($result) > 0) {
  echo "<table><tr><th>Id</th><th>FirstName</th><th>LastName</th></tr>";
  while($row = mysqli_fetch_assoc($result)) {
    echo "<tr>";
    echo "<td>" . $row["id"] . "</td>";
    echo "<td>" . $row["firstname"] . "</td>";
    echo "<td>" . $row["lastname"] . "</td>";
    echo "</tr>";
  }
  echo "</table>";
} else {
  echo "0 results.";
}
```

We can also print into a drop-down list using the select and option elements.
```php
if (mysqli_num_rows($result) > 0) {
    echo "<select>";
    while ($row = mysqli_fetch_array($result)) {
        echo "<option>" . $row["id"] . " > " . $row["firstname"] . " > " . $row["lastname"] . "</option>";
    }
    echo "</select>";
} else {
    echo "No results.";
}
```
### Data Insertion and Deletion
We can use basic SQL queries to insert and delete data from the table as well.
```php
//Query to Insert a Row.
$sql = "INSERT INTO MyGuests (firstname, lastname, email) 
VALUES ('Jaish', 'Khan', 'jaish@example.com')";

//Query to Delete a Row.
$sql = "DELETE FROM MyGuest WHERE id=1";
```

<div style="page-break-after: always;"></div>

## PHP Superglobal Variables
PHP has some special variables (arrays) that are always accessible and are system-defined. They all start with a `$_` and are uppercase. There are **9** superglobals in PHP (`$GLOBALS`, `$_SERVER`, `$_REQUEST`, `$_POST`, `$_GET`, `$_FILES`, `$_ENV`, `$_COOKIE`, `$_SESSION`).
### PHP POST vs GET
There are two ways of requesting data from the server: POST and GET.

| POST                                                           | GET                                                        |
| -------------------------------------------------------------- | ---------------------------------------------------------- |
| Data is sent as a proper request and is not visible.           | Data is attached to URL and is visible in the address bar. |
| Unlimited Data can be sent per request.                        | Only 2048 characters can be sent per request.              |
| ASCII and Binary characters; both are allowed.                 | Only ASCII characters are allowed.                         |
| Secure                                                         | Very Insecure                                              |
| Used for **sensitive data** like passwords and authentication. | Used for **trivial data** like plain text.                 |
| The client's request is stored in `$_POST` variable.           | The client's request is stored in `$_GET` variable.        |
| Heavier on the server.                                         | Lighter on the server.                                     |
We can use the `method=POST` or `method=GET` in an HTML form to submit using POST/GET. This data can then be accessed using the `$_POST` or `$_GET` superglobal variable. The `name` attribute is used to identify elements for php.
```html
<!-- index.html -->
<form action="test.php" method="GET">
  Name: <input type="text" name="name">
  E-mail: <input type="text" name="email">
  <input type="submit">
</form>
```
```php
//test.php
<?php 
echo "Welcome" . $_GET["name"];
echo "<br>Your email address is: " . $_GET["email"]; 
?>
```

<div style="page-break-after: always;"></div>

### PHP Cookies vs Sessions
Cookies and Sessions are both ways of storing user's information. This can be done for:
1. Storing the state across multiple pages.
2. Storing user settings like language (english) or theme (dark mode).
3. Tracking a user's behavior for analytics or targeted advertisement.
4. Authentication; so that user stays logged in.

| Cookies                                            | Sessions                                               |
| -------------------------------------------------- | ------------------------------------------------------ |
| Data is stored in small text files by the browser. | Data is stored in an encrypted format on the server.   |
| Limited to 4KB per cookie.                         | No Limit.                                              |
| They remain until a set amount of time.            | They remain until the user is logged in/browser is on. |
| Can be accessed by both client and server.         | Can be accessed by the server only.                    |

Cookies are created in PHP using the `setcookie(name, value, expiry)` function. They can then be accessed using the `$_COOKIE` superglobal variable.
```php
$cookie_name = "user";
$cookie_value = "Jaish Khan";

setcookie($cookie_name, $cookie_value, time() + (86400 * 30), "/"); 
//It is set to expire in 30 Days.

echo "Cookie is: " . $_COOKIE[$cookie_name];
```

Sessions are created in PHP using the `session_start()` function. We can then set them using the `$_SESSION` superglobal variable and also see the data same way. They can be emptied by the `session_unset()` function and deleted using the `session_destroy()` function.
```php
session_start();

$_SESSION["username"] = "jaishkhan";
$_SESSION["email"] = "jaishkhan771@gmail.com";

echo "Session is: " . "username=>" . $_SESSION["username"] . " email=>" . $_SESSION["email"];

session_unset();
session_destroy();
```

## Query String
This is another way of sending data via the GET method. We use a `?` after the file name and everything after that counts as query string.

```html
<a href="test.php?firstname=jaish&lastname=khan">Query String</a>
<!-- creates firstname=jaish and lastname=khan variables. -->
```

We can collect this data in the same way.
```php
echo "FirstName: " . $_GET["firstname"] . " LastName: " . $GET["lastname"];
```