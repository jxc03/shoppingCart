<h1 align="center">
  Shopping Cart
</h1>

<p>
  With this I learnt how to define classes and use them by creating class instances and implementing methods for data manipulation. This project will cover concepts like the ternary operator, the spread operator, the this keyword, and more.
</p>

## Preview
https://github.com/user-attachments/assets/0038d74d-900b-437b-b43a-48f4e31353b7

## Steps
**S1**<br>
You will be building a shopping cart application. The HTML and CSS are already provided, but you will need to build the JavaScript to make the page interactive.<br>

To start, you will need to get some of your elements from the DOM. Start by using `document.getElementById()` to get the `#cart-container`, `#products-container`, and `#dessert-card-container` elements. Store them in variables named `cartContainer`, `productsContainer`, and `dessertCards`, respectively. Since these will not change, remember to use `const` to declare them.

```js
const cartContainer = document.getElementById("cart-container");
const productsContainer = document.getElementById("products-container");
const dessertCards = document.getElementById("dessert-card-container");
```

**S2**<br>
Now you need to get your two buttons. Continuing the pattern, get the `#cart-btn` and `#clear-cart-btn` elements. Store them in variables named `cartBtn` and `clearCartBtn`, respectively.

```js
const cartBtn = document.getElementById("cart-btn");
const clearCartBtn = document.getElementById("clear-cart-btn");
```

**S3**<br>
Next is to get your totals. Get the `#total-items`, `#subtotal`, `#taxes`, and `#total` elements. Store them in variables named `totalNumberOfItems`, `cartSubTotal`, `cartTaxes`, and `cartTotal`, respectively.

```js
const totalNumberOfItems = document.getElementById("total-items");
const cartSubTotal = document.getElementById("subtotal");
const cartTaxes = document.getElementById("taxes");
const cartTotal = document.getElementById("total");
```

**S4**<br>
The last element to get is the `#show-hide-cart` element. Store it in a variable named `showHideCartSpan`. Then, use `let` to declare a variable named `isCartShowing` and set it to `false`.

```js
const showHideCartSpan = document.getElementById("show-hide-cart");
let isCartShowing = false;
```

**S5**<br>
A shopping cart does not serve much purpose without products. Declare a `products` variable and set it to an empty array. Using an array will allow you to store multiple products.

```js
const products = [];
```

**S6**<br>
You now need to start adding products. Before you do that, you need to consider the structure of your product data. A product will need a unique identifier to distinguish it from other products, a price so people know how much it costs, and a name so people know what they are buying. You should also add a category to each product.

Add an object to your `products` array. Give this object an `id` property set to the number `1`, a `name` property set to the string `"Vanilla Cupcakes (6 Pack)"`, a `price` property set to the number `12.99`, and a `category` property set to the string `"Cupcake"`.

```js
const products = [
  {id: 1, 
  name: "Vanilla Cupcakes (6 Pack)", 
  price: 12.99, 
  category: "Cupcake"}
];
```

**S7**<br>
Following that same data structure, add the products from this table (in order) to your `products` array. Increment the `id` for each product, counting up.<br>

`name	price	category`<br>
`French Macaron	3.99	Macaron`<br>
`Pumpkin Cupcake	3.99	Cupcake`<br>
`Chocolate Cupcake	5.99	Cupcake`<br>
`Chocolate Pretzels (4 Pack)	10.99	Pretzel`<br>
`Strawberry Ice Cream	2.99	Ice Cream`<br>
`Chocolate Macarons (4 Pack)	9.99	Macaron`<br>
`Strawberry Pretzel	4.99	Pretzel`<br>
`Butter Pecan Ice Cream	2.99	Ice Cream`<br>
`Rocky Road Ice Cream	2.99	Ice Cream`<br>
`Vanilla Macarons (5 Pack)	11.99	Macaron`<br>
`Lemon Cupcakes (4 Pack)	12.99	Cupcake`<br>

```js
{
    id: 2,
    name: "French Macaron",
    price: 3.99,
    category: "Macaron",
},
{
    id: 3,
    name: "Pumpkin Cupcake",
    price: 3.99,
    category: "Cupcake",
},
{
    id: 4,
    name: "Chocolate Cupcake",
    price: 5.99,
    category: "Cupcake",
},
{
    id: 5,
    name: "Chocolate Pretzels (4 Pack)",
    price: 10.99,
    category: "Pretzel",
},
{
    id: 6,
    name: "Strawberry Ice Cream",
    price: 2.99,
    category: "Ice Cream",
},
{
    id: 7,
    name: "Chocolate Macarons (4 Pack)",
    price: 9.99,
    category: "Macaron",
},
{
    id: 8,
    name: "Strawberry Pretzel",
    price: 4.99,
    category: "Pretzel",
},
{
    id: 9,
    name: "Butter Pecan Ice Cream",
    price: 2.99,
    category: "Ice Cream",
},
{
    id: 10,
    name: "Rocky Road Ice Cream",
    price: 2.99,
    category: "Ice Cream",
},
{
    id: 11,
    name: "Vanilla Macarons (5 Pack)",
    price: 11.99,
    category: "Macaron",
},
{
    id: 12,
    name: "Lemon Cupcakes (4 Pack)",
    price: 12.99,
    category: "Cupcake",
},
```

**S8**<br>
Now that you have your list of products, you can use JavaScript to insert them into the HTML. With this approach, if you decide to add more products, the HTML will automatically reflect that.<br>

Start by calling the `.forEach` method of your `products` array. Use arrow syntax to create an empty callback function.

```js
products.forEach(() => {});
```

**S9**<br>
Remember that you can use destructuring to extract multiple values from an array or object in a single statement.<br>

For the first parameter of your callback function, destructure the `name`, `id`, `price`, and `category` properties from the object passed in.

```js
products.forEach(
  ({name, id, price, category}) => {}
);
```

**S10**<br>
You need to display the available products in your HTML. Start by using the addition assignment operator to add an empty template literal string to the `innerHTML` property of the `dessertCards` variable.

```js
({ name, id, price, category }) => {
    dessertCards.innerHTML += ``
  }
```

**S11**<br>
In your template literal, create a `div` element with a class of `dessert-card`. In that `div`, create an `h2` element and give it the text of the `name` variable.

```js
dessertCards.innerHTML += `
<div class="dessert-card">
    <h2>${name}</h2>
</div>
`;
```

**S12**<br>
After your `h2` element, create two `p` elements. Give the first a `class` of `dessert-price`, and the text of the `price` variable with a dollar sign in front of it. Give the second a `class` of `product-category`, and the text `"Category: "` followed by the value of the `category` variable.

```js
<p class="dessert-price">$${price}</p>
<p class="product-category">Category: ${category}</p>
```

**S13**<br>
Finally, after your `p` elements, create a `button` element. Give it an `id` set to the value of the `id` variable, a `class` of btn add-to-cart-btn, and use `"Add to cart"` for the text.

```js
<button id="${id}" class="btn add-to-cart-btn">Add to cart</button>
```

**S14**<br>
You are already familiar with an HTML `class`, but JavaScript also has a class. In JavaScript, a class is like a blueprint for creating objects. It allows you to define a set of properties and methods, and instantiate (or create) new objects with those properties and methods.<br>

The `class` keyword is used to declare a class. Here is an example of declaring a `Computer` class:<br>
<b>`Example Code`</b><br>
`class Computer {};`<br>

Declare a `ShoppingCart` class.

```js
class ShoppingCart {};
```

**S15**<br>
Classes have a special `constructor` method, which is called when a new instance of the class is created. The `constructor` method is a great place to initialize properties of the class.<br>

Here is an example of a class with a `constructor` method:<br>
<b>`Example Code`</b><br>
`class Computer {`<br>
  `constructor() {`<br>
  `}`<br>
`}`<br>

Add an empty `constructor` method to the `ShoppingCart` class.

```js
class ShoppingCart {
  constructor() {}
};
```

**S16**<br>
The `this` keyword in JavaScript is used to refer to the current object. Depending on where `this` is used, what it references changes. In the case of a class, it refers to the instance of the object being constructed. You can use the `this` keyword to set the properties of the object being instantiated.<br> 

Here is an example:<br>
`Example Code`<br>
`class Computer {`<br>
  `constructor() {`<br>
    `this.ram = 16;`<br>
  `}`<br>
`}`<br>

In your constructor, use the `this` keyword to set the `items` property to an empty array. Also, set the `total` property to `0`, and the `taxRate` property to `8.25`.

```js
constructor() {
    this.items = [];
    this.total = 0;
    this.taxRate = 8.25;
}
```

**S17**<br>
Your `ShoppingCart` class needs the ability to add items. Create an empty `addItem` method, which takes two parameters: `id` and `products`. 

Creating a method might look like this:<br>
`Example Code`<br>
`class Computer {`<br>
  `constructor() {`<br>
    `this.ram = 16;`<br>
  `}`<br>
  `addRam(amount) {`<br>
    `this.ram += amount;`<br>
  `}`<br>
`}`<br>

The first parameter, `id`, is the `id` of the product the user has added to their cart. The second parameter, `products`, is an array of product objects. By using a parameter instead of directly referencing your existing `products` array, this method will be more flexible if you wanted to add additional product lists in the future.

```js
addItem(id, products) {}
```

**S18**<br>
You need to find the product that the user is adding to the cart. Remember that arrays have a `.find()` method. In your `addItem` function, declare a `product` variable, and assign it the value of calling the `.find()` method on the `products` array.<br>

For the callback to `.find()`, pass a function that takes a single parameter `item`, and returns whether the `id` property of `item` is strictly equal to the `id` parameter passed to `addItem`.

```js
addItem(id, products) {
    const product = products.find((item) => item.id === id);
}
```

**S19**<br>
Use `const` and destructuring to extract `name` and `price` variables from `product`.

```js
const {name, price} = product;
```

**S20**<br>
Now you need to push the `product` into the cart's `items` array. Remember to use the `this` keyword.

```js
this.items.push(product);
```

**S21**<br>
You now need a total count of each product that the user has in the cart. Declare a `totalCountPerProduct` variable, and assign it an empty object.

```js
const totalCountPerProduct = {};
```

**S22**<br>
Use the `.forEach()` method to loop through the `items` array. Pass an empty callback function that takes a single parameter `dessert`.

```js
this.items.forEach((dessert) => {})
```

**S23**<br>
In your `forEach` callback, you need to update the `totalCountPerProduct` object. Using the `id` of the current `dessert`as your property, update the value of the property to be the current value plus one. Do not use the addition assignment operator for this.

```js
totalCountPerProduct[dessert.id] =  totalCountPerProduct[dessert.id] + 1;
```

**S24**<br>
You now have a small bug. When you try to access a property of an object and the property doesn't exist, you get `undefined`. This means if the dessert isn't already present in the `totalCountPerProduct` object, you end up trying to add `1` to `undefined`, which results in `NaN`.

To fix this, you can use the `||` operator to set the value to `0` if it doesn't exist. Wrap your right-hand `totalCountPerProduct[dessert.id]` in parentheses, and add `|| 0` to the end of the expression.

```js
totalCountPerProduct[dessert.id] = (totalCountPerProduct[dessert.id] || 0) + 1;
```

**S25**<br>
Now you need to get prepared to update the display with the new product the user added. Declare a `currentProductCount` variable, and assign it the value of the `totalCountPerProduct` object's property matching the `id` of `product`.

```js
const currentProductCount = totalCountPerProduct[product.id]
```

**S26**<br>
You haven't written the code to generate the HTML yet, but if a product has already been added to the user's cart then there will be a matching element which you'll need.<bnr>

Use `.getElementById()` to get the matching element - you'll be setting the `id` value to `product-count-for-id${product.id}`, so use a template literal to query that value. Assign your query to a `  currentProductCountSpan` variable.

```js
const currentProductCountSpan = document.getElementById(`product-count-for-id${product.id}`)
```

**S27**<br>
The behaviour of the `addItem` method needs to change if the product is already in the cart or not. Create a ternary that checks if the current product is already in the cart. Use `undefined` for both the truthy and falsy expressions to avoid a syntax error.

```js
currentProductCount > 1 ? undefined : undefined;
```

**S28**<br>
For your truthy expression, removing the `undefined`, you need to update the `textContent` of the `currentProductCountSpan` to be the `currentProductCount` followed by an `x`. Use a template literal to do so.

```js
currentProductCount > 1 ? currentProductCountSpan.textContent = `${currentProductCount}x` : undefined;
```

**S29**<br>
For your falsy expression, you'll need to add new HTML to your `productsContainer`. Start by removing the `undefined`, then use the addition assignment operator and template literal syntax to add a div with the `class` set to `product` and the `id` set to `dessert${id}` to the `innerHTML` property of the `productsContainer`.

```js
currentProductCount > 1 
    ? currentProductCountSpan.textContent = `${currentProductCount}x`
    : productsContainer.innerHTML += `
    <div id="dessert${id}" class="product">
    </div
    `;
```

**S30**<br>
Inside your `div`, add two `p` elements. Set the text of the second `p` element to be the value of the `price` variable.

```js
<p></p>
<p>${price}</p>
```

**S31**<br>
In your first `p` element, add a `span` element. Give the `span` a class of `product-count` and an `id` of `product-count-for-id${id}`. Then, after the span, give your `p` element the text of the `name` variable.

```js
<p><span class="product-count" id="product-count-for-id${id}">${name}</span></p>
```

**S32**<br>
There is still more functionality that your `ShoppingCart` class needs, but first you need to be able to test the code you have currently written. You'll need to <i>instantiate</i> a new `ShoppingCart` object and assign it to a variable.<br>

Here is an example of instantiating the `Computer` class from earlier examples:<br>
<b>`Example Code`</b><br>
`const myComputer = new Computer();`<br>

Declare a `cart` variable, and assign it a new `ShoppingCart` object. Note the use of the `new` keyword when instantiating the object.

```js
const cart = new ShoppingCart();
```

**S33**<br>
You need to get all of the `Add to cart` buttons that you added to the DOM earlier. Declare an `addToCartBtns` variable, and assign it the value of calling the `getElementsByClassName()` method on the `document` object, passing in the string `"add-to-cart-btn"`.

```js
const addToCartBtns  = document.getElementsByClassName("add-to-cart-btn");
```

**S34**<br>
You need to iterate through the buttons in your `addToCartBtns` variable. However, `.getElementsByClassName()` returns a Collection, which does not have a `forEach` method.<br>

Use the spread operator on the `addToCartBtns` variable to convert it into an array. Then, use the `forEach` method to iterate through the array. Do not pass a callback function yet.

```js
[...addToCartBtns].forEach();
```

**S35**<br>
Add your callback function to the `forEach` method. It should take a `btn` parameter. Then, in the callback, add an event listener to the `btn`. The event listener should listen for a `click` event, and should take another callback with an `event` parameter. The second callback should be empty.

```js
[...addToCartBtns].forEach(
  (btn) => {
    btn.addEventListener("click", (event) => {})
  }
);
```

**S36**<br>
In your event listener callback, call the `.addItem()` method of your `cart` object, and pass in the `event.target.id`. Remember that the `id` here will be a string, so you need to convert it to a number.<br>

Pass your `products` array as the second argument.

```js
btn.addEventListener("click", (event) => {
  cart.addItem(Number(event.target.id), products)
})
```

**S37**<br>
Your cart currently isn't visible on the webpage. To make it visible, start by adding an event listener to the `cartBtn` variable, listening for the click event. The callback does not need any parameters.

```js
cartBtn.addEventListener("click", () => {})
```

**S38**<br>
Start by inverting the value of `isCartShowing`. Remember that you can use the logical not operator `!` to invert the value of a boolean. Assign the inverted value to `isCartShowing`.

```js
cartBtn.addEventListener("click", () => {
  isCartShowing = !isCartShowing;
});
```

**S39**<br>
Now assign the `textContent` of the `showHideCartSpan` variable the result of a ternary expression which checks if `isCartShowing` is true. If it is, set the `textContent` to `"Hide"`, otherwise set it to `"Show"`.

```js
showHideCartSpan.textContent = isCartShowing ? "Hide" : "Show"
```

**S40**<br>
Finally, update the `display` property of the `style` object of the `cartContainer` variable to another ternary which checks if `isCartShowing` is true. If it is, set the `display` property to `"block"`, otherwise set it to `"none"`.<br>

Now you should be able to see your cart and add items to it.

```js
cartContainer.style.display = isCartShowing ? "block" : "none"
```

**S41**<br>
You need a way to access the total number of items in the cart. The best way to do this is to add another method to your `ShoppingCart` class, rather than accessing the `items` array directly.<br>

Add a `getCounts` method to the `ShoppingCart` class. It should return the number of items in the `items` array.

```js
getCounts() {
  return this.items.length
}
```

**S42**<br>
Now you can update the total number of items on the webpage. Assign the value of your `cart` object's `.getCounts()` method to the `textContent` of the `totalNumberOfItems` variable.

```js
totalNumberOfItems.textContent = cart.getCounts()
```

**S43**<br>
You also need to update the total price of the cart when the user adds an item. Create a `calculateTotal` method in the `ShoppingCart` class.<br>

In that method, declare a `subTotal` variable and use the `reduce` method on the `items` array to calculate the sum of the `price` property of each item in the array. Use `total` and `item` as the parameters for your callback. Remember to set your initial value in the `reduce` method.

```js
calculateTotal() {
  const subTotal = this.items.reduce((total, item) => total + item.price, 0);
}
```

**S44**<br>
Part of the total cost will include the tax, so you need to calculate that as well. Create a `calculateTaxes` method in the `ShoppingCart` class. This method should take an `amount` parameter.

```js
calculateTaxes(amount) {}
```

**S45**<br>
Your `calculateTaxes` method should return the value of the `taxRate` (divided by 100, to convert it to a percent) multiplied by the `amount` parameter.

For clarity, wrap the `taxRate / 100` calculation in parentheses.

```js
calculateTaxes(amount) {
  return (this.taxRate / 100) * amount
}
```

**S46**<br>
Because of the way computers store and work with numbers, calculations involving decimal numbers can result in some strange behavior. For example, `0.1 + 0.2` is not equal to `0.3`. This is because computers store decimal numbers as binary fractions, and some binary fractions cannot be represented exactly as decimal fractions.<br>

We want to clean up the number result from your calculation. Wrap your calculation in parentheses (don't include the return statement!) and call the `.toFixed()` method on it. Pass the `.toFixed()` method the number `2` as an argument. This will round the number to two decimal places and return a string.

```js
return ((this.taxRate / 100) * amount).toFixed(2);
```

**S47**<br>
The issue with `.toFixed()` returning a string is that you want to be able to perform calculations with the tax rate. To fix this, you can pass the `.toFixed()` call (including the calculation) to the `parseFloat()` function. This will convert the fixed string back into a number, preserving the existing decimal places. <br>

Pass your `.toFixed()` call to `parseFloat()`.

```js
return parseFloat(((this.taxRate / 100) * amount).toFixed(2));
```

**S48**<br>
Declare a variable `tax` and assign it the value of calling your new `.calculateTaxes()` method, passing `subTotal` as the argument.

```js
const tax = this.calculateTaxes(subTotal);
```

**S49**<br>
Update the `total` value to be the sum of the `subTotal` and `tax` values.

```js
this.total = subTotal + tax;
```

**S50**<br>
You're going to update the HTML in this method as well. Set the `textContent` of the `cartSubTotal` to be the value of `subTotal` to a fixed 2 decimal places. Use template literal syntax to add the dollar sign to the beginning of the value.

```js
cartSubTotal.textContent = `$${subTotal.toFixed(2)}`;
```

**S51**<br>
Following the same pattern as your `cartSubTotal`, update the `cartTaxes` to display the `tax` value, and your `cartTotal` to display the `total` property.

```js
CartTaxes.textContent = `$${tax.toFixed(2)}`;
cartTotal.textContent = `$${this.total.toFixed(2)}`;
```

**S52**<br>
Finally, return the value of the `total` property. Remember your `this` keyword.

```js
return this.total;
```

**S53**<br>
Now call your `.calculateTotal()` method inside your `forEach` loop.

```js
return cart.calculateTotal();
```

**S54**<br>
Your last feature is to allow users to clear their cart. Add a `clearCart()` method to your `ShoppingCart` class.

```js
clearCart() {}
```

**S55**<br>
The first thing you should do is check if the `items` array is empty. If it is, display an `alert` to the user with the text `Your shopping cart is already empty`, then return from the function.<br>

Remember that `0` is a falsy value, so you can use the `!` operator to check if the array is empty. After displaying the alert, return from the function to stop execution.


```js
clearCart() {
  if (!this.items.length) {
    alert("Your shopping cart is already empty");
    return;
  }
}
```

**S56**<br>
Browsers have a built-in `confirm()` function which displays a confirmation prompt to the user. `confirm()` accepts a string, which is the message displayed to the user. It returns `true` if the user confirms, and `false` if the user cancels.<br>

Declare a variable `isCartCleared` and assign it the value of calling `confirm()` with the string `"Are you sure you want to clear all items from your shopping cart?"`.

```js
const isCartCleared = confirm("Are you sure you want to clear all items from your shopping cart?");
```

**S57**<br>
You only want to clear the cart if the user confirms the prompt. Create an `if` statement that checks if the user confirmed the prompt.<br>

In the `if` statement, set the `items` property back to an empty array, then set the `total` property to `0`.

```js
if (isCartCleared) {
  this.items = [];
  this.total = 0;
}
```

**S58**<br>
You also need to start clearing the HTML. Set the `innerHTML` property of the `productsContainer` back to an empty string.

```js
productsContainer.innerHTML = "";
```

**S59**<br>
Set the `textContent` of the `totalNumberOfItems`, `cartSubTotal`, `cartTaxes`, and `cartTotal` elements all to the number `0`.

```js
totalNumberOfItems.textContent = 0;
cartSubTotal.textContent = 0;
cartTaxes.textContent = 0;
cartTotal.textContent = 0;
```

**S60**<br>
Your final step is to make your clear button functional. Add a `click` event listener to the `clearCartBtn`. For the callback, you can pass in `cart.clearCart` directly.<br>

However, doing so will not work, because the context of `this` will be the `clearCartBtn` element. You need to bind the `clearCart` method to the `cart` object.<br>

You can do this by passing `cart.clearCart.bind(cart)` as the callback. And with that, your shopping cart project is complete!

```js
clearCartBtn.addEventListener('click', cart.clearCart.bind(cart));
```
