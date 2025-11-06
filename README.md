<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tentang Kamu — Tran</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400&display=swap');

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  color: #fff;
  background: radial-gradient(ellipse at bottom, #a2d5f2 0%, #ffb6c1 100%);
  overflow-x: hidden;
  position: relative;
}

/* Sparkling Background */
.sparkle-star {
  position: absolute;
  width: 2px;
  height: 2px;
  background: radial-gradient(circle, #fff 40%, rgba(255,255,255,0) 70%);
  border-radius: 50%;
  opacity: 0.6;
  animation: sparkle 2s infinite ease-in-out;
}

@keyframes sparkle {
  0%, 100% { opacity: 0.2; transform: scale(0.7); }
  50% { opacity: 1; transform: scale(1.3); }
}

/* Corner Photos */
.corner-photo {
  position: fixed;
  top: 20px;
  width: 80px;
  height: 80px;
  overflow: hidden;
  border-radius: 50%;
  border: 2px solid #fff;
  box-shadow: 0 4px 10px rgba(0,0,0,0.3);
  z-index: 1000;
}

.corner-photo.left { left: 20px; animation: floatLeft 3s ease-in-out infinite; cursor: grab; }
.corner-photo.right { right: 20px; animation: floatRight 4s ease-in-out infinite; cursor: grab; }

.corner-photo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s;
}

.corner-photo img:hover {
  transform: scale(1.1);
}

@keyframes floatLeft {
  0% { transform: translateY(0); }
  50% { transform: translateY(10px); }
  100% { transform: translateY(0); }
}

@keyframes floatRight {
  0% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
  100% { transform: translateY(0); }
}

/* Bubble */
.bubble {
  position: absolute;
  bottom: 0;
  background: rgba(255, 182, 193, 0.6);
  border-radius: 50%;
  pointer-events: none;
  animation: rise linear forwards;
}

@keyframes rise {
  0% { transform: translateY(0) scale(1); opacity: 1; }
  100% { transform: translateY(-600px) scale(1.5); opacity: 0; }
}

/* Popup Overlay */
#popupOverlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  backdrop-filter: blur(6px);
  background-color: rgba(0,0,0,0.4);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
}

/* Popup */
#popupMsg {
  position: relative;
  background: #ff69b4;
  color: #fff;
  padding: 30px 40px;
  border-radius: 12px;
  font-size: 1.3em;
  text-align: center;
  box-shadow: 0 5px 15px rgba(0,0,0,0.5);
  overflow: hidden;
}

/* Bintang popup */
.popup-stars {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.popup-stars div {
  position: absolute;
  width: 4px;
  height: 4px;
  background: radial-gradient(circle, #fff 40%, rgba(255,255,255,0) 70%);
  border-radius: 50%;
  opacity: 0.7;
  animation: twinklePopup 2s infinite ease-in-out;
}

@keyframes twinklePopup {
  0%, 100% { opacity: 0.2; transform: scale(0.8); }
  50% { opacity: 1; transform: scale(1.2); }
}

#popupBtn {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 1em;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  background-color: #fff;
  color: #ff69b4;
  font-weight: bold;
}

/* Header */
header {
  text-align: center;
  padding: 100px 20px 50px;
}

header h1 {
  font-family: 'Great Vibes', cursive;
  font-size: 4em;
  color: #ff69b4;
  margin-bottom: 10px;
  text-shadow: 0 2px 5px rgba(0,0,0,0.3);
}

header p {
  font-size: 1.2em;
  opacity: 0.9;
  color: #ffffff;
}

section {
  padding: 60px 20px;
  text-align: center;
  max-width: 900px;
  margin: auto;
}

/* === GALERI DENGAN ANIMASI LUCU === */
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 15px;
  margin-top: 30px;
}

.gallery-grid img {
  width: 100%;
  height: 150px;
  object-fit: cover;
  border-radius: 12px;
  border: 2px solid #fff;
  box-shadow: 0 4px 10px rgba(0,0,0,0.3);
  opacity: 0;
  transform: scale(0.9) translateY(20px);
  animation: fadeIn 1s forwards ease;
}

.gallery-grid img:nth-child(1) { animation-delay: 0.2s; }
.gallery-grid img:nth-child(2) { animation-delay: 0.4s; }
.gallery-grid img:nth-child(3) { animation-delay: 0.6s; }
.gallery-grid img:nth-child(4) { animation-delay: 0.8s; }
.gallery-grid img:nth-child(5) { animation-delay: 1s; }
.gallery-grid img:nth-child(6) { animation-delay: 1.2s; }
.gallery-grid img:nth-child(7) { animation-delay: 1.4s; }
.gallery-grid img:nth-child(8) { animation-delay: 1.6s; }

@keyframes fadeIn {
  to {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}

/* Hover lucu */
.gallery-grid img:hover {
  transform: scale(1.1) rotate(5deg);
  box-shadow: 0 8px 15px rgba(255,182,193,0.8);
  cursor: pointer;
  animation: floaty 2s ease-in-out infinite;
}

@keyframes floaty {
  0%, 100% { transform: scale(1.1) rotate(5deg) translateY(0); }
  50% { transform: scale(1.1) rotate(5deg) translateY(-8px); }
}

/* Sparkle kecil muncul saat hover foto */
.sparkle {
  position: absolute;
  font-size: 16px;
  pointer-events: none;
  animation: sparkleFly 1s ease-out forwards;
}

@keyframes sparkleFly {
  from { opacity: 1; transform: translateY(0) scale(1); }
  to { opacity: 0; transform: translateY(-30px) scale(0.5); }
}

.video-row {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
  margin-top: 30px;
}

.video-row video {
  width: 300px;
  height: 170px;
  border-radius: 12px;
  border: 2px solid #fff;
  box-shadow: 0 4px 10px rgba(0,0,0,0.3);
}

footer {
  text-align: center;
  padding: 30px;
  font-size: 0.9em;
  opacity: 0.8;
}

.timeline {
  margin-top: 40px;
  text-align: left;
}

.event {
  background: rgba(255,255,255,0.2);
  margin: 15px 0;
  padding: 15px;
  border-radius: 10px;
}
</style>
</head>
<body>

<!-- FOTO SUDUT -->
<div class="corner-photo left"><img src="foto_kiri.jpg" alt="Foto Kiri"></div>
<div class="corner-photo right"><img src="foto_kanan.jpg" alt="Foto Kanan"></div>

<header>
  <h1>Tentang Kamu — Tran</h1>
  <p>Sebuah kenangan indah yang tak akan kulupakan 🌙</p>
</header>

<!-- GALERI -->
<section>
  <h2>Galeri & Video Kenangan Kita 📸🎬</h2>
  <div class="gallery-grid">
    <img src="contoh foto.jpg" alt="Kita di pantai">
    <img src="contoh foto.jpg" alt="Di Bali">
    <img src="contoh foto.jpg" alt="Selfie bareng">
    <img src="contoh foto.jpg" alt="Bareng teman">
    <img src="contoh foto.jpg" alt="See bareng">
    <img src="foto_1.jpg" alt="Foto Kenangan 1">
    <img src="foto_2.jpg" alt="Foto Kenangan 2">
    <img src="foto_3.jpg" alt="Foto Kenangan 3">
    <img src="foto_4.jpg" alt="Foto Kenangan 4">
    <img src="foto_5.jpg" alt="Foto Kenangan 5">
  </div>

  <div class="video-row">
    <video controls loop muted>
      <source src="videos/kenangan.mp4" type="video/mp4">
    </video>
  </div>
</section>

<!-- Cerita -->
<section>
  <h2>Cerita Kita 💌</h2>
  <p>Dulu aku tidak tahu apa arti rindu — sampai aku mengenalmu...</p>
</section>

<!-- Timeline -->
<section class="timeline">
  <h2>Perjalanan Cinta Kita ⏳</h2>
  <div class="event"><strong>1 Oktober 2025</strong> — Hari pertama kita saling mengenal 💬</div>
  <div class="event"><strong>30 Desember 2025</strong> — Hari ulang tahunku, kau memberikan hadiah indah 💖</div>
  <div class="event"><strong>12 Juni 2023</strong> — Hari kamu bilang “ya” untuk jadi bagian hidupku 🌹</div>
</section>

<!-- Surat -->
<section>
  <h2>Surat Untukmu ✉️</h2>
  <p>Dear kamu... 💫</p>
</section>

<footer>
  Dibuat dengan ❤️ untuk kenangan yang abadi — Tran © 2025
</footer>

<!-- POPUP -->
<div id="popupOverlay">
  <div id="popupMsg">
    Hai sayang! 💖<br>semoga kamu suka ya?
    <button id="popupBtn">Iyaa 💖</button>
    <div class="popup-stars"></div>
  </div>
</div>

<script>
// Popup
document.body.style.overflow = 'hidden';
const popupStarsContainer = document.querySelector('.popup-stars');
for (let i = 0; i < 50; i++) {
  const star = document.createElement('div');
  star.style.top = Math.random() * 100 + '%';
  star.style.left = Math.random() * 100 + '%';
  star.style.width = (Math.random() * 3 + 2) + 'px';
  star.style.height = star.style.width;
  star.style.animationDuration = (Math.random() * 2 + 1) + 's';
  popupStarsContainer.appendChild(star);
}
document.getElementById('popupBtn').addEventListener('click', () => {
  document.getElementById('popupOverlay').remove();
  document.body.style.overflow = '';
});

// Sparkling background
function createSparkles(count) {
  for (let i = 0; i < count; i++) {
    const star = document.createElement('div');
    star.className = 'sparkle-star';
    star.style.top = Math.random() * window.innerHeight + 'px';
    star.style.left = Math.random() * window.innerWidth + 'px';
    star.style.width = (Math.random() * 2 + 1) + 'px';
    star.style.height = star.style.width;
    star.style.animationDuration = (Math.random() * 2 + 1) + 's';
    star.style.animationDelay = Math.random() * 2 + 's';
    document.body.appendChild(star);
  }
}
createSparkles(window.innerWidth < 600 ? 40 : 100);

// ✨ Sparkle emoji saat hover foto
document.querySelectorAll('.gallery-grid img').forEach(img => {
  img.addEventListener('mouseenter', (e) => {
    for (let i = 0; i < 5; i++) {
      const sparkle = document.createElement('div');
      sparkle.className = 'sparkle';
      sparkle.textContent = ['✨','💖','🌸','💫'][Math.floor(Math.random()*4)];
      sparkle.style.left = (e.offsetX + Math.random()*30 - 15) + 'px';
      sparkle.style.top = (e.offsetY + Math.random()*30 - 15) + 'px';
      img.parentElement.appendChild(sparkle);
      setTimeout(() => sparkle.remove(), 1000);
    }
  });
});

// ===== BUBBLE ANIMASI =====
function createBubbles(count) {
  for (let i = 0; i < count; i++) {
    const bubble = document.createElement('div');
    bubble.className = 'bubble';
    const size = Math.random() * 20 + 10;
    bubble.style.width = size + 'px';
    bubble.style.height = size + 'px';
    bubble.style.left = Math.random() * window.innerWidth + 'px';
    bubble.style.animationDuration = (4 + Math.random() * 3) + 's';
    document.body.appendChild(bubble);
    setTimeout(() => bubble.remove(), 7000);
  }
}
setInterval(() => createBubbles(3), 1000);

// ===== DRAGGABLE CORNER PHOTOS =====
function makeDraggable(element) {
  let isDragging = false;
  let offsetX, offsetY;

  element.style.cursor = "grab"; // kursor tangan

  element.addEventListener("mousedown", startDrag);
  element.addEventListener("touchstart", startDrag);

  function startDrag(e) {
    isDragging = true;
    element.style.cursor = "grabbing";

    const rect = element.getBoundingClientRect();
    if (e.touches) e = e.touches[0];
    offsetX = e.clientX - rect.left;
    offsetY = e.clientY - rect.top;

    document.addEventListener("mousemove", onDrag);
    document.addEventListener("mouseup", stopDrag);
    document.addEventListener("touchmove", onDrag);
    document.addEventListener("touchend", stopDrag);
  }

  function onDrag(e) {
    if (!isDragging) return;
    if (e.touches) e = e.touches[0];

    const x = e.clientX - offsetX;
    const y = e.clientY - offsetY;
    element.style.left = x + "px";
    element.style.top = y + "px";
    element.style.position = "fixed";
  }

  function stopDrag() {
    isDragging = false;
    element.style.cursor = "grab";
    document.removeEventListener("mousemove", onDrag);
    document.removeEventListener("mouseup", stopDrag);
    document.removeEventListener("touchmove", onDrag);
    document.removeEventListener("touchend", stopDrag);
  }
}

// panggil untuk kedua foto pojok
makeDraggable(document.querySelector(".corner-photo.left"));
makeDraggable(document.querySelector(".corner-photo.right"));
</script>

</body>
</html>
