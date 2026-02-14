<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Geetha Surprise ❤️</title>

<style>

body {
  margin: 0;
  font-family: Arial, sans-serif;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;

  /* background hearts style */
  background: linear-gradient(135deg, #ff9a9e, #fad0c4);
}

/* Card */
.card {
  background: white;
  padding: 30px;
  border-radius: 25px;
  text-align: center;
  width: 320px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.2);
}

/* Title */
h1 {
  color: #1e73be;
  margin-bottom: 10px;
}

/* Image container */
.image-container {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}

/* Image style */
.profile-img {
  width: 100%;
  max-width: 260px;
  border-radius: 20px;
  object-fit: cover;
  box-shadow: 0 8px 20px rgba(0,0,0,0.15);
  animation: fadeIn 1.2s ease-in-out;
}

/* Question text */
.question {
  font-size: 26px;
  color: #ff4081;
  margin: 15px 0;
  font-weight: bold;
}

/* Buttons */
.buttons {
  margin-top: 20px;
}

button {
  border: none;
  padding: 12px 25px;
  font-size: 18px;
  border-radius: 12px;
  cursor: pointer;
  margin: 8px;
  transition: 0.3s;
}

.yes-btn {
  background: #ff4d6d;
  color: white;
}

.yes-btn:hover {
  transform: scale(1.1);
}

.no-btn {
  background: #9aa0a6;
  color: white;
  position: relative;
}

/* animation */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(0.9);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

</style>
</head>

<body>

<div class="card">

  <h1>Geetha Surprise 💖</h1>

  <!-- IMAGE -->
  <div class="image-container">
    <img
      src="https://github.com/user-attachments/assets/58b924a8-1132-4506-860c-8ca2a7614b60"
      alt="Us"
      class="profile-img">
  </div>

  <!-- QUESTION -->
  <div class="question">
    Will you be my Valentine? 💝
  </div>

  <!-- BUTTONS -->
  <div class="buttons">
    <button class="yes-btn" onclick="sayYes()">Yes!</button>
    <button class="no-btn" id="noBtn">No</button>
  </div>

</div>

<script>

/* YES button */
function sayYes() {
  alert("Yay ❤️ I knew you'd say YES! 💕");
}

/* Moving NO button 😄 */
const noBtn = document.getElementById("noBtn");

noBtn.addEventListener("mouseover", () => {
  const x = Math.random() * 200 - 100;
  const y = Math.random() * 200 - 100;
  noBtn.style.transform = `translate(${x}px, ${y}px)`;
});

</script>

</body>
</html>
