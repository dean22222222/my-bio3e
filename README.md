<!-- Live Chat Button -->
<button class="chat-button">💬</button>

<!-- Live Chat Box -->
<div class="chat-box" id="chatBox">
  <div class="chat-header">Chat with Dean 🍕</div>
  <div class="chat-content" id="chatContent">
    <div class="message dean">Hey there! 👋 Got a question or just wanna say hi?</div>
  </div>
  <form class="chat-form" id="chatForm" action="https://formspree.io/f/xzzypwkv" method="POST">
    <input type="text" name="name" id="userName" placeholder="Your Name" required>
    <input type="email" name="email" id="userEmail" placeholder="Your Email" required>
    <textarea name="message" id="userMessage" rows="2" placeholder="Your Message..." required></textarea>
    <button type="submit">Send 🚀</button>
  </form>
</div>

<style>
  /* Chat styles */
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
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    transition: transform 0.2s ease, background 0.3s ease;
    z-index: 1000;
  }

  .chat-button:hover {
    background: #ff4040;
    transform: scale(1.1);
  }

  .chat-box {
    position: fixed;
    bottom: 90px;
    right: 20px;
    background: rgba(255, 255, 255, 0.95);
    border-radius: 12px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
    width: 320px;
    display: none;
    flex-direction: column;
    overflow: hidden;
    z-index: 1000;
  }

  .chat-header {
    background: #ffb347;
    padding: 12px;
    color: white;
    font-weight: bold;
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

  .message.user {
    background: #ff6b6b;
    color: white;
    align-self: flex-end;
  }

  .message.dean {
    background: #ffcc33;
    color: #333;
    align-self: flex-start;
  }

  .chat-form {
    display: flex;
    flex-direction: column;
    padding: 10px;
    gap: 5px;
  }

  .chat-form input, .chat-form textarea {
    width: 100%;
    padding: 8px;
    border-radius: 8px;
    border: 2px solid #ffb347;
    font-size: 0.9em;
  }

  .chat-form button {
    background: #ff6b6b;
    border: none;
    padding: 8px 15px;
    border-radius: 6px;
    color: white;
    font-size: 0.9em;
    cursor: pointer;
  }

  .chat-form button:hover {
    background: #ff4040;
  }
</style>

<script>
  const chatButton = document.querySelector('.chat-button');
  const chatBox = document.getElementById('chatBox');
  const chatContent = document.getElementById('chatContent');
  const chatForm = document.getElementById('chatForm');

  // Toggle chat box
  chatButton.addEventListener('click', () => {
    chatBox.style.display = chatBox.style.display === 'flex' ? 'none' : 'flex';
  });

  // Add message to chat
  function addMessage(text, sender) {
    const message = document.createElement('div');
    message.classList.add('message', sender);
    message.textContent = text;
    chatContent.appendChild(message);
    chatContent.scrollTop = chatContent.scrollHeight;
  }

  // Handle form submission
  chatForm.addEventListener('submit', function(e) {
    e.preventDefault();

    const name = document.getElementById('userName').value;
    const email = document.getElementById('userEmail').value;
    const message = document.getElementById('userMessage').value;

    // Show user's message instantly
    addMessage(message, 'user');

    // Send to Formspree
    fetch(chatForm.action, {
      method: 'POST',
      headers: { 'Accept': 'application/json' },
      body: new FormData(chatForm)
    }).then(response => {
      if(response.ok) {
        addMessage("Thanks! I got your message. 🍕", "dean");
        chatForm.reset();
      } else {
        addMessage("Oops, something went wrong. Try again!", "dean");
      }
    }).catch(() => {
      addMessage("Oops, something went wrong. Try again!", "dean");
    });
  });
</script>
