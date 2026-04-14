<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Butun dunyo tarixi | Umuminsoniy meros</title>
    <!-- Google Fonts va Font Awesome 6 (bepul ikonkalar) -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: #fef8f0;
            color: #2c2418;
            line-height: 1.5;
            scroll-behavior: smooth;
        }

        /* Asosiy konteyner */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* HEADER */
        .hero {
            background: linear-gradient(135deg, #1e2a3a 0%, #0f1a24 100%);
            color: #f3e9d2;
            padding: 4rem 0 5rem 0;
            text-align: center;
            border-bottom: 8px solid #c9a03d;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: "🌍";
            font-size: 14rem;
            opacity: 0.08;
            position: absolute;
            bottom: -40px;
            right: -30px;
            pointer-events: none;
        }

        .hero h1 {
            font-size: 3.3rem;
            letter-spacing: -0.02em;
            font-weight: 700;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.3);
        }

        .hero .sub {
            font-size: 1.2rem;
            max-width: 720px;
            margin: 0 auto;
            opacity: 0.9;
            font-weight: 400;
            background: rgba(0,0,0,0.3);
            display: inline-block;
            padding: 0.5rem 1.5rem;
            border-radius: 60px;
            backdrop-filter: blur(2px);
        }

        /* nav qisqa ichki havolalar */
        .era-nav {
            background: #fff6ea;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 1px solid #e6d5b8;
        }

        .nav-links {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0.5rem;
            padding: 0.8rem 1rem;
        }

        .nav-links a {
            background: transparent;
            color: #4a3722;
            text-decoration: none;
            font-weight: 600;
            padding: 0.5rem 1.2rem;
            border-radius: 40px;
            transition: all 0.2s ease;
            font-size: 0.9rem;
            letter-spacing: 0.3px;
            border: 1px solid #e2cfaa;
        }

        .nav-links a:hover {
            background: #c9a03d;
            color: white;
            border-color: #c9a03d;
            transform: translateY(-2px);
        }

        /* Asosiy bo'limlar */
        .section-title {
            font-size: 2.4rem;
            font-weight: 700;
            margin: 3rem 0 1rem 0;
            padding-bottom: 0.5rem;
            border-bottom: 4px solid #c9a03d;
            display: inline-block;
            color: #2c2418;
        }

        .timeline-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 2rem;
            margin: 2rem 0 3rem;
        }

        .history-card {
            background: white;
            border-radius: 28px;
            box-shadow: 0 12px 24px -12px rgba(0,0,0,0.15);
            overflow: hidden;
            transition: transform 0.25s ease, box-shadow 0.3s;
            border: 1px solid #f0e2cc;
        }

        .history-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 24px 32px -16px rgba(0,0,0,0.2);
        }

        .card-header {
            background: #2c3e2f;
            color: #fbf5e8;
            padding: 1rem 1.5rem;
            font-weight: 700;
            font-size: 1.4rem;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .card-header i {
            font-size: 1.8rem;
            color: #e6bc7e;
        }

        .card-body {
            padding: 1.5rem;
        }

        .date-range {
            font-family: monospace;
            background: #f6efdf;
            display: inline-block;
            padding: 0.2rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            color: #8b5a2b;
            margin-bottom: 0.8rem;
        }

        .card-body p {
            margin-bottom: 0.8rem;
            color: #3e2e1f;
        }

        .fact-highlight {
            background: #fef4e2;
            border-left: 5px solid #c9a03d;
            padding: 0.7rem 1rem;
            border-radius: 14px;
            font-size: 0.9rem;
            margin-top: 1rem;
            font-style: italic;
        }

        /* xronologik lenta (maxsus) */
        .timeline-horizontal {
            background: #e9ddce;
            border-radius: 48px;
            padding: 2rem 1.5rem;
            margin: 2rem 0;
            overflow-x: auto;
            white-space: nowrap;
            scrollbar-width: thin;
        }

        .timeline-steps {
            display: inline-flex;
            gap: 1.5rem;
            align-items: center;
        }

        .step {
            background: white;
            border-radius: 60px;
            padding: 0.8rem 1.5rem;
            display: inline-flex;
            flex-direction: column;
            align-items: center;
            min-width: 130px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: 0.2s;
        }

        .step .year {
            font-weight: 800;
            font-size: 1.2rem;
            color: #b36b1e;
        }

        .step .event {
            font-size: 0.8rem;
            font-weight: 500;
            color: #2c2418;
        }

        /* global statistika */
        .stats {
            background: #1f2a2e;
            color: #ffefcf;
            padding: 2rem;
            border-radius: 42px;
            margin: 3rem 0;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            text-align: center;
        }

        .stat-item {
            flex: 1;
            min-width: 140px;
            margin: 0.5rem;
        }

        .stat-number {
            font-size: 2.4rem;
            font-weight: 800;
            color: #e9bc6d;
        }

        /* footer */
        footer {
            background: #0f1a1f;
            color: #cfc5ae;
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
            font-size: 0.85rem;
            border-top: 2px solid #c9a03d;
        }

        /* Responsive */
        @media (max-width: 800px) {
            .container {
                padding: 0 1.2rem;
            }
            .hero h1 {
                font-size: 2.2rem;
            }
            .section-title {
                font-size: 1.8rem;
            }
            .timeline-grid {
                grid-template-columns: 1fr;
            }
        }

        button.scroll-top {
            position: fixed;
            bottom: 24px;
            right: 24px;
            background: #c9a03d;
            border: none;
            color: white;
            width: 48px;
            height: 48px;
            border-radius: 30px;
            font-size: 1.5rem;
            cursor: pointer;
            opacity: 0;
            transition: 0.2s;
            box-shadow: 0 4px 12px black;
            z-index: 99;
        }

        button.scroll-top.show {
            opacity: 1;
        }
    </style>
</head>
<body>

<header class="hero">
    <div class="container">
        <h1>🌐 Butun dunyo tarixi</h1>
        <div class="sub">Insoniyat sivilizatsiyasining to‘liq xronikasi — qadimdan hozirgacha</div>
        <p style="margin-top: 1.5rem; max-width: 700px; margin-left: auto; margin-right: auto; font-size: 1rem;">Arxeologik topilmalardan tortib, global ittifoqlargacha. Ming yilliklar davomidagi eng muhim voqealar, madaniyatlar va kashfiyotlar.</p>
    </div>
</header>

<div class="era-nav">
    <div class="container nav-links">
        <a href="#antiquity"><i class="fas fa-landmark"></i> Qadimgi dunyo</a>
        <a href="#medieval"><i class="fas fa-chess-knight"></i> O‘rta asrlar</a>
        <a href="#modern"><i class="fas fa-globe-americas"></i> Yangi davr</a>
        <a href="#contemporary"><i class="fas fa-microchip"></i> Zamonaviy tarix</a>
        <a href="#timeline"><i class="fas fa-chart-line"></i> Xronologik lenta</a>
    </div>
</div>

<main class="container">
    <!-- QADIMGI DUNYO -->
    <h2 id="antiquity" class="section-title"><i class="fas fa-pyramid"></i> Qadimgi dunyo (mil.avv. 3500 – mil.476)</h2>
    <div class="timeline-grid">
        <div class="history-card">
            <div class="card-header"><i class="fas fa-palette"></i> Shumerlar</div>
            <div class="card-body">
                <div class="date-range">≈ mil.avv. 3500</div>
                <p>Eng qadimgi sivilizatsiyalardan biri — Mesopotamiyada yozuv (mixxat), g‘ildirak va qonunlarning dastlabki shakllari.</p>
                <div class="fact-highlight">📜 “Gilam” lagash shahri, birinchi yozma qonunlar.</div>
            </div>
        </div>
        <div class="history-card">
            <div class="card-header"><i class="fas fa-eye"></i> Qadimgi Misr</div>
            <div class="card-body">
                <div class="date-range">mil.avv. 3100 – 30</div>
                <p>Fir'avnlar davri, piramidalar, ieroglif yozuvi, tibbiyot va astronomiyada ulkan yutuqlar.</p>
                <div class="fact-highlight">🏺 Xeops piramidasi 4500 yildan oshgan.</div>
            </div>
        </div>
        <div class="history-card">
            <div class="card-header"><i class="fas fa-dragon"></i> Indus vodiysi</div>
            <div class="card-body">
                <div class="date-range">mil.avv. 2600 – 1900</div>
                <p>Mohenjo-Daro va Xarappa — rejali shaharlar, kanalizatsiya tizimi va savdo aloqalari.</p>
                <div class="fact-highlight">🏛️ Dunyodagi birinchi gigiyena tizimlaridan biri.</div>
            </div>
        </div>
        <div class="history-card">
            <div class="card-header"><i class="fas fa-university"></i> Qadimgi Xitoy</div>
            <div class="card-body">
                <div class="date-range">mil.avv. 2070 – 220</div>
                <p>Shang sulolasi, Konfutsiy, Buyuk ipak yo‘li, qog‘oz va poroxning dastlabki kashfiyoti.</p>
                <div class="fact-highlight">🐉 Birinchi imperator Tsin Shixuandi — terrakota armiyasi.</div>
            </div>
        </div>
        <div class="history-card">
            <div class="card-header"><i class="fas fa-archway"></i> Yunoniston & Ellinizm</div>
            <div class="card-body">
                <div class="date-range">mil.avv. 800 – 146</div>
                <p>Demokratiya, falsafa (Sokrat, Platon, Aristotel), Olimpiya o‘yinlari, Aleksandr Makedonskiy.</p>
                <div class="fact-highlight">🏺 Parthenon, Yevropa tamal toshi.</div>
            </div>
        </div>
        <div class="history-card">
            <div class="card-header"><i class="fas fa-shield-alt"></i> Rim imperiyasi</div>
            <div class="card-body">
                <div class="date-range">mil.avv. 753 – mil.476</div>
                <p>Huquq tizimi (Rim huquqi), beton, akveduklar, lotin tili va nasroniylikning tarqalishi.</p>
                <div class="fact-highlight">🏛️ “Senatus Populusque Romanus” — G‘arb sivilizatsiyasining asosi.</div>
            </div>
        </div>
    </div>

    <!-- O‘RTA ASRLAR -->
    <h2 id="medieval" class="section-title"><i class="fas fa-castle"></i> O‘rta asrlar (476 – 1492)</h2>
    <div class="timeline-grid">
        <div class="history-card">
            <div class="card-header"><i class="fas fa-church"></i> Vizantiya imperiyasi</div>
            <div class="card-body"><div class="date-range">330 – 1453</div><p>Konstantinopol, Yustiniana kodeksi, pravoslavlik, slavyan alifbosi (Kirill va Mefodiy).</p><div class="fact-highlight">⛪ Ayasofya — 1000 yil davomida dunyodagi eng katta sobor.</div></div>
        </div>
        <div class="history-card">
            <div class="card-header"><i class="fas fa-moon"></i> Islom oltin asri</div>
            <div class="card-body"><div class="date-range">750 – 1258</div><p>Bag‘doddagi Hikmat uyi, algebra, astronomiya, tibbiyot, Ibn Sino, al-Xorazmiy.</p><div class="fact-highlight">📚 Raqamlarni “0” bilan ishlatish va algebra asoslari.</div></div>
        </div>
        <div class="history-card">
            <div class="card-header"><i class="fas fa-feather-alt"></i> Mo'g‘ullar imperiyasi</div>
            <div class="card-body"><div class="date-range">1206 – 1368</div><p>Chingizxon va uning vorislari — Yevroosiyoning katta qismini birlashtirgan eng ulkan quruqlik imperiyasi.</p><div class="fact-highlight">🏇 Pax Mongolica: Xavfsiz savdo va madaniyatlar almashinuvi.</div></div>
        </div>
        <div class="history-card">
            <div class="card-header"><i class="fas fa-crown"></i> Yevropa feodalizmi</div>
            <div class="card-body"><div class="date-range">500 – 1400</div><p>Ritsarlar, qal'alar, salib yurishlari, Magna Carta (1215) va universitetlarning paydo bo‘lishi.</p><div class="fact-highlight">📖 Parij va Oksford universitetlari – bilim markazlari.</div></div>
        </div>
        <div class="history-card">
            <div class="card-header"><i class="fas fa-fish"></i> Kichik muzlik davri & Qora o‘lim</div>
            <div class="card-body"><div class="date-range">1347 – 1351</div><p>Vabo pandemiyasi Yevropada 25–30 million kishining hayotiga zomin bo‘ldi, ijtimoiy o‘zgarishlarni tezlatdi.</p><div class="fact-highlight">⚰️ Oqibatda ishchi kuchi taqchilligi va ijtimoiy harakatlar kuchaydi.</div></div>
        </div>
    </div>

    <!-- YANGI DAVR -->
    <h2 id="modern" class="section-title"><i class="fas fa-ship"></i> Yangi davr (1492 – 1914)</h2>
    <div class="timeline-grid">
        <div class="history-card"><div class="card-header"><i class="fas fa-compass"></i> Buyuk geografik kashfiyotlar</div><div class="card-body"><div class="date-range">1492 – 1522</div><p>Kolumb Amerika, Magellan – dunyo aylanib chiqish, Vasko da Gama Hindistonga dengiz yo‘li.</p><div class="fact-highlight">🌎 Yer sharining globallashuvi boshlanishi.</div></div></div>
        <div class="history-card"><div class="card-header"><i class="fas fa-lightbulb"></i> Uyg‘onish davri</div><div class="card-body"><div class="date-range">1300 – 1600</div><p>Leonardo da Vinchi, Mikelanjelo, Rafael, Gutenbergning bosmaxonasi – ma’rifat va san’at gullashi.</p><div class="fact-highlight">📖 1455 yil: Gutenberg Injili – matbaa inqilobi.</div></div></div>
        <div class="history-card"><div class="card-header"><i class="fas fa-microscope"></i> Ilmiy inqilob</div><div class="card-body"><div class="date-range">1543 – 1687</div><p>Kopernik, Galiley, Kepler, Nyuton – fizika va astronomiyada yangi dunyoqarash.</p><div class="fact-highlight">🍎 Nyuton: “Philosophiæ Naturalis Principia Mathematica”.</div></div></div>
        <div class="history-card"><div class="card-header"><i class="fas fa-gavel"></i> Fransuz inqilobi & Napoleon</div><div class="card-body"><div class="date-range">1789 – 1815</div><p>“Erkinlik, tenglik, birodarlik”, Inson va fuqaro huquqlari deklaratsiyasi, Yevropada millatchilik.</p><div class="fact-highlight">⚜️ Napoleon kodeksi ko‘plab mamlakatlar huquq tizimiga ta’sir qildi.</div></div></div>
        <div class="history-card"><div class="card-header"><i class="fas fa-industry"></i> Sanoat inqilobi</div><div class="card-body"><div class="date-range">1760 – 1840</div><p>Bug‘ mashinasi, temir yo‘llar, fabrikalar, urbanizatsiya va kapitalizmning yuksalishi.</p><div class="fact-highlight">🏭 Dunyo ishlab chiqarish quvvati 10 barobar oshdi.</div></div></div>
    </div>

    <!-- ZAMONAVIY TARIX (XX-XXI asr) -->
    <h2 id="contemporary" class="section-title"><i class="fas fa-microchip"></i> Zamonaviy tarix (1914 – bugun)</h2>
    <div class="timeline-grid">
        <div class="history-card"><div class="card-header"><i class="fas fa-bomb"></i> Birinchi jahon urushi</div><div class="card-body"><div class="date-range">1914 – 1918</div><p>Antanta va Markaziy kuchlar; 20 milliondan ortiq qurbonlar; imperiyalar qulashi (Usmonli, Avstriya-Vengriya).</p><div class="fact-highlight">🕊️ Millatlar ligasi tashkil topdi (BMTning salafi).</div></div></div>
        <div class="history-card"><div class="card-header"><i class="fas fa-chart-line"></i> Ikkinchi jahon urushi & Xolokost</div><div class="card-body"><div class="date-range">1939 – 1945</div><p>70–85 million o‘lim, atom bombasi, BMT tashkil etilishi, dekolonizatsiya boshlanishi.</p><div class="fact-highlight">☮️ 1945: BMT Nizomi imzolandi.</div></div></div>
        <div class="history-card"><div class="card-header"><i class="fas fa-satellite"></i> Sovuq urush & Kosmik poyga</div><div class="card-body"><div class="date-range">1947 – 1991</div><p>Yadro qurollanishi, Koreya urushi, Vetnam, Oyga qo‘nish (1969), Berlin devori qulashi.</p><div class="fact-highlight">🚀 “Kichkina qadam...” – Nil Armstrong.</div></div></div>
        <div class="history-card"><div class="card-header"><i class="fas fa-laptop-code"></i> Raqamli inqilob</div><div class="card-body"><div class="date-range">1970 – hozirgacha</div><p>Internet, sun’iy intellekt, mobil texnologiyalar, global axborot jamiyati.</p><div class="fact-highlight">📡 1991: World Wide Web (Tim Berners-Lee).</div></div></div>
        <div class="history-card"><div class="card-header"><i class="fas fa-hand-holding-heart"></i> XXI asr muammolari</div><div class="card-body"><div class="date-range">2001 – ...</div><p>Iqlim o‘zgarishi, terrorizm, COVID-19 pandemiyasi, sun’iy intellekt va sun’iy biologiya.</p><div class="fact-highlight">🌱 Barqaror rivojlanish maqsadlari (UN 2030).</div></div></div>
    </div>

    <!-- XRONOLOGIK LENTA (gorizontal) -->
    <h2 id="timeline" class="section-title"><i class="fas fa-hourglass-half"></i> Xronologik lenta — asosiy bosqichlar</h2>
    <div class="timeline-horizontal">
        <div class="timeline-steps">
            <div class="step"><span class="year">~3300 BCE</span><span class="event">Mixxat, Shumer</span></div>
            <div class="step"><span class="year">~2560 BCE</span><span class="event">Buyuk piramida</span></div>
            <div class="step"><span class="year">776 BCE</span><span class="event">Birinchi Olimpiada</span></div>
            <div class="step"><span class="year">221 BCE</span><span class="event">Xitoy birlashadi</span></div>
            <div class="step"><span class="year">476 CE</span><span class="event">G‘arbiy Rim quladi</span></div>
            <div class="step"><span class="year">622 CE</span><span class="event">Hijra (Islom taqvimi)</span></div>
            <div class="step"><span class="year">1096</span><span class="event">Birinchi salib yurishi</span></div>
            <div class="step"><span class="year">1215</span><span class="event">Magna Carta</span></div>
            <div class="step"><span class="year">1348</span><span class="event">Qora o‘lim</span></div>
            <div class="step"><span class="year">1453</span><span class="event">Konstantinopol qulashi</span></div>
            <div class="step"><span class="year">1492</span><span class="event">Kolumb Amerikada</span></div>
            <div class="step"><span class="year">1776</span><span class="event">AQSH mustaqilligi</span></div>
            <div class="step"><span class="year">1789</span><span class="event">Fransuz inqilobi</span></div>
            <div class="step"><span class="year">1914</span><span class="event">Birinchi jahon urushi</span></div>
            <div class="step"><span class="year">1945</span><span class="event">BMT tashkil topdi</span></div>
            <div class="step"><span class="year">1969</span><span class="event">Oyga qo‘nish</span></div>
            <div class="step"><span class="year">1991</span><span class="event">SSSR parchalanishi</span></div>
            <div class="step"><span class="year">2020</span><span class="event">COVID-19 pandemiyasi</span></div>
        </div>
    </div>

    <!-- global statistika bloki (interaktiv) -->
    <div class="stats" id="statsBlock">
        <div class="stat-item"><div class="stat-number" id="totalCivs">+34</div><div>Asosiy sivilizatsiyalar</div></div>
        <div class="stat-item"><div class="stat-number" id="totalEvents">~127</div><div>Muhim tarixiy voqealar</div></div>
        <div class="stat-item"><div class="stat-number" id="globalWar">2</div><div>Jahon urushlari</div></div>
        <div class="stat-item"><div class="stat-number" id="yearsSpan">~5300+</div><div>Yillik tarix</div></div>
    </div>

    <p style="text-align: center; font-style: italic; margin-top: 1rem;">✨ Butun insoniyat xotirasi — ming yillar davomidagi bilim, kurash va madaniyatlarning kesishmasi.</p>
</main>

<footer>
    <p><i class="fas fa-globe-asia"></i> Butun dunyo tarixi — umumiy meros | Ma'lumotlar ochiq manbalardan, arxeologiya va tarixiy tadqiqotlar asosida.</p>
    <p style="margin-top: 0.5rem;">© 2025 | Insoniyat sivilizatsiyasining to‘liq xronikasi | Barcha davrlar va qitʼalar birlashtirilgan</p>
</footer>

<button class="scroll-top" id="scrollTopBtn"><i class="fas fa-arrow-up"></i></button>

<script>
    // Scroll to top tugmasi
    const scrollBtn = document.getElementById('scrollTopBtn');
    window.addEventListener('scroll', () => {
        if (window.scrollY > 500) {
            scrollBtn.classList.add('show');
        } else {
            scrollBtn.classList.remove('show');
        }
    });
    scrollBtn.addEventListener('click', () => {
        window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    // Navbar ichidagi havolalarni silliq aylantirish
    document.querySelectorAll('.nav-links a, .hero .container .sub, .section-title a').forEach(anchor => {
        if(anchor.hash && anchor.hash.startsWith("#")){
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                if(targetId && targetId !== "#"){
                    const targetElem = document.querySelector(targetId);
                    if(targetElem){
                        targetElem.scrollIntoView({ behavior: 'smooth', block: 'start' });
                    }
                }
            });
        }
    });

    // Qo'shimcha interaktiv: statistik raqamlarni biroz jonlantirish (har bir kartani hisobga olib emas, faqat dekorativ)
    // Statlarni dinamik yangilash yoki hover effekt (faqat ko'rinish uchun)
    const statNumbers = document.querySelectorAll('.stat-number');
    function animateStats() {
        // oddiy animatsiya - raqamlar o'zgaradi hisoblanmaydi, shunchaki joziba uchun
        // lekin haqiqiy ma'lumotlar mavjud, qayta yozmaymiz
        // hech qanday murakkab API kerak emas, faqat statik
    }
    // Hover effekti kartochkalarda
    const cards = document.querySelectorAll('.history-card');
    cards.forEach(card => {
        card.addEventListener('mouseenter', () => {
            card.style.transition = "transform 0.2s";
        });
    });
    // Saytga kirganda birinchi bo'limga animatsion o'tish yo'q, ammo foydalanuvchi tajribasi yaxshi.
    // Qo'shimcha ravishda asrlar bo'yicha qisqacha joriy yil ko'rsatish?
    console.log("Butun dunyo tarixi sayti ishga tushdi | Umuminsoniy xotira");
    
    // Kartochkalarga yangi ma'lumotlar yuklash yoki qo'shimcha funksiya kerak emas, hamma narsa to'liq.
    // Matnlar butun dunyo tarixining muhim bosqichlarini qamrab oladi.
    // Jami 20+ karta, 4 asosiy davr, gorizontal lenta, statistika bloki.
    // Responsive dizayn va zamonaviy ko'rinish.
</script>
</body>
</html>
