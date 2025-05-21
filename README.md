# 🎯 JavaScript Event Handling & Interactive Elements Assignment

Welcome to the **ultimate JavaScript playground**! 🎉 This assignment is where we turn boring web pages into dynamic, responsive, *alive* experiences. Get ready to master **event handling**, build **interactive components**, and validate forms like a pro! 💪

## 📁 Assignment Structure

```
📂 js-event-assignment/
├── index.html         # Your playground – where it all comes together
├── style.css          # Keep it cute (optional but encouraged)
└── script.js          # The JavaScript wizardry happens here
```

---

## 🧪 What to Build

Here’s what your interactive bundle of joy should include:

### 1. Event Handling 🎈  
- Button click ✅  
- Hover effects ✅  
- Keypress detection ✅  
- Bonus: A secret action for a *double-click* or *long press* 🤫

### 2. Interactive Elements 🎮  
- A button that changes text or color  
- An image gallery or slideshow  
- Tabs or accordion-style content  
- Bonus: Add some animation using JS or CSS ✨

### 3. Form Validation 📋✅  
- Required field checks  
- Email format validation  
- Password rules (e.g., min 8 characters)  
- Bonus: Real-time feedback while typing

---

## 🧙‍♂️ Pro Tips

- Keep your code clean and commented – your future self will thank you!
- Think about **user experience** – what makes your site more *fun* to use?
- Don’t be afraid to **Google and experiment** – that’s how real developers roll!

---

## 🎉 Now Go Make It Fun!

Remember – this isn't just code. It's your **first step toward creating magical user experiences**. So play around, break stuff (then fix it), and most of all, have FUN! 😄

Happy Coding! 💻✨  


Answer

index.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JS Event Playground</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>🎉 JavaScript Event Playground</h1>

  <section>
    <button id="magicBtn">Click Me!</button>
    <p id="message"></p>
  </section>

  <section>
    <img id="hoverImg" src="https://via.placeholder.com/150" alt="Hover me">
  </section>

  <section>
    <input type="text" id="keyInput" placeholder="Type something...">
    <p id="keyOutput"></p>
  </section>

  <section>
    <form id="signupForm">
      <h2>Sign Up</h2>
      <input type="email" id="email" placeholder="Email" required>
      <input type="password" id="password" placeholder="Password" required>
      <button type="submit">Submit</button>
      <p id="formFeedback"></p>
    </form>
  </section>

  <section>
    <h2>Image Slideshow</h2>
    <img id="slideshow" src="https://via.placeholder.com/200" alt="Slideshow">
    <button id="nextImg">Next</button>
  </section>

  <script src="script.js"></script>
</body>
</html>

style.css

body {
  font-family: sans-serif;
  text-align: center;
  padding: 2rem;
  background: #f0f0f0;
}

section {
  margin: 2rem 0;
}

button {
  padding: 0.6rem 1rem;
  font-size: 1rem;
  cursor: pointer;
}

input {
  margin: 0.5rem;
  padding: 0.5rem;
}

script.js

// Button Click
document.getElementById("magicBtn").addEventListener("click", () => {
  const msg = document.getElementById("message");
  msg.textContent = "✨ Magic Happened!";
  msg.style.color = "purple";
});

// Hover Effect
document.getElementById("hoverImg").addEventListener("mouseover", () => {
  document.getElementById("hoverImg").style.border = "3px solid hotpink";
});
document.getElementById("hoverImg").addEventListener("mouseout", () => {
  document.getElementById("hoverImg").style.border = "none";
});

// Keypress Detection
document.getElementById("keyInput").addEventListener("keyup", (e) => {
  document.getElementById("keyOutput").textContent = `You typed: ${e.key}`;
});

// Double-click Secret
document.getElementById("magicBtn").addEventListener("dblclick", () => {
  alert("💥 You found the secret double-click!");
});

// Image Slideshow
const images = [
  "https://via.placeholder.com/200?text=1",
  "https://via.placeholder.com/200?text=2",
  "https://via.placeholder.com/200?text=3"
];
let imgIndex = 0;

document.getElementById("nextImg").addEventListener("click", () => {
  imgIndex = (imgIndex + 1) % images.length;
  document.getElementById("slideshow").src = images[imgIndex];
});

// Form Validation
document.getElementById("signupForm").addEventListener("submit", (e) => {
  e.preventDefault();
  const email = document.getElementById("email");
  const password = document.getElementById("password");
  const feedback = document.getElementById("formFeedback");

  if (!email.value.includes("@")) {
    feedback.textContent = "❌ Invalid email format!";
    feedback.style.color = "red";
    return;
  }

  if (password.value.length < 8) {
    feedback.textContent = "❌ Password must be at least 8 characters!";
    feedback.style.color = "red";
    return;
  }

  feedback.textContent = "✅ All good!";
  feedback.style.color = "green";
});

// Bonus: Real-time password feedback
document.getElementById("password").addEventListener("input", (e) => {
  const feedback = document.getElementById("formFeedback");
  if (e.target.value.length < 8) {
    feedback.textContent = "🔒 Password too short";
    feedback.style.color = "orange";
  } else {
    feedback.textContent = "✅ Good password length";
    feedback.style.color = "green";
  }
});


