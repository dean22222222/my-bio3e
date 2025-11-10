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
  </style>
</head>
<body>
  <header>
    <h1>Hey, I'm Dean Sherrill 👋</h1>
    <p>Welcome to my slice of the internet 🍕</p>
  </header>

  <section class="about">
    <h2>About Me 🎧</h2>
    <p> I love coding and coming up with creative ideas — there’s just something so cool about turning a thought into something real. I actually started coding when I was 13, and ever since then, I’ve been hooked. I go to school right now, so I’m always balancing classes with my hobbies, but I like staying busy and learning new things.

When I’m not glued to my laptop, I’m usually texting my family or hanging out with them. They always know how to make me laugh and keep things fun. I also love playing Rec Room — it’s such a fun way to chill, meet people, and just mess around in different games.

Music is a huge part of my life too — I’m pretty much always listening to something, whether I’m working, relaxing, or just vibing. Overall, I’m all about having fun, staying creative, and keeping those good vibes going wherever I can.</p>
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

  <footer>
    <p>© 2025 Dean Sherrill | Made with ❤️ & 🍕</p>
  </footer>

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
</body>
</html>
