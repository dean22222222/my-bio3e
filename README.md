<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>About Dean Sherrill 🍕</title>
  <style>
    body {
      font-family: "Poppins", sans-serif;
      margin: 0;
      background: linear-gradient(135deg, #ffb347, #ffcc33);
      color: #333;
      text-align: center;
      cursor: url('https://cur.cursors-4u.net/food/foo-3/foo283.cur'), auto;
      overflow-x: hidden;
    }

    header {
      background-color: rgba(255, 255, 255, 0.25);
      padding: 40px 20px;
      backdrop-filter: blur(10px);
    }

    h1 { font-size: 2.8em; margin: 0; }

    section { padding: 40px 20px; }

    .about, .contact, .friends {
      background: rgba(255, 255, 255, 0.85);
      border-radius: 12px;
      display: inline-block;
      padding: 30px;
      margin-top: 20px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    }

    input, textarea {
      width: 90%;
      padding: 10px;
      margin: 10px 0;
      border: 2px solid #ffb347;
      border-radius: 6px;
      font-size: 1em;
    }

    button {
      background: #ff6b6b;
      color: white;
      padding: 12px 25px;
      border: none;
      border-radius: 30px;
      font-size: 1.1em;
      cursor: pointer;
      transition: transform 0.3s ease, background 0.3s ease;
      margin-top: 10px;
    }

    button:hover {
      background: #ff4040;
      transform: scale(1.1);
    }

    footer {
      margin-top: 60px;
      padding: 20px;
      background-color: rgba(255, 255, 255, 0.3);
    }

    .pizza {
      position: fixed;
      top: -50px;
      font-size: 2em;
      animation: floatDown 6s linear infinite;
      opacity: 0.9;
    }

    @keyframes floatDown {
      0% { transform: translateY(-60px) rotate(0deg); opacity: 1; }
      100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
    }

    /* Login popup */
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.5);
      backdrop-filter: blur(4px);
    }

    .modal-content {
      background: white;
      padding: 20px;
      width: 80%;
      max-width: 350px;
      margin: 100px auto;
      border-radius: 12px;
      text-align: center;
    }
  </style>
</head>
<body>

  <header>
    <h1>Hey, I'm Dean Sherrill 👋</h1>
    <p>Welcome to my slice of the internet 🍕</p>

    <!-- LOGIN BUTTON -->
    <button onclick="openLogin()">Login 🔐</button>
    <button onclick="logout()" id="logoutBtn" style="display:none;">Logout 🚪</button>
  </header>

  <section class="about">
    <h2>About Me 🎧</h2>
    <p> I’ve been into coding since I was 13 — ... (your text stays the same) </p>
  </section>

  <section class="contact">
    <h2>Get in Touch 📧</h2>
    <p>Send me a message directly — I’ll get it in my email!</p>
    <form action="https://formspree.io/f/xzzypwkv" method="POST">
      <input type="text" name="name" placeholder="Your Name" required><br>
      <input type="email" name="email" placeholder="Your Email" required><br>
      <textarea name="message" rows="5" placeholder="Your Message..." required></textarea><br>
      <button type="submit">Send Message 🚀</button>
    </form>
  </section>

  <!-- FRIENDS & FAMILY SECTION (HIDDEN UNTIL LOGGED IN) -->
  <section class="friends" id="friendsSection" style="display:none;">
    <h2>Friends & Family ❤️</h2>
    <p>Welcome! Since you're logged in, you can see this special section just for people I trust 😄</p>
  </section>

  <footer>
    <p>© 2025 Dean Sherrill | Made with ❤️ & 🍕</p>
  </footer>

  <!-- LOGIN POPUP -->
  <div class="modal" id="loginModal">
    <div class="modal-content">
      <h3>Login 🔐</h3>
      <input id="user" type="text" placeholder="Username">
      <input id="pass" type="password" placeholder="Password">
      <button onclick="login()">Login</button>
      <button onclick="closeLogin()">Cancel</button>
    </div>
  </div>

  <script>
    const correctUser = "family";   // <-- change this
    const correctPass = "pizza123"; // <-- change this

    function openLogin() {
      document.getElementById("loginModal").style.display = "block";
    }

    function closeLogin() {
      document.getElementById("loginModal").style.display = "none";
    }

    function login() {
      const u = document.getElementById("user").value;
      const p = document.getElementById("pass").value;

      if (u === correctUser && p === correctPass) {
        localStorage.setItem("loggedIn", "yes");
        closeLogin();
        showFriendsArea();
      } else {
        alert("Wrong username or password!");
      }
    }

    function logout() {
      localStorage.removeItem("loggedIn");
      document.getElementById("friendsSection").style.display = "none";
      document.getElementById("logoutBtn").style.display = "none";
    }

    function showFriendsArea() {
      document.getElementById("friendsSection").style.display = "block";
      document.getElementById("logoutBtn").style.display = "inline-block";
    }

    // Show section if already logged in
    if (localStorage.getItem("loggedIn") === "yes") {
      showFriendsArea();
    }

    // Falling pizza pieces
    const pizzaCount = 10;
    for (let i = 0; i < pizzaCount; i++) {
      const pizza = document.createElement('div');
      pizza.classList.add('pizza');
      pizza.textContent = '🍕';
      pizza.style.left = Math.random() * 100 + 'vw';
      pizza.style.animationDuration = 4 + Math.random() * 4 + 's';
      pizza.style.fontSize = 20 + Math.random() * 40 + 'px';
      document.body.appendChild(pizza);
    }
  </script>

</body>
</html>
