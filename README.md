## Hello, I'm currently working on a project to launch a shopping website. 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Store Name</title>
    <link rel="stylesheet" href="styles.css"> <!-- Link to your CSS file -->
</head>
<body>
    <header>
        <h1>Welcome to [Your Store Name]</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Products</a></li>
                <li><a href="#">About Us</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <section id="products">
        <h2>Our Products</h2>
        <!-- Product items will go here -->
    </section>
    
    <footer>
        <p>&copy; 2024 [Your Store Name]. All rights reserved.</p>
    </footer>
</body>
	</html>
	<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Store Name</title>
    <link rel="stylesheet" href="styles.css"> <!-- Link to your CSS file -->
</head>
<body>
    <header>
        <h1>Welcome to [Your Store Name]</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Products</a></li>
                <li><a href="#">About Us</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    <section id="products">
        <h2>Our Products</h2>
        <div class="product">
            <img src="images/product1.jpg" alt="Product 1">
            <h3>Anime Figurine 1</h3>
            <p>$29.99</p>
            <button class="add-to-cart" data-name="Anime Figurine 1" data-price="29.99">Add to Cart</button>
        </div>
        <div class="product">
            <img src="images/product2.jpg" alt="Product 2">
            <h3>Anime Figurine 2</h3>
            <p>$39.99</p>
            <button class="add-to-cart" data-name="Anime Figurine 2" data-price="39.99">Add to Cart</button>
        </div>
    </section>
    <section id="cart">
        <h2>Your Cart</h2>
        <div id="cart-items"></div>
        <p>Total: $<span id="cart-total">0.00</span></p>
        <button id="purchase">Purchase</button>
    </section>
    
    <footer>
        <p>&copy; 2024 [Your Store Name]. All rights reserved.</p>
    </footer>

    <script src="script.js"></script> <!-- Link to your JavaScript file -->
</body>
</html><section id="cart">
    <h2>Your Cart</h2>
    <div id="cart-items"></div>
    <p>Total (Before Shipping): $<span id="cart-total">0.00</span></p>
    
    <!-- Shipping Options -->
    <div id="shipping-options">
        <h3>Select Shipping:</h3>
        <select id="shipping">
            <option value="0">Standard Shipping (Free)</option>
            <option value="5">Express Shipping ($5.00)</option>
            <option value="10">Next-Day Shipping ($10.00)</option>
        </select>
    </div>

    <p>Total (Including Shipping): $<span id="total-with-shipping">0.00</span></p>
    <button id="purchase">Purchase</button>
</section>body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: #fff;
    padding: 10px 0;
    text-align: center;
}

nav ul {
    list-style: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 0 10px;
}

nav ul li a {
    color: #fff;
    text-decoration: none;
}

#products {
    padding: 20px;
    text-align: center;
}

footer {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 10px 0;
    position: fixed;
    bottom: 0;
    width: 100%;body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: #fff;
    padding: 10px 0;
    text-align: center;
}

nav ul {
    list-style: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 0 10px;
}

nav ul li a {
    color: #fff;
    text-decoration: none;
}

#products, #cart {
    padding: 20px;
    text-align: center;
}

.product {
    display: inline-block;
    margin: 10px;
    padding: 10px;
    border: 1px solid #ccc;
    background-color: #fff;
}

.product img {
    width: 150px;
    height: auto;
}

.add-to-cart {
    margin-top: 10px;
    padding: 10px;
    background-color: #28a745;
    color: #fff;
    border: none;
    cursor: pointer;
}

.add-to-cart:hover {
    background-color: #218838;
}

#cart {
    margin-top: 30px;
    border-top: 1px solid #ccc;
    padding-top: 20px;
}

#cart-items {
    margin-bottom: 20px;
}

#purchase {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    cursor: pointer;
}

#purchase:hover {
    background-color: #0056b3;
}

footer {
    background-color: #333;
    color: #fff;
    text-align: center;
    padding: 10px 0;
    position: fixed;
    bottom: 0;
    width: 100%;
}#shipping-options {
    margin-top: 20px;
}

#shipping-options h3 {
    margin-bottom: 10px;
}

#shipping {
    padding: 5px;
    font-size: 1em;
}document.addEventListener("DOMContentLoaded", function() {
    const cartItems = document.getElementById("cart-items");
    const cartTotal = document.getElementById("cart-total");
    const purchaseButton = document.getElementById("purchase");
    let total = 0;
    
    document.querySelectorAll(".add-to-cart").forEach(button => {
        button.addEventListener("click", function() {
            const name = this.dataset.name;
            const price = parseFloat(this.dataset.price);

            // Add item to cart
            const cartItem = document.createElement("div");
            cartItem.textContent = `${name} - $${price.toFixed(2)}`;
            cartItems.appendChild(cartItem);

            // Update total
            total += price;
            cartTotal.textContent = total.toFixed(2);
        });
    });

    purchaseButton.addEventListener("click", function() {
        if (total > 0) {
            alert(`Thank you for your purchase! Your total is $${total.toFixed(2)}.`);
            // Clear cart
            cartItems.innerHTML = "";
            cartTotal.textContent = "0.00";
            total = 0;
        } else {
            alert("Your cart is empty!");
        }
    });
});document.addEventListener("DOMContentLoaded", function() {
    const cartItems = document.getElementById("cart-items");
    const cartTotal = document.getElementById("cart-total");
    const totalWithShipping = document.getElementById("total-with-shipping");
    const shippingSelect = document.getElementById("shipping");
    const purchaseButton = document.getElementById("purchase");
    let total = 0;
    
    document.querySelectorAll(".add-to-cart").forEach(button => {
        button.addEventListener("click", function() {
            const name = this.dataset.name;
            const price = parseFloat(this.dataset.price);

            // Add item to cart
            const cartItem = document.createElement("div");
            cartItem.textContent = `${name} - $${price.toFixed(2)}`;
            cartItems.appendChild(cartItem);

            // Update total
            total += price;
            cartTotal.textContent = total.toFixed(2);
            updateTotalWithShipping(); // Update the total with shipping
        });
    });

    shippingSelect.addEventListener("change", updateTotalWithShipping);

    function updateTotalWithShipping() {
        const shippingCost = parseFloat(shippingSelect.value);
        totalWithShipping.textContent = (total + shippingCost).toFixed(2);
    }

    purchaseButton.addEventListener("click", function() {
        const shippingCost = parseFloat(shippingSelect.value);
        const finalTotal = total + shippingCost;
        
        if (total > 0) {
            alert(`Thank you for your purchase! Your total is $${finalTotal.toFixed(2)}.`);
            // Clear cart
            cartItems.innerHTML = "";
            cartTotal.textContent = "0.00";
            totalWithShipping.textContent = "0.00";
            total = 0;
        } else {
            alert("Your cart is empty!");
        }
    });
});