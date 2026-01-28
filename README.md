<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>E-Commerce Website</title>

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:Arial;
}

body{
  background:#f4f6f8;
}

/* NAVBAR */
nav{
  display:flex;
  justify-content:space-between;
  align-items:center;
  background:#0d1b2a;
  color:white;
  padding:15px 30px;
}

nav ul{
  list-style:none;
  display:flex;
  gap:25px;
}

nav a{
  color:white;
  text-decoration:none;
}

.cart{
  background:orange;
  padding:6px 14px;
  border-radius:20px;
}

/* PRODUCT GRID */
.products{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:25px;
  padding:30px;
}

.card{
  background:white;
  padding:15px;
  border-radius:10px;
  text-align:center;
  box-shadow:0 0 10px rgba(0,0,0,0.1);
}

.card button{
  margin-top:10px;
  padding:10px 18px;
  background:#1b9aaa;
  color:white;
  border:none;
  border-radius:5px;
  cursor:pointer;
}

/* CART */
.cart-box{
  background:white;
  margin:30px;
  padding:20px;
  border-radius:10px;
}

.cart-item{
  margin:8px 0;
  padding:8px;
  border-bottom:1px solid #ddd;
}

/* LOGIN */
.login{
  background:white;
  margin:30px auto;
  width:300px;
  padding:25px;
  border-radius:10px;
}

.login input{
  width:100%;
  padding:10px;
  margin:10px 0;
}

@media(max-width:600px){
  nav ul{display:none;}
}
</style>
</head>

<body>

<!-- NAVBAR -->
<nav>
  <h2>ShopEase</h2>
  <ul>
    <li><a href="#home">Home</a></li>
    <li><a href="#cart">Cart</a></li>
    <li><a href="#login">Login</a></li>
  </ul>
  <div class="cart">🛒 <span id="count">0</span></div>
</nav>

<!-- PRODUCTS -->
<section class="products" id="home">

  <div class="card">
    <h3>Headphones</h3>
    <p>₹1500</p>
    <button onclick="addToCart('Headphones',1500)">Add to Cart</button>
  </div>

  <div class="card">
    <h3>Smart Watch</h3>
    <p>₹2500</p>
    <button onclick="addToCart('Smart Watch',2500)">Add to Cart</button>
  </div>

  <div class="card">
    <h3>Shoes</h3>
    <p>₹3000</p>
    <button onclick="addToCart('Shoes',3000)">Add to Cart</button>
  </div>

</section>

<!-- CART -->
<div class="cart-box" id="cart">
  <h3>Cart Summary</h3>
  <div id="cartItems"></div>
  <h4>Total: ₹<span id="total">0</span></h4>
</div>

<!-- LOGIN -->
<div class="login" id="login">
  <h3>Login</h3>
  <input type="text" placeholder="Username">
  <input type="password" placeholder="Password">
  <button style="width:100%;padding:10px;background:#0d1b2a;color:white;">
    Login
  </button>
</div>

<script>
let cart = [];

function addToCart(name, price){
  cart.push({name, price});
  updateCart();
}

function updateCart(){
  document.getElementById("count").innerText = cart.length;

  let cartBox = document.getElementById("cartItems");
  cartBox.innerHTML = "";

  let total = 0;

  cart.forEach(item => {
    let div = document.createElement("div");
    div.className = "cart-item";
    div.innerText = item.name + " - ₹" + item.price;
    cartBox.appendChild(div);
    total += item.price;
  });

  document.getElementById("total").innerText = total;
}
</script>

</body>
</html>
