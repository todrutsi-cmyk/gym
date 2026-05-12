[index.html.html](https://github.com/user-attachments/files/27636790/index.html.html)

<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GYMFORGE</title>
<meta property="og:title" content="GYMFORGE">
<meta property="og:description" content="운동 기록 · 루틴 · 식단 · 통계">
<meta property="og:type" content="website">
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Noto+Sans+KR:wght@300;400;500;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#0d0d0d;--surface:#171717;--s2:#202020;--s3:#2a2a2a;
  --accent:#c8ff00;--adim:rgba(200,255,0,.08);--aborder:rgba(200,255,0,.22);
  --red:#ff4d4d;--blue:#4d9fff;--orange:#ff8c42;--purple:#a855f7;
  --text:#f0f0f0;--muted:#555;--muted2:#888;--border:#252525;
}
*{box-sizing:border-box;margin:0;padding:0;}
html,body{height:100%;background:var(--bg);color:var(--text);font-family:'Noto Sans KR',sans-serif;font-size:14px;overflow-x:hidden;}

header{display:flex;align-items:center;justify-content:flex-start;padding:14px 18px 0;border-bottom:1px solid var(--border);}
.logo{font-family:'Bebas Neue',sans-serif;font-size:28px;letter-spacing:3px;color:var(--accent);line-height:1;}
.logo span{color:var(--text);}
nav{display:flex;overflow-x:auto;scrollbar-width:none;}
nav::-webkit-scrollbar{display:none;}
nav button{flex-shrink:0;background:none;border:none;border-bottom:2px solid transparent;padding:11px 13px;font-family:'Noto Sans KR',sans-serif;font-size:12px;font-weight:500;color:var(--muted2);cursor:pointer;transition:all .2s;white-space:nowrap;}
nav button.active{color:var(--accent);border-bottom-color:var(--accent);}
nav button:hover:not(.active){color:var(--text);}

main{padding:14px;max-width:640px;margin:0 auto;}
.tab{display:none;}
.tab.active{display:block;}

.card{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:16px;margin-bottom:12px;}
.card-title{font-family:'Bebas Neue',sans-serif;font-size:17px;letter-spacing:1px;margin-bottom:12px;}
.sec-lbl{font-family:'Bebas Neue',sans-serif;font-size:15px;letter-spacing:1px;margin:4px 0 10px;}

.field{margin-bottom:11px;}
.field label{font-size:11px;color:var(--muted2);text-transform:uppercase;letter-spacing:1px;display:block;margin-bottom:4px;}
input,select,textarea{width:100%;background:var(--s2);border:1px solid var(--border);border-radius:8px;color:var(--text);font-family:'Noto Sans KR',sans-serif;font-size:14px;padding:9px 12px;outline:none;transition:border-color .2s;}
input:focus,select:focus,textarea:focus{border-color:var(--accent);}
select option{background:var(--s2);}
.r2{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
.r3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px;}

.btn{padding:9px 16px;border-radius:8px;font-family:'Noto Sans KR',sans-serif;font-size:13px;font-weight:500;cursor:pointer;border:none;transition:all .15s;display:inline-flex;align-items:center;gap:5px;}
.btn-accent{background:var(--accent);color:#0d0d0d;font-weight:700;}
.btn-accent:hover{background:#d4ff1a;transform:translateY(-1px);}
.btn-ghost{background:var(--s2);color:var(--text);border:1px solid var(--border);}
.btn-ghost:hover{border-color:var(--accent);color:var(--accent);}
.btn-red{background:rgba(255,77,77,.1);color:var(--red);border:1px solid rgba(255,77,77,.2);}
.btn-full{width:100%;justify-content:center;}
.btn-sm{padding:6px 11px;font-size:12px;}
.btn-xs{padding:4px 8px;font-size:11px;border-radius:6px;}
.icon-btn{background:none;border:none;color:var(--muted2);cursor:pointer;padding:4px 6px;border-radius:6px;font-size:15px;line-height:1;}
.icon-btn:hover{color:var(--red);background:rgba(255,77,77,.1);}

/* SET */
.set-header{display:grid;grid-template-columns:30px 1fr 1fr 36px;gap:6px;padding:0 2px 7px;font-size:11px;color:var(--muted);text-transform:uppercase;letter-spacing:1px;border-bottom:1px solid var(--border);margin-bottom:7px;text-align:center;}
.set-row{display:grid;grid-template-columns:30px 1fr 1fr 36px;gap:6px;align-items:center;margin-bottom:5px;}
.set-num{height:35px;background:var(--s2);border:1px solid var(--border);border-radius:6px;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;color:var(--muted2);}
.set-row input{text-align:center;padding:7px 4px;height:35px;margin:0;}
.add-set-btn{width:100%;background:none;border:1px dashed var(--border);color:var(--muted2);border-radius:8px;padding:7px;cursor:pointer;font-family:'Noto Sans KR',sans-serif;font-size:13px;margin-top:3px;transition:all .2s;}
.add-set-btn:hover{border-color:var(--accent);color:var(--accent);background:var(--adim);}

/* BADGE */
.badge-row{display:flex;flex-wrap:wrap;gap:4px;}
.badge{background:var(--surface);border:1px solid var(--border);border-radius:6px;padding:3px 7px;font-size:11px;color:var(--muted2);}
.tier-badge{font-size:10px;padding:2px 6px;border-radius:4px;font-weight:700;display:inline-block;}
.t1{background:rgba(200,255,0,.12);color:var(--accent);border:1px solid var(--aborder);}
.t2{background:rgba(77,159,255,.12);color:var(--blue);border:1px solid rgba(77,159,255,.25);}
.t3{background:rgba(168,85,247,.12);color:var(--purple);border:1px solid rgba(168,85,247,.25);}

/* CHIP */
.chip{padding:5px 10px;border-radius:20px;font-size:11px;font-weight:500;cursor:pointer;border:1px solid var(--border);background:var(--s2);color:var(--muted2);transition:all .15s;white-space:nowrap;}
.chip:hover,.chip.on{background:var(--adim);border-color:var(--aborder);color:var(--accent);}

/* EX ITEM */
.ex-item{background:var(--s2);border:1px solid var(--border);border-radius:10px;padding:12px 14px;margin-bottom:8px;display:flex;justify-content:space-between;align-items:flex-start;gap:10px;}
.ex-name{font-weight:700;font-size:15px;color:var(--accent);margin-bottom:5px;}

/* SW */
.sw-time{font-family:'Bebas Neue',sans-serif;font-size:64px;letter-spacing:4px;line-height:1;color:var(--accent);text-align:center;padding:16px 0 4px;}
.sw-btns{display:flex;justify-content:center;gap:10px;margin:12px 0;}
.sw-btn{width:64px;height:64px;border-radius:50%;font-family:'Bebas Neue',sans-serif;font-size:13px;letter-spacing:1px;cursor:pointer;border:none;transition:all .15s;}
.sw-btn:hover{transform:scale(1.06);}
.sw-go{background:var(--accent);color:#0d0d0d;}
.sw-stop{background:var(--red);color:#fff;}
.sw-reset,.sw-lap{background:var(--s2);color:var(--text);border:1px solid var(--border);}
.lap-item{display:flex;justify-content:space-between;padding:5px 4px;border-bottom:1px solid var(--border);font-size:12px;}
.lap-t{font-family:'Bebas Neue',sans-serif;font-size:14px;letter-spacing:1px;color:var(--accent);}

/* REST */
.rest-disp{font-family:'Bebas Neue',sans-serif;font-size:50px;color:var(--accent);letter-spacing:3px;text-align:center;line-height:1;}
.rest-bar{height:5px;background:var(--border);border-radius:3px;margin:10px 0;overflow:hidden;}
.rest-fill{height:100%;background:var(--accent);border-radius:3px;transition:width .1s linear;}
.rest-pre{display:flex;gap:6px;justify-content:center;flex-wrap:wrap;margin-top:8px;}

/* CAL */
.cal-nav{display:flex;align-items:center;justify-content:space-between;margin-bottom:12px;}
.cal-title{font-family:'Bebas Neue',sans-serif;font-size:22px;letter-spacing:1px;}
.cal-dow{display:grid;grid-template-columns:repeat(7,1fr);text-align:center;font-size:11px;color:var(--muted);margin-bottom:5px;}
.cal-grid{display:grid;grid-template-columns:repeat(7,1fr);gap:3px;}
.cal-day{aspect-ratio:1;display:flex;flex-direction:column;align-items:center;justify-content:center;border-radius:7px;font-size:12px;cursor:pointer;color:var(--muted2);border:1px solid transparent;position:relative;transition:all .15s;}
.cal-day:hover{background:var(--s2);color:var(--text);}
.cal-day.hw{background:var(--adim);color:var(--text);border-color:var(--aborder);}
.cal-day.hf{border-bottom:2px solid var(--orange);}
.cal-day.today{border-color:var(--accent);color:var(--accent);font-weight:700;}
.cal-day.sel{background:var(--accent);color:#0d0d0d;font-weight:700;border-color:var(--accent);}
.cal-dot{width:4px;height:4px;border-radius:50%;background:var(--accent);position:absolute;bottom:4px;}
.cal-day.sel .cal-dot{background:#0d0d0d;}

/* STATS */
.stats-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-bottom:12px;}
.stat-box{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:13px 8px;text-align:center;}
.stat-num{font-family:'Bebas Neue',sans-serif;font-size:28px;color:var(--accent);line-height:1;letter-spacing:1px;}
.stat-lbl{font-size:10px;color:var(--muted2);margin-top:3px;text-transform:uppercase;letter-spacing:.5px;}
.pr-row{display:flex;justify-content:space-between;align-items:center;padding:9px 0;border-bottom:1px solid var(--border);}
.pr-row:last-child{border-bottom:none;}
.pr-kg{font-family:'Bebas Neue',sans-serif;font-size:18px;color:var(--accent);letter-spacing:1px;}
.chart-wrap{position:relative;height:120px;display:flex;align-items:flex-end;gap:4px;}
.cbar-g{flex:1;display:flex;flex-direction:column;align-items:center;gap:3px;}
.cbar{width:100%;border-radius:4px 4px 0 0;min-height:2px;background:var(--accent);}
.cbar-lbl{font-size:10px;color:var(--muted2);}

/* BALANCE */
.bal-row{margin-bottom:10px;}
.bal-name{display:flex;justify-content:space-between;font-size:12px;color:var(--muted2);margin-bottom:4px;}
.bal-bar{height:7px;background:var(--border);border-radius:4px;overflow:hidden;}
.bal-fill{height:100%;background:var(--accent);border-radius:4px;transition:width .4s;}

/* FOOD */
.food-item{background:var(--s2);border:1px solid var(--border);border-radius:10px;padding:11px 13px;margin-bottom:7px;display:flex;justify-content:space-between;align-items:center;}
.food-kcal{font-family:'Bebas Neue',sans-serif;font-size:18px;color:var(--orange);letter-spacing:1px;}
.macro-sum{display:grid;grid-template-columns:repeat(3,1fr);gap:7px;margin-top:10px;}
.macro-box{text-align:center;background:var(--s2);border-radius:8px;padding:9px 4px;}
.macro-num{font-family:'Bebas Neue',sans-serif;font-size:20px;letter-spacing:1px;}
.macro-lbl{font-size:10px;color:var(--muted2);}

/* LOG */
.log-item{background:var(--s2);border:1px solid var(--border);border-radius:10px;padding:12px 14px;margin-bottom:7px;}
.log-date{font-size:11px;color:var(--muted2);margin-bottom:3px;}
.log-name{font-weight:700;font-size:14px;color:var(--accent);margin-bottom:5px;}

/* ROUTINE */
.rtab{flex-shrink:0;background:none;border:none;border-bottom:2px solid transparent;padding:9px 13px;font-family:'Noto Sans KR',sans-serif;font-size:12px;font-weight:500;color:var(--muted2);cursor:pointer;transition:all .2s;white-space:nowrap;}
.rtab.on{color:var(--accent);border-bottom-color:var(--accent);}
.rtn-card{background:var(--s2);border:1px solid var(--border);border-radius:12px;padding:14px;margin-bottom:10px;}
.rtn-name{font-size:15px;font-weight:700;color:var(--accent);margin-bottom:3px;}
.rtn-desc{font-size:12px;color:var(--muted2);margin-bottom:6px;line-height:1.5;}
.rtn-meta{display:flex;gap:6px;margin-bottom:10px;flex-wrap:wrap;}
.rtn-tag{font-size:11px;padding:3px 8px;border-radius:6px;background:var(--s3);color:var(--muted2);}
.rtn-tag.g{background:var(--adim);color:var(--accent);}
.rtn-tag.b{background:rgba(77,159,255,.1);color:var(--blue);}
.drag-handle{cursor:grab;color:var(--muted);font-size:16px;padding:0 4px;user-select:none;}
.rtn-ex-row{background:var(--s2);border:1px solid var(--border);border-radius:10px;padding:11px 13px;margin-bottom:7px;display:flex;align-items:flex-start;gap:10px;}
.rtn-ex-row.dragging{opacity:.4;border-style:dashed;}

/* SWAP */
.swap-modal{display:none;position:fixed;inset:0;background:rgba(0,0,0,.75);z-index:500;align-items:flex-end;justify-content:center;}
.swap-modal.open{display:flex;}
.swap-sheet{background:var(--surface);border-radius:16px 16px 0 0;padding:20px;width:100%;max-width:640px;max-height:70vh;overflow-y:auto;}
.swap-item{background:var(--s2);border:1px solid var(--border);border-radius:9px;padding:11px 13px;margin-bottom:7px;cursor:pointer;transition:all .15s;}
.swap-item:hover{border-color:var(--accent);}
.swap-btn{background:rgba(255,140,66,.1);color:var(--orange);border:1px solid rgba(255,140,66,.25);border-radius:6px;padding:4px 9px;font-size:11px;cursor:pointer;font-family:'Noto Sans KR',sans-serif;white-space:nowrap;}
.swap-btn:hover{background:rgba(255,140,66,.2);}

/* GUIDE */
.guide-acc-btn{width:100%;background:var(--s2);border:none;padding:13px 14px;display:flex;justify-content:space-between;align-items:center;cursor:pointer;text-align:left;}

/* BODY */
.body-num{font-family:'Bebas Neue',sans-serif;font-size:17px;color:var(--blue);letter-spacing:.5px;}

/* HOME */
.home-wrap{padding:20px 0;}
.home-header{padding:28px 0 32px;text-align:center;}
.home-date{font-size:11px;color:var(--muted);letter-spacing:2px;margin-bottom:6px;}
.home-today-status{font-size:13px;color:var(--muted2);}
.home-today-status em{color:var(--accent);font-style:normal;font-weight:700;}
.home-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-bottom:24px;}
.home-stat{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:14px 8px;text-align:center;}
.home-stat-num{font-family:'Bebas Neue',sans-serif;font-size:28px;color:var(--accent);line-height:1;}
.home-stat-lbl{font-size:10px;color:var(--muted2);margin-top:4px;text-transform:uppercase;letter-spacing:.5px;}
.streak-wrap{display:flex;gap:5px;justify-content:center;margin-bottom:24px;}
.streak-day{width:32px;height:32px;border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:10px;font-weight:700;border:1px solid var(--border);color:var(--muted);}
.streak-day.done{background:var(--adim);border-color:var(--aborder);color:var(--accent);}
.streak-day.cur{border-color:var(--accent);color:var(--accent);}
.home-menu{display:flex;flex-direction:column;gap:2px;margin-bottom:24px;}
.home-menu-item{display:flex;align-items:center;justify-content:space-between;padding:18px 20px;background:var(--surface);border:1px solid var(--border);border-radius:14px;cursor:pointer;transition:all .15s;text-align:left;width:100%;font-family:'Noto Sans KR',sans-serif;margin-bottom:6px;}
.home-menu-item:hover{border-color:var(--accent);background:var(--adim);}
.home-menu-item:active{transform:scale(.99);}
.home-menu-left{display:flex;align-items:center;gap:16px;}
.home-menu-num{font-family:'Bebas Neue',sans-serif;font-size:13px;color:var(--muted);letter-spacing:1px;min-width:20px;}
.home-menu-title{font-size:15px;font-weight:700;color:var(--text);}
.home-menu-sub{font-size:11px;color:var(--muted2);margin-top:2px;}
.home-menu-arrow{font-size:16px;color:var(--muted);transition:color .15s;}
.home-menu-item:hover .home-menu-arrow{color:var(--accent);}
.home-menu-item.primary{border-color:var(--aborder);background:var(--adim);}
.home-menu-item.primary .home-menu-title{color:var(--accent);}
.home-menu-item.primary .home-menu-arrow{color:var(--accent);}
.home-quote{border-left:2px solid var(--border);padding:10px 14px;margin-bottom:8px;}
.home-quote-text{font-size:12px;color:var(--muted2);line-height:1.7;}
.home-recent-title{font-family:'Bebas Neue',sans-serif;font-size:13px;letter-spacing:1px;color:var(--muted);margin-bottom:8px;}

/* MISC */
.flex-end{display:flex;justify-content:flex-end;gap:8px;}
.empty{text-align:center;padding:24px;color:var(--muted);font-size:13px;}
input[type=number]::-webkit-inner-spin-button{-webkit-appearance:none;}
input[type=date]{cursor:pointer;}
#rest-banner{display:none;position:fixed;top:0;left:0;right:0;background:var(--accent);color:#0d0d0d;text-align:center;padding:8px;font-family:'Bebas Neue',sans-serif;font-size:18px;letter-spacing:2px;z-index:998;cursor:pointer;}
#toast{position:fixed;bottom:22px;left:50%;transform:translateX(-50%) translateY(16px);background:var(--accent);color:#0d0d0d;font-weight:700;font-size:13px;padding:10px 22px;border-radius:100px;opacity:0;transition:all .3s;pointer-events:none;white-space:nowrap;z-index:999;letter-spacing:.5px;}
#toast.show{opacity:1;transform:translateX(-50%) translateY(0);}

/* INSIGHT */
.insight-card{background:rgba(200,255,0,.04);border:1px solid var(--aborder);border-radius:12px;padding:13px;margin-bottom:10px;}
.insight-title{font-size:13px;font-weight:700;color:var(--accent);margin-bottom:4px;}
.insight-body{font-size:12px;color:var(--muted2);line-height:1.6;}

/* WARN */
.warn-card{background:rgba(255,77,77,.06);border:1px solid rgba(255,77,77,.18);border-radius:10px;padding:12px 14px;margin-bottom:8px;}
.warn-title{font-size:13px;font-weight:700;color:var(--red);margin-bottom:3px;}
</style>
</head>
<body>

<div id="rest-banner" onclick="gotoTimer()">휴식 중 — <span id="banner-time">01:30</span></div>

<header>
  <nav>
    <button class="active" onclick="sw('home',this)">홈</button>
    <button onclick="sw('record',this)">기록</button>
    <button onclick="sw('timer',this)">타이머</button>
    <button onclick="sw('food',this)">식단</button>
    <button onclick="sw('history',this)">달력</button>
    <button onclick="sw('stats',this)">통계</button>
    <button onclick="sw('body',this)">몸무게</button>
    <button onclick="sw('routine',this)">루틴</button>
    <button onclick="sw('guide',this)">가이드</button>
  </nav>
</header>

<main>

<!-- 홈 -->
<div id="tab-home" class="tab active" style="margin-top:0;">
  <div id="home-screen"></div>
</div>

<!-- 기록 -->
<div id="tab-record" class="tab" style="margin-top:12px;">
  <div id="insight-area"></div>
  <div class="card">
    <div style="display:flex;align-items:center;justify-content:space-between;">
      <div class="card-title" style="margin:0;">루틴 불러오기</div>
      <button class="btn btn-ghost btn-xs" onclick="toggleRtnLoad()">펼치기</button>
    </div>
    <div id="rtn-load-inner" style="display:none;margin-top:12px;"></div>
  </div>
  <div class="card">
    <div class="field">
      <label>날짜</label>
      <input type="date" id="rec-date" onchange="renderTodayList();renderInsight();">
    </div>
    <div class="field">
      <label>부위</label>
      <div id="rec-chip-wrap" style="display:flex;flex-wrap:wrap;gap:5px;margin-top:4px;"></div>
    </div>
    <div class="field">
      <label>운동 선택</label>
      <select id="rec-ex" onchange="onExSel()"></select>
    </div>
    <div id="custom-row" class="field" style="display:none;">
      <label>직접 입력</label>
      <input type="text" id="rec-custom" placeholder="운동 이름">
    </div>
    <div id="swap-hint" style="display:none;margin-bottom:10px;">
      <button class="swap-btn" onclick="openSwap()">장비 없음? 대체 운동</button>
    </div>
    <div class="set-header"><span>세트</span><span>무게(kg)</span><span>횟수</span><span></span></div>
    <div id="sets-cont"></div>
    <button class="add-set-btn" onclick="addSet()">+ 세트 추가</button>
    <div class="flex-end" style="margin-top:12px;">
      <button class="btn btn-ghost btn-sm" onclick="startRest(90)">휴식 타이머</button>
      <button class="btn btn-accent btn-full" onclick="saveWO()">저장</button>
    </div>
  </div>
  <div class="sec-lbl" id="today-lbl">오늘 기록</div>
  <div id="today-list"></div>
</div>

<!-- 타이머 -->
<div id="tab-timer" class="tab" style="margin-top:12px;">
  <div class="card">
    <div class="card-title">스톱워치</div>
    <div class="sw-time" id="sw-disp">00:00.00</div>
    <div style="text-align:center;font-size:12px;color:var(--muted2);" id="sw-lap-cnt"></div>
    <div class="sw-btns">
      <button class="sw-btn sw-reset" onclick="swReset()">리셋</button>
      <button class="sw-btn sw-go" id="sw-btn" onclick="swToggle()">시작</button>
      <button class="sw-btn sw-lap" onclick="swLap()">랩</button>
    </div>
    <div id="lap-list" style="max-height:140px;overflow-y:auto;"></div>
  </div>
  <div class="card">
    <div class="card-title">휴식 타이머</div>
    <div style="background:var(--s2);border:1px solid var(--aborder);border-radius:10px;padding:14px;text-align:center;">
      <div style="font-size:11px;color:var(--muted2);text-transform:uppercase;letter-spacing:1px;margin-bottom:6px;">남은 시간</div>
      <div class="rest-disp" id="rest-disp">01:30</div>
      <div class="rest-bar"><div class="rest-fill" id="rest-fill" style="width:100%"></div></div>
      <div class="rest-pre">
        <button class="btn btn-ghost btn-xs" onclick="startRest(15)">15초</button>
        <button class="btn btn-ghost btn-xs" onclick="startRest(30)">30초</button>
        <button class="btn btn-ghost btn-xs" onclick="startRest(60)">1분</button>
        <button class="btn btn-ghost btn-xs" onclick="startRest(90)">1분30초</button>
        <button class="btn btn-ghost btn-xs" onclick="startRest(120)">2분</button>
        <button class="btn btn-ghost btn-xs" onclick="startRest(180)">3분</button>
      </div>
    </div>
    <div class="flex-end" style="margin-top:10px;">
      <button class="btn btn-ghost btn-sm" onclick="stopRest()">정지</button>
      <button class="btn btn-accent btn-sm" onclick="startRest(restDef)">다시 시작</button>
    </div>
    <div class="field" style="margin-top:10px;">
      <label>기본 휴식 (초)</label>
      <input type="number" id="rest-def-input" value="90" min="10" max="600" onchange="restDef=+this.value">
    </div>
  </div>
</div>

<!-- 식단 -->
<div id="tab-food" class="tab" style="margin-top:12px;">
  <div class="card">
    <div class="field"><label>날짜</label><input type="date" id="food-date" onchange="renderFood()"></div>
    <div class="field"><label>끼니</label>
      <select id="food-meal"><option>아침</option><option>점심</option><option>저녁</option><option>간식</option></select>
    </div>
    <!-- 음식 검색 -->
    <div class="field">
      <label>음식 검색</label>
      <input type="text" id="food-search" placeholder="닭가슴살, 오트밀, 연어..." oninput="searchFood(this.value)" autocomplete="off">
      <div id="food-search-result" style="display:none;background:var(--s2);border:1px solid var(--border);border-radius:8px;margin-top:4px;max-height:200px;overflow-y:auto;"></div>
    </div>
    <!-- 선택된 음식 표시 -->
    <div id="food-selected-info" style="display:none;background:var(--adim);border:1px solid var(--aborder);border-radius:10px;padding:12px 14px;margin-bottom:11px;">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px;">
        <div style="font-weight:700;font-size:14px;color:var(--accent);" id="food-selected-name"></div>
        <button class="btn-ghost btn-xs btn" onclick="clearFoodSelection()" style="font-size:11px;padding:3px 8px;">변경</button>
      </div>
      <div style="font-size:11px;color:var(--muted2);margin-bottom:10px;">100g 기준: <span id="food-selected-per100"></span></div>
      <div class="field" style="margin:0;">
        <label>섭취량 (g)</label>
        <input type="number" id="food-gram" placeholder="100" min="1" value="100" oninput="calcFoodMacro()" style="width:120px;">
      </div>
      <div id="food-calc-result" style="display:flex;gap:10px;margin-top:10px;flex-wrap:wrap;"></div>
    </div>
    <!-- 직접 입력 모드 -->
    <div id="food-manual-area">
      <div class="field"><label>음식 이름 (직접 입력)</label><input type="text" id="food-name" placeholder="또는 직접 입력..."></div>
      <div class="r3">
        <div class="field"><label>칼로리</label><input type="number" id="food-kcal" placeholder="0" min="0"></div>
        <div class="field"><label>탄수화물(g)</label><input type="number" id="food-carb" placeholder="0" min="0"></div>
        <div class="field"><label>단백질(g)</label><input type="number" id="food-prot" placeholder="0" min="0"></div>
      </div>
      <div class="field"><label>지방(g)</label><input type="number" id="food-fat" placeholder="0" min="0" style="width:33%;"></div>
    </div>
    <button class="btn btn-accent btn-full" onclick="saveFood()">추가</button>
  </div>
  <div class="card">
    <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:10px;">
      <div class="card-title" style="margin:0;">오늘 칼로리</div>
      <div style="display:flex;align-items:center;gap:6px;">
        <span style="font-size:11px;color:var(--muted2);">목표</span>
        <input type="number" id="kcal-goal" value="2500" min="0" style="width:75px;text-align:center;padding:5px;font-size:13px;">
      </div>
    </div>
    <div style="display:flex;justify-content:center;margin:8px 0;"><canvas id="kcal-cv" width="130" height="130"></canvas></div>
    <div class="macro-sum" id="macro-sum"></div>
  </div>
  <div class="sec-lbl">식단 기록</div>
  <div id="food-list"></div>
</div>

<!-- 달력 -->
<div id="tab-history" class="tab" style="margin-top:12px;">
  <div class="card">
    <div class="cal-nav">
      <button class="btn btn-ghost btn-sm" onclick="chMon(-1)">←</button>
      <div class="cal-title" id="cal-title"></div>
      <button class="btn btn-ghost btn-sm" onclick="chMon(1)">→</button>
    </div>
    <div class="cal-dow"><span>일</span><span>월</span><span>화</span><span>수</span><span>목</span><span>금</span><span>토</span></div>
    <div class="cal-grid" id="cal-grid"></div>
  </div>
  <div class="sec-lbl" id="cal-log-title">전체 기록</div>
  <div id="cal-log"></div>
</div>

<!-- 통계 -->
<div id="tab-stats" class="tab" style="margin-top:12px;">
  <div class="stats-grid" id="stats-boxes"></div>
  <div class="card">
    <div class="card-title">볼륨 밸런스</div>
    <div id="balance-warns"></div>
    <div id="balance-bars"></div>
  </div>
  <div class="card">
    <div class="card-title">주간 볼륨 (8주)</div>
    <div class="chart-wrap" id="vol-chart"></div>
  </div>
  <div class="card">
    <div class="card-title">PR — 운동별 최고 무게</div>
    <div id="pr-list"></div>
  </div>
  <div class="card">
    <div class="card-title">이번 주</div>
    <div id="week-list"></div>
  </div>
</div>

<!-- 몸무게 -->
<div id="tab-body" class="tab" style="margin-top:12px;">
  <div class="card">
    <div class="r3">
      <div class="field"><label>날짜</label><input type="date" id="body-date"></div>
      <div class="field"><label>몸무게(kg)</label><input type="number" id="body-weight" placeholder="75.0" step="0.1" min="0"></div>
      <div class="field"><label>체지방(%)</label><input type="number" id="body-fat" placeholder="15" step="0.1" min="0"></div>
    </div>
    <div class="field"><label>메모</label><input type="text" id="body-memo" placeholder="컨디션, 특이사항..."></div>
    <button class="btn btn-accent btn-full" onclick="saveBody()">기록하기</button>
  </div>
  <div class="card">
    <div class="card-title">체중 변화</div>
    <canvas id="body-chart" height="110" style="width:100%;display:block;"></canvas>
  </div>
  <div class="sec-lbl">기록 목록</div>
  <div id="body-list"></div>
</div>

<!-- 루틴 -->
<div id="tab-routine" class="tab" style="margin-top:12px;">
  <div style="display:flex;gap:0;border-bottom:1px solid var(--border);margin-bottom:14px;">
    <button class="rtab on" id="rtab-preset" onclick="switchRtab('preset',this)">프리셋</button>
    <button class="rtab" id="rtab-custom" onclick="switchRtab('custom',this)">내 루틴 만들기</button>
    <button class="rtab" id="rtab-saved" onclick="switchRtab('saved',this)">저장된 루틴</button>
  </div>
  <div id="rsec-preset"><div id="preset-routines"></div></div>
  <div id="rsec-custom" style="display:none;">
    <div class="card">
      <div class="card-title">기본 설정</div>
      <div class="r2">
        <div class="field"><label>루틴 이름</label><input type="text" id="rtn-name" placeholder="가슴+삼두 Day A"></div>
        <div class="field">
          <label>기본 휴식 (개별 미설정 시 적용)</label>
          <select id="rtn-rest">
            <option value="60">1분</option>
            <option value="90" selected>1분 30초</option>
            <option value="120">2분</option>
            <option value="180">3분</option>
            <option value="240">4분</option>
            <option value="300">5분</option>
          </select>
        </div>
      </div>
      <div class="field"><label>메모</label><input type="text" id="rtn-memo" placeholder="매주 화/금..."></div>
    </div>
    <div class="card">
      <div class="card-title">운동 추가</div>
      <div style="margin-bottom:10px;">
        <div style="font-size:11px;color:var(--muted2);text-transform:uppercase;letter-spacing:1px;margin-bottom:5px;">부위</div>
        <div id="pattern-chip-wrap" style="display:flex;flex-wrap:wrap;gap:6px;"></div>
      </div>
      <div class="field"><label>운동 선택</label><select id="rtn-ex-sel"></select></div>
      <div id="rtn-custom-row" class="field" style="display:none;">
        <label>직접 입력</label><input type="text" id="rtn-ex-custom" placeholder="운동 이름">
      </div>
      <div class="r3">
        <div class="field" style="margin:0;"><label>세트</label><input type="number" id="rtn-sets" value="3" min="1" max="20"></div>
        <div class="field" style="margin:0;"><label>횟수</label><input type="text" id="rtn-reps" value="10" placeholder="10 or 8-12"></div>
        <div class="field" style="margin:0;"><label>무게(kg)</label><input type="number" id="rtn-kg" placeholder="0" min="0" step="0.5"></div>
      </div>
      <div class="r2" style="margin-top:8px;">
        <div class="field" style="margin:0;">
          <label>개별 휴식</label>
          <select id="rtn-ex-rest">
            <option value="">기본값</option>
            <option value="15">15초</option>
            <option value="30">30초</option>
            <option value="45">45초</option>
            <option value="60">1분</option>
            <option value="90">1분 30초</option>
            <option value="120">2분</option>
            <option value="180">3분</option>
            <option value="240">4분</option>
            <option value="300">5분</option>
          </select>
        </div>
        <div class="field" style="margin:0;"><label>메모</label><input type="text" id="rtn-ex-note" placeholder="탑세트, RPE 8..."></div>
      </div>
      <button class="btn btn-ghost btn-full" onclick="addRtnEx()" style="margin-top:10px;">+ 운동 추가</button>
    </div>
    <div class="card" id="rtn-preview-card" style="display:none;">
      <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:12px;">
        <div class="card-title" style="margin:0;">구성 <span id="rtn-ex-count" style="font-size:13px;color:var(--muted2);"></span></div>
        <button class="btn btn-ghost btn-xs" onclick="clearRtnExs()">전체 삭제</button>
      </div>
      <div id="rtn-exlist"></div>
    </div>
    <button class="btn btn-accent btn-full" onclick="saveMyRoutine()" style="margin-bottom:20px;">저장하기</button>
  </div>
  <div id="rsec-saved" style="display:none;"><div id="my-routines"></div></div>
</div>

<!-- 가이드 -->
<div id="tab-guide" class="tab" style="margin-top:12px;">
  <div class="card">
    <div class="card-title">티어 시스템</div>
    <p style="font-size:13px;color:var(--muted2);line-height:1.8;margin-bottom:14px;">모든 운동을 중요도와 역할에 따라 3단계로 분류합니다.</p>
    <div style="display:flex;flex-direction:column;gap:10px;">
      <div style="background:rgba(200,255,0,.06);border:1px solid var(--aborder);border-radius:10px;padding:14px;">
        <div style="display:flex;align-items:center;gap:8px;margin-bottom:8px;"><span class="tier-badge t1" style="font-size:13px;padding:4px 10px;">T1</span><span style="font-weight:700;font-size:14px;">메인 리프트</span></div>
        <p style="font-size:13px;color:var(--muted2);line-height:1.7;">가장 무겁고 복잡한 다관절 운동. 세션 첫 번째로 수행.<br><span style="color:var(--accent);">예: 바벨 벤치프레스, 스쿼트, 데드리프트</span><br><span style="color:var(--muted);">3~6회 x 3~5세트 / 휴식 2~5분</span></p>
      </div>
      <div style="background:rgba(77,159,255,.06);border:1px solid rgba(77,159,255,.22);border-radius:10px;padding:14px;">
        <div style="display:flex;align-items:center;gap:8px;margin-bottom:8px;"><span class="tier-badge t2" style="font-size:13px;padding:4px 10px;">T2</span><span style="font-weight:700;font-size:14px;">보조 리프트 — 볼륨</span></div>
        <p style="font-size:13px;color:var(--muted2);line-height:1.7;">T1과 같은 근육군을 다른 각도로 자극. 중간 무게로 볼륨.<br><span style="color:var(--blue);">예: 인클라인 벤치, 랫풀다운, 레그프레스</span><br><span style="color:var(--muted);">8~12회 x 3~4세트 / 휴식 1~2분</span></p>
      </div>
      <div style="background:rgba(168,85,247,.06);border:1px solid rgba(168,85,247,.22);border-radius:10px;padding:14px;">
        <div style="display:flex;align-items:center;gap:8px;margin-bottom:8px;"><span class="tier-badge t3" style="font-size:13px;padding:4px 10px;">T3</span><span style="font-weight:700;font-size:14px;">고립 운동 — 마무리</span></div>
        <p style="font-size:13px;color:var(--muted2);line-height:1.7;">단관절 운동으로 특정 근육 집중 자극. 세션 마지막.<br><span style="color:var(--purple);">예: 케이블 플라이, 레이즈류, 컬, 익스텐션</span><br><span style="color:var(--muted);">12~20회 x 3세트 / 휴식 45~90초</span></p>
      </div>
    </div>
    <div style="background:var(--s3);border-radius:8px;padding:12px;margin-top:12px;font-size:12px;color:var(--muted2);line-height:1.7;">한 세션에 T1 1개, T2 1~2개, T3 1~2개가 이상적입니다.</div>
  </div>
  <div class="card">
    <div class="card-title">7대 움직임 패턴</div>
    <p style="font-size:13px;color:var(--muted2);line-height:1.7;margin-bottom:12px;">밀기(Push) : 당기기(Pull) = 1:1 이상을 유지하세요.</p>
    <div id="guide-pattern-list"></div>
  </div>
  <div class="card">
    <div class="card-title">루틴 가이드</div>
    <div id="guide-routine-list"></div>
  </div>
  <div class="card">
    <div class="card-title">RPE / RIR</div>
    <div class="r2" style="margin-bottom:12px;">
      <div style="background:var(--s2);border-radius:8px;padding:12px;">
        <div style="font-weight:700;color:var(--accent);margin-bottom:6px;font-size:13px;">RPE (주관적 강도)</div>
        <div style="font-size:12px;color:var(--muted2);line-height:1.8;">RPE 6 — 여유<br>RPE 7 — 3회 여유<br>RPE 8 — 2회 여유<br>RPE 9 — 1회 여유<br>RPE 10 — 완전 실패</div>
      </div>
      <div style="background:var(--s2);border-radius:8px;padding:12px;">
        <div style="font-weight:700;color:var(--blue);margin-bottom:6px;font-size:13px;">RIR (여유 횟수)</div>
        <div style="font-size:12px;color:var(--muted2);line-height:1.8;">RIR 3 = RPE 7<br>RIR 2 = RPE 8<br>RIR 1 = RPE 9<br>RIR 0 = RPE 10<br>= 완전 실패</div>
      </div>
    </div>
  </div>
  <div class="card">
    <div class="card-title">어떤 루틴을 골라야 할까?</div>
    <div style="display:flex;flex-direction:column;gap:8px;">
      <div style="background:var(--s2);border-left:3px solid var(--accent);border-radius:0 8px 8px 0;padding:12px;">
        <div style="font-weight:700;margin-bottom:4px;">헬스 1년 미만</div>
        <div style="font-size:12px;color:var(--muted2);">GZCLP 추천. 체계적 선형 증량으로 가장 빠르게 성장.</div>
      </div>
      <div style="background:var(--s2);border-left:3px solid var(--blue);border-radius:0 8px 8px 0;padding:12px;">
        <div style="font-weight:700;margin-bottom:4px;">1~3년 중급자</div>
        <div style="font-size:12px;color:var(--muted2);">탑 세트 & 백오프 또는 PPL 추천.</div>
      </div>
      <div style="background:var(--s2);border-left:3px solid var(--orange);border-radius:0 8px 8px 0;padding:12px;">
        <div style="font-weight:700;margin-bottom:4px;">시간이 없는 직장인</div>
        <div style="font-size:12px;color:var(--muted2);">마이오 세트 또는 도리안 HIT. 30분 안에 끝.</div>
      </div>
      <div style="background:var(--s2);border-left:3px solid var(--red);border-radius:0 8px 8px 0;padding:12px;">
        <div style="font-weight:700;margin-bottom:4px;">정체기 돌파</div>
        <div style="font-size:12px;color:var(--muted2);">GVT (10x10). 3~4주만 수행하세요.</div>
      </div>
    </div>
  </div>
</div>

</main>

<!-- 스왑 모달 -->
<div class="swap-modal" id="swap-modal">
  <div class="swap-sheet">
    <div style="font-family:'Bebas Neue',sans-serif;font-size:18px;letter-spacing:1px;margin-bottom:12px;" id="swap-title">대체 운동</div>
    <div id="swap-list"></div>
    <button class="btn btn-ghost btn-full" onclick="closeSwap()" style="margin-top:10px;">닫기</button>
  </div>
</div>

<div id="toast"></div>

<script>
// ─── DB ──────────────────────────────────────
const K={wo:'ar_wo',food:'ar_food',body:'ar_body',rtn:'ar_rtn'};
let db={
  wo:JSON.parse(localStorage.getItem(K.wo)||'[]'),
  food:JSON.parse(localStorage.getItem(K.food)||'[]'),
  body:JSON.parse(localStorage.getItem(K.body)||'[]'),
  rtn:JSON.parse(localStorage.getItem(K.rtn)||'[]')
};
function sdb(k){localStorage.setItem(K[k],JSON.stringify(db[k]));}

// ─── 운동 데이터 ─────────────────────────────
const PATTERNS={
  '수평 밀기 (가슴)':{
    1:['바벨 벤치프레스','인클라인 바벨 벤치프레스','디클라인 바벨 벤치프레스'],
    2:['덤벨 벤치프레스','인클라인 덤벨 프레스','디클라인 덤벨 프레스','체스트 프레스 머신','스미스 머신 벤치프레스','딥스 (가슴)'],
    3:['케이블 크로스오버','케이블 플라이','펙덱 플라이','덤벨 플라이','인클라인 덤벨 플라이','랜드마인 프레스','푸시업','와이드 푸시업','케이블 크로스오버 (하->상)']
  },
  '수직 밀기 (어깨)':{
    1:['오버헤드프레스 (바벨)','시티드 바벨 숄더프레스','스탠딩 바벨 숄더프레스'],
    2:['덤벨 숄더프레스','시티드 덤벨 숄더프레스','아놀드 프레스','머신 숄더프레스','스미스 머신 숄더프레스'],
    3:['사이드 레터럴 레이즈','케이블 사이드 레이즈','밴드 사이드 레이즈','프론트 레이즈','케이블 프론트 레이즈','업라이트 로우','페이스 풀 (어깨)','배튼 레이즈','덤벨 프론트 레이즈']
  },
  '수평 당기기 (등 두께)':{
    1:['바벨 로우','펜들레이 로우','티바 로우'],
    2:['원암 덤벨 로우','시티드 케이블 로우','머신 로우','스미스 머신 로우','메도우즈 로우','인버티드 로우'],
    3:['리어델트 덤벨 플라이','리어델트 머신 플라이','페이스 풀','밴드 페이스 풀','케이블 로우 (좁은 그립)','케이블 로우 (넓은 그립)','시티드 덤벨 로우','체스트 서포티드 로우','리어델트 케이블 플라이']
  },
  '수직 당기기 (등 너비)':{
    1:['가중 풀업','친업 (언더그립)','와이드 그립 풀업'],
    2:['랫 풀다운 (넓은 그립)','랫 풀다운 (좁은 그립)','언더그립 랫 풀다운','싱글암 케이블 풀다운','암 풀다운'],
    3:['케이블 풀오버','덤벨 풀오버','스트레이트암 풀다운','풀업 (자체중량)','밴드 풀다운','시티드 케이블 풀오버','랫 풀다운 (중립 그립)','싱글암 랫 풀다운']
  },
  '무릎 주동 (하체 앞)':{
    1:['바벨 백스쿼트','바벨 프론트 스쿼트','로우바 스쿼트'],
    2:['레그프레스','해크 스쿼트','불가리안 스플릿 스쿼트','런지','워킹 런지','스미스 머신 스쿼트','고블릿 스쿼트','수메 스쿼트'],
    3:['레그 익스텐션','싱글레그 레그 익스텐션','케이블 레그 익스텐션','박스 스쿼트','시시 스쿼트','월 싯','스텝업','페이퍼 스쿼트']
  },
  '고관절 주동 (하체 뒤)':{
    1:['컨벤셔널 데드리프트','스모 데드리프트','트랩바 데드리프트'],
    2:['루마니안 데드리프트','스티프레그 데드리프트','싱글레그 루마니안 데드','힙 쓰러스트 (바벨)','글루트 브릿지 (바벨)','케이블 킥백'],
    3:['레그컬 (라잉)','레그컬 (시티드)','레그컬 (스탠딩)','싱글레그 레그컬','힙 쓰러스트 (덤벨)','힙 어브덕션 머신','케이블 힙 익스텐션','굿모닝','하이퍼익스텐션','덤벨 레그컬']
  },
  '이두 (Biceps)':{
    1:['바벨 컬','이지바 컬'],
    2:['덤벨 컬','해머 컬','인클라인 덤벨 컬','컨센트레이션 컬','프리처 컬 (이지바)'],
    3:['케이블 컬','케이블 해머 컬','싱글암 케이블 컬','리버스 컬','크로스바디 해머 컬','스파이더 컬','프리처 컬 (덤벨)','밴드 컬','친업 (이두 위주)']
  },
  '삼두 (Triceps)':{
    1:['클로즈그립 벤치프레스','딥스 (삼두)'],
    2:['라잉 트라이셉스 익스텐션 (바벨)','라잉 트라이셉스 익스텐션 (덤벨)','오버헤드 트라이셉스 익스텐션 (바벨)','오버헤드 트라이셉스 익스텐션 (덤벨)','오버헤드 케이블 익스텐션'],
    3:['트라이셉스 푸쉬다운 (로프)','트라이셉스 푸쉬다운 (바)','싱글암 케이블 푸쉬다운','킥백','리버스 그립 푸쉬다운','다이아몬드 푸시업','스컬크러셔','밴드 트라이셉스 익스텐션']
  },
  '어깨 후면 (Rear Delt)':{
    1:['페이스 풀'],
    2:['리어델트 덤벨 플라이','벤트오버 리어 레이즈','인클라인 리어 레이즈'],
    3:['케이블 리어 레이즈','밴드 리어 레이즈','리어델트 머신','시티드 리어 레이즈','역방향 펙덱 플라이','밴드 페이스 풀','케이블 페이스 풀','W-레이즈','Y-T-W 레이즈']
  },
  '코어 (Core)':{
    1:['행잉 레그레이즈','캡틴스 체어 레그레이즈'],
    2:['플랭크','사이드 플랭크','케이블 우드찹','AB 롤아웃','잭나이프'],
    3:['크런치','바이시클 크런치','시티드 레그레이즈','리버스 크런치','토 터치','드래곤 플래그','밸런스볼 크런치','러시안 트위스트','마운틴 클라이머','버드독','데드버그','케이블 크런치','브이업','레그레이즈']
  },
  '종아리 (Calves)':{
    1:['스탠딩 카프레이즈 (바벨)'],
    2:['시티드 카프레이즈','레그프레스 카프레이즈','스미스 머신 카프레이즈'],
    3:['스탠딩 카프레이즈 (덤벨)','싱글레그 카프레이즈','동키 카프레이즈','박스 카프레이즈','스텝 카프레이즈','밴드 카프레이즈','시티드 카프레이즈 (덤벨)']
  },
  '유산소 / 기타':{
    1:['런닝 (트레드밀)','사이클 (스테이셔너리)'],
    2:['로잉 머신','일립티컬','스텝퍼','스키 에르그'],
    3:['줄넘기','버피','케틀벨 스윙','케틀벨 클린','케틀벨 스내치','배틀로프','박스 점프','슬레드 푸시','파머스 워크','메디신볼 슬램']
  }
};

const SWAP_MAP={
  '바벨 벤치프레스':['덤벨 벤치프레스','체스트 프레스 머신','딥스 (가슴)'],
  '인클라인 바벨 벤치프레스':['인클라인 덤벨 프레스','스미스 머신 벤치프레스'],
  '바벨 로우':['원암 덤벨 로우','시티드 케이블 로우','머신 로우'],
  '오버헤드프레스 (바벨)':['덤벨 숄더프레스','머신 숄더프레스','아놀드 프레스'],
  '바벨 백스쿼트':['레그프레스','고블릿 스쿼트','스미스 머신 스쿼트'],
  '컨벤셔널 데드리프트':['루마니안 데드리프트','힙 쓰러스트 (바벨)','레그컬 (라잉)'],
  '가중 풀업':['랫 풀다운 (넓은 그립)','암 풀다운'],
  '클로즈그립 벤치프레스':['트라이셉스 푸쉬다운 (로프)','오버헤드 케이블 익스텐션']
};

function getPatternOf(name){
  for(const[p,t] of Object.entries(PATTERNS))for(const exs of Object.values(t))if(exs.includes(name))return p;
  return null;
}
function getTierOf(name){
  for(const[,t] of Object.entries(PATTERNS))for(const[ti,exs] of Object.entries(t))if(exs.includes(name))return +ti;
  return null;
}

// ─── PRESETS ─────────────────────────────────
const PRESETS=[
  {id:'top-backoff',name:'탑 세트 & 백오프',level:'중급자 이상',time:'50분',restSec:180,tag:['근비대','스트렝스'],
   desc:'가장 무거운 세트 1개(Top) 후 중량을 낮춰 볼륨(Back-off) 채우기.',
   logic:'1세트(3~5회 RPE 9) -> 2~3세트(8~12회 무게 -15%)',
   exercises:[{name:'바벨 벤치프레스',sets:1,reps:'3-5',kg:0,note:'탑 세트 RPE 9'},{name:'바벨 벤치프레스',sets:3,reps:'8-12',kg:0,note:'백오프 -15%'},{name:'바벨 로우',sets:3,reps:'8-12',kg:0}]},
  {id:'gzclp',name:'GZCLP',level:'초보~중급자',time:'60분',restSec:180,tag:['선형진보','체계적'],
   desc:'T1/T2/T3 피라미드 구조의 계층적 선형 진보.',
   logic:'T1(3회 5세트) T2(10회 3세트) T3(15회 3세트 AMRAP)',
   exercises:[{name:'바벨 벤치프레스',sets:5,reps:'3',kg:0,note:'T1'},{name:'오버헤드프레스 (바벨)',sets:3,reps:'10',kg:0,note:'T2'},{name:'케이블 플라이',sets:3,reps:'15+',kg:0,note:'T3 AMRAP'}]},
  {id:'rp-hyp',name:'RP 근비대',level:'데이터 중심',time:'55분',restSec:120,tag:['근비대','4주 사이클'],
   desc:'매주 RIR을 줄여가며 강도를 높이고 5주차에 디로딩.',
   logic:'1주(RIR 3) -> 2주(RIR 2) -> 3주(RIR 1) -> 4주(RIR 0) -> 5주(디로딩)',
   exercises:[{name:'바벨 벤치프레스',sets:4,reps:'8-12',kg:0,note:'주마다 RIR 1씩 감소'},{name:'인클라인 덤벨 프레스',sets:3,reps:'10-15',kg:0},{name:'케이블 플라이',sets:3,reps:'12-20',kg:0}]},
  {id:'myo',name:'마이오 세트',level:'바쁜 직장인',time:'30분',restSec:15,tag:['고효율','짧은 휴식'],
   desc:'15초 휴식으로 근섬유 활성화 극대화. 30분 안에 끝.',
   logic:'활성 세트(12~20회) -> 15초 휴식 -> 미니 세트(3~5회) 5회 반복',
   exercises:[{name:'덤벨 벤치프레스',sets:1,reps:'12-20',kg:0,note:'활성 세트 후 15초 x5'},{name:'덤벨 숄더프레스',sets:1,reps:'12-20',kg:0,note:'활성 세트'},{name:'랫 풀다운 (넓은 그립)',sets:1,reps:'12-20',kg:0,note:'활성 세트'}]},
  {id:'531bbb',name:'5/3/1 BBB',level:'클래식 벌크업',time:'75분',restSec:90,tag:['벌크','클래식'],
   desc:'고중량 메인 후 저중량 고반복 50회 추가.',
   logic:'5/3/1 메인 세트 -> 같은 종목 10회 5세트 (1RM 50%)',
   exercises:[{name:'바벨 벤치프레스',sets:3,reps:'5/3/1',kg:0,note:'메인'},{name:'바벨 벤치프레스',sets:5,reps:'10',kg:0,note:'BBB 1RM 50%'},{name:'바벨 로우',sets:5,reps:'10',kg:0}]},
  {id:'phul',name:'PHUL 4분할',level:'주 4회',time:'65분',restSec:120,tag:['파워+근비대'],
   desc:'주초 스트렝스, 주후반 근비대로 성격 분리.',
   logic:'월/화(Power 3~5회) -> 목/금(Hypertrophy 8~12회)',
   exercises:[{name:'바벨 벤치프레스',sets:4,reps:'3-5',kg:0,note:'Power Day'},{name:'바벨 백스쿼트',sets:4,reps:'3-5',kg:0,note:'Power Day'},{name:'덤벨 벤치프레스',sets:4,reps:'8-12',kg:0,note:'Hypertrophy Day'}]},
  {id:'ppl',name:'PPL 3분할',level:'유연한 분할',time:'60분',restSec:90,tag:['대중적','유연'],
   desc:'미는 날 - 당기는 날 - 하체 날 무한 반복.',
   logic:'Push -> Pull -> Legs -> Rest 순환. 요일 무관.',
   exercises:[{name:'바벨 벤치프레스',sets:4,reps:'8-12',kg:0,note:'Push Day'},{name:'가중 풀업',sets:4,reps:'6-10',kg:0,note:'Pull Day'},{name:'바벨 백스쿼트',sets:4,reps:'8-12',kg:0,note:'Legs Day'}]},
  {id:'giant',name:'6-12-25 트라이 세트',level:'체지방+펌핑',time:'40분',restSec:120,tag:['고강도','대사 스트레스'],
   desc:'세 가지 운동 휴식 없이 연달아 수행. 대사 스트레스 극대화.',
   logic:'A(6회) -> B(12회) -> C(25회) -> 2분 휴식. 4세트.',
   exercises:[{name:'바벨 벤치프레스',sets:4,reps:'6',kg:0,note:'A — 무거운 무게'},{name:'덤벨 벤치프레스',sets:4,reps:'12',kg:0,note:'B — 중간 무게'},{name:'케이블 플라이',sets:4,reps:'25',kg:0,note:'C — 가벼운 무게'}]},
  {id:'gvt',name:'GVT 10x10',level:'상급자 정체기',time:'60분',restSec:90,tag:['10x10','상급자'],
   desc:'단순 반복으로 근성장 한계 돌파. 3~4주만 수행.',
   logic:'1RM 60% x 10회 x 10세트 / 휴식 60~90초 고정',
   exercises:[{name:'바벨 벤치프레스',sets:10,reps:'10',kg:0,note:'10x10 1RM 60%'},{name:'가중 풀업',sets:3,reps:'10',kg:0,note:'보조'}]},
  {id:'hit',name:'도리안 HIT',level:'고수용 25분',time:'25분',restSec:120,tag:['최고강도','1세트'],
   desc:'세트 수 최소화, 완전 실패 지점까지.',
   logic:'종목당 본 세트 1세트 (드롭세트 또는 강제 반복)',
   exercises:[{name:'바벨 벤치프레스',sets:1,reps:'실패',kg:0,note:'드롭세트 포함'},{name:'원암 덤벨 로우',sets:1,reps:'실패',kg:0,note:'강제 반복 가능'},{name:'바벨 백스쿼트',sets:1,reps:'실패',kg:0}]}
];

const QUOTES=[
  {text:'될 때까지 하는 거다. 안 되면 될 때까지.',src:'— 올라잇'},
  {text:'오늘 하기 싫은 걸 한 사람이, 내일 하고 싶은 걸 한다.',src:'— 알 수 없음'},
  {text:'간절함이 재능을 이긴다.',src:'— 올라잇'},
  {text:'포기하면 편하다. 근데 편한 게 다냐.',src:'— 올라잇'},
  {text:'정진. 쉬지 않고 나아감.',src:'— 올라잇'},
  {text:'살자. 제발. 될 때까지.',src:'— 올라잇'},
  {text:'누군가는 지금 이 시간에도 하고 있다.',src:'— 알 수 없음'},
  {text:'One more. 항상 한 번 더.',src:'— 올라잇'},
  {text:'압도적으로 해라. 대충 하려면 시작도 하지 마라.',src:'— 올라잇'},
  {text:'증명은 말이 아니라 몸으로 한다.',src:'— 올라잇'},
];

// ─── UTIL ────────────────────────────────────
function toStr(d){const dt=new Date(d);return`${dt.getFullYear()}-${s2(dt.getMonth()+1)}-${s2(dt.getDate())}`;}
function today(){return toStr(new Date());}
function s2(n){return String(n).padStart(2,'0');}
function fmtD(s){const[y,m,d]=s.split('-');return`${y}년 ${+m}월 ${+d}일`;}
function toast(msg){const t=document.getElementById('toast');t.textContent=msg;t.classList.add('show');setTimeout(()=>t.classList.remove('show'),2200);}
function secToStr(s){return s>=60?Math.floor(s/60)+'분'+(s%60?s%60+'초':''):s+'초';}

// ─── TAB ────────────────────────────────────
function sw(name,el){
  document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
  document.querySelectorAll('nav button').forEach(b=>b.classList.remove('active'));
  document.getElementById('tab-'+name).classList.add('active');
  el.classList.add('active');
  if(name==='home')renderHome();
  if(name==='history')renderCal();
  if(name==='stats')renderStats();
  if(name==='body')renderBody();
  if(name==='routine')renderRoutineTab();
  if(name==='guide')renderGuide();
  if(name==='food')renderFood();
  if(name==='record'){renderTodayList();renderInsight();}
}

// ─── HOME ───────────────────────────────────
function renderHome(){
  const now=new Date();
  const days=['일','월','화','수','목','금','토'];
  const months=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  const dateStr=`${now.getFullYear()} ${months[now.getMonth()]} ${now.getDate()} ${days[now.getDay()]}`;
  const totalDays=new Set(db.wo.map(d=>d.date)).size;
  const wk=new Date();wk.setDate(wk.getDate()-wk.getDay());
  const wks=toStr(wk),wke=toStr(new Date(wk.getTime()+6*86400000));
  const thisWeek=new Set(db.wo.filter(x=>x.date>=wks&&x.date<=wke).map(x=>x.date)).size;
  const totalVol=Math.round(db.wo.reduce((s,item)=>s+item.sets.reduce((s2,x)=>s2+x.kg*x.reps,0),0)/1000*10)/10;
  const todayItems=db.wo.filter(x=>x.date===today());
  const streakDays=Array.from({length:7},(_,i)=>{
    const d=new Date();d.setDate(d.getDate()-(6-i));
    const ds=toStr(d);
    return{label:days[d.getDay()],done:db.wo.some(x=>x.date===ds),isToday:ds===today()};
  });
  const q=QUOTES[now.getDate()%QUOTES.length];
  const recent=[...db.wo].sort((a,b)=>b.date.localeCompare(a.date)).slice(0,3);

  const MENU=[
    {nav:1,name:'record',title:'운동 기록',sub:'세트 · 무게 · 횟수',primary:true},
    {nav:7,name:'routine',title:'루틴',sub:'만들기 · 불러오기 · 프리셋'},
    {nav:2,name:'timer',title:'타이머',sub:'스톱워치 · 휴식 타이머'},
    {nav:3,name:'food',title:'식단',sub:'칼로리 · 탄단지 기록'},
    {nav:4,name:'history',title:'달력',sub:'날짜별 기록 확인'},
    {nav:5,name:'stats',title:'통계',sub:'볼륨 · PR · 밸런스 분석'},
    {nav:6,name:'body',title:'몸무게',sub:'체중 · 체지방 그래프'},
    {nav:8,name:'guide',title:'가이드',sub:'루틴 설명 · 티어 · RPE'},
  ];

  document.getElementById('home-screen').innerHTML=`
    <div class="home-wrap">
      <div class="home-header">
        <div class="home-date">${dateStr}</div>
        <div class="home-today-status">
          ${todayItems.length ? `오늘 <em>${todayItems.length}종목</em> 완료` : '오늘 기록 없음'}
        </div>
      </div>

      <div class="streak-wrap">
        ${streakDays.map(d=>`<div class="streak-day${d.done?' done':''}${d.isToday&&!d.done?' cur':''}">${d.label}</div>`).join('')}
      </div>

      <div class="home-stats">
        <div class="home-stat"><div class="home-stat-num">${totalDays}</div><div class="home-stat-lbl">운동 일수</div></div>
        <div class="home-stat"><div class="home-stat-num">${thisWeek}</div><div class="home-stat-lbl">이번 주</div></div>
        <div class="home-stat"><div class="home-stat-num">${totalVol}t</div><div class="home-stat-lbl">총 볼륨</div></div>
      </div>

      <div class="home-menu">
        ${MENU.map((m,i)=>`
          <button class="home-menu-item${m.primary?' primary':''}" onclick="sw('${m.name}',document.querySelectorAll('nav button')[${m.nav}])">
            <div class="home-menu-left">
              <span class="home-menu-num">0${i+1}</span>
              <div>
                <div class="home-menu-title">${m.title}</div>
                <div class="home-menu-sub">${m.sub}</div>
              </div>
            </div>
            <span class="home-menu-arrow">→</span>
          </button>`).join('')}
      </div>

      <div class="home-quote">
        <div class="home-quote-text">"${q.text}"</div>
      </div>

      ${recent.length?`
      <div class="home-recent-title">최근 기록</div>
      ${recent.map(item=>`
        <div class="log-item">
          <div class="log-date">${fmtD(item.date)}</div>
          <div class="log-name">${item.name}</div>
          <div class="badge-row">${item.sets.map((s,i)=>`<span class="badge">${i+1}세트 ${s.kg}kg x ${s.reps}회</span>`).join('')}</div>
        </div>`).join('')}`:''}
    </div>`;
}

// ─── RECORD ─────────────────────────────────
let sets=[];
function addSet(kg='',reps=''){sets.push({kg,reps});renderSets();}
function removeSet(i){sets.splice(i,1);renderSets();}
function renderSets(){
  const c=document.getElementById('sets-cont');c.innerHTML='';
  sets.forEach((s,i)=>{
    const r=document.createElement('div');r.className='set-row';
    r.innerHTML=`<div class="set-num">${i+1}</div>
      <input type="number" min="0" step="0.5" value="${s.kg}" placeholder="0" oninput="sets[${i}].kg=this.value" style="text-align:center;height:35px;padding:6px 4px;margin:0;">
      <input type="number" min="0" step="1" value="${s.reps}" placeholder="0" oninput="sets[${i}].reps=this.value" style="text-align:center;height:35px;padding:6px 4px;margin:0;">
      <button class="icon-btn" onclick="removeSet(${i})">x</button>`;
    c.appendChild(r);
  });
}

function initRecChips(){
  const wrap=document.getElementById('rec-chip-wrap');
  [{label:'전체',value:''},...Object.keys(PATTERNS).map(p=>({label:p,value:p}))].forEach((p,i)=>{
    const btn=document.createElement('button');
    btn.className='chip'+(i===0?' on':'');
    btn.textContent=p.label;
    btn.onclick=()=>{
      document.querySelectorAll('#rec-chip-wrap .chip').forEach(c=>c.classList.remove('on'));
      btn.classList.add('on');
      fillRecExSelect(p.value);
    };
    wrap.appendChild(btn);
  });
  fillRecExSelect('');
}

function fillRecExSelect(pattern){
  const sel=document.getElementById('rec-ex');
  sel.innerHTML='<option value="">-- 운동 선택 --</option>';
  const pats=pattern?{[pattern]:PATTERNS[pattern]}:PATTERNS;
  Object.entries(pats).forEach(([pat,tiers])=>{
    const grp=document.createElement('optgroup');grp.label=pat;
    Object.entries(tiers).forEach(([t,exs])=>{
      exs.forEach(e=>{
        const o=document.createElement('option');
        o.value=e;o.textContent=`[T${t}] ${e}`;
        o.dataset.tier=t;o.dataset.pattern=pat;
        grp.appendChild(o);
      });
    });
    sel.appendChild(grp);
  });
  const cu=document.createElement('option');cu.value='__c';cu.textContent='직접 입력';sel.appendChild(cu);
}

function onExSel(){
  const v=document.getElementById('rec-ex').value;
  document.getElementById('custom-row').style.display=v==='__c'?'block':'none';
  document.getElementById('swap-hint').style.display=(v&&v!=='__c'&&SWAP_MAP[v])?'flex':'none';
}

function getExName(){const v=document.getElementById('rec-ex').value;return v==='__c'?document.getElementById('rec-custom').value.trim():v;}
function getExMeta(field){
  const v=document.getElementById('rec-ex').value;
  const opt=document.querySelector(`#rec-ex option[value="${v}"]`);
  return opt?opt.dataset[field]:null;
}

function saveWO(){
  const name=getExName();
  if(!name){toast('운동을 선택해주세요');return;}
  const vs=sets.filter(s=>s.kg!==''||s.reps!=='');
  if(!vs.length){toast('세트를 입력해주세요');return;}
  const d=document.getElementById('rec-date').value;
  const tier=getExMeta('tier');
  db.wo.push({id:Date.now(),date:d,name,
    tier:tier?+tier:getTierOf(name),
    pattern:getExMeta('pattern')||getPatternOf(name),
    restSec:90,
    sets:vs.map(s=>({kg:parseFloat(s.kg)||0,reps:parseInt(s.reps)||0}))});
  sdb('wo');sets=[];renderSets();
  document.getElementById('rec-ex').value='';
  document.getElementById('custom-row').style.display='none';
  document.getElementById('swap-hint').style.display='none';
  addSet();addSet();addSet();
  renderTodayList();renderInsight();toast('저장 완료');
}

function renderTodayList(){
  const d=document.getElementById('rec-date').value;
  const items=db.wo.filter(x=>x.date===d);
  document.getElementById('today-lbl').textContent=d===today()?'오늘 기록':fmtD(d)+' 기록';
  const c=document.getElementById('today-list');
  if(!items.length){c.innerHTML='<div class="empty">기록 없음</div>';return;}
  c.innerHTML=items.map(item=>{
    const tb=item.tier?`<span class="tier-badge t${item.tier}">T${item.tier}</span>`:'';
    const rest=item.restSec||90;
    return`<div class="ex-item">
      <div style="flex:1;">
        <div class="ex-name">${item.name} ${tb}</div>
        <div class="badge-row">${item.sets.map((s,i)=>`<span class="badge">${i+1}세트 ${s.kg}kg x ${s.reps}회</span>`).join('')}</div>
        <div style="margin-top:7px;display:flex;gap:6px;flex-wrap:wrap;">
          <button class="swap-btn" style="background:rgba(77,159,255,.1);color:var(--blue);border-color:rgba(77,159,255,.25);" onclick="startRest(${rest})">${secToStr(rest)} 휴식</button>
          ${SWAP_MAP[item.name]?`<button class="swap-btn" onclick="openSwapFor('${item.name}')">대체 운동</button>`:''}
        </div>
      </div>
      <button class="icon-btn" onclick="delWO(${item.id})">x</button>
    </div>`;
  }).join('');
}

function delWO(id){if(!confirm('삭제할까요?'))return;db.wo=db.wo.filter(d=>d.id!==id);sdb('wo');renderTodayList();renderInsight();}

function renderInsight(){
  const d=document.getElementById('rec-date').value;
  const ago=new Date(d);ago.setDate(ago.getDate()-28);
  const recent=db.wo.filter(x=>x.date>=toStr(ago)&&x.date<=d);
  const patVol={};
  recent.forEach(item=>{
    const pat=item.pattern||getPatternOf(item.name);if(!pat)return;
    patVol[pat]=(patVol[pat]||0)+item.sets.reduce((s,x)=>s+x.kg*x.reps,0);
  });
  const pushV=(patVol['수평 밀기 (가슴)']||0)+(patVol['수직 밀기 (어깨)']||0);
  const pullV=(patVol['수평 당기기 (등 두께)']||0)+(patVol['수직 당기기 (등 너비)']||0);
  const area=document.getElementById('insight-area');
  const msgs=[];
  if(pushV>0&&pullV>0){
    const r=pullV/pushV;
    if(r<0.8)msgs.push({title:'당기기 볼륨 부족',body:`최근 4주간 등 볼륨이 가슴/어깨보다 ${Math.round((1-r)*100)}% 부족합니다.`});
    if(r>1.3)msgs.push({title:'밀기 볼륨 점검',body:`당기기 볼륨이 밀기보다 ${Math.round((r-1)*100)}% 많습니다. 가슴/어깨를 보충하세요.`});
  }
  area.innerHTML=msgs.map(m=>`<div class="insight-card"><div class="insight-title">${m.title}</div><div class="insight-body">${m.body}</div></div>`).join('');
}

// ─── ROUTINE LOAD ────────────────────────────
function toggleRtnLoad(){
  const el=document.getElementById('rtn-load-inner');
  const on=el.style.display==='none';
  el.style.display=on?'block':'none';
  if(on)renderRtnLoadList();
}
function renderRtnLoadList(){
  const all=[...PRESETS.map(p=>({...p,_pre:true})),...db.rtn];
  document.getElementById('rtn-load-inner').innerHTML=all.map(r=>`
    <div style="display:flex;justify-content:space-between;align-items:center;padding:9px 0;border-bottom:1px solid var(--border);">
      <span style="font-size:14px;">${r.name} <span style="font-size:11px;color:var(--muted2);">${r._pre?'프리셋':'내 루틴'} · ${r.exercises.length}종목</span></span>
      <button class="btn btn-ghost btn-xs" onclick="loadRoutine('${r.id}',${!!r._pre})">불러오기</button>
    </div>`).join('')||'<div class="empty">루틴 없음</div>';
}
function loadRoutine(id,isPreset){
  const r=isPreset?PRESETS.find(x=>x.id===id):db.rtn.find(x=>x.id===id);
  if(!r)return;
  const d=document.getElementById('rec-date').value;
  startRest(r.restSec||90);
  r.exercises.forEach(e=>{
    db.wo.push({id:Date.now()+Math.random(),date:d,name:e.name,
      tier:getTierOf(e.name),pattern:getPatternOf(e.name),
      restSec:e.restSec||r.restSec||90,
      sets:Array.from({length:e.sets},()=>({kg:e.kg||0,reps:0}))});
  });
  sdb('wo');renderTodayList();renderInsight();
  document.getElementById('rtn-load-inner').style.display='none';
  toast(r.name+' 불러왔어요');
}

// ─── SWAP ───────────────────────────────────
let swapTarget='';
function openSwap(){swapTarget=getExName();openSwapFor(swapTarget);}
function openSwapFor(name){
  swapTarget=name;
  const alts=SWAP_MAP[name];if(!alts){toast('대체 운동 정보 없음');return;}
  document.getElementById('swap-title').textContent=name+' 대체 운동';
  document.getElementById('swap-list').innerHTML=alts.map(a=>`
    <div class="swap-item" onclick="applySwap('${a}')">
      <div style="font-size:14px;font-weight:500;">${a}</div>
      <div style="font-size:11px;color:var(--muted2);">같은 패턴 운동</div>
    </div>`).join('');
  document.getElementById('swap-modal').classList.add('open');
}
function applySwap(name){
  document.getElementById('rec-ex').value='';
  document.getElementById('rec-custom').value=name;
  document.getElementById('custom-row').style.display='block';
  document.getElementById('swap-hint').style.display='none';
  closeSwap();toast(name+' 으로 변경');
}
function closeSwap(){document.getElementById('swap-modal').classList.remove('open');}
document.getElementById('swap-modal').onclick=function(e){if(e.target===this)closeSwap();};

// ─── STOPWATCH ──────────────────────────────
let swInt=null,swStart=0,swEl=0,swRun=false,laps=[];
function fmtSW(ms){const cs=Math.floor((ms%1000)/10),sec=Math.floor(ms/1000)%60,m=Math.floor(ms/60000);return`${s2(m)}:${s2(sec)}.${s2(cs)}`;}
function swToggle(){
  if(swRun){swEl+=Date.now()-swStart;clearInterval(swInt);swRun=false;document.getElementById('sw-btn').textContent='계속';}
  else{swStart=Date.now();swInt=setInterval(()=>{document.getElementById('sw-disp').textContent=fmtSW(swEl+Date.now()-swStart);},30);swRun=true;document.getElementById('sw-btn').textContent='정지';}
}
function swReset(){clearInterval(swInt);swRun=false;swEl=0;laps=[];document.getElementById('sw-disp').textContent='00:00.00';document.getElementById('sw-btn').textContent='시작';document.getElementById('sw-lap-cnt').textContent='';document.getElementById('lap-list').innerHTML='';}
function swLap(){
  if(!swRun&&swEl===0)return;
  const cur=swEl+(swRun?Date.now()-swStart:0);
  const lt=cur-(laps.length?laps[laps.length-1].total:0);
  laps.push({total:cur,lap:lt});
  document.getElementById('sw-lap-cnt').textContent=laps.length+'랩';
  document.getElementById('lap-list').innerHTML=laps.slice().reverse().map((l,i)=>`<div class="lap-item"><span style="color:var(--muted2);">랩 ${laps.length-i}</span><span class="lap-t">${fmtSW(l.lap)}</span></div>`).join('');
}

// ─── REST ───────────────────────────────────
let restInt=null,restTotal=90,restRem=90,restDef=90;
function startRest(sec){
  clearInterval(restInt);restTotal=sec;restRem=sec;restDef=sec;
  document.getElementById('rest-def-input').value=sec;
  document.getElementById('rest-banner').style.display='none';
  updRest();
  restInt=setInterval(()=>{restRem--;updRest();if(restRem<=0){clearInterval(restInt);toast('휴식 끝');}},1000);
}
function stopRest(){clearInterval(restInt);document.getElementById('rest-banner').style.display='none';}
function updRest(){
  const m=Math.floor(restRem/60),sec=restRem%60;
  const txt=`${s2(m)}:${s2(sec)}`;
  document.getElementById('rest-disp').textContent=txt;
  document.getElementById('rest-fill').style.width=Math.max(restRem,0)/restTotal*100+'%';
  document.getElementById('banner-time').textContent=txt;
}
function gotoTimer(){document.getElementById('rest-banner').style.display='none';document.querySelectorAll('nav button')[2].click();}

// ─── 식품 DB (100g 기준: kcal, 탄수화물, 단백질, 지방) ──────────
const FOOD_DB=[
  // 단백질 식품
  {name:'닭가슴살 (삶은)',cat:'단백질',kcal:165,carb:0,prot:31,fat:3.6},
  {name:'닭가슴살 (구운)',cat:'단백질',kcal:172,carb:0,prot:32,fat:3.8},
  {name:'닭다리 (껍질 제거)',cat:'단백질',kcal:155,carb:0,prot:27,fat:5},
  {name:'닭날개',cat:'단백질',kcal:203,carb:0,prot:26,fat:11},
  {name:'계란 (전란)',cat:'단백질',kcal:155,carb:1.1,prot:13,fat:11},
  {name:'계란 흰자',cat:'단백질',kcal:52,carb:0.7,prot:11,fat:0.2},
  {name:'계란 노른자',cat:'단백질',kcal:322,carb:3.6,prot:16,fat:27},
  {name:'소고기 안심',cat:'단백질',kcal:198,carb:0,prot:28,fat:9},
  {name:'소고기 등심',cat:'단백질',kcal:246,carb:0,prot:26,fat:15},
  {name:'소고기 우둔살',cat:'단백질',kcal:156,carb:0,prot:27,fat:5},
  {name:'돼지고기 안심',cat:'단백질',kcal:143,carb:0,prot:26,fat:4},
  {name:'돼지고기 삼겹살',cat:'단백질',kcal:331,carb:0,prot:18,fat:28},
  {name:'돼지고기 목살',cat:'단백질',kcal:230,carb:0,prot:21,fat:16},
  {name:'참치 통조림 (물)',cat:'단백질',kcal:108,carb:0,prot:25,fat:0.8},
  {name:'연어 (생)',cat:'단백질',kcal:208,carb:0,prot:20,fat:13},
  {name:'연어 (구운)',cat:'단백질',kcal:225,carb:0,prot:25,fat:13},
  {name:'고등어 (구운)',cat:'단백질',kcal:262,carb:0,prot:25,fat:17},
  {name:'새우 (삶은)',cat:'단백질',kcal:99,carb:0.9,prot:21,fat:1.1},
  {name:'오징어',cat:'단백질',kcal:92,carb:1.5,prot:18,fat:1.4},
  {name:'명태 (생)',cat:'단백질',kcal:82,carb:0,prot:18,fat:0.7},
  {name:'동태',cat:'단백질',kcal:78,carb:0,prot:17,fat:0.7},
  {name:'가자미',cat:'단백질',kcal:91,carb:0,prot:18,fat:1.8},
  {name:'두부 (단단한)',cat:'단백질',kcal:76,carb:1.9,prot:8,fat:4.5},
  {name:'두부 (연한)',cat:'단백질',kcal:55,carb:1.4,prot:5.9,fat:2.9},
  {name:'콩 (대두, 삶은)',cat:'단백질',kcal:173,carb:10,prot:17,fat:9},
  {name:'그릭요거트 (무지방)',cat:'단백질',kcal:59,carb:3.6,prot:10,fat:0.4},
  {name:'코티지치즈',cat:'단백질',kcal:98,carb:3.4,prot:11,fat:4.3},
  {name:'모짜렐라치즈',cat:'단백질',kcal:280,carb:2.2,prot:28,fat:17},
  {name:'훈제오리',cat:'단백질',kcal:201,carb:0,prot:21,fat:13},
  {name:'황태채',cat:'단백질',kcal:336,carb:0,prot:74,fat:2.8},
  // 탄수화물
  {name:'현미밥',cat:'탄수화물',kcal:111,carb:23,prot:2.6,fat:0.9},
  {name:'백미밥',cat:'탄수화물',kcal:130,carb:28,prot:2.7,fat:0.3},
  {name:'잡곡밥',cat:'탄수화물',kcal:118,carb:24,prot:3.2,fat:0.8},
  {name:'오트밀 (건)',cat:'탄수화물',kcal:389,carb:66,prot:17,fat:7},
  {name:'오트밀 (조리)',cat:'탄수화물',kcal:71,carb:12,prot:2.5,fat:1.5},
  {name:'고구마 (생)',cat:'탄수화물',kcal:86,carb:20,prot:1.6,fat:0.1},
  {name:'고구마 (찐)',cat:'탄수화물',kcal:90,carb:21,prot:1.8,fat:0.1},
  {name:'감자 (삶은)',cat:'탄수화물',kcal:87,carb:20,prot:1.9,fat:0.1},
  {name:'통밀빵',cat:'탄수화물',kcal:247,carb:41,prot:13,fat:4.2},
  {name:'식빵 (흰)',cat:'탄수화물',kcal:265,carb:49,prot:9,fat:3.2},
  {name:'베이글',cat:'탄수화물',kcal:257,carb:50,prot:10,fat:1.6},
  {name:'파스타 (조리)',cat:'탄수화물',kcal:158,carb:31,prot:5.8,fat:0.9},
  {name:'쌀국수 (조리)',cat:'탄수화물',kcal:108,carb:25,prot:1.8,fat:0.2},
  {name:'퀴노아 (조리)',cat:'탄수화물',kcal:120,carb:21,prot:4.4,fat:1.9},
  {name:'바나나',cat:'탄수화물',kcal:89,carb:23,prot:1.1,fat:0.3},
  {name:'사과',cat:'탄수화물',kcal:52,carb:14,prot:0.3,fat:0.2},
  {name:'블루베리',cat:'탄수화물',kcal:57,carb:14,prot:0.7,fat:0.3},
  {name:'딸기',cat:'탄수화물',kcal:32,carb:7.7,prot:0.7,fat:0.3},
  {name:'오렌지',cat:'탄수화물',kcal:47,carb:12,prot:0.9,fat:0.1},
  {name:'방울토마토',cat:'탄수화물',kcal:18,carb:3.9,prot:0.9,fat:0.2},
  // 지방 / 건강식품
  {name:'아보카도',cat:'지방',kcal:160,carb:9,prot:2,fat:15},
  {name:'아몬드',cat:'지방',kcal:579,carb:22,prot:21,fat:50},
  {name:'땅콩버터',cat:'지방',kcal:588,carb:20,prot:25,fat:50},
  {name:'올리브오일',cat:'지방',kcal:884,carb:0,prot:0,fat:100},
  {name:'코코넛오일',cat:'지방',kcal:862,carb:0,prot:0,fat:100},
  {name:'호두',cat:'지방',kcal:654,carb:14,prot:15,fat:65},
  {name:'아마씨',cat:'지방',kcal:534,carb:29,prot:18,fat:42},
  {name:'치아씨드',cat:'지방',kcal:486,carb:42,prot:17,fat:31},
  {name:'카슈넛',cat:'지방',kcal:553,carb:30,prot:18,fat:44},
  {name:'피스타치오',cat:'지방',kcal:560,carb:28,prot:20,fat:45},
  // 채소
  {name:'브로콜리',cat:'채소',kcal:34,carb:7,prot:2.8,fat:0.4},
  {name:'시금치',cat:'채소',kcal:23,carb:3.6,prot:2.9,fat:0.4},
  {name:'양배추',cat:'채소',kcal:25,carb:5.8,prot:1.3,fat:0.1},
  {name:'당근',cat:'채소',kcal:41,carb:10,prot:0.9,fat:0.2},
  {name:'오이',cat:'채소',kcal:15,carb:3.6,prot:0.7,fat:0.1},
  {name:'파프리카',cat:'채소',kcal:31,carb:6,prot:1,fat:0.3},
  {name:'아스파라거스',cat:'채소',kcal:20,carb:3.9,prot:2.2,fat:0.1},
  {name:'케일',cat:'채소',kcal:49,carb:9,prot:4.3,fat:0.9},
  {name:'양파',cat:'채소',kcal:40,carb:9.3,prot:1.1,fat:0.1},
  {name:'버섯 (느타리)',cat:'채소',kcal:33,carb:6.1,prot:3.1,fat:0.4},
  // 유제품
  {name:'우유 (일반)',cat:'유제품',kcal:61,carb:4.8,prot:3.2,fat:3.3},
  {name:'우유 (저지방)',cat:'유제품',kcal:46,carb:4.8,prot:3.4,fat:1},
  {name:'무지방 우유',cat:'유제품',kcal:34,carb:5,prot:3.4,fat:0.1},
  {name:'요거트 (플레인)',cat:'유제품',kcal:59,carb:3.6,prot:10,fat:0.4},
  {name:'체다치즈',cat:'유제품',kcal:403,carb:1.3,prot:25,fat:33},
  {name:'리코타치즈',cat:'유제품',kcal:174,carb:3,prot:11,fat:13},
  // 해외 헬스 식단
  {name:'프로틴쉐이크 (유청)',cat:'보충제',kcal:375,carb:10,prot:75,fat:5},
  {name:'카제인 단백질',cat:'보충제',kcal:365,carb:8,prot:77,fat:2},
  {name:'BCAA',cat:'보충제',kcal:130,carb:0,prot:32,fat:0},
  {name:'크레아틴',cat:'보충제',kcal:0,carb:0,prot:0,fat:0},
  {name:'라이스케이크 (무가당)',cat:'탄수화물',kcal:387,carb:81,prot:8,fat:3},
  {name:'프로틴바 (평균)',cat:'보충제',kcal:350,carb:35,prot:25,fat:10},
  {name:'에그화이트 파우더',cat:'단백질',kcal:382,carb:2,prot:82,fat:0.6},
  {name:'스테이크 (등심, 미국산)',cat:'단백질',kcal:271,carb:0,prot:26,fat:18},
  {name:'터키 가슴살',cat:'단백질',kcal:135,carb:0,prot:30,fat:1},
  {name:'버팔로 고기',cat:'단백질',kcal:143,carb:0,prot:28,fat:3},
  {name:'틸라피아',cat:'단백질',kcal:96,carb:0,prot:21,fat:1.7},
  {name:'대구',cat:'단백질',kcal:82,carb:0,prot:18,fat:0.7},
  {name:'흰살생선 (일반)',cat:'단백질',kcal:90,carb:0,prot:19,fat:1.5},
  {name:'문어',cat:'단백질',kcal:82,carb:2.2,prot:15,fat:1},
  {name:'훈제연어',cat:'단백질',kcal:117,carb:0,prot:18,fat:4.3},
  {name:'정어리 통조림',cat:'단백질',kcal:208,carb:0,prot:25,fat:11},
  {name:'아이슬란드 스키르',cat:'단백질',kcal:63,carb:4,prot:11,fat:0.2},
  {name:'에다마메 (콩)',cat:'단백질',kcal:121,carb:8.9,prot:11,fat:5.2},
  {name:'렌틸콩 (삶은)',cat:'탄수화물',kcal:116,carb:20,prot:9,fat:0.4},
  {name:'검은콩 (삶은)',cat:'탄수화물',kcal:132,carb:24,prot:8.9,fat:0.5},
  {name:'병아리콩 (삶은)',cat:'탄수화물',kcal:164,carb:27,prot:8.9,fat:2.6},
  {name:'팝콘 (무가당)',cat:'탄수화물',kcal:375,carb:74,prot:11,fat:4.3},
  {name:'현미 (건)',cat:'탄수화물',kcal:370,carb:77,prot:8,fat:2.9},
  {name:'스위트포테이토 (찐)',cat:'탄수화물',kcal:90,carb:21,prot:2,fat:0.1},
  {name:'수박',cat:'탄수화물',kcal:30,carb:7.6,prot:0.6,fat:0.2},
  {name:'포도',cat:'탄수화물',kcal:69,carb:18,prot:0.7,fat:0.2},
  {name:'키위',cat:'탄수화물',kcal:61,carb:15,prot:1.1,fat:0.5},
  {name:'망고',cat:'탄수화물',kcal:60,carb:15,prot:0.8,fat:0.4},
  {name:'파인애플',cat:'탄수화물',kcal:50,carb:13,prot:0.5,fat:0.1},
  {name:'올리브 (블랙)',cat:'지방',kcal:115,carb:6.3,prot:0.8,fat:10.7},
  {name:'참깨',cat:'지방',kcal:573,carb:23,prot:18,fat:50},
  {name:'아몬드밀크 (무가당)',cat:'유제품',kcal:17,carb:0.6,prot:0.6,fat:1.4},
  {name:'귀리우유',cat:'유제품',kcal:48,carb:9.1,prot:1,fat:1},
];

let selectedFoodItem = null;

function searchFood(q){
  const res=document.getElementById('food-search-result');
  if(!q.trim()){res.style.display='none';return;}
  const matched=FOOD_DB.filter(f=>f.name.includes(q)||f.cat.includes(q)).slice(0,10);
  if(!matched.length){res.style.display='none';return;}
  res.style.display='block';
  res.innerHTML=matched.map(f=>`
    <div onclick="selectFood(${JSON.stringify(f).replace(/"/g,'&quot;')})" style="padding:10px 14px;cursor:pointer;border-bottom:1px solid var(--border);transition:background .1s;" onmouseover="this.style.background='var(--s3)'" onmouseout="this.style.background=''">
      <div style="font-size:13px;font-weight:500;">${f.name}</div>
      <div style="font-size:11px;color:var(--muted2);margin-top:2px;">${f.kcal}kcal · 탄 ${f.carb}g · 단 ${f.prot}g · 지 ${f.fat}g <span style="color:var(--muted);margin-left:4px;">(100g)</span></div>
    </div>`).join('');
}

function selectFood(f){
  selectedFoodItem=f;
  document.getElementById('food-search').value=f.name;
  document.getElementById('food-search-result').style.display='none';
  document.getElementById('food-selected-name').textContent=f.name;
  document.getElementById('food-selected-per100').textContent=`${f.kcal}kcal · 탄 ${f.carb}g · 단 ${f.prot}g · 지 ${f.fat}g`;
  document.getElementById('food-selected-info').style.display='block';
  document.getElementById('food-manual-area').style.display='none';
  document.getElementById('food-gram').value=100;
  calcFoodMacro();
}

function calcFoodMacro(){
  if(!selectedFoodItem)return;
  const g=parseFloat(document.getElementById('food-gram').value)||100;
  const r=g/100;
  const kcal=Math.round(selectedFoodItem.kcal*r);
  const carb=(selectedFoodItem.carb*r).toFixed(1);
  const prot=(selectedFoodItem.prot*r).toFixed(1);
  const fat=(selectedFoodItem.fat*r).toFixed(1);
  document.getElementById('food-calc-result').innerHTML=`
    <span class="badge" style="color:var(--orange);font-size:13px;">${kcal} kcal</span>
    <span class="badge" style="color:var(--accent);">탄 ${carb}g</span>
    <span class="badge" style="color:var(--blue);">단 ${prot}g</span>
    <span class="badge" style="color:var(--muted2);">지 ${fat}g</span>`;
  document.getElementById('food-kcal').value=kcal;
  document.getElementById('food-carb').value=carb;
  document.getElementById('food-prot').value=prot;
  document.getElementById('food-fat').value=fat;
  document.getElementById('food-name').value=`${selectedFoodItem.name} ${g}g`;
}

function clearFoodSelection(){
  selectedFoodItem=null;
  document.getElementById('food-search').value='';
  document.getElementById('food-selected-info').style.display='none';
  document.getElementById('food-manual-area').style.display='block';
  document.getElementById('food-name').value='';
  ['food-kcal','food-carb','food-prot','food-fat'].forEach(id=>document.getElementById(id).value='');
}

// ─── FOOD ───────────────────────────────────
function saveFood(){
  const name=document.getElementById('food-name').value.trim();
  if(!name){toast('음식 이름을 입력해주세요');return;}
  const d=document.getElementById('food-date').value;
  db.food.push({id:Date.now(),date:d,meal:document.getElementById('food-meal').value,name,
    kcal:parseFloat(document.getElementById('food-kcal').value)||0,
    carb:parseFloat(document.getElementById('food-carb').value)||0,
    prot:parseFloat(document.getElementById('food-prot').value)||0,
    fat:parseFloat(document.getElementById('food-fat').value)||0});
  sdb('food');['food-name','food-kcal','food-carb','food-prot','food-fat'].forEach(id=>document.getElementById(id).value='');
  renderFood();toast('추가됨');
}
function renderFood(){
  const d=document.getElementById('food-date').value;
  const items=db.food.filter(x=>x.date===d);
  const goal=+document.getElementById('kcal-goal').value||2500;
  const totK=items.reduce((s,x)=>s+x.kcal,0);
  drawKcalRing(totK,goal);
  document.getElementById('macro-sum').innerHTML=`
    <div class="macro-box"><div class="macro-num" style="color:var(--orange)">${Math.round(totK)}</div><div class="macro-lbl">칼로리</div></div>
    <div class="macro-box"><div class="macro-num" style="color:var(--blue)">${Math.round(items.reduce((s,x)=>s+x.prot,0))}g</div><div class="macro-lbl">단백질</div></div>
    <div class="macro-box"><div class="macro-num" style="color:var(--accent)">${Math.round(items.reduce((s,x)=>s+x.carb,0))}g</div><div class="macro-lbl">탄수화물</div></div>`;
  const c=document.getElementById('food-list');
  if(!items.length){c.innerHTML='<div class="empty">식단 기록 없음</div>';return;}
  c.innerHTML=['아침','점심','저녁','간식'].map(meal=>{
    const mi=items.filter(x=>x.meal===meal);if(!mi.length)return'';
    return`<div class="sec-lbl" style="font-size:13px;">${meal}</div>`+mi.map(x=>`
      <div class="food-item">
        <div><div style="font-size:14px;font-weight:500;">${x.name}</div><div style="font-size:11px;color:var(--muted2);">탄 ${x.carb}g · 단 ${x.prot}g · 지 ${x.fat}g</div></div>
        <div style="display:flex;align-items:center;gap:8px;">
          <div class="food-kcal">${Math.round(x.kcal)} <span style="font-size:10px;color:var(--muted2);">kcal</span></div>
          <button class="icon-btn" onclick="delFood(${x.id})">x</button>
        </div>
      </div>`).join('');
  }).join('');
}
function delFood(id){db.food=db.food.filter(d=>d.id!==id);sdb('food');renderFood();}
function drawKcalRing(cur,goal){
  const cv=document.getElementById('kcal-cv');const ctx=cv.getContext('2d');
  const cx=65,cy=65,r=52,lw=11;
  ctx.clearRect(0,0,130,130);
  ctx.beginPath();ctx.arc(cx,cy,r,0,Math.PI*2);ctx.strokeStyle='#252525';ctx.lineWidth=lw;ctx.stroke();
  const pct=Math.min(cur/goal,1);
  if(pct>0){ctx.beginPath();ctx.arc(cx,cy,r,-Math.PI/2,-Math.PI/2+Math.PI*2*pct);ctx.strokeStyle=pct>=1?'#ff4d4d':'#ff8c42';ctx.lineWidth=lw;ctx.lineCap='round';ctx.stroke();}
  ctx.fillStyle='#f0f0f0';ctx.font='700 20px Bebas Neue,sans-serif';ctx.textAlign='center';ctx.textBaseline='middle';
  ctx.fillText(Math.round(cur),cx,cy-7);ctx.fillStyle='#555';ctx.font='400 10px Noto Sans KR,sans-serif';ctx.fillText('/'+goal+' kcal',cx,cy+10);
}

// ─── CALENDAR ───────────────────────────────
let calY=new Date().getFullYear(),calM=new Date().getMonth(),selDate=null;
function chMon(d){calM+=d;if(calM<0){calM=11;calY--;}if(calM>11){calM=0;calY++;}renderCal();}
function renderCal(){
  document.getElementById('cal-title').textContent=`${calY}.${s2(calM+1)}`;
  const first=new Date(calY,calM,1).getDay(),days=new Date(calY,calM+1,0).getDate();
  const td=today(),wD=new Set(db.wo.map(d=>d.date)),fD=new Set(db.food.map(d=>d.date));
  const g=document.getElementById('cal-grid');g.innerHTML='';
  for(let i=0;i<first;i++)g.appendChild(document.createElement('div'));
  for(let d=1;d<=days;d++){
    const ds=`${calY}-${s2(calM+1)}-${s2(d)}`;
    const el=document.createElement('div');
    el.className='cal-day'+(wD.has(ds)?' hw':'')+(fD.has(ds)?' hf':'')+(ds===td?' today':'')+(ds===selDate?' sel':'');
    el.textContent=d;
    if(wD.has(ds)){const dot=document.createElement('div');dot.className='cal-dot';el.appendChild(dot);}
    el.onclick=()=>{selDate=selDate===ds?null:ds;renderCal();renderCalLog();};
    g.appendChild(el);
  }renderCalLog();
}
function renderCalLog(){
  const items=selDate
    ?[...db.wo.filter(d=>d.date===selDate),...db.food.filter(d=>d.date===selDate).map(f=>({...f,_food:true}))]
    :[...db.wo,...db.food.map(f=>({...f,_food:true}))].sort((a,b)=>b.date.localeCompare(a.date)).slice(0,40);
  document.getElementById('cal-log-title').textContent=selDate?fmtD(selDate)+' 기록':'전체 기록';
  const c=document.getElementById('cal-log');
  if(!items.length){c.innerHTML='<div class="empty">기록 없음</div>';return;}
  c.innerHTML=items.map(item=>item._food
    ?`<div class="log-item"><div class="log-date">${fmtD(item.date)} · ${item.meal}</div><div class="log-name" style="color:var(--orange)">${item.name}</div><div class="badge-row"><span class="badge">${Math.round(item.kcal)} kcal</span></div></div>`
    :`<div class="log-item"><div class="log-date">${fmtD(item.date)}</div><div class="log-name">${item.name}</div><div class="badge-row">${item.sets.map((s,i)=>`<span class="badge">${i+1}세트 ${s.kg}kg x ${s.reps}회</span>`).join('')}</div></div>`
  ).join('');
}

// ─── STATS ──────────────────────────────────
function renderStats(){
  const totalDays=new Set(db.wo.map(d=>d.date)).size;
  const totalVol=db.wo.reduce((s,item)=>s+item.sets.reduce((s2,x)=>s2+x.kg*x.reps,0),0);
  const totalKcal=db.food.reduce((s,x)=>s+x.kcal,0);
  document.getElementById('stats-boxes').innerHTML=`
    <div class="stat-box"><div class="stat-num">${totalDays}</div><div class="stat-lbl">운동 일수</div></div>
    <div class="stat-box"><div class="stat-num">${(totalVol/1000).toFixed(1)}t</div><div class="stat-lbl">총 볼륨</div></div>
    <div class="stat-box"><div class="stat-num">${Math.round(totalKcal/1000)}k</div><div class="stat-lbl">총 kcal</div></div>`;

  const patVol={};
  db.wo.forEach(item=>{
    const pat=item.pattern||getPatternOf(item.name);if(!pat)return;
    patVol[pat]=(patVol[pat]||0)+item.sets.reduce((s,x)=>s+x.kg*x.reps,0);
  });
  const maxV=Math.max(...Object.values(patVol),1);
  const pushV=(patVol['수평 밀기 (가슴)']||0)+(patVol['수직 밀기 (어깨)']||0);
  const pullV=(patVol['수평 당기기 (등 두께)']||0)+(patVol['수직 당기기 (등 너비)']||0);
  const warns=[];
  if(pushV>0&&pullV>0){
    const ratio=pullV/pushV;
    if(ratio<0.8)warns.push('당기기 볼륨이 밀기보다 '+Math.round((1-ratio)*100)+'% 부족합니다. 등 운동을 추가하세요.');
    if(ratio>1.3)warns.push('밀기 볼륨이 당기기보다 '+Math.round((ratio-1)*100)+'% 부족합니다. 가슴/어깨를 보충하세요.');
  }
  document.getElementById('balance-warns').innerHTML=warns.map(w=>`<div class="warn-card"><div class="warn-title">불균형 감지</div><div style="font-size:12px;color:var(--muted2);">${w}</div></div>`).join('');
  document.getElementById('balance-bars').innerHTML=Object.entries(patVol).sort((a,b)=>b[1]-a[1]).map(([pat,vol])=>`
    <div class="bal-row">
      <div class="bal-name"><span>${pat}</span><span>${(vol/1000).toFixed(1)}t</span></div>
      <div class="bal-bar"><div class="bal-fill" style="width:${vol/maxV*100}%"></div></div>
    </div>`).join('');

  const chart=document.getElementById('vol-chart');chart.innerHTML='';
  const weekVols=[];
  for(let i=7;i>=0;i--){
    const d=new Date();d.setDate(d.getDate()-i*7);
    const ws=new Date(d);ws.setDate(d.getDate()-d.getDay());
    const we=new Date(ws);we.setDate(ws.getDate()+6);
    const wss=toStr(ws),wes=toStr(we);
    weekVols.push({label:`${ws.getMonth()+1}/${ws.getDate()}`,vol:db.wo.filter(x=>x.date>=wss&&x.date<=wes).reduce((s,item)=>s+item.sets.reduce((s2,x)=>s2+x.kg*x.reps,0),0)});
  }
  const maxWV=Math.max(...weekVols.map(w=>w.vol),1);
  weekVols.forEach(w=>{
    chart.innerHTML+=`<div class="cbar-g"><div class="cbar" style="height:${w.vol/maxWV*100}%;"></div><div class="cbar-lbl">${w.label}</div></div>`;
  });

  const pr={};
  db.wo.forEach(item=>{const mx=Math.max(...item.sets.map(s=>s.kg));if(!pr[item.name]||mx>pr[item.name])pr[item.name]=mx;});
  const ent=Object.entries(pr).sort((a,b)=>b[1]-a[1]);
  document.getElementById('pr-list').innerHTML=ent.length?ent.map(([n,kg])=>`<div class="pr-row"><span>${n}</span><span class="pr-kg">${kg}kg</span></div>`).join(''):'<div class="empty">기록 없음</div>';

  const wk=new Date();wk.setDate(wk.getDate()-wk.getDay());
  const wks=toStr(wk),wke=toStr(new Date(wk.getTime()+6*86400000));
  const wi=db.wo.filter(d=>d.date>=wks&&d.date<=wke);
  document.getElementById('week-list').innerHTML=wi.length
    ?wi.map(item=>`<div class="log-item"><div class="log-date">${fmtD(item.date)}</div><div class="log-name">${item.name}</div><div class="badge-row">${item.sets.map((s,i)=>`<span class="badge">${i+1}세트 ${s.kg}kg x ${s.reps}회</span>`).join('')}</div></div>`).join('')
    :'<div class="empty">이번 주 기록 없음</div>';
}

// ─── BODY ───────────────────────────────────
function saveBody(){
  const w=parseFloat(document.getElementById('body-weight').value);
  if(!w){toast('몸무게를 입력해주세요');return;}
  db.body.push({id:Date.now(),date:document.getElementById('body-date').value,weight:w,
    fat:parseFloat(document.getElementById('body-fat').value)||null,
    memo:document.getElementById('body-memo').value.trim()});
  sdb('body');['body-weight','body-fat','body-memo'].forEach(id=>document.getElementById(id).value='');
  renderBody();toast('기록됐어요');
}
function renderBody(){
  const sorted=[...db.body].sort((a,b)=>a.date.localeCompare(b.date));
  const cv=document.getElementById('body-chart');const ctx=cv.getContext('2d');
  cv.width=cv.offsetWidth||560;cv.height=110;ctx.clearRect(0,0,cv.width,cv.height);
  if(sorted.length<2){ctx.fillStyle='#555';ctx.font='13px Noto Sans KR';ctx.textAlign='center';ctx.fillText('기록 2개 이상이면 그래프 표시',cv.width/2,55);return;}
  const ws=sorted.map(x=>x.weight);const mn=Math.min(...ws)-2,mx=Math.max(...ws)+2;
  const pad=28,w=cv.width,h=cv.height;
  const px=i=>pad+(i/(sorted.length-1))*(w-pad*2);
  const py=v=>h-pad-(v-mn)/(mx-mn)*(h-pad*2);
  [0,.5,1].forEach(t=>{const y=py(mn+(mx-mn)*t);ctx.beginPath();ctx.moveTo(pad,y);ctx.lineTo(w-pad,y);ctx.strokeStyle='#2a2a2a';ctx.lineWidth=1;ctx.stroke();ctx.fillStyle='#555';ctx.font='10px Noto Sans KR';ctx.textAlign='right';ctx.fillText((mn+(mx-mn)*t).toFixed(1),pad-4,y+3);});
  ctx.beginPath();sorted.forEach((x,i)=>{i===0?ctx.moveTo(px(i),py(x.weight)):ctx.lineTo(px(i),py(x.weight));});
  ctx.strokeStyle='#4d9fff';ctx.lineWidth=2;ctx.lineJoin='round';ctx.stroke();
  sorted.forEach((x,i)=>{ctx.beginPath();ctx.arc(px(i),py(x.weight),3.5,0,Math.PI*2);ctx.fillStyle='#4d9fff';ctx.fill();});
  document.getElementById('body-list').innerHTML=[...sorted].reverse().map(x=>`
    <div class="card" style="padding:11px 14px;">
      <div style="display:flex;justify-content:space-between;align-items:flex-start;">
        <div>
          <div style="font-size:11px;color:var(--muted2);margin-bottom:4px;">${fmtD(x.date)}</div>
          <div style="display:flex;gap:16px;">
            <div><div class="body-num">${x.weight}kg</div><div style="font-size:10px;color:var(--muted2);">몸무게</div></div>
            ${x.fat?`<div><div class="body-num" style="color:var(--orange)">${x.fat}%</div><div style="font-size:10px;color:var(--muted2);">체지방</div></div>`:''}
          </div>
          ${x.memo?`<div style="font-size:11px;color:var(--muted2);margin-top:5px;">${x.memo}</div>`:''}
        </div>
        <button class="icon-btn" onclick="delBody(${x.id})">x</button>
      </div>
    </div>`).join('')||'<div class="empty">기록 없음</div>';
}
function delBody(id){db.body=db.body.filter(d=>d.id!==id);sdb('body');renderBody();}

// ─── ROUTINE ────────────────────────────────
let rtnExs=[],dragSrcIdx=null;

function switchRtab(name,el){
  document.querySelectorAll('.rtab').forEach(b=>b.classList.remove('on'));
  el.classList.add('on');
  ['preset','custom','saved'].forEach(n=>document.getElementById('rsec-'+n).style.display=n===name?'block':'none');
  if(name==='preset')renderPresetRoutines();
  if(name==='saved')renderMyRoutines();
  if(name==='custom')initRoutineBuilder();
}

function initRoutineBuilder(){
  const wrap=document.getElementById('pattern-chip-wrap');
  if(wrap&&wrap.children.length)return;
  if(!wrap)return;
  [{label:'전체',value:''},...Object.keys(PATTERNS).map(p=>({label:p,value:p}))].forEach((p,i)=>{
    const btn=document.createElement('button');btn.className='chip'+(i===0?' on':'');
    btn.textContent=p.label;
    btn.onclick=()=>{document.querySelectorAll('#pattern-chip-wrap .chip').forEach(c=>c.classList.remove('on'));btn.classList.add('on');fillRtnExSelect(p.value);};
    wrap.appendChild(btn);
  });
  fillRtnExSelect('');
  document.getElementById('rtn-ex-sel').onchange=function(){document.getElementById('rtn-custom-row').style.display=this.value==='__c'?'block':'none';};
}

function fillRtnExSelect(pattern){
  const sel=document.getElementById('rtn-ex-sel');if(!sel)return;
  sel.innerHTML='<option value="">-- 운동 선택 --</option>';
  const pats=pattern?{[pattern]:PATTERNS[pattern]}:PATTERNS;
  Object.entries(pats).forEach(([pat,tiers])=>{
    const grp=document.createElement('optgroup');grp.label=pat;
    Object.entries(tiers).forEach(([t,exs])=>{
      exs.forEach(e=>{const o=document.createElement('option');o.value=e;o.textContent=`[T${t}] ${e}`;o.dataset.tier=t;o.dataset.pattern=pat;grp.appendChild(o);});
    });
    sel.appendChild(grp);
  });
  const cu=document.createElement('option');cu.value='__c';cu.textContent='직접 입력';sel.appendChild(cu);
}

function addRtnEx(){
  const sel=document.getElementById('rtn-ex-sel');
  const v=sel?sel.value:'';
  const name=v==='__c'?document.getElementById('rtn-ex-custom').value.trim():v;
  if(!name){toast('운동을 선택해주세요');return;}
  const opt=sel&&sel.options[sel.selectedIndex];
  const restVal=document.getElementById('rtn-ex-rest').value;
  rtnExs.push({name,tier:opt&&opt.dataset.tier||null,pattern:opt&&opt.dataset.pattern||null,
    sets:+document.getElementById('rtn-sets').value||3,
    reps:document.getElementById('rtn-reps').value||'10',
    kg:parseFloat(document.getElementById('rtn-kg').value)||0,
    restSec:restVal?+restVal:null,
    note:document.getElementById('rtn-ex-note').value.trim()});
  if(sel)sel.value='';
  ['rtn-ex-note','rtn-kg'].forEach(id=>document.getElementById(id).value='');
  document.getElementById('rtn-ex-rest').value='';
  document.getElementById('rtn-custom-row').style.display='none';
  renderRtnExList();toast(name+' 추가');
}

function removeRtnEx(i){rtnExs.splice(i,1);renderRtnExList();}
function moveRtnEx(from,to){const item=rtnExs.splice(from,1)[0];rtnExs.splice(to,0,item);renderRtnExList();}
function clearRtnExs(){if(!rtnExs.length)return;if(!confirm('모두 삭제할까요?'))return;rtnExs=[];renderRtnExList();}

function renderRtnExList(){
  const card=document.getElementById('rtn-preview-card');
  if(card)card.style.display=rtnExs.length?'block':'none';
  const cnt=document.getElementById('rtn-ex-count');
  if(cnt)cnt.textContent=`(${rtnExs.length}종목)`;
  const c=document.getElementById('rtn-exlist');if(!c)return;
  c.innerHTML='';
  rtnExs.forEach((e,i)=>{
    const row=document.createElement('div');row.className='rtn-ex-row';row.draggable=true;
    row.innerHTML=`<div class="drag-handle">|||</div>
      <div style="flex:1;">
        <div style="display:flex;align-items:center;gap:6px;margin-bottom:5px;">
          ${e.tier?`<span class="tier-badge t${e.tier}">T${e.tier}</span>`:''}
          <span style="font-weight:700;font-size:14px;">${e.name}</span>
        </div>
        <div style="display:flex;flex-wrap:wrap;gap:5px;">
          <span class="badge">${e.sets}세트</span>
          <span class="badge">${e.reps}회</span>
          ${e.kg?`<span class="badge">${e.kg}kg</span>`:''}
          ${e.restSec?`<span class="badge" style="color:var(--blue);">${secToStr(e.restSec)}</span>`:`<span class="badge" style="color:var(--muted);">기본 휴식</span>`}
          ${e.note?`<span class="badge" style="color:var(--accent);">${e.note}</span>`:''}
        </div>
      </div>
      <div style="display:flex;flex-direction:column;gap:4px;">
        ${i>0?`<button class="icon-btn" onclick="moveRtnEx(${i},${i-1})">↑</button>`:'<div style="height:26px"></div>'}
        ${i<rtnExs.length-1?`<button class="icon-btn" onclick="moveRtnEx(${i},${i+1})">↓</button>`:'<div style="height:26px"></div>'}
        <button class="icon-btn" onclick="removeRtnEx(${i})">x</button>
      </div>`;
    row.ondragstart=()=>{dragSrcIdx=i;row.classList.add('dragging');};
    row.ondragend=()=>row.classList.remove('dragging');
    row.ondragover=ev=>ev.preventDefault();
    row.ondrop=ev=>{ev.preventDefault();if(dragSrcIdx!==null&&dragSrcIdx!==i){moveRtnEx(dragSrcIdx,i);dragSrcIdx=null;}};
    c.appendChild(row);
  });
}

function saveMyRoutine(){
  const name=document.getElementById('rtn-name').value.trim();
  if(!name){toast('루틴 이름을 입력해주세요');return;}
  if(!rtnExs.length){toast('운동을 추가해주세요');return;}
  db.rtn.push({id:'r_'+Date.now(),name,restSec:+document.getElementById('rtn-rest').value||90,
    memo:document.getElementById('rtn-memo').value.trim(),exercises:[...rtnExs]});
  sdb('rtn');rtnExs=[];renderRtnExList();
  ['rtn-name','rtn-memo'].forEach(id=>document.getElementById(id).value='');
  const pc=document.getElementById('rtn-preview-card');if(pc)pc.style.display='none';
  toast('루틴 저장됨');
  switchRtab('saved',document.getElementById('rtab-saved'));
}

function renderMyRoutines(){
  const c=document.getElementById('my-routines');if(!c)return;
  if(!db.rtn.length){c.innerHTML='<div class="empty">저장된 루틴이 없어요</div>';return;}
  c.innerHTML=db.rtn.map(r=>`
    <div class="rtn-card">
      <div style="display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:8px;">
        <div>
          <div class="rtn-name">${r.name}</div>
          <div style="display:flex;gap:6px;margin-top:4px;flex-wrap:wrap;">
            <span class="rtn-tag g">휴식 ${secToStr(r.restSec||90)}</span>
            <span class="rtn-tag b">${r.exercises.length}종목</span>
            ${r.memo?`<span class="rtn-tag">${r.memo}</span>`:''}
          </div>
        </div>
        <button class="icon-btn" onclick="delMyRtn('${r.id}')">x</button>
      </div>
      <div style="margin-bottom:10px;">${r.exercises.map((e,i)=>`
        <div style="display:flex;align-items:center;gap:6px;padding:6px 0;border-bottom:1px solid var(--border);">
          <span style="color:var(--muted2);font-size:12px;min-width:16px;">${i+1}.</span>
          ${e.tier?`<span class="tier-badge t${e.tier}">T${e.tier}</span>`:''}
          <span style="font-size:13px;font-weight:500;flex:1;">${e.name}</span>
          <span style="font-size:11px;color:var(--muted2);">${e.sets}x${e.reps}${e.kg?' / '+e.kg+'kg':''}${e.restSec?' · '+secToStr(e.restSec):''}${e.note?' · '+e.note:''}</span>
        </div>`).join('')}
      </div>
      <div style="display:flex;gap:8px;flex-wrap:wrap;">
        <button class="btn btn-accent btn-sm" onclick="loadMyRoutine('${r.id}')">오늘 불러오기</button>
        <button class="btn btn-ghost btn-sm" onclick="editRoutine('${r.id}')">수정</button>
      </div>
    </div>`).join('');
}

function renderPresetRoutines(){
  const el=document.getElementById('preset-routines');if(!el)return;
  el.innerHTML=PRESETS.map(r=>`
    <div class="rtn-card">
      <div class="rtn-name">${r.name}</div>
      <div class="rtn-desc">${r.desc}</div>
      <div class="rtn-meta">
        <span class="rtn-tag g">${r.time}</span>
        <span class="rtn-tag b">${r.level}</span>
        <span class="rtn-tag">휴식 ${r.restSec}초 자동</span>
        ${r.tag.map(t=>`<span class="rtn-tag">${t}</span>`).join('')}
      </div>
      <div style="font-size:12px;color:var(--muted2);margin-bottom:8px;line-height:1.7;">${r.exercises.map(e=>`· ${e.name} — ${e.sets}세트 ${e.reps}회${e.note?' ('+e.note+')':''}`).join('<br>')}</div>
      <div style="background:var(--s3);border-radius:8px;padding:10px 12px;font-size:12px;color:var(--muted2);margin-bottom:10px;line-height:1.6;">${r.logic}</div>
      <button class="btn btn-accent btn-sm" onclick="loadRoutine('${r.id}',true)">오늘 기록에 불러오기</button>
    </div>`).join('');
}

function loadMyRoutine(id){
  const r=db.rtn.find(x=>x.id===id);if(!r)return;
  const d=document.getElementById('rec-date').value;
  startRest(r.exercises[0]?.restSec||r.restSec||90);
  r.exercises.forEach(e=>{
    db.wo.push({id:Date.now()+Math.random(),date:d,name:e.name,
      tier:e.tier?+e.tier:getTierOf(e.name),pattern:e.pattern||getPatternOf(e.name),
      restSec:e.restSec||r.restSec||90,
      sets:Array.from({length:e.sets},()=>({kg:e.kg||0,reps:0}))});
  });
  sdb('wo');renderTodayList();renderInsight();
  sw('record',document.querySelectorAll('nav button')[1]);
  toast(r.name+' 불러왔어요');
}

function editRoutine(id){
  const r=db.rtn.find(x=>x.id===id);if(!r)return;
  rtnExs=[...r.exercises];
  db.rtn=db.rtn.filter(x=>x.id!==id);sdb('rtn');
  switchRtab('custom',document.getElementById('rtab-custom'));
  setTimeout(()=>{
    document.getElementById('rtn-name').value=r.name;
    document.getElementById('rtn-rest').value=r.restSec||90;
    document.getElementById('rtn-memo').value=r.memo||'';
    renderRtnExList();
  },50);
  toast('수정 모드로 불러왔어요');
}

function delMyRtn(id){if(!confirm('삭제할까요?'))return;db.rtn=db.rtn.filter(d=>d.id!==id);sdb('rtn');renderMyRoutines();}
function renderRoutineTab(){renderPresetRoutines();renderMyRoutines();}

// ─── GUIDE ──────────────────────────────────
function renderGuide(){
  const patEl=document.getElementById('guide-pattern-list');
  patEl.innerHTML=Object.entries(PATTERNS).map(([pat,tiers])=>`
    <div style="background:var(--s2);border:1px solid var(--border);border-radius:10px;padding:13px;margin-bottom:8px;">
      <div style="font-weight:700;font-size:14px;color:var(--accent);margin-bottom:8px;">${pat}</div>
      <div style="display:flex;flex-direction:column;gap:5px;font-size:12px;">
        <div><span class="tier-badge t1" style="margin-right:6px;">T1</span><span style="color:var(--muted2);">${(tiers[1]||[]).join(', ')}</span></div>
        <div><span class="tier-badge t2" style="margin-right:6px;">T2</span><span style="color:var(--muted2);">${(tiers[2]||[]).join(', ')}</span></div>
        <div><span class="tier-badge t3" style="margin-right:6px;">T3</span><span style="color:var(--muted2);">${(tiers[3]||[]).join(', ')}</span></div>
      </div>
    </div>`).join('');

  const GUIDE_INFO={
    'top-backoff':{when:'이미 기본 동작이 되고 무게를 올리고 싶을 때',how:'1. 워밍업 후 오늘 최고 무게(Top Set) 1세트\n2. 그 무게에서 10~15% 낮춰 3세트 (Back-off)\n3. Top Set은 RPE 9',warn:'폼이 무너지면 무게를 낮추세요'},
    'gzclp':{when:'헬스 1년 미만 초보자',how:'T1: 3회 5세트\nT2: 10회 3세트\nT3: 15회+ AMRAP\n완료 시 다음 세션 2.5kg 추가',warn:'실패 -> 6세트 -> 또 실패 -> 10% 감량 후 재도전'},
    'rp-hyp':{when:'중급자, 데이터 기반 근비대',how:'1주: RIR 3 / 2주: RIR 2 / 3주: RIR 1 / 4주: RIR 0 / 5주: 디로딩 (40% 감량)',warn:'디로딩 주를 건너뛰지 마세요'},
    'myo':{when:'시간 30분뿐, 근지구력과 펌핑이 목표',how:'활성 세트(12~20회) -> 15초 휴식 -> 미니 세트(3~5회) x 5',warn:'15초 휴식 정확히 지켜야 효과가 있어요'},
    '531bbb':{when:'벌크업 목표, 클래식 방식 선호',how:'메인: 5/3/1 방식\nBBB: 같은 종목 1RM 50% x 10회 x 5세트',warn:'처음엔 1RM 40%부터 시작'},
    'phul':{when:'주 4일 운동, 근력+외형 둘 다',how:'월/화: Power (3~5회)\n목/금: Hypertrophy (8~12회)',warn:'파워 데이에 폼 무너뜨리며 무게 올리지 마세요'},
    'ppl':{when:'주 3~6회, 유연한 스케줄',how:'Push -> Pull -> Legs -> 반복\n요일 무관',warn:'하체를 건너뛰지 마세요'},
    'giant':{when:'체지방 감소, 고강도 펌핑',how:'A(6회) -> B(12회) -> C(25회) 휴식 없이\n2분 휴식 후 반복 (4세트)',warn:'A->B->C 사이에 절대 쉬지 않아요'},
    'gvt':{when:'상급자 정체기 돌파. 3~4주만',how:'1RM 60% x 10회 x 10세트\n휴식 60~90초 고정',warn:'처음엔 60%가 쉬워 보여도 6~7세트부터 극한입니다'},
    'hit':{when:'상급자, 25분뿐, 극한 강도',how:'워밍업 2~3세트 후 본 세트 1세트 (완전 실패)\n드롭세트 또는 강제 반복',warn:'보조자 없으면 머신 사용 권장'}
  };

  document.getElementById('guide-routine-list').innerHTML=PRESETS.map(r=>{
    const g=GUIDE_INFO[r.id]||{};
    return`<div style="border:1px solid var(--border);border-radius:10px;margin-bottom:8px;overflow:hidden;">
      <button class="guide-acc-btn" onclick="toggleGuide('g_${r.id}','ga_${r.id}')">
        <div>
          <div style="font-weight:700;font-size:14px;color:var(--accent);font-family:'Noto Sans KR',sans-serif;">${r.name}</div>
          <div style="font-size:11px;color:var(--muted2);margin-top:2px;font-family:'Noto Sans KR',sans-serif;">${r.level} · ${r.time} · 휴식 ${r.restSec}초</div>
        </div>
        <span id="ga_${r.id}" style="color:var(--muted2);">▼</span>
      </button>
      <div id="g_${r.id}" style="display:none;padding:14px;background:var(--surface);border-top:1px solid var(--border);">
        <p style="font-size:13px;color:var(--text);line-height:1.7;margin-bottom:10px;">${r.desc}</p>
        ${g.when?`<div style="background:var(--adim);border:1px solid var(--aborder);border-radius:8px;padding:10px 12px;margin-bottom:10px;font-size:12px;color:var(--muted2);">추천 대상: ${g.when}</div>`:''}
        ${g.how?`<div style="background:var(--s2);border-radius:8px;padding:10px 12px;margin-bottom:10px;"><div style="font-size:12px;font-weight:700;color:var(--text);margin-bottom:6px;">수행 방법</div><pre style="font-size:12px;color:var(--muted2);white-space:pre-wrap;line-height:1.8;font-family:'Noto Sans KR',sans-serif;">${g.how}</pre></div>`:''}
        ${g.warn?`<div style="background:rgba(255,77,77,.07);border:1px solid rgba(255,77,77,.2);border-radius:8px;padding:10px 12px;margin-bottom:10px;font-size:12px;color:var(--muted2);">주의: ${g.warn}</div>`:''}
        <button class="btn btn-accent btn-sm" onclick="loadRoutine('${r.id}',true)">오늘 바로 시작</button>
      </div>
    </div>`;
  }).join('');
}

function toggleGuide(cId,aId){
  const el=document.getElementById(cId);const arr=document.getElementById(aId);
  const open=el.style.display!=='none';
  el.style.display=open?'none':'block';
  if(arr)arr.textContent=open?'▼':'▲';
}

// ─── INIT ───────────────────────────────────
document.getElementById('rec-date').value=today();
document.getElementById('food-date').value=today();
document.getElementById('body-date').value=today();
initRecChips();
addSet();addSet();addSet();
renderHome();
drawKcalRing(0,2500);
</script>
</body>
</html>
