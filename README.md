# SAPE
Scented Aromatic Paper Essence
<!DOCTYPE html><html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>SAPE - Scented Aromatic Paper Essential</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; }
    header, footer { background-color: #E0E0E0; padding: 1rem; text-align: center; }
    nav a { margin: 0 1rem; text-decoration: none; color: #333; }
    .hero { background-color: #F9F9F9; padding: 2rem; text-align: center; }
    .products, .blog, .newsletter, .checkout, .auth { padding: 2rem; }
    .product { border: 1px solid #ccc; padding: 1rem; margin: 1rem 0; }
    .quiz-result { margin-top: 1rem; font-weight: bold; }
  </style>
</head>
<body>
  <header>
    <h1>SAPE</h1>
    <p>Scented Aromatic Paper Essential</p>
    <nav>
      <a href="#shop">Shop</a>
      <a href="#quiz">Quiz</a>
      <a href="#blog">Blog</a>
      <a href="#refill">Refill</a>
      <a href="#checkout">Checkout</a>
      <a href="#login">Login</a>
    </nav>
  </header>  <section class="hero">
    <h2>Praktis, Wangi, dan Ramah Lingkungan 🌿</h2>
    <p>Sabun kertas alami dengan aroma lavender menenangkan.</p>
  </section>  <section id="shop" class="products">
    <h2>Produk Kami</h2>
    <div class="product">
      <h3>SAPE - Lavender</h3>
      <p>Sabun kertas dengan aroma lavender untuk relaksasi.</p>
      <button onclick="addToCart('SAPE - Lavender')">Add to Cart</button>
    </div>
    <div class="product">
      <h3>SAPE - Citrus</h3>
      <p>Sabun kertas aroma citrus menyegarkan untuk pagi hari.</p>
      <button onclick="addToCart('SAPE - Citrus')">Add to Cart</button>
    </div>
  </section>  <section id="quiz">
    <h2>Quiz: Pilih Aroma untukmu</h2>
    <label>Pilih mood kamu hari ini:
      <select id="mood">
        <option value="relax">Butuh relaksasi</option>
        <option value="fresh">Ingin segar</option>
        <option value="focus">Ingin fokus</option>
      </select>
    </label>
    <button onclick="recommendScent()">Lihat Rekomendasi</button>
    <div id="quizResult" class="quiz-result"></div>
  </section>  <section id="blog" class="blog">
    <h2>Artikel Terbaru</h2>
    <p><strong>Manfaat Aromaterapi dalam Kehidupan Sehari-hari</strong><br/>
    Pelajari bagaimana essential oil seperti lavender dapat membantu menenangkan pikiran.</p>
  </section>  <section id="refill" class="newsletter">
    <h2>Langganan Refill Reminder</h2>
    <input type="email" placeholder="Email kamu...">
    <button>Langganan</button>
  </section>  <section id="checkout" class="checkout">
    <h2>Keranjang & Checkout</h2>
    <div id="cartList">Keranjang kosong</div>
    <button onclick="checkout()">Checkout Sekarang</button>
  </section>  <section id="login" class="auth">
    <h2>Login Pengguna</h2>
    <input type="text" id="username" placeholder="Username"><br><br>
    <input type="password" id="password" placeholder="Password"><br><br>
    <button onclick="login()">Login</button>
    <p id="loginMessage"></p>
  </section>  <footer>
    <p>&copy; 2025 SAPE. Semua Hak Dilindungi.</p>
  </footer>  <script>
    const cart = [];
    function addToCart(productName) {
      cart.push(productName);
      alert(productName + " telah ditambahkan ke keranjang!");
      updateCartList();
    }

    function updateCartList() {
      const cartList = document.getElementById("cartList");
      if (cart.length === 0) {
        cartList.innerText = "Keranjang kosong";
      } else {
        cartList.innerHTML = "<ul>" + cart.map(item => `<li>${item}</li>`).join('') + "</ul>";
      }
    }

    function checkout() {
      if (cart.length === 0) {
        alert("Keranjang masih kosong!");
      } else {
        alert("Terima kasih telah berbelanja! Pesanan Anda diproses.");
        cart.length = 0;
        updateCartList();
      }
    }

    function recommendScent() {
      const mood = document.getElementById("mood").value;
      let result = "";
      if (mood === "relax") result = "Coba SAPE - Lavender untuk relaksasi.";
      else if (mood === "fresh") result = "Coba SAPE - Citrus untuk kesegaran ekstra.";
      else if (mood === "focus") result = "Coba SAPE - Mint untuk bantu fokus.";
      document.getElementById("quizResult").innerText = result;
    }

    function login() {
      const user = document.getElementById("username").value;
      const pass = document.getElementById("password").value;
      if (user === "admin" && pass === "sape123") {
        document.getElementById("loginMessage").innerText = "Login berhasil!";
      } else {
        document.getElementById("loginMessage").innerText = "Username atau password salah.";
      }
    }
  </script></body>
</html>
