<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no">
<title>TTS Jagoan Pancasila</title>
<link href="https://fonts.googleapis.com/css2?family=Fredoka+One&family=Nunito:wght@400;700;800;900&display=swap" rel="stylesheet">
<style>
:root{
  --red:#ff4757;--orange:#ff6348;--yellow:#ffa502;
  --green:#2ed573;--blue:#1e90ff;--purple:#a29bfe;
  --pink:#fd79a8;--teal:#00cec9;--bg:#fff8ee;
}
*{box-sizing:border-box;margin:0;padding:0}
html,body{width:100%;min-height:100vh}
body{
  font-family:'Nunito',sans-serif;
  background:var(--bg);
  padding:12px;
  background-image:
    radial-gradient(ellipse at 12% 8%,rgba(255,71,87,.10) 0%,transparent 50%),
    radial-gradient(ellipse at 88% 92%,rgba(30,144,255,.10) 0%,transparent 50%),
    radial-gradient(ellipse at 50% 50%,rgba(46,213,115,.06) 0%,transparent 60%);
}
 
/* ─── HEADER ─── */
.hdr{text-align:center;margin-bottom:14px;animation:popIn .7s cubic-bezier(.34,1.56,.64,1)}
.badge{
  display:inline-flex;align-items:center;gap:6px;
  background:linear-gradient(135deg,var(--red),var(--orange));
  color:#fff;font-size:10px;font-weight:900;letter-spacing:2px;text-transform:uppercase;
  padding:4px 16px;border-radius:20px;margin-bottom:8px;
  box-shadow:0 3px 12px rgba(255,71,87,.4);
}
h1{
  font-family:'Fredoka One',cursive;
  font-size:clamp(22px,6.5vw,40px);line-height:1.1;
  background:linear-gradient(135deg,#ff4757 0%,#ff6348 20%,#ffa502 45%,#2ed573 70%,#1e90ff 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  animation:hue 6s linear infinite;
  filter:drop-shadow(0 2px 0 rgba(0,0,0,.08));
}
@keyframes hue{0%,100%{filter:hue-rotate(0deg) drop-shadow(0 2px 0 rgba(255,71,87,.2))}
  50%{filter:hue-rotate(20deg) drop-shadow(0 2px 0 rgba(30,144,255,.2))}}
.stars{font-size:20px;margin-top:5px;animation:spread 2.5s ease-in-out infinite}
@keyframes spread{0%,100%{letter-spacing:4px}50%{letter-spacing:12px}}
 
/* ─── TOP BAR ─── */
.topbar{display:flex;gap:10px;margin-bottom:12px;align-items:stretch;flex-wrap:wrap}
.nama-card{
  flex:1;min-width:180px;
  background:linear-gradient(135deg,#e8f4fd,#e6fff4);
  border:2px solid #90caf9;border-radius:14px;
  padding:10px 14px;display:flex;align-items:center;gap:8px;
}
.nama-card label{font-size:12px;font-weight:900;color:#1565c0;white-space:nowrap}
.nama-card input{
  flex:1;min-width:0;border:none;background:transparent;
  font-family:'Nunito',sans-serif;font-size:14px;font-weight:800;
  color:#0d47a1;outline:none;border-bottom:2px dashed #90caf9;
}
.nama-card input::placeholder{color:#bbdefb;font-weight:600}
.skor-card{
  background:linear-gradient(135deg,#ffeaa7,#fdcb6e);
  border:2px solid #f9ca24;border-radius:14px;
  padding:10px 18px;display:flex;flex-direction:column;
  align-items:center;justify-content:center;min-width:88px;
  box-shadow:0 3px 14px rgba(253,203,110,.45);
}
.skor-lbl{font-size:9px;font-weight:900;color:#6d4c41;letter-spacing:1.5px;text-transform:uppercase}
.skor-num{font-family:'Fredoka One',cursive;font-size:30px;color:#4e342e;line-height:1;transition:all .3s}
.skor-num.bump{animation:bump .4s ease}
@keyframes bump{0%{transform:scale(1)}50%{transform:scale(1.4)}100%{transform:scale(1)}}
 
/* ─── PETUNJUK ─── */
.petunjuk{
  background:linear-gradient(135deg,#f3e5f5,#e8eaf6);
  border:2px dashed #ce93d8;border-radius:12px;
  padding:8px 12px;text-align:center;
  font-size:11px;font-weight:800;color:#6a1b9a;
  margin-bottom:10px;line-height:1.7;
}
.petunjuk b{background:#fff;border-radius:5px;padding:1px 6px;margin:0 2px}
 
/* ─── GRID ─── */
.grid-card{
  background:#fff;border-radius:18px;padding:14px;
  box-shadow:0 4px 24px rgba(0,0,0,.09);
  border:3px solid #f0f0f0;overflow-x:auto;
  margin-bottom:14px;display:flex;justify-content:center;
}
.tts-grid{display:inline-grid;gap:3px;user-select:none}
 
.cell{width:34px;height:34px;border-radius:6px;position:relative;display:flex;align-items:center;justify-content:center}
@media(max-width:380px){.cell{width:27px;height:27px;border-radius:4px}}
.cell.empty{background:transparent}
.cell.box{
  background:#fafafa;border:2px solid #dde3ee;
  cursor:pointer;transition:transform .12s,border-color .12s,background .15s;
}
.cell.box:hover{transform:scale(1.09);border-color:#90caf9}
 
/* highlight warna beda untuk mendatar vs menurun */
.cell.hl-a{background:#fffde7;border-color:#f9a825;box-shadow:0 0 0 2px rgba(249,168,37,.25)}
.cell.hl-d{background:#e3f2fd;border-color:#1565c0;box-shadow:0 0 0 2px rgba(21,101,192,.2)}
 
.cell.ok{background:linear-gradient(135deg,#b9f6ca,#69f0ae)!important;border-color:#00c853!important;animation:okPop .4s cubic-bezier(.34,1.56,.64,1)}
.cell.err{background:linear-gradient(135deg,#ffcdd2,#ef9a9a)!important;border-color:#e53935!important;animation:errShake .35s ease}
@keyframes okPop{0%{transform:scale(1)}50%{transform:scale(1.2)}100%{transform:scale(1)}}
@keyframes errShake{0%,100%{transform:translateX(0)}25%{transform:translateX(-4px)}75%{transform:translateX(4px)}}
 
.nbadge{
  position:absolute;top:1px;left:2px;
  font-size:10px;font-weight:900;
  color:#1a237e;
  pointer-events:none;
  font-family:'Fredoka One',cursive;
  line-height:1;
  text-shadow:0 0 3px rgba(255,255,255,1), 0 0 6px rgba(255,255,255,.9);
  letter-spacing:0;
  z-index:2;
}
.cell input{
  width:100%;height:100%;border:none;background:transparent;
  text-align:center;font-size:14px;font-weight:900;
  text-transform:uppercase;color:#1a237e;
  font-family:'Fredoka One',cursive;
  outline:none;caret-color:transparent;cursor:pointer;
}
 
/* ─── TOMBOL ─── */
.btns{display:flex;gap:10px;justify-content:center;margin-bottom:14px;flex-wrap:wrap}
.btn{
  padding:11px 26px;border-radius:12px;border:none;
  font-size:14px;font-weight:900;cursor:pointer;
  font-family:'Nunito',sans-serif;letter-spacing:.3px;
  transition:transform .15s,box-shadow .15s;
}
.btn:active{transform:scale(.95)!important}
.btn-cek{background:linear-gradient(135deg,#00b894,#00cec9);color:#fff;box-shadow:0 4px 16px rgba(0,184,148,.4)}
.btn-cek:hover{transform:translateY(-2px);box-shadow:0 6px 22px rgba(0,184,148,.5)}
.btn-ulang{background:linear-gradient(135deg,#636e72,#2d3436);color:#fff;box-shadow:0 4px 14px rgba(0,0,0,.2)}
.btn-ulang:hover{transform:translateY(-2px)}
 
/* ─── HASIL ─── */
.hasil{border-radius:16px;margin-bottom:14px;display:none;overflow:hidden}
.hasil.show{display:block;animation:popIn .5s cubic-bezier(.34,1.56,.64,1)}
.hasil-body{padding:16px 20px;text-align:center}
.hasil.sempurna .hasil-body{background:linear-gradient(135deg,#c8f7c5,#a8edc0);border:3px solid #27ae60}
.hasil.bagus    .hasil-body{background:linear-gradient(135deg,#ffeaa7,#fdcb6e);border:3px solid #f39c12}
.hasil.coba     .hasil-body{background:linear-gradient(135deg,#ffd6e0,#ffacc7);border:3px solid #e84393}
.emo{font-size:44px;animation:boing 1.2s ease-in-out infinite}
@keyframes boing{0%,100%{transform:translateY(0) rotate(-4deg)}50%{transform:translateY(-10px) rotate(4deg)}}
.hasil-judul{font-family:'Fredoka One',cursive;font-size:20px;color:#2d3436;margin:5px 0 3px}
.hasil-sub{font-size:12px;font-weight:800;color:#636e72;margin-bottom:10px}
.bar-bg{height:12px;border-radius:20px;background:rgba(0,0,0,.12);overflow:hidden}
.bar-fill{height:100%;border-radius:20px;background:linear-gradient(90deg,#2ed573,#1e90ff);transition:width 1s cubic-bezier(.25,1,.5,1)}
 
/* ─── SOAL ─── */
.soal-card{
  background:#fff;border-radius:18px;padding:16px;
  box-shadow:0 4px 24px rgba(0,0,0,.09);border:3px solid #f0f0f0;
  margin-bottom:14px;
}
.soal-cols{display:grid;grid-template-columns:1fr 1fr;gap:16px}
@media(max-width:480px){.soal-cols{grid-template-columns:1fr}}
.soal-grp h3{
  font-family:'Fredoka One',cursive;font-size:13px;
  padding:5px 12px;border-radius:10px;margin-bottom:8px;
  display:inline-flex;align-items:center;gap:5px;
}
.grp-a h3{background:linear-gradient(135deg,#fffde7,#fff9c4);color:#f57f17;border:1.5px solid #f9a825}
.grp-d h3{background:linear-gradient(135deg,#e3f2fd,#bbdefb);color:#0d47a1;border:1.5px solid #42a5f5}
.qi{
  display:flex;gap:6px;align-items:flex-start;
  padding:5px 8px;border-radius:8px;
  font-size:11.5px;font-weight:700;color:#37474f;
  cursor:pointer;transition:all .15s;border:1.5px solid transparent;margin-bottom:3px;
}
.grp-a .qi:hover{background:#fffde7;border-color:#f9a825;transform:translateX(3px)}
.grp-d .qi:hover{background:#e3f2fd;border-color:#42a5f5;transform:translateX(3px)}
.qi.aq-a{background:#fff9c4;border-color:#f9a825;color:#e65100}
.qi.aq-d{background:#e3f2fd;border-color:#1565c0;color:#0d47a1}
.qn{font-family:'Fredoka One',cursive;font-size:13px;min-width:24px}
.grp-a .qn{color:#f9a825}.grp-d .qn{color:#1e90ff}
.qi.aq-a .qn{color:#e65100}.qi.aq-d .qn{color:#0d47a1}
 
footer{text-align:center;font-size:11px;color:#b0bec5;font-weight:800;padding-bottom:8px}
 
/* ─── MUSIC BAR ─── */
.music-bar{
  display:flex;align-items:center;gap:10px;flex-wrap:wrap;
  background:linear-gradient(135deg,#e8eaf6,#f3e5f5);
  border:2px solid #b39ddb;border-radius:14px;
  padding:8px 14px;margin-bottom:12px;
}
.btn-music{
  background:linear-gradient(135deg,#7c4dff,#e040fb);
  color:#fff;border:none;border-radius:10px;
  padding:7px 14px;font-size:12px;font-weight:900;
  cursor:pointer;font-family:'Nunito',sans-serif;
  transition:transform .15s,box-shadow .15s;
  box-shadow:0 3px 10px rgba(124,77,255,.4);
  white-space:nowrap;
}
.btn-music:hover{transform:translateY(-2px);box-shadow:0 5px 14px rgba(124,77,255,.5)}
.btn-music:active{transform:scale(.95)}
.music-info{display:flex;align-items:center;gap:5px;flex:1;flex-wrap:wrap;justify-content:center}
.music-note{
  font-size:16px;color:#7c4dff;
  animation:noteFloat 1.5s ease-in-out infinite;
  display:inline-block;
}
.music-note:nth-child(2){animation-delay:.2s}
.music-note:nth-child(3){animation-delay:.4s}
.music-note:nth-child(4){animation-delay:.6s}
.music-note:nth-child(6){animation-delay:.8s}
.music-note:nth-child(7){animation-delay:1s}
.music-note:nth-child(8){animation-delay:1.2s}
.music-note.paused{animation-play-state:paused;opacity:.3}
@keyframes noteFloat{0%,100%{transform:translateY(0) scale(1)}50%{transform:translateY(-5px) scale(1.2)}}
 
/* ─── ANIM UTILS ─── */
@keyframes popIn{0%{transform:scale(.75);opacity:0}60%{transform:scale(1.07)}100%{transform:scale(1);opacity:1}}
.cf{position:fixed;top:-12px;pointer-events:none;z-index:9999;border-radius:3px;animation:cffall linear forwards}
@keyframes cffall{0%{transform:translateY(0) rotate(0);opacity:1}100%{transform:translateY(108vh) rotate(800deg);opacity:0}}
.fdeco{position:fixed;pointer-events:none;z-index:0;opacity:.12;font-size:22px;animation:frise linear infinite}
@keyframes frise{0%{transform:translateY(100vh) rotate(0);opacity:.15}100%{transform:translateY(-10vh) rotate(360deg);opacity:0}}
</style>
</head>
<body>
 
<div id="decos" style="position:fixed;inset:0;pointer-events:none;z-index:0;overflow:hidden"></div>
 
<div style="position:relative;z-index:1;max-width:720px;margin:0 auto">
 
<!-- HEADER -->
<div class="hdr">
  <div class="badge">🏆 Seru · Edukatif · Pancasila 🏆</div>
  <h1>TTS JAGOAN<br>PANCASILA</h1>
  <div class="stars">🌟 ⭐ 🌟</div>
</div>
 
<!-- TOP BAR -->
<div class="topbar">
  <div class="nama-card">
    <label>🧒 Nama:</label>
    <input type="text" id="nama" placeholder="Tulis namamu!" autocomplete="off" maxlength="30">
  </div>
  <div class="skor-card">
    <div class="skor-lbl">⚡ Skor</div>
    <div class="skor-num" id="skorNum">0</div>
  </div>
</div>
 
<!-- PETUNJUK -->
<div class="petunjuk">
  👆 Ketuk kotak untuk mengisi &nbsp;·&nbsp;
  <b style="background:#fffde7;color:#f57f17">Kuning = Mendatar →</b>
  <b style="background:#e3f2fd;color:#1565c0">Biru = Menurun ↓</b>
  &nbsp;·&nbsp; 🏆 Raih skor 100!
</div>
 
<!-- BACKSOUND -->
<div class="music-bar">
  <button class="btn-music" id="btnMusic" onclick="toggleMusic()">🎵 <span id="musicLabel">Nyalakan Musik</span></button>
  <div class="music-info">
    <span class="music-note paused" id="mn0">♩</span>
    <span class="music-note paused" id="mn1">♪</span>
    <span class="music-note paused" id="mn2">♫</span>
    <span class="music-note paused" id="mn3">♬</span>
    <span style="font-size:11px;font-weight:800;color:#6a1b9a">🎶 Musik Belajar Pancasila 🎶</span>
    <span class="music-note paused" id="mn4">♩</span>
    <span class="music-note paused" id="mn5">♪</span>
    <span class="music-note paused" id="mn6">♫</span>
    <span class="music-note paused" id="mn7">♬</span>
  </div>
</div>
 
<!-- GRID -->
<div class="grid-card">
  <div class="tts-grid" id="grid"></div>
</div>
 
<!-- HASIL -->
<div class="hasil" id="hasil">
  <div class="hasil-body">
    <div class="emo" id="hEmo">🎉</div>
    <div class="hasil-judul" id="hJudul"></div>
    <div class="hasil-sub" id="hSub"></div>
    <div class="bar-bg"><div class="bar-fill" id="barFill" style="width:0%"></div></div>
  </div>
</div>
 
<!-- TOMBOL -->
<div class="btns">
  <button class="btn btn-cek" onclick="periksa()">✔ Periksa Jawaban</button>
  <button class="btn btn-ulang" onclick="resetAll()">↺ Mulai Lagi</button>
</div>
 
<!-- SOAL -->
<div class="soal-card">
  <div class="soal-cols">
    <div class="soal-grp grp-a">
      <h3>→ Mendatar</h3>
      <div id="soalA"></div>
    </div>
    <div class="soal-grp grp-d">
      <h3>↓ Menurun</h3>
      <div id="soalD"></div>
    </div>
  </div>
</div>
 
<footer>🌈 Ayo jadi Jagoan Pancasila! Semangat belajar! 🌈</footer>
</div>
 
<script>
/*
╔══════════════════════════════════════════════════════════════╗
║  LAYOUT TERVERIFIKASI — sesuai gambar rancangan              ║
║  Grid: 10 baris (r0-r9) × 12 kolom (c0-c11)                 ║
║                                                              ║
║  MENDATAR (6):                                               ║
║   1. EMPAT      r0, c5-c9                                    ║
║   3. MUSYAWARAH r2, c0-c9                                    ║
║   5. ADIL       r4, c7-c10                                   ║
║   7. RUKUN      r6, c6-c10                                   ║
║   9. BINTANG    r8, c5-c11                                   ║
║  10. TIGA       r8, c0-c3                                    ║
║                                                              ║
║  MENURUN (4):                                                ║
║   2. MEMBANTU   c0, r2-r9                                    ║
║   4. RANTAI     c4, r1-r6                                    ║
║   6. SATU       c2, r2-r5                                    ║
║   8. PERSATUAN  c7, r0-r8                                    ║
║                                                              ║
║  PERPOTONGAN (10 titik):                                     ║
║   EMPAT[2]=P    ↔ PERSATUAN[0]=P  (r0,c7) ✓                ║
║   MUSYAWARAH[0]=M ↔ MEMBANTU[0]=M (r2,c0) ✓                ║
║   MUSYAWARAH[2]=S ↔ SATU[0]=S    (r2,c2) ✓                 ║
║   MUSYAWARAH[4]=A ↔ RANTAI[1]=A  (r2,c4) ✓                 ║
║   MUSYAWARAH[7]=R ↔ PERSATUAN[2]=R (r2,c7) ✓               ║
║   SATU[2]=T     ↔ (RANTAI c4≠c2) — no conflict ✓           ║
║   RANTAI[3]=T   ↔ (free r4,c4) ✓                           ║
║   ADIL[0]=A     ↔ PERSATUAN[4]=A (r4,c7) ✓                 ║
║   MEMBANTU[6]=T ↔ TIGA[0]=T      (r8,c0) ✓                 ║
║   PERSATUAN[6]=U ↔ RUKUN[1]=U   (r6,c7) ✓                  ║
║   PERSATUAN[8]=N ↔ BINTANG[2]=N (r8,c7) ✓                  ║
╚══════════════════════════════════════════════════════════════╝
*/
 
const ROWS=10, COLS=12;
 
const KATA={
  // ── MENDATAR ──
  1: {word:"EMPAT",     dir:"across", row:0, col:5,
      soal:"Pemilihan ketua kelas adalah penerapan sila ke ..."},
  3: {word:"MUSYAWARAH",dir:"across", row:2, col:0,
      soal:"Keputusan bersama sebaiknya diambil dengan cara …"},
  5: {word:"ADIL",      dir:"across", row:4, col:7,
      soal:"Sila ke-5 bermakna setiap warga negara berhak mendapat perlakuan yang ..."},
  7: {word:"RUKUN",     dir:"across", row:6, col:6,
      soal:"Kita harus hidup … agar tidak terjadi perpecahan"},
  9: {word:"BINTANG",   dir:"across", row:8, col:5,
      soal:"Lambang sila pertama adalah …"},
  10:{word:"TIGA",      dir:"across", row:8, col:0,
      soal:"Membantu ibu membersihkan rumah adalah contoh penerapan sila ke ..."},
  // ── MENURUN ──
  2: {word:"MEMBANTU",  dir:"down",   row:2, col:0,
      soal:"Jika ada teman kesulitan kita harus saling ..."},
  4: {word:"RANTAI",    dir:"down",   row:1, col:4,
      soal:"Sila ke-2 Pancasila dilambangkan dengan"},
  6: {word:"SATU",      dir:"down",   row:2, col:2,
      soal:"Kegiatan berdoa sebelum belajar mencerminkan pengamalan sila ke..."},
  8: {word:"PERSATUAN", dir:"down",   row:0, col:7,
      soal:"Sila ketiga mengajarkan kita menjaga … bangsa"},
};
 
// ── build cell map ──
let cMap={}, wCells={}, curNum=null, curDir=null;
 
function build(){
  Object.entries(KATA).forEach(([n,{word,dir,row,col}])=>{
    wCells[n]=[];
    for(let i=0;i<word.length;i++){
      const r=dir==="across"?row:row+i;
      const c=dir==="across"?col+i:col;
      const k=r+","+c;
      if(!cMap[k])cMap[k]={list:[],ans:{}};
      cMap[k].list.push({n:+n,dir,pos:i});
      cMap[k].ans[dir]=word[i];
      wCells[n].push(k);
    }
  });
}
 
// ── render grid ──
function renderGrid(){
  const g=document.getElementById("grid");
  g.style.gridTemplateColumns=`repeat(${COLS},34px)`;
  g.style.gridTemplateRows=`repeat(${ROWS},34px)`;
  g.innerHTML="";
  for(let r=0;r<ROWS;r++){
    for(let c=0;c<COLS;c++){
      const k=r+","+c, div=document.createElement("div");
      if(!cMap[k]){div.className="cell empty";g.appendChild(div);continue;}
      div.className="cell box"; div.id="C"+r+"_"+c;
      // number badge
      const starts=cMap[k].list.filter(x=>x.pos===0).sort((a,b)=>a.n-b.n);
      if(starts.length){
        const b=document.createElement("span");
        b.className="nbadge";b.textContent=starts[0].n;div.appendChild(b);
      }
      const inp=document.createElement("input");
      inp.type="text";inp.maxLength=1;inp.inputMode="text";
      inp.dataset.k=k;inp.dataset.r=r;inp.dataset.c=c;
      inp.addEventListener("focus",()=>onFocus(k));
      inp.addEventListener("input",e=>onInput(e,r,c));
      inp.addEventListener("keydown",e=>onKey(e,r,c));
      div.appendChild(inp);
      g.appendChild(div);
    }
  }
}
 
// ── highlight ──
function clearHL(){
  document.querySelectorAll(".cell.hl-a,.cell.hl-d")
    .forEach(el=>el.classList.remove("hl-a","hl-d"));
}
function onFocus(k){
  clearHL();
  const info=cMap[k]; if(!info) return;
  // toggle direction if cell shared by two words
  const dirs=[...new Set(info.list.map(x=>x.dir))];
  let dir;
  if(dirs.length===1) dir=dirs[0];
  else dir=(curDir&&dirs.includes(curDir))?curDir:dirs[0];
  const entry=info.list.find(x=>x.dir===dir)||info.list[0];
  curNum=entry.n; curDir=entry.dir;
  const hlC=curDir==="across"?"hl-a":"hl-d";
  wCells[curNum].forEach(ck=>{
    const[rr,cc]=ck.split(",").map(Number);
    document.getElementById("C"+rr+"_"+cc)?.classList.add(hlC);
  });
  // soal highlight
  document.querySelectorAll(".qi").forEach(el=>el.classList.remove("aq-a","aq-d"));
  const qa=document.querySelector(`.qi[data-n="${curNum}"][data-d="${curDir}"]`);
  if(qa){qa.classList.add(curDir==="across"?"aq-a":"aq-d");qa.scrollIntoView({block:"nearest"});}
}
 
// ── input ──
function onInput(e,r,c){
  const v=e.target.value.toUpperCase().replace(/[^A-Z]/g,"");
  e.target.value=v;
  if(v){sfxTik();move(r,c,1);}
}
function onKey(e,r,c){
  if(e.key==="Backspace"){const i=inp(r,c);if(i&&!i.value)move(r,c,-1);}
  const m={ArrowRight:[0,1],ArrowLeft:[0,-1],ArrowDown:[1,0],ArrowUp:[-1,0]};
  if(m[e.key]){const[dr,dc]=m[e.key];go(r+dr,c+dc);e.preventDefault();}
}
function move(r,c,d){curDir==="across"?go(r,c+d):go(r+d,c);}
function go(r,c){inp(r,c)?.focus();}
function inp(r,c){return document.querySelector(`input[data-k="${r},${c}"]`);}
 
// ── render soal ──
function renderSoal(){
  const sa=document.getElementById("soalA"), sd=document.getElementById("soalD");
  sa.innerHTML="";sd.innerHTML="";
  Object.entries(KATA).sort((a,b)=>+a[0]-+b[0]).forEach(([n,{dir,soal}])=>{
    const list=dir==="across"?sa:sd;
    const d=document.createElement("div");
    d.className="qi";d.dataset.n=n;d.dataset.d=dir;
    d.innerHTML=`<span class="qn">${n}.</span><span>${soal}</span>`;
    d.onclick=()=>{
      curNum=+n;curDir=dir;
      inp(...wCells[n][0].split(",").map(Number))?.focus();
    };
    list.appendChild(d);
  });
}
 
// ── periksa ──
function periksa(){
  const nama=document.getElementById("nama").value.trim();
  if(!nama){document.getElementById("nama").focus();return;}
  let ok=0,tot=0;
  Object.entries(KATA).forEach(([n,{word}])=>{
    wCells[n].forEach((k,i)=>{
      const ip=document.querySelector(`input[data-k="${k}"]`);
      const cell=document.getElementById("C"+k.replace(",","_"));
      if(!ip||!cell)return;
      tot++;
      cell.classList.remove("hl-a","hl-d");
      if(ip.value.toUpperCase()===word[i]){
        ok++;cell.classList.remove("err");cell.classList.add("ok");
      }else{
        cell.classList.remove("ok");cell.classList.add("err");
      }
    });
  });
  const pct=Math.round(ok/tot*100);
  const sn=document.getElementById("skorNum");
  sn.textContent=pct;sn.classList.remove("bump");void sn.offsetWidth;sn.classList.add("bump");
  let cls,emo,judul,sub;
  if(pct===100){
    cls="sempurna";emo="🏆";judul=`Luar Biasa, ${nama}! SEMPURNA!`;
    sub="Semua jawaban benar! Kamu adalah Jagoan Pancasila sejati! 🌟";
    launchConfetti(); sfxMenang();
  }else if(pct>=60){
    cls="bagus";emo="😊";judul=`Bagus, ${nama}! Skor ${ok}/${tot} (${pct}%)`;
    sub="Hampir sempurna! Perbaiki yang merah dan coba lagi! 💪";
    sfxBenar();
  }else{
    cls="coba";emo="💡";judul=`${nama}, Skor: ${ok}/${tot} (${pct}%)`;
    sub="Jangan menyerah! Baca soalnya pelan-pelan dan coba lagi! 🌈";
    sfxSalah();
  }
  const h=document.getElementById("hasil");
  h.className=`hasil show ${cls}`;
  document.getElementById("hEmo").textContent=emo;
  document.getElementById("hJudul").textContent=judul;
  document.getElementById("hSub").textContent=sub;
  document.getElementById("barFill").style.width=pct+"%";
  h.scrollIntoView({behavior:"smooth",block:"center"});
}
 
// ── reset ──
function resetAll(){
  document.querySelectorAll(".cell.box input").forEach(i=>i.value="");
  document.querySelectorAll(".cell.box").forEach(el=>el.classList.remove("ok","err","hl-a","hl-d"));
  document.getElementById("hasil").className="hasil";
  document.getElementById("skorNum").textContent="0";
  document.querySelectorAll(".qi").forEach(el=>el.classList.remove("aq-a","aq-d"));
  curNum=null;curDir=null;
}
 
// ── confetti ──
function launchConfetti(){
  const C=["#ff4757","#ffd32a","#2ed573","#1e90ff","#ff6348","#a29bfe","#fd79a8","#00cec9"];
  for(let i=0;i<90;i++){
    setTimeout(()=>{
      const el=document.createElement("div");
      el.className="cf";
      const sz=6+Math.random()*10;
      el.style.cssText=`left:${Math.random()*100}vw;width:${sz}px;height:${sz}px;
        background:${C[~~(Math.random()*C.length)]};
        animation-duration:${1.8+Math.random()*2.5}s;animation-delay:${Math.random()*.7}s;
        border-radius:${Math.random()>.5?sz+"px":"2px"}`;
      document.body.appendChild(el);
      setTimeout(()=>el.remove(),5000);
    },i*22);
  }
}
 
// ── floating deco ──
function initDeco(){
  const w=document.getElementById("decos");
  ["⭐","🌟","✨","💫","🎈","🎉","🏅","🌈"].forEach((e,i)=>{
    const d=document.createElement("div");
    d.className="fdeco";d.textContent=e;
    d.style.cssText=`left:${8+i*12}%;animation-duration:${11+i*1.8}s;animation-delay:${i*1.4}s`;
    w.appendChild(d);
  });
}
 
build();renderGrid();renderSoal();initDeco();
 
// ══════════════════════════════════════════
//  BACKSOUND ENGINE (Web Audio API)
// ══════════════════════════════════════════
let audioCtx=null, musicPlaying=false, musicNodes=[], musicScheduled=false;
 
function getCtx(){
  if(!audioCtx) audioCtx=new(window.AudioContext||window.webkitAudioContext)();
  return audioCtx;
}
 
// Membuat nada dengan frekuensi, waktu mulai, durasi, dan volume
function playNote(ctx, freq, startTime, dur, vol=0.18, type="sine"){
  const osc=ctx.createOscillator();
  const gain=ctx.createGain();
  osc.connect(gain); gain.connect(ctx.destination);
  osc.type=type; osc.frequency.value=freq;
  gain.gain.setValueAtTime(0,startTime);
  gain.gain.linearRampToValueAtTime(vol, startTime+0.02);
  gain.gain.exponentialRampToValueAtTime(0.001, startTime+dur);
  osc.start(startTime); osc.stop(startTime+dur+0.05);
  return osc;
}
 
// Melodi lagu anak ceria (Do Re Mi style — C major)
// Notasi: [frekuensi Hz, durasi detik]
const MELODY=[
  [523,0.25],[587,0.25],[659,0.25],[698,0.25],  // C D E F
  [784,0.5 ],[784,0.25],[698,0.25],              // G G F
  [659,0.25],[698,0.25],[784,0.5 ],              // E F G
  [523,0.25],[659,0.25],[523,0.5 ],              // C E C
  [659,0.25],[784,0.25],[880,0.25],[784,0.25],   // E G A G
  [698,0.25],[659,0.25],[587,0.5 ],              // F E D
  [523,0.25],[587,0.25],[659,0.25],[523,0.25],   // C D E C
  [659,0.5 ],[523,0.5 ],                         // E C
  [784,0.25],[880,0.25],[988,0.25],[880,0.25],   // G A B A
  [784,0.25],[698,0.25],[659,0.5 ],              // G F E
  [523,0.25],[587,0.25],[659,0.25],[698,0.25],   // C D E F
  [784,1.0 ],                                     // G (panjang)
];
 
// Iringan chord (bass)
const BASS=[
  [262,1],[294,1],[330,1],[349,1],  // C D E F bass
  [392,1],[392,1],[349,1],[330,1],
  [262,1],[330,1],[262,2],
  [392,2],[392,2],[330,2],[262,2],
];
 
function scheduleMelody(){
  if(!musicPlaying) return;
  const ctx=getCtx();
  const now=ctx.currentTime;
  let t=now;
  const oscs=[];
  // main melody
  MELODY.forEach(([f,d])=>{
    oscs.push(playNote(ctx,f,t,d,0.16,"sine"));
    t+=d;
  });
  // bass line (satu oktaf lebih rendah, volume lebih pelan)
  let bt=now;
  BASS.forEach(([f,d])=>{
    oscs.push(playNote(ctx,f,bt,d*0.5,0.07,"triangle"));
    bt+=d*0.5;
  });
  // tambah perkusi ringan (kick)
  for(let i=0;i<8;i++){
    const kickT=now+i*0.5;
    const buf=ctx.createBuffer(1,ctx.sampleRate*0.1,ctx.sampleRate);
    const data=buf.getChannelData(0);
    for(let j=0;j<data.length;j++) data[j]=(Math.random()*2-1)*Math.exp(-j/800);
    const src=ctx.createBufferSource();
    const gk=ctx.createGain();
    src.buffer=buf; src.connect(gk); gk.connect(ctx.destination);
    gk.gain.setValueAtTime(0.12,kickT);
    gk.gain.exponentialRampToValueAtTime(0.001,kickT+0.1);
    src.start(kickT);
    oscs.push(src);
  }
  musicNodes=oscs;
  // hitung total durasi melodi lalu loop
  const totalDur=MELODY.reduce((s,[,d])=>s+d,0);
  setTimeout(()=>{ if(musicPlaying) scheduleMelody(); }, (totalDur-0.1)*1000);
}
 
function toggleMusic(){
  if(!musicPlaying){
    // mulai
    musicPlaying=true;
    getCtx().resume().then(()=>scheduleMelody());
    document.getElementById("musicLabel").textContent="Matikan Musik";
    document.getElementById("btnMusic").style.background="linear-gradient(135deg,#e040fb,#7c4dff)";
    document.querySelectorAll(".music-note").forEach(el=>el.classList.remove("paused"));
  } else {
    // stop
    musicPlaying=false;
    musicNodes.forEach(n=>{try{n.stop();}catch(e){}});
    musicNodes=[];
    document.getElementById("musicLabel").textContent="Nyalakan Musik";
    document.getElementById("btnMusic").style.background="linear-gradient(135deg,#7c4dff,#e040fb)";
    document.querySelectorAll(".music-note").forEach(el=>el.classList.add("paused"));
  }
}
 
// ── Sound effects ──
function sfxTik(){
  try{
    const ctx=getCtx(); const t=ctx.currentTime;
    playNote(ctx,880,t,0.08,0.12,"sine");
  }catch(e){}
}
function sfxBenar(){
  try{
    const ctx=getCtx(); const t=ctx.currentTime;
    [523,659,784,1047].forEach((f,i)=>playNote(ctx,f,t+i*0.08,0.15,0.15,"sine"));
  }catch(e){}
}
function sfxSalah(){
  try{
    const ctx=getCtx(); const t=ctx.currentTime;
    playNote(ctx,200,t,0.2,0.15,"sawtooth");
    playNote(ctx,150,t+0.1,0.2,0.12,"sawtooth");
  }catch(e){}
}
function sfxMenang(){
  try{
    const ctx=getCtx(); const t=ctx.currentTime;
    const fanfare=[523,659,784,1047,1319,1047,784,659,523,784,1047];
    fanfare.forEach((f,i)=>playNote(ctx,f,t+i*0.1,0.18,0.18,"sine"));
  }catch(e){}
}
</script>
</body>
</html>

