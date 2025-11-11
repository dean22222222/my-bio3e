<!DOCTYPE html>
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

    h1 {
      font-size: 2.8em;
      margin: 0;
    }

    section {
      padding: 40px 20px;
    }

    .about, .contact {
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

    #talkjs-container {
      width: 350px;
      height: 500px;
      position: fixed;
      bottom: 70px;
      right: 20px;
      border-radius: 12px;
      overflow: hidden;
      z-index: 1000;
      display: none; /* start hidden */
    }

    #chat-toggle {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #ff6b6b;
      color: white;
      border: none;
      border-radius: 50%;
      width: 60px;
      height: 60px;
      font-size: 30px;
      cursor: pointer;
      z-index: 1001;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      transition: transform 0.2s ease;
    }

    #chat-toggle:hover {
      transform: scale(1.1);
    }
  </style>
</head>
<body>
  <header>
    <h1>Hey, I'm Dean Sherrill 👋</h1>
    <p>Welcome to my slice of the internet 🍕</p>
  </header>

  <section class="about">
    <h2>About Me 🎧</h2>
    <p> I love coding and coming up with creative ideas — there’s just something so cool about turning a thought into something real. I started coding at 13 and have been hooked ever since. I balance school with hobbies, but I love staying busy and learning new things.</p>
    <p>When I’m not coding, I’m usually texting my family or hanging out with them. I also love playing Rec Room and listening to music. Overall, I’m all about fun, creativity, and good vibes.</p>
  </section>

  <section class="contact">
    <h2>Get in Touch 📧</h2>
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

  <!-- Floating pizzas -->
  <script>
    for (let i = 0; i < 10; i++) {
      const pizza = document.createElement('div');
      pizza.classList.add('pizza');
      pizza.textContent = '🍕';
      pizza.style.left = Math.random() * 100 + 'vw';
      pizza.style.animationDuration = 4 + Math.random() * 4 + 's';
      pizza.style.fontSize = 20 + Math.random() * 40 + 'px';
      document.body.appendChild(pizza);
    }
  </script>

  <!-- TalkJS Chat -->
  <div id="talkjs-container"></div>
  <button id="chat-toggle">💬</button>
  <script src="https://cdn.talkjs.com/talk.js"></script>
  <script>
    let chatVisible = false;
    const chatToggle = document.getElementById('chat-toggle');
    const chatContainer = document.getElementById('talkjs-container');

    chatToggle.addEventListener('click', () => {
      chatVisible = !chatVisible;
      chatContainer.style.display = chatVisible ? 'block' : 'none';
    });

    Talk.ready.then(function() {
      const me = new Talk.User({
        id: "dean_sherrill",
        name: "Dean Sherrill",
        email: "dean@example.com",
        photoUrl: "https://i.pravatar.cc/150?img=3"
      });

      const session = new Talk.Session({
        appId: "tcN8OSbh", 
        me: me
      });

      const conversation = session.getOrCreateConversation("public_chat");
      conversation.setParticipant(me);

      const chatbox = session.createChatbox(conversation);
      chatbox.mount(document.getElementById("talkjs-container"));
    });
  </script>
</body>
</html>
