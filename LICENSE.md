[index.html](https://github.com/user-attachments/files/34584209/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Film 84C | Video & Photography · Trøndelag</title>
<meta name="description" content="Film 84C – student business company producing event films, commercials, reels and photography in Trøndelag.">

<style>
/* =====================================================
   1. DESIGN SETTINGS – change colours, fonts, sizes here
   ===================================================== */
:root {
  --bg:      #f5efdc;   /* page background */
  --page-bg: #dcd9cf;   /* page background, slightly darker than the logo */
  --card:    #e7e4da;   /* logo-matched light sections and cards */
  --text:    #630606;   /* main text */
  --muted:   #6b0505;   /* softer text */
  --accent:  #6d0606;   /* buttons, links, highlights */
  --dark:    #1a0b0b;   /* dark sections (showreel, footer) */
  --line:    #d6c9a5;   /* thin borders */

  --font-body:    system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
  --font-heading: system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
  /* Want a custom Google Font? Add a <link> in <head> and put its name above. */

  --radius: 10px;
  --section-pad: 80px 10%;
}

/* =====================================================
   2. BASE STYLES
   ===================================================== */
* { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body { font-family: var(--font-body); background: var(--page-bg); color: var(--text); line-height: 1.6; }
a { color: var(--accent); text-decoration: none; }
img, video { max-width: 100%; display: block; }
section { padding: var(--section-pad); }
h1, h2, h3 { font-family: var(--font-heading); line-height: 1.2; }
h2 { font-size: 2rem; margin-bottom: 12px; }
h2 span { color: var(--accent); }
.section-intro { color: var(--muted); max-width: 620px; margin-bottom: 36px; }

/* =====================================================
   3. NAVBAR
   ===================================================== */
nav {
  position: fixed; top: 0; width: 100%; z-index: 10;
  display: flex; justify-content: space-between; align-items: center;
  padding: 18px 10%;
  background: rgba(220, 217, 207, 0.94);
  backdrop-filter: blur(8px);
  border-bottom: 1px solid var(--line);
}
nav .logo {
  display: flex; align-items: center; justify-content: center;
  height: 80px;
}
nav .logo img {
  display: block; height: 80px; width: 80px;
  max-width: 200px;
  object-fit: cover;
  background: transparent;
  filter: none;
  border-radius: 50%;
  border: none;
}
nav ul { display: flex; gap: 24px; list-style: none; }
nav ul a { color: var(--text); font-weight: 500; }
nav ul a:hover { color: var(--accent); }

/* =====================================================
   4. BUTTONS
   ===================================================== */
.btn {
  display: inline-block; padding: 12px 26px; width: fit-content;
  border: 2px solid var(--accent); border-radius: 6px;
  color: var(--accent); font-weight: 600; background: transparent;
  cursor: pointer; font-family: inherit; font-size: 1rem; transition: 0.2s;
}
.btn:hover { background: var(--accent); color: var(--bg); }
.btn.solid { background: var(--accent); color: var(--bg); }
.btn.solid:hover { opacity: 0.85; }

/* =====================================================
   5. HERO (top of page)
   ===================================================== */
.hero {
  position: relative; min-height: 100vh; overflow: hidden;
  display: flex; flex-direction: column; justify-content: center;
  padding: 100px 10% 60px;
  background: var(--dark); color: var(--bg);
}
/* Background video – see HTML below. Dark overlay keeps text readable */
.hero-video {
  position: absolute; inset: 0; width: 100%; height: 100%;
  object-fit: cover; opacity: 0.45; z-index: 0;
}
.hero::after {
  content: ""; position: absolute; inset: 0; z-index: 1;
  background: linear-gradient(180deg, rgba(26,11,11,.35), rgba(26,11,11,.85));
}
.hero > *:not(video) { position: relative; z-index: 2; }
.hero .greeting { color: #f5b5b5; letter-spacing: 3px; text-transform: uppercase; font-size: .9rem; }
.hero h1 { font-size: clamp(3rem, 9vw, 6.5rem); margin: 10px 0; color: var(--bg); letter-spacing: -2px; }
.hero h1 span { color: #ffffff; }
.hero p.role { font-size: 1.4rem; color: #f5d9d9; margin-bottom: 14px; }
.hero p.desc { max-width: 560px; margin-bottom: 36px; color: #e8cfcf; }
.hero .btn { border-color: var(--bg); color: var(--bg); }
.hero .btn:hover { background: var(--bg); color: var(--accent); }
.hero .btn.solid { background: #420101; border-color: #710909; }

/* =====================================================
   6. VIDEO GRIDS
   ===================================================== */
.video-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 24px; }
.reel-grid  { display: grid; grid-template-columns: repeat(auto-fit, minmax(210px, 1fr)); gap: 20px; }

#videos .video-grid {
  max-width: 760px;
  margin: 0 auto;
}

.video-card {
  background: var(--card); border: 1px solid var(--line);
  border-radius: var(--radius); overflow: hidden; transition: transform .2s, border-color .2s;
}
.video-card:hover { transform: translateY(-6px); border-color: var(--accent); }
.video-card .frame { aspect-ratio: 16 / 9; background: linear-gradient(135deg, #740404, #7f1d1d); }
.reel-grid .video-card .frame { aspect-ratio: 9 / 16; }  /* vertical reels */
.video-card video, .video-card iframe { width: 100%; height: 100%; border: 0; object-fit: cover; }
.video-card .info { padding: 16px 20px 20px; }
.video-card h3 { font-size: 1.1rem; margin-bottom: 4px; }
.video-card p  { color: var(--muted); font-size: .92rem; }

/* =====================================================
   7. PHOTO GALLERY (click a photo to enlarge)
   ===================================================== */
.photo-grid { columns: 3 260px; column-gap: 16px; }
.photo-grid figure {
  break-inside: avoid; margin-bottom: 16px; cursor: zoom-in;
  border-radius: var(--radius); overflow: hidden;
  background: linear-gradient(135deg, #770303, #7f1d1d); min-height: 160px;
  border: 1px solid var(--line); transition: transform .2s;
}
.photo-grid figure:hover { transform: scale(1.02); }
.photo-grid img { width: 100%; height: auto; }

.lightbox {
  position: fixed; inset: 0; background: rgba(0,0,0,.92); z-index: 100;
  display: none; align-items: center; justify-content: center; padding: 20px; cursor: zoom-out;
}
.lightbox.open { display: flex; }
.lightbox img { max-height: 92vh; max-width: 94vw; border-radius: 6px; }

/* =====================================================
   8. SERVICES + ABOUT
   ===================================================== */
.services-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 20px; }
.service { background: var(--card); border: 1px solid var(--line); border-radius: var(--radius); padding: 26px; }
.service .icon { font-size: 2rem; margin-bottom: 10px; }
.service h3 { margin-bottom: 6px; }
.service p { color: var(--muted); font-size: .95rem; }

.about-grid { display: grid; grid-template-columns: 2fr 1fr; gap: 40px; align-items: start; }
.about-grid p { color: var(--muted); margin-bottom: 16px; }
.skills { display: flex; flex-wrap: wrap; gap: 10px; }
.skills span { background: var(--card); padding: 6px 14px; border-radius: 999px; font-size: .9rem; border: 1px solid var(--line); }

/* =====================================================
   9. CONTACT + FOOTER
   ===================================================== */
.contact { text-align: center; }
.contact p { color: var(--muted); max-width: 560px; margin: 0 auto 24px; }
form { max-width: 560px; margin: 0 auto; display: grid; gap: 14px; }
input, textarea {
  width: 100%; padding: 12px 14px; background: var(--card);
  border: 1px solid var(--line); border-radius: 6px; color: var(--text); font: inherit;
}
input::placeholder, textarea::placeholder { color: var(--muted); opacity: .7; }
input:focus, textarea:focus { outline: none; border-color: var(--accent); }
textarea { min-height: 130px; resize: vertical; }
footer { text-align: center; padding: 30px; color: var(--muted); font-size: .9rem; border-top: 1px solid var(--line); }

/* =====================================================
   10. MOBILE
   ===================================================== */
@media (max-width: 768px) {
  :root { --section-pad: 60px 6%; }
  nav { padding: 14px 6%; }
  nav ul { gap: 14px; font-size: .9rem; }
  .hero { padding-left: 6%; padding-right: 6%; }
  .about-grid { grid-template-columns: 1fr; }
}

/* =====================================================
   11. ✏️ YOUR OWN CSS – write your custom styles below.
   Anything here overrides the styles above.
   ===================================================== */


</style>
</head>

<body>

<!-- ================= NAVBAR ================= -->
<nav>
  <div class="logo">
    <img src="media/logo/2.png" alt="Film 84C logo">
  </div>
  <ul>
    <li><a href="#videos">Videos</a></li>
    <li><a href="#reels">Reels</a></li>
    <li><a href="#photos">Photos</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- ================= HERO =================
  BACKGROUND VIDEO: put a short, silent, compressed clip (5–15 s, under ~10 MB)
  in media/videos/hero.mp4. If the file doesn't exist, the dark background shows.
-->
<header class="hero">
  <video class="hero-video" autoplay muted loop playsinline>
    <source src="media/videos/first.mp4" type="video/mp4">
    <source src="media/videos/first.mov" type="video/quicktime">
  </video>
  <p class="greeting">🎬 Student business · Trøndelag</p>
  <h1>FILM <span>84C</span></h1>
  <p class="role">Video & Photography Production</p>
  <p class="desc">We capture events across Trøndelag and create commercials, reels and short videos that make people stop scrolling.</p>
  <div style="display:flex; gap:16px; flex-wrap:wrap;">
    <a class="btn solid" href="#videos">Watch Our Work</a>
    <a class="btn" href="#contact">Book Us</a>
  </div>
</header>

<!-- ================= VIDEOS =================
  HOW TO ADD A VIDEO – copy one <article class="video-card"> block.

  OPTION A (video file you uploaded):
    <video controls preload="metadata" poster="media/thumbs/my-thumb.jpg">
      <source src="media/videos/my-video.mp4" type="video/mp4">
    </video>

  OPTION B (YouTube – best for big files):
    <iframe src="https://www.youtube.com/embed/VIDEO_ID" allowfullscreen loading="lazy"></iframe>
    (VIDEO_ID is the part after "v=" in the YouTube link)

  OPTION C (Vimeo):
    <iframe src="https://player.vimeo.com/video/VIDEO_ID" allowfullscreen loading="lazy"></iframe>
-->
<section id="videos">
  <h2>Featured <span>Videos</span></h2>
  <p class="section-intro">Event films, commercials and short productions from across Trøndelag.</p>

  <div class="video-grid">

    <article class="video-card">
      <div class="frame">
        <video autoplay muted loop playsinline preload="metadata" poster="media/thumbs/trust-fest.jpg">
          <source src="media/videos/Trust fest.mov" type="video/quicktime">
        </video>
      </div>
      <div class="info">
        <h3>Tillitsfestival</h3>
        <p>Organized by Forandringshuset Levanger & Nord University.</p>
      </div>
    </article>

  </div>
</section>

<!-- ================= REELS (vertical 9:16 videos) ================= -->
<section id="reels" style="background: var(--card);">
  <h2>Reels & <span>Shorts</span></h2>
  <p class="section-intro">Vertical videos made for Instagram, TikTok and YouTube Shorts.</p>

  <div class="reel-grid">
    <article class="video-card">
      <div class="frame">
        <video autoplay muted loop playsinline preload="metadata" poster="media/thumbs/reel1.jpg">
          <source src="media/videos/reel1.mp4" type="video/mp4">
        </video>
      </div>
    </article>

    <article class="video-card">
      <div class="frame">
        <video autoplay muted loop playsinline preload="metadata" poster="media/thumbs/reel2.jpg">
          <source src="media/videos/reel2.mp4" type="video/mp4">
        </video>
      </div>
    </article>

    <article class="video-card">
      <div class="frame">
        <video autoplay muted loop playsinline preload="metadata" poster="media/thumbs/reel3.jpg">
          <source src="media/videos/reel3.mp4" type="video/mp4">
        </video>
      </div>
    </article>
  </div>
</section>

<!-- ================= PHOTOS =================
  HOW TO ADD A PHOTO – copy one <figure> line and change the file name.
  Put photos in media/photos/ (JPG, max ~500 KB–1 MB each for fast loading).
-->
<section id="photos">
  <h2>Photo <span>Gallery</span></h2>
  <p class="section-intro">Moments we've captured. Click a photo to enlarge it.</p>

  <div class="photo-grid">
    <figure><img src="media/photos/Tea%20ceremony/photo1.jpg" alt="Photo 1" loading="lazy" onerror="this.style.display='none'"></figure>
    <figure><img src="media/photos/Tea%20ceremony/photo2.jpg" alt="Photo 2" loading="lazy" onerror="this.style.display='none'"></figure>
    <figure><img src="media/photos/Tea%20ceremony/photo3.jpg" alt="Photo 3" loading="lazy" onerror="this.style.display='none'"></figure>
    <figure><img src="media/photos/Tea%20ceremony/photo4.jpg" alt="Photo 4" loading="lazy" onerror="this.style.display='none'"></figure>
    <figure><img src="media/photos/Trust%20festival/photo5.jpg" alt="Photo 5" loading="lazy" onerror="this.style.display='none'"></figure>
    <figure><img src="media/photos/Trust%20festival/photo6.jpg" alt="Photo 6" loading="lazy" onerror="this.style.display='none'"></figure>
    <figure><img src="media/photos/Trust%20festival/photo7.jpg" alt="Photo 7" loading="lazy" onerror="this.style.display='none'"></figure>
    <figure><img src="media/photos/Trust%20festival/photo8.jpg" alt="Photo 8" loading="lazy" onerror="this.style.display='none'"></figure>
    <figure><img src="media/photos/Trust%20festival/photo9.jpg" alt="Photo 9" loading="lazy" onerror="this.style.display='none'"></figure>
  </div>
</section>

<div class="lightbox" id="lightbox"><img src="" alt=""></div>

<!-- ================= SERVICES ================= -->
<section id="services" style="background: var(--card);">
  <h2>What We <span>Do</span></h2>
  <div class="services-grid">
    <div class="service"><div class="icon">🎉</div><h3>Event Coverage</h3><p>Photo and video of concerts, festivals, sports, school and company events in Trøndelag.</p></div>
    <div class="service"><div class="icon">📺</div><h3>Commercials</h3><p>Ads for local businesses – from idea and script to the finished edit.</p></div>
    <div class="service"><div class="icon">📱</div><h3>Reels & Short Videos</h3><p>Vertical, fast-paced content for social media.</p></div>
    <div class="service"><div class="icon">📸</div><h3>Photography</h3><p>Portraits, product photos and event photography.</p></div>
  </div>
</section>

<!-- ================= ABOUT ================= -->
<section id="about">
  <h2>About <span>Us</span></h2>
  <div class="about-grid">
    <div>
      <p>We’re a team of film and TV production students based in Trøndelag, Norway, with a passion for storytelling through video. From Reels to commercials, we bring your ideas to life with creativity, care, and a personal touch.</p>
    </div>
    <div>
      <h3 style="margin-bottom:14px;">Tools & Skills</h3>
      <div class="skills">
        <span>Videography</span><span>Photography</span><span>Editing</span><span>Colour Grading</span>
        <span>Reels</span><span>Storytelling</span>
      </div>
    </div>
  </div>
</section>

<!-- ================= CONTACT =================
  Change you@example.com to your real email address.
-->
<section id="contact" class="contact" style="background: var(--card);">
  <h2>Book <span>Film 84C</span></h2>
  <p>Have an event or a project in mind? Send us a message and we'll get back to you soon.</p>
  <form action="mailto:film84c@gmail.com" method="post" enctype="text/plain">
    <input type="text" name="name" placeholder="Your name" required>
    <input type="email" name="email" placeholder="Your email" required>
    <textarea name="message" placeholder="Tell us about your event or project" required></textarea>
    <button class="btn solid" type="submit" style="justify-self:center;">Send Message</button>
  </form>
  <p style="margin-top:24px;">
    <a href="https://www.instagram.com/film.84c/" target="_blank" rel="noreferrer">Instagram</a>
    · <a href="mailto:film84c@gmail.com">film84c@gmail.com</a>
  </p>
</section>

<footer>
  <p>© 2026 Film 84C · Video & Photography · Trøndelag</p>
</footer>

<!-- ================= SCRIPTS ================= -->
<script>
  // Photo lightbox
  const lb = document.getElementById('lightbox');
  const lbImg = lb.querySelector('img');
  document.querySelectorAll('.photo-grid img').forEach(img => {
    img.addEventListener('click', () => { lbImg.src = img.src; lb.classList.add('open'); });
  });
  lb.addEventListener('click', () => lb.classList.remove('open'));
  document.addEventListener('keydown', e => { if (e.key === 'Escape') lb.classList.remove('open'); });

  // Pause other videos when one starts playing
  document.querySelectorAll('video[controls]').forEach(v => {
    v.addEventListener('play', () => {
      document.querySelectorAll('video[controls]').forEach(o => { if (o !== v) o.pause(); });
    });
  });

  // ✏️ YOUR OWN JAVASCRIPT goes below

</script>
</body>
</html>
