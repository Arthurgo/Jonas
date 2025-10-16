<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Joninja Churros</title>
<style>
  * {margin:0; padding:0; box-sizing:border-box; font-family: 'Arial', sans-serif;}
  body {background:#fff8f0; color:#5c3a21;}
  a {text-decoration:none; color:inherit;}

  header {background:#d2691e; padding:20px; text-align:center; color:#fff; position:sticky; top:0; z-index:100;}
  header h1 {font-size:2em;}
  header p {font-size:1.1em; margin-top:5px;}

  /* Banner rotativo */
  .banner {position:relative; height:300px; overflow:hidden;}
  .banner-slide {position:absolute; width:100%; height:100%; display:flex; align-items:center; justify-content:center; flex-direction:column; transition:opacity 1s; opacity:0;}
  .banner-slide.active {opacity:1;}
  .banner-slide h2 {font-size:2em; color:#fff; text-shadow:2px 2px 5px #000;}
  .banner-slide p {font-size:1.2em; color:#fff; text-shadow:1px 1px 3px #000;}

  /* Cardápio */
  .menu {display:flex; flex-wrap:wrap; justify-content:center; padding:20px; gap:20px;}
  .item {background:#fff3e0; border-radius:10px; width:200px; padding:15px; text-align:center; box-shadow:0 5px 10px rgba(0,0,0,0.1); transition:transform 0.3s;}
  .item:hover {transform:scale(1.05);}
  .item img {width:100%; border-radius:10px; margin-bottom:10px;}
  .item h3 {margin-bottom:5px;}
  .item p {margin-bottom:10px;}
  .item button {background:#d2691e; color:#fff; border:none; padding:10px 15px; border-radius:5px; cursor:pointer;}
  .item button:hover {background:#b2551a;}

  /* Carrinho */
  .cart {position:fixed; right:20px; top:100px; width:250px; background:#fff3e0; padding:15px; border-radius:10px; box-shadow:0 5px 10px rgba(0,0,0,0.2);}
  .cart h3 {text-align:center; margin-bottom:10px;}
  .cart-items {max-height:300px; overflow-y:auto; margin-bottom:10px;}
  .cart-item {display:flex; justify-content:space-between; margin-bottom:5px; transition:all 0.3s;}
  .cart-item.added {animation:addItem 0.5s;}
  @keyframes addItem {0%{transform:translateX(-50px); opacity:0;}100%{transform:translateX(0); opacity:1;}}
  .cart-total {text-align:center; margin-bottom:10px;}
  .cart button {width:100%; background:#28a745; color:#fff; border:none; padding:10px; border-radius:5px; cursor:pointer;}
  .cart button:hover {background:#218838;}

  /* Depoimentos */
  .depoimentos {background:#f5deb3; padding:40px 20px; text-align:center;}
  .depoimentos h2 {margin-bottom:20px;}
  .depoimentos .depo {margin-bottom:15px; font-style:italic;}

  /* Endereço */
  .contato {padding:20px; text-align:center; background:#fff3e0;}
  .contato h2 {margin-bottom:15px;}
  .contato p {margin-bottom:5px;}

  @media(max-width:768px){.menu{flex-direction:column; align-items:center;}.cart{position:static; margin:20px auto;}}
</style>
</head>
<body>

<header>
  <h1>Joninja Churros</h1>
  <p>O melhor churros da cidade!</p>
</header>

<section class="banner">
  <div class="banner-slide active" style="background:#d2691e url('https://i.imgur.com/Oa0q0lm.jpg') center/cover no-repeat;">
    <h2>Churros Tradicional</h2>
    <p>O clássico que todo mundo ama!</p>
  </div>
  <div class="banner-slide" style="background:#b5651d url('https://i.imgur.com/UDwMLlH.jpg') center/cover no-repeat;">
    <h2>Churros de Chocolate</h2>
    <p>Recheado e irresistível!</p>
  </div>
  <div class="banner-slide" style="background:#c68642 url('https://i.imgur.com/h3i6k3P.jpg') center/cover no-repeat;">
    <h2>Churros Doce de Leite</h2>
    <p>Um sabor que derrete na boca!</p>
  </div>
</section>

<section class="menu">
  <div class="item">
    <img src="https://i.imgur.com/Oa0q0lm.jpg" alt="Churros Tradicional">
    <h3>Tradicional</h3>
    <p>R$8,00</p>
    <button onclick="addToCart('Tradicional', 8)">Adicionar 🍩</button>
  </div>
  <div class="item">
    <img src="https://i.imgur.com/UDwMLlH.jpg" alt="Churros Chocolate">
    <h3>Chocolate</h3>
    <p>R$10,00</p>
    <button onclick="addToCart('Chocolate', 10)">Adicionar 🍫</button>
  </div>
  <div class="item">
    <img src="https://i.imgur.com/h3i6k3P.jpg" alt="Churros Doce de Leite">
    <h3>Doce de Leite</h3>
    <p>R$12,00</p>
    <button onclick="addToCart('Doce de Leite', 12)">Adicionar 🥐</button>
  </div>
  <div class="item">
    <img src="https://i.imgur.com/yQ9yZra.jpg" alt="Churros Nutella">
    <h3>Nutella</h3>
    <p>R$15,00</p>
    <button onclick="addToCart('Nutella', 15)">Adicionar 🍫</button>
  </div>
</section>

<div class="cart">
  <h3>Carrinho 🛒</h3>
  <div class="cart-items" id="cart-items"></div>
  <div class="cart-total" id="cart-total">Total: R$0,00</div>
  <button onclick="checkout()">Finalizar Pedido 📲</button>
</div>

<section class="depoimentos">
  <h2>O que nossos clientes dizem</h2>
  <p class="depo">"Melhor churros que já comi! Sempre volto!" – Maria S.</p>
  <p class="depo">"Recomendo demais! Atendimento ótimo e sabor incrível." – João P.</p>
  <p class="depo">"Churros fresquinho e delicioso. Amo o de Nutella!" – Ana L.</p>
</section>

<section class="contato">
  <h2>Visite ou peça pelo WhatsApp</h2>
  <p>📍 Rua do Churros, 123, Cidade</p>
  <p>📱 WhatsApp: <a href="https://wa.me/5535991027992" target="_blank">(35) 99102-7992</a></p>
</section>

<script>
  let cart = [];

  function addToCart(name, price){
    cart.push({name, price});
    updateCart();
  }

  function updateCart(){
    const cartItems = document.getElementById('cart-items');
    const cartTotal = document.getElementById('cart-total');
    cartItems.innerHTML = '';
    let total = 0;
    cart.forEach((item)=>{
      total += item.price;
      let div = document.createElement('div');
      div.className = 'cart-item added';
      div.innerHTML = `${item.name} <span>R$${item.price.toFixed(2)}</span>`;
      cartItems.appendChild(div);
    });
    cartTotal.innerText = `Total: R$${total.toFixed(2)}`;
  }

  function checkout(){
    if(cart.length===0){alert('Seu carrinho está vazio!'); return;}
    let message = 'Olá, quero fazer o pedido:%0A';
    cart.forEach(item=>{
      message += `- ${item.name} R$${item.price.toFixed(2)}%0A`;
    });
    let total = cart.reduce((sum, item)=>sum+item.price,0);
    message += `Total: R$${total.toFixed(2)}`;
    window.open(`https://wa.me/5535991027992?text=${message}`, '_blank');
  }

  // Banner rotativo
  let slides = document.querySelectorAll('.banner-slide');
  let currentSlide = 0;
  setInterval(()=>{
    slides[currentSlide].classList.remove('active');
    currentSlide = (currentSlide+1)%slides.length;
    slides[currentSlide].classList.add('active');
  },5000);
</script>

</body>
</html>
