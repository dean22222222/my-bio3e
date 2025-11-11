<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Dean Sherrill 🍕 - Chat & About</title>
  <style>
    body {
      font-family: "Poppins", sans-serif;
      margin: 0;
      background: linear-gradient(135deg, #ffb347, #ffcc33);
      color: #333;
      text-align: center;
      overflow-x: hidden;
    }

    header {
      background-color: rgba(255, 255, 255, 0.25);
      padding: 40px 20px;
      backdrop-filter: blur(10px);
    }

    h1 {
      font-size: 2.8em;
      margin: 0;
    }

    section {
      padding: 40px 20px;
    }

    .about, .contact, .login-box {
      background: rgba(255, 255, 255, 0.85);
      border-radius: 12px;
      display: inline-block;
      padding: 30px;
      margin-top: 20px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
      max-width: 800px;
      text-align: left;
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

    /* Chat & Login */
    .chat-button {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #ff6b6b;
      color: white;
      border: none;
      border-radius: 50%;
      width: 60px;
      height: 60px;
      font-size: 28px;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      z-index: 1000;
    }

    .chat-button:hover { background: #ff4040; }

    .chat-box, .login-box {
      position: fixed;
      bottom: 90px;
      right: 20px;
      background: rgba(255, 255, 255, 0.95);
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.2);
      width: 320px;
      display: none;
      flex-direction: column;
      overflow: hidden;
      z-index: 1000;
    }

    .chat-header, .login-header {
      background: #ffb347;
      padding: 12px;
      color: white;
      font-weight: bold;
      text-align: center;
    }

    .chat-content {
      padding: 15px;
      flex: 1;
      max-height: 350px;
      overflow-y: auto;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .message {
      padding: 8px 12px;
      border-radius: 20px;
      max-width: 75%;
      font-size: 0.9em;
      line-height: 1.3;
    }

    .message.user { background: #ff6b6b; color: white; align-self: flex-end; }
    .message.dean { background: #ffcc33; color: #333; align-self: flex-start; }

    .chat-form, .login-form {
      display: flex;
      flex-direction: column;
      padding: 10px;
      gap: 5px;
    }

    .chat-form input, .chat-form textarea,
    .login-form input {
      width: 100%;
      padding: 8px;
      border-radius: 8px;
      border: 2px solid #ffb347;
      font-size: 0.9em;
    }

    .chat-form button, .login-form button {
      background: #ff6b6b;
      border: none;
      padding: 8px 15px;
      border-radius: 6px;
      color: white;
      font-size: 0.9em;
      cursor: pointer;
    }

    .chat-form button:hover, .login-form button:hover { background: #ff4040; }
  </style>
</head>
<body>
  <header>
    <h1>Hey, I'm Dean Sherrill 👋</h1>
    <p>Welcome to my slice of the internet 🍕</p>
  </header>

  <!-- About Me Section -->
  <section class="about">
    <h2>About Me 🎧</h2>
    <p>I love coding and coming up with creative ideas — there’s just something so cool about turning a thought into something real. I actually started coding when I was 13, and ever since then, I’ve been hooked. I go to school right now, so I’m always balancing classes with my hobbies, but I like staying busy and learning new things.</p>
    <p>When I’m not glued to my laptop, I’m usually texting my family or hanging out with them. They always know how to make me laugh and keep things fun. I also love playing Rec Room — it’s such a fun way to chill, meet people, and just mess around in different games.</p>
    <p>Music is a huge part of my life too — I’m pretty much always listening to something, whether I’m working, relaxing, or just vibing. Overall, I’m all about having fun, staying creative, and keeping those good vibes going wherever I can.</p>
  </section>

  <!-- Contact Section -->
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

  <footer>
    <p>© 2025 Dean Sherrill | Made with ❤️ & 🍕</p>
  </footer>

  <!-- Floating Pizzas -->
  <script>
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

  <!-- Chat / Login -->
  <button class="chat-button">💬</button>

  <!-- Login Box -->
  <div class="login-box" id="loginBox">
    <div class="login-header">Login to Chat 🍕</div>
    <form class="login-form" id="loginForm">
      <input type="text" id="loginName" placeholder="Your Name" required>
      <input type="email" id="loginEmail" placeholder="Your Email" required>
      <button type="submit">Login 🚀</button>
    </form>
  </div>

  <!-- Chat Box -->
  <div class="chat-box" id="chatBox">
    <div class="chat-header">Chat with Dean 🍕</div>
    <div class="chat-content" id="chatContent">
      <div class="message dean">Hey there! 👋 Got a question or just wanna say hi?</div>
    </div>
    <form class="chat-form" id="chatForm">
      <textarea id="userMessage" rows="2" placeholder="Your Message..." required></textarea>
      <button type="submit">Send 🚀</button>
    </form>
  </div>

  <script>
    const chatButton = document.querySelector('.chat-button');
    const chatBox = document.getElementById('chatBox');
    const loginBox = document.getElementById('loginBox');
    const chatContent = document.getElementById('chatContent');
    const chatForm = document.getElementById('chatForm');
    let userName = '';
    let userEmail = '';

    chatButton.addEventListener('click', () => {
      if (!userName) {
        loginBox.style.display = loginBox.style.display === 'flex' ? 'none' : 'flex';
      } else {
        chatBox.style.display = chatBox.style.display === 'flex' ? 'none' : 'flex';
      }
    });

    // Login handler
    document.getElementById('loginForm').addEventListener('submit', function(e) {
      e.preventDefault();
      userName = document.getElementById('loginName').value;
      userEmail = document.getElementById('loginEmail').value;
      loginBox.style.display = 'none';
      chatBox.style.display = 'flex';
      addMessage(`Welcome, ${userName}! 🎉`, 'dean');
    });

    function addMessage(text, sender) {
      const message = document.createElement('div');
      message.classList.add('message', sender);
      message.textContent = text;
      chatContent.appendChild(message);
      chatContent.scrollTop = chatContent.scrollHeight;
    }

    // Chat form
    chatForm.addEventListener('submit', function(e) {
      e.preventDefault();
      const message = document.getElementById('userMessage').value;
      if (!message) return;
      addMessage(message, 'user');
      document.getElementById('userMessage').value = '';

      // Optional: auto-reply
      setTimeout(() => {
        addMessage("Thanks for your message! 🍕 I'll get back to you soon.", "dean");
      }, 1000);
    });
  </script>
</body>
</html>
