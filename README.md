  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Empresa JR</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .container {
      display: flex;
      flex-direction: column;
      flex: 1;
      background-color: white;
      padding: 20px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      border-radius: 8px;
      margin: 0;
      width: 100%;
      max-width: 1200px;
    }
    header {
      background-color: #11a0c0;
      color: white;
      padding: 10px;
      width: 100%;
      box-sizing: border-box;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    .logo img {
      width: 50px;
      height: auto;
    }
    nav {
      margin: 0;
    }
    nav ul {
      list-style: none;
      padding: 0;
      margin: 0;
      display: flex;
      justify-content: center;
      flex-grow: 1;
    }
    nav ul li {
      margin: 0 10px;
    }
    nav ul li a {
      color: white;
      text-decoration: none;
    }
    .contact-links {
      margin-top: 10px;
    }
    .contact-links a {
      color: #ffffff;
      text-decoration: none;
      margin: 0 10px;
    }
    main {
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }
    section {
      margin: 20px 0;
    }
    .product-search {
      margin-bottom: 20px;
      padding: 10px;
      width: 100%;
      max-width: 600px;
      box-sizing: border-box;
    }
    .products {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
    }
    .product {
      background-color: #ffffff;
      border: 1px solid #ddd;
      border-radius: 8px;
      padding: 10px;
      text-align: center;
      width: 150px;
    }
    .product img {
      width: 100%;
      border-radius: 8px;
    }
    .product h3 {
      margin: 10px 0 5px;
    }
    .product p {
      margin: 0;
      font-weight: bold;
    }
    footer {
      background-color: #333;
      color: rgb(244, 244, 244);
      padding: 10px;
      width: 100%;
      box-sizing: border-box;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="logo">
        <img src="IMG_20240104_183552_087.png" alt="JR">
      </div>
      <nav>
        <ul>
          <li><a href="#home">Inicio</a></li>
          <li><a href="#about">Acerca de</a></li>
          <li><a href="#services">Servicios</a></li>
          <li><a href="#contact">Contacto</a></li>
        </ul>
      </nav>
      <div class="contact-links">
        <a href="https://www.facebook.com" target="_blank">Facebook</a>
        <a href="https://wa.me/541157663325?text=Hola%20buenos%20dias%20empresa%20JR" target="_blank">WhatsApp</a>
      </div>
    </header>

    <main>
      <section id="home">
        <h1>Bienvenido a JR</h1>
        <p>Somos una empresa dedicada a brindar soluciones innovadoras.</p>
      </section>

      <section id="products">
        <h2>Nuestros Productos</h2>
        <input class="product-search" type="text" id="search" placeholder="Buscar productos...">
        <div class="products" id="product-list">
          <!-- Product items will be added here dynamically -->
        </div>
      </section>
    </main>

    <footer>
      <p>&copy; 2024 JR. Todos los derechos reservados.</p>
    </footer>
  </div>

  <script>
    const products = [
      { id: 1, name: "Arroz", img: "https://via.placeholder.com/150", price: "$1.00" },
      { id: 2, name: "Frijoles", img: "https://via.placeholder.com/150", price: "$1.50" },
      { id: 3, name: "Aceite de cocina", img: "https://via.placeholder.com/150", price: "$2.00" },
      { id: 4, name: "Azúcar", img: "https://via.placeholder.com/150", price: "$1.20" },
      { id: 5, name: "Leche", img: "https://via.placeholder.com/150", price: "$0.80" },
      { id: 6, name: "Pan", img: "https://via.placeholder.com/150", price: "$1.10" },
      { id: 7, name: "Café", img: "https://via.placeholder.com/150", price: "$2.50" },
      { id: 8, name: "Huevos", img: "https://via.placeholder.com/150", price: "$1.30" },
      { id: 9, name: "Pasta", img: "https://via.placeholder.com/150", price: "$0.90" },
      { id: 10, name: "Sal", img: "https://via.placeholder.com/150", price: "$0.50" }
    ];

    const productList = document.getElementById('product-list');
    const searchInput = document.getElementById('search');

    function displayProducts(productsToDisplay) {
      productList.innerHTML = '';
      productsToDisplay.forEach(product => {
        const productElement = document.createElement('div');
        productElement.classList.add('product');
        productElement.innerHTML = `
          <img src="${product.img}" alt="${product.name}">
          <h3>${product.name}</h3>
          <p>${product.price}</p>
        `;
        productList.appendChild(productElement);
      });
    }

    searchInput.addEventListener('input', (event) => {
      const searchTerm = event.target.value.toLowerCase();
      const filteredProducts = products.filter(product => product.name.toLowerCase().includes(searchTerm));
      displayProducts(filteredProducts);
    });

    displayProducts(products); // Initial display
  </script>
</body>
</html>
