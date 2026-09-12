```html
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Kulamat Kekecewaanmu</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400&family=Space+Mono:wght@400;700&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: #050505;
    color: #e8e8e8;
    font-family: "Cormorant Garamond", serif;
    overflow-x: hidden;
}

/* =========================
   NOISE
========================= */

body::before {
    content: "";
    position: fixed;
    inset: 0;
    pointer-events: none;
    opacity: .08;
    z-index: 9999;

    background-image:
        repeating-radial-gradient(
            circle at 0 0,
            #fff 0,
            #fff 1px,
            transparent 1px,
            transparent 3px
        );

    background-size: 5px 5px;
}

/* =========================
   OPENING
========================= */

.intro {
    min-height: 100vh;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
}

.title {
    position: relative;
    z-index: 5;
    text-align: center;
}

.title small {
    display: block;
    font-family: "Space Mono", monospace;
    font-size: 10px;
    letter-spacing: 7px;
    opacity: .45;
    margin-bottom: 25px;
}

.title h1 {
    font-size: clamp(55px, 11vw, 150px);
    line-height: .75;
    font-weight: 400;
    font-style: italic;
    letter-spacing: -7px;
    animation: breathing 5s infinite ease-in-out;
}

.title p {
    margin-top: 35px;
    font-family: "Space Mono", monospace;
    font-size: 10px;
    letter-spacing: 4px;
    opacity: .5;
}

@keyframes breathing {
    0%,100% {
        transform: scale(1);
    }
    50% {
        transform: scale(.97) skewX(-1deg);
    }
}

/* =========================
   ABSURD OBJECTS
========================= */

.object {
    position: absolute;
    border: 1px solid rgba(255,255,255,.4);
}

.eye {
    width: 180px;
    height: 90px;
    border-radius: 50%;
    left: 7%;
    top: 20%;
    transform: rotate(-17deg);
}

.eye::before {
    content: "";
    position: absolute;
    width: 35px;
    height: 35px;
    background: #eee;
    border-radius: 50%;
    left: 72px;
    top: 25px;
}

.eye::after {
    content: "";
    position: absolute;
    width: 10px;
    height: 10px;
    background: #050505;
    border-radius: 50%;
    left: 84px;
    top: 38px;
}

.circle {
    width: 300px;
    height: 300px;
    border-radius: 50%;
    right: -100px;
    top: 15%;
    border: 1px dashed rgba(255,255,255,.3);
    animation: rotate 30s linear infinite;
}

.circle::after {
    content: "KECEWA";
    position: absolute;
    font-family: "Space Mono";
    font-size: 10px;
    letter-spacing: 5px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.square {
    width: 70px;
    height: 70px;
    left: 18%;
    bottom: 13%;
    transform: rotate(45deg);
    animation: squareMove 8s infinite alternate ease-in-out;
}

@keyframes rotate {
    to {
        transform: rotate(360deg);
    }
}

@keyframes squareMove {
    from {
        transform: rotate(45deg) translate(0,0);
    }

    to {
        transform: rotate(130deg) translate(40px,-20px);
    }
}

/* =========================
   SCROLL MESSAGE
========================= */

.scroll {
    position: absolute;
    bottom: 25px;
    left: 50%;
    transform: translateX(-50%);
    font-family: "Space Mono";
    font-size: 9px;
    letter-spacing: 4px;
    opacity: .35;
    animation: blink 2s infinite;
}

@keyframes blink {
    50% {
        opacity: .05;
    }
}

/* =========================
   STORY
========================= */

.story {
    position: relative;
    max-width: 900px;
    margin: auto;
    padding: 180px 30px;
}

.story::before {
    content: "∴";
    position: absolute;
    font-size: 500px;
    opacity: .025;
    left: 20%;
    top: 100px;
    pointer-events: none;
}

.chapter {
    font-family: "Space Mono";
    font-size: 9px;
    letter-spacing: 5px;
    opacity: .4;
    margin-bottom: 70px;
}

.paragraph {
    font-size: clamp(25px, 4vw, 42px);
    line-height: 1.35;
    margin-bottom: 130px;
    max-width: 800px;
}

.paragraph:nth-child(even) {
    margin-left: auto;
    text-align: right;
}

.fade {
    opacity: .45;
    font-style: italic;
}

/* =========================
   GLITCH TEXT
========================= */

.glitch {
    position: relative;
    display: inline-block;
    font-style: italic;
}

.glitch::before,
.glitch::after {
    content: attr(data-text);
    position: absolute;
    left: 0;
    top: 0;
    opacity: .7;
}

.glitch::before {
    transform: translate(2px, -1px);
    clip-path: inset(0 0 55% 0);
}

.glitch::after {
    transform: translate(-2px, 1px);
    clip-path: inset(55% 0 0 0);
}

/* =========================
   REVERSE CLOCK
========================= */

.clock-section {
    min-height: 70vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    position: relative;
    overflow: hidden;
    border-top: 1px solid #222;
    border-bottom: 1px solid #222;
}

.clock-section::before {
    content: "WAKTU TIDAK PERNAH PULANG";
    position: absolute;
    font-family: "Space Mono";
    font-size: clamp(40px, 9vw, 130px);
    white-space: nowrap;
    opacity: .025;
    animation: moveText 20s linear infinite;
}

@keyframes moveText {
    from {
        transform: translateX(100%);
    }

    to {
        transform: translateX(-100%);
    }
}

.clock {
    position: relative;
    z-index: 2;
}

.clock-label {
    font-family: "Space Mono";
    font-size: 9px;
    letter-spacing: 5px;
    opacity: .4;
    margin-bottom: 25px;
}

.time {
    font-family: "Space Mono";
    font-size: clamp(30px, 7vw, 80px);
    letter-spacing: 5px;
}

/* =========================
   FINAL
========================= */

.final {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 40px;
    position: relative;
}

.final-text {
    max-width: 800px;
}

.final-text h2 {
    font-size: clamp(50px, 10vw, 130px);
    font-weight: 400;
    font-style: italic;
    line-height: .8;
    margin-bottom: 60px;
}

.final-text p {
    font-size: 25px;
    line-height: 1.5;
    opacity: .65;
}

.final-text small {
    display: block;
    margin-top: 80px;
    font-family: "Space Mono";
    font-size: 8px;
    letter-spacing: 4px;
    opacity: .25;
}

/* =========================
   FLOATING WORDS
========================= */

.word {
    position: fixed;
    font-family: "Space Mono";
    font-size: 8px;
    letter-spacing: 3px;
    opacity: .15;
    pointer-events: none;
    z-index: 1;
}

.w1 {
    top: 30%;
    left: 2%;
    transform: rotate(-90deg);
}

.w2 {
    right: 3%;
    bottom: 30%;
    transform: rotate(90deg);
}

.w3 {
    left: 45%;
    top: 10%;
}

/* =========================
   MOBILE
========================= */

@media(max-width:600px) {

    .eye {
        width: 100px;
        height: 50px;
    }

    .eye::before {
        width: 20px;
        height: 20px;
        left: 40px;
        top: 14px;
    }

    .eye::after {
        width: 6px;
        height: 6px;
        left: 47px;
        top: 21px;
    }

    .circle {
        width: 180px;
        height: 180px;
    }

    .story {
        padding: 120px 25px;
    }

    .paragraph {
        margin-bottom: 100px;
    }
}

</style>
</head>

<body>

<!-- =========================
     FLOATING WORDS
========================= -->

<div class="word w1">SEBUAH KOTA YANG TERLUPA</div>
<div class="word w2">JANGAN PULANG</div>
<div class="word w3">ERROR : PERASAAN TIDAK DITEMUKAN</div>


<!-- =========================
     OPENING
========================= -->

<section class="intro">

    <div class="object eye"></div>
    <div class="object circle"></div>
    <div class="object square"></div>

    <div class="title">

        <small>ARSIP KEGAGALAN SEBUAH PERASAAN</small>

        <h1>
            Kulamat<br>
            Kekecewaanmu
        </h1>

        <p>
            sebuah cerita yang lupa bagaimana caranya selesai
        </p>

    </div>

    <div class="scroll">
        ↓ GULIR UNTUK TERSESAT ↓
    </div>

</section>


<!-- =========================
     STORY
========================= -->

<section class="story">

    <div class="chapter">
        BAB I — TENTANG SESUATU YANG TIDAK SELESAI
    </div>

    <p class="paragraph">

        Bukan seperti orang membaca surat kabar
        atau ramalan cuaca,
        melainkan seperti seseorang yang berdiri
        di tepi laut dan mendengar batu-batu kecil
        berbisik tentang hal-hal
        yang tak pernah sempat diucapkan.

    </p>


    <p class="paragraph fade">

        Kekecewaanmu ternyata tidak berwarna hitam.

        Ia menyerupai taman yang lupa musim,
        tempat bunga-bunga mekar tanpa nama
        lalu gugur sebelum sempat dikenang.

    </p>


    <p class="paragraph">

        Di sana,
        jam-jam berjalan mundur
        sambil memanggul sisa percakapan
        yang telah menjadi debu.

    </p>


    <p class="paragraph">

        Burung-burung membawa
        serpihan harapan ke langit yang retak.

        Mereka terbang rendah,
        seolah takut bahwa cita-cita
        yang terlalu tinggi
        akan berubah menjadi hujan
        yang tak kembali ke bumi.

    </p>


    <p class="paragraph fade">

        Dan di sudut paling sunyi
        dari matamu,

        ada sebuah kota kecil
        yang telah lama ditinggalkan penghuninya.

    </p>


    <p class="paragraph">

        Pintu-pintu masih terbuka.

        Lampu-lampu masih menyala.

        Tetapi tak ada seorang pun pulang.

    </p>


    <p class="paragraph">

        Hanya angin yang mondar-mandir,

        menghafal nama-nama
        yang perlahan dilupakan.

    </p>

</section>


<!-- =========================
     REVERSE CLOCK
========================= -->

<section class="clock-section">

    <div class="clock">

        <div class="clock-label">
            WAKTU YANG MEMILIH UNTUK MUNDUR
        </div>

        <div class="time" id="clock">
            00:00:00
        </div>

    </div>

</section>


<!-- =========================
     FINAL
========================= -->

<section class="final">

    <div class="final-text">

        <h2 class="glitch"
            data-text="Barangkali, kekecewaan memang bukan luka.">
            Barangkali, kekecewaan memang bukan luka.
        </h2>

        <p>
            Ia adalah rumah tua yang terus berdiri,
            meski penghuninya telah belajar hidup
            di tempat lain.
        </p>

        <small>
            END OF TRANSMISSION — 404: PERASAAN TIDAK DITEMUKAN
        </small>

    </div>

</section>


<script>

/* =========================
   REVERSE CLOCK
========================= */

let seconds = 0;

function reverseClock() {

    seconds--;

    if (seconds < -86400) {
        seconds = 0;
    }

    let abs = Math.abs(seconds);

    let h = Math.floor(abs / 3600);
    let m = Math.floor((abs % 3600) / 60);
    let s = abs % 60;

    const formatted =
        String(h).padStart(2, "0") + ":" +
        String(m).padStart(2, "0") + ":" +
        String(s).padStart(2, "0");

    document.getElementById("clock").innerText =
        seconds < 0 ? "-" + formatted : formatted;
}

setInterval(reverseClock, 1000);


/* =========================
   RANDOM GLITCH
========================= */

const glitchTexts = [
    "Kekecewaan sedang tumbuh...",
    "Pintu masih terbuka.",
    "Tidak ada yang pulang.",
    "Angin sedang mengingat nama.",
    "Harapan mengalami kerusakan.",
    "Waktu salah arah.",
    "Sebuah kota sedang lupa.",
    "Perasaan tidak ditemukan."
];

setInterval(() => {

    const title = document.querySelector(".title p");

    const random =
        glitchTexts[Math.floor(Math.random() * glitchTexts.length)];

    title.innerText = random;

}, 3500);


/* =========================
   MOUSE DISTORTION
========================= */

document.addEventListener("mousemove", (e) => {

    const x = (e.clientX / window.innerWidth - .5) * 20;
    const y = (e.clientY / window.innerHeight - .5) * 20;

    document.querySelector(".eye").style.transform =
        `translate(${x}px, ${y}px) rotate(-17deg)`;

    document.querySelector(".square").style.transform =
        `translate(${-x}px, ${-y}px) rotate(45deg)`;

});


/* =========================
   RANDOM PAGE TITLE
========================= */

const titles = [
    "Kulamat Kekecewaanmu",
    "404 — Perasaan Hilang",
    "Sebuah Kota yang Lupa",
    "Jangan Pulang",
    "Arsip Kekecewaan",
    "Waktu Berjalan Mundur"
];

let titleIndex = 0;

setInterval(() => {

    titleIndex++;

    if (titleIndex >= titles.length) {
        titleIndex = 0;
    }

    document.title = titles[titleIndex];

}, 4000);

</script>

</body>
</html>
```