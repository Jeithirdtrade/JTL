<html lang="sw">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="JTL Zanzibar - Kampuni ya biashara na huduma mbalimbali Zanzibar. Ubora, uaminifu na ufanisi.">
<meta name="keywords" content="JTL Zanzibar, biashara Zanzibar, huduma Zanzibar, JTL, Tanzania">
<meta name="author" content="JTL Zanzibar">
<meta name="theme-color" content="#123b5d">
<title>JTL Zanzibar | Biashara & Ushirikiano</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<style>
/* ===== RESET ===== */
* { margin: 0; padding: 0; box-sizing: border-box; }
html { scroll-behavior: smooth; -webkit-text-size-adjust: 100%; }
body {
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    background: #f5f7fa; color: #1e293b; line-height: 1.6;
    width: 100%; min-height: 100%; overflow-x: hidden;
}
img { width: 100%; display: block; }
a { text-decoration: none; color: inherit; }
button, input, textarea, select { font-family: inherit; }

:root {
    --blue: #123b5d; --blue-light: #1f6b9c;
    --red: #c0392b; --red-light: #e74c3c;
    --green: #20a05a; --green-light: #2ecc71;
    --yellow: #f1c40f; --yellow-light: #ffe66d;
    --purple: #743b91; --purple-light: #9b59b6;
    --dark: #101820; --dark-2: #172331;
    --white: #ffffff; --light: #f5f7fa; --gray: #64748b; --border: #e2e8f0;
    --shadow: 0 10px 35px rgba(15, 23, 42, 0.10);
    --shadow-lg: 0 20px 60px rgba(15, 23, 42, 0.16);
    --radius: 18px; --transition: 0.3s ease;
    --gutter: 56px; --header-h: 78px;
}

.container { width: 100%; max-width: none; margin: 0 auto; padding-left: var(--gutter); padding-right: var(--gutter); }

::-webkit-scrollbar { width: 8px; height: 8px; }
::-webkit-scrollbar-track { background: #edf1f5; }
::-webkit-scrollbar-thumb { background: var(--blue); border-radius: 20px; }

section[id] { scroll-margin-top: calc(var(--header-h) + 12px); }

/* ===== PRELOADER ===== */
.preloader {
    position: fixed; inset: 0; z-index: 99999;
    display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 22px;
    background: linear-gradient(135deg, #123b5d 0%, #743b91 100%);
    transition: opacity 0.6s ease, visibility 0.6s ease;
}
.preloader.hide { opacity: 0; visibility: hidden; }
.preloader-logo {
    width: 100px; height: 100px; padding: 4px; border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    background: conic-gradient(from 0deg, var(--yellow) 0deg, var(--green-light) 90deg, var(--purple-light) 180deg, var(--red-light) 270deg, var(--yellow) 360deg);
    box-shadow: 0 8px 30px rgba(241,196,15,0.4);
    animation: logoCycle 3s linear infinite;
    overflow: hidden;
}
.preloader-logo img {
    width: 100%; height: 100%; object-fit: contain; border-radius: 50%;
    background: white; padding: 5px;
    animation: logoCounter 3s linear infinite;
}
.preloader-text { color: white; font-size: 1.3rem; font-weight: 900; letter-spacing: 1.5px; }
.preloader-bar { width: 220px; height: 4px; background: rgba(255,255,255,0.18); border-radius: 10px; overflow: hidden; }
.preloader-bar-fill { height: 100%; width: 0; background: linear-gradient(90deg, var(--yellow), var(--green-light)); animation: loadBar 1.1s ease forwards; }

@keyframes loadBar { to { width: 100%; } }

/* ===== SCROLL PROGRESS ===== */
.scroll-progress {
    position: fixed; top: 0; left: 0; height: 3px; width: 0;
    background: linear-gradient(90deg, var(--yellow), var(--red), var(--purple), var(--green-light));
    z-index: 10001; transition: width 0.08s linear;
}

/* ===== HEADER ===== */
header {
    position: fixed; top: 0; left: 0; width: 100%; z-index: 9999;
    background: rgba(18, 59, 93, 0.96);
    backdrop-filter: blur(14px); -webkit-backdrop-filter: blur(14px);
    box-shadow: 0 5px 25px rgba(0,0,0,0.15);
}
.navbar { min-height: var(--header-h); display: flex; align-items: center; justify-content: space-between; gap: 20px; }
.logo { display: flex; align-items: center; gap: 12px; color: white; font-size: 1.25rem; font-weight: 900; letter-spacing: 0.4px; flex-shrink: 0; }
.logo-name { white-space: nowrap; }
.logo-icon {
    width: 50px; height: 50px; padding: 3px;
    display: flex; align-items: center; justify-content: center; border-radius: 50%;
    background: conic-gradient(from 0deg, var(--yellow) 0deg, var(--green-light) 90deg, var(--purple-light) 180deg, var(--red-light) 270deg, var(--yellow) 360deg);
    box-shadow: 0 0 0 2px rgba(255,255,255,0.10), 0 6px 22px rgba(241,196,15,0.35);
    flex-shrink: 0; animation: logoCycle 5s linear infinite;
    transition: box-shadow var(--transition);
    overflow: hidden;
}
.logo-icon img {
    width: 100%; height: 100%; object-fit: contain; border-radius: 50%;
    background: white; padding: 3px;
    animation: logoCounter 5s linear infinite;
}
.logo:hover .logo-icon { box-shadow: 0 0 0 3px rgba(255,255,255,0.18), 0 10px 32px rgba(241,196,15,0.60); }
.logo span { color: var(--yellow); }
@keyframes logoCycle { from { transform: rotate(0); } to { transform: rotate(360deg); } }
@keyframes logoCounter { from { transform: rotate(0); } to { transform: rotate(-360deg); } }
@media (prefers-reduced-motion: reduce) { .logo-icon, .logo-icon img, .preloader-logo, .preloader-logo img { animation: none; } }

.nav-links { list-style: none; display: flex; align-items: center; gap: 6px; }
.nav-links a { display: block; color: rgba(255,255,255,0.88); font-size: 0.92rem; font-weight: 700; padding: 10px 15px; border-radius: 10px; white-space: nowrap; transition: var(--transition); }
.nav-links a:hover, .nav-links a.active { background: var(--yellow); color: var(--dark); }
.nav-right { display: flex; align-items: center; gap: 10px; flex-shrink: 0; }
.lang-toggle {
    display: inline-flex; align-items: center; justify-content: center; gap: 7px;
    height: 42px; padding: 0 16px; border-radius: 50px;
    border: 1px solid rgba(255,255,255,0.28); background: rgba(255,255,255,0.10);
    color: white; font-size: 0.8rem; font-weight: 800; letter-spacing: 0.5px; cursor: pointer; transition: var(--transition);
}
.lang-toggle i { font-size: 0.85rem; }
.lang-toggle:hover { background: var(--yellow); border-color: var(--yellow); color: var(--dark); transform: translateY(-2px); }
.menu-toggle {
    display: none; align-items: center; justify-content: center;
    width: 44px; height: 44px; border-radius: 12px;
    border: 1px solid rgba(255,255,255,0.28); background: rgba(255,255,255,0.10);
    color: white; font-size: 1rem; cursor: pointer; transition: var(--transition);
}
.menu-toggle:hover, .menu-toggle[aria-expanded="true"] { background: var(--yellow); border-color: var(--yellow); color: var(--dark); }

/* ===== HERO ===== */
.hero { min-height: 100vh; padding: 150px 0 90px; position: relative; overflow: hidden; display: flex; align-items: center; background: linear-gradient(120deg, #123b5d 0%, #263b75 45%, #743b91 72%, #c0392b 100%); }
@supports (min-height: 100svh) { .hero { min-height: 100svh; } }
.hero::before { content: ""; position: absolute; inset: 0; background: radial-gradient(circle at 10% 20%, rgba(241,196,15,0.16), transparent 35%), radial-gradient(circle at 90% 80%, rgba(46,204,113,0.14), transparent 35%); }
.hero > .container { width: 100%; }
.hero-grid { position: relative; z-index: 2; display: grid; grid-template-columns: 1.05fr 0.95fr; align-items: center; gap: 70px; }
.hero-content { color: white; }
.hero-badge { display: inline-flex; align-items: center; gap: 8px; padding: 8px 15px; margin-bottom: 22px; border-radius: 50px; background: rgba(255,255,255,0.10); border: 1px solid rgba(255,255,255,0.18); backdrop-filter: blur(8px); font-size: 0.82rem; font-weight: 700; }
.hero h1 { font-size: clamp(2.4rem, 4.6vw, 4.6rem); line-height: 1.05; font-weight: 900; margin-bottom: 25px; letter-spacing: -1.5px; }
.hero h1 .yellow { color: var(--yellow); }
.hero h1 .green { color: var(--green-light); }
.hero h1 .red { color: var(--red-light); }
.hero-description { max-width: 720px; color: rgba(255,255,255,0.84); font-size: clamp(0.95rem, 1.05vw, 1.08rem); line-height: 1.8; margin-bottom: 30px; }
.hero-buttons { display: flex; flex-wrap: wrap; gap: 14px; margin-bottom: 40px; }
.btn { min-height: 52px; display: inline-flex; align-items: center; justify-content: center; gap: 9px; padding: 13px 24px; border-radius: 50px; font-size: 0.9rem; font-weight: 800; border: 0; cursor: pointer; text-align: center; transition: var(--transition); }
.btn:hover { transform: translateY(-3px); }
.btn-primary { background: var(--yellow); color: var(--dark); box-shadow: 0 8px 25px rgba(241,196,15,0.28); }
.btn-secondary { background: rgba(255,255,255,0.10); color: white; border: 1px solid rgba(255,255,255,0.25); }
.btn-secondary:hover { background: rgba(255,255,255,0.18); }
.btn-drive { background: var(--green); color: white; box-shadow: 0 8px 25px rgba(32,160,90,0.35); }
.btn-drive:hover { background: var(--green-light); box-shadow: 0 12px 30px rgba(32,160,90,0.45); }

.hero-stats { display: flex; gap: 45px; }
.stat-number { display: block; color: var(--yellow); font-size: 1.9rem; font-weight: 900; }
.stat-label { display: block; color: rgba(255,255,255,0.65); font-size: 0.75rem; text-transform: uppercase; letter-spacing: 0.7px; }

.hero-visual { position: relative; }
.hero-card { padding: 15px; background: rgba(255,255,255,0.09); border: 1px solid rgba(255,255,255,0.16); border-radius: 24px; backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px); box-shadow: 0 30px 80px rgba(0,0,0,0.25); }
.hero-card img { height: 52vh; min-height: 420px; max-height: 620px; object-fit: cover; border-radius: 16px; }
.hero-tags { display: flex; flex-wrap: wrap; justify-content: center; gap: 8px; padding: 15px 5px 3px; }
.hero-tags span { display: inline-flex; align-items: center; gap: 6px; padding: 6px 12px; border-radius: 30px; font-size: 0.72rem; font-weight: 800; }
.hero-tags i { font-size: 0.72rem; }
.tag-yellow { background: var(--yellow); color: var(--dark); }
.tag-green { background: var(--green); color: white; }
.tag-purple { background: var(--purple); color: white; }

/* ===== TRUST STRIP ===== */
.trust-strip { background: white; padding: 35px 0; border-bottom: 1px solid var(--border); }
.trust-label { text-align: center; color: var(--gray); font-size: 0.75rem; text-transform: uppercase; letter-spacing: 1.5px; margin-bottom: 22px; font-weight: 800; }
.trust-logos { display: flex; justify-content: center; align-items: center; flex-wrap: wrap; gap: 45px; }
.trust-logo { display: flex; align-items: center; gap: 10px; color: var(--gray); font-weight: 800; font-size: 1rem; opacity: 0.65; transition: 0.3s; }
.trust-logo:hover { opacity: 1; color: var(--blue); transform: translateY(-2px); }
.trust-logo i { font-size: 1.5rem; color: var(--blue); }

/* ===== SECTIONS ===== */
section { padding: 100px 0; }
.section-heading { max-width: 760px; margin: 0 auto 55px; text-align: center; }
.section-heading h2 { font-size: clamp(1.9rem, 3vw, 2.9rem); color: var(--dark); font-weight: 900; margin-bottom: 15px; }
.section-heading h2 span { color: var(--purple); }
.section-heading p { color: var(--gray); font-size: 1rem; }
.section-line { width: 65px; height: 4px; margin: 15px auto 0; border-radius: 10px; background: linear-gradient(90deg, var(--yellow), var(--red), var(--purple)); }

/* ===== ABOUT ===== */
.about { background: white; }
.about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 70px; align-items: center; }
.about-image { position: relative; }
.about-image img { height: 520px; object-fit: cover; border-radius: 22px; box-shadow: var(--shadow-lg); }
.about-image::after { content: ""; position: absolute; width: 120px; height: 120px; right: -20px; bottom: -20px; background: var(--yellow); border-radius: 25px; z-index: -1; }
.about-content h3 { color: var(--blue); font-size: clamp(1.5rem, 2vw, 2rem); margin-bottom: 15px; }
.about-content h3 span { color: var(--purple); }
.about-content p { color: #52606d; margin-bottom: 15px; line-height: 1.8; }
.features { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-top: 25px; }
.feature { display: flex; align-items: center; gap: 10px; padding: 13px; border-radius: 12px; background: var(--light); font-weight: 700; font-size: 0.88rem; transition: var(--transition); }
.feature:hover { transform: translateY(-3px); background: #eef4f8; }
.feature i { color: var(--blue); font-size: 1.1rem; flex-shrink: 0; }

/* ===== SERVICES ===== */
.services { background: var(--light); }
.services-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; }
.service-card { background: white; padding: 34px 26px; border-radius: var(--radius); box-shadow: var(--shadow); border-top: 4px solid var(--blue); transition: var(--transition); text-align: center; }
.service-card:hover { transform: translateY(-8px); box-shadow: var(--shadow-lg); }
.service-card:nth-child(2) { border-top-color: var(--red); }
.service-card:nth-child(3) { border-top-color: var(--green); }
.service-card:nth-child(4) { border-top-color: var(--purple); }
.service-card:nth-child(5) { border-top-color: var(--yellow); }
.service-card:nth-child(6) { border-top-color: var(--red); }
.service-icon { width: 70px; height: 70px; display: flex; align-items: center; justify-content: center; margin: 0 auto 18px; border-radius: 20px; background: rgba(18,59,93,0.08); color: var(--blue); font-size: 1.8rem; transition: var(--transition); }
.service-card:hover .service-icon { transform: scale(1.1) rotate(-8deg); background: var(--blue); color: white; }
.service-card h3 { font-size: 1.08rem; color: var(--dark); margin-bottom: 10px; }
.service-card p { color: var(--gray); font-size: 0.9rem; line-height: 1.7; }

/* ===== BOOK ===== */
.book { background: white; position: relative; overflow: hidden; }
.book::before { content: ""; position: absolute; width: 280px; height: 280px; border-radius: 50%; background: radial-gradient(circle, rgba(116,59,145,0.10), transparent 70%); top: -60px; left: -60px; }
.book::after { content: ""; position: absolute; width: 240px; height: 240px; border-radius: 50%; background: radial-gradient(circle, rgba(241,196,15,0.14), transparent 70%); bottom: -60px; right: -60px; }
.book > .container { position: relative; z-index: 2; }
.book-grid { display: grid; grid-template-columns: 0.85fr 1.15fr; gap: 60px; align-items: center; }
.book-cover { position: relative; text-align: center; }
.book-cover img {
    width: 100%; max-width: 360px; margin: 0 auto;
    border-radius: 14px; box-shadow: 0 25px 60px rgba(15,23,42,0.28), 0 8px 20px rgba(15,23,42,0.15);
    transition: transform 0.4s ease, box-shadow 0.4s ease;
    object-fit: cover;
}
.book-cover img:hover { transform: translateY(-10px) rotate(-1.5deg); box-shadow: 0 35px 80px rgba(15,23,42,0.35), 0 12px 25px rgba(15,23,42,0.18); }
.book-cover::before {
    content: ""; position: absolute; width: 90px; height: 90px; border-radius: 20px;
    background: linear-gradient(135deg, var(--yellow), var(--red));
    top: -18px; left: 50%; transform: translateX(-50%) rotate(-8deg);
    z-index: -1; opacity: 0.85;
}
.book-content h3 { color: var(--blue); font-size: clamp(1.5rem, 2vw, 2rem); margin-bottom: 15px; }
.book-content h3 span { color: var(--purple); }
.book-content p { color: #52606d; margin-bottom: 15px; line-height: 1.8; }
.book-buttons { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 28px; }

/* ===== MORE BOOKS GRID ===== */
.books-more { margin-top: 80px; position: relative; }
.books-more::before {
    content: ""; display: block; width: 90px; height: 3px; margin: 0 auto 25px;
    background: linear-gradient(90deg, var(--yellow), var(--red), var(--purple));
    border-radius: 10px;
}
.books-more-title { text-align: center; font-size: clamp(1.5rem, 2.2vw, 2rem); color: var(--blue); margin-bottom: 8px; font-weight: 900; }
.books-more-title span { color: var(--purple); }
.books-more-sub { text-align: center; color: var(--gray); margin-bottom: 35px; font-size: 0.94rem; max-width: 620px; margin-left: auto; margin-right: auto; }
.books-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(185px, 1fr));
    gap: 22px;
}
.book-card {
    background: white;
    border-radius: 16px;
    overflow: hidden;
    box-shadow: var(--shadow);
    transition: transform 0.35s ease, box-shadow 0.35s ease;
    display: flex;
    flex-direction: column;
    border: 1px solid var(--border);
}
.book-card:hover {
    transform: translateY(-7px);
    box-shadow: var(--shadow-lg);
    border-color: transparent;
}
.book-thumb {
    width: 100%;
    aspect-ratio: 3/4;
    background: linear-gradient(135deg, #eef4f8, #f5f7fa);
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}
.book-thumb::after {
    content: ""; position: absolute; inset: 0;
    background: linear-gradient(to top, rgba(0,0,0,0.10), transparent 40%);
    pointer-events: none;
}
.book-thumb img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform 0.4s ease;
}
.book-card:hover .book-thumb img { transform: scale(1.06); }
.book-thumb i { font-size: 3rem; color: var(--blue); }
.book-card-info {
    padding: 14px 12px 16px;
    text-align: center;
    display: flex;
    flex-direction: column;
    gap: 10px;
    align-items: center;
    flex: 1;
    justify-content: space-between;
}
.book-card-info h4 {
    font-size: 0.92rem;
    font-weight: 800;
    color: var(--dark);
    margin: 0;
    letter-spacing: 0.2px;
}
.book-card-info a {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    padding: 8px 16px;
    border-radius: 50px;
    background: var(--green);
    color: white;
    font-size: 0.78rem;
    font-weight: 800;
    transition: var(--transition);
    width: 100%;
}
.book-card-info a:hover {
    background: var(--green-light);
    transform: translateY(-2px);
    box-shadow: 0 6px 15px rgba(32,160,90,0.30);
}

/* ===== TESTIMONIALS ===== */
.testimonials { background: linear-gradient(135deg, #f5f7fa, #eef4f8); }
.testimonial-slider { position: relative; overflow: hidden; max-width: 900px; margin: 0 auto; }
.testimonial-track { display: flex; transition: transform 0.6s cubic-bezier(0.4,0,0.2,1); }
.testimonial-card { min-width: 100%; padding: 42px 38px; background: white; border-radius: 22px; box-shadow: var(--shadow-lg); text-align: center; }
.testimonial-card .stars { color: var(--yellow); font-size: 1.1rem; margin-bottom: 18px; display: flex; justify-content: center; gap: 4px; }
.testimonial-card .text { font-size: 1.05rem; font-style: italic; color: #334155; line-height: 1.8; margin-bottom: 25px; }
.testimonial-avatar { width: 65px; height: 65px; border-radius: 50%; background: linear-gradient(135deg, var(--blue), var(--purple)); color: white; display: flex; align-items: center; justify-content: center; font-weight: 900; font-size: 1.5rem; margin: 0 auto 12px; }
.testimonial-card:nth-child(2) .testimonial-avatar { background: linear-gradient(135deg, var(--red), var(--purple)); }
.testimonial-card:nth-child(3) .testimonial-avatar { background: linear-gradient(135deg, var(--green), var(--blue)); }
.testimonial-card:nth-child(4) .testimonial-avatar { background: linear-gradient(135deg, var(--purple), var(--red)); }
.testimonial-name { font-weight: 800; color: var(--dark); }
.testimonial-role { color: var(--gray); font-size: 0.85rem; }
.testimonial-dots { display: flex; justify-content: center; gap: 10px; margin-top: 28px; }
.testimonial-dot { width: 12px; height: 12px; border-radius: 50%; background: #cbd5e1; border: 0; cursor: pointer; transition: 0.3s; }
.testimonial-dot.active { background: var(--blue); width: 30px; border-radius: 6px; }

/* ===== CTA BANNER ===== */
.cta-banner { padding: 65px 0; background: linear-gradient(120deg, #123b5d, #743b91); position: relative; overflow: hidden; }
.cta-banner::before { content: ""; position: absolute; width: 300px; height: 300px; background: radial-gradient(circle, rgba(241,196,15,0.25), transparent 70%); top: -100px; right: -100px; }
.cta-banner::after { content: ""; position: absolute; width: 250px; height: 250px; background: radial-gradient(circle, rgba(46,204,113,0.18), transparent 70%); bottom: -80px; left: -80px; }
.cta-inner { display: flex; align-items: center; justify-content: space-between; gap: 40px; position: relative; z-index: 2; flex-wrap: wrap; }
.cta-inner h2 { color: white; font-size: clamp(1.5rem, 2.5vw, 2rem); margin-bottom: 8px; }
.cta-inner p { color: rgba(255,255,255,0.85); }

/* ===== FAQ ===== */
.faq { background: white; }
.faq-list { max-width: 800px; margin: 0 auto; }
.faq-item { border: 1px solid var(--border); border-radius: 14px; margin-bottom: 12px; overflow: hidden; transition: 0.3s; background: var(--light); }
.faq-item.open { border-color: var(--blue); background: white; box-shadow: var(--shadow); }
.faq-question { width: 100%; padding: 18px 22px; display: flex; justify-content: space-between; align-items: center; gap: 15px; background: none; border: 0; text-align: left; font-weight: 700; color: var(--dark); font-size: 0.95rem; cursor: pointer; }
.faq-question i { color: var(--blue); transition: 0.3s; flex-shrink: 0; }
.faq-item.open .faq-question i { transform: rotate(180deg); }
.faq-answer { max-height: 0; overflow: hidden; transition: max-height 0.4s ease; }
.faq-answer-inner { padding: 0 22px 20px; color: var(--gray); line-height: 1.7; font-size: 0.92rem; }
.faq-item.open .faq-answer { max-height: 350px; }

/* ===== CONTACT ===== */
.contact { background: white; }
.contact-grid { display: grid; grid-template-columns: 0.85fr 1.15fr; gap: 30px; }
.contact-info { padding: 38px; border-radius: 22px; color: white; background: linear-gradient(135deg, var(--blue), var(--purple)); box-shadow: var(--shadow-lg); }
.contact-info h3 { font-size: 1.7rem; margin-bottom: 10px; }
.contact-info > p { color: rgba(255,255,255,0.78); margin-bottom: 25px; }
.contact-item { display: flex; align-items: center; gap: 14px; padding: 15px 0; border-bottom: 1px solid rgba(255,255,255,0.10); }
.contact-item:last-of-type { border-bottom: 0; }
.contact-icon { width: 45px; height: 45px; flex-shrink: 0; display: flex; align-items: center; justify-content: center; border-radius: 50%; background: rgba(255,255,255,0.10); }
.contact-label { display: block; font-size: 0.68rem; opacity: 0.6; text-transform: uppercase; }
.contact-value { font-size: 0.92rem; font-weight: 700; word-break: break-word; }
.contact-value a { color: var(--yellow); }
.social-links { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 25px; }
.social-links a { width: 42px; height: 42px; display: flex; align-items: center; justify-content: center; border-radius: 50%; background: rgba(255,255,255,0.10); transition: var(--transition); }
.social-links a:hover { background: var(--yellow); color: var(--dark); transform: translateY(-4px); }
.contact-form { padding: 38px; background: var(--light); border-radius: 22px; box-shadow: var(--shadow); }
.contact-form h3 { color: var(--blue); font-size: 1.7rem; margin-bottom: 5px; }
.contact-form > p { color: var(--gray); margin-bottom: 25px; }
.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 18px; }
.form-group { margin-bottom: 18px; }
.form-group label { display: flex; align-items: center; gap: 6px; margin-bottom: 7px; color: var(--dark); font-size: 0.85rem; font-weight: 700; }
.form-group label i { color: var(--blue); font-size: 0.78rem; }
.form-group input, .form-group textarea, .form-group select { width: 100%; padding: 13px 15px; border: 1px solid var(--border); border-radius: 11px; background: white; color: var(--dark); outline: none; font-size: 0.92rem; transition: var(--transition); }
.form-group input:focus, .form-group textarea:focus, .form-group select:focus { border-color: var(--blue); box-shadow: 0 0 0 3px rgba(18,59,93,0.08); }
.form-group textarea { min-height: 130px; resize: vertical; }
.submit-btn { width: 100%; border: 0; min-height: 54px; border-radius: 50px; background: linear-gradient(135deg, var(--blue), var(--purple)); color: white; font-weight: 800; font-size: 0.95rem; cursor: pointer; transition: var(--transition); display: inline-flex; align-items: center; justify-content: center; gap: 9px; }
.submit-btn:hover { transform: translateY(-3px); box-shadow: 0 10px 25px rgba(18,59,93,0.25); }

/* ===== LOCATION ===== */
.location { padding-top: 0; background: var(--light); }
.map-container { overflow: hidden; border-radius: 22px; box-shadow: var(--shadow-lg); background: white; }
.map-container iframe { width: 100%; height: 480px; border: 0; display: block; }
.location-details { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; padding: 22px; }
.location-item { display: flex; align-items: center; justify-content: center; gap: 9px; color: #52606d; font-weight: 600; font-size: 0.88rem; text-align: center; }
.location-item i { color: var(--red); flex-shrink: 0; }

/* ===== FOOTER ===== */
footer { background: var(--dark); color: rgba(255,255,255,0.65); padding: 65px 0 25px; }
.footer-grid { display: grid; grid-template-columns: 1.3fr 0.8fr 0.8fr; gap: 60px; padding-bottom: 40px; }
.footer-brand h3 { color: white; font-size: 1.6rem; margin-bottom: 12px; display: flex; align-items: center; gap: 10px; }
.footer-brand h3 span { color: var(--yellow); }
.footer-brand h3 i { color: var(--yellow); font-size: 1.2rem; }
.footer-brand p { max-width: 520px; line-height: 1.8; font-size: 0.9rem; }
.footer-column h4 { color: white; margin-bottom: 15px; font-size: 1rem; }
.footer-links { list-style: none; }
.footer-links li { margin-bottom: 8px; }
.footer-links a { transition: var(--transition); display: inline-flex; align-items: center; gap: 6px; }
.footer-links a:hover { color: var(--yellow); }
.footer-links a i { color: var(--green-light); font-size: 0.85rem; }
.footer-social { display: flex; flex-wrap: wrap; gap: 10px; }
.footer-social a { width: 40px; height: 40px; display: flex; align-items: center; justify-content: center; border-radius: 50%; background: rgba(255,255,255,0.07); transition: var(--transition); }
.footer-social a:hover { background: var(--yellow); color: var(--dark); transform: translateY(-3px); }
.footer-bottom { padding-top: 22px; border-top: 1px solid rgba(255,255,255,0.08); text-align: center; font-size: 0.78rem; }
.footer-bottom .highlight { color: var(--yellow); font-weight: 800; }

/* ===== FLOATING ACTIONS ===== */
.floating-actions { position: fixed; right: 20px; bottom: 22px; display: flex; flex-direction: column; gap: 12px; z-index: 9998; }
.fab-wa, .fab-top {
    width: 56px; height: 56px; border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    color: white; font-size: 1.5rem; box-shadow: 0 8px 25px rgba(0,0,0,0.25);
    cursor: pointer; border: 0; transition: all 0.3s ease; position: relative;
}
.fab-wa { background: #25d366; animation: waPulse 2s infinite; }
.fab-wa:hover { transform: scale(1.1); color: white; }
@keyframes waPulse {
    0%, 100% { box-shadow: 0 8px 25px rgba(37,211,102,0.4), 0 0 0 0 rgba(37,211,102,0.7); }
    50% { box-shadow: 0 8px 25px rgba(37,211,102,0.4), 0 0 0 15px rgba(37,211,102,0); }
}
.fab-top { background: var(--blue); opacity: 0; visibility: hidden; transform: translateY(20px); }
.fab-top.show { opacity: 1; visibility: visible; transform: translateY(0); }
.fab-top:hover { background: var(--yellow); color: var(--dark); transform: translateY(-3px); }
.fab-tooltip { position: absolute; right: 70px; top: 50%; transform: translateY(-50%); background: var(--dark); color: white; padding: 8px 14px; border-radius: 8px; font-size: 0.78rem; font-weight: 700; white-space: nowrap; opacity: 0; pointer-events: none; transition: 0.3s; }
.fab-tooltip::after { content: ""; position: absolute; right: -6px; top: 50%; transform: translateY(-50%); border: 6px solid transparent; border-left-color: var(--dark); }
.fab-wa:hover .fab-tooltip { opacity: 1; }

/* ===== TOAST ===== */
.toast { position: fixed; left: 50%; bottom: 25px; transform: translate(-50%, 120px); opacity: 0; z-index: 10000; padding: 14px 22px; border-radius: 12px; background: var(--dark); color: white; box-shadow: var(--shadow-lg); border-left: 4px solid var(--green); transition: 0.4s ease; max-width: calc(100% - 40px); text-align: center; font-size: 0.85rem; pointer-events: none; }
.toast.show { transform: translate(-50%, 0); opacity: 1; }
.toast.error { border-left-color: var(--red); }

/* ===== SCROLL REVEAL ===== */
.reveal { opacity: 0; transform: translateY(35px); transition: opacity 0.8s ease, transform 0.8s ease; }
.reveal.visible { opacity: 1; transform: translateY(0); }
.reveal-delay-1 { transition-delay: 0.1s; }
.reveal-delay-2 { transition-delay: 0.2s; }
.reveal-delay-3 { transition-delay: 0.3s; }

/* ===== RESPONSIVE ===== */
@media (min-width: 1600px) { :root { --gutter: 80px; } .hero-grid { gap: 90px; } .services-grid { gap: 30px; } }
@media (max-width: 1200px) { :root { --gutter: 32px; } .hero-grid, .about-grid { gap: 45px; } .footer-grid { gap: 40px; } .hero-stats { gap: 32px; } .services-grid { gap: 20px; } .book-grid { gap: 40px; } }
@media (max-width: 1024px) {
    :root { --gutter: 26px; --header-h: 72px; }
    .menu-toggle { display: inline-flex; }
    .nav-links {
        position: absolute; top: 100%; left: 0; right: 0;
        flex-direction: column; align-items: stretch; gap: 6px;
        padding: 14px var(--gutter) 22px;
        background: rgba(18,59,93,0.99); backdrop-filter: blur(14px);
        border-top: 1px solid rgba(255,255,255,0.10);
        box-shadow: 0 20px 40px rgba(0,0,0,0.28);
        max-height: calc(100vh - var(--header-h)); overflow-y: auto;
        opacity: 0; visibility: hidden; pointer-events: none; transform: translateY(-14px);
        transition: opacity 0.28s ease, transform 0.28s ease, visibility 0.28s ease;
    }
    .nav-links.open { opacity: 1; visibility: visible; pointer-events: auto; transform: translateY(0); }
    .nav-links a { padding: 13px 16px; font-size: 0.95rem; }
    .hero { min-height: auto; padding: 130px 0 70px; }
    .hero-grid { grid-template-columns: 1fr; gap: 45px; }
    .hero-content { text-align: center; }
    .hero-description { margin-left: auto; margin-right: auto; }
    .hero-buttons, .hero-stats { justify-content: center; }
    .hero-card img { height: 420px; min-height: 300px; max-height: 520px; }
    .about-grid { grid-template-columns: 1fr; gap: 40px; }
    .about-image img { height: 400px; }
    .book-grid { grid-template-columns: 1fr; gap: 45px; }
    .book-cover img { max-width: 320px; }
    .book-content { text-align: center; }
    .book-content .features { grid-template-columns: 1fr 1fr; }
    .book-buttons { justify-content: center; }
    .services-grid { grid-template-columns: repeat(2, 1fr); }
    .contact-grid { grid-template-columns: 1fr; }
    .footer-grid { grid-template-columns: 1fr 1fr; gap: 40px; }
    .footer-brand { grid-column: 1 / -1; }
    section { padding: 80px 0; }
    .section-heading { margin-bottom: 42px; }
    .trust-logos { gap: 30px; }
}
@media (max-width: 768px) {
    :root { --gutter: 20px; --header-h: 68px; }
    .logo { font-size: 1.02rem; gap: 9px; }
    .logo-icon { width: 42px; height: 42px; padding: 3px; }
    .lang-toggle { height: 40px; padding: 0 13px; font-size: 0.75rem; }
    .menu-toggle { width: 40px; height: 40px; }
    section { padding: 62px 0; }
    .hero { padding: 110px 0 60px; }
    .hero h1 { font-size: clamp(1.9rem, 7.5vw, 2.6rem); letter-spacing: -0.6px; line-height: 1.12; }
    .hero-badge { font-size: 0.74rem; padding: 7px 13px; margin-bottom: 18px; }
    .hero-description { font-size: 0.95rem; line-height: 1.75; margin-bottom: 24px; }
    .hero-buttons { flex-direction: column; gap: 10px; margin-bottom: 32px; }
    .hero-buttons .btn { width: 100%; min-height: 50px; }
    .hero-stats { gap: 24px; flex-wrap: wrap; justify-content: center; }
    .stat-number { font-size: 1.5rem; }
    .stat-label { font-size: 0.66rem; }
    .hero-card { padding: 10px; border-radius: 18px; }
    .hero-card img { height: 300px; min-height: 220px; max-height: 380px; border-radius: 12px; }
    .hero-tags span { font-size: 0.68rem; padding: 5px 10px; }
    .section-heading h2 { font-size: clamp(1.6rem, 5.5vw, 2rem); }
    .section-heading p { font-size: 0.92rem; }
    .about-image img { height: 300px; border-radius: 18px; }
    .about-image::after { width: 80px; height: 80px; right: -12px; bottom: -12px; border-radius: 18px; }
    .about-content h3 { font-size: 1.45rem; }
    .about-content p { font-size: 0.94rem; }
    .features { grid-template-columns: 1fr; gap: 10px; }
    .book-cover img { max-width: 260px; }
    .book-cover::before { width: 70px; height: 70px; top: -12px; }
    .book-content h3 { font-size: 1.45rem; }
    .book-content p { font-size: 0.94rem; }
    .book-content .features { grid-template-columns: 1fr; }
    .book-buttons .btn { width: 100%; }
    .books-more { margin-top: 45px; }
    .books-more-title { font-size: 1.3rem; }
    .books-more-sub { font-size: 0.86rem; margin-bottom: 25px; }
    .books-grid { grid-template-columns: repeat(auto-fill, minmax(140px, 1fr)); gap: 14px; }
    .book-card-info h4 { font-size: 0.82rem; }
    .book-card-info a { font-size: 0.72rem; padding: 7px 12px; }
    .services-grid { grid-template-columns: 1fr; gap: 16px; }
    .service-card { padding: 26px 20px; }
    .service-icon { width: 60px; height: 60px; font-size: 1.5rem; border-radius: 16px; }
    .contact-info, .contact-form { padding: 26px 20px; border-radius: 18px; }
    .contact-info h3, .contact-form h3 { font-size: 1.35rem; }
    .contact-value { font-size: 0.88rem; }
    .form-group input, .form-group textarea, .form-group select { font-size: 16px; }
    .map-container iframe { height: 320px; }
    .location-details { grid-template-columns: 1fr; gap: 14px; padding: 20px; }
    footer { padding: 48px 0 22px; }
    .footer-grid { grid-template-columns: 1fr; gap: 32px; padding-bottom: 30px; }
    .footer-brand { grid-column: auto; }
    .footer-brand h3 { font-size: 1.35rem; }
    .testimonial-card { padding: 30px 22px; }
    .testimonial-card .text { font-size: 0.95rem; }
    .cta-inner { flex-direction: column; text-align: center; }
    .trust-logos { gap: 22px; }
    .trust-logo { font-size: 0.85rem; }
    .trust-logo i { font-size: 1.2rem; }
    .floating-actions { right: 14px; bottom: 16px; gap: 10px; }
    .fab-wa, .fab-top { width: 50px; height: 50px; font-size: 1.3rem; }
}
@media (max-width: 560px) { .form-row { grid-template-columns: 1fr; gap: 0; } .hero-card img { height: 250px; min-height: 200px; } .about-image img { height: 250px; } .social-links a, .footer-social a { width: 38px; height: 38px; } .books-grid { grid-template-columns: repeat(2, 1fr); gap: 12px; } }
@media (max-width: 400px) {
    :root { --gutter: 16px; }
    .logo { font-size: 0.92rem; }
    .logo span { display: none; }
    .logo-icon { width: 38px; height: 38px; padding: 2px; }
    .hero h1 { font-size: 1.7rem; }
    .hero-badge { font-size: 0.7rem; }
    .stat-label { font-size: 0.6rem; }
    .contact-info, .contact-form { padding: 22px 16px; }
}
</style>
</head>
<body>

<!-- PRELOADER -->
<div class="preloader" id="preloader">
    <div class="preloader-logo">
        <img src="https://lh3.googleusercontent.com/d/1l6GKIeBMUOtRAQh5xoYir2xAgw4rjaei" alt="JTL Zanzibar Logo" onerror="this.outerHTML='<i class=&quot;fas fa-bicycle&quot; style=&quot;font-size:2rem;color:#101820;&quot;></i>'">
    </div>
    <div class="preloader-text">JTL Zanzibar</div>
    <div class="preloader-bar"><div class="preloader-bar-fill"></div></div>
</div>

<!-- SCROLL PROGRESS -->
<div class="scroll-progress" id="scrollProgress"></div>

<!-- HEADER -->
<header>
    <div class="container">
        <nav class="navbar">
            <a href="#home" class="logo" aria-label="JTL Zanzibar">
                <div class="logo-icon" aria-hidden="true">
                    <img src="https://lh3.googleusercontent.com/d/1l6GKIeBMUOtRAQh5xoYir2xAgw4rjaei" alt="JTL Zanzibar Logo" onerror="this.outerHTML='<i class=&quot;fas fa-bicycle&quot; style=&quot;font-size:1.05rem;color:#101820;&quot;></i>'">
                </div>
                <div class="logo-name" data-i18n-html="logo_text">JTL <span>Zanzibar</span></div>
            </a>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home" data-i18n="nav_home">Nyumbani</a></li>
                <li><a href="#about" data-i18n="nav_about">Kuhusu Sisi</a></li>
                <li><a href="#services" data-i18n="nav_services">Huduma</a></li>
                <li><a href="#book" data-i18n="nav_book">Vitabu</a></li>
                <li><a href="#contact" data-i18n="nav_contact">Wasiliana</a></li>
            </ul>
            <div class="nav-right">
                <button class="lang-toggle" id="langToggle" type="button" aria-label="Switch language">
                    <i class="fas fa-globe"></i><span id="langLabel">EN</span>
                </button>
                <button class="menu-toggle" id="menuToggle" type="button" aria-label="Menyu" aria-controls="navLinks" aria-expanded="false">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </nav>
    </div>
</header>

<!-- HERO -->
<section class="hero" id="home">
    <div class="container">
        <div class="hero-grid">
            <div class="hero-content">
                <div class="hero-badge"><i class="fas fa-star"></i><span data-i18n="hero_badge">Karibu JTL Zanzibar</span></div>
                <h1 data-i18n-html="hero_title">Biashara <span class="yellow">Bora</span>, <span class="green">Ushirikiano</span> <span class="red">Imara</span></h1>
                <p class="hero-description" data-i18n="hero_desc">JTL Zanzibar ni kampuni inayojihusisha na biashara na huduma mbalimbali Zanzibar. Tunatoa ubora, uaminifu na ufanisi katika kila tunachofanya kwa ajili ya wateja wetu.</p>
                <div class="hero-buttons">
                    <a href="#contact" class="btn btn-primary"><i class="fas fa-paper-plane"></i><span data-i18n="btn_contact">Wasiliana Nasi</span></a>
                    <a href="#services" class="btn btn-secondary"><i class="fas fa-briefcase"></i><span data-i18n="btn_services">Huduma Zetu</span></a>
                    <a href="https://drive.google.com/drive/folders/14i708FRvneNRfBEBI3WDnM0OMREu47zT" class="btn btn-drive" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="btn_drive">Fungua Hifadhi ya Nyenzo</span></a>
                </div>
                <div class="hero-stats">
                    <div><span class="stat-number" data-counter="1">1+</span><span class="stat-label" data-i18n="stat1_label">Miaka ya Uzoefu</span></div>
                    <div><span class="stat-number" data-counter="500">500+</span><span class="stat-label" data-i18n="stat2_label">Wateja Walioridhika</span></div>
                    <div><span class="stat-number" data-counter="22">22+</span><span class="stat-label" data-i18n="stat3_label">Vitabu Vilivyochapishwa</span></div>
                </div>
            </div>
            <div class="hero-visual">
                <div class="hero-card">
                    <img src="https://images.unsplash.com/photo-1552664730-d307ca884978?auto=format&fit=crop&w=1200&q=80" alt="JTL Zanzibar business team" data-i18n-alt="hero_img_alt" loading="lazy">
                    <div class="hero-tags">
                        <span class="tag-yellow"><i class="fas fa-medal"></i><span data-i18n="tag1">Ubora</span></span>
                        <span class="tag-green"><i class="fas fa-handshake"></i><span data-i18n="tag2">Uaminifu</span></span>
                        <span class="tag-purple"><i class="fas fa-bolt"></i><span data-i18n="tag3">Ufanisi</span></span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- TRUST STRIP -->
<section class="trust-strip">
    <div class="container">
        <p class="trust-label" data-i18n="trust_label">Wanaotutegemea</p>
        <div class="trust-logos">
            <div class="trust-logo"><i class="fas fa-building"></i><span data-i18n="trust_1">Zanzibar Inc</span></div>
            <div class="trust-logo"><i class="fas fa-hotel"></i><span data-i18n="trust_2">Coastal Hotels</span></div>
            <div class="trust-logo"><i class="fas fa-ship"></i><span data-i18n="trust_3">Spice Traders</span></div>
            <div class="trust-logo"><i class="fas fa-store"></i><span data-i18n="trust_4">Stone Town Mall</span></div>
        </div>
    </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
    <div class="container">
        <div class="section-heading reveal">
            <h2 data-i18n-html="about_heading">Kuhusu <span>Sisi</span></h2>
            <p data-i18n="about_sub">Mshirika wako wa kuaminika katika biashara na huduma Zanzibar.</p>
            <div class="section-line"></div>
        </div>
        <div class="about-grid">
            <div class="about-image reveal"><img src="https://images.unsplash.com/photo-1521737604893-d14cc237f11d?auto=format&fit=crop&w=1200&q=80" alt="JTL Zanzibar team" data-i18n-alt="about_img_alt" loading="lazy"></div>
            <div class="about-content reveal reveal-delay-1">
                <h3 data-i18n-html="about_h3">Mshirika Wako wa <span>Kuaminika</span></h3>
                <p data-i18n="about_p1">JTL Zanzibar ni kampuni iliyoanzishwa kwa lengo la kutoa huduma bora za biashara kwa wakazi na wageni wa Zanzibar. Tunaamini kuwa mafanikio ya biashara yanatokana na uaminifu, ubora na huduma kwa wateja.</p>
                <p data-i18n="about_p2">Kwa miaka mingi tumekuwa tukiwahudumia wateja wetu kwa kutoa suluhisho la biashara lililo bora na la kuaminika. Timu yetu ya wataalamu iko tayari kukusaidia kufikia malengo yako.</p>
                <div class="features">
                    <div class="feature"><i class="fas fa-users"></i><span data-i18n="feat1">Timu ya Wataalamu</span></div>
                    <div class="feature"><i class="fas fa-bolt"></i><span data-i18n="feat2">Huduma za Haraka</span></div>
                    <div class="feature"><i class="fas fa-tags"></i><span data-i18n="feat3">Bei Nafuu</span></div>
                    <div class="feature"><i class="fas fa-handshake"></i><span data-i18n="feat4">Uaminifu</span></div>
                    <div class="feature"><i class="fas fa-headset"></i><span data-i18n="feat5">Msaada wa Wateja</span></div>
                    <div class="feature"><i class="fas fa-award"></i><span data-i18n="feat6">Ubora wa Kimataifa</span></div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- SERVICES -->
<section class="services" id="services">
    <div class="container">
        <div class="section-heading reveal">
            <h2 data-i18n-html="services_heading">Huduma <span>Zetu</span></h2>
            <p data-i18n="services_sub">Tunatoa huduma mbalimbali za biashara kwa viwango vya juu.</p>
            <div class="section-line"></div>
        </div>
        <div class="services-grid">
            <div class="service-card reveal"><div class="service-icon"><i class="fas fa-store"></i></div><h3 data-i18n="srv1_t">Biashara ya Jumla</h3><p data-i18n="srv1_d">Tunajihusisha na biashara mbalimbali za jumla na rejareja kwa bidhaa za ubora wa hali ya juu.</p></div>
            <div class="service-card reveal reveal-delay-1"><div class="service-icon"><i class="fas fa-truck-fast"></i></div><h3 data-i18n="srv2_t">Usafirishaji na Lojistiki</h3><p data-i18n="srv2_d">Huduma za usafirishaji wa bidhaa kwa haraka, usalama na gharama nafuu kote Zanzibar.</p></div>
            <div class="service-card reveal reveal-delay-2"><div class="service-icon"><i class="fas fa-briefcase"></i></div><h3 data-i18n="srv3_t">Ushauri wa Biashara</h3><p data-i18n="srv3_d">Tunatoa ushauri wa kitaalamu kwa wajasiriamali na makampuni ili kukuza biashara zao.</p></div>
            <div class="service-card reveal"><div class="service-icon"><i class="fas fa-boxes-stacked"></i></div><h3 data-i18n="srv4_t">Ugavi na Ununuzi</h3><p data-i18n="srv4_d">Tunagavi bidhaa na vifaa mbalimbali kwa taasisi, makampuni na watu binafsi.</p></div>
            <div class="service-card reveal reveal-delay-1"><div class="service-icon"><i class="fas fa-laptop-code"></i></div><h3 data-i18n="srv5_t">Huduma za Kidijitali</h3><p data-i18n="srv5_d">Tunatoa huduma za kidijitali ikiwemo uundaji wa tovuti, mifumo ya biashara na masoko ya mtandao.</p></div>
            <div class="service-card reveal reveal-delay-2"><div class="service-icon"><i class="fas fa-building"></i></div><h3 data-i18n="srv6_t">Uwekezaji na Mali</h3><p data-i18n="srv6_d">Tunasaidia katika uwekezaji, ushauri wa mali na usimamizi wa miradi mbalimbali.</p></div>
        </div>
    </div>
</section>

<!-- BOOK (WITH MULTIPLE BOOKS) -->
<section class="book" id="book">
    <div class="container">
        <div class="section-heading reveal">
            <h2 data-i18n-html="book_heading">Vitabu <span>Vyetu</span></h2>
            <p data-i18n="book_sub">Mkusanyiko wa machapisho yetu maalum — yaliyoandaliwa kwa ajili yako.</p>
            <div class="section-line"></div>
        </div>

        <!-- FEATURED BOOK -->
        <div class="book-grid">
            <div class="book-cover reveal">
                <img
                    src="https://lh3.googleusercontent.com/d/1E9i8OfY_j81rfWyijL5QYK36SKYaZbdG"
                    alt="Book Cover - JTL Zanzibar"
                    data-i18n-alt="book_img_alt"
                    loading="lazy"
                    onerror="this.onerror=null;this.src='https://drive.google.com/uc?export=view&amp;id=1E9i8OfY_j81rfWyijL5QYK36SKYaZbdG';">
            </div>
            <div class="book-content reveal reveal-delay-1">
                <h3 data-i18n-html="book_h3">Gundua <span>Kitabu Kikuu</span></h3>
                <p data-i18n="book_p1">Kitabu hiki ni mwongozo kamili wa biashara na ujasiriamali, kilichoandaliwa na wataalamu wa JTL Zanzibar kwa ajili ya wajasiriamali, wanafunzi na wataalamu wa biashara.</p>
                <p data-i18n="book_p2">Ndani yake utapata mbinu bora, mikakati na maarifa muhimu yatakayokusaidia kukuza biashara yako na kufikia mafanikio endelevu.</p>
                <div class="features">
                    <div class="feature"><i class="fas fa-book-open"></i><span data-i18n="book_feat1">Mwongozo Kamili</span></div>
                    <div class="feature"><i class="fas fa-lightbulb"></i><span data-i18n="book_feat2">Mbinu Bora</span></div>
                    <div class="feature"><i class="fas fa-chart-line"></i><span data-i18n="book_feat3">Mikakati ya Ukuaji</span></div>
                    <div class="feature"><i class="fas fa-user-graduate"></i><span data-i18n="book_feat4">Kwa Kila Mtu</span></div>
                </div>
                <div class="book-buttons">
                    <a href="https://drive.google.com/file/d/1E9i8OfY_j81rfWyijL5QYK36SKYaZbdG/view?usp=drivesdk" class="btn btn-drive" target="_blank" rel="noopener noreferrer">
                        <i class="fab fa-google-drive"></i><span data-i18n="book_btn">Fungua Kitabu</span>
                    </a>
                    <a href="#contact" class="btn btn-secondary" style="background:var(--blue);color:white;border-color:var(--blue);">
                        <i class="fas fa-info-circle"></i><span data-i18n="book_btn2">Uliza Zaidi</span>
                    </a>
                </div>
            </div>
        </div>

        <!-- MORE BOOKS GRID -->
        <div class="books-more reveal">
            <h3 class="books-more-title" data-i18n-html="books_more_title">Vitabu <span>Zaidi</span></h3>
            <p class="books-more-sub" data-i18n="books_more_sub">Chunguza mkusanyiko wetu kamili wa machapisho na vitabu vya JTL Zanzibar.</p>
            <div class="books-grid">

                <!-- Book 1 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1xzgOhkYz5U4qWXvWVyKxu_gP5SvCIPH1" alt="Kitabu 1" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 1</h4>
                        <a href="https://drive.google.com/file/d/1xzgOhkYz5U4qWXvWVyKxu_gP5SvCIPH1/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 2 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1ueWUgP4se-2fQDURSZdlsABa3DDb5MWX" alt="Kitabu 2" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 2</h4>
                        <a href="https://drive.google.com/file/d/1ueWUgP4se-2fQDURSZdlsABa3DDb5MWX/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 3 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1SS78Dwt3eAoq9ckM3Kwk7jk2Y4NCXhs7" alt="Kitabu 3" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 3</h4>
                        <a href="https://drive.google.com/file/d/1SS78Dwt3eAoq9ckM3Kwk7jk2Y4NCXhs7/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 4 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1_kVj2S8NUH42-NfyyZQIP7Og-t_8qQtL" alt="Kitabu 4" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 4</h4>
                        <a href="https://drive.google.com/file/d/1_kVj2S8NUH42-NfyyZQIP7Og-t_8qQtL/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 5 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1WtHDVzJwgC920mrHF0yz1cFV4NFa4pAk" alt="Kitabu 5" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 5</h4>
                        <a href="https://drive.google.com/file/d/1WtHDVzJwgC920mrHF0yz1cFV4NFa4pAk/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 6 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1FexF1_mWINsm5d1TMCDuiWgf_qKuRFJY" alt="Kitabu 6" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 6</h4>
                        <a href="https://drive.google.com/file/d/1FexF1_mWINsm5d1TMCDuiWgf_qKuRFJY/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 7 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1NylBaFS75COFm77DGfwiCjBOws_F2vIb" alt="Kitabu 7" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 7</h4>
                        <a href="https://drive.google.com/file/d/1NylBaFS75COFm77DGfwiCjBOws_F2vIb/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 8 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1CgwHXx5IlnsI1ngmQTteaBy-7OYFfnJt" alt="Kitabu 8" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 8</h4>
                        <a href="https://drive.google.com/file/d/1CgwHXx5IlnsI1ngmQTteaBy-7OYFfnJt/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 9 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1nD0W-WkmiOj1jVfnVVfcU_5RTd9vqVnM" alt="Kitabu 9" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 9</h4>
                        <a href="https://drive.google.com/file/d/1nD0W-WkmiOj1jVfnVVfcU_5RTd9vqVnM/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 10 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/17hq9CO5WS7HumpG-PmEMCXUoVWZVOiwA" alt="Kitabu 10" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 10</h4>
                        <a href="https://drive.google.com/file/d/17hq9CO5WS7HumpG-PmEMCXUoVWZVOiwA/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 11 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1EpNna6LcDhwA9mTl6_s2AsRbWmJKvZab" alt="Kitabu 11" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 11</h4>
                        <a href="https://drive.google.com/file/d/1EpNna6LcDhwA9mTl6_s2AsRbWmJKvZab/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 12 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1_7YO9Urd5pmS_XjmDCi2vP37RI_EAN3S" alt="Kitabu 12" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 12</h4>
                        <a href="https://drive.google.com/file/d/1_7YO9Urd5pmS_XjmDCi2vP37RI_EAN3S/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 13 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1yu0aPmrH0qZ69tZQu2IHeNxltRqV-qlr" alt="Kitabu 13" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 13</h4>
                        <a href="https://drive.google.com/file/d/1yu0aPmrH0qZ69tZQu2IHeNxltRqV-qlr/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 14 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1Q6ZrfzBpREvf3sP-cRlorTed9QMEHNyA" alt="Kitabu 14" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 14</h4>
                        <a href="https://drive.google.com/file/d/1Q6ZrfzBpREvf3sP-cRlorTed9QMEHNyA/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 15 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1KkeX3tBLPlbzC3oOKXukqWcdEnRZ8di9" alt="Kitabu 15" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 15</h4>
                        <a href="https://drive.google.com/file/d/1KkeX3tBLPlbzC3oOKXukqWcdEnRZ8di9/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 16 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1CAODYH5mysHPlhCDUTdbRwIj390-9uaP" alt="Kitabu 16" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 16</h4>
                        <a href="https://drive.google.com/file/d/1CAODYH5mysHPlhCDUTdbRwIj390-9uaP/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 17 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1wv-rFNLfYq4-8j4-812BVJqkFOg4EET9" alt="Kitabu 17" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 17</h4>
                        <a href="https://drive.google.com/file/d/1wv-rFNLfYq4-8j4-812BVJqkFOg4EET9/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 18 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/16dB2pZl2G1wgMRMMehhKHAK6IJpWpqHC" alt="Kitabu 18" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 18</h4>
                        <a href="https://drive.google.com/file/d/16dB2pZl2G1wgMRMMehhKHAK6IJpWpqHC/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 19 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1OYJINnKlPNgEBuTZh04ql9UQlYuzLTCx" alt="Kitabu 19" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 19</h4>
                        <a href="https://drive.google.com/file/d/1OYJINnKlPNgEBuTZh04ql9UQlYuzLTCx/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 20 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1Z9Q5g1fiNosyyAqKpKFp-EKCOm9SEKna" alt="Kitabu 20" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 20</h4>
                        <a href="https://drive.google.com/file/d/1Z9Q5g1fiNosyyAqKpKFp-EKCOm9SEKna/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

                <!-- Book 21 -->
                <div class="book-card">
                    <div class="book-thumb">
                        <img src="https://lh3.googleusercontent.com/d/1mHaGzgVDuDtYGAbYd7a6qDEOT0z1GlYH" alt="Kitabu 21" loading="lazy" onerror="this.onerror=null;this.parentElement.innerHTML='<i class=&quot;fas fa-file-pdf&quot;></i>';">
                    </div>
                    <div class="book-card-info">
                        <h4><span data-i18n="book_n">Kitabu</span> 21</h4>
                        <a href="https://drive.google.com/file/d/1mHaGzgVDuDtYGAbYd7a6qDEOT0z1GlYH/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="book_open">Fungua</span></a>
                    </div>
                </div>

            </div>
        </div>
    </div>
</section>

<!-- TESTIMONIALS -->
<section class="testimonials" id="testimonials">
    <div class="container">
        <div class="section-heading reveal">
            <h2 data-i18n-html="testimonials_heading">Sauti za <span>Wateja</span></h2>
            <p data-i18n="testimonials_sub">Wateja wetu wanazungumza - jiunge na familia yetu ya wateja walioridhika.</p>
            <div class="section-line"></div>
        </div>
        <div class="testimonial-slider">
            <div class="testimonial-track" id="testimonialTrack">
                <div class="testimonial-card">
                    <div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                    <p class="text" data-i18n="t1_text">"Huduma bora na za haraka. JTL Zanzibar wamekuwa msaada mkubwa kwa biashara yangu. Nawapendekeza kwa kila mtu!"</p>
                    <div class="testimonial-avatar"><i class="fas fa-user"></i></div>
                    <div class="testimonial-name" data-i18n="t1_name">Ahmed Hassan</div>
                    <div class="testimonial-role" data-i18n="t1_role">Mfanyabiashara, Stone Town</div>
                </div>
                <div class="testimonial-card">
                    <div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                    <p class="text" data-i18n="t2_text">"Kutoka ushauri hadi utekelezaji, timu ni ya kitaalamu na ya kuaminika. Huduma zao zimeboresha biashara yangu kwa kiasi kikubwa."</p>
                    <div class="testimonial-avatar"><i class="fas fa-user"></i></div>
                    <div class="testimonial-name" data-i18n="t2_name">Fatma Ali</div>
                    <div class="testimonial-role" data-i18n="t2_role">Mmiliki wa Hoteli, Nungwi</div>
                </div>
                <div class="testimonial-card">
                    <div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                    <p class="text" data-i18n="t3_text">"Uaminifu na ubora ni sifa kuu za JTL. Tumekuwa tukifanya kazi nao kwa miaka mingi na hatujawahi kukatishwa tamaa."</p>
                    <div class="testimonial-avatar"><i class="fas fa-user-tie"></i></div>
                    <div class="testimonial-name" data-i18n="t3_name">Mohamed Suleiman</div>
                    <div class="testimonial-role" data-i18n="t3_role">Mkurugenzi, Zanzibar Trading</div>
                </div>
                <div class="testimonial-card">
                    <div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                    <p class="text" data-i18n="t4_text">"Huduma za kidijitali walizotoa zimebadilisha kabisa biashara yangu. Tovuti nzuri na mfumo rahisi wa kutumia. Asanteni sana!"</p>
                    <div class="testimonial-avatar"><i class="fas fa-user"></i></div>
                    <div class="testimonial-name" data-i18n="t4_name">Zainab Omar</div>
                    <div class="testimonial-role" data-i18n="t4_role">Mjasiriamali, Paje</div>
                </div>
            </div>
            <div class="testimonial-dots" id="testimonialDots"></div>
        </div>
    </div>
</section>

<!-- CTA BANNER -->
<section class="cta-banner">
    <div class="container">
        <div class="cta-inner reveal">
            <div>
                <h2 data-i18n="cta_title">Tayari Kuanza Safari Yako ya Mafanikio?</h2>
                <p data-i18n="cta_desc">Wasiliana nasi leo na tuanze kujenga suluhisho la biashara linalokufaa.</p>
            </div>
            <a href="#contact" class="btn btn-primary"><i class="fas fa-rocket"></i><span data-i18n="cta_btn">Anza Sasa</span></a>
        </div>
    </div>
</section>

<!-- FAQ -->
<section class="faq" id="faq">
    <div class="container">
        <div class="section-heading reveal">
            <h2 data-i18n-html="faq_heading">Maswali ya <span>Mara kwa Mara</span></h2>
            <p data-i18n="faq_sub">Majibu ya haraka kwa maswali yanayoulizwa sana.</p>
            <div class="section-line"></div>
        </div>
        <div class="faq-list">
            <div class="faq-item">
                <button class="faq-question"><span data-i18n="faq_q1">Je, mnatoa huduma kwa makampuni makubwa?</span><i class="fas fa-chevron-down"></i></button>
                <div class="faq-answer"><div class="faq-answer-inner" data-i18n="faq_a1">Ndiyo, tunahudumia wateja wa aina zote - kutoka kwa wajasiriamali binafsi hadi makampuni makubwa na taasisi.</div></div>
            </div>
            <div class="faq-item">
                <button class="faq-question"><span data-i18n="faq_q2">Mnafanyaje kazi kuhusu bei na malipo?</span><i class="fas fa-chevron-down"></i></button>
                <div class="faq-answer"><div class="faq-answer-inner" data-i18n="faq_a2">Tunatoa bei nafuu na za ushindani. Tunaruhusu malipo kwa awamu kwa miradi mikubwa, na tunatoa nukuu ya bure kabla ya kuanza kazi.</div></div>
            </div>
            <div class="faq-item">
                <button class="faq-question"><span data-i18n="faq_q3">Mnahudumia maeneo gani?</span><i class="fas fa-chevron-down"></i></button>
                <div class="faq-answer"><div class="faq-answer-inner" data-i18n="faq_a3">Tunahudumia Zanzibar yote - Unguja na Pemba. Kwa miradi maalum tunaweza kufanya kazi kote Tanzania.</div></div>
            </div>
            <div class="faq-item">
                <button class="faq-question"><span data-i18n="faq_q4">Muda gani wa kujibu ujumbe?</span><i class="fas fa-chevron-down"></i></button>
                <div class="faq-answer"><div class="faq-answer-inner" data-i18n="faq_a4">Tunajibu ujumbe wote ndani ya saa 24. Kwa mahitaji ya haraka, wasiliana nasi kupitia WhatsApp au simu moja kwa moja.</div></div>
            </div>
            <div class="faq-item">
                <button class="faq-question"><span data-i18n="faq_q5">Je, mna dhamana ya ubora wa kazi?</span><i class="fas fa-chevron-down"></i></button>
                <div class="faq-answer"><div class="faq-answer-inner" data-i18n="faq_a5">Ndiyo, tunatoa dhamana ya ubora kwa kazi zote tunazofanya. Kuridhika kwako ni kipaumbele chetu cha kwanza.</div></div>
            </div>
        </div>
    </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
    <div class="container">
        <div class="section-heading reveal">
            <h2 data-i18n-html="contact_heading">Wasiliana <span>Nasi</span></h2>
            <p data-i18n="contact_sub">Tuko tayari kukusaidia — wasiliana nasi leo.</p>
            <div class="section-line"></div>
        </div>
        <div class="contact-grid">
            <div class="contact-info reveal">
                <h3 data-i18n="ci_h3">Taarifa za Mawasiliano</h3>
                <p data-i18n="ci_p">Karibu ofisini kwetu au wasiliana nasi kwa njia yoyote ile.</p>
                <div class="contact-item"><div class="contact-icon"><i class="fas fa-phone"></i></div><div><span class="contact-label" data-i18n="ci_phone_label">Simu</span><span class="contact-value"><a href="tel:+255776290901">+255 776 290 901</a></span></div></div>
                <div class="contact-item"><div class="contact-icon"><i class="fas fa-envelope"></i></div><div><span class="contact-label" data-i18n="ci_email_label">Barua Pepe</span><span class="contact-value"><a href="mailto:jeithirdtrade@gmail.com">jeithirdtrade@gmail.com</a></span></div></div>
                <div class="contact-item"><div class="contact-icon"><i class="fas fa-location-dot"></i></div><div><span class="contact-label" data-i18n="ci_loc_label">Mahali</span><span class="contact-value" data-i18n="ci_loc_value">Zanzibar, Tanzania</span></div></div>
                <div class="contact-item"><div class="contact-icon"><i class="fas fa-clock"></i></div><div><span class="contact-label" data-i18n="ci_hours_label">Saa za Kazi</span><span class="contact-value" data-i18n="ci_hours_value">Jumatatu - Jumamosi: 8:00 - 18:00</span></div></div>
                <div class="social-links">
                    <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
                    <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                    <a href="https://wa.me/255776290901" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                    <a href="https://drive.google.com/drive/folders/14i708FRvneNRfBEBI3WDnM0OMREu47zT" target="_blank" rel="noopener noreferrer" aria-label="Google Drive"><i class="fab fa-google-drive"></i></a>
                </div>
            </div>
            <form class="contact-form reveal reveal-delay-1" id="contactForm" novalidate>
                <h3 data-i18n="form_h3">Tutumie Ujumbe</h3>
                <p data-i18n="form_p">Jaza fomu hapa chini na tutakujibu haraka iwezekanavyo.</p>
                <div class="form-row">
                    <div class="form-group">
                        <label for="name"><i class="fas fa-user"></i><span data-i18n="f_name">Jina Kamili</span></label>
                        <input type="text" id="name" name="name" required placeholder="Jina lako" data-i18n-placeholder="f_name_ph">
                    </div>
                    <div class="form-group">
                        <label for="email"><i class="fas fa-envelope"></i><span data-i18n="f_email">Barua Pepe</span></label>
                        <input type="email" id="email" name="email" required placeholder="barua@mfano.com" data-i18n-placeholder="f_email_ph">
                    </div>
                </div>
                <div class="form-row">
                    <div class="form-group">
                        <label for="phone"><i class="fas fa-phone"></i><span data-i18n="f_phone">Namba ya Simu</span></label>
                        <input type="tel" id="phone" name="phone" placeholder="+255 7XX XXX XXX" data-i18n-placeholder="f_phone_ph">
                    </div>
                    <div class="form-group">
                        <label for="subject"><i class="fas fa-briefcase"></i><span data-i18n="f_subject">Aina ya Huduma</span></label>
                        <select id="subject" name="subject">
                            <option value="" data-i18n="f_subject_ph">Chagua huduma</option>
                            <option value="general" data-i18n="f_subject_1">Ujumbe wa Jumla</option>
                            <option value="consulting" data-i18n="f_subject_2">Ushauri wa Biashara</option>
                            <option value="supply" data-i18n="f_subject_3">Ugavi na Ununuzi</option>
                            <option value="digital" data-i18n="f_subject_4">Huduma za Kidijitali</option>
                            <option value="book" data-i18n="f_subject_book">Kuhusu Vitabu</option>
                            <option value="other" data-i18n="f_subject_5">Nyingine</option>
                        </select>
                    </div>
                </div>
                <div class="form-group">
                    <label for="message"><i class="fas fa-comment-dots"></i><span data-i18n="f_msg">Ujumbe Wako</span></label>
                    <textarea id="message" name="message" required placeholder="Andika ujumbe wako hapa..." data-i18n-placeholder="f_msg_ph"></textarea>
                </div>
                <button type="submit" class="submit-btn"><i class="fas fa-paper-plane"></i><span data-i18n="f_submit">Tuma Ujumbe</span></button>
            </form>
        </div>
    </div>
</section>

<!-- LOCATION -->
<section class="location" id="location">
    <div class="container">
        <div class="map-container reveal">
            <iframe src="https://www.google.com/maps?q=Zanzibar%2C%20Tanzania&output=embed" title="JTL Zanzibar Location" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            <div class="location-details">
                <div class="location-item"><i class="fas fa-location-dot"></i><span data-i18n="loc1">Zanzibar, Tanzania</span></div>
                <div class="location-item"><i class="fas fa-clock"></i><span data-i18n="loc2">Jumatatu - Jumamosi: 8:00 - 18:00</span></div>
                <div class="location-item"><i class="fas fa-phone"></i><span>+255776290901</span></div>
            </div>
        </div>
    </div>
</section>

<!-- FOOTER -->
<footer>
    <div class="container">
        <div class="footer-grid">
            <div class="footer-brand">
                <h3><i class="fas fa-bicycle"></i>JTL <span>Zanzibar</span></h3>
                <p data-i18n="footer_desc">Kampuni ya biashara na huduma mbalimbali Zanzibar. Tunatoa ubora, uaminifu na ufanisi katika kila tunachofanya.</p>
            </div>
            <div class="footer-column">
                <h4 data-i18n="footer_col1">Viungo vya Haraka</h4>
                <ul class="footer-links">
                    <li><a href="#home"><i class="fas fa-house"></i><span data-i18n="nav_home">Nyumbani</span></a></li>
                    <li><a href="#about"><i class="fas fa-circle-info"></i><span data-i18n="nav_about">Kuhusu Sisi</span></a></li>
                    <li><a href="#services"><i class="fas fa-briefcase"></i><span data-i18n="nav_services">Huduma</span></a></li>
                    <li><a href="#book"><i class="fas fa-book"></i><span data-i18n="nav_book">Vitabu</span></a></li>
                    <li><a href="#contact"><i class="fas fa-envelope"></i><span data-i18n="nav_contact">Wasiliana</span></a></li>
                    <li><a href="https://drive.google.com/drive/folders/14i708FRvneNRfBEBI3WDnM0OMREu47zT" target="_blank" rel="noopener noreferrer"><i class="fab fa-google-drive"></i><span data-i18n="footer_drive">Hifadhi ya Nyenzo</span></a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h4 data-i18n="footer_col2">Tufuate</h4>
                <div class="footer-social">
                    <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" aria-label="Facebook"><i class="fab fa-facebook-f"></i></a>
                    <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
                    <a href="https://wa.me/255776290901" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
                    <a href="mailto:jeithirdtrade@gmail.com" aria-label="Email"><i class="fas fa-envelope"></i></a>
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <span data-i18n-html="footer_copy">© 2025 <span class="highlight">JTL Zanzibar</span>. Haki zote zimehifadhiwa.</span>
        </div>
    </div>
</footer>

<!-- FLOATING ACTIONS -->
<div class="floating-actions">
    <a href="https://wa.me/255776290901" class="fab-wa" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp">
        <i class="fab fa-whatsapp"></i>
        <span class="fab-tooltip" data-i18n="whatsapp_tip">Piga Gumzo WhatsApp</span>
    </a>
    <button class="fab-top" id="backTop" aria-label="Rudi Juu">
        <i class="fas fa-arrow-up"></i>
    </button>
</div>

<div class="toast" id="toast" role="status" aria-live="polite"></div>

<script>
/* ========== TRANSLATIONS ========== */
const translations = {
    sw: {
        logo_text: 'JTL <span>Zanzibar</span>',
        nav_home: 'Nyumbani', nav_about: 'Kuhusu Sisi', nav_services: 'Huduma', nav_book: 'Vitabu', nav_contact: 'Wasiliana',
        hero_badge: 'Karibu JTL Zanzibar',
        hero_title: 'Biashara <span class="yellow">Bora</span>, <span class="green">Ushirikiano</span> <span class="red">Imara</span>',
        hero_desc: 'JTL Zanzibar ni kampuni inayojihusisha na biashara na huduma mbalimbali Zanzibar. Tunatoa ubora, uaminifu na ufanisi katika kila tunachofanya kwa ajili ya wateja wetu.',
        hero_img_alt: 'Timu ya JTL Zanzibar',
        btn_contact: 'Wasiliana Nasi', btn_services: 'Huduma Zetu', btn_drive: 'Fungua Hifadhi ya Nyenzo',
        stat1_label: 'Miaka ya Uzoefu', stat2_label: 'Wateja Walioridhika', stat3_label: 'Vitabu Vilivyochapishwa',
        tag1: 'Ubora', tag2: 'Uaminifu', tag3: 'Ufanisi',
        trust_label: 'Wanaotutegemea', trust_1: 'Zanzibar Inc', trust_2: 'Coastal Hotels', trust_3: 'Spice Traders', trust_4: 'Stone Town Mall',
        about_heading: 'Kuhusu <span>Sisi</span>', about_sub: 'Mshirika wako wa kuaminika katika biashara na huduma Zanzibar.',
        about_h3: 'Mshirika Wako wa <span>Kuaminika</span>',
        about_p1: 'JTL Zanzibar ni kampuni iliyoanzishwa kwa lengo la kutoa huduma bora za biashara kwa wakazi na wageni wa Zanzibar. Tunaamini kuwa mafanikio ya biashara yanatokana na uaminifu, ubora na huduma kwa wateja.',
        about_p2: 'Kwa miaka mingi tumekuwa tukiwahudumia wateja wetu kwa kutoa suluhisho la biashara lililo bora na la kuaminika. Timu yetu ya wataalamu iko tayari kukusaidia kufikia malengo yako.',
        about_img_alt: 'Timu ya JTL Zanzibar katika kikao',
        feat1: 'Timu ya Wataalamu', feat2: 'Huduma za Haraka', feat3: 'Bei Nafuu', feat4: 'Uaminifu', feat5: 'Msaada wa Wateja', feat6: 'Ubora wa Kimataifa',
        services_heading: 'Huduma <span>Zetu</span>', services_sub: 'Tunatoa huduma mbalimbali za biashara kwa viwango vya juu.',
        srv1_t: 'Biashara ya Jumla', srv1_d: 'Tunajihusisha na biashara mbalimbali za jumla na rejareja kwa bidhaa za ubora wa hali ya juu.',
        srv2_t: 'Usafirishaji na Lojistiki', srv2_d: 'Huduma za usafirishaji wa bidhaa kwa haraka, usalama na gharama nafuu kote Zanzibar.',
        srv3_t: 'Ushauri wa Biashara', srv3_d: 'Tunatoa ushauri wa kitaalamu kwa wajasiriamali na makampuni ili kukuza biashara zao.',
        srv4_t: 'Ugavi na Ununuzi', srv4_d: 'Tunagavi bidhaa na vifaa mbalimbali kwa taasisi, makampuni na watu binafsi.',
        srv5_t: 'Huduma za Kidijitali', srv5_d: 'Tunatoa huduma za kidijitali ikiwemo uundaji wa tovuti, mifumo ya biashara na masoko ya mtandao.',
        srv6_t: 'Uwekezaji na Mali', srv6_d: 'Tunasaidia katika uwekezaji, ushauri wa mali na usimamizi wa miradi mbalimbali.',
        book_heading: 'Vitabu <span>Vyetu</span>',
        book_sub: 'Mkusanyiko wa machapisho yetu maalum — yaliyoandaliwa kwa ajili yako.',
        book_h3: 'Gundua <span>Kitabu Kikuu</span
