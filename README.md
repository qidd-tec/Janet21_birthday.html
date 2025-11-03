<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1"/>
<title>HAPPY BIRTHDAY MY QUEEN</title>
<style>
  :root{
    --black:#050305;
    --soft-pink:#fff1f7;
    --pink-1:#ffeef6;
    --pink-2:#ffd6ea;
    --accent:#ff4da6;
    --text-dark:#3a0a14;
  }
  html,body{height:100%;margin:0;font-family:Inter, system-ui, -apple-system, 'Segoe UI', Roboto, Arial; -webkit-font-smoothing:antialiased;}
  body{background:var(--black);color:var(--soft-pink);overflow-x:hidden;transition:background .9s ease;}
  /* Loading */
  #loading{position:fixed;inset:0;display:flex;align-items:center;justify-content:center;background:linear-gradient(180deg,#ffbfdc,#ffd6ea);z-index:110}
  #loading h1{font-size:20px;color:#70102a}
  /* Intro / Candle stage */
  #candleStage{position:fixed;inset:0;display:flex;align-items:center;justify-content:center;flex-direction:column;gap:18px;z-index:100;background:var(--black)}
  .top-text{font-size:20px;color:#fff;margin-bottom:6px;text-align:center}
  .candle-wrap{display:flex;flex-direction:column;align-items:center;gap:12px}
  /* large candle */
  .candle{
    width:180px; height:420px; border-radius:22px; background:linear-gradient(180deg,#fff8f6,#ffefef);
    position:relative; display:flex;align-items:flex-start;justify-content:center;padding-top:28px; box-shadow:0 30px 80px rgba(0,0,0,0.6);
  }
  .candle:before{content:'';position:absolute;left:50%;transform:translateX(-50%);bottom:12px;width:120px;height:36px;background:linear-gradient(180deg,#ffe8f1,#ffd8e9);border-radius:12px}
  .wick{width:6px;height:18px;background:#3a0a14;border-radius:3px;position:relative;z-index:2}
  .flame{
    position:absolute;top:8px;left:50%;transform:translateX(-50%) translateY(0);
    width:44px;height:66px;border-radius:50% 50% 50% 50%;
    background: radial-gradient(circle at 40% 30%, #ffd54d, #ff6b6b);
    filter:drop-shadow(0 16px 38px rgba(255,80,130,0.22));
    opacity:0; transform-origin:center bottom; animation:flicker 1s infinite;
  }
  @keyframes flicker{
    0%{transform:translateX(-50%) translateY(0) scale(1)}
    50%{transform:translateX(-50%) translateY(3px) scale(.98)}
    100%{transform:translateX(-50%) translateY(0) scale(1)}
  }
  .glow{position:absolute;left:50%;top:110px;transform:translateX(-50%);width:260px;height:260px;border-radius:50%;background:radial-gradient(circle,#ffdfd6, transparent 45%);opacity:0;transition:opacity .6s ease}
  .btn{background:var(--accent);color:#fff;padding:12px 18px;border-radius:14px;border:0;font-weight:700;cursor:pointer;box-shadow:0 12px 30px rgba(255,77,166,0.14)}
  .ghost{background:transparent;border:2px solid rgba(255,255,255,0.08);color:var(--soft-pink)}
  /* smoke */
  .smoke{position:absolute;top:-12px;left:50%;transform:translateX(-50%);opacity:0;pointer-events:none}
  .smoke:before,.smoke:after{content:'';position:absolute;border-radius:50%;width:22px;height:22px;background:rgba(255,255,255,0.08);left:0;top:0;filter:blur(6px)}
  /* main content (pink theme) */
  main{display:none;min-height:100vh;background:linear-gradient(180deg,var(--pink-1),var(--pink-2));color:var(--text-dark);padding:36px 20px;transition:opacity .6s ease}
  .nav-icons{position:fixed;right:14px;top:40%;display:flex;flex-direction:column;gap:12px;z-index:90}
  .nav-icon{width:56px;height:56px;border-radius:14px;background:linear-gradient(180deg,#ffe7f3,#ffd1ea);display:flex;align-items:center;justify-content:center;box-shadow:0 8px 20px rgba(255,77,166,0.12);cursor:pointer;color:#4a0310;font-weight:700}
  .section{max-width:980px;margin:18px auto;padding:18px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.9), rgba(255,255,255,0.8));box-shadow:0 8px 30px rgba(0,0,0,0.05)}
  .title{font-size:clamp(20px,4vw,32px);margin:0 0 8px}
  .subtitle{color:#6a2631;margin:0 0 6px}
  .message{padding:14px;border-radius:10px;background:linear-gradient(180deg,#fff,#fff6fb);color:var(--text-dark)}
  .photos-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:12px;margin-top:14px}
  .photo-card{border-radius:12px;overflow:hidden;background:#fff;box-shadow:0 6px 18px rgba(0,0,0,0.06);display:flex;flex-direction:column}
  .photo-card img{width:100%;height:160px;object-fit:cover}
  .photo-caption{padding:8px;font-size:14px;color:#5a2630;background:#fff2f8}
  footer{margin-top:26px;text-align:center;color:#5a2630}
  /* sparkle transition overlay */
  .sparkle-overlay{position:fixed;inset:0;pointer-events:none;opacity:0;transition:opacity .6s ease;z-index:95}
  .sparkle-dot{position:absolute;background:radial-gradient(circle,#fff2ff,transparent);width:8px;height:8px;border-radius:50%;opacity:.9}
  /* responsive */
  @media (max-width:720px){.candle{width:130px;height:320px}.glow{width:200px;height:200px}.nav-icon{width:48px;height:48px}}
</style>
</head>
<body>

<!-- Loading -->
<div id="loading"><h1>Loading your surprise 🎁💖</h1></div>

<!-- Candle Stage (black theme) -->
<div id="candleStage" aria-hidden="false">
  <div class="candle-wrap">
    <div class="top-text">Hey birthday queen 👑 ready for 21?</div>

    <div style="position:relative">
      <div class="candle" id="candle">
        <div class="wick" aria-hidden="true"></div>
        <div class="flame" id="flame" style="opacity:0"></div>
        <div class="glow" id="glow" style="opacity:0"></div>
        <div class="smoke" id="smoke" aria-hidden="true"></div>
      </div>
    </div>

    <div id="candleButtons">
      <button id="lightBtn" class="btn">Light the Candle 🕯️</button>
    </div>
    <div style="height:8px"></div>
    <div style="opacity:0.85;color:#fff2f2">Take a moment and make a wish when ready 💫</div>
  </div>
</div>

<!-- Sparkles overlay used during transitions -->
<div class="sparkle-overlay" id="sparkleOverlay"></div>

<!-- Navigation icons -->
<div class="nav-icons" aria-hidden="true" id="navIcons" style="display:none">
  <div class="nav-icon" data-target="welcome">✨</div>
  <div class="nav-icon" data-target="special">💌</div>
  <div class="nav-icon" data-target="speech">🎙️</div>
  <div class="nav-icon" data-target="photos">📸</div>
  <div class="nav-icon" data-target="outro">💞</div>
</div>

<!-- Main pink content -->
<main id="mainContent" aria-hidden="true" style="display:none;opacity:0">
  <section id="welcome" class="section">
    <h1 class="title">Happy 21st Birthday, My Love🎂💗</h1>
    <p class="subtitle">Welcome, beautiful — the day is yours.
"Hey my love ❤️, happy anniversary month and happy birthday month! 🥰 Every moment with you feels like a beautiful dream I never want to wake up from. You are my joy, my peace, my everything. I can’t wait to celebrate us and you this month—because you deserve all the love and happiness in the world. 💖" Enjoy the little moments ✨</p>
  </section>

  <section id="special" class="section">
    <h2 class="title">Special Touch 💌</h2>
    <div class="message">
      <p><strong>Every year you bloom a little more,</strong><br>and I thank God for letting me meet your light 💖<br>You are my calm, my spark, and my forever wish.</p>
    </div>
  </section>

  <section id="speech" class="section">
    <h2 class="title">Birthday Speech 🎙️</h2>
    <div class="message">
      <p>Hey love 💓 I know it's 3 years turning into legal age and so far so good 😊 I mean I didn't know you back then and people say I wish I met you earlier but for me I am right where I wanted to meet you — not experimenting, not shuffling my cards, not wishing… just doing it the right way to love, care, grow and be in the moment 💞</p>
      <p>And yes 😂 3 years in, I found the best version of yourself — one who appreciates herself, tries her best and personally I wish the best for you my girl 💐 because you told me your dreams and I loved them to the point if it doesn't work out for me I pray it does for you 🙏</p>
      <p>But GOD on our side? Everything will work out in His time ⏳<br><em>Isaiah 60:22 — At the right time I the Lord will make it happen.</em> 💫</p>
      <p>He has made 21 possible — He is to be praised 🙌 So enjoy your day as you grow older baby 💝</p>
    </div>
  </section>

  <section id="photos" class="section">
  <h2 class="title">Scene 5 — Photos 📸</h2>
  <div class="photos-grid" id="photosGrid">
    <!-- 7 updated images -->
    <div class="photo-card">
      <img src="https://raw.githubusercontent.com/qidd-tec/My_images-/c2383c7e6dd03fe84faa172e1c16e58a8e4bc314/IMG-20250206-WA0037.jpg" alt="photo1">
      <div class="photo-caption">How you embraced yourself more 💖</div>
    </div>
    <div class="photo-card">
      <img src="https://raw.githubusercontent.com/qidd-tec/My_images-/c2383c7e6dd03fe84faa172e1c16e58a8e4bc314/IMG-20250316-WA0015.jpg" alt="photo2">
      <div class="photo-caption">How you've grown to be beautiful 🌸</div>
    </div>
    <div class="photo-card">
      <img src="https://raw.githubusercontent.com/qidd-tec/My_images-/c2383c7e6dd03fe84faa172e1c16e58a8e4bc314/IMG-20250316-WA0040.jpg" alt="photo3">
      <div class="photo-caption">Always love you ❤️</div>
    </div>
    <div class="photo-card">
      <img src="https://raw.githubusercontent.com/qidd-tec/My_images-/c2383c7e6dd03fe84faa172e1c16e58a8e4bc314/IMG-20250608-WA0018.jpg" alt="photo4">
      <div class="photo-caption">Your smile is my favorite sunrise ☀️</div>
    </div>
    <div class="photo-card">
      <img src="https://raw.githubusercontent.com/qidd-tec/My_images-/c2383c7e6dd03fe84faa172e1c16e58a8e4bc314/IMG-20250812-WA0008.jpg" alt="photo5">
      <div class="photo-caption">You glow even in silence 🌷</div>
    </div>
    <div class="photo-card">
      <img src="https://raw.githubusercontent.com/qidd-tec/My_images-/c2383c7e6dd03fe84faa172e1c16e58a8e4bc314/IMG-20250812-WA0009.jpg" alt="photo6">
      <div class="photo-caption">You make ordinary moments magical 💞</div>
    </div>
    <div class="photo-card">
      <img src="https://raw.githubusercontent.com/qidd-tec/My_images-/c2383c7e6dd03fe84faa172e1c16e58a8e4bc314/IMG-20250925-WA0024.jpg" alt="photo7">
      <div class="photo-caption">Forever proud of you, my Queen 👑</div>
    </div>
  </div>
  <p style="margin-top:12px;color:#6a2631">Photos are hosted from my heart — enjoy our memories together💖</p>
</section>

  <section id="outro" class="section" style="text-align:center">
    <h2 class="title">💌 Made with love by Qidd Kelvin 💞</h2>
    <p class="subtitle">To many more birthdays, my Queen 👑</p>
  </section>

  <footer><p style="color:#6a2631">Enjoy your day, baby — from mutuku 💝</p></footer>
</main>

<!-- hidden iframe for music - will be set on button click -->
<iframe id="ytPlayer" style="display:none;width:0;height:0;border:0"></iframe>

<script>
  // Short helpers
  const loading = document.getElementById('loading');
  const candleStage = document.getElementById('candleStage');
  const lightBtn = document.getElementById('lightBtn');
  const candle = document.getElementById('candle');
  const flame = document.getElementById('flame');
  const glow = document.getElementById('glow');
  const candleButtons = document.getElementById('candleButtons');
  const smoke = document.getElementById('smoke');
  const main = document.getElementById('mainContent');
  const navIcons = document.getElementById('navIcons');
  const sparkleOverlay = document.getElementById('sparkleOverlay');
  const ytPlayer = document.getElementById('ytPlayer');

  // YouTube video ID (Ni We - Kinoti Kinyua)
  const YT_ID = "0aYmdaI2inc";

  // initial stage: remove loading after a brief moment
  setTimeout(()=> {
    loading.style.display = 'none';
    // candle stage visible; nothing else
  }, 900);

  // function to create Make a Wish button after lighting
  function showMakeWish(){
    candleButtons.innerHTML = '<button id="wishBtn" class="btn">Make a Wish ✨</button>';
    const wishBtn = document.getElementById('wishBtn');
    wishBtn.addEventListener('click', onMakeWish);
  }

  // show flame (lighting)
  function lightCandle(){
    flame.style.opacity = 1;
    glow.style.opacity = 0.9;
    // show Make a Wish after short delay
    setTimeout(()=> showMakeWish(), 600);
  }

  // extinguish flame with slow fade and smoke
  function extinguishCandle(){
    let op = 1;
    const fade = setInterval(()=>{
      op -= 0.03;
      if(op <= 0){
        op = 0; clearInterval(fade);
      }
      flame.style.opacity = op;
      glow.style.opacity = op * 0.9;
    }, 50);
    // show a little smoke element (fade-in then float up)
    smoke.style.opacity = 0.9;
    smoke.style.transition = 'transform 2200ms linear, opacity 2200ms ease';
    smoke.style.transform = 'translateY(-80px) scale(1.6)';
    smoke.style.width = '28px'; smoke.style.height='28px';
    setTimeout(()=> { smoke.style.opacity = 0; }, 2000);
  }

  // After make a wish, extinguish then transition after 2.2s
  function onMakeWish(){
    // extinguish
    extinguishCandle();
    // disable button quickly
    const wishBtn = document.getElementById('wishBtn');
    wishBtn.disabled = true;
    wishBtn.textContent = 'Blown 🎉';
    // wait ~2.2s then reveal pink theme + music prompt
    setTimeout(()=> {
      revealPinkAndAskMusic();
    }, 2200);
  }

  // Light button handler
  lightBtn.addEventListener('click', ()=>{
    lightBtn.disabled = true;
    lightBtn.textContent = 'Lit 🔥';
    lightCandle();
  });

  // show sparkle overlay for transitions
  function showSparkles(duration=700){
    // create a few sparkles then fade
    sparkleOverlay.style.opacity = 1;
    // create random dots
    for(let i=0;i<20;i++){
      const d = document.createElement('div');
      d.className = 'sparkle-dot';
      d.style.left = (10 + Math.random()*80) + '%';
      d.style.top = (10 + Math.random()*80) + '%';
      d.style.width = (6 + Math.random()*10) + 'px';
      d.style.height = d.style.width;
      d.style.opacity = (0.6 + Math.random()*0.4);
      sparkleOverlay.appendChild(d);
      // animate scale/opacity with CSS
      d.animate([
        { transform: 'scale(0.6)', opacity: 0.9 },
        { transform: 'scale(1.6)', opacity: 0 }
      ], { duration: duration + Math.random()*200, easing:'ease-out' });
      setTimeout(()=> d.remove(), duration+300);
    }
    setTimeout(()=> sparkleOverlay.style.opacity = 0, duration);
  }

  // reveal pink theme and ask user to start music
  function revealPinkAndAskMusic(){
    // transition body background
    document.body.style.background = 'linear-gradient(180deg,var(--pink-1),var(--pink-2))';
    // hide candle stage
    candleStage.style.opacity = 0;
    candleStage.style.pointerEvents = 'none';
    setTimeout(()=> candleStage.style.display = 'none', 600);
    // show sparkles
    showSparkles(600);
    // show music prompt overlay (simple modal at top of main)
    // create music prompt
    const prompt = document.createElement('div');
    prompt.style.position = 'fixed';
    prompt.style.left = '50%';
    prompt.style.top = '16%';
    prompt.style.transform = 'translateX(-50%)';
    prompt.style.zIndex = 92;
    prompt.style.padding = '16px 18px';
    prompt.style.borderRadius = '12px';
    prompt.style.background = 'linear-gradient(180deg,#fff,#fff7fb)';
    prompt.style.color = '#4a0310';
    prompt.style.boxShadow = '0 10px 28px rgba(0,0,0,0.08)';
    prompt.innerHTML = '<div style="font-weight:700;margin-bottom:6px">Please turn up your volume 🔊</div><div style="font-size:14px;color:#6a2631;margin-bottom:10px">Want to start the music?</div>';
    const btn = document.createElement('button');
    btn.className = 'btn';
    btn.textContent = 'Music — Turn Up Volume 🎶';
    btn.onclick = ()=> {
      // start music and remove prompt
      startMusic();
      btn.disabled = true;
      btn.textContent = 'Playing 🎶';
      setTimeout(()=> prompt.remove(), 600);
    };
    prompt.appendChild(btn);
    document.body.appendChild(prompt);

    // reveal main content (after tiny delay)
    setTimeout(()=>{
      main.style.display = 'block';
      setTimeout(()=> main.style.opacity = 1, 30);
      main.setAttribute('aria-hidden','false');
      // show nav icons
      document.getElementById('navIcons').style.display = 'flex';
      document.getElementById('navIcons').setAttribute('aria-hidden','false');
    }, 450);
  }

  // function to start the YouTube audio by setting iframe src (user gesture required)
  function startMusic(){
    // set hidden iframe src to the embed URL with autoplay & playlist for loop
    ytPlayer.src = 'https://www.youtube.com/embed/' + YT_ID + '?autoplay=1&loop=1&playlist=' + YT_ID + '&controls=0&rel=0&iv_load_policy=3';
    // small confetti burst (calm)
    try {
      const s = document.createElement('script');
      s.src = 'https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js';
      s.onload = function(){ confetti({ particleCount: 40, spread: 50, origin: { y: 0.6 } }); };
      document.body.appendChild(s);
    } catch(e){}
  }

  // nav icons click to scroll
  document.querySelectorAll('.nav-icon').forEach(el=>{
    el.addEventListener('click', ()=>{
      const id = el.getAttribute('data-target');
      const target = document.getElementById(id);
      if(target) target.scrollIntoView({behavior:'smooth', block:'center'});
    });
  });

  // small accessibility: hide sparkles overlay clicks
  sparkleOverlay.addEventListener('click',(e)=> e.stopPropagation());

  // ensure touch/click works on mobile quickly
  document.addEventListener('touchstart', ()=>{}, {passive:true});
</script>
</body>
</html>
  
