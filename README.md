# WMD-CA-4
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LIYARA Juice Bar | Official</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        :root { --primary: #f39c12; --secondary: #2ecc71; --dark: #333; --light: #f4f7f6; }
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; }
        body { background-color: var(--light); color: var(--dark); scroll-behavior: smooth; }

        /* Navigation */
        nav { display: flex; justify-content: space-between; align-items: center; padding: 20px 8%; background: white; box-shadow: 0 2px 10px rgba(0,0,0,0.1); position: sticky; top: 0; z-index: 1000; }
        .logo { font-size: 26px; font-weight: 700; color: #2ecc71; text-transform: uppercase; letter-spacing: 2px; }
        .logo span { color: #f39c12; }
        nav ul { display: flex; list-style: none; }
        nav ul li { margin-left: 25px; }
        nav ul li a { text-decoration: none; color: #555; font-weight: 500; cursor: pointer; transition: 0.3s; }
        nav ul li a:hover { color: var(--secondary); }

        /* Page Layout */
        .page { display: none; padding: 40px 8%; min-height: 80vh; animation: fadeIn 0.4s ease; }
        .page.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        /* Home Page Banner */
        #home { 
            text-align: center; padding: 120px 8%;
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://images.unsplash.com/photo-1490818387583-1baba5e638af?q=80&w=1500&auto=format&fit=crop');
            background-size: cover; background-position: center;
            color: white; border-radius: 0 0 30px 30px;
        }

        /* Menu Grid */
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 20px; }
        .card { background: white; border-radius: 12px; overflow: hidden; box-shadow: 0 4px 10px rgba(0,0,0,0.05); text-align: center; padding-bottom: 15px; }
        .card img { width: 100%; height: 180px; object-fit: cover; }
        .btn-add { background: var(--secondary); color: white; border: none; padding: 8px 20px; border-radius: 5px; cursor: pointer; font-weight: 600; margin-top: 10px; }

        /* Forms & Containers */
        .container { display: grid; grid-template-columns: 1fr 1fr; gap: 30px; }
        .box { background: white; padding: 25px; border-radius: 12px; box-shadow: 0 4px 15px rgba(0,0,0,0.05); }
        input, textarea { width: 100%; padding: 12px; margin: 10px 0; border: 1px solid #ddd; border-radius: 5px; }
        .btn-main { background: var(--primary); color: white; border: none; padding: 15px; border-radius: 5px; cursor: pointer; width: 100%; font-weight: 700; margin-top: 10px; text-transform: uppercase; }
        
        /* Online Payment Page Style */
        #payment-box { max-width: 500px; margin: auto; }
        .card-icons { text-align: center; margin-bottom: 20px; }
        .card-icons img { width: 45px; margin: 0 8px; }
    </style>
</head>
<body>

    <nav>
        <div class="logo">🍃 LI<span>YARA</span></div>
        <ul>
            <li><a onclick="showPage('home')">Home</a></li>
            <li><a onclick="showPage('menu')">Menu</a></li>
            <li><a onclick="showPage('order')">Order Bag (<span id="count">0</span>)</a></li>
            <li><a onclick="showPage('payment')">Payment</a></li>
            <li><a onclick="showPage('feedback')">Feedback</a></li>
        </ul>
    </nav>

    <section id="home" class="page active">
        <h1 style="font-size: 50px;">Fresh Food & Pure Juices</h1>
        <p style="font-size: 20px; margin: 15px 0;">Healthy choices for a better life. Experience the taste of nature.</p>
        <button class="btn-main" style="width: 200px; border-radius: 30px;" onclick="showPage('menu')">Shop Now</button>
    </section>

    <section id="menu" class="page">
        <h2 style="text-align: center; margin-bottom: 30px;">Our Fresh Menu</h2>
        <div class="grid">
            <div class="card"><img src="https://images.unsplash.com/photo-1613478223719-2ab802602423?w=400" alt="Orange"><h3>Fresh Orange</h3><p>Rs. 200</p><button class="btn-add" onclick="addToBag('Fresh Orange', 200)">Add</button></div>
            <div class="card"><img src="https://images.unsplash.com/photo-1595981267035-7b04ca84a82d?w=400" alt="Watermelon"><h3>Watermelon Juice</h3><p>Rs. 180</p><button class="btn-add" onclick="addToBag('Watermelon Juice', 180)">Add</button></div>
            <div class="card"><img src="https://images.unsplash.com/photo-1528498033373-3c6c08e93d79?w=400" alt="Lemon"><h3>Fresh Lemon</h3><p>Rs. 150</p><button class="btn-add" onclick="addToBag('Fresh Lemon', 150)">Add</button></div>
            <div class="card"><img src="https://images.unsplash.com/photo-1572490122747-3968b75cc699?w=400" alt="Chocolate"><h3>Chocolate Shake</h3><p>Rs. 300</p><button class="btn-add" onclick="addToBag('Chocolate Shake', 300)">Add</button></div>
            <div class="card"><img src="https://images.unsplash.com/photo-1579954115545-a95591f28bfc?w=400" alt="Vanilla"><h3>Vanilla Shake</h3><p>Rs. 280</p><button class="btn-add" onclick="addToBag('Vanilla Shake', 280)">Add</button></div>
            <div class="card"><img src="https://images.unsplash.com/photo-1553177174-1e958152528c?w=400" alt="Strawberry"><h3>Strawberry Shake</h3><p>Rs. 320</p><button class="btn-add" onclick="addToBag('Strawberry Shake', 320)">Add</button></div>
        </div>
    </section>

    <section id="order" class="page">
        <div class="container">
            <div class="box">
                <h3>Delivery Details</h3>
                <input type="text" id="custName" placeholder="Full Name">
                <input type="text" id="custAddress" placeholder="Address">
                <button class="btn-main" onclick="finishOrder()">Next: Payment</button>
            </div>
            <div class="box">
                <h3>Order Summary</h3>
                <div id="summary-list">Your bag is empty.</div>
                <hr style="margin: 15px 0;">
                <h3 id="total-display">Total: Rs. 0.00</h3>
            </div>
        </div>
    </section>

    <section id="payment" class="page">
        <div class="box" id="payment-box">
            <h3 style="text-align: center; margin-bottom: 20px;">Online Card Payment</h3>
            <div class="card-icons">
                <img src="https://img.icons8.com/color/48/000000/visa.png"/>
                <img src="https://img.icons8.com/color/48/000000/mastercard.png"/>
                <img src="https://img.icons8.com/color/48/000000/amex.png"/>
            </div>
            <label>Cardholder Name</label>
            <input type="text" placeholder="Name on Card">
            <label>Card Number</label>
            <input type="text" id="cardNum" placeholder="1234 5678 9012 3456" maxlength="16">
            <div style="display: flex; gap: 10px;">
                <div style="flex: 2;"><label>Expiry</label><input type="text" placeholder="MM/YY" maxlength="5"></div>
                <div style="flex: 1;"><label>CVV</label><input type="password" placeholder="***" maxlength="3"></div>
            </div>
            <button class="btn-main" style="background: #2ecc71;" onclick="processPayment()">Confirm Payment</button>
            <p style="text-align: center; font-size: 12px; color: #888; margin-top: 15px;">🔒 Your payment information is encrypted and secure.</p>
        </div>
    </section>

    <section id="feedback" class="page">
        <div class="box" style="max-width: 600px; margin: auto; text-align: center;">
            <h2>Feedback</h2>
            <textarea id="fbText" rows="5" placeholder="Tell us what you think..."></textarea>
            <button class="btn-main" onclick="alert('Thank you for your feedback!'); showPage('home')">Submit</button>
        </div>
    </section>

    <script>
        let bag = [];

        function showPage(id) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById(id).classList.add('active');
            window.scrollTo(0,0);
        }

        function addToBag(name, price) {
            bag.push({name, price});
            document.getElementById('count').innerText = bag.length;
            updateSummary();
            alert(name + " added!");
        }

        function updateSummary() {
            const list = document.getElementById('summary-list');
            const totalDisplay = document.getElementById('total-display');
            if(bag.length === 0) {
                list.innerHTML = "Your bag is empty.";
                totalDisplay.innerText = "Total: Rs. 0.00";
                return;
            }
            let total = 0;
            let html = "";
            bag.forEach(item => {
                html += `<p style="display:flex; justify-content:space-between;"><span>${item.name}</span> <span>Rs. ${item.price}</span></p>`;
                total += item.price;
            });
            list.innerHTML = html;
            totalDisplay.innerText = "Total: Rs. " + total + ".00";
        }

        function finishOrder() {
            let name = document.getElementById('custName').value;
            if(bag.length > 0 && name != "") {
                showPage('payment');
            } else {
                alert("Please add items to bag and fill delivery details.");
            }
        }

        function processPayment() {
            let card = document.getElementById('cardNum').value;
            if(card.length == 16) {
                alert("Payment Success! Thank you for ordering from LIYARA.");
                bag = [];
                document.getElementById('count').innerText = "0";
                updateSummary();
                showPage('home');
            } else {
                alert("Please enter a valid 16-digit card number.");
            }
        }
    </script>
</body>
</html>
