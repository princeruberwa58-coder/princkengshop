<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>PRINCKENG SHOP</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: #f5f6f8;
            color: #111827;
        }

        header {
            background: #111827;
            color: white;
            padding: 18px 6%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 23px;
            font-weight: 800;
        }

        nav {
            display: flex;
            gap: 20px;
            align-items: center;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-size: 15px;
        }

        .cart-button {
            background: white;
            color: #111827;
            border: none;
            padding: 10px 15px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
        }

        .hero {
            padding: 70px 6%;
            background: linear-gradient(135deg, #111827, #374151);
            color: white;
            text-align: center;
        }

        .hero h1 {
            font-size: 48px;
            margin-bottom: 15px;
        }

        .hero p {
            font-size: 18px;
            color: #d1d5db;
            margin-bottom: 25px;
        }

        .shop-button {
            display: inline-block;
            background: white;
            color: #111827;
            padding: 13px 22px;
            border-radius: 10px;
            text-decoration: none;
            font-weight: bold;
        }

        .container {
            width: 88%;
            max-width: 1200px;
            margin: 40px auto;
        }

        .section-title {
            font-size: 28px;
            margin-bottom: 20px;
        }

        .controls {
            display: flex;
            gap: 12px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .controls input,
        .controls select {
            padding: 13px;
            border: 1px solid #d1d5db;
            border-radius: 9px;
            background: white;
            font-size: 15px;
        }

        .search {
            flex: 1;
            min-width: 220px;
        }

        .products {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 22px;
        }

        .product {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,.06);
            transition: .2s;
        }

        .product:hover {
            transform: translateY(-4px);
        }

        .product-image {
            height: 210px;
            background: #e5e7eb;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .product-info {
            padding: 18px;
        }

        .product-info h3 {
            margin-bottom: 8px;
        }

        .price {
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 8px;
        }

        .stock {
            color: #6b7280;
            font-size: 14px;
            margin-bottom: 14px;
        }

        .add-btn {
            width: 100%;
            padding: 11px;
            border: none;
            background: #111827;
            color: white;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
        }

        .add-btn:disabled {
            background: #9ca3af;
            cursor: not-allowed;
        }

        .admin {
            background: white;
            padding: 25px;
            border-radius: 15px;
            margin-top: 50px;
            box-shadow: 0 5px 20px rgba(0,0,0,.06);
        }

        .admin h2 {
            margin-bottom: 20px;
        }

        .admin-form {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 12px;
        }

        .admin-form input {
            padding: 12px;
            border: 1px solid #d1d5db;
            border-radius: 8px;
        }

        .admin-form button {
            background: #111827;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
        }

        .inventory {
            margin-top: 25px;
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 13px;
            border-bottom: 1px solid #e5e7eb;
            text-align: left;
        }

        th {
            background: #f3f4f6;
        }

        .delete-btn {
            background: #dc2626;
            color: white;
            border: none;
            padding: 7px 10px;
            border-radius: 6px;
            cursor: pointer;
        }

        .cart {
            position: fixed;
            right: -400px;
            top: 0;
            width: 360px;
            max-width: 90%;
            height: 100vh;
            background: white;
            box-shadow: -5px 0 20px rgba(0,0,0,.2);
            z-index: 200;
            padding: 25px;
            transition: .3s;
            overflow-y: auto;
        }

        .cart.open {
            right: 0;
        }

        .cart-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 25px;
        }

        .close-cart {
            border: none;
            background: none;
            font-size: 25px;
            cursor: pointer;
        }

        .cart-item {
            border-bottom: 1px solid #eee;
            padding: 15px 0;
        }

        .cart-total {
            margin-top: 25px;
            font-size: 20px;
            font-weight: bold;
        }

        .checkout {
            width: 100%;
            padding: 13px;
            margin-top: 15px;
            background: #16a34a;
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
        }

        footer {
            margin-top: 60px;
            background: #111827;
            color: white;
            text-align: center;
            padding: 30px;
        }

        @media(max-width: 600px) {
            .hero h1 {
                font-size: 34px;
            }

            header {
                padding: 15px 4%;
            }

            nav a {
                display: none;
            }

            .container {
                width: 92%;
            }

            .cart {
                width: 330px;
            }
        }
    </style>
</head>

<body>

<header>
    <div class="logo">PRINCKENG SHOP</div>

    <nav>
        <a href="#products">Shop</a>
        <a href="#admin">Stock</a>

        <button class="cart-button" onclick="openCart()">
            🛒 Cart (<span id="cartCount">0</span>)
        </button>
    </nav>
</header>

<section class="hero">
    <h1>PRINCKENG SHOP</h1>
    <p>Quality products. Simple shopping. Great service.</p>

    <a href="#products" class="shop-button">
        Shop Now
    </a>
</section>

<main class="container">

    <h2 class="section-title" id="products">
        Our Products
    </h2>

    <div class="controls">
        <input
            class="search"
            type="text"
            id="search"
            placeholder="Search products..."
            oninput="displayProducts()"
        >

        <select id="category" onchange="displayProducts()">
            <option value="all">All Categories</option>
        </select>
    </div>

    <div class="products" id="productsList"></div>


    <section class="admin" id="admin">

        <h2>📦 Stock Management</h2>

        <p style="margin-bottom:20px;color:#6b7280;">
            Add products and manage your shop stock.
        </p>

        <div class="admin-form">

            <input
                type="text"
                id="productName"
                placeholder="Product name"
            >

            <input
                type="number"
                id="productPrice"
                placeholder="Price (KES)"
            >

            <input
                type="number"
                id="productStock"
                placeholder="Stock quantity"
            >

            <input
                type="text"
                id="productCategory"
                placeholder="Category"
            >

            <input
                type="text"
                id="productImage"
                placeholder="Image URL"
            >

            <button onclick="addProduct()">
                + Add Product
            </button>

        </div>

        <div class="inventory">

            <table>

                <thead>
                    <tr>
                        <th>Product</th>
                        <th>Price</th>
                        <th>Stock</th>
                        <th>Category</th>
                        <th>Action</th>
                    </tr>
                </thead>

                <tbody id="inventoryList"></tbody>

            </table>

        </div>

    </section>

</main>


<div class="cart" id="cart">

    <div class="cart-header">

        <h2>🛒 Your Cart</h2>

        <button class="close-cart" onclick="closeCart()">
            ×
        </button>

    </div>

    <div id="cartItems"></div>

    <div class="cart-total">
        Total: KES <span id="cartTotal">0</span>
    </div>

    <button class="checkout" onclick="checkout()">
        Order on WhatsApp
    </button>

</div>


<footer>

    <h3>PRINCKENG SHOP</h3>

    <p style="margin-top:10px;">
        Your trusted online shop.
    </p>

    <p style="margin-top:15px;color:#9ca3af;">
        © 2026 PRINCKENG SHOP. All rights reserved.
    </p>

</footer>


<script>

let products = JSON.parse(
    localStorage.getItem("princkengProducts")
) || [

    {
        id: 1,
        name: "Example Product",
        price: 1000,
        stock: 10,
        category: "General",
        image: "https://via.placeholder.com/500x400?text=Product"
    },

    {
        id: 2,
        name: "Sample Item",
        price: 1500,
        stock: 5,
        category: "General",
        image: "https://via.placeholder.com/500x400?text=Product"
    }

];


let cart = [];


function saveProducts() {

    localStorage.setItem(
        "princkengProducts",
        JSON.stringify(products)
    );

}


function displayProducts() {

    const list = document.getElementById("productsList");

    const search =
        document.getElementById("search").value.toLowerCase();

    const category =
        document.getElementById("category").value;

    list.innerHTML = "";


    const filtered = products.filter(product => {

        const matchesSearch =
            product.name.toLowerCase().includes(search);

        const matchesCategory =
            category === "all" ||
            product.category === category;

        return matchesSearch && matchesCategory;

    });


    filtered.forEach(product => {

        const card = document.createElement("div");

        card.className = "product";


        card.innerHTML = `

            <div class="product-image">

                <img
                    src="${product.image}"
                    alt="${product.name}"
                    onerror="this.src='https://via.placeholder.com/500x400?text=No+Image'"
                >

            </div>

            <div class="product-info">

                <h3>${product.name}</h3>

                <div class="price">
                    KES ${Number(product.price).toLocaleString()}
                </div>

                <div class="stock">
                    ${
                        product.stock > 0
                        ? product.stock + " in stock"
                        : "Out of stock"
                    }
                </div>

                <button
                    class="add-btn"
                    onclick="addToCart(${product.id})"
                    ${product.stock <= 0 ? "disabled" : ""}
                >
                    ${
                        product.stock > 0
                        ? "Add to Cart"
                        : "Out of Stock"
                    }
                </button>

            </div>

        `;

        list.appendChild(card);

    });


    updateCategories();

}


function updateCategories() {

    const categorySelect =
        document.getElementById("category");

    const current =
        categorySelect.value;

    const categories =
        [...new Set(products.map(p => p.category))];


    categorySelect.innerHTML =
        `<option value="all">All Categories</option>`;


    categories.forEach(category => {

        categorySelect.innerHTML += `
            <option value="${category}">
                ${category}
            </option>
        `;

    });


    categorySelect.value = current;

}


function addProduct() {

    const name =
        document.getElementById("productName").value.trim();

    const price =
        Number(document.getElementById("productPrice").value);

    const stock =
        Number(document.getElementById("productStock").value);

    const category =
        document.getElementById("productCategory").value.trim();

    const image =
        document.getElementById("productImage").value.trim();


    if (!name || !price || stock < 0 || !category) {

        alert("Please fill in the product details.");

        return;

    }


    const product = {

        id: Date.now(),

        name: name,

        price: price,

        stock: stock,

        category: category,

        image:
            image ||
            "https://via.placeholder.com/500x400?text=Product"

    };


    products.push(product);

    saveProducts();

    displayProducts();

    displayInventory();


    document.getElementById("productName").value = "";
    document.getElementById("productPrice").value = "";
    document.getElementById("productStock").value = "";
    document.getElementById("productCategory").value = "";
    document.getElementById("productImage").value = "";


    alert("Product added successfully! ✅");

}


function displayInventory() {

    const table =
        document.getElementById("inventoryList");

    table.innerHTML = "";


    products.forEach(product => {

        table.innerHTML += `

            <tr>

                <td>${product.name}</td>

                <td>
                    KES ${Number(product.price).toLocaleString()}
                </td>

                <td>
                    ${product.stock}
                </td>

                <td>
                    ${product.category}
                </td>

                <td>

                    <button
                        class="delete-btn"
                        onclick="deleteProduct(${product.id})"
                    >
                        Delete
                    </button>

                </td>

            </tr>

        `;

    });

}


function deleteProduct(id) {

    if (!confirm("Delete this product?")) return;


    products =
        products.filter(product => product.id !== id);


    saveProducts();

    displayProducts();

    displayInventory();

}


function addToCart(id) {

    const product =
        products.find(p => p.id === id);


    if (!product || product.stock <= 0) return;


    const existing =
        cart.find(item => item.id === id);


    if (existing) {

        if (existing.quantity < product.stock) {

            existing.quantity++;

        }

    } else {

        cart.push({

            id: product.id,

            name: product.name,

            price: product.price,

            quantity: 1

        });

    }


    updateCart();

}


function updateCart() {

    const items =
        document.getElementById("cartItems");

    items.innerHTML = "";


    let total = 0;

    let count = 0;


    cart.forEach(item => {

        total += item.price * item.quantity;

        count += item.quantity;


        items.innerHTML += `

            <div class="cart-item">

                <strong>${item.name}</strong>

                <p>
                    KES ${Number(item.price).toLocaleString()}
                    × ${item.quantity}
                </p>

                <button
                    onclick="removeFromCart(${item.id})"
                    style="margin-top:7px;padding:5px;"
                >
                    Remove
                </button>

            </div>

        `;

    });


    document.getElementById("cartTotal").textContent =
        total.toLocaleString();

    document.getElementById("cartCount").textContent =
        count;

}


function removeFromCart(id) {

    cart =
        cart.filter(item => item.id !== id);

    updateCart();

}


function openCart() {

    document
        .getElementById("cart")
        .classList.add("open");

}


function closeCart() {

    document
        .getElementById("cart")
        .classList.remove("open");

}


function checkout() {

    if (cart.length === 0) {

        alert("Your cart is empty.");

        return;

    }


    let message =
        "Hello PRINCKENG SHOP! I would like to order:%0A%0A";


    let total = 0;


    cart.forEach(item => {

        const subtotal =
            item.price * item.quantity;

        total += subtotal;


        message +=
            `${item.name} - ${item.quantity} × KES ${item.price}%0A`;

    });


    message +=
        `%0ATotal: KES ${total}`;


    /*
       CHANGE 254700000000
       TO YOUR WHATSAPP NUMBER.

       Example:
       Kenya number 0712345678
       becomes:
       254712345678
    */


    const phone =
        "254700000000";


    window.open(
        `https://wa.me/${phone}?text=${message}`,
        "_blank"
    );

}


displayProducts();

displayInventory();

</script>

</body>
</html>
