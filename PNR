<!doctype html>
<!--
  ⚡ ПРН Контроль — чек-лист пусконаладки объектов (ЭФИ · ТМ · АСКУЭ)
  Установка на iPhone: разместите этот файл как index.html по HTTPS (например, GitHub Pages),
  откройте ссылку в Safari → «Поделиться» → «На экран "Домой"» → «Добавить».
  Данные хранятся локально на устройстве (localStorage). Приложение работает без сборки и зависимостей.
-->
<html lang="ru">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>ПНР Контроль — ЭФИ, телемеханика, АСКУЭ</title>
<meta name="description" content="Чек-лист пусконаладочных работ по объектам: электрофизические измерения, телемеханика, АСКУЭ, ответственные лица. Объект закрывается и подсвечивается зелёным.">
<meta name="theme-color" content="#0B1220">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="ПНР">
<meta name="format-detection" content="telephone=no">
<link id="appleIcon" rel="apple-touch-icon" href="">
<link id="favicon" rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect width='100' height='100' rx='22' fill='%230B1220'/%3E%3Cpath d='M62 8 L20 58 H44 L37 92 L82 40 H56 L69 8 Z' fill='%233DDC84'/%3E%3C/svg%3E">
<link id="manifestLink" rel="manifest" href="">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Unbounded:wght@500;700;900&family=Manrope:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;600;700&display=swap" rel="stylesheet">
<style>
/* ============ ПАЛИТРА / БАЗА ============ */
:root{
  color-scheme:dark;
  --bg0:#070C16; --bg1:#0B1220;
  --surface:#111A2E; --surface2:#16223B; --field:#0D1526;
  --line:rgba(122,152,204,.16); --line2:rgba(122,152,204,.30);
  --ink:#EAF1FF; --dim:#9FB0CC; --faint:#66779A;
  --amber:#FFB224; --amber2:#FF8A00;
  --cyan:#2BD9FF;  --cyan2:#0EA5E9;
  --violet:#B78CFF;--violet2:#8B5CF6;
  --green:#3DDC84; --green2:#1FB865;
  --red:#FF5D5D;   --red2:#E23B3B;
  --magenta:#FF4FD8;
  --ease:cubic-bezier(.22,.9,.28,1);
  --f-head:'Unbounded',system-ui,sans-serif;
  --f-body:'Manrope',system-ui,-apple-system,sans-serif;
  --f-mono:'JetBrains Mono',ui-monospace,monospace;
}
*{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent}
[hidden]{display:none!important}
html{scroll-behavior:smooth}
html.lock{overflow:hidden}
body{
  font-family:var(--f-body);font-size:15px;line-height:1.45;color:var(--ink);
  background:linear-gradient(180deg,var(--bg1),var(--bg0) 70%);
  min-height:100vh;min-height:100dvh;overflow-x:hidden;
}
::selection{background:rgba(43,217,255,.28);color:#fff}
button{font-family:inherit;color:inherit;background:none;border:0;cursor:pointer;touch-action:manipulation}
input,select{font-family:inherit;touch-action:manipulation}
svg.ic{width:18px;height:18px;flex:none;display:block}
:focus-visible{outline:2px solid var(--cyan);outline-offset:2px;border-radius:8px}
.sr-only{position:absolute;width:1px;height:1px;overflow:hidden;clip:rect(0 0 0 0)}

/* скроллбары в стиле приложения */
::-webkit-scrollbar{width:10px;height:8px}
::-webkit-scrollbar-track{background:rgba(10,16,30,.6)}
::-webkit-scrollbar-thumb{background:linear-gradient(180deg,var(--cyan2),var(--violet2));border-radius:8px;border:2px solid #0B1220}
::-webkit-scrollbar-thumb:hover{background:linear-gradient(180deg,var(--cyan),var(--violet))}
*{scrollbar-width:thin;scrollbar-color:#3a5f8f #0a101e}

/* ============ ФОН: сетка, авроры, зерно ============ */
.bg{position:fixed;inset:0;z-index:0;pointer-events:none;overflow:hidden}
.bg-grid{position:absolute;inset:0;
  background-image:linear-gradient(rgba(148,170,210,.05) 1px,transparent 1px),linear-gradient(90deg,rgba(148,170,210,.05) 1px,transparent 1px);
  background-size:44px 44px;
  -webkit-mask-image:radial-gradient(120% 90% at 50% 0%,#000 30%,transparent 90%);
          mask-image:radial-gradient(120% 90% at 50% 0%,#000 30%,transparent 90%);
}
.aurora{position:absolute;width:60vmax;height:60vmax;border-radius:50%;filter:blur(90px);opacity:.55;will-change:transform}
.a-cyan{top:-28vmax;left:-18vmax;background:radial-gradient(circle,rgba(14,165,233,.20),transparent 65%);animation:drift1 46s var(--ease) infinite alternate}
.a-amber{bottom:-30vmax;right:-20vmax;background:radial-gradient(circle,rgba(255,138,0,.13),transparent 65%);animation:drift2 58s var(--ease) infinite alternate}
.a-violet{top:22%;right:-26vmax;background:radial-gradient(circle,rgba(139,92,246,.13),transparent 65%);animation:drift1 64s var(--ease) infinite alternate-reverse}
.a-green{bottom:-24vmax;left:12vmax;background:radial-gradient(circle,rgba(61,220,132,.22),transparent 62%);opacity:0;transition:opacity 1.2s ease}
@keyframes drift1{from{transform:translate(0,0) scale(1)}to{transform:translate(9vmax,7vmax) scale(1.12)}}
@keyframes drift2{from{transform:translate(0,0) scale(1.05)}to{transform:translate(-8vmax,-6vmax) scale(.95)}}
.grain{position:absolute;inset:0;opacity:.05;mix-blend-mode:overlay;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='160' height='160'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2'/%3E%3C/filter%3E%3Crect width='160' height='160' filter='url(%23n)' opacity='0.55'/%3E%3C/svg%3E")}
body.all-closed .a-green{filter:blur(80px)}

/* ============ ШАПКА ============ */
header{position:sticky;top:0;z-index:50;
  background:rgba(10,16,30,.78);backdrop-filter:blur(16px) saturate(150%);-webkit-backdrop-filter:blur(16px) saturate(150%);
  border-bottom:1px solid var(--line);transition:box-shadow .3s ease;
  padding-top:env(safe-area-inset-top);
}
header.scrolled{box-shadow:0 12px 40px -18px rgba(0,0,0,.85)}
.hwrap{max-width:1080px;margin:0 auto;padding:10px 16px 10px}
.hrow{display:flex;align-items:center;gap:10px}
.brand-row{padding-bottom:8px}
.brand{display:flex;align-items:center;gap:10px;min-width:0}
.brand-ic{width:36px;height:36px;flex:none;border-radius:11px;display:grid;place-items:center;
  background:linear-gradient(150deg,#15223C,#0D1526);border:1px solid var(--line2);
  box-shadow:0 0 18px rgba(61,220,132,.18), inset 0 0 12px rgba(43,217,255,.08)}
.brand-ic svg{width:20px;height:20px}
.brand-tx{min-width:0}
.brand-tx h1{font-family:var(--f-head);font-weight:900;font-size:clamp(14px,4vw,17px);letter-spacing:.3px;white-space:nowrap;
  background:linear-gradient(90deg,#EAF1FF 30%,#9BE8FF 70%,#B78CFF);-webkit-background-clip:text;background-clip:text;color:transparent}
.brand-tx p{font-family:var(--f-mono);font-size:9.5px;letter-spacing:1.4px;text-transform:uppercase;color:var(--faint);white-space:nowrap;margin-top:2px}
.hspace{flex:1}
.ring{position:relative;width:42px;height:42px;flex:none}
.ring svg{width:42px;height:42px;display:block}
.ring .rbg{fill:none;stroke:rgba(122,152,204,.18);stroke-width:4.5}
.ring .rfg{fill:none;stroke:url(#ringGrad);stroke-width:4.5;stroke-linecap:round;
  stroke-dasharray:106.8;stroke-dashoffset:106.8;transition:stroke-dashoffset 1s var(--ease) .25s}
.ring span{position:absolute;inset:0;display:grid;place-items:center;font-family:var(--f-mono);font-size:9.5px;font-weight:700;color:var(--dim)}
.ibtn{width:40px;height:40px;flex:none;display:grid;place-items:center;border-radius:11px;
  border:1px solid var(--line);background:rgba(22,34,59,.55);color:var(--dim);
  transition:color .2s,border-color .2s,box-shadow .25s,transform .15s,background .2s}
.ibtn:hover{color:var(--ink);border-color:rgba(43,217,255,.45);box-shadow:0 0 14px rgba(43,217,255,.18);transform:translateY(-1px)}
.ibtn:active{transform:scale(.94)}
.ibtn.sm{width:32px;height:32px;border-radius:9px}
.ibtn.sm svg{width:15px;height:15px}
.ibtn.act{width:36px;height:36px;border-radius:10px;background:transparent}
.ibtn.act svg{width:16px;height:16px}
.ibtn.danger:hover{color:var(--red);border-color:rgba(255,93,93,.5);box-shadow:0 0 14px rgba(255,93,93,.2)}
.btn-primary{display:inline-flex;align-items:center;gap:8px;height:40px;padding:0 16px;border-radius:12px;
  font-weight:800;font-size:13.5px;color:#1A1206;letter-spacing:.2px;
  background:linear-gradient(135deg,#FFC53D,#FF8A00 58%,#FF6A00);
  box-shadow:0 6px 22px -6px rgba(255,138,0,.55), inset 0 1px 0 rgba(255,255,255,.35);
  transition:filter .2s,transform .15s,box-shadow .25s}
.btn-primary:hover{filter:brightness(1.07);transform:translateY(-1px);box-shadow:0 10px 28px -6px rgba(255,138,0,.65)}
.btn-primary:active{transform:scale(.96)}
.btn-primary svg{width:16px;height:16px}
.search-row{padding-bottom:8px}
.search{position:relative;flex:1;min-width:0}
.search>svg{position:absolute;left:12px;top:50%;transform:translateY(-50%);width:16px;height:16px;color:var(--faint);pointer-events:none}
.search input{width:100%;height:42px;border-radius:12px;border:1px solid var(--line);
  background:rgba(13,21,38,.75);color:var(--ink);font-size:16px;font-weight:500;padding:0 40px 0 38px;
  transition:border-color .2s,box-shadow .2s}
.search input::placeholder{color:var(--faint)}
.search input:focus{outline:none;border-color:rgba(43,217,255,.55);box-shadow:0 0 0 3px rgba(43,217,255,.14)}
.search .ibtn{position:absolute;right:5px;top:50%;transform:translateY(-50%)}
.chips-row{gap:8px}
.chips{display:flex;gap:7px;flex:1;min-width:0;overflow-x:auto;padding-bottom:2px;scrollbar-width:none}
.chips::-webkit-scrollbar{height:4px}
.chips::-webkit-scrollbar-thumb{background:rgba(43,217,255,.35);border:0}
.chip-f{flex:none;display:inline-flex;align-items:center;gap:6px;height:34px;padding:0 12px;border-radius:999px;
  font-family:var(--f-mono);font-size:11.5px;font-weight:600;color:var(--dim);
  border:1px solid var(--line);background:rgba(22,34,59,.45);transition:all .2s}
.chip-f b{font-size:10.5px;font-weight:700;padding:1px 6px;border-radius:6px;background:rgba(122,152,204,.16);color:var(--dim)}
.chip-f:hover{border-color:var(--line2);color:var(--ink)}
.chip-f.active[data-filter="all"]{color:var(--cyan);border-color:rgba(43,217,255,.5);background:rgba(43,217,255,.12);box-shadow:0 0 14px rgba(43,217,255,.14)}
.chip-f.active[data-filter="all"] b{background:rgba(43,217,255,.2);color:var(--cyan)}
.chip-f.active[data-filter="open"]{color:var(--amber);border-color:rgba(255,178,36,.5);background:rgba(255,178,36,.12);box-shadow:0 0 14px rgba(255,178,36,.14)}
.chip-f.active[data-filter="open"] b{background:rgba(255,178,36,.2);color:var(--amber)}
.chip-f.active[data-filter="closed"]{color:var(--green);border-color:rgba(61,220,132,.5);background:rgba(61,220,132,.12);box-shadow:0 0 14px rgba(61,220,132,.16)}
.chip-f.active[data-filter="closed"] b{background:rgba(61,220,132,.2);color:var(--green)}
.sort{flex:none}
.sort select{appearance:none;-webkit-appearance:none;height:34px;border-radius:10px;border:1px solid var(--line);
  background:rgba(22,34,59,.55) url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='14' height='14' viewBox='0 0 24 24' fill='none' stroke='%239FB0CC' stroke-width='2.4' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E") no-repeat right 9px center;
  color:var(--dim);font-size:12px;font-weight:700;padding:0 28px 0 11px;cursor:pointer;transition:border-color .2s,color .2s}
.sort select:hover{border-color:var(--line2);color:var(--ink)}
.sort select:focus{outline:none;border-color:rgba(43,217,255,.55)}

/* ============ КОНТЕНТ ============ */
.wrap{max-width:1080px;margin:0 auto;padding:0 16px;position:relative;z-index:2}
main{padding-top:14px;padding-bottom:130px}
.banner{display:flex;align-items:center;gap:12px;padding:12px 14px;margin-bottom:14px;border-radius:16px;
  border:1px solid rgba(43,217,255,.35);
  background:linear-gradient(120deg,rgba(43,217,255,.12),rgba(139,92,246,.10) 55%,rgba(61,220,132,.10));
  box-shadow:0 8px 30px -14px rgba(43,217,255,.35);animation:cardIn .6s var(--ease) .15s backwards}
.banner-ic{width:38px;height:38px;flex:none;border-radius:11px;display:grid;place-items:center;color:var(--cyan);
  background:rgba(43,217,255,.12);border:1px solid rgba(43,217,255,.35)}
.banner-tx{flex:1;min-width:0}
.banner-tx b{display:block;font-size:13.5px;font-weight:800}
.banner-tx p{font-size:11.5px;color:var(--dim);margin-top:1px}
.btn-ghost{display:inline-flex;align-items:center;gap:7px;height:36px;padding:0 14px;border-radius:10px;
  border:1px solid var(--line2);color:var(--dim);font-size:12.5px;font-weight:700;background:rgba(22,34,59,.4);
  transition:all .2s}
.btn-ghost:hover{color:var(--ink);border-color:rgba(43,217,255,.5);box-shadow:0 0 12px rgba(43,217,255,.15)}
.btn-ghost:active{transform:scale(.96)}
.btn-ghost svg{width:15px;height:15px}
.btn-sm{height:32px;padding:0 11px;font-size:11.5px}

.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(min(340px,100%),1fr));gap:14px}

/* ---- карточка объекта ---- */
.card{position:relative;min-width:0;padding:16px;border-radius:18px;overflow:hidden;
  background:linear-gradient(160deg,#141F38,#0F1728 70%);
  border:1px solid var(--line);
  box-shadow:0 10px 30px -18px rgba(0,0,0,.8);
  transition:opacity .55s var(--ease) var(--d,0ms),transform .55s var(--ease) var(--d,0ms),
             border-color .25s,box-shadow .3s,background .4s}
.card::before{content:'';position:absolute;left:0;right:0;top:0;height:2px;opacity:.55;
  background:linear-gradient(90deg,transparent,rgba(43,217,255,.6),rgba(183,140,255,.5),transparent)}
.card.settled{transition:transform .25s var(--ease),border-color .25s,box-shadow .3s,background .4s,opacity .3s}
.card.settled:hover{transform:translateY(-2px);border-color:var(--line2);box-shadow:0 16px 40px -18px rgba(0,0,0,.9),0 0 24px rgba(43,217,255,.07)}
.card.pre{opacity:0;transform:translateY(18px) scale(.985)}
.card.pre.in{opacity:1;transform:none}
.card.pop-in{animation:popIn .45s var(--ease) backwards}
@keyframes popIn{from{opacity:0;transform:scale(.94)}to{opacity:1;transform:none}}
@keyframes cardIn{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:none}}
.card-top{display:flex;align-items:flex-start;gap:10px}
.card-name{flex:1;min-width:0;font-family:var(--f-head);font-weight:700;font-size:clamp(14.5px,2.3vw,17px);
  line-height:1.4;letter-spacing:.2px;overflow-wrap:anywhere}
.status-badge{flex:none;display:inline-flex;align-items:center;gap:6px;margin-top:2px;
  font-family:var(--f-mono);font-size:10px;font-weight:700;letter-spacing:1.2px;text-transform:uppercase;
  padding:5px 9px;border-radius:8px;white-space:nowrap}
.status-badge .bi{width:11px;height:11px}
.b-open{color:var(--amber);background:rgba(255,178,36,.1);border:1px solid rgba(255,178,36,.38)}
.b-open .dot{width:6px;height:6px;border-radius:50%;background:var(--amber);animation:pulse 2s ease infinite}
@keyframes pulse{0%,100%{box-shadow:0 0 0 0 rgba(255,178,36,.5)}50%{box-shadow:0 0 0 5px rgba(255,178,36,0)}}
.b-closed{color:#0E2417;background:linear-gradient(135deg,#4ADE80,#22C55E);border:1px solid rgba(61,220,132,.7);
  box-shadow:0 0 16px rgba(61,220,132,.35)}
.card-chips{display:flex;flex-wrap:wrap;gap:6px;margin-top:9px}
.chip{display:inline-flex;align-items:center;gap:5px;font-family:var(--f-mono);font-size:10.5px;font-weight:600;
  padding:4px 8px;border-radius:7px;border:1px solid var(--line);background:rgba(22,34,59,.55);color:var(--dim)}
.chip svg{width:11px;height:11px}
.chip-kind{color:var(--cyan);border-color:rgba(43,217,255,.35);background:rgba(43,217,255,.08)}
.chip-num{color:var(--faint)}
.chip-deadline.soon{color:var(--amber);border-color:rgba(255,178,36,.45);background:rgba(255,178,36,.1)}
.chip-deadline.over{color:var(--red);border-color:rgba(255,93,93,.5);background:rgba(255,93,93,.1)}
.chip-deadline.ok{color:var(--green);border-color:rgba(61,220,132,.45);background:rgba(61,220,132,.1)}
.works-label{font-family:var(--f-mono);font-size:10px;font-weight:700;letter-spacing:1.6px;text-transform:uppercase;
  color:var(--faint);margin:14px 0 8px}
.works-label.ok{color:var(--green)}
.works{display:flex;flex-direction:column;gap:8px}

/* ---- строка вида работ ---- */
.w-efi{--wc:#FFB224;--wcs:rgba(255,178,36,.13);--wcb:rgba(255,178,36,.4)}
.w-tm{--wc:#2BD9FF;--wcs:rgba(43,217,255,.12);--wcb:rgba(43,217,255,.4)}
.w-askue{--wc:#B78CFF;--wcs:rgba(183,140,255,.13);--wcb:rgba(183,140,255,.42)}
.work{position:relative;display:grid;grid-template-columns:26px 1fr auto;gap:10px;align-items:center;
  padding:10px 12px;border-radius:12px;cursor:pointer;user-select:none;-webkit-user-select:none;
  background:rgba(13,21,38,.6);border:1px solid rgba(122,152,204,.12);
  transition:background .3s,border-color .3s}
.work:hover{border-color:var(--line2)}
.work:active{background:rgba(22,34,59,.8)}
.work.done{background:linear-gradient(120deg,rgba(61,220,132,.1),rgba(61,220,132,.04));border-color:rgba(61,220,132,.32)}
.work-check{position:absolute;left:12px;top:12px;width:26px;height:26px;opacity:0;margin:0;pointer-events:none}
.cbox{width:26px;height:26px;border-radius:8px;display:grid;place-items:center;
  border:2px solid rgba(154,171,204,.45);background:#0B1322;transition:all .25s var(--ease)}
.cbox svg{width:100%;height:100%;opacity:0;transition:opacity .15s}
.cbox svg path{fill:none;stroke:#08130C;stroke-width:3.4;stroke-linecap:round;stroke-linejoin:round}
.work-check:checked~.cbox{background:linear-gradient(145deg,#4ADE80,#1FB865);border-color:var(--green);
  box-shadow:0 2px 12px rgba(61,220,132,.4)}
.work-check:checked~.cbox svg{opacity:1}
.work-check:focus-visible~.cbox{box-shadow:0 0 0 3px rgba(43,217,255,.35)}
.cbox.anim{animation:cpop .32s cubic-bezier(.3,1.6,.5,1)}
.cbox.anim svg path{stroke-dasharray:23;animation:draw .3s ease-out forwards}
@keyframes cpop{0%{transform:scale(1)}45%{transform:scale(1.16)}100%{transform:scale(1)}}
@keyframes draw{from{stroke-dashoffset:23}to{stroke-dashoffset:0}}
.wmain{min-width:0;display:block}
.wline{display:flex;flex-wrap:wrap;align-items:center;gap:6px}
.wcode{font-family:var(--f-mono);font-size:10.5px;font-weight:700;letter-spacing:.5px;padding:2px 7px;border-radius:6px;
  color:var(--wc);background:var(--wcs);border:1px solid var(--wcb)}
.wtitle{font-size:13px;font-weight:700;color:var(--ink)}
.wperson{display:flex;flex-wrap:wrap;align-items:center;gap:6px;margin-top:5px}
.avatar{width:22px;height:22px;flex:none;border-radius:50%;display:grid;place-items:center;
  font-family:var(--f-mono);font-size:9px;font-weight:700;color:var(--wc);background:var(--wcs);border:1px solid var(--wcb)}
.avatar.warn{color:var(--amber);background:rgba(255,178,36,.1);border:1px dashed rgba(255,178,36,.55)}
.pname{font-size:12.5px;font-weight:700;color:var(--ink);overflow-wrap:anywhere}
.pname.warn{color:var(--amber);font-style:italic;font-weight:600}
.prole{font-size:10.5px;color:var(--faint)}
.wmeta{display:flex;align-items:center;gap:4px;font-family:var(--f-mono);font-size:11.5px;font-weight:700;
  color:var(--green);white-space:nowrap}
.wmeta .mi{width:12px;height:12px}
.wait{font-size:10px;font-weight:600;letter-spacing:.6px;color:var(--faint);text-transform:uppercase}

/* ---- низ карточки ---- */
.card-foot{display:flex;align-items:center;gap:10px;margin-top:13px}
.prog{display:flex;gap:5px;flex:1;min-width:0}
.seg{height:6px;flex:1;border-radius:4px;background:rgba(148,170,210,.14);transition:background .4s,box-shadow .4s}
.seg.done{background:var(--wc);box-shadow:0 0 10px var(--wcs)}
.prog-label{font-family:var(--f-mono);font-size:11px;font-weight:700;color:var(--dim);white-space:nowrap}
.card-acts{display:flex;gap:4px}

/* ---- ЗАКРЫТЫЙ ОБЪЕКТ: зелёная подсветка ---- */
.card.closed{
  background:linear-gradient(150deg,rgba(61,220,132,.17),rgba(61,220,132,.05) 46%,rgba(15,26,32,.95));
  border-color:rgba(61,220,132,.55);
  box-shadow:0 12px 44px -14px rgba(61,220,132,.4),0 0 0 1px rgba(61,220,132,.12)}
.card.closed::before{opacity:1;background:linear-gradient(90deg,transparent,#3DDC84 30%,#A3F7BF 50%,#3DDC84 70%,transparent)}
.card.closed .card-name{color:#F2FFF7}
.card.closed .seg.done{background:linear-gradient(90deg,#3DDC84,#22C55E);box-shadow:0 0 10px rgba(61,220,132,.35)}
.card.closed .prog-label{color:var(--green)}
.card.settled.closed:hover{box-shadow:0 18px 54px -14px rgba(61,220,132,.55);border-color:rgba(61,220,132,.8)}
.card.just-closed{animation:closePulse 1.15s ease-out}
@keyframes closePulse{0%{box-shadow:0 0 0 0 rgba(61,220,132,.55)}100%{box-shadow:0 0 0 30px rgba(61,220,132,0)}}

/* ---- пустые состояния ---- */
.empty{text-align:center;padding:56px 20px;animation:cardIn .5s var(--ease) backwards}
.empty-ic{width:76px;height:76px;margin:0 auto 18px;border-radius:50%;display:grid;place-items:center;
  border:1.5px dashed var(--line2);color:var(--faint);background:rgba(22,34,59,.35)}
.empty-ic svg{width:30px;height:30px}
.empty-ic.ok{color:var(--green);border-color:rgba(61,220,132,.5);background:rgba(61,220,132,.08);box-shadow:0 0 30px rgba(61,220,132,.15)}
.empty h3{font-family:var(--f-head);font-weight:700;font-size:16px;margin-bottom:8px}
.empty p{font-size:13px;color:var(--dim);max-width:340px;margin:0 auto 18px}

/* ---- подвал ---- */
.foot{position:relative;z-index:2;display:flex;flex-wrap:wrap;align-items:center;gap:10px;
  padding-top:16px;padding-bottom:calc(22px + env(safe-area-inset-bottom));border-top:1px solid var(--line)}
.foot-l{display:flex;align-items:center;gap:7px;font-family:var(--f-mono);font-size:10.5px;color:var(--faint);flex:1;min-width:200px}
.foot-l svg{width:13px;height:13px;color:var(--green)}
.foot-r{display:flex;flex-wrap:wrap;gap:7px;align-items:center}
.fbtn{display:inline-flex;align-items:center;gap:6px;height:32px;padding:0 11px;border-radius:9px;
  font-family:var(--f-mono);font-size:10.5px;font-weight:600;color:var(--dim);
  border:1px solid var(--line);background:rgba(22,34,59,.4);transition:all .2s}
.fbtn:hover{color:var(--ink);border-color:var(--line2)}
.fbtn svg{width:13px;height:13px}
.installed-tag{display:inline-flex;align-items:center;gap:5px;font-family:var(--f-mono);font-size:10.5px;color:var(--green)}
.installed-tag svg{width:13px;height:13px}

/* ============ ШТОРКИ / МОДАЛКИ ============ */
.scrim{position:fixed;inset:0;z-index:100;display:flex;align-items:flex-end;justify-content:center;
  background:rgba(4,8,18,.72);backdrop-filter:blur(6px);-webkit-backdrop-filter:blur(6px);
  animation:fadeIn .22s ease}
.scrim.closing{animation:fadeOut .2s ease forwards}
@keyframes fadeIn{from{opacity:0}}
@keyframes fadeOut{to{opacity:0}}
.sheet{width:100%;max-width:560px;max-height:88vh;max-height:88dvh;display:flex;flex-direction:column;
  background:linear-gradient(180deg,#152139,#0F1728);border:1px solid var(--line2);border-bottom:0;
  border-radius:24px 24px 0 0;box-shadow:0 -20px 80px rgba(0,0,0,.7);
  animation:sheetUp .32s var(--ease)}
.scrim.closing .sheet{animation:sheetDown .2s ease forwards}
@keyframes sheetUp{from{transform:translateY(60px);opacity:0}to{transform:none;opacity:1}}
@keyframes sheetDown{to{transform:translateY(60px);opacity:0}}
.handle{width:44px;height:4px;border-radius:4px;margin:10px auto 0;flex:none;
  background:linear-gradient(90deg,var(--cyan2),var(--violet2));opacity:.6}
.sheet-head{display:flex;align-items:center;gap:10px;padding:14px 18px;border-bottom:1px solid var(--line);flex:none}
.sheet-title{flex:1;min-width:0}
.sheet-title h2{font-family:var(--f-head);font-weight:700;font-size:15.5px}
.sheet-title p{font-size:11.5px;color:var(--faint);margin-top:2px}
.sheet-body{overflow-y:auto;padding:18px;flex:1}
.sheet-foot{display:flex;align-items:center;gap:9px;padding:13px 18px calc(13px + env(safe-area-inset-bottom));
  border-top:1px solid var(--line);flex:none}
.sheet-foot .sp{flex:1}
@media(min-width:640px){
  .scrim{align-items:center;padding:24px}
  .sheet{border-radius:24px;border-bottom:1px solid var(--line2)}
  .handle{display:none}
}
.fld{display:block;margin-bottom:14px;min-width:0}
.lbl{display:flex;align-items:center;gap:6px;font-family:var(--f-mono);font-size:10px;font-weight:700;
  letter-spacing:1.4px;text-transform:uppercase;color:var(--dim);margin-bottom:6px}
.req{color:var(--amber)}
.fld input,.fld select{width:100%;height:44px;border-radius:12px;border:1px solid var(--line);
  background:var(--field);color:var(--ink);font-size:16px;font-weight:500;padding:0 12px;
  transition:border-color .2s,box-shadow .2s}
.fld select{appearance:none;-webkit-appearance:none;cursor:pointer;
  background:var(--field) url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='14' height='14' viewBox='0 0 24 24' fill='none' stroke='%239FB0CC' stroke-width='2.4' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E") no-repeat right 11px center}
.fld input::placeholder{color:var(--faint)}
.fld input:focus,.fld select:focus{outline:none;border-color:rgba(43,217,255,.55);box-shadow:0 0 0 3px rgba(43,217,255,.14)}
.fld input.invalid{border-color:rgba(255,93,93,.65);box-shadow:0 0 0 3px rgba(255,93,93,.15);animation:shake .35s ease}
@keyframes shake{0%,100%{transform:none}25%{transform:translateX(-5px)}75%{transform:translateX(5px)}}
.err{font-size:11px;color:var(--red);margin-top:5px;font-weight:600}
.frow{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.psec{margin-top:4px;padding-top:14px;border-top:1px dashed var(--line)}
.psec-h{font-family:var(--f-mono);font-size:10px;font-weight:700;letter-spacing:1.6px;text-transform:uppercase;color:var(--dim)}
.psec-p{font-size:11px;color:var(--faint);margin:3px 0 12px}
.pdot{width:8px;height:8px;border-radius:3px;background:var(--wc);box-shadow:0 0 8px var(--wcs);flex:none}
.btn-danger{display:inline-flex;align-items:center;gap:7px;height:40px;padding:0 14px;border-radius:11px;
  color:var(--red);border:1px solid rgba(255,93,93,.4);background:rgba(255,93,93,.08);font-size:12.5px;font-weight:700;transition:all .2s}
.btn-danger:hover{background:rgba(255,93,93,.16);box-shadow:0 0 14px rgba(255,93,93,.2)}
.btn-danger svg{width:15px;height:15px}
.btn-ghost.big{height:40px;padding:0 16px;font-size:13px}
.btn-primary.big{height:40px}

/* ---- шторка установки ---- */
.step{display:flex;gap:12px;align-items:flex-start;margin-bottom:15px}
.step-ic{width:42px;height:42px;flex:none;border-radius:12px;display:grid;place-items:center;
  background:rgba(22,34,59,.7);border:1px solid var(--line2);color:var(--cyan)}
.step-ic svg{width:20px;height:20px}
.step:nth-child(2) .step-ic{color:var(--amber)}
.step:nth-child(3) .step-ic{color:var(--violet)}
.step:nth-child(4) .step-ic{color:var(--green)}
.step-tx{min-width:0}
.step-tx b{display:block;font-size:13.5px;font-weight:800}
.step-tx p{font-size:12px;color:var(--dim);margin-top:2px}
.note{display:flex;gap:9px;align-items:flex-start;padding:11px 12px;border-radius:12px;font-size:12px;margin-top:10px}
.note svg{width:15px;height:15px;flex:none;margin-top:1px}
.note.ok{color:#BFF5D6;background:rgba(61,220,132,.1);border:1px solid rgba(61,220,132,.35)}
.note.ok svg{color:var(--green)}
.note.warn{color:#FFE2AE;background:rgba(255,178,36,.09);border:1px solid rgba(255,178,36,.35)}
.note.warn svg{color:var(--amber)}
.note.dim{color:var(--dim);background:rgba(22,34,59,.5);border:1px solid var(--line)}
.note.dim svg{color:var(--faint)}

/* ============ ТОСТЫ ============ */
.toasts{position:fixed;left:50%;transform:translateX(-50%);bottom:calc(16px + env(safe-area-inset-bottom));
  z-index:300;display:flex;flex-direction:column;gap:8px;width:min(440px,calc(100vw - 24px));pointer-events:none}
.toast{pointer-events:auto;position:relative;overflow:hidden;display:flex;align-items:center;gap:10px;
  padding:11px 12px;border-radius:14px;background:rgba(19,30,54,.96);border:1px solid var(--line2);
  box-shadow:0 14px 44px -10px rgba(0,0,0,.85);backdrop-filter:blur(10px);
  animation:toastIn .3s var(--ease)}
.toast.out{animation:toastOut .2s ease forwards}
@keyframes toastIn{from{opacity:0;transform:translateY(14px) scale(.97)}to{opacity:1;transform:none}}
@keyframes toastOut{to{opacity:0;transform:translateY(10px) scale(.97)}}
.t-ic{width:28px;height:28px;flex:none;border-radius:9px;display:grid;place-items:center}
.t-ic svg{width:15px;height:15px}
.t-success .t-ic{color:var(--green);background:rgba(61,220,132,.14);border:1px solid rgba(61,220,132,.4)}
.t-info .t-ic{color:var(--cyan);background:rgba(43,217,255,.12);border:1px solid rgba(43,217,255,.4)}
.t-warn .t-ic{color:var(--amber);background:rgba(255,178,36,.12);border:1px solid rgba(255,178,36,.4)}
.t-danger .t-ic{color:var(--red);background:rgba(255,93,93,.12);border:1px solid rgba(255,93,93,.4)}
.t-msg{flex:1;min-width:0;font-size:12.5px;font-weight:700;overflow-wrap:anywhere}
.t-act{flex:none;height:32px;padding:0 11px;border-radius:8px;font-family:var(--f-mono);font-size:10.5px;font-weight:700;
  letter-spacing:.8px;text-transform:uppercase;color:var(--cyan);border:1px solid rgba(43,217,255,.45);background:rgba(43,217,255,.1);transition:all .2s}
.t-act:hover{background:rgba(43,217,255,.2)}
.t-x{flex:none;width:28px;height:28px;display:grid;place-items:center;border-radius:8px;color:var(--faint)}
.t-x:hover{color:var(--ink)}
.t-x svg{width:13px;height:13px}
.t-bar{position:absolute;left:0;bottom:0;height:2px;width:100%;animation:shrink linear forwards}
.t-success .t-bar{background:linear-gradient(90deg,#3DDC84,#A3F7BF)}
.t-info .t-bar{background:linear-gradient(90deg,#0EA5E9,#2BD9FF)}
.t-warn .t-bar{background:linear-gradient(90deg,#FF8A00,#FFC53D)}
.t-danger .t-bar{background:linear-gradient(90deg,#E23B3B,#FF5D5D)}
@keyframes shrink{from{width:100%}to{width:0}}

/* ---- конфетти ---- */
#confetti{position:fixed;inset:0;z-index:250;pointer-events:none;overflow:hidden}
.cf{position:absolute;display:block;will-change:transform,opacity}

@media(max-width:560px){
  .brand-tx p{display:none}
  .hwrap{padding:8px 12px 8px}
  .wrap{padding:0 12px}
}
@media(max-width:420px){
  .btn-primary .bp-label{display:none}
  .btn-primary{padding:0 13px}
  .ring{width:38px;height:38px}
  .ring svg{width:38px;height:38px}
}
@media(prefers-reduced-motion:reduce){
  *,*::before,*::after{animation-duration:.01ms!important;animation-iteration-count:1!important;transition-duration:.01ms!important}
  html{scroll-behavior:auto}
}
</style>
</head>
<body>

<!-- SVG-спрайт -->
<svg width="0" height="0" style="position:absolute" aria-hidden="true">
  <defs>
    <linearGradient id="ringGrad" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0" stop-color="#2BD9FF"/><stop offset="1" stop-color="#3DDC84"/>
    </linearGradient>
    <linearGradient id="boltGrad" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0" stop-color="#FFC53D"/><stop offset=".55" stop-color="#FFB224"/><stop offset="1" stop-color="#3DDC84"/>
    </linearGradient>
  </defs>
  <symbol id="i-bolt" viewBox="0 0 24 24"><path d="M13.5 2 5 13.4h5.4L9 22l9.6-12.6h-5.5L15 2Z" fill="currentColor"/></symbol>
  <symbol id="i-bolt-g" viewBox="0 0 24 24"><path d="M13.5 2 5 13.4h5.4L9 22l9.6-12.6h-5.5L15 2Z" fill="url(#boltGrad)"/></symbol>
  <symbol id="i-plus" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14" fill="none" stroke="currentColor" stroke-width="2.6" stroke-linecap="round"/></symbol>
  <symbol id="i-search" viewBox="0 0 24 24"><circle cx="11" cy="11" r="7" fill="none" stroke="currentColor" stroke-width="2.2"/><path d="m20 20-3.8-3.8" stroke="currentColor" stroke-width="2.2" stroke-linecap="round"/></symbol>
  <symbol id="i-x" viewBox="0 0 24 24"><path d="M6 6l12 12M18 6 6 18" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"/></symbol>
  <symbol id="i-check" viewBox="0 0 24 24"><path d="m4.5 12.5 5 5L19.5 6.5" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/></symbol>
  <symbol id="i-pencil" viewBox="0 0 24 24"><path d="M4 20h4L20 8a2.4 2.4 0 0 0-4-4L4 16v4Z" fill="none" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/><path d="m13.5 6.5 4 4" stroke="currentColor" stroke-width="2"/></symbol>
  <symbol id="i-trash" viewBox="0 0 24 24"><path d="M4 7h16M9 7V5a1 1 0 0 1 1-1h4a1 1 0 0 1 1 1v2m3 0-1 13a1 1 0 0 1-1 1H8a1 1 0 0 1-1-1L6 7m4 4v6m4-6v6" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></symbol>
  <symbol id="i-cal" viewBox="0 0 24 24"><rect x="3.5" y="5" width="17" height="16" rx="2.5" fill="none" stroke="currentColor" stroke-width="2"/><path d="M3.5 10h17M8 2.5V6m8-3.5V6" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></symbol>
  <symbol id="i-share" viewBox="0 0 24 24"><path d="M12 3v12m0-12L8 7m4-4 4 4" fill="none" stroke="currentColor" stroke-width="2.1" stroke-linecap="round" stroke-linejoin="round"/><path d="M6 10H5a1.5 1.5 0 0 0-1.5 1.5v8A1.5 1.5 0 0 0 5 21h14a1.5 1.5 0 0 0 1.5-1.5v-8A1.5 1.5 0 0 0 19 10h-1" fill="none" stroke="currentColor" stroke-width="2.1" stroke-linecap="round"/></symbol>
  <symbol id="i-home-add" viewBox="0 0 24 24"><rect x="3.5" y="3.5" width="17" height="17" rx="4.5" fill="none" stroke="currentColor" stroke-width="2"/><path d="M12 8v8M8 12h8" stroke="currentColor" stroke-width="2.2" stroke-linecap="round"/></symbol>
  <symbol id="i-safari" viewBox="0 0 24 24"><circle cx="12" cy="12" r="9" fill="none" stroke="currentColor" stroke-width="2"/><path d="m15.5 8.5-2 5-5 2 2-5 5-2Z" fill="currentColor"/></symbol>
  <symbol id="i-phone" viewBox="0 0 24 24"><rect x="6.5" y="2.5" width="11" height="19" rx="2.5" fill="none" stroke="currentColor" stroke-width="2"/><path d="M10.5 18.5h3" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></symbol>
  <symbol id="i-download" viewBox="0 0 24 24"><path d="M12 3v11m0 0 4-4m-4 4-4-4M4 17v2.5A1.5 1.5 0 0 0 5.5 21h13a1.5 1.5 0 0 0 1.5-1.5V17" fill="none" stroke="currentColor" stroke-width="2.1" stroke-linecap="round" stroke-linejoin="round"/></symbol>
  <symbol id="i-refresh" viewBox="0 0 24 24"><path d="M20 12a8 8 0 1 1-2.3-5.6M20 3v4h-4" fill="none" stroke="currentColor" stroke-width="2.1" stroke-linecap="round" stroke-linejoin="round"/></symbol>
  <symbol id="i-alert" viewBox="0 0 24 24"><path d="M12 3 2.5 20h19L12 3Z" fill="none" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/><path d="M12 9.5v4.5" stroke="currentColor" stroke-width="2.2" stroke-linecap="round"/><circle cx="12" cy="17" r="1.2" fill="currentColor"/></symbol>
  <symbol id="i-copy" viewBox="0 0 24 24"><rect x="8.5" y="8.5" width="12" height="12" rx="2.5" fill="none" stroke="currentColor" stroke-width="2"/><path d="M15.5 5.5v-1a1 1 0 0 0-1-1h-10a1 1 0 0 0-1 1v10a1 1 0 0 0 1 1h1" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></symbol>
  <symbol id="i-dots" viewBox="0 0 24 24"><circle cx="12" cy="5" r="1.8" fill="currentColor"/><circle cx="12" cy="12" r="1.8" fill="currentColor"/><circle cx="12" cy="19" r="1.8" fill="currentColor"/></symbol>
</svg>

<!-- фон -->
<div class="bg" aria-hidden="true">
  <div class="bg-grid"></div>
  <div class="aurora a-cyan"></div>
  <div class="aurora a-amber"></div>
  <div class="aurora a-violet"></div>
  <div class="aurora a-green" id="auroraGreen"></div>
  <div class="grain"></div>
</div>

<!-- шапка -->
<header id="appHeader">
  <div class="hwrap">
    <div class="hrow brand-row">
      <div class="brand">
        <span class="brand-ic"><svg class="ic" aria-hidden="true"><use href="#i-bolt-g"/></svg></span>
        <div class="brand-tx">
          <h1>ПНР Контроль</h1>
          <p>пусконаладка · ЭФИ · ТМ · АСКУЭ</p>
        </div>
      </div>
      <div class="hspace"></div>
      <div class="ring" id="ringBox" title="Выполнено работ">
        <svg viewBox="0 0 44 44" aria-hidden="true">
          <circle class="rbg" cx="22" cy="22" r="17"/>
          <circle class="rfg" id="ringFg" cx="22" cy="22" r="17" transform="rotate(-90 22 22)"/>
        </svg>
        <span id="ringPct">0%</span>
      </div>
      <button type="button" id="btnInstallTop" class="ibtn" aria-label="Установить на iPhone">
        <svg class="ic"><use href="#i-share"/></svg>
      </button>
      <button type="button" id="btnAdd" class="btn-primary" aria-label="Добавить объект">
        <svg class="ic"><use href="#i-plus"/></svg><span class="bp-label">Объект</span>
      </button>
    </div>
    <div class="hrow search-row">
      <div class="search">
        <svg class="ic" aria-hidden="true"><use href="#i-search"/></svg>
        <input id="search" type="search" placeholder="Поиск: объект или ответственный…" autocomplete="off" aria-label="Поиск по объектам и ответственным">
        <button type="button" id="btnClearSearch" class="ibtn sm" aria-label="Очистить поиск" hidden>
          <svg class="ic"><use href="#i-x"/></svg>
        </button>
      </div>
    </div>
    <div class="hrow chips-row">
      <div class="chips" id="chips" role="group" aria-label="Фильтр объектов">
        <button type="button" class="chip-f active" data-filter="all" aria-pressed="true">Все <b id="cnt-all">0</b></button>
        <button type="button" class="chip-f" data-filter="open" aria-pressed="false">В работе <b id="cnt-open">0</b></button>
        <button type="button" class="chip-f" data-filter="closed" aria-pressed="false">Закрытые <b id="cnt-closed">0</b></button>
      </div>
      <label class="sort">
        <span class="sr-only">Сортировка</span>
        <select id="sortSel" aria-label="Сортировка объектов">
          <option value="status">Сначала в работе</option>
          <option value="name">По наименованию</option>
          <option value="deadline">По сроку</option>
          <option value="progress">По готовности</option>
        </select>
      </label>
    </div>
  </div>
</header>

<main id="main" class="wrap">
  <section id="installBanner" class="banner" hidden>
    <span class="banner-ic"><svg class="ic"><use href="#i-phone"/></svg></span>
    <div class="banner-tx">
      <b>Установите на iPhone</b>
      <p>Safari → «Поделиться» → «На экран „Домой“»</p>
    </div>
    <button type="button" class="btn-ghost btn-sm" data-act="banner-how">Инструкция</button>
    <button type="button" class="ibtn sm" data-act="banner-x" aria-label="Скрыть подсказку">
      <svg class="ic"><use href="#i-x"/></svg>
    </button>
  </section>

  <section id="list" class="grid"></section>
  <section id="empty" class="empty" hidden></section>
</main>

<footer class="wrap foot">
  <span class="foot-l"><svg class="ic"><use href="#i-bolt"/></svg>ПНР Контроль · данные хранятся на устройстве</span>
  <div class="foot-r">
    <span id="footInstalled" class="installed-tag" hidden><svg class="ic"><use href="#i-check"/></svg>Установлено</span>
    <button type="button" id="footInstall" class="fbtn"><svg class="ic"><use href="#i-share"/></svg>На iPhone</button>
    <button type="button" id="btnExport" class="fbtn"><svg class="ic"><use href="#i-download"/></svg>Экспорт</button>
    <button type="button" id="btnReset" class="fbtn"><svg class="ic"><use href="#i-refresh"/></svg>Демо</button>
  </div>
</footer>

<!-- шторка объекта -->
<div class="scrim" id="objScrim" hidden>
  <form class="sheet" id="objForm" role="dialog" aria-modal="true" aria-labelledby="objSheetTitle" novalidate>
    <div class="handle" aria-hidden="true"></div>
    <div class="sheet-head">
      <div class="sheet-title">
        <h2 id="objSheetTitle">Новый объект</h2>
        <p id="objSheetSub">Виды работ и ответственные лица</p>
      </div>
      <button type="button" class="ibtn sm" id="btnObjClose" aria-label="Закрыть">
        <svg class="ic"><use href="#i-x"/></svg>
      </button>
    </div>
    <div class="sheet-body">
      <label class="fld">
        <span class="lbl">Наименование объекта <span class="req">*</span></span>
        <input id="fName" type="text" placeholder="ПС 110/10 кВ «Заречная»" maxlength="90" autocomplete="off">
        <span class="err" id="fNameErr" hidden>Укажите наименование объекта (минимум 2 символа)</span>
      </label>
      <div class="frow">
        <label class="fld">
          <span class="lbl">Тип объекта</span>
          <select id="fKind">
            <option>ПС</option><option>РП</option><option>КТП</option><option>КРУН</option><option>ВЛ</option><option>ЗРУ</option>
          </select>
        </label>
        <label class="fld">
          <span class="lbl">Срок выполнения</span>
          <input id="fDeadline" type="date">
        </label>
      </div>
      <div class="psec">
        <div class="psec-h">Ответственные лица</div>
        <p class="psec-p">ФИО по каждому виду работ. Можно назначить позже.</p>
        <label class="fld w-efi">
          <span class="lbl"><span class="pdot"></span>ЭФИ · электрофизические измерения</span>
          <input id="fPerson-efi" type="text" placeholder="Соколов А. В." maxlength="60" autocomplete="off">
        </label>
        <label class="fld w-tm">
          <span class="lbl"><span class="pdot"></span>ТМ · телемеханика</span>
          <input id="fPerson-tm" type="text" placeholder="Мельникова И. П." maxlength="60" autocomplete="off">
        </label>
        <label class="fld w-askue">
          <span class="lbl"><span class="pdot"></span>АСКУЭ · учёт электроэнергии</span>
          <input id="fPerson-askue" type="text" placeholder="Гарипов Р. Н." maxlength="60" autocomplete="off">
        </label>
      </div>
    </div>
    <div class="sheet-foot">
      <button type="button" class="btn-danger" id="btnObjDelete" hidden>
        <svg class="ic"><use href="#i-trash"/></svg>Удалить
      </button>
      <span class="sp"></span>
      <button type="button" class="btn-ghost big" id="btnObjCancel">Отмена</button>
      <button type="submit" class="btn-primary big" id="btnObjSave">Добавить объект</button>
    </div>
  </form>
</div>

<!-- шторка установки -->
<div class="scrim" id="installScrim" hidden>
  <div class="sheet" role="dialog" aria-modal="true" aria-labelledby="installTitle">
    <div class="handle" aria-hidden="true"></div>
    <div class="sheet-head">
      <div class="sheet-title">
        <h2 id="installTitle">Установка на iPhone</h2>
        <p>4 шага — иконка ⚡ появится на рабочем столе</p>
      </div>
      <button type="button" class="ibtn sm" id="btnInstallClose" aria-label="Закрыть">
        <svg class="ic"><use href="#i-x"/></svg>
      </button>
    </div>
    <div class="sheet-body">
      <div class="note ok" id="installedNote" hidden>
        <svg class="ic"><use href="#i-check"/></svg>
        <span>Приложение уже установлено и работает в полноэкранном режиме.</span>
      </div>
      <div id="installSteps">
        <div class="step">
          <span class="step-ic"><svg class="ic"><use href="#i-safari"/></svg></span>
          <div class="step-tx"><b>1. Откройте эту страницу в Safari</b>
          <p>Если вы во встроенном браузере (Telegram, почта) — скопируйте ссылку и откройте её в Safari.</p></div>
        </div>
        <div class="step">
          <span class="step-ic"><svg class="ic"><use href="#i-share"/></svg></span>
          <div class="step-tx"><b>2. Нажмите «Поделиться»</b>
          <p>Кнопка с квадратом и стрелкой вверх — на нижней панели Safari.</p></div>
        </div>
        <div class="step">
          <span class="step-ic"><svg class="ic"><use href="#i-home-add"/></svg></span>
          <div class="step-tx"><b>3. Выберите «На экран „Домой“»</b>
          <p>Прокрутите список действий вниз; если пункта нет — нажмите «Изменить действия…».</p></div>
        </div>
        <div class="step">
          <span class="step-ic"><svg class="ic"><use href="#i-phone"/></svg></span>
          <div class="step-tx"><b>4. Нажмите «Добавить»</b>
          <p>Иконка «ПНР» появится на рабочем столе и будет открываться как обычное приложение, без адресной строки.</p></div>
        </div>
      </div>
      <div class="note ok">
        <svg class="ic"><use href="#i-check"/></svg>
        <span>Все объекты, галочки и ответственные сохраняются локально на вашем устройстве.</span>
      </div>
      <div class="note warn" id="fileNote" hidden>
        <svg class="ic"><use href="#i-alert"/></svg>
        <span>Файл открыт локально (file://). Для установки разместите index.html по HTTPS-адресу (например, GitHub Pages) и откройте ссылку в Safari.</span>
      </div>
      <div class="note dim">
        <svg class="ic"><use href="#i-dots"/></svg>
        <span>Android / Chrome: меню ⋮ → «Установить приложение» или «Добавить на главный экран».</span>
      </div>
    </div>
    <div class="sheet-foot">
      <button type="button" class="btn-ghost big" id="copyLink">
        <svg class="ic"><use href="#i-copy"/></svg>Скопировать ссылку
      </button>
      <span class="sp"></span>
      <button type="button" class="btn-primary big" id="btnInstallAction">Понятно</button>
    </div>
  </div>
</div>

<div id="toasts" class="toasts" role="status" aria-live="polite"></div>
<div id="confetti" aria-hidden="true"></div>

<script>
'use strict';
/* ================= КОНСТАНТЫ И ДАННЫЕ ================= */
const LS_DATA='pnr-objects-v1', LS_UI='pnr-ui-v1', LS_BANNER='pnr-banner-dismissed';
const WORKS=[
  {key:'efi',   code:'ЭФИ',   title:'Электрофизические измерения', role:'инженер ЭФИ'},
  {key:'tm',    code:'ТМ',    title:'Телемеханика',                role:'инженер СДТУ'},
  {key:'askue', code:'АСКУЭ', title:'Учёт электроэнергии',         role:'инженер АСКУЭ'}
];
const RING_C=106.8;
const reduced=window.matchMedia&&matchMedia('(prefers-reduced-motion: reduce)').matches;
const $=s=>document.querySelector(s), $$=s=>Array.from(document.querySelectorAll(s));
const esc=s=>String(s??'').replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
const icon=(id,cls='')=>`<svg class="ic ${cls}" aria-hidden="true"><use href="#${id}"/></svg>`;
const clone=o=>typeof structuredClone==='function'?structuredClone(o):JSON.parse(JSON.stringify(o));
const uid=()=> (typeof crypto!=='undefined'&&crypto.randomUUID)?crypto.randomUUID():'id-'+Date.now().toString(36)+Math.random().toString(36).slice(2,8);
const todayISO=()=>{const d=new Date();return d.getFullYear()+'-'+String(d.getMonth()+1).padStart(2,'0')+'-'+String(d.getDate()).padStart(2,'0')};
function fmtD(iso){
  if(!iso)return'';
  const p=String(iso).slice(0,10).split('-');
  if(p.length!==3)return'';
  const y=new Date().getFullYear();
  return p[2]+'.'+p[1]+(p[0]!==String(y)?'.'+p[0].slice(2):'');
}
function parseD(iso){const p=iso.slice(0,10).split('-').map(Number);return new Date(p[0],p[1]-1,p[2])}
function daysLeft(iso){const t=new Date();t.setHours(0,0,0,0);return Math.round((parseD(iso)-t)/864e5)}
const plural=(n,a,b,c)=>{n=Math.abs(n)%100;const d=n%10;if(n>10&&n<20)return c;if(d===1)return a;if(d>1&&d<5)return b;return c};
const initials=p=>{const t=p.trim().split(/\s+/);return((t[0]?.[0]||'')+(t[1]?.[0]||'')).toUpperCase()||'?'};
const vibrate=p=>{try{navigator.vibrate&&navigator.vibrate(p)}catch(e){}};

function seeds(){
  const W=(person,done=false,at=null)=>({person,done,at});
  return [
    {id:uid(),num:1,name:'ПС 110/10 кВ «Заречная»',kind:'ПС',deadline:'2026-11-23',createdAt:'2026-11-10',closedAt:null,
      works:{efi:W('Соколов А. В.',true,'2026-11-18'),tm:W('Мельникова И. П.'),askue:W('Гарипов Р. Н.')}},
    {id:uid(),num:2,name:'ПС 220/110 кВ «Северная»',kind:'ПС',deadline:'2026-12-12',createdAt:'2026-11-12',closedAt:null,
      works:{efi:W('Ковалёв Д. С.'),tm:W('Мельникова И. П.'),askue:W('Штерн Е. А.')}},
    {id:uid(),num:3,name:'РП-10 кВ № 7 «Озёрный»',kind:'РП',deadline:'2026-11-21',createdAt:'2026-11-05',closedAt:'2026-11-19',
      works:{efi:W('Соколов А. В.',true,'2026-11-17'),tm:W('Нуртдинов А. Р.',true,'2026-11-18'),askue:W('Гарипов Р. Н.',true,'2026-11-19')}},
    {id:uid(),num:4,name:'ПС 35/10 кВ «Таёжная»',kind:'ПС',deadline:'2026-11-30',createdAt:'2026-11-14',closedAt:null,
      works:{efi:W('Ковалёв Д. С.',true,'2026-11-19'),tm:W('Нуртдинов А. Р.'),askue:W('Штерн Е. А.',true,'2026-11-18')}},
    {id:uid(),num:5,name:'КТП-10/0,4 кВ № 118 «Лесная»',kind:'КТП',deadline:'2026-11-18',createdAt:'2026-11-15',closedAt:null,
      works:{efi:W('Соколов А. В.'),tm:W(''),askue:W('Гарипов Р. Н.',true,'2026-11-16')}}
  ];
}

/* ================= ХРАНИЛИЩЕ ================= */
const store={
  m:null,warned:false,
  get(k){try{return localStorage.getItem(k)}catch(e){return this.m?this.m[k]??null:null}},
  set(k,v){try{localStorage.setItem(k,v)}catch(e){
    (this.m=this.m||{})[k]=v;
    if(!this.warned){this.warned=true;toast('warn','Хранилище недоступно: данные сохранятся только до закрытия вкладки')}
  }}
};
const state={objects:[],filter:'all',sort:'status',query:''};
function save(){store.set(LS_DATA,JSON.stringify(state.objects))}
function saveUI(){store.set(LS_UI,JSON.stringify({filter:state.filter,sort:state.sort}))}
function load(){
  const raw=store.get(LS_DATA);
  if(raw===null){state.objects=seeds();save()}
  else{try{const a=JSON.parse(raw);state.objects=Array.isArray(a)?a:seeds()}catch(e){state.objects=seeds()}}
  try{const u=JSON.parse(store.get(LS_UI)||'{}');
    if(['all','open','closed'].includes(u.filter))state.filter=u.filter;
    if(['status','name','deadline','progress'].includes(u.sort))state.sort=u.sort;
  }catch(e){}
}

/* ================= ТОСТЫ ================= */
const TICONS={success:'i-check',info:'i-bolt',warn:'i-alert',danger:'i-trash'};
const TDUR={success:2800,info:3200,warn:4200,danger:6000};
function toast(type,msg,action,dur){
  const box=$('#toasts');
  while(box.children.length>=3){const f=box.firstElementChild;clearTimeout(f._t);f.remove()}
  const d=dur||TDUR[type]||3000;
  const el=document.createElement('div');
  el.className='toast t-'+type;
  el.innerHTML=`<span class="t-ic">${icon(TICONS[type]||'i-bolt')}</span>
    <span class="t-msg">${esc(msg)}</span>
    ${action?`<button type="button" class="t-act">${esc(action.label)}</button>`:''}
    <button type="button" class="t-x" aria-label="Закрыть уведомление">${icon('i-x')}</button>
    <span class="t-bar" style="animation-duration:${d}ms"></span>`;
  const dismiss=()=>{if(!el.isConnected)return;clearTimeout(el._t);el.classList.add('out');setTimeout(()=>el.remove(),200)};
  el.querySelector('.t-x').addEventListener('click',dismiss);
  if(action)el.querySelector('.t-act').addEventListener('click',()=>{dismiss();action.fn()});
  box.appendChild(el);
  el._t=setTimeout(dismiss,d);
}

/* ================= ВЫЧИСЛЕНИЯ ================= */
const doneCount=o=>WORKS.filter(w=>o.works[w.key].done).length;
const isClosed=o=>!!o.closedAt;
function deadlineInfo(o){
  if(isClosed(o))return{cls:'ok',ic:'i-check',label:'Закрыт '+fmtD(o.closedAt)};
  if(!o.deadline)return{cls:'',ic:'i-cal',label:'Срок не задан'};
  const n=daysLeft(o.deadline);
  if(n<0)return{cls:'over',ic:'i-alert',label:'Просрочен на '+(-n)+' '+plural(-n,'день','дня','дней')};
  if(n===0)return{cls:'soon',ic:'i-cal',label:'Срок сегодня'};
  if(n<=3)return{cls:'soon',ic:'i-cal',label:'Срок '+fmtD(o.deadline)+' · '+n+' '+plural(n,'день','дня','дней')};
  return{cls:'',ic:'i-cal',label:'Срок '+fmtD(o.deadline)};
}
function matchesCurrent(o){
  const closed=isClosed(o);
  if(state.filter==='open'&&closed)return false;
  if(state.filter==='closed'&&!closed)return false;
  const q=state.query.trim().toLowerCase();
  if(!q)return true;
  const hay=[o.name,o.kind,WORKS.map(w=>o.works[w.key].person).join(' ')].join(' ').toLowerCase();
  return hay.includes(q);
}
function normalizeFiltersFor(o){
  if(!matchesCurrent(o)){
    state.filter='all';state.query='';
    $('#search').value='';$('#btnClearSearch').hidden=true;saveUI();
  }
}

/* ================= ШАБЛОНЫ ================= */
const badgeInner=c=>c?`${icon('i-check','bi')}Закрыт`:`<span class="dot"></span>В работе`;
const metaHTML=w=>w.done?`${icon('i-check','mi')}${fmtD(w.at)}`:`<span class="wait">ожидает</span>`;
function workRowHTML(o,W){
  const w=o.works[W.key],p=(w.person||'').trim();
  return `<label class="work w-${W.key} ${w.done?'done':''}" data-w="${W.key}">
    <input type="checkbox" class="work-check" data-obj="${o.id}" data-work="${W.key}" ${w.done?'checked':''} aria-label="${esc(W.code+' — '+W.title)}">
    <span class="cbox"><svg viewBox="0 0 26 26" aria-hidden="true"><path d="M6 13.5l5 5L20 8"/></svg></span>
    <span class="wmain">
      <span class="wline"><span class="wcode">${W.code}</span><span class="wtitle">${esc(W.title)}</span></span>
      <span class="wperson">
        <span class="avatar ${p?'':'warn'}">${p?esc(initials(p)):'?'}</span>
        <span class="pname ${p?'':'warn'}">${p?esc(p):'Не назначен'}</span>
        <span class="prole">· ${esc(W.role)}</span>
      </span>
    </span>
    <span class="wmeta">${metaHTML(w)}</span>
  </label>`;
}
function cardHTML(o){
  const closed=isClosed(o),di=deadlineInfo(o);
  return `<article class="card ${closed?'closed':''}" data-id="${o.id}">
    <div class="card-top">
      <h2 class="card-name">${esc(o.name)}</h2>
      <span class="status-badge ${closed?'b-closed':'b-open'}">${badgeInner(closed)}</span>
    </div>
    <div class="card-chips">
      <span class="chip chip-kind">${esc(o.kind)}</span>
      <span class="chip chip-deadline ${di.cls}">${icon(di.ic)}${esc(di.label)}</span>
      <span class="chip chip-num">№ ${String(o.num||0).padStart(3,'0')}</span>
    </div>
    <div class="works-label ${closed?'ok':''}">${closed?'Все работы выполнены':'Виды работ'}</div>
    <div class="works">${WORKS.map(W=>workRowHTML(o,W)).join('')}</div>
    <div class="card-foot">
      <div class="prog">${WORKS.map(W=>`<span class="seg w-${W.key} ${o.works[W.key].done?'done':''}" data-w="${W.key}"></span>`).join('')}</div>
      <span class="prog-label">${doneCount(o)}/3</span>
      <div class="card-acts">
        <button type="button" class="ibtn act" data-act="edit" data-id="${o.id}" aria-label="Изменить объект: ${esc(o.name)}">${icon('i-pencil')}</button>
        <button type="button" class="ibtn act danger" data-act="del" data-id="${o.id}" aria-label="Удалить объект: ${esc(o.name)}">${icon('i-trash')}</button>
      </div>
    </div>
  </article>`;
}

/* ================= РЕНДЕР ================= */
let io=null,reconTimer=null,settleTimer=null;
if('IntersectionObserver'in window&&!reduced){
  io=new IntersectionObserver(es=>es.forEach(e=>{
    if(e.isIntersecting){e.target.classList.add('in');io.unobserve(e.target)}
  }),{threshold:.08});
}
function renderStats(){
  const total=state.objects.length;
  const closed=state.objects.filter(isClosed).length;
  $('#cnt-all').textContent=total;
  $('#cnt-open').textContent=total-closed;
  $('#cnt-closed').textContent=closed;
  $$('#chips .chip-f').forEach(b=>{
    const on=b.dataset.filter===state.filter;
    b.classList.toggle('active',on);b.setAttribute('aria-pressed',on);
  });
  const wTotal=total*3,wDone=state.objects.reduce((s,o)=>s+doneCount(o),0);
  const pct=wTotal?Math.round(wDone/wTotal*100):0;
  $('#ringFg').style.strokeDashoffset=String(RING_C*(1-(wTotal?wDone/wTotal:0)));
  $('#ringPct').textContent=pct+'%';
  $('#ringBox').title=`Выполнено ${wDone} из ${wTotal} работ`;
  $('#auroraGreen').style.opacity=total?String(.1+.45*(closed/total)):'0';
  document.body.classList.toggle('all-closed',total>0&&closed===total);
}
function visibleObjects(){
  const arr=state.objects.filter(matchesCurrent);
  const byName=(a,b)=>a.name.localeCompare(b.name,'ru');
  const dl=o=>o.deadline?parseD(o.deadline).getTime():Infinity;
  if(state.sort==='name')arr.sort(byName);
  else if(state.sort==='deadline')arr.sort((a,b)=>dl(a)-dl(b)||byName(a,b));
  else if(state.sort==='progress')arr.sort((a,b)=>doneCount(b)-doneCount(a)||byName(a,b));
  else arr.sort((a,b)=>{
    const ca=isClosed(a),cb=isClosed(b);
    if(ca!==cb)return ca?1:-1;
    if(ca)return String(b.closedAt).localeCompare(String(a.closedAt));
    return dl(a)-dl(b)||byName(a,b);
  });
  return arr;
}
function renderEmpty(){
  const e=$('#empty');
  if(state.objects.length===0){
    e.innerHTML=`<div class="empty-ic">${icon('i-bolt')}</div>
      <h3>Пока нет объектов</h3>
      <p>Добавьте первый объект — виды работ и ответственных можно назначить сразу.</p>
      <button type="button" class="btn-primary big" data-act="add">${icon('i-plus')}Добавить объект</button>`;
  }else if(state.query.trim()){
    e.innerHTML=`<div class="empty-ic">${icon('i-search')}</div>
      <h3>Ничего не найдено</h3>
      <p>По запросу «${esc(state.query.trim())}» нет объектов ни по наименованиям, ни по ответственным.</p>
      <button type="button" class="btn-ghost big" data-act="clear-filters">Сбросить поиск и фильтры</button>`;
  }else if(state.filter==='open'){
    e.innerHTML=`<div class="empty-ic ok">${icon('i-check')}</div>
      <h3>Все объекты закрыты</h3>
      <p>Отличная работа — незавершённых объектов не осталось.</p>
      <button type="button" class="btn-ghost big" data-act="show-all">Показать все</button>`;
  }else{
    e.innerHTML=`<div class="empty-ic">${icon('i-check')}</div>
      <h3>Закрытых объектов пока нет</h3>
      <p>Отметьте галочками все три вида работ на карточке — объект закроется и подсветится зелёным.</p>
      <button type="button" class="btn-ghost big" data-act="show-all">Показать все</button>`;
  }
}
function renderList(animate){
  clearTimeout(reconTimer);clearTimeout(settleTimer);
  if(io)io.disconnect();
  const list=$('#list'),arr=visibleObjects();
  if(arr.length===0){list.innerHTML='';renderEmpty();$('#empty').hidden=false;return}
  $('#empty').hidden=true;
  list.innerHTML=arr.map(cardHTML).join('');
  const cards=Array.from(list.children);
  if(animate&&io){
    cards.forEach((c,i)=>{c.classList.add('pre');c.style.setProperty('--d',Math.min(i*60,420)+'ms');io.observe(c)});
    settleTimer=setTimeout(()=>cards.forEach(c=>c.classList.add('settled')),1300);
  }else{
    cards.forEach(c=>c.classList.add('settled'));
    if(animate&&!reduced)cards.forEach((c,i)=>{c.style.animation=`cardIn .5s var(--ease) ${Math.min(i*50,300)}ms backwards`});
  }
}
function renderAll(animate){renderStats();renderList(animate)}

/* ================= ОБНОВЛЕНИЕ КАРТОЧКИ НА МЕСТЕ ================= */
function updateCardInPlace(card,o){
  if(!card)return;
  const closed=isClosed(o),di=deadlineInfo(o);
  card.classList.toggle('closed',closed);
  const badge=card.querySelector('.status-badge');
  badge.className='status-badge '+(closed?'b-closed':'b-open');
  badge.innerHTML=badgeInner(closed);
  const chip=card.querySelector('.chip-deadline');
  chip.className='chip chip-deadline '+di.cls;
  chip.innerHTML=icon(di.ic)+esc(di.label);
  const lbl=card.querySelector('.works-label');
  lbl.classList.toggle('ok',closed);
  lbl.textContent=closed?'Все работы выполнены':'Виды работ';
  WORKS.forEach(W=>{
    const w=o.works[W.key];
    const row=card.querySelector(`.work[data-w="${W.key}"]`);
    row.classList.toggle('done',w.done);
    row.querySelector('.work-check').checked=w.done;
    row.querySelector('.wmeta').innerHTML=metaHTML(w);
    card.querySelector(`.seg[data-w="${W.key}"]`).classList.toggle('done',w.done);
  });
  card.querySelector('.prog-label').textContent=doneCount(o)+'/3';
}

/* ================= КОНФЕТТИ ================= */
const CF_COLORS=['#3DDC84','#A3F7BF','#FFB224','#2BD9FF','#B78CFF','#FF4FD8','#EAF1FF'];
function confettiAt(card){
  if(reduced)return;
  const layer=$('#confetti');
  if(layer.children.length>120)return;
  const r=card.getBoundingClientRect();
  const cx=r.left+r.width/2,cy=Math.max(70,r.top+64);
  for(let i=0;i<26;i++){
    const p=document.createElement('i');p.className='cf';
    const s=4+Math.random()*6;
    p.style.cssText=`left:${cx-s/2}px;top:${cy-s/2}px;width:${s}px;height:${s*(Math.random()>.5?1:.45)}px;background:${CF_COLORS[i%CF_COLORS.length]};border-radius:${Math.random()>.6?'50%':'2px'}`;
    layer.appendChild(p);
    if(!p.animate){p.remove();continue}
    const ang=(-160+Math.random()*140)*Math.PI/180,v=70+Math.random()*110;
    const dx=Math.cos(ang)*v,dy=Math.sin(ang)*v,rot=(Math.random()-.5)*520;
    p.animate([
      {transform:'translate(0,0) rotate(0deg)',opacity:1},
      {transform:`translate(${dx}px,${dy}px) rotate(${rot*.6}deg)`,opacity:1,offset:.55},
      {transform:`translate(${dx*1.15}px,${dy+150}px) rotate(${rot}deg)`,opacity:0}
    ],{duration:800+Math.random()*500,easing:'cubic-bezier(.15,.6,.35,1)'}).onfinish=()=>p.remove();
  }
}

/* ================= ПЕРЕКЛЮЧЕНИЕ ГАЛОЧЕК ================= */
function onToggle(input){
  const o=state.objects.find(x=>x.id===input.dataset.obj);
  if(!o)return;
  const w=o.works[input.dataset.work];
  w.done=input.checked;w.at=w.done?todayISO():null;
  const all=WORKS.every(x=>o.works[x.key].done);
  const wasClosed=isClosed(o);
  let celebrated=false;
  if(all&&!wasClosed){o.closedAt=todayISO();celebrated=true}
  else if(!all&&wasClosed){o.closedAt=null;toast('info','Объект возвращён в работу: '+o.name)}
  save();
  const card=input.closest('.card');
  updateCardInPlace(card,o);
  renderStats();
  const cbox=card.querySelector(`.work[data-w="${input.dataset.work}"] .cbox`);
  if(w.done){cbox.classList.remove('anim');void cbox.offsetWidth;cbox.classList.add('anim');
    cbox.addEventListener('animationend',()=>cbox.classList.remove('anim'),{once:true});}
  if(celebrated){
    card.classList.remove('just-closed');void card.offsetWidth;card.classList.add('just-closed');
    card.addEventListener('animationend',()=>card.classList.remove('just-closed'),{once:true});
    confettiAt(card);vibrate([30,40,60]);
    toast('success','Объект закрыт: '+o.name);
  }else vibrate(18);
  if(state.filter!=='all'||state.sort==='status'||state.sort==='progress'){
    clearTimeout(reconTimer);
    reconTimer=setTimeout(()=>renderList(false),celebrated?1500:800);
  }
}

/* ================= УДАЛЕНИЕ + ОТМЕНА ================= */
function deleteObject(id){
  const idx=state.objects.findIndex(x=>x.id===id);
  if(idx<0)return;
  const obj=state.objects[idx];
  state.objects.splice(idx,1);save();renderStats();
  const card=$('#list').querySelector(`.card[data-id="${id}"]`);
  const done=()=>renderList(false);
  if(card&&!reduced){
    card.classList.add('settled');
    card.style.height=card.offsetHeight+'px';card.style.overflow='hidden';
    requestAnimationFrame(()=>{
      card.style.transition='height .3s ease,opacity .25s ease,transform .3s ease,padding .3s ease,border-width .3s ease';
      card.style.height='0px';card.style.opacity='0';card.style.transform='scale(.96)';
      card.style.paddingTop='0';card.style.paddingBottom='0';card.style.borderWidth='0';
    });
    setTimeout(done,330);
  }else done();
  toast('danger','Удалено: '+obj.name,{label:'Отменить',fn(){
    state.objects.splice(Math.min(idx,state.objects.length),0,obj);
    normalizeFiltersFor(obj);save();renderAll(false);
    const c=$('#list').querySelector(`.card[data-id="${obj.id}"]`);
    if(c)c.classList.add('pop-in');
    toast('success','Объект восстановлен');
  }},6500);
}

/* ================= ШТОРКИ ================= */
let lastFocus=null;
function openSheet(scrim,focusEl){
  lastFocus=document.activeElement;
  scrim.hidden=false;
  document.documentElement.classList.add('lock');
  setTimeout(()=>{(focusEl||scrim.querySelector('input,select,button'))?.focus?.()},80);
}
function closeSheet(scrim){
  if(scrim.hidden)return;
  scrim.classList.add('closing');
  setTimeout(()=>{
    scrim.hidden=true;scrim.classList.remove('closing');
    if($('#objScrim').hidden&&$('#installScrim').hidden)document.documentElement.classList.remove('lock');
    if(lastFocus&&lastFocus.focus)lastFocus.focus();
  },200);
}
function trapTab(e,scrim){
  if(e.key!=='Tab')return;
  const f=Array.from(scrim.querySelectorAll('button,[href],input,select,textarea,[tabindex]:not([tabindex="-1"])'))
    .filter(el=>!el.hidden&&el.offsetParent!==null);
  if(!f.length)return;
  const first=f[0],last=f[f.length-1];
  if(e.shiftKey&&document.activeElement===first){e.preventDefault();last.focus()}
  else if(!e.shiftKey&&document.activeElement===last){e.preventDefault();first.focus()}
}

/* ---- шторка объекта ---- */
let editingId=null;
function openObjectSheet(mode,obj){
  editingId=obj?obj.id:null;
  $('#objSheetTitle').textContent=obj?'Изменить объект':'Новый объект';
  $('#objSheetSub').textContent=obj?'Наименование, срок и ответственные лица':'Заполните карточку объекта';
  $('#btnObjSave').textContent=obj?'Сохранить':'Добавить объект';
  $('#btnObjDelete').hidden=!obj;
  $('#fName').value=obj?obj.name:'';
  $('#fKind').value=obj?obj.kind:'ПС';
  $('#fDeadline').value=obj?(obj.deadline||''):'';
  WORKS.forEach(W=>{$('#fPerson-'+W.key).value=obj?(obj.works[W.key].person||''):''});
  $('#fName').classList.remove('invalid');$('#fNameErr').hidden=true;
  openSheet($('#objScrim'),$('#fName'));
}
$('#objForm').addEventListener('submit',e=>{
  e.preventDefault();
  const name=$('#fName').value.trim();
  if(name.length<2){
    const f=$('#fName');f.classList.remove('invalid');void f.offsetWidth;f.classList.add('invalid');
    $('#fNameErr').hidden=false;f.focus();return;
  }
  const kind=$('#fKind').value,deadline=$('#fDeadline').value||null;
  const persons={};WORKS.forEach(W=>persons[W.key]=$('#fPerson-'+W.key).value.trim());
  let target;
  if(editingId){
    target=state.objects.find(x=>x.id===editingId);
    if(target){
      target.name=name;target.kind=kind;target.deadline=deadline;
      WORKS.forEach(W=>target.works[W.key].person=persons[W.key]);
    }
  }else{
    target={id:uid(),num:state.objects.reduce((m,o)=>Math.max(m,o.num||0),0)+1,
      name,kind,deadline,createdAt:todayISO(),closedAt:null,works:{}};
    WORKS.forEach(W=>target.works[W.key]={person:persons[W.key],done:false,at:null});
    state.objects.unshift(target);
  }
  if(target)normalizeFiltersFor(target);
  save();closeSheet($('#objScrim'));renderAll(false);
  if(target){
    const c=$('#list').querySelector(`.card[data-id="${target.id}"]`);
    if(c){c.classList.add('pop-in');setTimeout(()=>c.scrollIntoView({behavior:reduced?'auto':'smooth',block:'nearest'}),60)}
  }
  toast('success',editingId?'Изменения сохранены':'Объект добавлен: '+name);
});
$('#btnObjDelete').addEventListener('click',()=>{
  const id=editingId;closeSheet($('#objScrim'));
  setTimeout(()=>deleteObject(id),210);
});
$('#btnObjCancel').addEventListener('click',()=>closeSheet($('#objScrim')));
$('#btnObjClose').addEventListener('click',()=>closeSheet($('#objScrim')));

/* ---- шторка установки ---- */
let deferredPrompt=null;
window.addEventListener('beforeinstallprompt',e=>{
  e.preventDefault();deferredPrompt=e;
  $('#btnInstallAction').textContent='Установить приложение';
});
window.addEventListener('appinstalled',()=>{
  toast('success','Приложение установлено');refreshInstallUI();
});
const isStandalone=()=>navigator.standalone===true||(window.matchMedia&&matchMedia('(display-mode: standalone)').matches);
function refreshInstallUI(){
  const st=isStandalone();
  $('#btnInstallTop').hidden=st;
  $('#footInstall').hidden=st;
  $('#footInstalled').hidden=!st;
  $('#installedNote').hidden=!st;
  $('#installSteps').hidden=st;
  $('#btnInstallAction').hidden=st;
  $('#installBanner').hidden=st||!!store.get(LS_BANNER);
  const isFile=location.protocol==='file:';
  $('#fileNote').hidden=!isFile;
  $('#copyLink').hidden=isFile||!navigator.clipboard;
}
function openInstall(){refreshInstallUI();openSheet($('#installScrim'),$('#btnInstallAction'))}
$('#btnInstallTop').addEventListener('click',openInstall);
$('#footInstall').addEventListener('click',openInstall);
$('#btnInstallClose').addEventListener('click',()=>closeSheet($('#installScrim')));
$('#btnInstallAction').addEventListener('click',async()=>{
  if(deferredPrompt){
    deferredPrompt.prompt();
    try{const r=await deferredPrompt.userChoice;
      if(r.outcome==='accepted'){closeSheet($('#installScrim'))}
      else toast('info','Установку можно выполнить позже через меню браузера');
    }catch(e){}
    deferredPrompt=null;
  }else closeSheet($('#installScrim'));
});
$('#copyLink').addEventListener('click',()=>{
  navigator.clipboard.writeText(location.href)
    .then(()=>toast('success','Ссылка скопирована — откройте её в Safari'))
    .catch(()=>toast('warn','Не удалось скопировать ссылку'));
});

/* ================= СОБЫТИЯ СПИСКА / ПАНЕЛЕЙ ================= */
$('#main').addEventListener('change',e=>{
  if(e.target.classList.contains('work-check'))onToggle(e.target);
});
$('#main').addEventListener('click',e=>{
  const b=e.target.closest('[data-act]');
  if(!b)return;
  const act=b.dataset.act;
  if(act==='edit'){const o=state.objects.find(x=>x.id===b.dataset.id);if(o)openObjectSheet('edit',o)}
  else if(act==='del')deleteObject(b.dataset.id);
  else if(act==='add')openObjectSheet('new');
  else if(act==='show-all'){state.filter='all';saveUI();renderAll(false)}
  else if(act==='clear-filters'){
    state.filter='all';state.query='';$('#search').value='';$('#btnClearSearch').hidden=true;
    saveUI();renderAll(false);
  }
  else if(act==='banner-how')openInstall();
  else if(act==='banner-x'){store.set(LS_BANNER,'1');$('#installBanner').hidden=true}
});
$('#btnAdd').addEventListener('click',()=>openObjectSheet('new'));
$('#chips').addEventListener('click',e=>{
  const b=e.target.closest('.chip-f');if(!b)return;
  state.filter=b.dataset.filter;saveUI();renderStats();renderList(false);
});
$('#sortSel').addEventListener('change',e=>{state.sort=e.target.value;saveUI();renderList(false)});
let searchT=null;
$('#search').addEventListener('input',e=>{
  clearTimeout(searchT);
  const v=e.target.value;
  $('#btnClearSearch').hidden=!v;
  searchT=setTimeout(()=>{state.query=v;renderList(false)},130);
});
$('#btnClearSearch').addEventListener('click',()=>{
  $('#search').value='';$('#btnClearSearch').hidden=true;state.query='';renderList(false);$('#search').focus();
});

/* ---- клики по подложке, Esc, ловушка фокуса, «/» ---- */
[['#objScrim'],['#installScrim']].forEach(([sel])=>{
  const sc=$(sel);
  sc.addEventListener('click',e=>{if(e.target===sc)closeSheet(sc)});
  sc.addEventListener('keydown',e=>trapTab(e,sc));
});
document.addEventListener('keydown',e=>{
  if(e.key==='Escape'){
    if(!$('#objScrim').hidden)closeSheet($('#objScrim'));
    else if(!$('#installScrim').hidden)closeSheet($('#installScrim'));
  }
  if(e.key==='/'&&!e.target.closest('input,select,textarea')&&$('#objScrim').hidden&&$('#installScrim').hidden){
    e.preventDefault();$('#search').focus();
  }
});

/* ================= ПОДВАЛ: ЭКСПОРТ / ДЕМО ================= */
$('#btnExport').addEventListener('click',()=>{
  const payload={app:'ПНР Контроль',version:1,exportedAt:new Date().toISOString(),objects:state.objects};
  const blob=new Blob([JSON.stringify(payload,null,2)],{type:'application/json'});
  const a=document.createElement('a');
  a.href=URL.createObjectURL(blob);
  a.download='pnr-objects-'+todayISO()+'.json';
  document.body.appendChild(a);a.click();a.remove();
  setTimeout(()=>URL.revokeObjectURL(a.href),4000);
  toast('success','Экспортировано объектов: '+state.objects.length);
});
$('#btnReset').addEventListener('click',()=>{
  const prev=clone(state.objects);
  state.objects=seeds();save();renderAll(false);
  toast('warn','Демо-данные восстановлены',{label:'Отменить',fn(){
    state.objects=prev;save();renderAll(false);toast('success','Ваши данные возвращены');
  }},6000);
});

/* ================= ИКОНКИ ПРИЛОЖЕНИЯ + МАНИФЕСТ ================= */
function makeIcon(s){
  const c=document.createElement('canvas');c.width=c.height=s;
  const x=c.getContext('2d');
  const g=x.createLinearGradient(0,0,s,s);
  g.addColorStop(0,'#121E36');g.addColorStop(1,'#080D18');
  x.fillStyle=g;x.fillRect(0,0,s,s);
  x.strokeStyle='rgba(120,160,220,.07)';x.lineWidth=1;
  for(let i=1;i<8;i++){
    x.beginPath();x.moveTo(i*s/8,0);x.lineTo(i*s/8,s);x.stroke();
    x.beginPath();x.moveTo(0,i*s/8);x.lineTo(s,i*s/8);x.stroke();
  }
  let r=x.createRadialGradient(s*.85,s*.12,0,s*.85,s*.12,s*.6);
  r.addColorStop(0,'rgba(43,217,255,.3)');r.addColorStop(1,'rgba(43,217,255,0)');
  x.fillStyle=r;x.fillRect(0,0,s,s);
  r=x.createRadialGradient(s*.14,s*.9,0,s*.14,s*.9,s*.65);
  r.addColorStop(0,'rgba(61,220,132,.32)');r.addColorStop(1,'rgba(61,220,132,0)');
  x.fillStyle=r;x.fillRect(0,0,s,s);
  x.save();
  x.translate(s*.5,s*.5);x.scale(s/112,s/112);x.translate(-51,-50);
  const p=new Path2D('M62 4 L18 58 L44 58 L36 96 L84 40 L56 40 L70 4 Z');
  const bg=x.createLinearGradient(0,0,0,100);
  bg.addColorStop(0,'#FFC53D');bg.addColorStop(.55,'#FFB224');bg.addColorStop(1,'#3DDC84');
  x.shadowColor='rgba(61,220,132,.55)';x.shadowBlur=12;
  x.fillStyle=bg;x.fill(p);
  x.restore();
  return c.toDataURL('image/png');
}
function buildAppIcons(){
  try{
    const i180=makeIcon(180),i192=makeIcon(192),i512=makeIcon(512),i64=makeIcon(64);
    $('#appleIcon').href=i180;
    $('#favicon').href=i64;
    if(/^https?:$/.test(location.protocol)){
      const m={
        name:'ПНР Контроль — объекты и виды работ',short_name:'ПНР',lang:'ru',
        description:'Чек-лист пусконаладки: ЭФИ, телемеханика, АСКУЭ, ответственные лица.',
        start_url:location.href.split(/[?#]/)[0],
        scope:location.href.replace(/[?#].*$/,'').replace(/[^/]*$/,''),
        display:'standalone',background_color:'#0B1220',theme_color:'#0B1220',
        icons:[
          {src:i192,sizes:'192x192',type:'image/png',purpose:'any'},
          {src:i512,sizes:'512x512',type:'image/png',purpose:'any'},
          {src:i512,sizes:'512x512',type:'image/png',purpose:'maskable'}
        ]
      };
      $('#manifestLink').href=URL.createObjectURL(new Blob([JSON.stringify(m)],{type:'application/manifest+json'}));
    }
  }catch(e){/* иконки не критичны для работы */}
}

/* ================= ПРОЧЕЕ ================= */
window.addEventListener('scroll',()=>{
  $('#appHeader').classList.toggle('scrolled',window.scrollY>6);
},{passive:true});

/* ================= СТАРТ ================= */
load();
buildAppIcons();
$('#sortSel').value=state.sort;
refreshInstallUI();
renderAll(true);
</script>
</body>
</html>
