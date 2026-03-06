# Lovecart
Love at doorstep
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Eli's Love Store</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
<style>
body{
margin:0;
font-family:'Poppins',sans-serif;
background:linear-gradient(135deg,#1a1a1a,#2b2140);
color:white;
}
header{
display:flex;
justify-content:space-between;
padding:20px 40px;
background:#111;
align-items:center;
}
header h1{color:#c8a2ff}
nav a{
margin:0 15px;
color:white;
text-decoration:none;
font-weight:500
}
.hero{
text-align:center;
padding:100px 20px
}
.hero h2{
font-size:48px;
color:#c8a2ff
}
.hero button{
padding:15px 30px;
font-size:18px;
background:#c8a2ff;
border:none;
border-radius:8px;
cursor:pointer
}
.products{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
gap:30px;
padding:40px
}
.card{
background:#1e1e1e;
padding:25px;
border-radius:12px;
text-align:center
}
.card h3{color:#c8a2ff}
.card button{
margin-top:10px;
padding:10px 20px;
border:none;
background:#c8a2ff;
border-radius:6px;
cursor:pointer
}
.cart{
position:fixed;
right:20px;
bottom:20px;
background:#c8a2ff;
color:black;
padding:15px 20px;
border-radius:50px;
cursor:pointer
}
.cart-panel{
position:fixed;
right:-400px;
top:0;
height:100%;
width:320px;
background:#111;
padding:20px;
transition:0.4s
}
.cart-panel.open{right:0}
.checkout{
margin-top:20px;
padding:10px;
width:100%;
background:#c8a2ff;
border:none;
border-radius:6px;
}
.message{
display:none;
text-align:center;
padding:100px 20px
}
</style>
</head>
<body>
<header>
<h1>Eli's Love Store</h1>
<nav>
<a href="#">Home</a>
<a href="#shop">Shop</a>
</nav>
</header><section class="hero">
<h2>Everything here belongs to Eli ❤️</h2>
<p>A special store made with love by Anjum</p>
<button onclick="document.getElementById('shop').scrollIntoView()">Start Shopping</button>
</section><section id="shop" class="products">
<div class="card">
<h3>💋 Kiss</h3>
<p>Redeem anytime</p>
<button onclick="addToCart('Kiss')">Add to Cart</button>
</div><div class="card">
<h3>🤗 Hug</h3>
<p>Warm tight hug</p>
<button onclick="addToCart('Hug')">Add to Cart</button>
</div><div class="card">
<h3>❤️ Pure Love</h3>
<p>Unlimited affection</p>
<button onclick="addToCart('Pure Love')">Add to Cart</button>
</div><div class="card">
<h3>🌙 Late Night Call</h3>
<p>Redeem anytime</p>
<button onclick="addToCart('Late Night Call')">Add to Cart</button>
</div><div class="card">
<h3>🎬 Movie Night</h3>
<p>Cozy time together</p>
<button onclick="addToCart('Movie Night')">Add to Cart</button>
</div><div class="card">
<h3>✈️ Malaysia Visit</h3>
<p>Coming soon</p>
<button onclick="addToCart('Malaysia Visit')">Add to Cart</button>
</div>
</section><div class="cart" onclick="toggleCart()">🛒 Cart</div><div class="cart-panel" id="cartPanel">
<h2>Your Cart</h2>
<ul id="cartItems"></ul>
<button class="checkout" onclick="checkout()">Checkout</button>
</div><section class="message" id="message">
<h1>Order Confirmed ❤️</h1>
<p>Eli, your order has been successfully placed.</p>
<p>Delivery will be personally handled by Anjum with unlimited love, hugs, kisses and a lifetime warranty of loyalty.</p>
<p>Thank you for being the most special person in his world.</p>
</section><script>
let cart=[]

function addToCart(item){
cart.push(item)
renderCart()
}

function renderCart(){
const list=document.getElementById('cartItems')
list.innerHTML=''
cart.forEach(i=>{
let li=document.createElement('li')
li.textContent=i
list.appendChild(li)
})
}

function toggleCart(){
document.getElementById('cartPanel').classList.toggle('open')
}

function checkout(){
document.getElementById('shop').style.display='none'
document.querySelector('.hero').style.display='none'
document.getElementById('cartPanel').style.display='none'
document.querySelector('.cart').style.display='none'
document.getElementById('message').style.display='block'
}
</script></body>
</html>
