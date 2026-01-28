<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>E-Commerce Website</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Arial;
}

/* NAVBAR */
nav {
  background: #1f2933;
  color: white;
  display: flex;
  justify-content: space-between;
  padding: 15px 30px;
  align-items: center;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 20px;
}

nav a {
  text-decoration: none;
  color: white;
}

.cart {
  background: #ff3b3b;
  padding: 5px 10px;
  border-radius: 20px;
}

/* PRODUCT GRID */
.products {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 25px;
  padding: 40px;
}

.card {
  border: 1px solid #ddd;
  border-radius: 12px;
  padding: 15px;
  text-align: center;
  transition: 0.3s;
}

.card:hover {
  transform: scale(1.03);
}

.card img {
  width: 100%;
}

.card button {
  margin-top: 10px;
  padding: 10px 18px;
  background: #2563eb;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 6px;
}

/* TOTAL */
.total {
  text-align: center;
  font-size: 22px;
  padding-bottom: 30px;
}

/* LOGIN */
.login {
  max-width: 350px;
  margin: 40px auto;
  border: 1px solid #ccc;
  padding: 25px;
  border-radius: 12px;
}

.login input {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
}

.login button {
  width: 100%;
  padding: 10px;
  background: green;
  color: white;
  border: none;
}

/* RESPONSIVE */
@media (max-width: 600px) {
  nav ul {
    flex-direction: column;
    gap: 10px;
  }
}
</style>
</head>

<body>

<!-- NAVBAR -->
<nav>
  <h2>E-Shop</h2>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#login">Login</a></li>
    <li class="cart">🛒 Cart: <span id="cartCount">0</span></li>
  </ul>
</nav>

<!-- PRODUCTS -->
<section class="products">
  <div class="card">
    <img src="https://via.placeholder.com/200">
    <h3>Headphones</h3>
    <p>₹1500</p>
    <button onclick="addToCart(1500)">Add to Cart</button>
  </div>

  <div class="card">
    <img src="https://via.placeholder.com/200">
    <h3>Smart Watch</h3>
    <p>₹2500</p>
    <button onclick="addToCart(2500)">Add to Cart</button>
  </div>

  <div class="card">
    <img src="https://via.placeholder.com/200">
    <h3>Shoes</h3>
    <p>₹3000</p>
    <button onclick="addToCart(3000)">Add to Cart</button>
  </div>

  <div class="card">
    <img src="https://via.placeholder.com/200">
    <h3>Backpack</h3>
    <p>₹1800</p>
    <button onclick="addToCart(1800)">Add to Cart</button>
  </div>
</section>

<!-- TOTAL PRICE -->
<div class="total">
  Total Price: ₹<span id="totalPrice">0</span>
</div>

<!-- LOGIN SECTION -->
<section class="login" id="login">
  <h2>Login</h2>
  <input type="text" placeholder="Username">
  <input type="password" placeholder="Password">
  <button>Login</button>
</section>

<script>
let cart = 0;
let total = 0;

function addToCart(price) {
  cart++;
  total += price;

  document.getElementById("cartCount").innerText = cart;
  document.getElementById("totalPrice").innerText = total;
}
</script>

</body>
</html>
