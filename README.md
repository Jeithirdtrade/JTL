<meta name="viewport"
      content="width=device-width, initial-scale=1.0">

<meta name="description"
      content="JTL Zanzibar - Kampuni ya biashara na huduma mbalimbali Zanzibar. Ubora, uaminifu na ufanisi.">

<meta name="keywords"
      content="JTL Zanzibar, biashara Zanzibar, huduma Zanzibar, JTL, Tanzania">

<meta name="author"
      content="JTL Zanzibar">

<meta name="theme-color"
      content="#123b5d">

<title>JTL Zanzibar | Biashara & Ushirikiano</title>

<!-- FONT AWESOME -->
<link rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

<style>

    /* =========================================================
       RESET
    ========================================================= */

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    html {
        scroll-behavior: smooth;
    }

    body {
        font-family:
            "Segoe UI",
            Tahoma,
            Geneva,
            Verdana,
            sans-serif;

        background: #f5f7fa;
        color: #1e293b;
        line-height: 1.6;
        overflow-x: hidden;
    }

    img {
        width: 100%;
        display: block;
    }

    a {
        text-decoration: none;
        color: inherit;
    }

    button,
    input,
    textarea,
    select {
        font-family: inherit;
    }

    :root {
        --blue: #123b5d;
        --blue-light: #1f6b9c;

        --red: #c0392b;
        --red-light: #e74c3c;

        --green: #20a05a;
        --green-light: #2ecc71;

        --yellow: #f1c40f;
        --yellow-light: #ffe66d;

        --purple: #743b91;
        --purple-light: #9b59b6;

        --dark: #101820;
        --dark-2: #172331;

        --white: #ffffff;
        --light: #f5f7fa;
        --gray: #64748b;
        --border: #e2e8f0;

        --shadow:
            0 10px 35px rgba(15, 23, 42, 0.10);

        --shadow-lg:
            0 20px 60px rgba(15, 23, 42, 0.16);

        --radius: 18px;

        --transition: 0.3s ease;
    }

    .container {
        width: min(1180px, 92%);
        margin: auto;
    }


    /* =========================================================
       SCROLLBAR
    ========================================================= */

    ::-webkit-scrollbar {
        width: 8px;
    }

    ::-webkit-scrollbar-track {
        background: #edf1f5;
    }

    ::-webkit-scrollbar-thumb {
        background: var(--blue);
        border-radius: 20px;
    }


    /* =========================================================
       HEADER
    ========================================================= */

    header {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        z-index: 9999;

        background:
            rgba(18, 59, 93, 0.96);

        backdrop-filter: blur(14px);

        box-shadow:
            0 5px 25px rgba(0, 0, 0, 0.15);
    }

    .navbar {
        min-height: 74px;

        display: flex;
        align-items: center;
        justify-content: space-between;

        gap: 30px;
    }

    /* LOGO */

    .logo {
        display: flex;
        align-items: center;
        gap: 10px;

        color: white;

        font-size: 1.25rem;
        font-weight: 900;

        letter-spacing: 0.4px;

        flex-shrink: 0;
    }

    .logo-icon {
        width: 44px;
        height: 44px;

        display: flex;
        align-items: center;
        justify-content: center;

        border-radius: 12px;

        background: var(--yellow);
        color: var(--dark);

        font-size: 1.35rem;
        font-weight: 900;

        box-shadow:
            0 5px 20px rgba(241, 196, 15, 0.35);
    }

    .logo span {
        color: var(--yellow);
    }


    /* NAVIGATION */

    .nav-links {
        list-style: none;

        display: flex;
        align-items: center;

        gap: 6px;
    }

    .nav-links a {
        color:
            rgba(255, 255, 255, 0.88);

        font-size: 0.92rem;
        font-weight: 700;

        padding: 10px 15px;

        border-radius: 10px;

        transition:
            var(--transition);
    }

    .nav-links a:hover,
    .nav-links a.active {
        background: var(--yellow);
        color: var(--dark);
    }


    /* HAMBURGER */

    .hamburger {
        display: none;

        width: 45px;
        height: 45px;

        border: 0;
        border-radius: 10px;

        background:
            rgba(255, 255, 255, 0.10);

        cursor: pointer;
    }

    .hamburger span {
        display: block;

        width: 25px;
        height: 3px;

        margin: 5px auto;

        background: white;

        border-radius: 10px;

        transition: var(--transition);
    }

    .hamburger.active span:nth-child(1) {
        transform:
            translateY(8px)
            rotate(45deg);
    }

    .hamburger.active span:nth-child(2) {
        opacity: 0;
    }

    .hamburger.active span:nth-child(3) {
        transform:
            translateY(-8px)
            rotate(-45deg);
    }


    /* =========================================================
       HERO
    ========================================================= */

    .hero {
        min-height: 760px;

        padding:
            150px 0
            90px;

        position: relative;

        overflow: hidden;

        background:
            linear-gradient(
                120deg,
                #123b5d 0%,
                #263b75 45%,
                #743b91 72%,
                #c0392b 100%
            );
    }

    .hero::before {
        content: "";

        position: absolute;
        inset: 0;

        background:
            radial-gradient(
                circle at 10% 20%,
                rgba(241, 196, 15, 0.16),
                transparent 35%
            ),

            radial-gradient(
                circle at 90% 80%,
                rgba(46, 204, 113, 0.14),
                transparent 35%
            );
    }

    .hero-grid {
        position: relative;
        z-index: 2;

        display: grid;

        grid-template-columns:
            1.05fr
            0.95fr;

        align-items: center;

        gap: 70px;
    }

    .hero-content {
        color: white;
    }

    .hero-badge {
        display: inline-flex;

        align-items: center;
        gap: 8px;

        padding: 8px 15px;

        margin-bottom: 22px;

        border-radius: 50px;

        background:
            rgba(255, 255, 255, 0.10);

        border:
            1px solid rgba(255, 255, 255, 0.18);

        backdrop-filter: blur(8px);

        font-size: 0.82rem;
        font-weight: 700;
    }

    .hero h1 {
        font-size:
            clamp(2.7rem, 6vw, 4.8rem);

        line-height: 1.05;

        font-weight: 900;

        margin-bottom: 25px;

        letter-spacing: -1.5px;
    }

    .hero h1 .yellow {
        color: var(--yellow);
    }

    .hero h1 .green {
        color: var(--green-light);
    }

    .hero h1 .red {
        color: var(--red-light);
    }

    .hero-description {
        max-width: 650px;

        color:
            rgba(255, 255, 255, 0.84);

        font-size: 1.08rem;

        line-height: 1.8;

        margin-bottom: 30px;
    }

    .hero-buttons {
        display: flex;
        flex-wrap: wrap;

        gap: 14px;

        margin-bottom: 40px;
    }

    .btn {
        min-height: 52px;

        display: inline-flex;

        align-items: center;
        justify-content: center;

        gap: 9px;

        padding:
            13px 24px;

        border-radius: 50px;

        font-size: 0.9rem;
        font-weight: 800;

        border: 0;

        cursor: pointer;

        transition:
            var(--transition);
    }

    .btn:hover {
        transform: translateY(-3px);
    }

    .btn-primary {
        background: var(--yellow);
        color: var(--dark);

        box-shadow:
            0 8px 25px
            rgba(241, 196, 15, 0.28);
    }

    .btn-secondary {
        background:
            rgba(255, 255, 255, 0.10);

        color: white;

        border:
            1px solid rgba(255, 255, 255, 0.25);
    }

    .btn-secondary:hover {
        background:
            rgba(255, 255, 255, 0.18);
    }


    /* HERO STATS */

    .hero-stats {
        display: flex;

        gap: 45px;
    }

    .stat-number {
        display: block;

        color: var(--yellow);

        font-size: 1.9rem;

        font-weight: 900;
    }

    .stat-label {
        display: block;

        color:
            rgba(255, 255, 255, 0.65);

        font-size: 0.75rem;

        text-transform: uppercase;

        letter-spacing: 0.7px;
    }


    /* HERO IMAGE */

    .hero-visual {
        position: relative;
    }

    .hero-card {
        padding: 15px;

        background:
            rgba(255, 255, 255, 0.09);

        border:
            1px solid
            rgba(255, 255, 255, 0.16);

        border-radius: 24px;

        backdrop-filter: blur(15px);

        box-shadow:
            0 30px 80px
            rgba(0, 0, 0, 0.25);
    }

    .hero-card img {
        height: 420px;

        object-fit: cover;

        border-radius: 16px;
    }

    .hero-tags {
        display: flex;

        flex-wrap: wrap;

        justify-content: center;

        gap: 8px;

        padding:
            15px 5px 3px;
    }

    .hero-tags span {
        padding:
            6px 12px;

        border-radius: 30px;

        font-size: 0.72rem;

        font-weight: 800;
    }

    .tag-yellow {
        background: var(--yellow);
        color: var(--dark);
    }

    .tag-green {
        background: var(--green);
        color: white;
    }

    .tag-purple {
        background: var(--purple);
        color: white;
    }


    /* =========================================================
       GENERAL SECTIONS
    ========================================================= */

    section {
        padding:
            100px 0;
    }

    .section-heading {
        max-width: 720px;

        margin:
            0 auto 55px;

        text-align: center;
    }

    .section-heading h2 {
        font-size:
            clamp(2rem, 4vw, 2.8rem);

        color: var(--dark);

        font-weight: 900;

        margin-bottom: 15px;
    }

    .section-heading h2 span {
        color: var(--purple);
    }

    .section-heading p {
        color: var(--gray);

        font-size: 1rem;
    }

    .section-line {
        width: 65px;
        height: 4px;

        margin: 15px auto 0;

        border-radius: 10px;

        background:
            linear-gradient(
                90deg,
                var(--yellow),
                var(--red),
                var(--purple)
            );
    }


    /* =========================================================
       ABOUT
    ========================================================= */

    .about {
        background: white;
    }

    .about-grid {
        display: grid;

        grid-template-columns:
            1fr
            1fr;

        gap: 70px;

        align-items: center;
    }

    .about-image {
        position: relative;
    }

    .about-image img {
        height: 450px;

        object-fit: cover;

        border-radius: 22px;

        box-shadow: var(--shadow-lg);
    }

    .about-image::after {
        content: "";

        position: absolute;

        width: 120px;
        height: 120px;

        right: -20px;
        bottom: -20px;

        background: var(--yellow);

        border-radius: 25px;

        z-index: -1;
    }

    .about-content h3 {
        color: var(--blue);

        font-size: 2rem;

        margin-bottom: 15px;
    }

    .about-content h3 span {
        color: var(--purple);
    }

    .about-content p {
        color: #52606d;

        margin-bottom: 15px;

        line-height: 1.8;
    }

    .features {
        display: grid;

        grid-template-columns:
            1fr
            1fr;

        gap: 12px;

        margin-top: 25px;
    }

    .feature {
        display: flex;

        align-items: center;

        gap: 10px;

        padding: 13px;

        border-radius: 12px;

        background: var(--light);

        font-weight: 700;

        font-size: 0.88rem;

        transition: var(--transition);
    }

    .feature:hover {
        transform: translateY(-3px);

        background: #eef4f8;
    }

    .feature i {
        color: var(--blue);

        font-size: 1.1rem;
    }


    /* =========================================================
       SERVICES
    ========================================================= */

    .services {
        background: var(--light);
    }

    .services-grid {
        display: grid;

        grid-template-columns:
            repeat(3, 1fr);

        gap: 24px;
    }

    .service-card {
        background: white;

        padding: 32px 25px;

        border-radius: var(--radius);

        box-shadow: var(--shadow);

        border-top: 4px solid var(--blue);

        transition: var(--transition);

        text-align: center;
    }

    .service-card:hover {
        transform: translateY(-8px);

        box-shadow: var(--shadow-lg);
    }

    .service-card:nth-child(2) {
        border-top-color: var(--red);
    }

    .service-card:nth-child(3) {
        border-top-color: var(--green);
    }

    .service-card:nth-child(4) {
        border-top-color: var(--purple);
    }

    .service-card:nth-child(5) {
        border-top-color: var(--yellow);
    }

    .service-card:nth-child(6) {
        border-top-color: var(--red);
    }

    .service-icon {
        width: 70px;
        height: 70px;

        display: flex;

        align-items: center;
        justify-content: center;

        margin: 0 auto 18px;

        border-radius: 20px;

        background:
            rgba(18, 59, 93, 0.08);

        color: var(--blue);

        font-size: 1.8rem;
    }

    .service-card h3 {
        font-size: 1.08rem;

        color: var(--dark);

        margin-bottom: 10px;
    }

    .service-card p {
        color: var(--gray);

        font-size: 0.9rem;

        line-height: 1.7;
    }


    /* =========================================================
       CONTACT
    ========================================================= */

    .contact {
        background: white;
    }

    .contact-grid {
        display: grid;

        grid-template-columns:
            0.85fr
            1.15fr;

        gap: 30px;
    }

    .contact-info {
        padding: 38px;

        border-radius: 22px;

        color: white;

        background:
            linear-gradient(
                135deg,
                var(--blue),
                var(--purple)
            );

        box-shadow: var(--shadow-lg);
    }

    .contact-info h3 {
        font-size: 1.7rem;

        margin-bottom: 10px;
    }

    .contact-info > p {
        color:
            rgba(255, 255, 255, 0.78);

        margin-bottom: 25px;
    }

    .contact-item {
        display: flex;

        align-items: center;

        gap: 14px;

        padding: 15px 0;

        border-bottom:
            1px solid
            rgba(255, 255, 255, 0.10);
    }

    .contact-item:last-of-type {
        border-bottom: 0;
    }

    .contact-icon {
        width: 45px;
        height: 45px;

        flex-shrink: 0;

        display: flex;

        align-items: center;
        justify-content: center;

        border-radius: 50%;

        background:
            rgba(255, 255, 255, 0.10);
    }

    .contact-label {
        display: block;

        font-size: 0.68rem;

        opacity: 0.6;

        text-transform: uppercase;
    }

    .contact-value {
        font-size: 0.92rem;

        font-weight: 700;
    }

    .contact-value a {
        color: var(--yellow);
    }

    .social-links {
        display: flex;

        gap: 10px;

        margin-top: 25px;
    }

    .social-links a {
        width: 42px;
        height: 42px;

        display: flex;

        align-items: center;
        justify-content: center;

        border-radius: 50%;

        background:
            rgba(255, 255, 255, 0.10);

        transition: var(--transition);
    }

    .social-links a:hover {
        background: var(--yellow);

        color: var(--dark);

        transform: translateY(-4px);
    }


    /* CONTACT FORM */

    .contact-form {
        padding: 38px;

        background: var(--light);

        border-radius: 22px;

        box-shadow: var(--shadow);
    }

    .contact-form h3 {
        color: var(--blue);

        font-size: 1.7rem;

        margin-bottom: 5px;
    }

    .contact-form > p {
        color: var(--gray);

        margin-bottom: 25px;
    }

    .form-row {
        display: grid;

        grid-template-columns:
            1fr
            1fr;

        gap: 18px;
    }

    .form-group {
        margin-bottom: 18px;
    }

    .form-group label {
        display: block;

        margin-bottom: 7px;

        color: var(--dark);

        font-size: 0.85rem;

        font-weight: 700;
    }

    .form-group input,
    .form-group textarea,
    .form-group select {
        width: 100%;

        padding: 13px 15px;

        border:
            1px solid var(--border);

        border-radius: 11px;

        background: white;

        outline: none;

        font-size: 0.92rem;

        transition: var(--transition);
    }

    .form-group input:focus,
    .form-group textarea:focus,
    .form-group select:focus {
        border-color: var(--blue);

        box-shadow:
            0 0 0 3px
            rgba(18, 59, 93, 0.08);
    }

    .form-group textarea {
        min-height: 130px;

        resize: vertical;
    }

    .submit-btn {
        width: 100%;

        border: 0;

        min-height: 54px;

        border-radius: 50px;

        background:
            linear-gradient(
                135deg,
                var(--blue),
                var(--purple)
            );

        color: white;

        font-weight: 800;

        cursor: pointer;

        transition: var(--transition);
    }

    .submit-btn:hover {
        transform: translateY(-3px);

        box-shadow:
            0 10px 25px
            rgba(18, 59, 93, 0.25);
    }


    /* =========================================================
       LOCATION
    ========================================================= */

    .location {
        padding-top: 0;

        background: var(--light);
    }

    .map-container {
        overflow: hidden;

        border-radius: 22px;

        box-shadow: var(--shadow-lg);

        background: white;
    }

    .map-container iframe {
        width: 100%;

        height: 430px;

        border: 0;

        display: block;
    }

    .location-details {
        display: grid;

        grid-template-columns:
            repeat(3, 1fr);

        gap: 10px;

        padding: 22px;
    }

    .location-item {
        display: flex;

        align-items: center;

        justify-content: center;

        gap: 9px;

        color: #52606d;

        font-weight: 600;

        font-size: 0.88rem;

        text-align: center;
    }

    .location-item i {
        color: var(--red);
    }


    /* =========================================================
       FOOTER
    ========================================================= */

    footer {
        background: var(--dark);

        color:
            rgba(255, 255, 255, 0.65);

        padding: 65px 0 25px;
    }

    .footer-grid {
        display: grid;

        grid-template-columns:
            1.3fr
            0.8fr
            0.8fr;

        gap: 60px;

        padding-bottom: 40px;
    }

    .footer-brand h3 {
        color: white;

        font-size: 1.6rem;

        margin-bottom: 12px;
    }

    .footer-brand h3 span {
        color: var(--yellow);
    }

    .footer-brand p {
        max-width: 450px;

        line-height: 1.8;

        font-size: 0.9rem;
    }

    .footer-column h4 {
        color: white;

        margin-bottom: 15px;

        font-size: 1rem;
    }

    .footer-links {
        list-style: none;
    }

    .footer-links li {
        margin-bottom: 8px;
    }

    .footer-links a {
        transition: var(--transition);
    }

    .footer-links a:hover {
        color: var(--yellow);
    }

    .footer-social {
        display: flex;

        gap: 10px;
    }

    .footer-social a {
        width: 40px;
        height: 40px;

        display: flex;

        align-items: center;
        justify-content: center;

        border-radius: 50%;

        background:
            rgba(255, 255, 255, 0.07);

        transition: var(--transition);
    }

    .footer-social a:hover {
        background: var(--yellow);

        color: var(--dark);

        transform: translateY(-3px);
    }

    .footer-bottom {
        padding-top: 22px;

        border-top:
            1px solid
            rgba(255, 255, 255, 0.08);

        text-align: center;

        font-size: 0.78rem;
    }

    .footer-bottom .highlight {
        color: var(--yellow);

        font-weight: 800;
    }


    /* =========================================================
       TOAST
    ========================================================= */

    .toast {
        position: fixed;

        left: 50%;
        bottom: 25px;

        transform:
            translate(-50%, 120px);

        opacity: 0;

        z-index: 10000;

        padding: 14px 22px;

        border-radius: 12px;

        background: var(--dark);

        color: white;

        box-shadow: var(--shadow-lg);

        border-left:
            4px solid var(--green);

        transition: 0.4s ease;

        max-width: 90%;

        text-align: center;

        font-size: 0.85rem;
    }

    .toast.show {
        transform:
            translate(-50%, 0);

        opacity: 1;
    }

    .toast.error {
        border-left-color: var(--red);
    }


    /* =========================================================
       RESPONSIVE - TABLET
    ========================================================= */

    @media (max-width: 900px) {

        .navbar {
            min-height: 68px;
        }

        .hamburger {
            display: block;
        }

        .nav-links {
            position: absolute;

            top: 68px;
            left: 0;

            width: 100%;

            display: none;

            flex-direction: column;

            align-items: stretch;

            padding: 12px;

            background:
                rgba(18, 59, 93, 0.98);

            box-shadow:
                0 10px 30px
                rgba(0, 0, 0, 0.18);
        }

        .nav-links.open {
            display: flex;
        }

        .nav-links a {
            display: block;

            padding: 13px 15px;
        }

        .hero {
            min-height: auto;

            padding:
                130px 0
                75px;
        }

        .hero-grid {
            grid-template-columns: 1fr;

            gap: 50px;
        }

        .hero-content {
            text-align: center;
        }

        .hero-description {
            margin-left: auto;
            margin-right: auto;
        }

        .hero-buttons {
            justify-content: center;
        }

        .hero-stats {
            justify-content: center;
        }

        .hero-visual {
            max-width: 650px;

            width: 100%;

            margin: auto;
        }

        .about-grid {
            grid-template-columns: 1fr;

            gap: 40px;
        }

        .about-image {
            max-width: 700px;

            margin: auto;

            width: 100%;
        }

        .contact-grid {
            grid-template-columns: 1fr;
        }

        .services-grid {
            grid-template-columns:
                repeat(2, 1fr);
        }

        .footer-grid {
            grid-template-columns:
                1fr 1fr;
        }

        .footer-brand {
            grid-column: 1 / -1;
        }
    }


    /* =========================================================
       RESPONSIVE - MOBILE
    ========================================================= */

    @media (max-width: 600px) {

        .container {
            width: 90%;
        }

        section {
            padding:
                70px 0;
        }

        .hero {
            padding:
                115px 0
                65px;
        }

        .hero h1 {
            font-size: 2.45rem;

            letter-spacing: -1px;
        }

        .hero-description {
            font-size: 0.94rem;
        }

        .hero-buttons {
            flex-direction: column;
        }

        .btn {
            width: 100%;
        }

        .hero-stats {
            gap: 25px;
        }

        .stat-number {
            font-size: 1.5rem;
        }

        .hero-card img {
            height: 260px;
        }

        .section-heading {
            margin-bottom: 38px;
        }

        .about-image img {
            height: 300px;
        }

        .about-image::after {
            width: 80px;
            height: 80px;
        }

        .features {
            grid-template-columns: 1fr;
        }

        .services-grid {
            grid-template-columns: 1fr;
        }

        .service-card {
            padding:
                28px 20px;
        }

        .contact-info,
        .contact-form {
            padding: 25px 20px;
        }

        .form-row {
            grid-template-columns: 1fr;
            gap: 0;
        }

        .map-container iframe {
            height: 300px;
        }

        .location-details {
            grid-template-columns: 1fr;

            padding: 20px;
        }

        .footer-grid {
            grid-template-columns: 1fr;

            gap: 35px;
        }

        .footer-brand {
            grid-column: auto;
        }
    }


    /* =========================================================
       SMALL MOBILE
    ========================================================= */

    @media (max-width: 380px) {

        .logo {
            font-size: 1rem;
        }

        .logo-icon {
            width: 38px;
            height: 38px;
        }

        .hero h1 {
            font-size: 2rem;
        }

        .hero-stats {
            gap: 17px;
        }

        .hero-card img {
            height: 220px;
        }
    }

</style>

Modified the code above to make page to use  two languages which is swahili and English changes and to put ones button if user clicks it's open direct to the link of https://drive.google.com/drive/folders/14i708FRvneNRfBEBI3WDnM0OMREu47zT 
And make the page to have a digital website like in a picture by addition 
