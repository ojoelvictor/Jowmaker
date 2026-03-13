<!DOCTYPE html>

<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>JOW MAKER — Produtora Audiovisual</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700;1,900&family=Sora:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  background: #171717;
  color: #DEDEDE;
  font-family: 'Sora', sans-serif;
  overflow-x: hidden;
}
:root {
--or: #F25623;
--bk: #171717;
--lg: #DEDEDE;
--dg: #4D4D4D;
--wh: #ffffff;
}
::-webkit-scrollbar { width: 3px; }
::-webkit-scrollbar-track { background: var(--bk); }
::-webkit-scrollbar-thumb { background: var(--or); }
nav {
position: fixed; top: 0; left: 0; right: 0; z-index: 999;
height: 72px; padding: 0 52px;
display: flex; align-items: center; justify-content: space-between;
background: rgba(23,23,23,0.9);
backdrop-filter: blur(24px);
border-bottom: 1px solid rgba(255,255,255,0.06);
}
.nav-logo img { height: 22px; filter: brightness(0) invert(1); display: block; }
.nav-menu { display: flex; gap: 40px; list-style: none; }
.nav-menu a { color: rgba(222,222,222,0.45); text-decoration: none; font-size: 12px; font-weight: 500; letter-spacing: 0.06em; transition: color .2s; }
.nav-menu a:hover { color: var(--lg); }
.nav-cta { background: var(--or); color: var(--wh); border: none; padding: 11px 26px; border-radius: 100px; font-family: 'Sora', sans-serif; font-size: 12px; font-weight: 600; cursor: pointer; letter-spacing: 0.04em; transition: transform .2s, box-shadow .2s; }
.nav-cta:hover { transform: translateY(-2px); box-shadow: 0 8px 28px rgba(242,86,35,.4); }
.hero { min-height: 100vh; padding-top: 72px; display: grid; grid-template-columns: 1fr 1fr; position: relative; }
.hero-l { background: linear-gradient(160deg, #F25623 0%, #c0390e 60%, #171717 100%); position: relative; overflow: hidden; display: flex; flex-direction: column; justify-content: flex-end; padding: 56px 52px; min-height: calc(100vh - 72px); }
.hero-l::after { content: ''; position: absolute; inset: 0; background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23000000' fill-opacity='0.04'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E"); pointer-events: none; }
.hero-badge { position: absolute; top: 40px; left: 52px; background: rgba(0,0,0,0.2); border: 1px solid rgba(255,255,255,0.15); border-radius: 100px; padding: 7px 16px; font-size: 10px; font-weight: 600; letter-spacing: 0.2em; text-transform: uppercase; color: rgba(255,255,255,0.7); display: flex; align-items: center; gap: 8px; }
.badge-dot { width: 6px; height: 6px; border-radius: 50%; background: rgba(255,255,255,0.9); animation: blink 2s ease-in-out infinite; }
@keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.3} }
.hero-h1 { font-family: 'Playfair Display', serif; font-weight: 900; font-size: clamp(58px, 5.5vw, 88px); line-height: 0.95; letter-spacing: -2px; color: #fff; margin-bottom: 24px; position: relative; z-index: 1; }
.hero-h1 em { font-style: italic; display: block; }
.hero-p { font-size: 14px; font-weight: 300; color: rgba(255,255,255,0.65); max-width: 320px; line-height: 1.8; margin-bottom: 36px; position: relative; z-index: 1; }
.hero-btns { display: flex; gap: 12px; position: relative; z-index: 1; }
.btn-w { background: #fff; color: var(--or); border: none; padding: 13px 28px; border-radius: 100px; font-family: 'Sora',sans-serif; font-size: 12px; font-weight: 700; cursor: pointer; transition: transform .2s, box-shadow .2s; }
.btn-w:hover { transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,0,0,.25); }
.btn-gl { background: rgba(255,255,255,0.1); border: 1px solid rgba(255,255,255,0.25); color: #fff; padding: 13px 24px; border-radius: 100px; font-family: 'Sora',sans-serif; font-size: 12px; font-weight: 500; cursor: pointer; display: flex; align-items: center; gap: 8px; transition: background .2s; }
.btn-gl:hover { background: rgba(255,255,255,0.18); }
.hero-pills { position: absolute; bottom: 0; left: 0; right: 0; display: flex; border-top: 1px solid rgba(255,255,255,0.1); }
.hero-pill { flex: 1; padding: 18px 20px; border-right: 1px solid rgba(255,255,255,0.1); display: flex; flex-direction: column; gap: 4px; }
.hero-pill:last-child { border-right: none; }
.hp-num { font-size: 9px; font-weight: 700; color: rgba(255,255,255,0.4); letter-spacing: 0.15em; }
.hp-name { font-size: 11px; font-weight: 500; color: rgba(255,255,255,0.7); }
.hero-r { background: var(--bk); display: flex; flex-direction: column; padding: 52px; gap: 16px; justify-content: center; }
.hero-quote { background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.07); border-radius: 20px; padding: 32px; }
.hq-title { font-family: 'Playfair Display', serif; font-size: 20px; font-weight: 700; color: #fff; margin-bottom: 10px; line-height: 1.3; }
.hq-sub { font-size: 13px; font-weight: 300; color: rgba(222,222,222,0.4); line-height: 1.75; }
.hero-reel { background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.07); border-radius: 20px; aspect-ratio: 16/9; position: relative; overflow: hidden; cursor: pointer; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.hero-reel::before { content:''; position:absolute; inset:0; background: linear-gradient(135deg, rgba(242,86,35,.1), transparent 65%); }
.reel-btn { width: 60px; height: 60px; border-radius: 50%; background: var(--or); color: #fff; display: flex; align-items: center; justify-content: center; font-size: 18px; padding-left: 4px; box-shadow: 0 0 0 14px rgba(242,86,35,.1); position: relative; z-index: 1; transition: transform .25s, box-shadow .25s; }
.hero-reel:hover .reel-btn { transform: scale(1.1); box-shadow: 0 0 0 22px rgba(242,86,35,.07); }
.reel-lbl { position: absolute; bottom: 14px; left: 18px; font-size: 9px; letter-spacing: 0.22em; text-transform: uppercase; color: rgba(255,255,255,.3); font-weight: 500; }
.hero-stats { display: grid; grid-template-columns: repeat(3,1fr); gap: 12px; }
.hstat { background: rgba(255,255,255,.03); border: 1px solid rgba(255,255,255,.07); border-radius: 14px; padding: 20px; text-align: center; }
.hstat-n { font-family: 'Playfair Display', serif; font-size: 30px; font-weight: 900; color: var(--or); letter-spacing: -1px; }
.hstat-l { font-size: 10px; color: rgba(222,222,222,.3); margin-top: 4px; }
.mq { background: var(--or); padding: 15px 0; overflow: hidden; }
.mq-track { display: flex; gap: 52px; white-space: nowrap; animation: mq 22s linear infinite; }
.mq-item { font-size: 10px; font-weight: 700; letter-spacing: 0.3em; text-transform: uppercase; color: rgba(255,255,255,.6); flex-shrink: 0; }
@keyframes mq { from{transform:translateX(0)} to{transform:translateX(-50%)} }
.paraquem { background: var(--lg); padding: 110px 52px; }
.pq-inner { max-width: 1200px; margin: 0 auto; }
.sec-tag { font-size: 10px; font-weight: 700; letter-spacing: 0.28em; text-transform: uppercase; color: var(--or); margin-bottom: 16px; display: flex; align-items: center; gap: 10px; }
.sec-tag::before { content:''; width:22px; height:1.5px; background:var(--or); }
.pq-h2 { font-family: 'Playfair Display', serif; font-size: clamp(38px,3.8vw,58px); font-weight: 900; line-height: 1.05; letter-spacing: -1.5px; color: var(--bk); margin-bottom: 60px; }
.pq-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: 3px; }
.pq-card { background: var(--bk); border-radius: 0; padding: 48px 36px; position: relative; overflow: hidden; transition: background .3s; cursor: default; }
.pq-grid .pq-card:first-child { border-radius: 24px 0 0 24px; }
.pq-grid .pq-card:last-child { border-radius: 0 24px 24px 0; }
.pq-card::before { content:''; position:absolute; bottom:0; left:0; width:0; height:2px; background:var(--or); transition: width .5s ease; }
.pq-card:hover { background: #1f1f1f; }
.pq-card:hover::before { width:100%; }
.pq-num { font-family: 'Playfair Display', serif; font-size: 72px; font-weight: 900; color: rgba(242,86,35,.1); line-height: 1; margin-bottom: -8px; letter-spacing: -3px; }
.pq-icon { font-size: 28px; margin: 12px 0; }
.pq-title { font-family: 'Playfair Display', serif; font-size: 22px; font-weight: 700; color: #fff; margin-bottom: 12px; }
.pq-desc { font-size: 13px; font-weight: 300; color: rgba(222,222,222,.45); line-height: 1.8; }
.pq-tags { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 24px; }
.pq-tag { background: rgba(242,86,35,.12); border: 1px solid rgba(242,86,35,.2); color: var(--or); border-radius: 100px; padding: 5px 12px; font-size: 10px; font-weight: 600; letter-spacing: 0.08em; }
.servicos { background: var(--bk); padding: 110px 52px; }
.svc-inner { max-width: 1200px; margin: 0 auto; }
.svc-top { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; align-items: end; margin-bottom: 56px; }
.svc-h2 { font-family: 'Playfair Display', serif; font-size: clamp(38px,3.8vw,58px); font-weight: 900; line-height: 1.05; letter-spacing: -1.5px; color: #fff; }
.svc-h2 em { font-style: italic; color: var(--or); }
.svc-intro { font-size: 14px; font-weight: 300; color: rgba(222,222,222,.4); line-height: 1.8; padding-top: 8px; }
.svc-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: 3px; }
.svc-card { background: rgba(255,255,255,.03); border: 1px solid rgba(255,255,255,.06); padding: 40px 32px; transition: background .25s, border-color .25s; cursor: default; position: relative; overflow: hidden; }
.svc-card::after { content:''; position:absolute; bottom:0; left:0; width:0; height:2px; background:var(--or); transition: width .4s; }
.svc-card:hover { background: rgba(255,255,255,.05); border-color: rgba(255,255,255,.1); }
.svc-card:hover::after { width:100%; }
.svc-n { font-size: 10px; font-weight: 700; letter-spacing: 0.18em; color: var(--or); margin-bottom: 20px; }
.svc-ico { font-size: 24px; margin-bottom: 16px; }
.svc-t { font-family: 'Playfair Display', serif; font-size: 19px; font-weight: 700; color: #fff; margin-bottom: 10px; }
.svc-d { font-size: 12px; font-weight: 300; color: rgba(222,222,222,.4); line-height: 1.8; }
.portfolio { background: var(--lg); padding: 110px 52px; }
.port-inner { max-width: 1200px; margin: 0 auto; }
.port-top { display: flex; align-items: flex-end; justify-content: space-between; margin-bottom: 44px; }
.port-h2 { font-family: 'Playfair Display', serif; font-size: clamp(38px,3.8vw,58px); font-weight: 900; line-height: 1.05; letter-spacing: -1.5px; color: var(--bk); }
.port-link { font-size: 11px; font-weight: 700; letter-spacing: 0.14em; text-transform: uppercase; color: var(--or); text-decoration: none; display: flex; align-items: center; gap: 6px; transition: gap .2s; }
.port-link:hover { gap: 12px; }
.pgrid { display: grid; grid-template-columns: 2fr 1fr 1fr; grid-template-rows: 280px 280px; gap: 3px; border-radius: 24px; overflow: hidden; }
.pc { position: relative; overflow: hidden; cursor: pointer; background: var(--dg); }
.pc.tall { grid-row: span 2; }
.pc-bg { position: absolute; inset: 0; transition: transform .6s ease; }
.pc:hover .pc-bg { transform: scale(1.05); }
.pc1 .pc-bg { background: linear-gradient(145deg, #2c2c2c, #0e0e0e); }
.pc1 .pc-bg::after { content:''; position:absolute;inset:0;background:radial-gradient(circle at 30% 70%,rgba(242,86,35,.22),transparent 60%); }
.pc2 .pc-bg { background: linear-gradient(145deg, #242424, #0a0a0a); }
.pc2 .pc-bg::after { content:''; position:absolute;inset:0;background:radial-gradient(circle at 75% 25%,rgba(242,86,35,.18),transparent 55%); }
.pc3 .pc-bg { background: linear-gradient(200deg, #1c1c1c, #080808); }
.pc4 .pc-bg { background: linear-gradient(145deg, #282828, #101010); }
.pc5 .pc-bg { background: linear-gradient(165deg, #202020, #0c0c0c); }
.pc5 .pc-bg::after { content:''; position:absolute;inset:0;background:radial-gradient(circle at 50% 60%,rgba(242,86,35,.15),transparent 65%); }
.pc-ov { position: absolute; inset: 0; background: linear-gradient(to top, rgba(23,23,23,.94) 0%, transparent 55%); opacity: 0; transition: opacity .35s; }
.pc:hover .pc-ov { opacity: 1; }
.pc-info { position: absolute; bottom: 0; left: 0; right: 0; padding: 24px; transform: translateY(8px); opacity: 0; transition: all .3s; }
.pc:hover .pc-info { transform: translateY(0); opacity: 1; }
.pc-cat { font-size: 9px; font-weight: 700; letter-spacing: 0.2em; text-transform: uppercase; color: var(--or); margin-bottom: 4px; }
.pc-title { font-family: 'Playfair Display', serif; font-size: 17px; font-weight: 700; color: #fff; }
.processo { background: var(--or); padding: 110px 52px; }
.proc-inner { max-width: 1200px; margin: 0 auto; }
.proc-tag { font-size: 10px; font-weight: 700; letter-spacing: 0.28em; text-transform: uppercase; color: rgba(255,255,255,.55); margin-bottom: 16px; display: flex; align-items: center; gap: 10px; }
.proc-tag::before { content:''; width:22px; height:1.5px; background:rgba(255,255,255,.4); }
.proc-h2 { font-family: 'Playfair Display', serif; font-size: clamp(38px,3.8vw,58px); font-weight: 900; line-height: 1.05; letter-spacing: -1.5px; color: #fff; margin-bottom: 56px; }
.steps { display: grid; grid-template-columns: repeat(4,1fr); gap: 3px; }
.step { background: rgba(0,0,0,.1); padding: 40px 30px; transition: background .25s; }
.steps .step:first-child { border-radius: 20px 0 0 20px; }
.steps .step:last-child { border-radius: 0 20px 20px 0; }
.step:hover { background: rgba(0,0,0,.2); }
.step-n { font-family: 'Playfair Display', serif; font-size: 60px; font-weight: 900; color: rgba(255,255,255,.12); line-height: 1; letter-spacing: -2px; margin-bottom: 2px; }
.step-t { font-size: 15px; font-weight: 600; color: #fff; margin: 10px 0 10px; }
.step-d { font-size: 12px; font-weight: 300; color: rgba(255,255,255,.6); line-height: 1.8; }
.cta-sec { background: var(--bk); padding: 130px 52px; text-align: center; position: relative; overflow: hidden; }
.cta-sec::before { content: '"'; position: absolute; font-family: 'Playfair Display', serif; font-size: 40vw; font-weight: 900; color: rgba(242,86,35,.04); top: 50%; left: 50%; transform: translate(-50%,-50%); line-height: 1; pointer-events: none; }
.cta-tag { font-size: 10px; font-weight: 700; letter-spacing: 0.28em; text-transform: uppercase; color: var(--or); margin-bottom: 20px; display: flex; align-items: center; justify-content: center; gap: 10px; }
.cta-tag::before,.cta-tag::after { content:''; width:22px; height:1.5px; background:var(--or); }
.cta-h2 { font-family: 'Playfair Display', serif; font-size: clamp(48px,6vw,88px); font-weight: 900; line-height: 0.97; letter-spacing: -2.5px; color: #fff; margin-bottom: 20px; position: relative; }
.cta-h2 em { font-style: italic; color: var(--or); }
.cta-p { font-size: 14px; font-weight: 300; color: rgba(222,222,222,.4); max-width: 440px; margin: 0 auto 44px; line-height: 1.8; position: relative; }
.btn-cta { display: inline-block; text-decoration: none; background: var(--or); color: #fff; padding: 16px 48px; border-radius: 100px; font-family: 'Sora', sans-serif; font-size: 13px; font-weight: 700; letter-spacing: 0.04em; transition: transform .2s, box-shadow .2s; position: relative; }
.btn-cta:hover { transform: translateY(-3px); box-shadow: 0 16px 44px rgba(242,86,35,.4); }
footer { background: #0e0e0e; border-top: 1px solid rgba(255,255,255,.05); padding: 40px 52px; display: flex; align-items: center; justify-content: space-between; }
.ft-logo img { height: 18px; filter: brightness(0) invert(1); opacity: .3; }
.ft-links { display: flex; gap: 32px; list-style: none; }
.ft-links a { color: rgba(222,222,222,.25); text-decoration: none; font-size: 11px; font-weight: 500; transition: color .2s; }
.ft-links a:hover { color: var(--or); }
.ft-copy { font-size: 11px; color: rgba(255,255,255,.15); }
.rv { opacity: 0; transform: translateY(28px); transition: opacity .8s ease, transform .8s ease; }
.rv.on { opacity: 1; transform: translateY(0); }
.rv2 { opacity: 0; transform: translateY(28px); transition: opacity .8s .15s ease, transform .8s .15s ease; }
.rv2.on { opacity: 1; transform: translateY(0); }

/* ── PORTFOLIO VIDEO CARD ── */
.pc-video {
position: absolute;
inset: 0;
width: 100%;
height: 100%;
border: none;
display: block;
}

@media (max-width: 1024px) {
nav { padding: 0 28px; }
.hero { grid-template-columns: 1fr; }
.hero-r { display: none; }
.hero-l { min-height: calc(100vh - 72px); padding: 48px 28px 120px; }
.hero-h1 { font-size: 64px; }
.pq-grid { grid-template-columns: 1fr 1fr; }
.pq-grid .pq-card:first-child { border-radius: 24px 0 0 0; }
.pq-grid .pq-card:last-child { grid-column: span 2; border-radius: 0 0 24px 24px; }
.svc-grid { grid-template-columns: 1fr 1fr; }
.pgrid { grid-template-columns: 1fr 1fr; grid-template-rows: 220px 220px 220px; }
.pc.tall { grid-row: span 1; }
.steps { grid-template-columns: 1fr 1fr; gap: 3px; }
.steps .step:first-child { border-radius: 20px 0 0 0; }
.steps .step:last-child { border-radius: 0 0 20px 0; }
.steps .step:nth-child(2) { border-radius: 0 20px 0 0; }
.steps .step:nth-child(3) { border-radius: 0 0 0 20px; }
.svc-top { grid-template-columns: 1fr; gap: 16px; }
.paraquem, .servicos, .portfolio, .processo, .cta-sec { padding: 80px 28px; }
}
@media (max-width: 768px) {
nav { padding: 0 20px; height: 64px; }
.nav-menu { display: none; }
.nav-cta { padding: 9px 18px; font-size: 11px; }
.hero { grid-template-columns: 1fr; }
.hero-l { padding: 44px 20px 110px; min-height: calc(100vh - 64px); }
.hero-badge { left: 20px; top: 28px; font-size: 9px; padding: 6px 12px; }
.hero-h1 { font-size: clamp(48px, 12vw, 64px); letter-spacing: -1.5px; }
.hero-p { font-size: 13px; max-width: 100%; }
.hero-btns { flex-direction: column; align-items: flex-start; gap: 10px; }
.btn-w, .btn-gl { width: 100%; justify-content: center; padding: 14px 20px; }
.hero-pills { grid-template-columns: repeat(2,1fr); }
.hero-pill { padding: 14px 16px; }
.pq-grid { grid-template-columns: 1fr; gap: 3px; }
.pq-grid .pq-card:first-child { border-radius: 20px 20px 0 0; }
.pq-grid .pq-card:last-child { grid-column: span 1; border-radius: 0 0 20px 20px; }
.pq-card { padding: 36px 24px; }
.svc-grid { grid-template-columns: 1fr; gap: 3px; }
.svc-card { padding: 32px 24px; border-radius: 0 !important; }
.svc-grid .svc-card:first-child { border-radius: 20px 20px 0 0 !important; }
.svc-grid .svc-card:last-child { border-radius: 0 0 20px 20px !important; }
.port-h2 { font-size: clamp(32px,8vw,44px); }
.port-top { flex-direction: column; align-items: flex-start; gap: 16px; margin-bottom: 28px; }
.pgrid { grid-template-columns: 1fr; grid-template-rows: repeat(5, 220px); border-radius: 20px; }
.pc.tall { grid-row: span 1; }
.pc:first-child { border-radius: 20px 20px 0 0; }
.pc:last-child { border-radius: 0 0 20px 20px; }
.proc-h2 { font-size: clamp(32px,8vw,44px); margin-bottom: 32px; }
.steps { grid-template-columns: 1fr; gap: 3px; }
.steps .step { border-radius: 0 !important; padding: 32px 24px; }
.steps .step:first-child { border-radius: 20px 20px 0 0 !important; }
.steps .step:last-child { border-radius: 0 0 20px 20px !important; }
.cta-sec { padding: 80px 20px; }
.cta-h2 { font-size: clamp(38px,10vw,56px); letter-spacing: -1.5px; }
.btn-cta { padding: 15px 36px; font-size: 13px; width: 100%; text-align: center; }
footer { flex-direction: column; gap: 24px; text-align: center; padding: 36px 20px; }
.ft-links { gap: 20px; flex-wrap: wrap; justify-content: center; }
}
@media (max-width: 400px) {
.hero-h1 { font-size: 42px; }
.nav-cta { display: none; }
}
.hamburger { display: none; flex-direction: column; gap: 5px; background: none; border: none; cursor: pointer; padding: 4px; }
.hamburger span { display: block; width: 24px; height: 2px; background: var(–lg); border-radius: 2px; transition: all .3s; }
.hamburger.open span:nth-child(1) { transform: rotate(45deg) translate(5px,5px); }
.hamburger.open span:nth-child(2) { opacity: 0; }
.hamburger.open span:nth-child(3) { transform: rotate(-45deg) translate(5px,-5px); }
.mobile-menu { display: none; position: fixed; top: 64px; left: 0; right: 0; bottom: 0; background: rgba(23,23,23,0.98); backdrop-filter: blur(24px); z-index: 998; flex-direction: column; justify-content: center; align-items: center; opacity: 0; transition: opacity .3s; }
.mobile-menu.open { display: flex; opacity: 1; }
.mobile-menu ul { list-style: none; text-align: center; display: flex; flex-direction: column; gap: 8px; }
.mobile-menu a { font-family: ‘Playfair Display’, serif; font-size: 36px; font-weight: 700; color: rgba(222,222,222,0.7); text-decoration: none; display: block; padding: 10px 0; transition: color .2s; }
.mobile-menu a:last-child { font-family: ‘Sora’, sans-serif; font-size: 14px; font-weight: 700; background: var(–or); color: #fff; padding: 14px 36px; border-radius: 100px; margin-top: 12px; letter-spacing: 0.04em; }
.mobile-menu a:hover { color: var(–or); }
@media (max-width: 768px) { .hamburger { display: flex; } }
</style>

</head>
<body>

<nav>
  <div class="nav-logo"><img src="https://i.imgur.com/placeholder.png" alt="JOW MAKER"></div>
  <ul class="nav-menu">
    <li><a href="#paraquem">Para quem</a></li>
    <li><a href="#servicos">Serviços</a></li>
    <li><a href="#portfolio">Portfólio</a></li>
    <li><a href="#processo">Processo</a></li>
    <li><a href="#mediakit">Media Kit</a></li>
  </ul>
  <button class="nav-cta" onclick="window.open('https://wa.me/5524993095410','_blank')">Solicitar orçamento</button>
  <button class="hamburger" id="hamburger" aria-label="Menu">
    <span></span><span></span><span></span>
  </button>
  <div class="mobile-menu" id="mobileMenu">
    <ul>
      <li><a href="#paraquem" onclick="closeMenu()">Para quem</a></li>
      <li><a href="#servicos" onclick="closeMenu()">Serviços</a></li>
      <li><a href="#portfolio" onclick="closeMenu()">Portfólio</a></li>
      <li><a href="#processo" onclick="closeMenu()">Processo</a></li>
      <li><a href="#mediakit" onclick="closeMenu()">Media Kit</a></li>
      <li><a href="https://wa.me/5524993095410" target="_blank" onclick="closeMenu()">Solicitar orçamento</a></li>
    </ul>
  </div>
</nav>

<div class="hero">
  <div class="hero-l">
    <div class="hero-badge"><span class="badge-dot"></span>Produtora Audiovisual Premium</div>
    <h1 class="hero-h1">A sua história<br>merece ser<br><em>vista.</em></h1>
    <p class="hero-p">Produzimos vídeos que impressionam, emocionam e ficam na memória. Para marcas que querem autoridade, eventos que merecem ser eternizados e criadores que querem crescer de verdade.</p>
    <div class="hero-btns">
      <button class="btn-w" onclick="document.getElementById('portfolio').scrollIntoView({behavior:'smooth'})">Ver portfólio</button>
      <button class="btn-gl"><span>▶</span> Showreel</button>
    </div>
    <div class="hero-pills">
      <div class="hero-pill"><div class="hp-num">#01</div><div class="hp-name">Marcas</div></div>
      <div class="hero-pill"><div class="hp-num">#02</div><div class="hp-name">Eventos</div></div>
      <div class="hero-pill"><div class="hp-num">#03</div><div class="hp-name">Criadores</div></div>
      <div class="hero-pill"><div class="hp-num">#04</div><div class="hp-name">Artistas</div></div>
    </div>
  </div>
  <div class="hero-r">
    <div class="hero-quote">
      <div class="hq-title">Qualidade que fala por si mesma.</div>
      <div class="hq-sub">Equipamentos de cinema, equipe especializada e olhar artístico em cada projeto. Não entregamos só arquivo — entregamos a versão mais impressionante da sua história.</div>
    </div>
    <div class="hero-reel">
      <div class="reel-btn">▶</div>
      <div class="reel-lbl">SHOWREEL JOW MAKER 2025</div>
    </div>
    <div class="hero-stats">
      <div class="hstat"><div class="hstat-n">200+</div><div class="hstat-l">Projetos</div></div>
      <div class="hstat"><div class="hstat-n">8</div><div class="hstat-l">Anos</div></div>
      <div class="hstat"><div class="hstat-n">98%</div><div class="hstat-l">Satisfação</div></div>
    </div>
  </div>
</div>

<div class="mq">
  <div class="mq-track">
    <span class="mq-item">FILMAGEM PROFISSIONAL </span>
    <span class="mq-item">EDIÇÃO CINEMATOGRÁFICA </span>
    <span class="mq-item">CASAMENTOS & EVENTOS </span>
    <span class="mq-item">PUBLICIDADE </span>
    <span class="mq-item">VIDEOCLIPE </span>
    <span class="mq-item">STORYMAKER </span>
    <span class="mq-item">SOCIAL MEDIA </span>
    <span class="mq-item">COLOR GRADING </span>
    <span class="mq-item">FILMAGEM PROFISSIONAL </span>
    <span class="mq-item">EDIÇÃO CINEMATOGRÁFICA </span>
    <span class="mq-item">CASAMENTOS & EVENTOS </span>
    <span class="mq-item">PUBLICIDADE </span>
    <span class="mq-item">VIDEOCLIPE </span>
    <span class="mq-item">STORYMAKER </span>
    <span class="mq-item">SOCIAL MEDIA </span>
    <span class="mq-item">COLOR GRADING </span>
  </div>
</div>

<div class="paraquem" id="paraquem">
  <div class="pq-inner">
    <div class="rv">
      <div class="sec-tag">Feito para você</div>
      <h2 class="pq-h2">Quem a JOW MAKER<br>atende.</h2>
    </div>
    <div class="pq-grid rv2">
      <div class="pq-card">
        <div class="pq-num">01</div>
        <div class="pq-icon"></div>
        <div class="pq-title">Marcas & Empresas</div>
        <div class="pq-desc">Sua empresa tem uma história que o texto não consegue contar. Criamos filmes institucionais, campanhas publicitárias e conteúdo digital que posicionam, vendem e constroem autoridade de verdade.</div>
        <div class="pq-tags"><span class="pq-tag">Institucional</span><span class="pq-tag">Publicidade</span><span class="pq-tag">Social Media</span></div>
      </div>
      <div class="pq-card">
        <div class="pq-num">02</div>
        <div class="pq-icon"></div>
        <div class="pq-title">Eventos</div>
        <div class="pq-desc">Casamentos, festas de 15 anos e shows são momentos únicos. Entregamos cobertura cinematográfica completa, o tipo de memória que você vai querer reviver anos depois como se fosse hoje.</div>
        <div class="pq-tags"><span class="pq-tag">Casamentos</span><span class="pq-tag">15 anos</span><span class="pq-tag">Shows</span></div>
      </div>
      <div class="pq-card">
        <div class="pq-num">03</div>
        <div class="pq-icon"></div>
        <div class="pq-title">Criadores de Conteúdo</div>
        <div class="pq-desc">Você sabe criar. Nós damos a estrutura técnica e criativa para o seu conteúdo alcançar outro nível. Reels, videoclipes, Storymaker e Social Media com qualidade que impressiona desde o primeiro frame.</div>
        <div class="pq-tags"><span class="pq-tag">Reels</span><span class="pq-tag">Videoclipe</span><span class="pq-tag">Storymaker</span></div>
      </div>
    </div>
  </div>
</div>

<div class="servicos" id="servicos">
  <div class="svc-inner">
    <div class="svc-top rv">
      <div>
        <div class="sec-tag" style="color:var(--or);">Do conceito à entrega</div>
        <h2 class="svc-h2">Produção<br>sem<br><em>meio-termo.</em></h2>
      </div>
      <p class="svc-intro">Cada serviço foi pensado para gerar impacto real. Não existe projeto pequeno quando o resultado precisa impressionar.</p>
    </div>
    <div class="svc-grid rv2">
      <div class="svc-card"><div class="svc-n">01</div><div class="svc-ico"></div><div class="svc-t">Filmagem</div><div class="svc-d">Câmeras cinema, drones, estabilizadores e iluminação profissional. Cada frame pensado para comunicar o que sua marca precisa dizer, com zero espaço para o amador.</div></div>
      <div class="svc-card"><div class="svc-n">02</div><div class="svc-ico">️</div><div class="svc-t">Edição & Color Grading</div><div class="svc-d">Montagem que prende, color grading que cria identidade e finalização em qualquer formato. Do Reel de 15 segundos ao filme de 30 minutos.</div></div>
      <div class="svc-card"><div class="svc-n">03</div><div class="svc-ico"></div><div class="svc-t">Eventos</div><div class="svc-d">Casamentos, festas de 15 anos e shows merecem mais do que foto borrada e vídeo tremido. Entregamos cobertura cinematográfica completa.</div></div>
      <div class="svc-card"><div class="svc-n">04</div><div class="svc-ico"></div><div class="svc-t">Publicidade</div><div class="svc-d">Anúncios que param o feed. Filmes institucionais que posicionam. Campanhas que vendem. Produção publicitária com visão estratégica de quem entende de resultado.</div></div>
      <div class="svc-card"><div class="svc-n">05</div><div class="svc-ico"></div><div class="svc-t">Videoclipe</div><div class="svc-d">Sua música merece uma visual identity à altura. Direção criativa, produção de set e edição que amplificam a emoção da música e constroem a imagem do artista.</div></div>
      <div class="svc-card"><div class="svc-n">06</div><div class="svc-ico"></div><div class="svc-t">Storymaker & Social Media</div><div class="svc-d">Reels, Stories, Shorts e conteúdo para tráfego pago, criados por quem entende de algoritmo e de estética. Presença digital consistente que engaja e converte todo dia.</div></div>
    </div>
  </div>
</div>

<div class="portfolio" id="portfolio">
  <div class="port-inner">
    <div class="port-top rv">
      <div>
        <div class="sec-tag">Nosso trabalho</div>
        <h2 class="port-h2">Trabalhos<br>selecionados.</h2>
      </div>
      <a href="#" class="port-link">Ver todos →</a>
    </div>
    <div class="pgrid rv2">
      <!-- CARD 1 — Vídeo YouTube em destaque -->
      <div class="pc tall pc1" style="background:#000; cursor:default;">
        <iframe
          class="pc-video"
          src="https://www.youtube.com/embed/Af68pasIZRY?rel=0&modestbranding=1&color=white"
          title="Showreel JOW MAKER 2025"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen>
        </iframe>
      </div>
      <div class="pc pc2" style="background:#000; cursor:default;">
        <iframe
          class="pc-video"
          src="https://www.youtube.com/embed/uUjSzV3qnqI?rel=0&modestbranding=1&color=white"
          title="Marketing Nutricional"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen>
        </iframe>
        <div class="pc-info" style="opacity:1; transform:translateY(0);">
          <div class="pc-cat">Marketing</div>
          <div class="pc-title">Marketing Nutricional</div>
        </div>
      </div>
      <div class="pc pc3">
        <div class="pc-bg"></div>
        <div class="pc-ov"></div>
        <div class="pc-info"><div class="pc-cat">Eventos</div><div class="pc-title">Casamento Silva & Lima</div></div>
      </div>
      <div class="pc pc4">
        <div class="pc-bg"></div>
        <div class="pc-ov"></div>
        <div class="pc-info"><div class="pc-cat">Institucional</div><div class="pc-title">Filme Corporativo</div></div>
      </div>
      <div class="pc pc5">
        <div class="pc-bg"></div>
        <div class="pc-ov"></div>
        <div class="pc-info"><div class="pc-cat">Social Media</div><div class="pc-title">Conteúdo Digital</div></div>
      </div>
    </div>
  </div>
</div>

<!-- ── CANVA APRESENTAÇÃO ── -->

<div id="mediakit" style="background:#111; padding: 110px 52px;">
  <div style="max-width:1200px; margin:0 auto;">
    <div class="sec-tag" style="color:var(--or); margin-bottom:16px;">Media Kit</div>
    <h2 style="font-family:'Playfair Display',serif; font-size:clamp(38px,3.8vw,58px); font-weight:900; letter-spacing:-1.5px; color:#fff; margin-bottom:44px; line-height:1.05;">
      Conheça a<br><em style="font-style:italic; color:var(--or);">JOW MAKER.</em>
    </h2>
    <div style="position:relative; width:100%; max-width:420px; margin:0 auto; border-radius:16px; overflow:hidden; box-shadow:0 24px 64px rgba(0,0,0,.6);">
      <div style="padding-top:281.11%; position:relative;">
        <iframe
          loading="lazy"
          style="position:absolute; width:100%; height:100%; top:0; left:0; border:none; padding:0; margin:0;"
          src="https://www.canva.com/design/DAGlsuI0xCU/Ad5XlIxe4RrZhvNjMjZaRA/view?embed"
          allowfullscreen allow="fullscreen">
        </iframe>
      </div>
    </div>
  </div>
</div>

<div class="processo" id="processo">
  <div class="proc-inner">
    <div class="rv">
      <div class="proc-tag">Nossa metodologia</div>
      <h2 class="proc-h2">Do briefing<br>à entrega perfeita.</h2>
    </div>
    <div class="steps rv2">
      <div class="step"><div class="step-n">01</div><div class="step-t">Diagnóstico</div><div class="step-d">Antes de ligar qualquer câmera, entendemos seu negócio, público-alvo e objetivo. O vídeo certo começa com a pergunta certa.</div></div>
      <div class="step"><div class="step-n">02</div><div class="step-t">Pré-produção</div><div class="step-d">Roteiro, storyboard, locações, casting e equipamentos. Cada detalhe mapeado, porque surpresa ruim no dia da gravação sai caro para todo mundo.</div></div>
      <div class="step"><div class="step-n">03</div><div class="step-t">Produção</div><div class="step-d">Equipe técnica afinada e direção criativa presente. Cada take tem propósito e cada hora no set gera resultado real.</div></div>
      <div class="step"><div class="step-n">04</div><div class="step-t">Entrega</div><div class="step-d">Edição, color grading, mixagem de áudio e exportação em todos os formatos. Revisões inclusas. Você aprova quando estiver 100% satisfeito.</div></div>
    </div>
  </div>
</div>

<div class="cta-sec" id="cta">
  <div class="cta-tag">Próximo passo</div>
  <h2 class="cta-h2">Pronto para um<br>vídeo que <em>impressiona?</em></h2>
  <p class="cta-p">Fale com a JOW MAKER e receba uma proposta personalizada em até 24h. Sem enrolação.</p>
  <a href="https://wa.me/5524993095410" target="_blank" rel="noopener" class="btn-cta">Solicitar orçamento</a>
</div>

<footer>
  <div class="ft-logo"><img src="https://i.imgur.com/placeholder.png" alt="JOW MAKER"></div>
  <ul class="ft-links">
    <li><a href="#">Instagram</a></li>
    <li><a href="#">YouTube</a></li>
    <li><a href="#">Contato</a></li>
  </ul>
  <div class="ft-copy">© 2025 JOW MAKER</div>
</footer>

<script>
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if(e.isIntersecting) { e.target.classList.add('on'); obs.unobserve(e.target); }
    });
  }, { threshold: 0.08 });
  document.querySelectorAll('.rv, .rv2').forEach(el => obs.observe(el));

  const ham = document.getElementById('hamburger');
  const mob = document.getElementById('mobileMenu');
  ham.addEventListener('click', () => {
    ham.classList.toggle('open');
    mob.classList.toggle('open');
    document.body.style.overflow = mob.classList.contains('open') ? 'hidden' : '';
  });
  function closeMenu() {
    ham.classList.remove('open');
    mob.classList.remove('open');
    document.body.style.overflow = '';
  }
</script>

</body>
</html>
