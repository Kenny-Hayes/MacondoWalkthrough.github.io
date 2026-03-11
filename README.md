# MacondoWalkthrough.github.io
Walkthrough the magical world of Macondo from Gabriel Garcia Marquez's "One Hundred Years of Solitude"
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Macondo & Nostalgia — One Hundred Years of Solitude</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400;1,600;1,700&family=Cinzel:wght@400;600;700&display=swap');

:root {
  --gold:#c9a84c; --gold-light:#e8c878; --gold-dim:#7a6030;
  --amber:#e8b86d; --rust:#8b3a1a;
  --dark:#090805; --dark2:#120f08;
  --parchment:#f0e2c0; --parchment-dim:#a09070;
  --dust:#9a8060; --sepia:#c8a878;
  --nostalgia:#d4a0c0; --nostalgia-dim:#7a4060;
}
*{margin:0;padding:0;box-sizing:border-box;}
body{background:var(--dark);color:var(--parchment);font-family:'Cormorant Garamond',Georgia,serif;overflow-x:hidden;cursor:none;}

#cursor{position:fixed;width:18px;height:18px;border:1px solid var(--gold);border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);mix-blend-mode:difference;}
#cursor-dot{position:fixed;width:4px;height:4px;background:var(--gold);border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);}

/* INTRO */
#intro{position:fixed;inset:0;background:radial-gradient(ellipse at 40% 50%,#1a2a0a 0%,#09080a 60%,#090805 100%);display:flex;flex-direction:column;align-items:center;justify-content:center;z-index:1000;transition:opacity 1.8s ease;}
#intro.out{opacity:0;pointer-events:none;}
.intro-ornament{font-size:1.4rem;color:var(--gold-dim);letter-spacing:.8em;margin-bottom:1.8rem;animation:fadeUp 2s ease .2s both;}
.intro-title{font-family:'Cinzel',serif;font-size:clamp(3rem,8vw,7rem);font-weight:700;color:var(--gold);text-align:center;letter-spacing:.15em;line-height:1;animation:fadeUp 2s ease .4s both;text-shadow:0 0 80px rgba(201,168,76,.3);}
.intro-amp{font-family:'Cormorant Garamond',serif;font-style:italic;font-size:clamp(1.1rem,2.5vw,1.8rem);color:var(--nostalgia);letter-spacing:.25em;text-align:center;margin-top:.8rem;animation:fadeUp 2s ease .7s both;}
.intro-line{width:200px;height:1px;background:linear-gradient(90deg,transparent,var(--gold),var(--nostalgia),transparent);margin:2rem auto;animation:fadeUp 2s ease .9s both;}
.intro-quote{max-width:500px;text-align:center;font-style:italic;font-size:clamp(.95rem,1.8vw,1.1rem);color:var(--dust);line-height:1.8;animation:fadeUp 2s ease 1.1s both;padding:0 2rem;}
.intro-author{font-family:'Cinzel',serif;font-size:.7rem;letter-spacing:.2em;color:var(--gold-dim);margin-top:1rem;animation:fadeUp 2s ease 1.3s both;}
.enter-btn{margin-top:2.8rem;padding:.9rem 3.5rem;border:1px solid var(--gold);background:transparent;color:var(--gold);font-family:'Cinzel',serif;font-size:.8rem;letter-spacing:.25em;text-transform:uppercase;cursor:none;transition:all .4s;animation:fadeUp 2s ease 1.6s both;position:relative;overflow:hidden;}
.enter-btn::before{content:'';position:absolute;inset:0;background:linear-gradient(90deg,var(--gold-dim),var(--gold));transform:translateX(-100%);transition:transform .4s;z-index:-1;}
.enter-btn:hover::before{transform:translateX(0);}
.enter-btn:hover{color:var(--dark);}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:200;padding:0 3rem;height:60px;display:flex;justify-content:space-between;align-items:center;background:rgba(9,8,5,.96);border-bottom:1px solid rgba(201,168,76,.12);backdrop-filter:blur(10px);}
.nav-logo{font-family:'Cinzel',serif;font-size:.9rem;letter-spacing:.2em;color:var(--gold);}
.nav-tabs{display:flex;}
.nav-tab{padding:.4rem 1.2rem;background:transparent;border:none;border-bottom:2px solid transparent;color:var(--dust);font-family:'Cinzel',serif;font-size:.65rem;letter-spacing:.18em;text-transform:uppercase;cursor:none;transition:all .3s;height:60px;display:flex;align-items:center;}
.nav-tab:hover{color:var(--parchment);}
.nav-tab.active{color:var(--gold);border-bottom-color:var(--gold);}

section{display:none;min-height:100vh;}
section.active{display:block;}

/* ===== NOSTALGIA SECTION ===== */
#nostalgia-section{background:var(--dark2);padding:60px 0 6rem;}
.sec-header{text-align:center;padding:3.5rem 2rem 2.5rem;position:relative;}
.sec-header::before{content:'';position:absolute;top:0;left:50%;transform:translateX(-50%);width:1px;height:3.5rem;background:linear-gradient(180deg,transparent,var(--nostalgia));}
.eyebrow{font-family:'Cinzel',serif;font-size:.65rem;letter-spacing:.35em;color:var(--nostalgia-dim);text-transform:uppercase;margin-bottom:.8rem;}
.sec-title{font-family:'Cinzel',serif;font-size:clamp(1.8rem,4vw,3rem);font-weight:700;color:var(--gold);line-height:1.2;}
.sec-sub{font-style:italic;font-size:1.05rem;color:var(--dust);margin-top:.7rem;max-width:580px;margin-left:auto;margin-right:auto;line-height:1.7;}

.nos-intro-block{max-width:800px;margin:0 auto 3rem;padding:2.5rem 3rem;border:1px solid rgba(212,160,192,.2);background:linear-gradient(135deg,rgba(212,160,192,.04) 0%,rgba(201,168,76,.03) 100%);position:relative;}
.nos-intro-block::before{content:'"';position:absolute;top:-1.2rem;left:2rem;font-family:'Cormorant Garamond',serif;font-size:5rem;color:rgba(212,160,192,.12);line-height:1;}
.nos-intro-block p{font-size:1.08rem;line-height:1.85;color:var(--parchment-dim);font-style:italic;}
.nos-intro-block strong{color:var(--nostalgia);font-style:normal;}

.author-note{max-width:800px;margin:0 auto 3.5rem;padding:0 2rem;display:grid;grid-template-columns:3px 1fr;gap:1.5rem;}
.author-note .bar{background:var(--gold);border-radius:2px;}
.author-note h3{font-family:'Cinzel',serif;font-size:.7rem;letter-spacing:.25em;color:var(--gold);text-transform:uppercase;margin-bottom:.5rem;}
.author-note p{font-size:1.02rem;line-height:1.8;color:var(--parchment-dim);}

.nos-grid{max-width:1100px;margin:0 auto;padding:0 2rem;display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:1.5px;background:rgba(212,160,192,.1);border:1px solid rgba(212,160,192,.1);}
.nos-card{background:var(--dark2);padding:2.2rem 2.4rem;position:relative;overflow:hidden;cursor:none;transition:background .4s;}
.nos-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,transparent,var(--nostalgia),transparent);transform:scaleX(0);transition:transform .5s;}
.nos-card:hover::before{transform:scaleX(1);}
.nos-card:hover{background:rgba(212,160,192,.04);}
.card-num{font-family:'Cinzel',serif;font-size:2.8rem;font-weight:700;color:rgba(212,160,192,.07);position:absolute;top:.8rem;right:1.2rem;line-height:1;user-select:none;}
.card-icon{font-size:1.6rem;margin-bottom:.8rem;display:block;}
.card-tag{display:inline-block;padding:.2rem .7rem;border:1px solid var(--nostalgia-dim);font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:.2em;color:var(--nostalgia-dim);text-transform:uppercase;margin-bottom:.8rem;}
.nos-card h3{font-family:'Cormorant Garamond',serif;font-size:1.35rem;font-weight:600;color:var(--amber);margin-bottom:.3rem;line-height:1.3;}
.nos-card .character{font-style:italic;color:var(--nostalgia);font-size:.88rem;margin-bottom:.8rem;}
.nos-card p{font-size:.95rem;line-height:1.8;color:var(--parchment-dim);}
.quote-pull{margin-top:1rem;padding:.7rem 1rem;border-left:2px solid var(--nostalgia-dim);font-style:italic;font-size:.88rem;color:var(--dust);line-height:1.6;}

.theme-strip{max-width:800px;margin:4rem auto 0;padding:0 2rem;text-align:center;}
.theme-strip h3{font-family:'Cinzel',serif;font-size:.65rem;letter-spacing:.3em;color:var(--gold-dim);margin-bottom:1.5rem;text-transform:uppercase;}
.theme-chips{display:flex;flex-wrap:wrap;gap:.7rem;justify-content:center;}
.chip{padding:.45rem 1.1rem;border:1px solid rgba(201,168,76,.22);font-size:.85rem;font-style:italic;color:var(--dust);transition:all .3s;}
.chip:hover{border-color:var(--gold);color:var(--gold);}

/* ===== 3D SCENE ===== */
#scene-section{position:relative;height:100vh;overflow:hidden;padding-top:0;}
#three-canvas{width:100%;height:100%;display:block;}
.scene-ui{position:absolute;inset:0;pointer-events:none;display:flex;flex-direction:column;justify-content:space-between;}
.scene-top{padding:70px 2.5rem 0;pointer-events:all;}
.era-badge{display:inline-flex;align-items:center;gap:.7rem;padding:.45rem 1.1rem;border:1px solid rgba(201,168,76,.28);background:rgba(9,8,5,.72);backdrop-filter:blur(6px);}
.era-badge-num{font-family:'Cinzel',serif;font-size:.62rem;letter-spacing:.2em;color:var(--gold-dim);}
.era-badge-lbl{font-family:'Cinzel',serif;font-size:.62rem;letter-spacing:.2em;color:var(--gold);text-transform:uppercase;}
.scene-bottom{padding:0 2.5rem 2.5rem;background:linear-gradient(0deg,rgba(9,8,5,.97) 0%,rgba(9,8,5,.5) 60%,transparent 100%);padding-top:5rem;}
.scene-era-name{font-family:'Cinzel',serif;font-size:clamp(1.6rem,3.5vw,3rem);font-weight:700;color:var(--gold);line-height:1.1;transition:all .5s;}
.scene-era-sub{font-style:italic;font-size:1rem;color:var(--amber);margin-top:.35rem;transition:all .5s;}
.scene-nos-note{margin-top:.9rem;display:inline-flex;align-items:flex-start;gap:.7rem;max-width:560px;padding:.7rem 1.1rem;border-left:2px solid var(--nostalgia-dim);background:rgba(212,160,192,.05);backdrop-filter:blur(4px);}
.scene-nos-note .snlbl{font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:.18em;color:var(--nostalgia);text-transform:uppercase;white-space:nowrap;padding-top:.1rem;}
.scene-nos-note .sntxt{font-style:italic;font-size:.88rem;color:var(--dust);line-height:1.5;}
.era-dots{position:absolute;right:2rem;top:50%;transform:translateY(-50%);display:flex;flex-direction:column;gap:.55rem;pointer-events:all;}
.era-dot{position:relative;width:9px;height:9px;border:1px solid rgba(201,168,76,.4);border-radius:50%;background:transparent;cursor:none;transition:all .3s;}
.era-dot.active{background:var(--gold);border-color:var(--gold);box-shadow:0 0 10px rgba(201,168,76,.5);}
.era-dot:hover{border-color:var(--gold);}
.era-dot-lbl{position:absolute;right:17px;top:50%;transform:translateY(-50%);white-space:nowrap;font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:.1em;color:var(--dust);opacity:0;transition:opacity .2s;pointer-events:none;text-transform:uppercase;background:rgba(9,8,5,.85);padding:.18rem .45rem;}
.era-dot:hover .era-dot-lbl{opacity:1;}
.scene-arrows{position:absolute;bottom:2.5rem;right:2.5rem;display:flex;gap:.4rem;pointer-events:all;}
.arr-btn{width:34px;height:34px;border:1px solid rgba(201,168,76,.3);background:rgba(9,8,5,.6);backdrop-filter:blur(4px);color:var(--gold-dim);font-size:.9rem;cursor:none;transition:all .3s;display:flex;align-items:center;justify-content:center;}
.arr-btn:hover{border-color:var(--gold);color:var(--gold);}

/* ===== MAP ===== */
#map-section{background:radial-gradient(ellipse at 50% 20%,#111a08 0%,var(--dark) 65%);padding:60px 0 5rem;}
.map-layout{display:grid;grid-template-columns:200px 1fr 250px;max-width:1280px;margin:0 auto;min-height:calc(100vh - 60px);}
.map-left{border-right:1px solid rgba(201,168,76,.1);padding:1.8rem 1.2rem;display:flex;flex-direction:column;gap:.3rem;overflow-y:auto;}
.map-panel-title{font-family:'Cinzel',serif;font-size:.6rem;letter-spacing:.25em;color:var(--gold-dim);text-transform:uppercase;padding-bottom:.8rem;border-bottom:1px solid rgba(201,168,76,.1);margin-bottom:.4rem;}
.map-era-btn{padding:.75rem .9rem;background:transparent;border:none;border-left:2px solid transparent;color:var(--dust);font-family:'Cormorant Garamond',serif;font-size:.98rem;cursor:none;transition:all .3s;text-align:left;line-height:1.3;}
.map-era-btn:hover{color:var(--parchment);border-left-color:var(--gold-dim);}
.map-era-btn.active{color:var(--gold);border-left-color:var(--gold);background:rgba(201,168,76,.05);}
.map-era-btn small{display:block;font-size:.72rem;color:var(--dust);font-style:italic;margin-top:.1rem;}
.map-center{display:flex;flex-direction:column;align-items:center;padding:1.8rem 1.5rem;}
.map-title-area{text-align:center;margin-bottom:1.2rem;}
.map-era-heading{font-family:'Cinzel',serif;font-size:1.2rem;font-weight:700;color:var(--gold);}
.map-era-pop{font-style:italic;font-size:.82rem;color:var(--dust);margin-top:.25rem;}
#macondo-svg{width:100%;max-width:620px;border:1px solid rgba(201,168,76,.15);background:rgba(0,0,0,.2);}
.map-legend{display:flex;flex-wrap:wrap;gap:.9rem;justify-content:center;margin-top:1rem;}
.leg-item{display:flex;align-items:center;gap:.35rem;font-size:.75rem;color:var(--dust);font-style:italic;}
.leg-dot{width:9px;height:9px;border-radius:2px;flex-shrink:0;}
.map-right{border-left:1px solid rgba(201,168,76,.1);padding:1.8rem 1.3rem;overflow-y:auto;}
.map-desc-era{font-family:'Cormorant Garamond',serif;font-size:1.25rem;font-style:italic;color:var(--amber);margin-bottom:.7rem;}
.map-desc-text{font-size:.92rem;line-height:1.82;color:var(--parchment-dim);margin-bottom:1.3rem;}
.map-locs-title{font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:.2em;color:var(--gold-dim);text-transform:uppercase;margin-bottom:.8rem;}
.map-loc-item{display:flex;gap:.7rem;margin-bottom:.7rem;align-items:flex-start;}
.map-loc-dot{width:7px;height:7px;border-radius:50%;flex-shrink:0;margin-top:.3rem;}
.map-loc-info strong{display:block;font-size:.83rem;color:var(--parchment);font-style:italic;font-family:'Cormorant Garamond',serif;font-weight:600;}
.map-loc-info span{font-size:.76rem;color:var(--dust);line-height:1.4;}
.map-nos-box{margin-top:1.3rem;padding:.9rem 1rem;border:1px solid rgba(212,160,192,.15);background:rgba(212,160,192,.04);}
.map-nos-box h4{font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:.2em;color:var(--nostalgia-dim);text-transform:uppercase;margin-bottom:.45rem;}
.map-nos-box p{font-size:.83rem;font-style:italic;color:var(--dust);line-height:1.6;}

/* ===== TIMELINE ===== */
#timeline-section{background:var(--dark);padding:60px 0 6rem;}
.tl-wrap{max-width:880px;margin:0 auto;padding:0 2rem;}
.tl-gen-head{font-family:'Cinzel',serif;font-size:.62rem;letter-spacing:.25em;color:var(--gold-dim);text-transform:uppercase;padding:1.5rem 0 .4rem 0;border-top:1px solid rgba(201,168,76,.08);margin-top:.5rem;}
.tl-event{display:grid;grid-template-columns:72px 1px 1fr;gap:0 1.8rem;opacity:0;transform:translateY(14px);transition:opacity .5s,transform .5s;}
.tl-event.vis{opacity:1;transform:translateY(0);}
.tl-left{text-align:right;padding:1.8rem 0;}
.tl-gen-lbl{font-family:'Cinzel',serif;font-size:.55rem;letter-spacing:.12em;color:var(--gold-dim);text-transform:uppercase;line-height:1.4;}
.tl-line-col{display:flex;flex-direction:column;align-items:center;}
.tl-line-seg{flex:1;width:1px;background:rgba(201,168,76,.18);}
.tl-node{width:9px;height:9px;flex-shrink:0;border:1px solid var(--gold);border-radius:50%;background:var(--dark);margin:.28rem 0;transition:background .3s,box-shadow .3s;}
.tl-event:hover .tl-node{background:var(--gold);box-shadow:0 0 10px rgba(201,168,76,.5);}
.tl-right{padding:1.6rem 0;border-bottom:1px solid rgba(201,168,76,.06);}
.tl-tags{display:flex;gap:.35rem;margin-bottom:.5rem;flex-wrap:wrap;}
.tl-tag{padding:.12rem .55rem;border:1px solid;font-family:'Cinzel',serif;font-size:.52rem;letter-spacing:.14em;text-transform:uppercase;}
.tl-tag.founding{border-color:#2a5a2a;color:#4a9a4a;}
.tl-tag.war{border-color:#5a1515;color:#c04040;}
.tl-tag.progress{border-color:var(--gold-dim);color:var(--gold);}
.tl-tag.decay{border-color:#5a4a30;color:#9a8050;}
.tl-tag.nostalgia{border-color:var(--nostalgia-dim);color:var(--nostalgia);}
.tl-tag.supernatural{border-color:#503070;color:#a070d0;}
.tl-title{font-family:'Cormorant Garamond',serif;font-size:1.3rem;font-weight:600;font-style:italic;color:var(--amber);margin-bottom:.45rem;line-height:1.3;}
.tl-body{font-size:.93rem;line-height:1.8;color:var(--parchment-dim);}
.tl-nos{margin-top:.7rem;padding:.55rem .85rem;border-left:2px solid var(--nostalgia-dim);background:rgba(212,160,192,.04);font-style:italic;font-size:.83rem;color:var(--dust);line-height:1.5;}
.tl-nos::before{content:'✦ Nostalgia: ';color:var(--nostalgia);font-style:normal;font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:.1em;}

@keyframes fadeUp{from{opacity:0;transform:translateY(22px)}to{opacity:1;transform:translateY(0)}}

/* Rain */
#rain-wrap{position:fixed;inset:0;pointer-events:none;z-index:1;opacity:0;transition:opacity 2s;}
#rain-wrap.on{opacity:1;}
#rain-cnv{width:100%;height:100%;}

/* ===== INLINE EDIT MODE ===== */
#edit-toggle {
  position: fixed;bottom: 2rem;right: 2rem;z-index: 5000;display: none;align-items: center;gap: .6rem;padding: .6rem 1.4rem;background: rgba(9,8,5,.92);border: 1px solid var(--gold);color: var(--gold);font-family: 'Cinzel', serif;font-size: .65rem;letter-spacing: .18em;text-transform: uppercase;cursor: none;transition: all .3s;backdrop-filter: blur(8px);
}
#edit-toggle:hover { background: var(--gold); color: var(--dark); }
#edit-toggle .dot { width: 8px; height: 8px; border-radius: 50%; background: var(--gold-dim); transition: background .3s; }
body.editing #edit-toggle .dot { background: #60e060; }
body.editing #edit-toggle { border-color: #60e060; color: #60e060; }
body.editing #edit-toggle:hover { background: #60e060; color: var(--dark); }
[data-editable] { position: relative; transition: outline .2s; outline: 1px dashed transparent; border-radius: 2px; }
body.editing [data-editable]:hover { outline: 1px dashed rgba(201,168,76,.5); cursor: text !important; }
body.editing [data-editable]:focus { outline: 1px solid var(--gold); background: rgba(201,168,76,.06); cursor: text !important; }
.edit-hint { position: fixed; pointer-events: none; z-index: 6000; background: rgba(9,8,5,.9); border: 1px solid var(--gold); color: var(--gold); font-family: 'Cinzel', serif; font-size: .6rem; letter-spacing: .12em; padding: .3rem .7rem; opacity: 0; transition: opacity .2s; white-space: nowrap; }
.edit-hint.show { opacity: 1; }
#edit-toast { position: fixed; bottom: 5rem; right: 2rem; z-index: 6000; background: rgba(9,8,5,.95); border-left: 2px solid #60e060; color: #90f090; font-family: 'Cinzel', serif; font-size: .65rem; letter-spacing: .1em; padding: .6rem 1.2rem; opacity: 0; transform: translateY(10px); transition: all .4s; pointer-events: none; }
#edit-toast.show { opacity: 1; transform: translateY(0); }
</style>
</head>
<body>

<div id="cursor"></div>
<div id="cursor-dot"></div>
<div id="rain-wrap"><canvas id="rain-cnv"></canvas></div>

<!-- INTRO -->
<div id="intro">
  <div class="intro-ornament">✦ &nbsp; ✦ &nbsp; ✦</div>
  <div class="intro-title">MACONDO</div>
  <div class="intro-amp">& The Architecture of Nostalgia</div>
  <div class="intro-line"></div>
  <div class="intro-quote">"He was still too young to know that the heart's memory eliminates the bad and magnifies the good, and that thanks to this artifice we manage to endure the burden of the past."</div>
  <div class="intro-author">— Gabriel García Márquez, One Hundred Years of Solitude</div>
  <button class="enter-btn" id="enter-btn">Begin the Journey</button>
</div>

<!-- EDIT UI -->
<button id="edit-toggle"><span class="dot"></span> Edit Mode</button>
<div class="edit-hint" id="edit-hint">Click to edit</div>
<div id="edit-toast">✓ Saved</div>

<!-- APP -->
<div id="app" style="display:none">
  <nav>
    <div class="nav-logo" data-editable contenteditable="false" spellcheck="false">MACONDO</div>
    <div class="nav-tabs">
      <button class="nav-tab active" data-sec="nostalgia-section">Nostalgia</button>
      <button class="nav-tab" data-sec="scene-section">3D World</button>
      <button class="nav-tab" data-sec="map-section">Living Map</button>
      <button class="nav-tab" data-sec="timeline-section">Chronicle</button>
    </div>
  </nav>

  <!-- ===== NOSTALGIA ===== -->
  <section id="nostalgia-section" class="active">
    <div class="sec-header">
      <div class="eyebrow" data-editable contenteditable="false" spellcheck="false">Thematic Analysis</div>
      <div class="sec-title" data-editable contenteditable="false" spellcheck="false">Nostalgia in One Hundred Years of Solitude</div>
      <div class="sec-sub" data-editable contenteditable="false" spellcheck="false">How García Márquez uses longing for the irretrievable past as the engine of fate, character, and the ultimate destruction of Macondo</div>
    </div>

    <div class="nos-intro-block">
      <p data-editable contenteditable="false" spellcheck="false">Nostalgia in this novel is not merely sentiment — it is <strong>architecture</strong>. García Márquez constructs Macondo as a place that is always already vanishing, where every character's deepest wound is their inability to return to a paradise they remember — or <em>imagine</em> they remember. The town and the Buendía family do not die from war or plague, but from the <strong>insistence on living inside a remembered past</strong> rather than the present.</p>
    </div>

    <div class="author-note">
      <div class="bar"></div>
      <div>
        <h3>Why García Márquez Used Nostalgia</h3>
        <p>Writing in 1967, García Márquez was mourning the loss of the Caribbean Colombia of his childhood — its oral traditions, its myths, its isolated village life rapidly being erased by modernization and American corporate influence. Nostalgia is his literary instrument for arguing that <em>all civilizations carry within them the seeds of their own forgetting</em>. The Buendías' inability to escape cyclical repetition mirrors Latin America's repeated cycles of revolution, exploitation, and erasure. By making nostalgia the fatal flaw of every generation, he critiques both personal and political refusal to change.</p>
      </div>
    </div>

    <div class="nos-grid">
      <div class="nos-card">
        <div class="card-num">01</div>
        <span class="card-icon">🏡</span>
        <div class="card-tag">The Founding</div>
        <h3>The Paradise That Never Was</h3>
        <div class="character">José Arcadio Buendía & The Founding Families</div>
        <p>The founding of Macondo is itself an act of nostalgic reconstruction. José Arcadio leaves his original village out of guilt, yet the new village he builds is modeled on an idealized memory of communal paradise — arranged so every house has equal access to the river. His descendants spend generations trying to return to this imagined original purity, a purity that never actually existed.</p>
        <div class="quote-pull">"Macondo was a village of twenty adobe houses built on the bank of a river of clear water that ran along a bed of polished stones, which were white and enormous, like prehistoric eggs."</div>
      </div>
      <div class="nos-card">
        <div class="card-num">02</div>
        <span class="card-icon">🚪</span>
        <div class="card-tag">Self-Imprisonment</div>
        <h3>The Room of Endless Waiting</h3>
        <div class="character">Rebeca Buendía</div>
        <p>After the death of José Arcadio, Rebeca seals herself inside her house for decades, wearing only a black dress and letting the garden swallow the walls. She arrived as a child clutching a bag containing her parents' bones — the literal baggage of the dead past. Her entire existence becomes a monument to what she lost: she refuses the present entirely, living only in the amber of grief and memory.</p>
        <div class="quote-pull">She locked herself inside and nailed the door and windows shut — buried alive with her grief for over forty years, refusing any future that did not contain the lost past.</div>
      </div>
      <div class="nos-card">
        <div class="card-num">03</div>
        <span class="card-icon">🐟</span>
        <div class="card-tag">Repetition & Futility</div>
        <h3>The Golden Fish Melted Down</h3>
        <div class="character">Colonel Aureliano Buendía</div>
        <p>After waging seventeen failed civil wars, the Colonel retreats to his workshop and spends his remaining years crafting tiny golden fish — then melting them down and starting over. This endless cycle is García Márquez's most devastating image of nostalgia as paralysis. The Colonel is not a craftsman; he is a man trying to recover a version of himself that existed before the wars. The fish are never finished because the past can never be recovered.</p>
        <div class="quote-pull">He made seventeen little golden fishes and then he melted them down and made them again, forever — reaching for a self the wars had dissolved.</div>
      </div>
      <div class="nos-card">
        <div class="card-num">04</div>
        <span class="card-icon">👑</span>
        <div class="card-tag">Class & Illusion</div>
        <h3>The Kingdom That Never Existed</h3>
        <div class="character">Fernanda del Carpio</div>
        <p>Fernanda is nostalgic for a social status and aristocratic order she was raised to expect but that never truly existed. Raised to be a queen in a decaying family, she brings rigid formality utterly alien to Macondo's spirit — eating from a golden chamber pot, consulting invisible doctors by letter. Her nostalgia is for a hierarchical past that was itself a fiction, making her tragedy doubly ironic: she mourns something that never was.</p>
        <div class="quote-pull">She had been raised to become a queen, trained in the rigors of an imaginary monarchy — mourning a world she had never actually possessed.</div>
      </div>
      <div class="nos-card">
        <div class="card-num">05</div>
        <span class="card-icon">📜</span>
        <div class="card-tag">Prophecy & Memory</div>
        <h3>The Parchments Remember Everything</h3>
        <div class="character">Melquíades & The Final Aureliano</div>
        <p>Melquíades' parchments — written in Sanskrit, in verse, encrypted by a century — contain the entire history of the Buendía family from beginning to end. When the last Aureliano finally deciphers them, he discovers they describe the very moment he is living. The parchments are the ultimate symbol of nostalgia made cosmic: the past and future collapse into a single moment of recognition.</p>
        <div class="quote-pull">"He had already understood that he would never leave that room, for it was foreseen that the city of mirrors would be wiped out by the wind."</div>
      </div>
      <div class="nos-card">
        <div class="card-num">06</div>
        <span class="card-icon">🌿</span>
        <div class="card-tag">The Town as Memory</div>
        <h3>Macondo as Collective Nostalgia</h3>
        <div class="character">The Town Itself</div>
        <p>Macondo is a collective character whose arc mirrors the lifespan of memory: vibrant in youth, distorted in middle age, erased at the end. The town repeatedly forgets its own history — the insomnia plague erases individual memory; the banana massacre is erased by state decree. García Márquez argues that nostalgia without the willingness to confront the true past is not memory — it is a beautiful lie that destroys everything it touches.</p>
        <div class="quote-pull">The inhabitants of Macondo were kept in a permanent alternation between excitement and disappointment, doubt and revelation — never quite able to remember why.</div>
      </div>
    </div>

    <div class="theme-strip">
      <h3>Core Themes of Nostalgia in the Novel</h3>
      <div class="theme-chips">
        <span class="chip">Cyclical Repetition</span>
        <span class="chip">Grief as Architecture</span>
        <span class="chip">Imagined Paradise</span>
        <span class="chip">Political Amnesia</span>
        <span class="chip">Memory vs. History</span>
        <span class="chip">The Unbreakable Past</span>
        <span class="chip">Solitude as Consequence</span>
        <span class="chip">Identity & Erasure</span>
      </div>
    </div>
  </section>

  <!-- ===== 3D SCENE ===== -->
  <section id="scene-section">
    <canvas id="three-canvas"></canvas>
    <div class="scene-ui">
      <div class="scene-top">
        <div class="era-badge">
          <span class="era-badge-num" id="era-num">ERA 01/06</span>
          <span style="color:var(--gold-dim)">|</span>
          <span class="era-badge-lbl" id="era-top-lbl">Founding</span>
        </div>
      </div>
      <div class="scene-bottom">
        <div class="scene-era-name" id="era-name">The Founding of Macondo</div>
        <div class="scene-era-sub" id="era-sub">Twenty adobe houses beside a river of clear water</div>
        <div class="scene-nos-note">
          <span class="snlbl">Nostalgia</span>
          <span class="sntxt" id="era-nos">A utopia built from guilt — the original paradise the whole family will spend a century trying to return to.</span>
        </div>
      </div>
    </div>
    <div class="era-dots" id="era-dots"></div>
    <div class="scene-arrows">
      <button class="arr-btn" id="prev-era">←</button>
      <button class="arr-btn" id="next-era">→</button>
    </div>
  </section>

  <!-- ===== MAP ===== -->
  <section id="map-section">
    <div class="map-layout">
      <div class="map-left">
        <div class="map-panel-title">Select Era</div>
        <div id="map-era-list"></div>
      </div>
      <div class="map-center">
        <div class="map-title-area">
          <div class="map-era-heading" id="map-heading">The Founding</div>
          <div class="map-era-pop" id="map-pop">~20 inhabitants · Year 1</div>
        </div>
        <svg id="macondo-svg" viewBox="0 0 700 560" xmlns="http://www.w3.org/2000/svg"></svg>
        <div class="map-legend">
          <div class="leg-item"><div class="leg-dot" style="background:#2a6a2a"></div>Jungle</div>
          <div class="leg-item"><div class="leg-dot" style="background:#4060a0"></div>River</div>
          <div class="leg-item"><div class="leg-dot" style="background:#c9a84c"></div>Buendía House</div>
          <div class="leg-item"><div class="leg-dot" style="background:#d8c880"></div>Homes</div>
          <div class="leg-item"><div class="leg-dot" style="background:#6b7080"></div>Military/Gov.</div>
          <div class="leg-item"><div class="leg-dot" style="background:#8b3a1a"></div>Commerce</div>
          <div class="leg-item"><div class="leg-dot" style="background:#d4a0c0"></div>Nostalgia Site</div>
        </div>
      </div>
      <div class="map-right">
        <div class="map-panel-title">Era Details</div>
        <div class="map-desc-era" id="map-desc-era">The Founding</div>
        <div class="map-desc-text" id="map-desc-text"></div>
        <div class="map-locs-title">Key Locations</div>
        <div id="map-locs"></div>
        <div class="map-nos-box">
          <h4>Nostalgia Connection</h4>
          <p id="map-nos-p"></p>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== TIMELINE ===== -->
  <section id="timeline-section">
    <div class="sec-header" style="position:relative;">
      <div style="position:absolute;top:0;left:50%;transform:translateX(-50%);width:1px;height:3.5rem;background:linear-gradient(180deg,transparent,var(--gold));"></div>
      <div class="eyebrow">Complete Chronicle</div>
      <div class="sec-title">Seven Generations of Macondo</div>
      <div class="sec-sub">Every pivotal event, with its nostalgic undercurrent</div>
    </div>
    <div class="tl-wrap" id="tl-track"></div>
  </section>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
// ===================== CURSOR =====================
const $c=document.getElementById('cursor');
const $d=document.getElementById('cursor-dot');
document.addEventListener('mousemove',e=>{
  $c.style.left=e.clientX+'px';$c.style.top=e.clientY+'px';
  $d.style.left=e.clientX+'px';$d.style.top=e.clientY+'px';
});

// ===================== DATA =====================
const ERAS=[
  {id:0,label:'Founding',name:'The Founding of Macondo',sub:'Twenty adobe houses beside a river of clear water',nos:'A utopia built from guilt — the original paradise the whole family will spend a century trying to return to.',sky:0x0a1408,fog:0x0a1408,fd:.018,amb:.45,dirC:0xffe8c0,dirI:.7,gc:0x1a2a10,rc:0x2060a0,bc:8,tc:45,st:'paradise'},
  {id:1,label:'Gypsies',name:'The Age of Gypsies & Wonder',sub:'Melquíades brings ice, magnets, and the alchemy of knowledge',nos:'Melquíades writes the parchments here — encoding a nostalgia for the future, a memory of what has not yet happened.',sky:0x08080f,fog:0x08080f,fd:.015,amb:.5,dirC:0xd0c0ff,dirI:.5,gc:0x181a18,rc:0x203060,bc:14,tc:32,st:'wonder'},
  {id:2,label:'Civil Wars',name:'The Civil Wars',sub:'Colonel Aureliano Buendía wages seventeen uprisings — losing all seventeen',nos:'The Colonel\'s golden fish are nostalgia made visible: crafting and melting endlessly, reaching for a self destroyed by war.',sky:0x150505,fog:0x150505,fd:.022,amb:.28,dirC:0xff5020,dirI:.6,gc:0x2a1808,rc:0x1a1010,bc:24,tc:16,st:'war'},
  {id:3,label:'Banana Boom',name:'The Banana Boom',sub:'The United Fruit Company transforms Macondo beyond recognition',nos:'Prosperity destroys the very simplicity the founding families mourned. Progress and nostalgia are shown to be mortal enemies.',sky:0x120d04,fog:0x120d04,fd:.014,amb:.75,dirC:0xffd060,dirI:.9,gc:0x281e08,rc:0x183050,bc:42,tc:8,st:'boom'},
  {id:4,label:'The Deluge',name:'The Massacre & The Deluge',sub:'Three thousand workers. Five years of rain. Official forgetting.',nos:'The erasure of the massacre is the most political nostalgia: the state manufactures a false past, forcing people to mourn what was never allowed to exist.',sky:0x040408,fog:0x040408,fd:.04,amb:.18,dirC:0x4060a0,dirI:.3,gc:0x0f1210,rc:0x0a1525,bc:38,tc:4,st:'rain'},
  {id:5,label:'The Ruin',name:'The Long Ruin',sub:'Solitude consumes every Buendía. The parchments are finally read.',nos:'The last Aureliano reads the parchments and realizes: the family\'s entire existence was a nostalgia for itself, circular and doomed from the first word.',sky:0x060503,fog:0x060503,fd:.028,amb:.12,dirC:0x806040,dirI:.2,gc:0x150f07,rc:0x080808,bc:16,tc:3,st:'decay'},
];

// ===================== NAV =====================
document.getElementById('enter-btn').addEventListener('click',()=>{
  document.getElementById('intro').classList.add('out');
  const app=document.getElementById('app');
  app.style.display='block';
  setTimeout(()=>{initMap();initTL();},100);
});
document.querySelectorAll('.nav-tab').forEach(btn=>{
  btn.addEventListener('click',()=>{
    document.querySelectorAll('.nav-tab').forEach(b=>b.classList.remove('active'));
    document.querySelectorAll('section').forEach(s=>s.classList.remove('active'));
    btn.classList.add('active');
    document.getElementById(btn.dataset.sec).classList.add('active');
    if(btn.dataset.sec==='scene-section'&&!renderer) initThree();
    if(btn.dataset.sec==='timeline-section') setTimeout(animateTL,80);
  });
});

// ===================== THREE.JS — v3 =====================
let renderer,scene3,cam3,clk3,eraIdx=0,sceneObjs=[];
let isDragging=false,lastMX=0,lastMY=0,camPhi=0.45,camTheta=0,camR=32,autoOrbit=true;

// ---- Utilities ----
function shadeColor(hex,f){
  const r=(hex>>16)&0xff,g=(hex>>8)&0xff,b=hex&0xff,k=1+f;
  return(Math.min(255,Math.max(0,r*k))<<16)|(Math.min(255,Math.max(0,g*k))<<8)|Math.min(255,Math.max(0,b*k));
}
function mkMat(col,extra){return new THREE.MeshLambertMaterial(Object.assign({color:col},extra||{}));}
function mkMesh(geo,col,px,py,pz,rx,ry,rz,extra){
  const m=new THREE.Mesh(geo,mkMat(col,extra));
  if(px!==undefined)m.position.set(px,py,pz);
  if(rx!==undefined)m.rotation.set(rx,ry,rz);
  m.castShadow=true; m.receiveShadow=true;
  return m;
}
function addMesh(g,geo,col,px,py,pz,rx,ry,rz,extra){g.add(mkMesh(geo,col,px,py,pz,rx,ry,rz,extra));}
function B(w,h,d){return new THREE.BoxGeometry(w,h,d);}
function C(rt,rb,h,s){return new THREE.CylinderGeometry(rt,rb,h,s||8);}
function K(r,h,s){return new THREE.ConeGeometry(r,h,s||8);}
function S(r,w,h){return new THREE.SphereGeometry(r,w||8,h||6);}

// ========== BUILDINGS ==========

function makeHouse(o){
  const x=o.x||0,z=o.z||0,w=o.w||2.2,d=o.d||1.8,h=o.h||2.2;
  const wc=o.wc||0xf0e8d0,rc=o.rc||0xb03c18;
  const g=new THREE.Group();

  // Body
  addMesh(g,B(w,h,d),wc,0,h/2,0);
  // Foundation
  addMesh(g,B(w+0.14,0.2,d+0.14),shadeColor(wc,-0.22),0,0.1,0);
  // Eave slab
  addMesh(g,B(w+0.28,0.09,d+0.28),shadeColor(rc,0.08),0,h+0.01,0);
  // Hip roof
  const rh=h*0.38+0.18;
  const rpeak=mkMesh(C(0.04,Math.max(w,d)*0.64,rh,4),rc,0,h+rh/2-0.04,0,0,Math.PI/4,0);
  g.add(rpeak);

  // Door recess
  const dw=w*0.22,dh=h*0.52;
  addMesh(g,B(dw+0.06,dh+0.04,0.22),0x1a0a02,0,dh/2+0.02,d/2-0.05);
  // Door leaf
  addMesh(g,B(dw,dh,0.07),0x3a1a06,0,dh/2+0.02,d/2-0.04);
  // Door frame
  addMesh(g,B(dw+0.12,dh+0.12,0.06),shadeColor(wc,0.12),0,dh/2+0.02,d/2+0.01);

  // Windows
  const nw=w>2.0?2:1;
  const wxp=nw===2?[-w*0.27,w*0.27]:[w*0.26];
  wxp.forEach(function(wx){
    const wy=h*0.64,ww=w*0.15,wh2=h*0.22;
    addMesh(g,B(ww+0.06,wh2+0.04,0.16),0x1a1008,wx,wy,d/2-0.04);
    addMesh(g,B(ww,wh2,0.06),0xffe88a,wx,wy,d/2-0.01,0,0,0,{transparent:true,opacity:0.85});
    addMesh(g,B(ww+0.1,wh2+0.1,0.05),shadeColor(wc,0.12),wx,wy,d/2+0.01);
    if(o.shutter){
      addMesh(g,B(ww*0.55,wh2,0.05),0x2a5c1a,wx-ww*0.77,wy,d/2+0.01);
      addMesh(g,B(ww*0.55,wh2,0.05),0x2a5c1a,wx+ww*0.77,wy,d/2+0.01);
    }
  });

  // Chimney
  if(o.chimney){
    const cc=shadeColor(wc,-0.28);
    addMesh(g,B(0.24,h*0.6,0.24),cc,w*0.28,h+h*0.28,-d*0.18);
    addMesh(g,B(0.32,0.1,0.32),cc,w*0.28,h+h*0.6,-d*0.18);
  }

  // Porch
  if(o.porch){
    const pc=shadeColor(wc,-0.08);
    addMesh(g,B(w+0.2,0.1,0.9),pc,0,0.06,d/2+0.45);
    const np=Math.ceil(w/1.2);
    for(var i=0;i<np;i++){
      var px2=-w/2+0.2+i*(w/Math.max(np-1,1));
      if(Math.abs(px2)<=w/2+0.01) addMesh(g,C(0.055,0.065,h*0.65,6),shadeColor(wc,0.12),px2,h*0.325,d/2+0.88);
    }
    addMesh(g,B(w+0.3,0.09,0.95),shadeColor(rc,0.08),0,h*0.67,d/2+0.45);
  }

  if(o.decay) g.rotation.z=(Math.random()-0.5)*0.05;
  g.position.set(x,0,z);
  if(o.tilt) g.rotation.y=o.tilt;
  return g;
}

function makeChurch(era,cx,cz){
  const st=era.st,g=new THREE.Group();
  const wc=st==='decay'?0x8a8070:st==='rain'?0x9a9080:0xf0ece0;
  const rc=st==='decay'?0x5a4a30:0x7a4520;

  // Nave
  addMesh(g,B(3.5,4,5.5),wc,0,2,0);
  addMesh(g,B(3.8,0.1,5.8),shadeColor(rc,0.08),0,4.02,0);
  const nr=mkMesh(C(0.06,2.5,1.5,4),rc,0,4.75,0,0,Math.PI/4,0);
  g.add(nr);

  // Tower
  const tw=1.2,th=7.5;
  addMesh(g,B(tw,th,tw),wc,0,th/2,-2.9);
  addMesh(g,B(tw*1.18,th*0.2,tw*1.18),shadeColor(wc,-0.14),0,th*0.78,-2.9);
  // Belfry openings
  [-1,1].forEach(function(ax){
    addMesh(g,B(0.06,th*0.13,tw*0.6),shadeColor(wc,-0.14),ax*(tw*0.6),th*0.8,-2.9);
    addMesh(g,B(tw*0.6,th*0.13,0.06),shadeColor(wc,-0.14),0,th*0.8,-2.9+ax*(tw*0.6));
  });
  const sp=mkMesh(K(tw*0.62,th*0.36,4),rc,0,th+th*0.18,-2.9,0,Math.PI/4,0);
  g.add(sp);
  if(st!=='decay'){
    addMesh(g,B(0.07,0.55,0.07),0xc9a84c,0,th+th*0.36+0.27,-2.9);
    addMesh(g,B(0.32,0.07,0.07),0xc9a84c,0,th+th*0.36+0.38,-2.9);
  }
  // Door
  addMesh(g,B(0.88,2.2,0.2),0x120802,0,1.1,2.78);
  addMesh(g,B(0.72,2.0,0.08),0x2a1004,0,1.0,2.8);
  // Rose window
  const rose=mkMesh(C(0.42,0.42,0.07,12),0xffd070,0,3.2,2.82,Math.PI/2,0,0,{transparent:true,opacity:0.65});
  g.add(rose);

  g.position.set(cx,0,cz);
  return g;
}

function makeBuendiaHouse(era){
  const st=era.st,g=new THREE.Group();
  const wc=st==='decay'?0x7a5c3a:st==='rain'?0x8a7450:st==='war'?0xc8b898:0xede0b0;
  const rc=st==='decay'?0x4a2808:st==='rain'?0x5a3818:st==='war'?0x7a2a0a:0x9a3010;
  const ac=shadeColor(wc,0.14);

  // Main wing
  addMesh(g,B(5.8,3.5,4.2),wc,0,1.75,0);
  // Workshop wing
  addMesh(g,B(2.6,2.8,3.2),wc,4.0,1.4,-1.0);
  // Foundations
  addMesh(g,B(6.2,0.22,4.5),shadeColor(wc,-0.2),0,0.11,0);
  addMesh(g,B(2.8,0.22,3.4),shadeColor(wc,-0.2),4.0,0.11,-1.0);
  // Roofs
  var mr=mkMesh(C(0.06,4.0,1.6,4),rc,0,3.5+0.8,0,0,Math.PI/4,0); g.add(mr);
  addMesh(g,B(6.2,0.1,4.5),shadeColor(rc,0.08),0,3.52,0);
  var wr=mkMesh(C(0.05,2.0,1.1,4),rc,4.0,2.8+0.55,-1.0,0,Math.PI/4,0); g.add(wr);

  // Verandah
  addMesh(g,B(6.0,0.12,1.3),shadeColor(wc,-0.07),0,0.06,2.75);
  [-2.0,-0.7,0.7,2.0].forEach(function(px){
    addMesh(g,C(0.11,0.13,2.9,8),ac,px,1.45,3.3);
    addMesh(g,B(0.3,0.16,0.3),shadeColor(wc,-0.18),px,0.08,3.3);
    addMesh(g,B(0.26,0.13,0.26),ac,px,2.97,3.3);
  });
  addMesh(g,B(6.1,0.13,1.38),rc,0,2.98,2.78);

  // Grand door
  addMesh(g,B(1.15,2.8,0.3),0x100802,0,1.4,2.22);
  addMesh(g,B(0.92,2.6,0.1),0x5a3010,0,1.3,2.26);
  [[-0.24,0.55],[0.24,0.55],[-0.24,1.6],[0.24,1.6]].forEach(function(p){
    addMesh(g,B(0.3,0.62,0.06),shadeColor(0x5a3010,-0.1),p[0],p[1],2.3);
  });
  addMesh(g,B(1.06,2.7,0.08),ac,0,1.4,2.3);

  // Front windows
  [-1.7,-0.5,0.5,1.7].forEach(function(wx){
    addMesh(g,B(0.52,0.72,0.18),0x0c0806,wx,2.65,2.24);
    addMesh(g,B(0.44,0.64,0.07),0xffd060,wx,2.65,2.28,0,0,0,{transparent:true,opacity:0.82});
    addMesh(g,B(0.58,0.78,0.06),ac,wx,2.65,2.3);
    addMesh(g,B(0.24,0.62,0.05),0x5a3010,wx-0.4,2.65,2.31);
    addMesh(g,B(0.24,0.62,0.05),0x5a3010,wx+0.4,2.65,2.31);
  });
  // Side windows
  [-1.1,1.1].forEach(function(wz){
    addMesh(g,B(0.08,0.64,0.5),0x0c0806,-2.92,2.2,wz);
    addMesh(g,B(0.07,0.56,0.44),0xffd060,-2.9,2.2,wz,0,0,0,{transparent:true,opacity:0.82});
  });

  // Alchemist chimney
  addMesh(g,B(0.42,1.9,0.42),shadeColor(wc,-0.3),1.8,3.5+0.95,-1.2);
  addMesh(g,B(0.58,0.12,0.58),shadeColor(wc,-0.3),1.8,3.5+1.95,-1.2);

  // Courtyard
  if(st!=='decay'){
    addMesh(g,B(0.2,1.3,1.6),shadeColor(wc,-0.04),-2.6,0.65,4.0);
    addMesh(g,B(0.2,1.3,1.6),shadeColor(wc,-0.04),2.6,0.65,4.0);
    addMesh(g,B(4.0,0.14,0.18),shadeColor(wc,-0.04),0,1.28,4.0);
  }
  if(st==='decay'){
    [[-1.4,2.7,2.27],[0.9,1.4,2.27],[-0.2,3.0,2.27]].forEach(function(p){
      addMesh(g,B(0.04,0.4+Math.random()*0.4,0.03),shadeColor(wc,-0.45),p[0],p[1],p[2],0,0,(Math.random()-0.5)*0.5);
    });
  }
  g.position.set(5,0,-1.5);
  return g;
}

function makeGarrison(cx,cz,era){
  const st=era.st,g=new THREE.Group();
  const wc=st==='decay'?0x6a6458:0x8a8070;
  const rc=st==='decay'?0x4a3a28:0x5a4a30;

  addMesh(g,B(5.5,3.2,5),wc,0,1.6,0);
  addMesh(g,B(5.8,0.28,5.3),rc,0,3.26,0);
  addMesh(g,B(5.8,0.65,5.3),shadeColor(wc,-0.08),0,3.65,0);
  for(var i=-2;i<=2;i++){
    addMesh(g,B(0.38,0.42,0.22),wc,i*1.15,4.06,2.56);
    addMesh(g,B(0.38,0.42,0.22),wc,i*1.15,4.06,-2.56);
  }
  addMesh(g,B(1.3,2.7,0.24),0x0c0804,0,1.35,2.54);
  addMesh(g,B(1.06,2.5,0.1),0x1a1004,0,1.25,2.58);
  addMesh(g,B(1.44,2.84,0.08),shadeColor(wc,0.1),0,1.35,2.6);
  addMesh(g,B(0.22,0.58,0.12),0x060400,-1.9,2.2,2.52);
  addMesh(g,B(0.22,0.58,0.12),0x060400,1.9,2.2,2.52);
  addMesh(g,C(0.55,0.62,4.4,8),wc,-2.7,2.2,-2.4);
  addMesh(g,K(0.7,1.1,8),rc,-2.7,4.65,-2.4);

  g.position.set(cx,0,cz);
  return g;
}

function makeBananaFactory(cx,cz){
  const g=new THREE.Group();
  const wc=0xd4c060,rc=0x4a3010,sc=0x7a7058;

  // Main building
  addMesh(g,B(12,5,8),wc,0,2.5,0);
  addMesh(g,B(12.4,0.28,8.4),rc,0,5.14,0);
  addMesh(g,B(12.4,0.5,8.4),shadeColor(wc,-0.1),0,5.5,0);
  for(var i=-5;i<=5;i++) addMesh(g,B(0.5,0.5,0.22),wc,i*1.1,5.88,4.28);

  // Doors
  addMesh(g,B(3.0,3.5,0.3),0x3a2808,-2.5,1.75,4.18);
  addMesh(g,B(2.8,3.3,0.14),0x2a1c04,-2.5,1.65,4.22);
  addMesh(g,B(0.9,2.3,0.2),0x3a2808,2.5,1.15,4.18);
  addMesh(g,B(0.74,2.1,0.1),0x3a2408,2.5,1.05,4.22);

  // Windows
  [-4.5,4.5].forEach(function(wx){
    for(var wy=1.2;wy<5;wy+=1.4){
      addMesh(g,B(1.8,1.0,0.16),0x3a2808,wx,wy,4.16);
      addMesh(g,B(1.6,0.88,0.08),0xb8e0e0,wx,wy,4.2,0,0,0,{transparent:true,opacity:0.6});
    }
  });

  // Three chimneys
  [[-4,5.2],[-1,5.2],[2,5.2]].forEach(function(p){
    var ch=4.5;
    var chim=mkMesh(C(0.32,0.42,ch,8),sc,p[0],p[1]+ch/2,-1); chim.userData={smoke:true,baseY:p[1]+ch+0.5}; g.add(chim);
    addMesh(g,C(0.5,0.5,0.18,8),0x3a2808,p[0],p[1]+ch-0.06,-1);
    var smoke=mkMesh(S(0.7,6,4),0x202018,p[0],p[1]+ch+0.5,-1,0,0,0,{transparent:true,opacity:0.45});
    smoke.userData={smoke:true,baseY:p[1]+ch+0.5}; g.add(smoke);
  });

  // Crates
  for(var ci=0;ci<3;ci++){
    for(var cj=0;cj<2;cj++){
      addMesh(g,B(1.1,0.7,0.8),0x8a6020,-1.2+ci*1.3,0.35+cj*0.75,5.2);
      if(cj===1){
        for(var bk=0;bk<3;bk++){
          var bunch=mkMesh(C(0.18,0.12,0.55,4),0xe8c020,-1.2+ci*1.3+bk*0.18-0.18,1.15+cj*0.75,5.2,0,0,Math.PI/4*(bk-1));
          g.add(bunch);
        }
      }
    }
  }

  // Banana plants
  for(var bi=0;bi<6;bi++){
    var bx=-5+bi*2,bz=-5-bi*0.6;
    addMesh(g,C(0.18,0.22,3.5,6),0x4a6020,bx,1.75,bz);
    for(var lf=0;lf<5;lf++){
      var la=lf*(Math.PI*2/5);
      var leaf=mkMesh(B(2.2,0.06,0.55),0x4a7a18,bx+Math.cos(la)*1.1,3.6,bz+Math.sin(la)*0.8,0.3,la,0);
      g.add(leaf);
    }
    addMesh(g,C(0.22,0.14,0.7,5),0xe8c020,bx-0.3,2.8,bz,0,0,0.6);
  }

  // Sign board
  addMesh(g,B(6,0.8,0.12),0xfff8d0,0,6.0,4.3);
  for(var li=0;li<8;li++) addMesh(g,B(0.35,0.35,0.08),0x1a1a08,-2.6+li*0.7,6.0,4.38);
  addMesh(g,B(4,0.4,0.1),0xffe060,0,5.38,4.32);

  // Fence
  var fm2=0x7a7860;
  for(var fz=-6;fz<=8;fz+=1.8){
    addMesh(g,C(0.06,0.07,2.2,4),fm2,9.5,1.1,fz);
    if(fz<8){
      addMesh(g,B(0.03,0.03,1.8),fm2,9.5,1.7,fz+0.9);
      addMesh(g,B(0.03,0.03,1.8),fm2,9.5,0.8,fz+0.9);
    }
  }

  g.position.set(cx,0,cz);
  return g;
}

function makeLocomotive(cx,cz){
  const g=new THREE.Group();
  const yc=0xe8c020,dk=0x2a1a04,mt=0x808070,ck=0x303028,wc2=0xb0d8e0;

  // Track
  [-0.5,0.5].forEach(function(rx){ addMesh(g,B(0.12,0.1,60),mt,rx,0.05,0); });
  for(var i=-25;i<25;i+=1.5) addMesh(g,B(1.4,0.08,0.28),0x4a2e10,0,0.0,i);

  // Loco group (moves along Z)
  var loco=new THREE.Group();

  // Cab
  addMesh(loco,B(3.2,2.2,2.0),yc,0,1.5,0);
  addMesh(loco,B(3.4,0.22,2.2),shadeColor(yc,-0.2),0,2.72,0);
  // Boiler
  var boiler=mkMesh(C(0.88,0.92,4.8,12),yc,-3.6,1.35,0,0,0,Math.PI/2); g.add(boiler); loco.add(boiler);
  addMesh(loco,C(0.92,0.92,0.22,12),dk,-6.1,1.35,0,Math.PI/2,0,0);
  // Chimney stack
  addMesh(loco,C(0.28,0.22,1.2,8),ck,-5.0,2.4,0);
  addMesh(loco,C(0.42,0.42,0.18,8),ck,-5.0,3.08,0);
  // Dome
  addMesh(loco,C(0.35,0.28,0.55,8),yc,-3.0,2.28,0);
  // Headlamp
  addMesh(loco,S(0.22,8,6),0xffe880,-6.18,1.8,0);
  // Cowcatcher
  addMesh(loco,B(0.6,0.7,2.2),dk,-6.5,0.5,0);
  // Cab windows
  [[1.55,2.0,0.95],[1.55,2.0,-0.95],[-0.8+1.55,2.0,1.02],[-0.8+1.55,2.0,-1.02]].forEach(function(p){
    addMesh(loco,B(0.08,0.65,0.5),wc2,p[0],p[1],p[2],0,0,0,{transparent:true,opacity:0.75});
  });
  // Wheels
  [-5.8,-3.8,-2.2,-1.0,0.2,1.4].forEach(function(wz){
    [-0.92,0.92].forEach(function(side){
      addMesh(loco,C(0.55,0.55,0.22,14),dk,wz,0.58,side,Math.PI/2,0,0);
      addMesh(loco,C(0.58,0.58,0.1,14),mt,wz,0.58,side,Math.PI/2,0,0);
    });
  });
  addMesh(loco,B(2.8,0.14,0.1),mt,-0.3,0.9,0.93);

  // Tender
  var tender=new THREE.Group();
  addMesh(tender,B(2.5,1.5,2.0),dk,0,1.05,0);
  addMesh(tender,B(2.5,0.3,2.0),0x1a1210,0,1.95,0);
  [-0.8,0.8].forEach(function(tz){
    [-0.92,0.92].forEach(function(side){
      addMesh(tender,C(0.5,0.5,0.18,12),dk,0,0.52,side,Math.PI/2,0,0);
    });
  });
  tender.position.set(3.2,0,0);
  loco.add(tender);

  loco.position.set(-4,0,0);
  loco.rotation.y=Math.PI/2;
  g.add(loco);
  g.userData={locoGroup:loco};
  g.position.set(cx,0,cz);
  g.rotation.y=-Math.PI/2;
  return g;
}

function makeHotAirBalloon(cx,cy,cz){
  const g=new THREE.Group();

  // Main envelope
  addMesh(g,S(2.4,14,10),0xe8b820,0,0,0,0,0,0,{transparent:true,opacity:0.88});
  // Stripe segments
  for(var i=0;i<12;i++){
    var sc2=i%2===0?0xe8c020:0xc83020;
    var la=i*(Math.PI*2/12);
    addMesh(g,S(2.42,2,8),sc2,Math.cos(la)*0.2,0,Math.sin(la)*0.2,0,0,0,{transparent:true,opacity:0.5});
  }
  // Crown
  addMesh(g,S(0.5,8,6),0xd84020,0,2.42,0);
  // Ropes
  for(var ri=0;ri<8;ri++){
    var ra=ri*Math.PI/4;
    var rope=mkMesh(C(0.03,0.03,2.8,4),0x8a6030,Math.cos(ra)*1.2,-1.0,Math.sin(ra)*1.2,Math.sin(ra)*0.6,0,Math.cos(ra)*0.6);
    g.add(rope);
  }
  // Basket
  addMesh(g,B(1.1,0.8,1.1),0x8a5a18,0,-3.4,0);
  for(var bi2=0;bi2<3;bi2++){
    addMesh(g,B(1.15,0.05,0.05),0x6a3a08,0,-3.1+bi2*0.28,0.56);
    addMesh(g,B(0.05,0.05,1.15),0x6a3a08,0.56,-3.1+bi2*0.28,0);
  }
  // Burner
  addMesh(g,K(0.18,0.5,6),0xff8020,0,-2.56,0,0,0,0,{transparent:true,opacity:0.85});
  // Basket ropes
  for(var ri2=0;ri2<4;ri2++){
    var ra2=ri2*Math.PI/2;
    var r2=mkMesh(C(0.025,0.025,1.3,4),0x8a6030,Math.cos(ra2)*0.5,-2.9,Math.sin(ra2)*0.5,Math.sin(ra2)*0.4,0,Math.cos(ra2)*0.4);
    g.add(r2);
  }

  g.position.set(cx,cy,cz);
  g.userData={balloon:true,baseY:cy};
  return g;
}

function makePerson(type,px,pz,fa){
  const g=new THREE.Group();
  var skin=0xd4956a,shirtC=0xe8dcc0,pantsC=0x4a3828,hatC=0,capeC=0,h=1.65;
  if(type==='villager'){skin=0xc88050;shirtC=0xf0e8d0;pantsC=0x4a3020;}
  if(type==='gypsy'){skin=0xb07040;shirtC=0xd44020;capeC=0x8a1a70;pantsC=0x2a1840;hatC=0x2a1840;}
  if(type==='soldier'){skin=0xd09060;shirtC=0x4a5a2a;pantsC=0x3a4a1a;hatC=0x3a4a18;}
  if(type==='worker'){skin=0xc07840;shirtC=0xd0c090;pantsC=0x483820;hatC=0x5a4020;}
  if(type==='gringo'){skin=0xe0c0a0;shirtC=0xf0f0e8;pantsC=0x304858;hatC=0xf0ece0;}

  // Legs
  addMesh(g,C(0.09,0.1,h*0.38,5),pantsC,-0.12,h*0.2,0);
  addMesh(g,C(0.09,0.1,h*0.38,5),pantsC,0.12,h*0.2,0);
  addMesh(g,B(0.14,0.1,0.22),0x1a0e04,-0.12,0.04,0.06);
  addMesh(g,B(0.14,0.1,0.22),0x1a0e04,0.12,0.04,0.06);
  // Torso
  addMesh(g,B(0.34,h*0.34,0.26),shirtC,0,h*0.52,0);
  if(capeC) addMesh(g,K(0.3,h*0.38,6),capeC,0,h*0.46,0,0,0,0,{transparent:false});
  // Head
  addMesh(g,S(0.13,7,6),skin,0,h*0.88,0);
  addMesh(g,S(0.135,6,4),0x1a0a04,0,h*0.92,0);
  // Arms
  addMesh(g,C(0.065,0.075,h*0.26,5),shirtC,-0.24,h*0.61,0,0,0,-0.25);
  addMesh(g,C(0.065,0.075,h*0.26,5),shirtC,0.24,h*0.61,0,0,0,0.25);
  addMesh(g,S(0.072,5,4),skin,-0.24*1.2,h*0.5,0);
  addMesh(g,S(0.072,5,4),skin,0.24*1.2,h*0.5,0);
  // Hat
  if(hatC){
    addMesh(g,C(0.14,0.14,0.22,8),hatC,0,h*0.97,0);
    addMesh(g,C(0.22,0.22,0.04,8),hatC,0,h*0.955,0);
  }
  if(type==='gypsy') addMesh(g,C(0.025,0.025,0.1,6),0xc9a84c,0.15,h*0.84,0.1);

  g.position.set(px,0,pz);
  g.rotation.y=fa||0;
  g.userData={walker:true,walkDir:fa||0,walkSpeed:0.6+Math.random()*0.4,walkPhase:Math.random()*Math.PI*2,type:type};
  return g;
}

// ========== SCENE ==========
function initThree(){
  var canvas=document.getElementById('three-canvas');
  renderer=new THREE.WebGLRenderer({canvas:canvas,antialias:true});
  renderer.setSize(canvas.clientWidth,canvas.clientHeight);
  renderer.setPixelRatio(Math.min(window.devicePixelRatio,2));
  renderer.shadowMap.enabled=true;
  renderer.shadowMap.type=THREE.PCFSoftShadowMap;
  renderer.toneMapping=THREE.ACESFilmicToneMapping;
  renderer.toneMappingExposure=1.1;
  scene3=new THREE.Scene();
  cam3=new THREE.PerspectiveCamera(52,canvas.clientWidth/canvas.clientHeight,0.1,300);
  clk3=new THREE.Clock();

  // Mouse/touch drag orbit
  canvas.addEventListener('mousedown',function(e){isDragging=true;lastMX=e.clientX;lastMY=e.clientY;autoOrbit=false;canvas.style.cursor='grabbing';});
  canvas.addEventListener('touchstart',function(e){isDragging=true;lastMX=e.touches[0].clientX;lastMY=e.touches[0].clientY;autoOrbit=false;},{passive:true});
  window.addEventListener('mouseup',function(){isDragging=false;canvas.style.cursor='grab';});
  window.addEventListener('touchend',function(){isDragging=false;});
  canvas.addEventListener('mousemove',function(e){
    if(!isDragging)return;
    camTheta-=(e.clientX-lastMX)*0.005;
    camPhi=Math.max(0.12,Math.min(1.4,camPhi+(e.clientY-lastMY)*0.005));
    lastMX=e.clientX; lastMY=e.clientY;
  });
  canvas.addEventListener('touchmove',function(e){
    if(!isDragging)return;
    camTheta-=(e.touches[0].clientX-lastMX)*0.005;
    camPhi=Math.max(0.12,Math.min(1.4,camPhi+(e.touches[0].clientY-lastMY)*0.005));
    lastMX=e.touches[0].clientX; lastMY=e.touches[0].clientY;
  },{passive:true});
  canvas.addEventListener('wheel',function(e){camR=Math.max(10,Math.min(60,camR+e.deltaY*0.04));},{passive:true});
  canvas.style.cursor='grab';

  buildScene(ERAS[0]);
  buildDots();
  loop3();

  window.addEventListener('resize',function(){
    if(!renderer)return;
    renderer.setSize(canvas.clientWidth,canvas.clientHeight);
    cam3.aspect=canvas.clientWidth/canvas.clientHeight;
    cam3.updateProjectionMatrix();
  });
  document.getElementById('prev-era').addEventListener('click',function(){switchEra((eraIdx-1+ERAS.length)%ERAS.length);});
  document.getElementById('next-era').addEventListener('click',function(){switchEra((eraIdx+1)%ERAS.length);});
}

function add3(o){scene3.add(o);sceneObjs.push(o);return o;}
function addGroup(grp){scene3.add(grp);sceneObjs.push(grp);return grp;}

function clearScene(){
  sceneObjs.forEach(function(o){
    scene3.remove(o);
    o.traverse(function(child){
      if(child.geometry)child.geometry.dispose();
      if(child.material){
        if(Array.isArray(child.material))child.material.forEach(function(m){m.dispose();});
        else child.material.dispose();
      }
    });
  });
  sceneObjs=[];
  scene3.children.filter(function(c){return c.isLight;}).forEach(function(l){scene3.remove(l);});
}

var HOUSE_SLOTS=[
  {x:-14,z:-18},{x:-9,z:-18},{x:-4.5,z:-18},{x:10,z:-18},{x:15,z:-18},{x:20,z:-18},
  {x:-14,z:-12},{x:-9,z:-12},{x:-4.5,z:-12},{x:10,z:-12},{x:15,z:-12},{x:20,z:-12},
  {x:-14,z:-6},{x:-9,z:-6},{x:10,z:-6},{x:15,z:-6},{x:20,z:-6},
  {x:-4.5,z:0},{x:10,z:0},{x:15,z:0},{x:20,z:0},
  {x:-4.5,z:6},{x:10,z:6},{x:15,z:6},{x:20,z:6},
  {x:-14,z:12},{x:-9,z:12},{x:-4.5,z:12},{x:10,z:12},{x:15,z:12},{x:20,z:12},
  {x:-14,z:18},{x:-9,z:18},{x:-4.5,z:18},{x:10,z:18},{x:15,z:18},{x:20,z:18},
  {x:-19,z:-18},{x:25,z:-6},{x:25,z:6},{x:25,z:18},{x:-19,z:12}
];

var HOUSE_CFGS={
  paradise:{walls:[0xf0e8d0,0xe8ddc0,0xf4edd8,0xece0c4,0xf8f0e0],roofs:[0xb03c18,0xa03010,0xc04820,0x953010,0xb84018]},
  wonder:  {walls:[0xe8dcc4,0xddd0b0,0xf0e4cc,0xe4d8b8,0xece2c8],roofs:[0xa03518,0x8a2a10,0xb04020,0x982e12,0xac3a18]},
  war:     {walls:[0xc8b898,0xb8a880,0xd0bc98,0xb0a078,0xc0aa88],roofs:[0x7a2808,0x682008,0x8a3010,0x702208,0x7e2a08]},
  boom:    {walls:[0xe0c870,0xd8be58,0xe8d080,0xd0b848,0xdcc060],roofs:[0x703818,0x5a2a10,0x7a4020,0x623010,0x6e3818]},
  rain:    {walls:[0x9a9080,0x888070,0xa09888,0x908578,0x9a8c7a],roofs:[0x4a3820,0x3c2c18,0x523e28,0x443218,0x4c3a20]},
  decay:   {walls:[0x7a6848,0x6a5838,0x826e50,0x6e6040,0x786650],roofs:[0x3a2810,0x2e2008,0x422e14,0x362210,0x3c2a10]}
};

function buildScene(era){
  clearScene();
  scene3.background=new THREE.Color(era.sky);
  scene3.fog=new THREE.FogExp2(era.fog,era.fd);

  scene3.add(new THREE.AmbientLight(0xfff8e8,era.amb));
  var dl=new THREE.DirectionalLight(era.dirC,era.dirI);
  dl.position.set(-8,18,12); dl.castShadow=true;
  dl.shadow.mapSize.set(2048,2048);
  dl.shadow.camera.left=-40; dl.shadow.camera.right=40; dl.shadow.camera.top=40; dl.shadow.camera.bottom=-40;
  scene3.add(dl);
  var fl=new THREE.DirectionalLight(era.st==='war'?0xff4010:era.st==='rain'?0x4060c0:0xffe8b0,era.dirI*0.28);
  fl.position.set(12,8,-10); scene3.add(fl);

  // Ground plane (gently undulating via segment heights)
  var tgeo=new THREE.PlaneGeometry(120,120,18,18);
  var tpos=tgeo.attributes.position;
  for(var vi=0;vi<tpos.count;vi++){
    var vx=tpos.getX(vi),vz=tpos.getZ(vi);
    var roadMask=Math.max(0,1-Math.abs(vx)/4);
    var hv=(Math.sin(vx*0.18)*0.4+Math.cos(vz*0.22)*0.3+Math.sin((vx+vz)*0.09)*0.5)*(1-roadMask*0.9);
    tpos.setZ(vi,hv);
  }
  tgeo.computeVertexNormals();
  var terrain=new THREE.Mesh(tgeo,mkMat(era.gc));
  terrain.rotation.x=-Math.PI/2; terrain.receiveShadow=true; terrain.position.y=-0.05;
  add3(terrain);

  // Roads
  var roadC=era.st==='boom'?0x706050:era.st==='decay'||era.st==='rain'?0x282015:0x5c3e22;
  var rd=new THREE.Mesh(new THREE.PlaneGeometry(4,90),mkMat(roadC));
  rd.rotation.x=-Math.PI/2; rd.position.set(0,0.02,0); add3(rd);
  [-2.2,2.2].forEach(function(ex){
    var e=new THREE.Mesh(new THREE.PlaneGeometry(0.25,90),mkMat(shadeColor(roadC,-0.15)));
    e.rotation.x=-Math.PI/2; e.position.set(ex,0.022,0); add3(e);
  });
  if(era.id>=3){
    [5,-9,-20].forEach(function(cz2){
      var cr=new THREE.Mesh(new THREE.PlaneGeometry(80,3.5),mkMat(roadC));
      cr.rotation.x=-Math.PI/2; cr.position.set(0,0.022,cz2); add3(cr);
    });
  }

  // River
  var rvc=era.st==='decay'?0x0d1a28:era.st==='rain'?0x0a1220:0x1a4890;
  var rv=new THREE.Mesh(new THREE.PlaneGeometry(5,90),mkMat(rvc,{transparent:true,opacity:0.85}));
  rv.rotation.x=-Math.PI/2; rv.position.set(-20,0.025,0); add3(rv);
  var bank=new THREE.Mesh(new THREE.BoxGeometry(1.4,0.15,90),mkMat(shadeColor(era.gc,-0.12)));
  bank.position.set(-17.4,0.08,0); add3(bank);
  // River stones
  for(var si=0;si<25;si++){
    var ssz=0.18+Math.random()*0.35;
    var stone=mkMesh(S(ssz,5,4),0xd0c8b0,-20+(-2.8+Math.random()*5.6),ssz*0.2,(Math.random()-0.5)*60);
    stone.scale.y=0.4+Math.random()*0.35; add3(stone);
  }

  // Core buildings
  addGroup(makeBuendiaHouse(era));
  var bg=new THREE.PointLight(0xff9020,era.st==='decay'?0.5:1.3,14);
  bg.position.set(5,3,-1.5); scene3.add(bg);
  if(era.id>=1) addGroup(makeChurch(era,-8,-10));
  if(era.id>=2) addGroup(makeGarrison(-12,5,era));
  if(era.id===3){
    addGroup(makeBananaFactory(-14,12));
    addGroup(makeHotAirBalloon(8,18,8));
  }
  if(era.id>=3 && era.id<=4) addGroup(makeLocomotive(-20,-14));
  if(era.id>=4){
    addMesh(new THREE.Group(),B(6,3,5),0x5a5038,-13,1.5,12); // ruin remnant
  }

  // Houses
  var hc=HOUSE_CFGS[era.st]||HOUSE_CFGS.paradise;
  var count=Math.min(era.bc,HOUSE_SLOTS.length);
  for(var hi=0;hi<count;hi++){
    var slot=HOUSE_SLOTS[hi];
    addGroup(makeHouse({
      x:slot.x, z:slot.z,
      w:2.0+(hi%4)*0.28, d:1.7+(hi%3)*0.22, h:2.0+(hi%3)*0.42,
      wc:hc.walls[hi%hc.walls.length], rc:hc.roofs[hi%hc.roofs.length],
      porch:(era.st==='paradise'||era.st==='wonder')&&hi%3===0,
      shutter:era.st!=='decay'&&era.st!=='rain',
      chimney:hi%5===0&&era.st!=='decay',
      decay:era.st==='decay'
    }));
  }

  // Boom extra buildings
  if(era.id===3){
    // Hotel
    var hg=new THREE.Group();
    addMesh(hg,B(6,5,5),0xd0b850,0,2.5,0);
    addMesh(hg,B(6.3,0.25,5.3),0x5a2808,0,5.12,0);
    addMesh(hg,B(6.3,0.55,5.3),0xc0a040,0,5.5,0);
    for(var r=0;r<3;r++) for(var c=0;c<4;c++) addMesh(hg,B(0.75,0.85,0.12),0xb8d8d8,-2.2+c*1.4,1.2+r*1.4,2.58,0,0,0,{transparent:true,opacity:0.7});
    hg.position.set(18,0,-10); addGroup(hg);
    // Town hall
    var tg=new THREE.Group();
    addMesh(tg,B(7,4.5,5),0x8a8068,0,2.25,0);
    addMesh(tg,B(7.3,0.25,5.3),0x4a3a28,0,4.62,0);
    addMesh(tg,B(7.3,0.5,5.3),0x7a7058,0,4.98,0);
    [-2.5,0,2.5].forEach(function(px2){ addMesh(tg,C(0.12,0.14,4.0,8),0x9a9078,px2,2.0,2.6); });
    tg.position.set(-18,0,-10); addGroup(tg);
    // Banana plantation rows near factory
    for(var br=0;br<4;br++){
      for(var bc2=0;bc2<5;bc2++){
        var bx2=-6-bc2*2.8,bz2=5+br*3.5;
        add3(mkMesh(C(0.2,0.24,3.5,6),0x4a6020,bx2,1.75,bz2));
        for(var lf2=0;lf2<5;lf2++){
          var la2=lf2*(Math.PI*2/5);
          add3(mkMesh(B(2.4,0.06,0.5),0x4a7a18,bx2+Math.cos(la2)*1.0,3.6,bz2+Math.sin(la2)*0.7,0.28,la2,0));
        }
        add3(mkMesh(C(0.2,0.12,0.7,5),0xe8c020,bx2-0.3,2.8,bz2,0,0,0.6));
      }
    }
    // Streetlamps
    [-6,-2,2,6,10].forEach(function(pz2){
      add3(mkMesh(C(0.07,0.09,5,6),0x706858,2.6,2.5,pz2));
      var pl=new THREE.PointLight(0xfff0a0,1.5,9); pl.position.set(2.6,5.1,pz2); scene3.add(pl);
      add3(mkMesh(S(0.22,8,6),0xfff0b0,2.6,5.05,pz2));
    });
  }

  // People
  var PEOPLE={
    paradise:[{t:'villager',x:-3,z:2},{t:'villager',x:3,z:4},{t:'villager',x:-5,z:-3},{t:'villager',x:12,z:-5},{t:'villager',x:-12,z:-8}],
    wonder:  [{t:'gypsy',x:-5,z:3,a:0.8},{t:'gypsy',x:-3,z:-1,a:-0.5},{t:'gypsy',x:-7,z:-5,a:1.2},{t:'villager',x:12,z:0},{t:'villager',x:3,z:-8}],
    war:     [{t:'soldier',x:-14,z:4,a:0},{t:'soldier',x:-12,z:7,a:Math.PI},{t:'soldier',x:-10,z:5,a:Math.PI/2},{t:'villager',x:12,z:-5},{t:'villager',x:-3,z:-10}],
    boom:    [{t:'worker',x:-8,z:14,a:0.3},{t:'worker',x:-10,z:16,a:-0.2},{t:'worker',x:-6,z:11,a:1.0},{t:'worker',x:-12,z:13,a:2.0},{t:'gringo',x:16,z:-8,a:-0.5},{t:'gringo',x:14,z:-5,a:0.8},{t:'villager',x:3,z:3}],
    rain:    [{t:'worker',x:-5,z:4},{t:'worker',x:3,z:-6},{t:'villager',x:10,z:0}],
    decay:   [{t:'villager',x:3,z:-8},{t:'villager',x:-8,z:-5}]
  };
  (PEOPLE[era.st]||[]).forEach(function(p){ addGroup(makePerson(p.t,p.x,p.z,p.a||0)); });

  // Trees (seeded RNG)
  var tcolors={paradise:0x2a7a18,wonder:0x206018,war:0x1a4812,boom:0x185010,rain:0x0e2a0a,decay:0x152208};
  var tc=tcolors[era.st]||0x2a7a18;
  var seed=era.id*997+1;
  function rnd(){seed=(seed*1664525+1013904223)&0xffffffff;return(seed>>>0)/0xffffffff;}
  for(var ti=0;ti<era.tc;ti++){
    var ang=rnd()*Math.PI*2,dist=20+rnd()*28;
    var tx=Math.cos(ang)*dist,tz=Math.sin(ang)*dist;
    if(Math.abs(tx)<4.5)continue;
    if(era.id===3&&tx<-6&&tx>-22&&tz>6&&tz<18)continue;
    var th=3.5+rnd()*4.5;
    add3(mkMesh(C(0.16,0.24,th,7),0x4a2e10,tx,th/2,tz));
    var csz=1.3+rnd()*1.2;
    add3(mkMesh(S(csz,7,5),tc,tx,th+csz*0.28,tz));
    if(csz>1.6) add3(mkMesh(S(csz*0.65,5,4),shadeColor(tc,0.1),tx+csz*0.3,th+csz*0.7,tz+csz*0.18));
    if((era.st==='paradise'||era.st==='wonder')&&ti%3===0){
      for(var fi=0;fi<5;fi++){
        var fa2=fi*(Math.PI*2/5)+rnd()*0.4;
        add3(mkMesh(C(0.05,0.05,2.0,4),shadeColor(tc,0.18),tx+Math.cos(fa2)*1.0,th+0.5,tz+Math.sin(fa2)*1.0,Math.sin(fa2)*0.75,0,Math.cos(fa2)*0.75));
      }
    }
  }

  // Fireflies
  if(era.st==='paradise'||era.st==='wonder'){
    for(var ffi=0;ffi<55;ffi++){
      var fly=mkMesh(S(0.055,4,4),0xffffa0,(rnd()-.5)*32,0.5+rnd()*6,(rnd()-.5)*32,0,0,0,{transparent:true,opacity:0.9});
      fly.userData={off:rnd()*Math.PI*2,sp:0.4+rnd()*0.8};
      add3(fly);
    }
  }
  // Rain drops
  if(era.st==='rain'){
    for(var ri3=0;ri3<900;ri3++){
      var dr=mkMesh(C(0.006,0.006,0.52,3),0x5090d0,(rnd()-.5)*65,rnd()*26,(rnd()-.5)*65,0,0,0,{transparent:true,opacity:0.28});
      dr.userData={sp:5+rnd()*8}; add3(dr);
    }
    document.getElementById('rain-wrap').classList.add('on');
  } else {
    document.getElementById('rain-wrap').classList.remove('on');
  }
  // Stars
  if(era.st==='war'||era.st==='wonder'||era.st==='paradise'){
    for(var sti=0;sti<260;sti++){
      var th2=rnd()*Math.PI*2,ph=rnd()*Math.PI*0.5;
      var star=mkMesh(S(0.04,3,3),0xffffff,Math.cos(th2)*Math.sin(ph)*95,Math.cos(ph)*95+10,Math.sin(th2)*Math.sin(ph)*95,0,0,0,{transparent:true,opacity:0.3+rnd()*0.6});
      add3(star);
    }
  }
}

function loop3(){
  requestAnimationFrame(loop3);
  var t=clk3.getElapsedTime();
  var era=ERAS[eraIdx];

  if(autoOrbit) camTheta+=0.00022;
  var cy=camR*Math.cos(camPhi),cr=camR*Math.sin(camPhi);
  cam3.position.set(Math.sin(camTheta)*cr,cy+1,Math.cos(camTheta)*cr);
  cam3.lookAt(0,2.5,0);

  sceneObjs.forEach(function(obj){
    if(!obj.userData)return;
    // Rain
    if(era.st==='rain'&&obj.userData.sp&&!obj.userData.walker){
      obj.position.y-=obj.userData.sp*0.016;
      if(obj.position.y<-2)obj.position.y=26;
    }
    // Fireflies
    if((era.st==='paradise'||era.st==='wonder')&&obj.userData.off!==undefined&&!obj.userData.walker){
      obj.position.x+=Math.sin(t*obj.userData.sp+obj.userData.off)*0.028;
      obj.position.z+=Math.cos(t*obj.userData.sp*0.7+obj.userData.off)*0.028;
      obj.position.y+=Math.sin(t*obj.userData.sp*1.3+obj.userData.off)*0.014;
      if(obj.material)obj.material.opacity=0.15+Math.abs(Math.sin(t*2+obj.userData.off))*0.85;
    }
    // People walking
    if(obj.userData.walker){
      var spd=obj.userData.walkSpeed;
      var dir=obj.userData.walkDir+Math.sin(t*0.3+obj.userData.walkPhase)*0.3;
      obj.position.x+=Math.sin(dir)*spd*0.008;
      obj.position.z+=Math.cos(dir)*spd*0.008;
      obj.rotation.y=dir;
      obj.position.y=Math.abs(Math.sin(t*spd*3+obj.userData.walkPhase))*0.06;
      if(obj.position.x>24)obj.position.x=-24;
      if(obj.position.x<-24)obj.position.x=24;
      if(obj.position.z>24)obj.position.z=-24;
      if(obj.position.z<-24)obj.position.z=24;
    }
    // Balloon
    if(obj.userData.balloon){
      obj.position.y=obj.userData.baseY+Math.sin(t*0.4)*1.2;
      obj.rotation.y=t*0.08;
      obj.rotation.z=Math.sin(t*0.3)*0.04;
    }
    // Smoke
    if(obj.userData.smoke&&obj.userData.baseY!==undefined&&obj.geometry&&obj.geometry.type&&obj.geometry.type.indexOf('Sphere')>=0){
      obj.position.y=obj.userData.baseY+Math.sin(t*0.8+obj.userData.baseY)*0.6;
      if(obj.scale)obj.scale.setScalar(1+Math.sin(t*0.5)*0.2);
    }
    // Locomotive
    if(obj.userData.locoGroup){
      obj.userData.locoGroup.position.z=((t*2.5)%55)-25;
    }
  });

  // Flicker house light
  var ptls=scene3.children.filter(function(c){return c.isPointLight;});
  var wfl=ptls.find(function(l){return l.position.x>3;});
  if(wfl)wfl.intensity=(era.st==='decay'?0.4:0.9)+Math.sin(t*1.4)*0.22;

  renderer.render(scene3,cam3);
}

function buildDots(){
  var c=document.getElementById('era-dots'); c.innerHTML='';
  ERAS.forEach(function(era,i){
    var btn=document.createElement('button');
    btn.className='era-dot'+(i===0?' active':'');
    btn.innerHTML='<span class="era-dot-lbl">'+era.label+'</span>';
    btn.addEventListener('click',function(){switchEra(i);});
    c.appendChild(btn);
  });
}

function switchEra(idx){
  eraIdx=idx;
  buildScene(ERAS[idx]);
  document.querySelectorAll('.era-dot').forEach(function(b,i){b.classList.toggle('active',i===idx);});
  document.getElementById('era-name').textContent=ERAS[idx].name;
  document.getElementById('era-sub').textContent=ERAS[idx].sub;
  document.getElementById('era-nos').textContent=ERAS[idx].nos;
  document.getElementById('era-num').textContent='ERA 0'+(idx+1)+'/06';
  document.getElementById('era-top-lbl').textContent=ERAS[idx].label.toUpperCase();
}


// ===================== MAP DATA =====================
const MAP_DATA=[
  {name:'The Founding',pop:'~20 inhabitants',year:'Year 1',
   desc:'Twenty families cross the mountains, founding a village so new that many things lacked names. The town is laid out so every house has equal access to the river — an idealized commune built from memory of what community should be.',
   nos:'The very layout of the town is an idealized memory of fairness that will be destroyed the moment outsiders arrive.',
   locs:[
     {name:'Buendía House',color:'#c9a84c',note:'The ancestral home built facing the river. Site of alchemy, magic, and eventual ruin.'},
     {name:'The Clear River',color:'#4060a0',note:'Symbol of original purity. Its water grows darker as the novel progresses.'},
     {name:'Main Road',color:'#8b5a2a',note:'A single unpaved street connecting all houses — equality before commerce arrives.'},
     {name:'Jungle Edge',color:'#2a6a2a',note:'The route Melquíades will soon use to bring marvels from the outside world.'},
   ],
   buildings:[
     {x:370,y:270,w:56,h:48,color:'#c9a84c',label:'Buendía House',nos:true},
     {x:295,y:258,w:28,h:23,color:'#d8c880',label:''},
     {x:440,y:280,w:26,h:22,color:'#d8c880',label:''},
     {x:310,y:315,w:24,h:20,color:'#d8c880',label:''},
     {x:438,y:237,w:23,h:19,color:'#d8c880',label:''},
     {x:278,y:312,w:21,h:18,color:'#d8c880',label:''},
     {x:462,y:322,w:21,h:18,color:'#d8c880',label:''},
     {x:346,y:218,w:21,h:18,color:'#d8c880',label:''},
   ],
   roads:[{x1:350,y1:80,x2:350,y2:520,w:8}],
   zones:['dense']},

  {name:'The Age of Wonder',pop:'~180 inhabitants',year:'Generation 1–2',
   desc:'Gypsies arrive each spring. A school is built. The insomnia plague sweeps through, erasing memory. Melquíades closes himself in his room and writes the prophetic parchments that will not be deciphered for one hundred years.',
   nos:'Melquíades writes the parchments here — encoding a nostalgia for the future, a memory of what has not yet happened. His room is described as a pocket of the past.',
   locs:[
     {name:'Buendía House',color:'#c9a84c',note:'Expanded. Melquíades has his own room here where he writes the parchments encoding the family\'s entire future.'},
     {name:'Gypsy Camp',color:'#9a7040',note:'Set up beyond the town edge. Source of all marvels: ice, telescopes, magnets, the daguerreotype.'},
     {name:'School',color:'#7a9a5a',note:'The first institution — a sign of Macondo\'s growing connection to the outside world.'},
     {name:'Úrsula\'s Garden',color:'#2a6a2a',note:'Úrsula plants and tends the garden that will eventually be swallowed by the house itself.'},
   ],
   buildings:[
     {x:370,y:265,w:66,h:55,color:'#c9a84c',label:'Buendía House',nos:true},
     {x:264,y:255,w:38,h:32,color:'#9a7040',label:'Gypsy Camp'},
     {x:480,y:248,w:42,h:36,color:'#7a9a5a',label:'School'},
     {x:294,y:310,w:28,h:24,color:'#d8c880',label:''},
     {x:446,y:316,w:26,h:22,color:'#d8c880',label:''},
     {x:334,y:215,w:24,h:20,color:'#d8c880',label:''},
     {x:456,y:202,w:24,h:20,color:'#d8c880',label:''},
     {x:268,y:342,w:22,h:18,color:'#d8c880',label:''},
     {x:502,y:312,w:22,h:18,color:'#d8c880',label:''},
     {x:310,y:362,w:22,h:18,color:'#d8c880',label:''},
     {x:440,y:362,w:22,h:18,color:'#d8c880',label:''},
   ],
   roads:[{x1:350,y1:60,x2:350,y2:530,w:9},{x1:200,y1:330,x2:540,y2:330,w:7}],
   zones:['dense','right']},

  {name:'Macondo at War',pop:'~600 inhabitants',year:'Generation 2–3',
   desc:'Colonel Aureliano Buendía transforms from goldsmith to revolutionary. A military garrison appears. The town is divided by ideology. The Colonel retreats to make golden fish in his workshop, endlessly crafting and melting.',
   nos:'The Colonel\'s workshop — where he melts and remakes the golden fish — is the novel\'s purest image of nostalgia as paralysis: reaching forever for a self that the wars dissolved.',
   locs:[
     {name:'Buendía House',color:'#c9a84c',note:'Aureliano\'s goldsmith workshop is here. This is where the golden fish are made and unmade, the most visible image of nostalgia in the book.'},
     {name:'Military Garrison',color:'#6b7080',note:'Installed by the Conservative government. Its presence signals the end of Macondo\'s innocence and isolation.'},
     {name:'The Church',color:'#d8d0c0',note:'Site of political sermons and social control. Father Nicanor performs his levitation here.'},
     {name:'Rebeca\'s House',color:'#d4a0c0',note:'After José Arcadio\'s death, Rebeca seals herself inside for decades — nostalgia made architecture.'},
   ],
   buildings:[
     {x:370,y:255,w:66,h:55,color:'#c9a84c',label:'Buendía House',nos:true},
     {x:254,y:245,w:52,h:44,color:'#6b7080',label:'Garrison'},
     {x:490,y:244,w:44,h:38,color:'#d8d0c0',label:'Church'},
     {x:254,y:342,w:38,h:32,color:'#d4a0c0',label:"Rebeca's",nos:true},
     {x:466,y:332,w:32,h:26,color:'#8b3a1a',label:''},
     {x:308,y:310,w:28,h:24,color:'#c8a060',label:''},
     {x:442,y:382,w:26,h:22,color:'#c8a060',label:''},
     {x:300,y:376,w:24,h:20,color:'#c8a060',label:''},
     {x:506,y:376,w:24,h:20,color:'#c8a060',label:''},
     {x:330,y:190,w:23,h:19,color:'#c8a060',label:''},
     {x:450,y:185,w:23,h:19,color:'#c8a060',label:''},
     {x:238,y:396,w:21,h:17,color:'#8b3a1a',label:''},
   ],
   roads:[{x1:350,y1:55,x2:350,y2:525,w:10},{x1:190,y1:310,x2:560,y2:310,w:8},{x1:190,y1:240,x2:560,y2:240,w:7}],
   zones:['sparse','right']},

  {name:'The Banana Boom',pop:'~4,000 inhabitants',year:'Generation 4–5',
   desc:'The United Fruit Company arrives. Electricity, a cinema, hotels, luxury. Fernanda del Carpio brings her imaginary aristocracy. The town sprawls and loses its soul as thousands of workers flood in to work the plantations.',
   nos:'Fernanda mourns an aristocratic world that never truly existed. Her nostalgia for status poisons the Buendía house from within, as the town is poisoned from without by corporate greed.',
   locs:[
     {name:'Buendía House',color:'#c9a84c',note:'Now full of Fernanda\'s suffocating rituals and invisible doctors. Nostalgia for status has replaced genuine life.'},
     {name:'Banana Company HQ',color:'#8b3a1a',note:'The gringo enclave behind wire fencing — a colony within a colony, soon to unleash the massacre.'},
     {name:'Hotel',color:'#9a7040',note:'Built for foreign company men. Signals Macondo\'s transformation into an economic outpost.'},
     {name:'Town Hall',color:'#6b7080',note:'Now fully controlled by banana company-aligned interests. Democracy replaced by commerce.'},
     {name:'Meme\'s School',color:'#7a9a5a',note:'Where Meme\'s affair with Mauricio Babilonia — surrounded by yellow butterflies — begins and ends in tragedy.'},
   ],
   buildings:[
     {x:365,y:250,w:72,h:60,color:'#c9a84c',label:'Buendía House',nos:true},
     {x:234,y:234,w:60,h:50,color:'#6b7080',label:'Town Hall'},
     {x:500,y:235,w:55,h:46,color:'#9a7040',label:'Hotel'},
     {x:234,y:342,w:55,h:44,color:'#8b3a1a',label:'Banana Co.'},
     {x:496,y:332,w:48,h:40,color:'#7a9a5a',label:"Meme's School"},
     {x:300,y:315,w:32,h:26,color:'#c8a060',label:''},
     {x:440,y:310,w:30,h:26,color:'#c8a060',label:''},
     {x:530,y:392,w:28,h:24,color:'#8b3a1a',label:''},
     {x:220,y:402,w:28,h:24,color:'#8b3a1a',label:''},
     {x:310,y:392,w:26,h:22,color:'#c8a060',label:''},
     {x:440,y:396,w:26,h:22,color:'#c8a060',label:''},
     {x:350,y:165,w:26,h:22,color:'#c8a060',label:''},
     {x:480,y:160,w:26,h:22,color:'#c8a060',label:''},
     {x:228,y:175,w:26,h:22,color:'#c8a060',label:''},
     {x:550,y:242,w:24,h:20,color:'#8b3a1a',label:''},
     {x:210,y:307,w:24,h:20,color:'#6b7080',label:''},
     {x:555,y:307,w:24,h:20,color:'#8b3a1a',label:''},
   ],
   roads:[{x1:350,y1:40,x2:350,y2:540,w:11},{x1:175,y1:300,x2:575,y2:300,w:9},{x1:175,y1:220,x2:575,y2:220,w:8},{x1:175,y1:392,x2:575,y2:392,w:8},{x1:470,y1:40,x2:470,y2:540,w:8},{x1:230,y1:40,x2:230,y2:540,w:8}],
   zones:['verysparse']},

  {name:'The Deluge',pop:'~500 inhabitants',year:'Generation 5',
   desc:'The banana workers are massacred. It rains without stopping for four years, eleven months, and two days. The company dissolves. Buildings rot. Official forgetting erases history — the government declares nothing happened.',
   nos:'State-sponsored erasure of memory is the novel\'s most political nostalgia: the authorities manufacture a false past, making it impossible to mourn what officially never existed.',
   locs:[
     {name:'Buendía House',color:'#8b7040',note:'Half-collapsed. José Arcadio Segundo hides in Melquíades\' room with the parchments — the only honest memory left in Macondo.'},
     {name:'Empty Garrison',color:'#5a6070',note:'Abandoned by soldiers after the massacre. Now filling with water and rot.'},
     {name:'Train Station',color:'#4a5040',note:'The last train carried away what the banana company didn\'t want. It never returned.'},
   ],
   buildings:[
     {x:365,y:255,w:65,h:55,color:'#8b7040',label:'Buendía House',nos:true},
     {x:240,y:245,w:55,h:46,color:'#5a6070',label:'Old Garrison'},
     {x:495,y:245,w:50,h:42,color:'#4a5040',label:'Station'},
     {x:295,y:332,w:40,h:32,color:'#4a4530',label:''},
     {x:456,y:332,w:36,h:28,color:'#4a4530',label:''},
     {x:310,y:396,w:28,h:22,color:'#3a3520',label:''},
     {x:440,y:392,w:28,h:22,color:'#3a3520',label:''},
     {x:224,y:376,w:26,h:20,color:'#3a4530',label:''},
     {x:520,y:382,w:26,h:20,color:'#3a3520',label:''},
   ],
   roads:[{x1:350,y1:55,x2:350,y2:520,w:9},{x1:185,y1:305,x2:560,y2:305,w:8},{x1:185,y1:225,x2:560,y2:225,w:7}],
   zones:['regrow','right'],
   rain:true},

  {name:'The Ruins',pop:'~40 inhabitants',year:'Generation 6–7',
   desc:'The town is almost empty. The Buendía house is a labyrinth of abandonment. The last Aureliano finally deciphers Melquíades\' parchments and discovers they describe the very moment he is reading — as the biblical wind arrives.',
   nos:'The final revelation: the family was condemned to one hundred years of solitude and would never have a second chance on earth. Nostalgia becomes a death sentence written one hundred years before it is carried out.',
   locs:[
     {name:'Buendía House — Ruin',color:'#6a5030',note:'Melquíades\' room is the only intact space — a room outside of time where past and future exist simultaneously.'},
     {name:'Rebeca\'s Sealed House',color:'#d4a0c0',note:'Still sealed after fifty years. Rebeca, impossibly old, has already become part of the decay she sealed herself inside.'},
   ],
   buildings:[
     {x:365,y:255,w:55,h:48,color:'#6a5030',label:'Buendía Ruin',nos:true},
     {x:254,y:250,w:40,h:34,color:'#d4a0c0',label:"Rebeca's",nos:true},
     {x:490,y:256,w:32,h:28,color:'#3a3020',label:''},
     {x:304,y:332,w:26,h:22,color:'#302818',label:''},
     {x:430,y:327,w:22,h:18,color:'#302818',label:''},
   ],
   roads:[{x1:350,y1:80,x2:350,y2:510,w:7}],
   zones:['dense','right','reclaim']},
];

const TL=[
  {gen:'First Generation',title:'José Arcadio Buendía Founds Macondo',tags:['founding','nostalgia'],body:'Fleeing guilt after killing Prudencio Aguilar, José Arcadio leads twenty families to found Macondo beside a clear river. The town is organized so every house has equal access to the water — a utopian arrangement designed from memory of what community should be.',nos:'The founding is already an act of nostalgic reconstruction: building the ideal village that never existed in the one left behind.'},
  {gen:'First Generation',title:'The Gypsies Arrive with Marvels',tags:['founding','supernatural'],body:'Melquíades and his gypsies bring magnets, ice, flying carpets, and daguerreotypes. José Arcadio becomes obsessed with making ice again, with finding the philosopher\'s stone — reaching for futures that are really fantasies of a more innocent past.',nos:'Every marvel the gypsies bring awakens a nostalgia for something that was never quite possessed — the wonder of a world still explicable by magic.'},
  {gen:'First Generation',title:'The Insomnia Plague Erases Memory',tags:['supernatural','nostalgia'],body:'A plague of insomnia spreads through Macondo. Inhabitants begin to forget the names of things, then the things themselves. They label every object with its name and function. But the labels outlast the memories, and meaning itself begins to drain away.',nos:'The insomnia plague is nostalgia literalized: a community terrified of forgetting, discovering that memory is fragile and the past can vanish completely.'},
  {gen:'First Generation',title:'Melquíades Writes the Parchments',tags:['supernatural','nostalgia'],body:'Melquíades, seemingly returned from the dead, closes himself in his room and writes in Sanskrit verse, encoding the entire future history of the Buendía family into parchments that will not be deciphered for a century.',nos:'The parchments are the ultimate nostalgic object: containing the memory of a future that hasn\'t happened yet, written for someone who will be born long after the author is dead.'},
  {gen:'Second Generation',title:'Colonel Aureliano Buendía & The Golden Fish',tags:['war','nostalgia'],body:'After seventeen failed civil uprisings, the Colonel retreats to his workshop. He spends the rest of his life crafting tiny golden fish — then melting them down to make them again, endlessly. He speaks to almost no one. He experiences nothing new.',nos:'The golden fish are nostalgia made visible and physical. He is trying to recover a version of himself that existed before the wars, before disillusionment — and the endless melting-down is the admission that he never can.'},
  {gen:'Second Generation',title:'Rebeca Seals Herself Inside',tags:['decay','nostalgia'],body:'After the death of José Arcadio, Rebeca bricks up the doors and windows of her house and never emerges again. She had arrived in Macondo as a child carrying her parents\' bones in a bag; her whole life has been an act of carrying the dead.',nos:'Rebeca\'s sealed house is the novel\'s most architectural image of nostalgia: grief becomes a structure you live inside, closing yourself off from any future that does not contain the lost past.'},
  {gen:'Third Generation',title:'Macondo Grows & the State Arrives',tags:['progress'],body:'A mayor, a priest, and government institutions arrive. Streets are laid, a billiard parlor and cinema open. Macondo is being absorbed into the nation — subjected to its politics, bureaucracy, and official versions of history.',nos:'For the older Buendías, every institution that arrives marks the distance from the founding paradise. Growth feels like loss.'},
  {gen:'Fourth Generation',title:'The Banana Company Transforms Everything',tags:['progress','decay'],body:'Mr. Herbert eats a banana and the United Fruit Company arrives. Electric lights, a cinema, hotels, and thousands of migrant workers flood Macondo. The transformation is total and irreversible.',nos:'Prosperity destroys the simplicity the founding families mourned. The banana boom proves that modernization and nostalgia are lethal to each other.'},
  {gen:'Fourth Generation',title:'Fernanda del Carpio & Her Phantom Kingdom',tags:['nostalgia','decay'],body:'Fernanda del Carpio, trained from birth to be queen of a vanished aristocracy, imposes her rituals on the Buendía house: a golden chamber pot, invisible doctors, letters to phantoms. She mourns a social order that was never real.',nos:'Fernanda\'s entire character studies how nostalgia can be inherited and weaponized: she mourns a past she never lived, turning grief for an imaginary world into tyranny over a real one.'},
  {gen:'Fifth Generation',title:'The Banana Workers\' Massacre',tags:['war','decay'],body:'Three thousand striking workers are gathered in the central plaza. The army opens fire. The bodies are loaded onto a train and dumped in the sea. The government declares that nothing happened — and Macondo believes it.',nos:'State-sponsored erasure of memory is the most political nostalgia in the novel: the authorities manufacture a false past, making it impossible to mourn what officially never existed.'},
  {gen:'Fifth Generation',title:'Four Years, Eleven Months & Two Days of Rain',tags:['decay','nostalgia'],body:'After the massacre comes the rain — unceasing, rotting everything. The banana company dismantles its operation and leaves. The town turns to mud and silence. What was modern becomes ruin almost overnight.',nos:'The rain is described as if nature itself is grieving. The deluge washes away even the false memory of the boom years, leaving only the older and deeper losses.'},
  {gen:'Sixth Generation',title:'The Long Decline of the Buendías',tags:['decay','nostalgia'],body:'The house fills with ants. Úrsula, blind and over a hundred years old, shrinks to a tiny doll and is finally carried off. The garden consumes rooms. Cousins love cousins. Solitude metastasizes into the last Buendías.',nos:'Every room of the house holds a memory too painful to throw away and too heavy to live with. The house is a museum of nostalgia in which the exhibits have taken over.'},
  {gen:'Seventh Generation',title:'The Last Aureliano Deciphers the Parchments',tags:['supernatural','nostalgia','decay'],body:'Aureliano Babilonia, the last of his line, finally reads Melquíades\' parchments and discovers they describe his own life — including the very moment of his reading. He reads that the city of mirrors will be wiped from the earth and the race condemned to one hundred years of solitude will never have a second chance.',nos:'The final revelation: nostalgia was always the family\'s doom. They were condemned from the beginning to long for a paradise they could never return to — and the longing itself prevented them from building anything that could last.'},
];

// ===================== MAP =====================
let mapIdx=0;
function initMap(){
  const list=document.getElementById('map-era-list');
  MAP_DATA.forEach((era,i)=>{
    const btn=document.createElement('button');
    btn.className='map-era-btn'+(i===0?' active':'');
    btn.innerHTML=`${era.name}<small>${era.year}</small>`;
    btn.addEventListener('click',()=>{
      mapIdx=i;
      document.querySelectorAll('.map-era-btn').forEach((b,j)=>b.classList.toggle('active',j===i));
      drawMap(i);
    });
    list.appendChild(btn);
  });
  drawMap(0);
}

function drawMap(idx){
  const era=MAP_DATA[idx];
  const svg=document.getElementById('macondo-svg');
  svg.innerHTML='';
  const W=700,H=560;
  const defs=svgEl('defs');
  defs.innerHTML=`<filter id="glow" x="-50%" y="-50%" width="200%" height="200%"><feGaussianBlur stdDeviation="8" result="blur"/><feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge></filter>
  <filter id="soft" x="-20%" y="-20%" width="140%" height="140%"><feGaussianBlur stdDeviation="3"/></filter>`;
  svg.appendChild(defs);
  const bgC=['#0a1408','#080810','#130606','#0e0a04','#040407','#070604'];
  svgRect(svg,0,0,W,H,bgC[idx]||'#0a1408');
  drawJungle(svg,W,H,era.zones||[]);
  const rvC=idx>=4?'#0d1a28':idx===5?'#080a10':'#1a4890';
  const rp=svgEl('path');
  rp.setAttribute('d','M 105 0 C 112 140 98 280 108 420 C 118 510 105 560 105 560 L 132 560 C 132 560 142 510 132 420 C 122 280 136 140 128 0 Z');
  rp.setAttribute('fill',rvC);rp.setAttribute('opacity','.8');
  svg.appendChild(rp);
  svgText(svg,118,28,'River','#4060a0',9,'Cinzel,serif',270);
  era.roads.forEach(r=>{
    const l=svgEl('line');
    l.setAttribute('x1',r.x1);l.setAttribute('y1',r.y1);l.setAttribute('x2',r.x2);l.setAttribute('y2',r.y2);
    l.setAttribute('stroke',idx>=4?'#282015':'#5c3e22');l.setAttribute('stroke-width',r.w||8);
    svg.appendChild(l);
  });
  era.buildings.forEach(b=>{
    if(b.nos){
      const g=svgEl('ellipse');
      g.setAttribute('cx',b.x);g.setAttribute('cy',b.y);
      g.setAttribute('rx',b.w*.95);g.setAttribute('ry',b.h*.95);
      g.setAttribute('fill','#d4a0c0');g.setAttribute('opacity','.16');
      g.setAttribute('filter','url(#glow)');
      svg.appendChild(g);
    }
  });
  era.buildings.forEach((b,i)=>{
    const g=svgEl('g');
    const sh=svgEl('rect');
    sh.setAttribute('x',b.x-b.w/2+4);sh.setAttribute('y',b.y-b.h/2+4);
    sh.setAttribute('width',b.w);sh.setAttribute('height',b.h);
    sh.setAttribute('fill','rgba(0,0,0,.45)');sh.setAttribute('rx','2');
    g.appendChild(sh);
    const r2=svgEl('rect');
    r2.setAttribute('x',b.x-b.w/2);r2.setAttribute('y',b.y-b.h/2);
    r2.setAttribute('width',b.w);r2.setAttribute('height',b.h);
    r2.setAttribute('fill',b.color);r2.setAttribute('rx','2');
    if(idx===5){r2.setAttribute('opacity','.65');r2.setAttribute('transform',`rotate(${(i%3-1)*3},${b.x},${b.y})`);}
    const an=svgEl('animate');
    an.setAttribute('attributeName','opacity');an.setAttribute('from','0');an.setAttribute('to',idx===5?'.65':'1');
    an.setAttribute('dur','.3s');an.setAttribute('begin',`${i*.04}s`);an.setAttribute('fill','freeze');
    r2.appendChild(an);g.appendChild(r2);
    const by2=b.y-b.h/2;
    const rof=svgEl('polygon');
    rof.setAttribute('points',`${b.x-b.w/2},${by2} ${b.x+b.w/2},${by2} ${b.x},${by2-b.h*.35}`);
    rof.setAttribute('fill',idx===3?'#7a3010':'#601010');
    if(idx===5)rof.setAttribute('opacity','.3');
    g.appendChild(rof);
    if(idx<5&&b.w>30){
      [-1,1].forEach(side=>{
        const wr=svgEl('rect');
        wr.setAttribute('x',b.x+side*b.w*.22-3);wr.setAttribute('y',b.y+b.h*.1-4);
        wr.setAttribute('width','6');wr.setAttribute('height','8');
        wr.setAttribute('fill','#ffe080');wr.setAttribute('opacity','.55');
        g.appendChild(wr);
      });
    }
    if(b.label){
      const lt=svgEl('text');
      lt.setAttribute('x',b.x);lt.setAttribute('y',b.y+b.h/2+13);
      lt.setAttribute('text-anchor','middle');lt.setAttribute('fill',b.nos?'#d4a0c0':'#c9a84c');
      lt.setAttribute('font-size','9.5');lt.setAttribute('font-family','Cinzel,serif');
      lt.textContent=b.label;g.appendChild(lt);
    }
    svg.appendChild(g);
  });
  drawCompass(svg,W-46,H-46);
  const pb=svgEl('g');
  svgRectG(pb,W-132,12,118,38,'rgba(0,0,0,.65)',4);
  svgText(pb,W-73,26,'POPULATION','#7a6030',7,'Cinzel,serif');
  svgText(pb,W-73,41,era.pop,'#c9a84c',11,'Cinzel,serif');
  svg.appendChild(pb);
  if(era.buildings.some(b=>b.nos)){
    const nl=svgEl('g');
    svgRectG(nl,14,H-46,162,30,'rgba(0,0,0,.6)',3);
    const nd=svgEl('circle');
    nd.setAttribute('cx','30');nd.setAttribute('cy',H-31);nd.setAttribute('r','5');
    nd.setAttribute('fill','#d4a0c0');nd.setAttribute('opacity','.75');nl.appendChild(nd);
    svgText(nl,42,H-27,'Nostalgia Site','#d4a0c0',9,'Cinzel,serif','start');
    svg.appendChild(nl);
  }
  if(idx<=1){
    for(let i=0;i<22;i++){
      const fc=svgEl('circle');
      fc.setAttribute('cx',140+Math.random()*(W-160));fc.setAttribute('cy',40+Math.random()*(H-60));
      fc.setAttribute('r','2');fc.setAttribute('fill','#ffffa0');
      const fa=svgEl('animate');
      fa.setAttribute('attributeName','opacity');fa.setAttribute('values','0;0.9;0');
      fa.setAttribute('dur',(1+Math.random()*2.5)+'s');fa.setAttribute('repeatCount','indefinite');
      fa.setAttribute('begin',Math.random()*4+'s');
      fc.appendChild(fa);svg.appendChild(fc);
    }
  }
  if(era.rain){
    for(let i=0;i<80;i++){
      const rl=svgEl('line');
      const rx=140+Math.random()*(W-160),ry=Math.random()*H;
      rl.setAttribute('x1',rx);rl.setAttribute('y1',ry);rl.setAttribute('x2',rx+4);rl.setAttribute('y2',ry+14);
      rl.setAttribute('stroke','#5090c0');rl.setAttribute('stroke-width','0.8');rl.setAttribute('opacity','.45');
      const ra=svgEl('animateTransform');
      ra.setAttribute('attributeName','transform');ra.setAttribute('type','translate');
      ra.setAttribute('values',`0,0;-10,${H}`);ra.setAttribute('dur',(0.4+Math.random()*0.4)+'s');
      ra.setAttribute('repeatCount','indefinite');ra.setAttribute('begin',Math.random()+'s');
      rl.appendChild(ra);svg.appendChild(rl);
    }
  }
  document.getElementById('map-heading').textContent=era.name;
  document.getElementById('map-pop').textContent=`${era.pop} · ${era.year}`;
  document.getElementById('map-desc-era').textContent=era.name;
  document.getElementById('map-desc-text').textContent=era.desc;
  document.getElementById('map-nos-p').textContent=era.nos;
  const locsEl=document.getElementById('map-locs');locsEl.innerHTML='';
  era.locs.forEach(loc=>{
    const d=document.createElement('div');d.className='map-loc-item';
    d.innerHTML=`<div class="map-loc-dot" style="background:${loc.color}"></div><div class="map-loc-info"><strong>${loc.name}</strong><span>${loc.note}</span></div>`;
    locsEl.appendChild(d);
  });
}

const SVG_NS='http://www.w3.org/2000/svg';
function svgEl(tag){return document.createElementNS(SVG_NS,tag);}
function svgRect(parent,x,y,w,h,fill){const r=svgEl('rect');r.setAttribute('x',x);r.setAttribute('y',y);r.setAttribute('width',w);r.setAttribute('height',h);r.setAttribute('fill',fill);parent.appendChild(r);}
function svgRectG(parent,x,y,w,h,fill,rx){const r=svgEl('rect');r.setAttribute('x',x);r.setAttribute('y',y);r.setAttribute('width',w);r.setAttribute('height',h);r.setAttribute('fill',fill);if(rx)r.setAttribute('rx',rx);parent.appendChild(r);}
function svgText(parent,x,y,content,fill,size,family,anchor){const t=svgEl('text');t.setAttribute('x',x);t.setAttribute('y',y);t.setAttribute('text-anchor',anchor||'middle');t.setAttribute('fill',fill);t.setAttribute('font-size',size||10);t.setAttribute('font-family',family||'serif');t.textContent=content;parent.appendChild(t);}

function drawJungle(svg,W,H,zones){
  const base='#0a2208',light='#123010';
  const density=zones.includes('verysparse')?8:zones.includes('sparse')?28:zones.includes('dense')?75:zones.includes('regrow')?38:50;
  for(let i=0;i<density;i++){
    const onR=i%2===0||zones.includes('right');
    const x=onR?(W-10-Math.random()*130):(142+Math.random()*100);
    const y=Math.random()*H;
    const r=10+Math.random()*28;
    const c=svgEl('circle');
    c.setAttribute('cx',x);c.setAttribute('cy',y);c.setAttribute('r',r);
    c.setAttribute('fill',Math.random()>.5?base:light);c.setAttribute('opacity',String(.24+Math.random()*.38));
    svg.appendChild(c);
  }
  if(zones.includes('reclaim')){
    for(let i=0;i<45;i++){
      const x=155+Math.random()*400,y=65+Math.random()*420;
      const c=svgEl('circle');
      c.setAttribute('cx',x);c.setAttribute('cy',y);c.setAttribute('r',5+Math.random()*18);
      c.setAttribute('fill','#0d2008');c.setAttribute('opacity',String(.1+Math.random()*.18));
      svg.appendChild(c);
    }
  }
}

function drawCompass(svg,cx,cy){
  const g=svgEl('g');
  const bg=svgEl('circle');bg.setAttribute('cx',cx);bg.setAttribute('cy',cy);bg.setAttribute('r','20');bg.setAttribute('fill','rgba(0,0,0,.55)');bg.setAttribute('stroke','rgba(201,168,76,.3)');bg.setAttribute('stroke-width','1');g.appendChild(bg);
  [['N',0,true],['S',180,false],['E',90,false],['W',270,false]].forEach(([lbl,ang,primary])=>{
    const rad=ang*Math.PI/180;
    const lx=cx+Math.sin(rad)*14,ly=cy-Math.cos(rad)*14;
    svgText(g,lx,ly+4,lbl,primary?'#c9a84c':'#7a6030',9,'Cinzel,serif');
  });
  svg.appendChild(g);
}

// ===================== TIMELINE =====================
function initTL(){
  const track=document.getElementById('tl-track');
  let lastGen='';
  TL.forEach((ev,i)=>{
    if(ev.gen!==lastGen){
      const h=document.createElement('div');h.className='tl-gen-head';h.textContent=ev.gen;track.appendChild(h);lastGen=ev.gen;
    }
    const el=document.createElement('div');el.className='tl-event';
    el.innerHTML=`<div class="tl-left"><div class="tl-gen-lbl">${ev.gen.split(' ').slice(-1)[0]}<br>Gen.</div></div>
    <div class="tl-line-col"><div class="tl-line-seg"></div><div class="tl-node"></div><div class="tl-line-seg"></div></div>
    <div class="tl-right">
      <div class="tl-tags">${ev.tags.map(t=>`<span class="tl-tag ${t}">${t}</span>`).join('')}</div>
      <div class="tl-title">${ev.title}</div>
      <div class="tl-body">${ev.body}</div>
      ${ev.nos?`<div class="tl-nos">${ev.nos}</div>`:''}
    </div>`;
    track.appendChild(el);
  });
  const obs=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('vis');});},{threshold:.08});
  document.querySelectorAll('.tl-event').forEach(el=>obs.observe(el));
}

function animateTL(){
  document.querySelectorAll('.tl-event').forEach((el,i)=>{
    const r=el.getBoundingClientRect();
    if(r.top<window.innerHeight+300)setTimeout(()=>el.classList.add('vis'),i*40);
  });
}

// ============================================================
// INLINE EDIT MODE
// ============================================================
(function(){
  const EDITABLE_SELECTORS = [
    '.nav-logo','.intro-title','.intro-amp','.intro-quote','.intro-author','.enter-btn',
    '.eyebrow','.sec-title','.sec-sub',
    '.nos-card h3','.nos-card p','.nos-card .card-tag','.nos-card .character','.nos-card .quote-pull','.nos-card .card-num',
    '.author-note h3','.author-note p','.nos-intro-block p','.theme-strip h3','.chip',
    '#era-name','#era-desc','#map-heading','#map-pop','#map-desc-era','#map-desc-text','#map-nos-p',
    '.tl-title','.tl-body','.tl-gen-head','.tl-nos','.tl-gen-lbl',
  ];
  let editing=false;
  const toggle=document.getElementById('edit-toggle');
  const hint=document.getElementById('edit-hint');
  const toast=document.getElementById('edit-toast');
  let toastTimer;
  const origEnter=document.getElementById('enter-btn');
  origEnter.addEventListener('click',()=>{
    setTimeout(()=>{toggle.style.display='flex';},800);
  },{once:true});
  toggle.addEventListener('click',()=>{
    editing=!editing;
    document.body.classList.toggle('editing',editing);
    toggle.querySelector('.dot').style.background=editing?'#60e060':'';
    toggle.childNodes[1].textContent=editing?' Exit Edit':' Edit Mode';
    applyEditable(editing);
    if(editing)showToast('Click any text to edit it');
  });
  function applyEditable(on){
    EDITABLE_SELECTORS.forEach(sel=>{
      document.querySelectorAll(sel).forEach(el=>{
        if(on){
          el.setAttribute('contenteditable','true');el.setAttribute('spellcheck','false');el.style.cursor='text';
          el.addEventListener('mouseenter',showHint);el.addEventListener('mouseleave',hideHint);el.addEventListener('mousemove',moveHint);
          el.addEventListener('blur',onBlur);el.addEventListener('keydown',onKeydown);
        } else {
          el.setAttribute('contenteditable','false');el.style.cursor='';
          el.removeEventListener('mouseenter',showHint);el.removeEventListener('mouseleave',hideHint);el.removeEventListener('mousemove',moveHint);
          el.removeEventListener('blur',onBlur);el.removeEventListener('keydown',onKeydown);el.blur();
        }
      });
    });
    document.querySelectorAll('.map-loc-item strong, .map-loc-item span').forEach(el=>{
      if(on){el.setAttribute('contenteditable','true');el.setAttribute('spellcheck','false');el.addEventListener('blur',onBlur);el.addEventListener('keydown',onKeydown);}
      else{el.setAttribute('contenteditable','false');el.blur();}
    });
  }
  function showHint(e){hint.textContent='Click to edit';hint.classList.add('show');moveHint(e);}
  function hideHint(){hint.classList.remove('show');}
  function moveHint(e){hint.style.left=(e.clientX+14)+'px';hint.style.top=(e.clientY-28)+'px';}
  function onBlur(){showToast('✓ Text updated');}
  function onKeydown(e){
    const sl=['H3','H2','H1','STRONG','SPAN','DIV'];
    if(e.key==='Enter'&&sl.includes(e.target.tagName)){e.preventDefault();e.target.blur();}
    if(e.key==='Escape'){e.target.blur();}
  }
  function showToast(msg){clearTimeout(toastTimer);toast.textContent=msg;toast.classList.add('show');toastTimer=setTimeout(()=>toast.classList.remove('show'),2200);}
  document.addEventListener('mousemove',e=>{
    if(editing&&e.target.getAttribute('contenteditable')==='true'){
      document.getElementById('cursor').style.width='3px';document.getElementById('cursor').style.height='20px';document.getElementById('cursor').style.borderRadius='1px';
    } else {
      document.getElementById('cursor').style.width='';document.getElementById('cursor').style.height='';document.getElementById('cursor').style.borderRadius='';
    }
  });
})();

// ===================== RAIN CANVAS =====================
const rCnv=document.getElementById('rain-cnv');
const rCtx=rCnv.getContext('2d');
const drops=Array.from({length:200},()=>({x:Math.random()*2000,y:Math.random()*1200,sp:5+Math.random()*8,len:12+Math.random()*18}));
function resizeRain(){rCnv.width=window.innerWidth;rCnv.height=window.innerHeight;}
resizeRain();window.addEventListener('resize',resizeRain);
function rainLoop(){
  rCtx.clearRect(0,0,rCnv.width,rCnv.height);
  rCtx.strokeStyle='rgba(100,160,220,.4)';rCtx.lineWidth=.7;
  drops.forEach(d=>{rCtx.beginPath();rCtx.moveTo(d.x,d.y);rCtx.lineTo(d.x+4,d.y+d.len);rCtx.stroke();d.y+=d.sp;if(d.y>rCnv.height){d.y=-20;d.x=Math.random()*rCnv.width;}});
  requestAnimationFrame(rainLoop);
}
rainLoop();
</script>
</body>
</html>
