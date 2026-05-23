Join the most profitable company in Kenya trusted by millions of people
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>InvestPro Kenya</title>

<link rel="stylesheet"
href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"/>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{
background:#f4f5f7;
padding-bottom:120px;
}

header{
background:white;
padding:18px;
display:flex;
justify-content:space-between;
align-items:center;
box-shadow:0 2px 10px rgba(0,0,0,0.08);
position:sticky;
top:0;
z-index:100;
}

.logo{
display:flex;
align-items:center;
gap:10px;
}

.logo i{
font-size:28px;
color:#16a34a;
}

.logo h1{
font-size:28px;
}

.logo span{
color:#16a34a;
}

.balance-card{
background:white;
margin:20px;
padding:30px;
border-radius:25px;
text-align:center;
box-shadow:0 5px 20px rgba(0,0,0,0.08);
}

.balance-card h2{
font-size:50px;
color:#16a34a;
margin:10px 0;
}

.spin-btn{
width:100%;
padding:18px;
border:none;
border-radius:15px;
background:linear-gradient(to right,#059669,#22c55e);
color:white;
font-size:22px;
font-weight:bold;
margin-top:20px;
cursor:pointer;
}

.section-title{
padding:0 20px;
margin-top:30px;
display:flex;
justify-content:space-between;
align-items:center;
}

.section-title h2{
font-size:34px;
}

.vip{
background:#ff9800;
padding:10px 18px;
border-radius:12px;
color:white;
font-weight:bold;
}

.packages{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
gap:18px;
padding:20px;
}

.card{
background:white;
padding:25px;
border-radius:22px;
text-align:center;
box-shadow:0 4px 15px rgba(0,0,0,0.06);
transition:0.3s;
}

.card:hover{
transform:translateY(-5px);
}

.card h3{
font-size:32px;
margin-bottom:12px;
}

.profit{
font-size:22px;
font-weight:bold;
color:#16a34a;
margin-bottom:8px;
}

.buy-btn{
margin-top:15px;
padding:14px 20px;
border:none;
border-radius:12px;
background:#16a34a;
color:white;
font-size:18px;
cursor:pointer;
width:100%;
}

.deposit-box{
background:white;
margin:20px;
padding:25px;
border-radius:20px;
box-shadow:0 4px 15px rgba(0,0,0,0.06);
}

.deposit-box h2{
margin-bottom:15px;
}

.deposit-box input{
width:100%;
padding:15px;
margin-top:10px;
border-radius:12px;
border:1px solid #ccc;
font-size:18px;
}

.deposit-btn{
width:100%;
padding:16px;
margin-top:15px;
background:#16a34a;
color:white;
border:none;
border-radius:12px;
font-size:20px;
font-weight:bold;
cursor:pointer;
}

.float-btn{
position:fixed;
right:20px;
bottom:90px;
width:70px;
height:70px;
border-radius:50%;
display:flex;
justify-content:center;
align-items:center;
font-size:30px;
color:white;
background:#22c55e;
box-shadow:0 4px 20px rgba(0,0,0,0.2);
text-decoration:none;
}

footer{
position:fixed;
bottom:0;
width:100%;
background:white;
display:flex;
justify-content:space-around;
padding:15px 0;
box-shadow:0 -2px 10px rgba(0,0,0,0.08);
}

footer div{
text-align:center;
font-size:14px;
}

footer i{
display:block;
font-size:22px;
margin-bottom:4px;
color:#16a34a;
}

@media(max-width:768px){

.section-title h2{
font-size:26px;
}

.card h3{
font-size:26px;
}

}

</style>
</head>

<body>

<header>
<div class="logo">
<i class="fa-solid fa-chart-line"></i>
<h1>Invest<span>Pro</span></h1>
</div>

<i class="fa-solid fa-bars"></i>
</header>

<section class="balance-card">
<h4>Total Earnings</h4>
<h2 id="earnings">KSh 0</h2>
<p>Grow your portfolio daily</p>

<button class="spin-btn">
✨ Daily Harvest Bonus
</button>
</section>

<div class="section-title">
<h2>Investment Packages</h2>
<div class="vip">VIP</div>
</div>

<section class="packages" id="packages"></section>

<section class="deposit-box">

<h2>M-Pesa Deposit</h2>

<p><strong>Paybill/Till:</strong> 4498280</p>

<input type="text" id="phone" placeholder="07XXXXXXXX">

<input type="number" id="amount" placeholder="Amount">

<button class="deposit-btn" onclick="payNow()">
Deposit via M-Pesa
</button>

</section>

<a href="https://wa.me/254753608376" class="float-btn">
<i class="fa-brands fa-whatsapp"></i>
</a>

<footer>

<div>
<i class="fa-solid fa-house"></i>
Home
</div>

<div>
<i class="fa-solid fa-wallet"></i>
Invest
</div>

<div>
<i class="fa-solid fa-money-bill-wave"></i>
Withdraw
</div>

<div>
<i class="fa-solid fa-user"></i>
Account
</div>

</footer>

<script>

const packagesContainer = document.getElementById("packages");

let totalEarnings = 0;

for(let amount = 750; amount <= 30000; amount += 500){

const daily = (amount * 0.15).toFixed(0);

const card = document.createElement("div");

card.className = "card";

card.innerHTML = `
<h3>KSh ${amount.toLocaleString()}</h3>

<div class="profit">
+KSh ${daily}/day
</div>

<p>15% Daily Return</p>

<button class="buy-btn"
onclick="selectPackage(${amount}, ${daily})">
Invest Now
</button>
`;

packagesContainer.appendChild(card);

}

function selectPackage(amount, daily){

document.getElementById("amount").value = amount;

totalEarnings += Number(daily);

document.getElementById("earnings").innerText =
"KSh " + totalEarnings.toLocaleString();

window.scrollTo({
top:document.body.scrollHeight,
behavior:"smooth"
});

}

async function payNow(){

const phone =
document.getElementById("phone").value;

const amount =
document.getElementById("amount").value;

if(!phone || !amount){<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>InvestPro Kenya</title>

<link rel="stylesheet"
href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"/>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{
background:#f4f5f7;
padding-bottom:120px;
}

header{
background:white;
padding:18px;
display:flex;
justify-content:space-between;
align-items:center;
box-shadow:0 2px 10px rgba(0,0,0,0.08);
position:sticky;
top:0;
z-index:100;
}

.logo{
display:flex;
align-items:center;
gap:10px;
}

.logo i{
font-size:28px;
color:#16a34a;
}

.logo h1{
font-size:28px;
}

.logo span{
color:#16a34a;
}

.balance-card{
background:white;
margin:20px;
padding:30px;
border-radius:25px;
text-align:center;
box-shadow:0 5px 20px rgba(0,0,0,0.08);
}

.balance-card h2{
font-size:50px;
color:#16a34a;
margin:10px 0;
}

.spin-btn{
width:100%;
padding:18px;
border:none;
border-radius:15px;
background:linear-gradient(to right,#059669,#22c55e);
color:white;
font-size:22px;
font-weight:bold;
margin-top:20px;
cursor:pointer;
}

.section-title{
padding:0 20px;
margin-top:30px;
display:flex;
justify-content:space-between;
align-items:center;
}

.section-title h2{
font-size:34px;
}

.vip{
background:#ff9800;
padding:10px 18px;
border-radius:12px;
color:white;
font-weight:bold;
}

.packages{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
gap:18px;
padding:20px;
}

.card{
background:white;
padding:25px;
border-radius:22px;
text-align:center;
box-shadow:0 4px 15px rgba(0,0,0,0.06);
transition:0.3s;
}

.card:hover{
transform:translateY(-5px);
}

.card h3{
font-size:32px;
margin-bottom:12px;
}

.profit{
font-size:22px;
font-weight:bold;
color:#16a34a;
margin-bottom:8px;
}

.buy-btn{
margin-top:15px;
padding:14px 20px;
border:none;
border-radius:12px;
background:#16a34a;
color:white;
font-size:18px;
cursor:pointer;
width:100%;
}

.deposit-box{
background:white;
margin:20px;
padding:25px;
border-radius:20px;
box-shadow:0 4px 15px rgba(0,0,0,0.06);
}

.deposit-box h2{
margin-bottom:15px;
}

.deposit-box input{
width:100%;
padding:15px;
margin-top:10px;
border-radius:12px;
border:1px solid #ccc;
font-size:18px;
}

.deposit-btn{
width:100%;
padding:16px;
margin-top:15px;
background:#16a34a;
color:white;
border:none;
border-radius:12px;
font-size:20px;
font-weight:bold;
cursor:pointer;
}

.float-btn{
position:fixed;
right:20px;
bottom:90px;
width:70px;
height:70px;
border-radius:50%;
display:flex;
justify-content:center;
align-items:center;
font-size:30px;
color:white;
background:#22c55e;
box-shadow:0 4px 20px rgba(0,0,0,0.2);
text-decoration:none;
}

footer{
position:fixed;
bottom:0;
width:100%;
background:white;
display:flex;
justify-content:space-around;
padding:15px 0;
box-shadow:0 -2px 10px rgba(0,0,0,0.08);
}

footer div{
text-align:center;
font-size:14px;
}

footer i{
display:block;
font-size:22px;
margin-bottom:4px;
color:#16a34a;
}

@media(max-width:768px){

.section-title h2{
font-size:26px;
}

.card h3{
font-size:26px;
}

}

</style>
</head>

<body>

<header>
<div class="logo">
<i class="fa-solid fa-chart-line"></i>
<h1>Invest<span>Pro</span></h1>
</div>

<i class="fa-solid fa-bars"></i>
</header>

<section class="balance-card">
<h4>Total Earnings</h4>
<h2 id="earnings">KSh 0</h2>
<p>Grow your portfolio daily</p>

<button class="spin-btn">
✨ Daily Harvest Bonus
</button>
</section>

<div class="section-title">
<h2>Investment Packages</h2>
<div class="vip">VIP</div>
</div>

<section class="packages" id="packages"></section>

<section class="deposit-box">

<h2>M-Pesa Deposit</h2>

<p><strong>Paybill/Till:</strong> 4498280</p>

<input type="text" id="phone" placeholder="07XXXXXXXX">

<input type="number" id="amount" placeholder="Amount">

<button class="deposit-btn" onclick="payNow()">
Deposit via M-Pesa
</button>

</section>

<a href="https://wa.me/254753608376" class="float-btn">
<i class="fa-brands fa-whatsapp"></i>
</a>

<footer>

<div>
<i class="fa-solid fa-house"></i>
Home
</div>

<div>
<i class="fa-solid fa-wallet"></i>
Invest
</div>

<div>
<i class="fa-solid fa-money-bill-wave"></i>
Withdraw
</div>

<div>
<i class="fa-solid fa-user"></i>
Account
</div>

</footer>

<script>

const packagesContainer = document.getElementById("packages");

let totalEarnings = 0;

for(let amount = 750; amount <= 30000; amount += 500){

const daily = (amount * 0.15).toFixed(0);

const card = document.createElement("div");

card.className = "card";

card.innerHTML = `
<h3>KSh ${amount.toLocaleString()}</h3>

<div class="profit">
+KSh ${daily}/day
</div>

<p>15% Daily Return</p>

<button class="buy-btn"
onclick="selectPackage(${amount}, ${daily})">
Invest Now
</button>
`;

packagesContainer.appendChild(card);

}

function selectPackage(amount, daily){

document.getElementById("amount").value = amount;

totalEarnings += Number(daily);

document.getElementById("earnings").innerText =
"KSh " + totalEarnings.toLocaleString();

window.scrollTo({
top:document.body.scrollHeight,
behavior:"smooth"
});

}

async function payNow(){

const phone =
document.getElementById("phone").value;

const amount =
document.getElementById("amount").value;

if(!phone || !amount){

alert("Enter phone and amount");

return;

}

try{

/*
CONNECT YOUR NODE/EXPRESS BACKEND HERE
*/

const response = await fetch("/stkpush",{

method:"POST",

headers:{
"Content-Type":"application/json"
},

body:JSON.stringify({
phone,
amount
})

});

const data = await response.json();

alert(data.message || "STK Push Sent");

}catch(error){

alert("Backend API not connected");

}

}

</script>

</body>
</html>

alert("Enter phone and amount");

return;

}

try{

/*
CONNECT YOUR NODE/EXPRESS BACKEND HERE
*/

const response = await fetch("/stkpush",{

method:"POST",

headers:{
"Content-Type":"application/json"
},

body:JSON.stringify({
phone,
amount
})

});

const data = await response.json();

alert(data.message || "STK Push Sent");

}catch(error){

alert("Backend API not connected");

}

}

</script>

</body>
</html>
