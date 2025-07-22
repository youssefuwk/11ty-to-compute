<!DOCTYPE html>    <html dir="rtl" lang="ar">        <head>        
  <meta charset="UTF-8" />        
  <title>خلفية فضائية فقط</title>        
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />        
  <style>        
    * { margin:0; padding:0; box-sizing:border-box; }        
    html, body {        
      height:100vh; overflow:hidden;        
      background: linear-gradient(135deg, #020c36, #1a0050);        
      position:relative;        
    }      html::before {        
  content: '';        
  position: absolute;        
  inset: 0;        
  background: linear-gradient(135deg, rgba(0,229,255,0.4), rgba(213,0,249,0.4));        
  mix-blend-mode: screen;        
  z-index: 0;        
  pointer-events: none;        
  filter: brightness(1.3) saturate(2);        
}        body::before {
content: '';
position: absolute;
bottom: 0;
right: 0;
width: 100%;
height: 100%;
background:
radial-gradient(circle at bottom right, rgba(0,255,255,0.25), transparent 70%),
radial-gradient(circle at 20% 30%, rgba(255,0,255,0.12), transparent 70%),
radial-gradient(circle at 70% 10%, rgba(0,200,255,0.1), transparent 70%);
filter: blur(80px);
mix-blend-mode: screen;
z-index: 0;
pointer-events: none;
}

/* ✅ طبقة تعزيز ألوان الخلفية */
body::after {
content: '';
position: absolute;
inset: 0;
background: linear-gradient(135deg, #051442cc, #2b007ecc);
z-index: -1;
pointer-events: none;
mix-blend-mode: soft-light;
opacity: 1;
}

.stars1, .stars2, .stars3 {
content: ''; position: absolute;
top: 0; left: 0;
width: 100%; height: 100%;
background-repeat: repeat;
opacity: 0.15;
z-index: 0;
}

.stars1 {
background-image: radial-gradient(white 0.7px, transparent 1px);
background-size: 120px 120px;
animation: twinkle 5s ease-in-out infinite alternate, moveStars1 45s linear infinite;
}

.stars2 {
background-image: radial-gradient(white 1px, transparent 1px);
background-size: 160px 160px;
animation: twinkle 6s ease-in-out infinite alternate, moveStars2 70s linear infinite;
}

.stars3 {
background-image: radial-gradient(white 1.2px, transparent 1px);
background-size: 220px 220px;
animation: twinkle 7s ease-in-out infinite alternate, moveStars3 90s linear infinite;
}

@keyframes twinkle {
0%, 100% { opacity: 0.15; }
50% { opacity: 0.25; }
}

@keyframes moveStars1 {
0% { background-position: 0 0; }
100% { background-position: -300px 150px; }
}

@keyframes moveStars2 {
0% { background-position: 100px 0; }
100% { background-position: -200px 200px; }
}

@keyframes moveStars3 {
0% { background-position: 0 100px; }
100% { background-position: 250px -250px; }
}

.shooting-star {
position: absolute;
width: 120px;
height: 2px;
background: linear-gradient(90deg, white, transparent);
border-radius: 50%;
opacity: 0;
z-index: 1;
will-change: transform, opacity;
transform: rotate(-45deg);
animation-name: shooting;
animation-timing-function: ease-in-out;
animation-fill-mode: forwards;
}

@keyframes shooting {
0% {
transform: translate(0, 0) rotate(-45deg);
opacity: 0;
}
10% {
opacity: 1;
}
100% {
transform: translate(-700px, 700px) rotate(-45deg);
opacity: 0;
}
}

.random-star {
position: absolute;
width: 2px;
height: 2px;
background: white;
border-radius: 50%;
opacity: 0;
animation: randomFlicker 10s infinite ease-in-out;
}

@keyframes randomFlicker {
0%, 100% { opacity: 0; }
5% { opacity: 1; }
10% { opacity: 0; }
30% { opacity: 1; }
35% { opacity: 0; }
70% { opacity: 1; }
75% { opacity: 0; }
}

.animated-blue-layer {
position: absolute;
inset: 0;
pointer-events: none;
z-index: 1;
background: radial-gradient(circle at var(--x, 50%) var(--y, 50%), rgba(0,229,255,0.18), transparent 80%);
filter: blur(160px);
animation: moveGlow 80s infinite ease-in-out;
mix-blend-mode: screen;
will-change: opacity, transform;
}

@keyframes moveGlow {
0% { --x: 10%; --y: 20%; opacity: 0.05; }
20% { --x: 50%; --y: 30%; opacity: 0.1; }
40% { --x: 80%; --y: 40%; opacity: 0.2; }
60% { --x: 60%; --y: 70%; opacity: 0.15; }
80% { --x: 30%; --y: 60%; opacity: 0.1; }
100% { --x: 10%; --y: 20%; opacity: 0.05; }
}

.big-twinkling-stars {
position: absolute;
top: 0; left: 0;
width: 100%; height: 100%;
pointer-events: none;
z-index: 2;
}

.big-twinkling-stars span {
position: absolute;
width: 3px;
height: 3px;
background: white;
border-radius: 50%;
box-shadow: 0 0 6px 1px rgba(255,255,255,0.6);
opacity: 0;
animation: bigTwinkle 5s infinite ease-in-out;
}

@keyframes bigTwinkle {
0%, 100% { opacity: 0; transform: scale(0.7); }
50% { opacity: 1; transform: scale(1); }
}

/* تحسين جودة الريندر */
.animated-blue-layer,
.stars1,
.stars2,
.stars3,
body::before,
html::before {
backface-visibility: hidden;
transform: translateZ(0);
will-change: opacity, transform;
image-rendering: optimizeQuality;
}

  </style>        
</head>        
<body>        
  <div class="animated-blue-layer"></div>        
  <div class="stars1"></div>        
  <div class="stars2"></div>        
  <div class="stars3"></div>        <!-- Shooting Stars -->        <div class="shooting-star" style="top:10%; left:85%; animation-delay:0s; animation-duration:1.2s;"></div>        
  <div class="shooting-star" style="top:15%; left:10%; animation-delay:7s; animation-duration:1.3s;"></div>        
  <div class="shooting-star" style="top:10%; left:85%; animation-delay:14s; animation-duration:1.2s;"></div>        
  <div class="shooting-star" style="top:15%; left:10%; animation-delay:15s; animation-duration:1.3s;"></div>        
  <div class="shooting-star" style="top:10%; left:85%; animation-delay:21s; animation-duration:1.2s;"></div>        
  <div class="shooting-star" style="top:15%; left:10%; animation-delay:28s; animation-duration:1.3s;"></div>        
  <div class="shooting-star" style="top:10%; left:85%; animation-delay:35s; animation-duration:1.2s;"></div>        
  <div class="shooting-star" style="top:15%; left:10%; animation-delay:36s; animation-duration:1.3s;"></div>        <!-- Random flickering stars -->        <div class="random-star" style="top:8%; left:20%; animation-delay:2s;"></div>        
  <div class="random-star" style="top:30%; left:40%; animation-delay:4s;"></div>        
  <div class="random-star" style="top:50%; left:15%; animation-delay:1s;"></div>        
  <div class="random-star" style="top:60%; left:70%; animation-delay:3s;"></div>        
  <div class="random-star" style="top:80%; left:35%; animation-delay:5s;"></div>        
  <div class="random-star" style="top:25%; left:75%; animation-delay:6s;"></div>        <!-- نجوم لامعة عشوائية -->        <div class="big-twinkling-stars" id="bigStars"></div>        <!-- سكريبت توليد النجوم العشوائية -->    <script>      
    const container = document.getElementById('bigStars');      
    const starCount = 20;      for (let i = 0; i < starCount; i++) {      
  const star = document.createElement('span');      
  star.style.top = Math.random() * 100 + '%';      
  star.style.left = Math.random() * 100 + '%';      
  star.style.animationDelay = (Math.random() * 10).toFixed(2) + 's';      
  star.style.animationDuration = (Math.random() * 5 + 3).toFixed(2) + 's';      
  container.appendChild(star);      
}    

// ✨ نجوم إضافية خفيفة في الأعلى يمين وشمال (بعد التعديل)    
const extraStars = 6;    
for (let i = 0; i < extraStars; i++) {    
  const star = document.createElement('span');    
  star.style.top = (Math.random() * 20) + '%';    
  star.style.left = (Math.random() < 0.5 ? Math.random() * 15 : 85 + Math.random() * 15) + '%';    
  star.style.opacity = 0.25;    
  star.style.width = '1.5px';    
  star.style.height = '1.5px';    
  star.style.animationDelay = (Math.random() * 10).toFixed(2) + 's';    
  star.style.animationDuration = (Math.random() * 6 + 6).toFixed(2) + 's';    
  container.appendChild(star);    
}

</script>    </body>

</html>
