<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>MYK — Mehmet Yalçınkaya</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600&family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400&display=swap" rel="stylesheet">

<style>
:root{
 --gold:#c9a66b;
 --gold2:#ead4a7;
 --black:#070707;
 --white:#f7f3ec;
 --muted:#9b9b9b;
}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{
 background:var(--black);
 color:white;
 font-family:"DM Sans",sans-serif;
 overflow-x:hidden;
}
a{text-decoration:none;color:inherit}
button,input,select{font:inherit}

/* LOADER */
.loader{
 position:fixed;inset:0;background:#050505;z-index:99999;
 display:grid;place-items:center;
 transition:1s ease;
}
.loader.hide{opacity:0;visibility:hidden}
.loader-box{text-align:center}
.loader-logo{
 font:400 60px "Playfair Display",serif;
 letter-spacing:14px;
}
.loader-line{
 width:0;height:1px;background:var(--gold);
 margin:24px auto;
 animation:loader 1.6s forwards;
}
.loader-text{
 font-size:9px;letter-spacing:5px;color:#777
}
@keyframes loader{to{width:210px}}

/* NAV */
nav{
 position:fixed;top:0;left:0;width:100%;height:90px;
 padding:0 5vw;display:flex;align-items:center;
 justify-content:space-between;z-index:1000;
 transition:.5s;
}
nav.scrolled{
 height:70px;background:rgba(5,5,5,.8);
 backdrop-filter:blur(20px);
 border-bottom:1px solid rgba(255,255,255,.08);
}
.logo{
 font:500 25px "Playfair Display",serif;
 letter-spacing:7px;
}
.logo b{color:var(--gold)}
.nav-links{
 display:flex;gap:32px;list-style:none;
}
.nav-links a{
 font-size:10px;letter-spacing:2px;color:#ccc;
 transition:.3s
}
.nav-links a:hover{color:var(--gold)}
.reserve-nav{
 padding:13px 20px;
 border:1px solid rgba(201,166,107,.7);
 font-size:10px;letter-spacing:2px;
 transition:.3s;
}
.reserve-nav:hover{background:var(--gold);color:#000}

/* HERO */
.hero{
 height:125vh;min-height:780px;
 position:relative;overflow:hidden;
}
.hero-bg{
 position:absolute;inset:0;
 background-position:center;
 background-size:cover;
}
.hero-outside{
 background-image:
 linear-gradient(rgba(0,0,0,.15),rgba(0,0,0,.75)),
 url("https://images.unsplash.com/photo-1515003197210-e0cd71810b5f?auto=format&fit=crop&w=2400&q=90");
 transform:scale(1.05);
}
.hero-inside{
 background-image:
 linear-gradient(rgba(0,0,0,.15),rgba(0,0,0,.8)),
 url("https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=2400&q=90");
 opacity:0;
 transform:scale(1.3);
}
.hero video{
 position:absolute;inset:0;width:100%;height:100%;
 object-fit:cover;opacity:.45;z-index:1;
}
.hero:after{
 content:"";position:absolute;inset:0;z-index:2;
 background:linear-gradient(to bottom,transparent 45%,rgba(0,0,0,.95));
}
.hero-content{
 position:absolute;z-index:5;
 left:8vw;bottom:17vh;
 max-width:900px;
 transition:transform .2s;
}
.kicker{
 color:var(--gold);font-size:10px;
 letter-spacing:5px;margin-bottom:25px;
}
.hero h1{
 font:400 clamp(60px,9vw,135px)/.88 "Playfair Display",serif;
}
.hero h1 em{color:var(--gold)}
.hero-copy{
 margin-top:35px;color:#d1d1d1;
 max-width:560px;line-height:1.9;font-size:14px;
}
.buttons{display:flex;gap:14px;margin-top:35px}
.btn{
 display:inline-block;padding:17px 27px;
 border:1px solid rgba(255,255,255,.35);
 font-size:10px;letter-spacing:2px;
 transition:.35s;
}
.btn.gold{background:var(--gold);border-color:var(--gold);color:#080808}
.btn:hover{transform:translateY(-3px);background:white;color:#000}
.scroll{
 position:absolute;right:5vw;bottom:45px;z-index:5;
 writing-mode:vertical-rl;
 color:#999;font-size:8px;letter-spacing:4px
}
.scroll:before{
 content:"";display:block;width:1px;height:65px;
 background:linear-gradient(var(--gold),transparent);
 margin:0 auto 14px;
}

/* GENERAL */
.section{padding:150px 8vw}
.grid{
 display:grid;grid-template-columns:1fr 1fr;
 gap:90px;align-items:center;
}
.label{
 color:var(--gold);font-size:9px;
 letter-spacing:4px;margin-bottom:24px;
}
.title{
 font:400 clamp(45px,6vw,82px)/.95 "Playfair Display",serif;
}
.title em{color:var(--gold)}
.text{
 color:#999;line-height:2;margin-top:30px;
 max-width:580px;font-size:14px;
}

/* STORY */
.story{
 background:
 radial-gradient(circle at 80% 20%,rgba(201,166,107,.1),transparent 30%),
 #080808;
}
.story-image{
 height:650px;
 background:
 linear-gradient(to bottom,transparent,rgba(0,0,0,.5)),
 url("https://images.unsplash.com/photo-1414235077428-338989a2e8c0?auto=format&fit=crop&w=1500&q=90")
 center/cover;
 position:relative;
}
.story-number{
 position:absolute;right:25px;bottom:20px;
 font:400 65px "Playfair Display",serif;
 color:rgba(255,255,255,.15);
}

/* CARDS */
.experience{background:#0d0d0d}
.cards{
 margin-top:80px;
 display:grid;grid-template-columns:repeat(3,1fr);gap:18px;
}
.card{
 height:540px;position:relative;overflow:hidden
}
.card img{
 width:100%;height:100%;object-fit:cover;
 transition:1s
}
.card:hover img{transform:scale(1.08)}
.card:after{
 content:"";position:absolute;inset:0;
 background:linear-gradient(transparent 30%,rgba(0,0,0,.9))
}
.card-content{
 position:absolute;z-index:2;bottom:32px;left:28px;right:28px
}
.card-content h3{
 font:400 31px "Playfair Display",serif
}
.card-content p{color:#bbb;font-size:12px;line-height:1.7;margin-top:8px}

/* INGREDIENT ANIMATION */
.transform{
 min-height:190vh;
 background:
 radial-gradient(circle at center,rgba(201,166,107,.1),transparent 35%),
 #060606;
}
.sticky{
 position:sticky;top:0;height:100vh;
 display:grid;place-items:center;overflow:hidden
}
.transform-heading{
 position:absolute;top:13%;text-align:center;z-index:5
}
.transform-heading h2{
 font:400 clamp(45px,7vw,90px)/.9 "Playfair Display",serif
}
.transform-heading p{
 margin-top:15px;color:#777;
 font-size:9px;letter-spacing:3px
}
.plate{
 width:min(470px,75vw);aspect-ratio:1;
 border-radius:50%;
 position:relative;
 background:radial-gradient(circle,#181818 0 47%,#d6d0c5 48% 51%,#eeeae3 52%);
 box-shadow:0 60px 100px rgba(0,0,0,.8);
 transform:scale(.65);
 opacity:.25;
}
.plate:after{
 content:"";position:absolute;inset:16%;
 border:1px solid rgba(0,0,0,.2);border-radius:50%
}
.ingredient{
 position:absolute;width:75px;height:75px;border-radius:50%;
 background-position:center;background-size:cover;
 box-shadow:0 20px 35px rgba(0,0,0,.65)
}
.a{left:7%;top:18%;background-image:url("https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=300&q=85")}
.b{right:7%;top:20%;background-image:url("https://images.unsplash.com/photo-1512621776951-a57141f2eefd?auto=format&fit=crop&w=300&q=85")}
.c{left:10%;bottom:15%;background-image:url("https://images.unsplash.com/photo-1498837167922-ddd27525d352?auto=format&fit=crop&w=300&q=85")}
.d{right:10%;bottom:13%;background-image:url("https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=300&q=85")}
.food-final{
 position:absolute;inset:17%;border-radius:50%;overflow:hidden;
 opacity:0;transform:scale(.5)
}
.food-final img{width:100%;height:100%;object-fit:cover}

/* DISHES */
.dishes{
 background:#eee8df;color:#111
}
.dishes .label{color:#96733d}
.dishes .title em{color:#96733d}
.dish-grid{
 margin-top:80px;
 display:grid;grid-template-columns:repeat(3,1fr);gap:22px
}
.dish{
 background:#fff;overflow:hidden
}
.dish:nth-child(2){transform:translateY(70px)}
.dish:nth-child(3){transform:translateY(140px)}
.dish img{
 width:100%;height:470px;object-fit:cover;
 transition:1s
}
.dish:hover img{transform:scale(1.06)}
.dish-info{padding:24px}
.dish-info h3{
 font:400 28px "Playfair Display",serif
}
.dish-info p{color:#777;font-size:12px;margin-top:8px}

/* CHEF */
.chef{background:#090909}
.chef-image{
 height:700px;
 background:
 linear-gradient(to right,rgba(0,0,0,.8),transparent),
 url("https://images.unsplash.com/photo-1577219491135-ce391730fb2c?auto=format&fit=crop&w=1500&q=90")
 center/cover
}

/* CINEMA */
.cinema{
 height:100vh;min-height:700px;
 display:grid;place-items:center;text-align:center;
 background:
 linear-gradient(rgba(0,0,0,.25),rgba(0,0,0,.85)),
 url("https://images.unsplash.com/photo-1559339352-11d035aa65de?auto=format&fit=crop&w=2400&q=90")
 center/cover fixed;
}
.cinema h2{
 font:400 clamp(55px,9vw,125px)/.85 "Playfair Display",serif
}
.cinema em{color:var(--gold)}
.cinema p{
 margin-top:25px;color:#bbb;
 font-size:10px;letter-spacing:4px
}

/* MENU */
.menu{background:#101010}
.menu-list{max-width:900px;margin:75px auto 0}
.menu-item{
 display:flex;justify-content:space-between;
 padding:28px 0;border-bottom:1px solid #252525;
 gap:30px
}
.menu-item h3{
 font:400 25px "Playfair Display",serif
}
.menu-item p{font-size:11px;color:#777;margin-top:7px}
.menu-tag{color:var(--gold);font-size:10px;white-space:nowrap}

/* RESERVATION */
.reservation{
 background:
 radial-gradient(circle at center top,rgba(201,166,107,.12),transparent 40%),
 #070707
}
.reservation-box{
 max-width:850px;margin:auto;text-align:center
}
.form{
 margin-top:55px;
 display:grid;grid-template-columns:1fr 1fr;gap:13px
}
.form input,.form select{
 width:100%;padding:18px;
 background:#121212;border:1px solid #292929;
 color:#fff;outline:0
}
.form input:focus,.form select:focus{border-color:var(--gold)}
.form .wide{grid-column:1/-1}
.form button{
 grid-column:1/-1;padding:19px;
 border:0;background:var(--gold);color:#000;
 cursor:pointer;letter-spacing:2px;font-size:10px
}

/* CONTACT */
.contact{background:#eee8df;color:#111}
.contact .label{color:#96733d}
.contact-info{margin-top:35px}
.contact-line{
 padding:19px 0;border-bottom:1px solid rgba(0,0,0,.14);
 line-height:1.7
}
.contact-line span{
 display:block;color:#888;font-size:9px;
 letter-spacing:2px;margin-bottom:5px
}
.contact-line a{color:#111}
.map{
 min-height:500px;
 background:
 linear-gradient(rgba(0,0,0,.25),rgba(0,0,0,.65)),
 url("https://images.unsplash.com/photo-1552566626-52f8b828add9?auto=format&fit=crop&w=1500&q=90")
 center/cover;
 display:grid;place-items:center
}
.map a{
 background:#fff;color:#111;padding:17px 23px;
 font-size:9px;letter-spacing:2px
}

/* FOOTER */
footer{
 background:#050505;padding:75px 8vw 25px
}
.footer-top{
 display:flex;justify-content:space-between;gap:40px
}
.footer-logo{
 font:400 48px "Playfair Display",serif;
 letter-spacing:5px
}
.footer-logo b{color:var(--gold)}
.footer-links{display:flex;gap:25px;color:#777;font-size:10px}
.footer-bottom{
 margin-top:75px;padding-top:22px;
 border-top:1px solid #222;
 display:flex;justify-content:space-between;
 color:#555;font-size:9px
}

/* FLOAT */
.float{
 position:fixed;right:22px;bottom:22px;z-index:900;
 width:62px;height:62px;border-radius:50%;
 background:var(--gold);color:#000;
 display:grid;place-items:center;text-align:center;
 font-size:8px;line-height:1.4;
 box-shadow:0 15px 40px #000;
 transition:.3s
}
.float:hover{transform:scale(1.1)}

/* REVEAL */
.reveal{
 opacity:0;transform:translateY(45px);
 transition:1s cubic-bezier(.2,.7,.2,1)
}
.reveal.active{opacity:1;transform:none}

/* MOBILE */
@media(max-width:800px){
 nav{height:70px;padding:0 20px}
 .nav-links{display:none}
 .logo{font-size:19px}
 .reserve-nav{padding:10px 13px}
 .hero{height:100vh;min-height:720px}
 .hero-content{left:25px;right:25px;bottom:90px}
 .hero h1{font-size:59px}
 .hero-copy{font-size:12px}
 .buttons{flex-direction:column;align-items:flex-start}
 .section{padding:100px 25px}
 .grid{grid-template-columns:1fr;gap:50px}
 .story-image{height:450px}
 .cards,.dish-grid{grid-template-columns:1fr}
 .card{height:450px}
 .dish:nth-child(2),.dish:nth-child(3){transform:none}
 .dish img{height:390px}
 .plate{width:330px}
 .ingredient{width:55px;height:55px}
 .chef-image{height:500px}
 .cinema{background-attachment:scroll}
 .form{grid-template-columns:1fr}
 .form .wide,.form button{grid-column:auto}
 .footer-top{flex-direction:column}
 .footer-links{flex-wrap:wrap}
 .footer-bottom{flex-direction:column;gap:12px}
}
</style>
</head>

<body>

<!-- LOADER -->
<div class="loader" id="loader">
 <div class="loader-box">
  <div class="loader-logo">MYK</div>
  <div class="loader-line"></div>
  <div class="loader-text">MEHMET YALÇINKAYA</div>
 </div>
</div>

<!-- NAV -->
<nav id="nav">
 <a class="logo" href="#home">MYK<b>.</b></a>

 <ul class="nav-links">
  <li><a href="#story">HİKÂYE</a></li>
  <li><a href="#experience">DENEYİM</a></li>
  <li><a href="#dishes">LEZZETLER</a></li>
  <li><a href="#chef">ŞEF</a></li>
  <li><a href="#menu">MENÜ</a></li>
  <li><a href="#contact">İLETİŞİM</a></li>
 </ul>

 <a class="reserve-nav" href="#reservation">REZERVASYON</a>
</nav>

<!-- HERO -->
<section class="hero" id="home">

 <div class="hero-bg hero-outside" id="outside"></div>
 <div class="hero-bg hero-inside" id="inside"></div>

 <video autoplay muted loop playsinline poster="https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=2200&q=90">
  <source src="restaurant-entry.mp4" type="video/mp4">
 </video>

 <div class="hero-content">
  <div class="kicker">İSTANBUL · GASTRONOMİ · DENEYİM</div>

  <h1>
   Lezzetin
   <br>
   <em>ötesinde.</em>
  </h1>

  <p class="hero-copy">
   Şef Mehmet Yalçınkaya'nın gastronomi vizyonunu;
   modern mutfak, seçkin servis ve etkileyici atmosferle
   bir araya getiren özel bir deneyim.
  </p>

  <div class="buttons">
   <a class="btn gold" href="#reservation">MASANIZI AYIRTIN</a>
   <a class="btn" href="#dishes">LEZZETLERİ KEŞFET</a>
  </div>
 </div>

 <div class="scroll">
  <span>AŞAĞI KAYDIR</span>
 </div>
</section>

<!-- STORY -->
<section class="section story" id="story">
 <div class="grid">

  <div class="reveal">
   <div class="label">01 / HİKÂYE</div>

   <h2 class="title">
    Bir tabaktan<br>
    <em>daha fazlası.</em>
   </h2>

   <p class="text">
    MYK Restoran; mutfak, tasarım, servis ve atmosferin
    aynı hikâyede buluştuğu bir gastronomi deneyimi.
    Her detay, masaya gelen tabağın hikâyesini
    tamamlamak için tasarlanır.
   </p>
  </div>

  <div class="story-image reveal">
   <div class="story-number">01</div>
  </div>

 </div>
</section>

<!-- EXPERIENCE -->
<section class="section experience" id="experience">

 <div class="reveal">
  <div class="label">02 / DENEYİM</div>

  <h2 class="title">
   Akşamınızın<br>
   <em>her anı.</em>
  </h2>
 </div>

 <div class="cards">

  <article class="card reveal">
   <img src="https://images.unsplash.com/photo-1559339352-11d035aa65de?auto=format&fit=crop&w=1100&q=90">
   <div class="card-content">
    <h3>Atmosfer</h3>
    <p>Işık, müzik ve tasarımın dengelendiği sofistike bir ortam.</p>
   </div>
  </article>

  <article class="card reveal">
   <img src="https://images.unsplash.com/photo-1414235077428-338989a2e8c0?auto=format&fit=crop&w=1100&q=90">
   <div class="card-content">
    <h3>Gastronomi</h3>
    <p>Malzemenin karakterini öne çıkaran modern yorumlar.</p>
   </div>
  </article>

  <article class="card reveal">
   <img src="https://images.unsplash.com/photo-1515003197210-e0cd71810b5f?auto=format&fit=crop&w=1100&q=90">
   <div class="card-content">
    <h3>Masa</h3>
    <p>Paylaşılan anların merkezinde özenli bir servis deneyimi.</p>
   </div>
  </article>

 </div>
</section>

<!-- TRANSFORMATION -->
<section class="transform" id="transformation">

 <div class="sticky">

  <div class="transform-heading">
   <div class="label">03 / MUTFAK</div>

   <h2>
    Malzemeden<br>
    <em>esere.</em>
   </h2>

   <p>AŞAĞI KAYDIR · DÖNÜŞÜMÜ İZLE</p>
  </div>

  <div class="plate" id="plate">

   <div class="ingredient a" id="a"></div>
   <div class="ingredient b" id="b"></div>
   <div class="ingredient c" id="c"></div>
   <div class="ingredient d" id="d"></div>

   <div class="food-final" id="finalFood">
    <img src="https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1000&q=90">
   </div>

  </div>
 </div>
</section>

<!-- DISHES -->
<section class="section dishes" id="dishes">

 <div class="reveal">
  <div class="label">04 / SEÇKİ</div>

  <h2 class="title">
   Şefin<br>
   <em>dokunuşu.</em>
  </h2>
 </div>

 <div class="dish-grid">

  <article class="dish reveal">
   <img src="https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1000&q=90">
   <div class="dish-info">
    <h3>Şefin Seçkisi</h3>
    <p>Mevsimin karakterini taşıyan özel yorum.</p>
   </div>
  </article>

  <article class="dish reveal">
   <img src="https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=1000&q=90">
   <div class="dish-info">
    <h3>Modern Anadolu</h3>
    <p>Geleneksel malzemelere çağdaş yaklaşım.</p>
   </div>
  </article>

  <article class="dish reveal">
   <img src="https://images.unsplash.com/photo-1512621776951-a57141f2eefd?auto=format&fit=crop&w=1000&q=90">
   <div class="dish-info">
    <h3>Final Dokunuş</h3>
    <p>Gecenin sonuna özel hazırlanmış seçki.</p>
   </div>
  </article>

 </div>

 <div style="text-align:center;margin-top:100px">
  <a class="btn gold" href="https://mykcaferestoran.com.tr/" target="_blank">
   TAM MENÜYÜ GÖR
  </a>
 </div>
</section>

<!-- CHEF -->
<section class="section chef" id="chef">

 <div class="grid">

  <div class="reveal">
   <div class="label">05 / ŞEF</div>

   <h2 class="title">
    Mehmet<br>
    <em>Yalçınkaya.</em>
   </h2>

   <p class="text">
    Güçlü malzemeler, modern teknikler ve
    sofrayı bir deneyime dönüştüren bir mutfak yaklaşımı.
    MYK'nın karakteri, bu anlayışın etrafında şekillenir.
   </p>
  </div>

  <div class="chef-image reveal"></div>

 </div>
</section>

<!-- CINEMA -->
<section class="cinema">

 <div class="reveal">
  <div class="label">MYK RESTORAN</div>

  <h2>
   Masada<br>
   <em>başlar.</em>
  </h2>

  <p>LEZZET · ATMOSFER · HİKÂYE</p>
 </div>

</section>

<!-- MENU -->
<section class="section menu" id="menu">

 <div class="reveal">
  <div class="label">06 / MENÜ</div>

  <h2 class="title">
   Seçkin<br>
   <em>lezzetler.</em>
  </h2>
 </div>

 <div class="menu-list">

  <div class="menu-item reveal">
   <div>
    <h3>Şefin Başlangıcı</h3>
    <p>Mevsimsel dokunuşlarla hazırlanan başlangıç.</p>
   </div>
   <span class="menu-tag">SEÇKİ</span>
  </div>

  <div class="menu-item reveal">
   <div>
    <h3>MYK Ana Tabak</h3>
    <p>Şefin modern mutfak yorumu.</p>
   </div>
   <span class="menu-tag">İMZA</span>
  </div>

  <div class="menu-item reveal">
   <div>
    <h3>İmza Lezzet</h3>
    <p>Restoranın karakterini yansıtan özel tabak.</p>
   </div>
   <span class="menu-tag">İMZA</span>
  </div>

  <div class="menu-item reveal">
   <div>
    <h3>Final</h3>
    <p>Gecenin sonuna özel tatlı deneyimi.</p>
   </div>
   <span class="menu-tag">SEÇKİ</span>
  </div>

 </div>
</section>

<!-- RESERVATION -->
<section class="section reservation" id="reservation">

 <div class="reservation-box reveal">

  <div class="label">07 / REZERVASYON</div>

  <h2 class="title">
   Masanız<br>
   <em>hazır.</em>
  </h2>

  <p class="text" style="margin-left:auto;margin-right:auto">
   Rezervasyon talebinizi oluşturun.
   Form gönderildiğinde bilgileriniz WhatsApp üzerinden
   restorana iletilir.
  </p>

  <form class="form" id="reservationForm">

   <input id="name" type="text" placeholder="Ad Soyad" required>

   <input id="phone" type="tel" placeholder="Telefon" required>

   <input id="date" type="date" required>

   <select id="time" required>
    <option value="">Saat seçin</option>
    <option>18:00</option>
    <option>18:30</option>
    <option>19:00</option>
    <option>19:30</option>
    <option>20:00</option>
    <option>20:30</option>
    <option>21:00</option>
    <option>21:30</option>
    <option>22:00</option>
   </select>

   <input
    class="wide"
    id="people"
    type="number"
    min="1"
    max="20"
    placeholder="Kişi sayısı"
    required>

   <button type="submit">
    REZERVASYON TALEBİ GÖNDER
   </button>

  </form>

 </div>
</section>

<!-- CONTACT -->
<section class="section contact" id="contact">

 <div class="grid">

  <div class="reveal">

   <div class="label">08 / İLETİŞİM</div>

   <h2 class="title">
    Bizi<br>
    <em>bulun.</em>
   </h2>

   <div class="contact-info">

    <div class="contact-line">
     <span>ADRES</span>
     Convention Center, Yeşilköy Mah. Atatürk Cad,
     İstanbul WOW Hotel No:23C No:15,
     34149 Bakırköy / İstanbul
    </div>

    <div class="contact-line">
     <span>TELEFON</span>
     <a href="tel:+905301093414">0530 109 34 14</a>
    </div>

    <div class="contact-line">
     <span>ÇALIŞMA SAATLERİ</span>
     Her gün · 01:00'e kadar<br>
     Mutfak · 23:00'e kadar
    </div>

   </div>
  </div>

  <div class="map reveal">
   <a target="_blank"
      href="https://www.google.com/maps/search/?api=1&query=MYK+Restoran+by+Mehmet+Yalçınkaya+İstanbul">
    HARİTADA GÖRÜNTÜLE
   </a>
  </div>

 </div>
</section>

<!-- FOOTER -->
<footer>

 <div class="footer-top">

  <div>
   <div class="footer-logo">MYK<b>.</b></div>
   <p style="color:#666;margin-top:8px">
    by Mehmet Yalçınkaya
   </p>
  </div>

  <div class="footer-links">
   <a href="#story">Hikâye</a>
   <a href="#dishes">Lezzetler</a>
   <a href="#menu">Menü</a>
   <a href="#reservation">Rezervasyon</a>
  </div>

 </div>

 <div class="footer-bottom">
  <span>© 2026 MYK Restoran</span>
  <span>İstanbul · Türkiye</span>
  <span>Premium Dining Experience</span>
 </div>

</footer>

<a href="#reservation" class="float">
 MASA<br>AYIRT
</a>

<script>

/* LOADER */
window.addEventListener("load",()=>{
 setTimeout(()=>{
  document.getElementById("loader").classList.add("hide");
 },1200);
});

/* NAV */
const nav=document.getElementById("nav");

window.addEventListener("scroll",()=>{
 nav.classList.toggle("scrolled",window.scrollY>50);
});

/* REVEAL */
const observer=new IntersectionObserver(entries=>{
 entries.forEach(entry=>{
  if(entry.isIntersecting){
   entry.target.classList.add("active");
  }
 });
},{threshold:.13});

document.querySelectorAll(".reveal")
.forEach(el=>observer.observe(el));

/* HERO CINEMATIC CAMERA */
const hero=document.querySelector(".hero");
const outside=document.getElementById("outside");
const inside=document.getElementById("inside");

function heroCamera(){

 const rect=hero.getBoundingClientRect();
 const max=hero.offsetHeight-innerHeight;

 let p=-rect.top/max;
 p=Math.max(0,Math.min(1,p));

 outside.style.transform=`scale(${1.05+p*.38})`;

 inside.style.opacity=Math.min(1,p*1.8);

 inside.style.transform=`scale(${1.3-p*.4})`;
}

window.addEventListener("scroll",heroCamera);
heroCamera();

/* INGREDIENT -> PLATE */
const section=document.querySelector(".transform");
const plate=document.getElementById("plate");
const finalFood=document.getElementById("finalFood");

const ingredients=[
 document.getElementById("a"),
 document.getElementById("b"),
 document.getElementById("c"),
 document.getElementById("d")
];

function dishTransformation(){

 const rect=section.getBoundingClientRect();
 const max=section.offsetHeight-innerHeight;

 let p=-rect.top/max;
 p=Math.max(0,Math.min(1,p));

 plate.style.transform=`scale(${.65+p*.35})`;
 plate.style.opacity=.25+p*.75;

 const starts=[
  [-210,-150],
  [210,-140],
  [-190,150],
  [190,150]
 ];

 const ends=[
  [-90,-55],
  [90,-45],
  [-80,75],
  [80,70]
 ];

 ingredients.forEach((el,i)=>{

  let q=Math.max(0,Math.min(1,(p-.08)/.58));

  const x=starts[i][0]+
   (ends[i][0]-starts[i][0])*q;

  const y=starts[i][1]+
   (ends[i][1]-starts[i][1])*q;

  const rotation=(1-q)*220;

  el.style.transform=
   `translate(${x}px,${y}px)
    rotate(${rotation}deg)
    scale(${1-q*.25})`;

  el.style.opacity=1-q*.45;
 });

 let finalP=Math.max(0,Math.min(1,(p-.67)/.33));

 finalFood.style.opacity=finalP;
 finalFood.style.transform=
  `scale(${.5+finalP*.5})`;

}

window.addEventListener("scroll",dishTransformation);
dishTransformation();

/* MOUSE CINEMA */
if(innerWidth>900){

 document.addEventListener("mousemove",e=>{

  const x=(e.clientX/innerWidth-.5)*8;
  const y=(e.clientY/innerHeight-.5)*8;

  document.querySelector(".hero-content").style.transform=
   `translate(${x}px,${y}px)`;

 });
}

/* RESERVATION -> WHATSAPP */
document.getElementById("reservationForm")
.addEventListener("submit",e=>{

 e.preventDefault();

 const name=document.getElementById("name").value;
 const phone=document.getElementById("phone").value;
 const date=document.getElementById("date").value;
 const time=document.getElementById("time").value;
 const people=document.getElementById("people").value;

 const message=
`Merhaba MYK Restoran,

Rezervasyon talebi oluşturmak istiyorum.

Ad Soyad: ${name}
Telefon: ${phone}
Tarih: ${date}
Saat: ${time}
Kişi Sayısı: ${people}`;

 const url=
 "https://wa.me/905301093414?text="+
 encodeURIComponent(message);

 window.open(url,"_blank");
});

</script> 

</body>
</html>
