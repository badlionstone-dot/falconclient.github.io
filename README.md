# falconclient.github.io
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Falcon Client | Dominate the Game</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap');
        body { background-color: #050507; color: white; font-family: 'Inter', sans-serif; scroll-behavior: smooth; }
        .falcon-gradient { background: linear-gradient(90deg, #4da3ff 0%, #ffffff 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .hero-glow { background: radial-gradient(circle at center, #1a2a4a 0%, #050507 70%); }
        .btn-falcon { background: linear-gradient(135deg, #1e40af 0%, #3b82f6 100%); transition: transform 0.2s, box-shadow 0.2s; }
        .btn-falcon:hover { transform: scale(1.05); box-shadow: 0 0 20px rgba(59, 130, 246, 0.5); }
        .logo-img { border-radius: 50%; object-fit: cover; }
        .page-content { display: block; }
        #news-page { display: none; }
        
        /* Language Dropdown Style */
        .lang-dropdown { background: #0d0d10; border: 1px solid #333; border-radius: 12px; display: none; position: absolute; top: 120%; left: 0; min-width: 180px; z-index: 100; overflow: hidden; }
        .lang-option { transition: all 0.2s; color: #9ca3af; font-weight: bold; font-size: 0.75rem; letter-spacing: 0.1em; }
        .lang-option:hover { background: #1e40af; color: white; }
    </style>
</head>
<body>

    <nav class="flex items-center justify-between px-8 py-5 sticky top-0 bg-[#050507]/90 backdrop-blur-md z-50 border-b border-white/5">
        <div class="flex items-center space-x-6">
            <div class="flex items-center space-x-3 cursor-pointer" onclick="showHome()">
                <img src="https://cdn.discordapp.com/attachments/1476480553338409084/1493947660380540948/colorful-falcon-wing-logo-vector-44206163-photoaidcom-cropped.png?ex=69e0d2ae&is=69df812e&hm=32dbdbd6bd747f761b53f85d0ad7222d0b5aca1efa7fbc77896865d2961061ae&" alt="Falcon Logo" class="h-12 w-12 logo-img">
                <div class="text-xl font-black italic text-white uppercase tracking-tighter">FALCON<span class="text-blue-500">CLIENT</span></div>
            </div>

            <div class="relative">
                <button onclick="toggleLang()" class="flex items-center space-x-3 bg-white/5 px-4 py-2 rounded-lg border border-white/10 hover:border-blue-500/50 transition">
                    <span id="lang-label" class="text-xs font-black uppercase tracking-[0.2em] text-gray-300">LANGUAGE</span>
                    <span id="current-flag" class="text-lg">🇺🇸</span>
                    <i class="fa-solid fa-caret-down text-[10px] text-blue-500"></i>
                </button>
                <div id="lang-menu" class="lang-dropdown shadow-2xl">
                    <div onclick="changeLang('en', '🇺🇸')" class="lang-option p-3 cursor-pointer flex items-center space-x-3 border-b border-white/5 uppercase"><span>🇺🇸</span> <span>ENGLISH</span></div>
                    <div onclick="changeLang('bn', '🇧🇩')" class="lang-option p-3 cursor-pointer flex items-center space-x-3 border-b border-white/5 uppercase"><span>🇧🇩</span> <span>BANGLA</span></div>
                    <div onclick="changeLang('ar', '🇸🇦')" class="lang-option p-3 cursor-pointer flex items-center space-x-3 border-b border-white/5 uppercase"><span>🇸🇦</span> <span>ARABIC</span></div>
                    <div onclick="changeLang('ru', '🇷🇺')" class="lang-option p-3 cursor-pointer flex items-center space-x-3 border-b border-white/5 uppercase"><span>🇷🇺</span> <span>RUSSIAN</span></div>
                    <div onclick="changeLang('de', '🇩🇪')" class="lang-option p-3 cursor-pointer flex items-center space-x-3 border-b border-white/5 uppercase"><span>🇩🇪</span> <span>GERMAN</span></div>
                    <div onclick="changeLang('fr', '🇫🇷')" class="lang-option p-3 cursor-pointer flex items-center space-x-3 uppercase"><span>🇫🇷</span> <span>FRENCH</span></div>
                </div>
            </div>
        </div>

        <div class="hidden md:flex space-x-8 font-semibold text-sm uppercase tracking-widest text-gray-400">
            <a href="javascript:void(0)" onclick="showHome()" class="hover:text-white transition" id="nav-home">Home</a>
            <a href="javascript:void(0)" onclick="showNews()" class="hover:text-white transition uppercase" id="nav-news">NEWS</a>
            <a href="#faq-section" class="hover:text-white transition uppercase" id="nav-faq">FAQ</a>
            <a href="https://discord.gg/zVkaYcPhJs" target="_blank" class="hover:text-white transition font-bold" id="nav-discord">Discord</a>
        </div>
        <button class="btn-falcon px-8 py-2.5 rounded-md font-bold text-sm uppercase tracking-wider" id="btn-download">Download</button>
    </nav>

    <main id="home-page" class="page-content">
        <section class="hero-glow flex flex-col items-center justify-center text-center py-32 px-4">
            <img src="https://cdn.discordapp.com/attachments/1476480553338409084/1493947660380540948/colorful-falcon-wing-logo-vector-44206163-photoaidcom-cropped.png?ex=69e0d2ae&is=69df812e&hm=32dbdbd6bd747f761b53f85d0ad7222d0b5aca1efa7fbc77896865d2961061ae&" alt="Falcon Logo" class="h-48 w-48 mb-10 shadow-2xl rounded-full">
            <h1 class="text-6xl md:text-9xl font-black mb-6 tracking-tighter italic text-white uppercase leading-tight">
                <span class="falcon-gradient">FALCON CLIENT</span>
            </h1>
            <p id="hero-desc" class="text-gray-400 text-lg md:text-xl max-w-xl mb-10 leading-relaxed font-medium">
                The ultimate competitive Minecraft client. Optimized strictly for 1.8.9 for the best PvP experience.
            </p>
            <button class="bg-white text-black px-14 py-5 rounded-full font-black text-xl hover:bg-blue-50 transition flex items-center justify-center shadow-lg uppercase" id="hero-dl-btn">
                <i class="fa-brands fa-windows mr-3"></i> DOWNLOAD
            </button>
        </section>

        <section class="grid grid-cols-1 md:grid-cols-3 gap-0 border-y border-white/5 bg-[#08080a]">
            <div class="text-center py-16 border-r border-white/5">
                <div class="text-5xl font-black text-white mb-2">500+</div>
                <div id="stat-dl" class="text-blue-500 font-bold uppercase tracking-widest text-xs">Total Downloads</div>
            </div>
            <div class="text-center py-16 border-r border-white/5">
                <div class="text-5xl font-black text-white mb-2">1.8.9</div>
                <div id="stat-engine" class="text-blue-500 font-bold uppercase tracking-widest text-xs">Engine Version</div>
            </div>
            <div class="text-center py-16">
                <div class="text-5xl font-black text-white mb-2 flex justify-center items-center">
                    <span id="fps-counter">1</span><span>+</span>
                </div>
                <div id="stat-fps" class="text-blue-500 font-bold uppercase tracking-widest text-xs">FPS Boost</div>
            </div>
        </section>

        <section id="faq-section" class="py-24 bg-[#050507]">
            <div class="max-w-4xl mx-auto px-6">
                <h2 id="faq-header" class="text-5xl font-black mb-12 uppercase italic text-center">Frequently Asked <span class="text-blue-500">Questions</span></h2>
                <div class="space-y-6">
                    <div class="bg-[#0d0d10] border border-white/5 p-8 rounded-3xl border-l-4 border-l-blue-600 text-left">
                        <h4 class="text-blue-500 font-bold uppercase tracking-widest text-sm mb-2" id="q1">Is Falcon Client a hack client?</h4>
                        <p class="text-gray-400 text-lg" id="a1">No, Falcon Client is a performance-focused competitive client.</p>
                    </div>
                    <div class="bg-[#0d0d10] border border-white/5 p-8 rounded-3xl border-l-4 border-l-blue-600 text-left">
                        <h4 class="text-blue-500 font-bold uppercase tracking-widest text-sm mb-2" id="q2">Can I add my own mods?</h4>
                        <p class="text-gray-400 text-lg" id="a2">Yes, currently you can. But in the next update, adding external mods will not be possible.</p>
                    </div>
                    <div class="bg-[#0d0d10] border border-white/5 p-8 rounded-3xl border-l-4 border-l-blue-600 text-left">
                        <h4 class="text-blue-500 font-bold uppercase tracking-widest text-sm mb-2" id="q3">Does Falcon Client have a launcher?</h4>
                        <p class="text-gray-400 text-lg" id="a3">No, but a dedicated launcher is coming soon!</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <main id="news-page" class="page-content min-h-screen py-20 bg-[#050507]">
        <div class="max-w-4xl mx-auto px-6 text-center">
            <h2 id="news-title" class="text-5xl font-black mb-12 uppercase italic text-white">Latest <span class="text-blue-500">Updates</span></h2>
            <div class="bg-[#0d0d10] border border-white/5 p-10 rounded-3xl border-l-4 border-l-blue-600 inline-block text-left">
                <h3 id="news-mod-title" class="text-3xl font-bold mb-4 text-white uppercase tracking-tight">Mods are updated!</h3>
                <p id="news-mod-desc" class="text-gray-400 leading-relaxed text-lg">All internal mod engines are optimized for smoother gameplay.</p>
            </div>
        </div>
    </main>

    <footer class="bg-[#030305] py-20 px-10 text-center border-t border-white/5">
        <p class="text-gray-500 text-sm tracking-widest font-bold uppercase mb-4">&copy; 2026 FALCON CLIENT.</p>
        <a href="https://discord.gg/zVkaYcPhJs" target="_blank" class="bg-blue-600/10 text-blue-500 px-6 py-3 rounded-full border border-blue-500/20 hover:bg-blue-600 hover:text-white transition font-bold uppercase tracking-widest text-xs inline-flex items-center">
            <i class="fa-brands fa-discord mr-2 text-base"></i> <span id="footer-discord">Join our Discord</span>
        </a>
    </footer>

    <script>
        function animateFPS() {
            const counter = document.getElementById('fps-counter');
            let current = 1; const target = 999;
            const timer = setInterval(() => {
                const increment = Math.floor(Math.random() * 4) + 3;
                current += increment;
                if (current >= target) { counter.innerText = target; clearInterval(timer); }
                else { counter.innerText = current; }
            }, 20);
        }

        const translations = {
            en: { 
                langBtn: "LANGUAGE", home: "HOME", news: "NEWS", faq: "FAQ", discord: "DISCORD", download: "DOWNLOAD", 
                heroDesc: "The ultimate competitive Minecraft client. Optimized strictly for 1.8.9.", 
                statDl: "TOTAL DOWNLOADS", statEngine: "ENGINE VERSION", statFps: "FPS BOOST", 
                faqH: "FREQUENTLY ASKED QUESTIONS",
                q1: "Is Falcon Client a hack client?", a1: "No, Falcon Client is a performance client.",
                q2: "Can I add my own mods?", a2: "Yes, currently you can. Next update will not.",
                q3: "Does it have a launcher?", a3: "No, but a launcher is coming soon!",
                join: "JOIN OUR DISCORD", newsT: "LATEST UPDATES"
            },
            bn: { 
                langBtn: "LANGUAGE", home: "হোম", news: "নিউজ", faq: "প্রশ্নাবলী", discord: "ডিসকর্ড", download: "ডাউনলোড", 
                heroDesc: "সেরা প্রতিযোগিতামূলক মাইনক্রাফ্ট ক্লায়েন্ট। ১.৮.৯ এর জন্য তৈরি।", 
                statDl: "মোট ডাউনলোড", statEngine: "ইঞ্জিন ভার্সন", statFps: "এফপিএস বুস্ট", 
                faqH: "সাধারণ জিজ্ঞাসা",
                q1: "ফ্যালকন ক্লায়েন্ট কি হ্যাক ক্লায়েন্ট?", a1: "না, এটি একটি পারফরম্যান্স ভিত্তিক ক্লায়েন্ট।",
                q2: "মড যোগ করা যাবে?", a2: "হ্যাঁ, বর্তমানে পারবেন। তবে পরের আপডেটে পারবেন না।",
                q3: "লঞ্চার আছে?", a3: "না, তবে খুব শীঘ্রই আসছে!",
                join: "আমাদের ডিসকর্ড-এ যোগ দিন", newsT: "সর্বশেষ আপডেট"
            },
            ar: { 
                langBtn: "LANGUAGE", home: "الرئيسية", news: "أخبار", faq: "الأسئلة", discord: "ديسكورد", download: "تحميل", 
                heroDesc: "أفضل عميل ماين كرافت تنافسي. تم تحسينه لنسخة 1.8.9.", 
                statDl: "إجمالي التحميلات", statEngine: "نسخة المحرك", statFps: "تعزيز FPS", 
                faqH: "الأسئلة الشائعة",
                q1: "هل هو غش؟", a1: "لا، فالكون هو عميل لزيادة الأداء.",
                q2: "هل يمكنني إضافة مودات؟", a2: "نعم حالياً، ولكن التحديث القادم لن يدعم ذلك.",
                q3: "هل يوجد لانشر؟", a3: "لا، لكنه قادم قريباً!",
                join: "انضم إلى ديسكورد", newsT: "آخر التحديثات"
            },
            ru: { 
                langBtn: "LANGUAGE", home: "ГЛАВНАЯ", news: "НОВОСТИ", faq: "FAQ", discord: "ДИСКОРД", download: "СКАЧАТЬ", 
                heroDesc: "Лучший соревновательный клиент Minecraft. Оптимизирован для 1.8.9.", 
                statDl: "ЗАГРУЗОК", statEngine: "ВЕРСИЯ ДВИЖКА", statFps: "БУСТ FPS", 
                faqH: "ЧАСТО ЗАДАВАЕМЫЕ ВОПРОСЫ",
                q1: "Это чит-клиент?", a1: "Нет, Falcon — это клиент для производительности.",
                q2: "Можно добавить моды?", a2: "Да, сейчас можно. В следующем обновлении — нет.",
                q3: "Есть лаунчер?", a3: "Нет, но скоро появится!",
                join: "НАШ ДИСКОРД", newsT: "ПОСЛЕДНИЕ НОВОСТИ"
            },
            de: { 
                langBtn: "LANGUAGE", home: "START", news: "NEWS", faq: "FAQ", discord: "DISCORD", download: "DOWNLOAD", 
                heroDesc: "Der ultimative kompetitive Minecraft-Client. Optimiert für 1.8.9.", 
                statDl: "DOWNLOADS GESAMT", statEngine: "ENGINE VERSION", statFps: "FPS BOOST", 
                faqH: "HÄUFIG GESTELLTE FRAGEN",
                q1: "Ist es ein Hack-Client?", a1: "Nein, Falcon ist ein Performance-Client.",
                q2: "Kann ich Mods hinzufügen?", a2: "Ja, aktuell schon. Im nächsten Update nicht mehr.",
                q3: "Gibt es einen Launcher?", a3: "Nein, aber einer kommt bald!",
                join: "UNSER DISCORD", newsT: "NEUESTE UPDATES"
            },
            fr: { 
                langBtn: "LANGUAGE", home: "ACCUEIL", news: "INFOS", faq: "FAQ", discord: "DISCORD", download: "TÉLÉCHARGER", 
                heroDesc: "Le client Minecraft compétitif ultime. Optimisé pour 1.8.9.", 
                statDl: "TÉLÉCHARGEMENTS", statEngine: "VERSION MOTEUR", statFps: "BOOST FPS", 
                faqH: "QUESTIONS FRÉQUENTES",
                q1: "Est-ce un cheat?", a1: "Non, Falcon est un client de performance.",
                q2: "Puis-je ajouter des mods?", a2: "Oui actuellement. Pas dans la prochaine mise à jour.",
                q3: "Y a-t-il un launcher?", a3: "Non, mais il arrive bientôt!",
                join: "NOTRE DISCORD", newsT: "DERNIÈRES INFOS"
            }
        };

        function toggleLang() {
            const menu = document.getElementById('lang-menu');
            menu.style.display = menu.style.display === 'block' ? 'none' : 'block';
        }

        function changeLang(lang, flag) {
            document.getElementById('current-flag').innerText = flag;
            document.getElementById('lang-menu').style.display = 'none';
            const t = translations[lang] || translations['en'];
            
            // Buttons and Nav (Dropdown list items are NOT updated, staying in English)
            document.getElementById('lang-label').innerText = t.langBtn;
            document.getElementById('nav-home').innerText = t.home;
            document.getElementById('nav-news').innerText = t.news;
            document.getElementById('nav-faq').innerText = t.faq;
            document.getElementById('nav-discord').innerText = t.discord;
            document.getElementById('btn-download').innerText = t.download;
            document.getElementById('hero-dl-btn').innerHTML = `<i class="fa-brands fa-windows mr-3"></i> ${t.download}`;
            
            document.getElementById('hero-desc').innerText = t.heroDesc;
            document.getElementById('stat-dl').innerText = t.statDl;
            document.getElementById('stat-engine').innerText = t.statEngine;
            document.getElementById('stat-fps').innerText = t.statFps;
            document.getElementById('footer-discord').innerText = t.join;

            document.getElementById('faq-header').innerHTML = `${t.faqH.split(' ').slice(0,-1).join(' ')} <span class="text-blue-500">${t.faqH.split(' ').slice(-1)}</span>`;
            document.getElementById('q1').innerText = t.q1; document.getElementById('a1').innerText = t.a1;
            document.getElementById('q2').innerText = t.q2; document.getElementById('a2').innerText = t.a2;
            document.getElementById('q3').innerText = t.q3; document.getElementById('a3').innerText = t.a3;
        }

        function showNews() { document.getElementById('home-page').style.display = 'none'; document.getElementById('news-page').style.display = 'block'; window.scrollTo(0,0); }
        function showHome() { document.getElementById('home-page').style.display = 'block'; document.getElementById('news-page').style.display = 'none'; }
        
        window.onload = animateFPS;
        window.onclick = function(event) { if (!event.target.closest('.relative')) { document.getElementById('lang-menu').style.display = 'none'; } }
    </script>
</body>
</html>
