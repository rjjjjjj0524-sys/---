<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no" />
  <title>居服員數位口袋書・緊急應變</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      font-family: -apple-system, BlinkMacSystemFont, "Noto Sans TC", "PingFang TC", "Microsoft JhengHei", sans-serif;
      -webkit-tap-highlight-color: transparent;
      background: #f3f4f6;
    }
    .screen { display: none; min-height: 100vh; }
    .screen.active { display: block; }

    @keyframes slideInRight  { from { transform:translateX(40px);  opacity:0 } to { transform:translateX(0); opacity:1 } }
    @keyframes slideInLeft   { from { transform:translateX(-30px); opacity:0 } to { transform:translateX(0); opacity:1 } }
    .anim-right { animation: slideInRight 0.22s ease forwards; }
    .anim-left  { animation: slideInLeft  0.22s ease forwards; }

    @keyframes pulse-dot { 0%,100%{opacity:1} 50%{opacity:.35} }
    .pulse { animation: pulse-dot 1.8s infinite; }

    .tap-card { transition: transform .12s ease; }
    .tap-card:active { transform: scale(0.97); }

    ol.steps { counter-reset: s; list-style: none; padding:0; margin:0; }
    ol.steps li {
      counter-increment: s;
      display: flex; gap: 10px; margin-bottom: 10px; align-items: flex-start;
    }
    ol.steps li::before {
      content: counter(s);
      min-width: 24px; height: 24px;
      display: flex; align-items: center; justify-content: center;
      border-radius: 50%; font-size: 12px; font-weight: 700;
      flex-shrink: 0; margin-top: 1px;
    }
  </style>
</head>
<body>

<!-- ╔══════════════════════════════╗
     ║   SCREEN 1 : HOME           ║
     ╚══════════════════════════════╝ -->
<div id="s-home" class="screen active">
  <header class="bg-white shadow-sm sticky top-0 z-20">
    <div class="max-w-lg mx-auto px-4 py-3 flex items-center gap-2">
      <span class="text-xl">📖</span>
      <div>
        <div class="text-[10px] text-gray-400 tracking-wider">居服員數位口袋書</div>
        <div class="text-base font-bold text-gray-800">緊急應變</div>
      </div>
    </div>
  </header>

  <div class="max-w-lg mx-auto px-4 pt-4">
    <div class="bg-amber-50 border-l-4 border-amber-400 rounded-r-2xl px-4 py-3 text-sm text-amber-800">
      ⚠️ <strong>有立即危險先打 119 / 110</strong>，安全後再查看處理方式
    </div>
  </div>

  <main class="max-w-lg mx-auto px-4 pt-4 pb-14 space-y-3">
    <!-- 多項目：點擊進分類頁 -->
    <button onclick="nav('s-cat','119')"
      class="tap-card w-full text-left bg-red-600 text-white rounded-2xl px-5 py-4 flex items-center gap-4 shadow-md">
      <span class="text-3xl pulse">🔴</span>
      <div class="flex-1">
        <div class="font-bold text-base leading-tight">先打 119，不要先找網頁</div>
        <div class="text-red-100 text-sm mt-0.5 leading-snug">叫不醒、沒呼吸、持續胸痛、疑似中風……</div>
      </div>
      <svg class="w-5 h-5 text-red-200 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/></svg>
    </button>

    <!-- 多項目：點擊進分類頁 -->
    <button onclick="nav('s-cat','orange')"
      class="tap-card w-full text-left bg-white rounded-2xl px-5 py-4 flex items-center gap-4 shadow-sm border border-gray-100">
      <span class="text-3xl">🟠</span>
      <div class="flex-1">
        <div class="font-bold text-gray-800 text-base">身體突然不舒服</div>
        <div class="text-gray-500 text-sm mt-0.5">低血糖、血壓異常、吃錯藥、嘔吐腹瀉……</div>
      </div>
      <svg class="w-5 h-5 text-gray-300 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/></svg>
    </button>

    <!-- 多項目：點擊進分類頁 -->
    <button onclick="nav('s-cat','yellow')"
      class="tap-card w-full text-left bg-white rounded-2xl px-5 py-4 flex items-center gap-4 shadow-sm border border-gray-100">
      <span class="text-3xl">🟡</span>
      <div class="flex-1">
        <div class="font-bold text-gray-800 text-base">跌倒或受傷</div>
        <div class="text-gray-500 text-sm mt-0.5">跌倒、掉下床、燙傷、撞傷或傷口流血……</div>
      </div>
      <svg class="w-5 h-5 text-gray-300 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/></svg>
    </button>

    <!-- 單一項目：直接跳處理步驟 -->
    <button onclick="nav('s-detail','purple',0)"
      class="tap-card w-full text-left bg-white rounded-2xl px-5 py-4 flex items-center gap-4 shadow-sm border border-gray-100">
      <span class="text-3xl">🟣</span>
      <div class="flex-1">
        <div class="font-bold text-gray-800 text-base">個案不見了</div>
        <div class="text-gray-500 text-sm mt-0.5">不在家，或外出時走失……</div>
      </div>
      <svg class="w-5 h-5 text-gray-300 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/></svg>
    </button>

    <!-- 單一項目：直接跳處理步驟 -->
    <button onclick="nav('s-detail','blue',0)"
      class="tap-card w-full text-left bg-white rounded-2xl px-5 py-4 flex items-center gap-4 shadow-sm border border-gray-100">
      <span class="text-3xl">🔵</span>
      <div class="flex-1">
        <div class="font-bold text-gray-800 text-base">皮膚或感染問題</div>
        <div class="text-gray-500 text-sm mt-0.5">乾癢、紅腫、破皮、疑似壓傷或疥瘡……</div>
      </div>
      <svg class="w-5 h-5 text-gray-300 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/></svg>
    </button>

    <!-- 單一項目：直接跳處理步驟 -->
    <button onclick="nav('s-detail','attack',0)"
      class="tap-card w-full text-left bg-white rounded-2xl px-5 py-4 flex items-center gap-4 shadow-sm border border-gray-100">
      <span class="text-3xl">🟥</span>
      <div class="flex-1">
        <div class="font-bold text-gray-800 text-base">被罵、威脅或攻擊</div>
        <div class="text-gray-500 text-sm mt-0.5">辱罵、恐嚇、推打、酒後鬧事……</div>
      </div>
      <svg class="w-5 h-5 text-gray-300 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/></svg>
    </button>

    <!-- 單一項目：直接跳處理步驟 -->
    <button onclick="nav('s-detail','harass',0)"
      class="tap-card w-full text-left bg-white rounded-2xl px-5 py-4 flex items-center gap-4 shadow-sm border border-gray-100">
      <span class="text-3xl">🩷</span>
      <div class="flex-1">
        <div class="font-bold text-gray-800 text-base">遇到性騷擾</div>
        <div class="text-gray-500 text-sm mt-0.5">故意觸碰、黃色笑話、要求親密行為……</div>
      </div>
      <svg class="w-5 h-5 text-gray-300 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/></svg>
    </button>

    <!-- 單一項目：直接跳處理步驟 -->
    <button onclick="nav('s-detail','traffic',0)"
      class="tap-card w-full text-left bg-white rounded-2xl px-5 py-4 flex items-center gap-4 shadow-sm border border-gray-100">
      <span class="text-3xl">⚫</span>
      <div class="flex-1">
        <div class="font-bold text-gray-800 text-base">發生交通事故</div>
        <div class="text-gray-500 text-sm mt-0.5">騎車摔倒、車禍、陪同外出遇到事故……</div>
      </div>
      <svg class="w-5 h-5 text-gray-300 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/></svg>
    </button>
  </main>
</div>


<!-- ╔══════════════════════════════╗
     ║   SCREEN 2 : CATEGORY       ║
     ╚══════════════════════════════╝ -->
<div id="s-cat" class="screen">
  <header id="cat-header" class="sticky top-0 z-20 shadow-sm">
    <div class="max-w-lg mx-auto px-4 py-3 flex items-center gap-3">
      <button onclick="goBack()" class="p-1.5 rounded-full active:bg-black/10">
        <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7"/></svg>
      </button>
      <span id="cat-icon" class="text-2xl"></span>
      <span id="cat-title" class="font-bold text-base flex-1"></span>
    </div>
  </header>

  <div class="max-w-lg mx-auto px-4 pt-4 pb-14">
    <p id="cat-desc" class="text-sm text-gray-500 mb-4 px-1 leading-relaxed"></p>
    <div id="cat-alert" class="hidden mb-4"></div>
    <div id="cat-top-btn" class="mb-4"></div>
    <div id="cat-list" class="space-y-3"></div>
  </div>
</div>


<!-- ╔══════════════════════════════╗
     ║   SCREEN 3 : DETAIL         ║
     ╚══════════════════════════════╝ -->
<div id="s-detail" class="screen">
  <header id="detail-header" class="sticky top-0 z-20 bg-white shadow-sm">
    <div class="max-w-lg mx-auto px-4 py-3 flex items-center gap-3">
      <button onclick="goBack()" class="p-1.5 rounded-full active:bg-black/10 text-gray-600">
        <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5"><path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7"/></svg>
      </button>
      <span id="detail-num" class="w-7 h-7 rounded-full flex items-center justify-center text-xs font-bold text-white flex-shrink-0"></span>
      <span id="detail-title" class="font-bold text-base flex-1 text-gray-800"></span>
    </div>
  </header>

  <div class="max-w-lg mx-auto px-4 pt-5 pb-16 space-y-5" id="detail-body">
    <!-- 由 JavaScript 自動動態載入 -->
  </div>
</div>


<script>
// ══════════════════════════════════════════════
// 資料庫 (DATA)
// ══════════════════════════════════════════════
const cats = {
  '119': {
    icon: '🔴', title: '先打 119，不要先找網頁',
    headerBg: 'bg-red-600', headerText: 'text-white',
    desc: '嚴重狀況先打 119 並開擴音，再依救護人員指示處理。',
    alert: null,
    topBtn: { label:'📞 立即撥打 119', href:'tel:119', cls:'bg-red-600 text-white' },
    stepNumBg: '#dc2626',
    items: [
      { title:'噎到／嗆到', tag:'食物卡住，可能突然無法呼吸',
        desc:'食物卡住造成氣道阻塞，必須快速判斷嚴重程度。',
        steps:['還能咳嗽：鼓勵用力咳。','不能說話／不能呼吸：立即執行哈姆立克法並大聲求救。','昏倒：平躺，準備胸外按壓。'],
        notices:['不能說話／不能呼吸／昏倒 ➔ 立即撥打 119，開擴音邊救人'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
      { title:'疑似中風', tag:'突然嘴歪、手腳無力、說話不清',
        desc:'把握黃金治療時間，盡快辨識症狀並記錄發作時間。',
        steps:['<strong>看臉：</strong>請他笑，觀察是否嘴歪。','<strong>看手：</strong>雙手平舉，看是否一側無力。','<strong>聽說話：</strong>請他說一句話，是否說不清楚。','<strong>記時間：</strong>記下症狀幾點幾分開始。','不要讓個案吃喝、不要自行加藥。'],
        notices:['嘴歪／手無力／說話不清 ➔ 立即撥打 119，告知發作時間','通報督導與家屬'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
      { title:'胸痛或呼吸困難', tag:'胸痛、喘、冒冷汗、嘴唇發紫',
        desc:'可能是心臟病發，不要讓個案自行走動。',
        steps:['讓個案坐起或半坐臥，鬆開緊身衣物。','保持空氣流通，不要自行增加藥量。','失去意識時，依 119 指示準備胸外按壓。'],
        notices:['持續胸痛／明顯呼吸困難／嘴唇發紫／冒冷汗 ➔ 立即撥打 119','緩解後 ➔ 通報督導與家屬'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
      { title:'抽搐／癲癇', tag:'突然抽搐、倒地、失去意識',
        desc:'保護個案安全，避免二次傷害。',
        steps:['移開周圍硬物，保護頭部。','不要拉手腳，不要把東西塞進嘴巴。','停止抽搐後：讓個案側躺，保持呼吸道通暢。'],
        notices:['抽搐超過 5 分鐘／連續發作／沒呼吸 ➔ 撥打 119','清醒後 ➔ 通報督導與家屬'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
      { title:'叫不醒或沒有正常呼吸', tag:'叫不醒、昏睡、昏迷',
        desc:'立刻確認意識與呼吸，判斷是否需要 CPR。',
        steps:['叫名字、輕拍肩膀。','觀察呼吸：胸口是否有起伏。','有呼吸：讓個案側躺。','沒呼吸、沒意識：平躺，立即開始胸外按壓（CPR）。'],
        notices:['叫不醒／沒呼吸 ➔ 立即撥打 119，開擴音急救','同時通報督導與家屬'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
      { title:'大量流血', tag:'割傷、撞傷造成大量出血',
        desc:'立刻加壓止血，不要移除紗布。',
        steps:['用乾淨紗布或布料直接按壓傷口加壓。','持續加壓，不要一直掀開查看。','若血已透布，再加一塊紗布繼續壓。'],
        notices:['大量流血止不住 ➔ 撥打 119','小擦傷 ➔ 處理後通報督導與家屬'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
    ]
  },

  'orange': {
    icon: '🟠', title: '身體突然不舒服',
    headerBg: 'bg-white', headerText: 'text-gray-800',
    desc: '個案仍有意識，但突然不舒服或出現身體異常。',
    alert: null, topBtn: null, stepNumBg: '#f97316',
    items: [
      { title:'低血糖', tag:'冒冷汗、發抖、虛弱，嚴重會昏倒',
        desc:'血糖過低若不及時處理，可能導致昏迷。',
        steps:['人清醒：給予糖果、果汁或方糖等糖分。','15 分鐘後再確認狀況：症狀未改善，再補充糖分並求助。','人昏倒：不要餵食或喝水，立即求救。'],
        notices:['昏倒／抽搐／呼吸異常／補糖後仍沒改善 ➔ 立即撥打 119','狀況改善 ➔ 通報督導與家屬'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
      { title:'血壓太高或太低', tag:'頭暈、胸痛、喘或昏厥',
        desc:'先讓個案休息，再根據症狀決定是否就醫。',
        steps:['先坐下或平躺，休息後再量一次。','高血壓：很高又不舒服，立即求助。','低血壓：頭暈、無力先休息，不要走動。','觀察症狀：胸痛、喘、無力、說話不清、昏厥。'],
        notices:['胸痛／喘／說話不清／昏厥 ➔ 立即撥打 119','血壓異常但無明顯症狀 ➔ 重測，通報督導與家屬'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
      { title:'吃錯藥、重複或漏吃藥', tag:'吃錯時間、數量，或誤吞外用藥',
        desc:'不要催吐，保留藥袋提供醫護人員參考。',
        steps:['不要催吐。','找藥袋：看吃了什麼、幾顆、幾點吃。','留著藥袋／藥盒，給醫護人員查看。','觀察：頭暈、冒冷汗、發抖、嗜睡。'],
        notices:['意識模糊／想吐／呼吸急促 ➔ 撥打 119，帶上藥袋','情況穩定 ➔ 通報督導與家屬聯繫醫師'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
      { title:'一直嘔吐、腹瀉或疑似脫水', tag:'反覆嘔吐或腹瀉，容易脫水',
        desc:'防止嗆到，少量補水，注意脫水症狀。',
        steps:['先防嗆：讓個案側躺或身體前傾。','能喝水：少量、多次慢慢補充水分。','觀察脫水：口乾、尿量少、頭暈、無力、精神變差。'],
        notices:['持續吐／喝不下水／明顯脫水／血便／劇烈腹痛 ➔ 撥打 119 或盡速就醫'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
      { title:'流鼻血', tag:'突然大量流鼻血',
        desc:'坐直前傾壓鼻翼，持續 10 分鐘。',
        steps:['讓個案坐直並身體前傾，不要仰頭。','捏住鼻翼（不是鼻梁），持續壓 10 分鐘。','不要擤鼻、不要一直鬆手查看。'],
        notices:['大量出血／壓 10 分鐘仍不停／頭暈蒼白或意識改變 ➔ 撥打 119'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
    ]
  },

  'yellow': {
    icon: '🟡', title: '跌倒或受傷',
    headerBg: 'bg-white', headerText: 'text-gray-800',
    desc: '不要急著扶起；先確認意識、呼吸及受傷位置。',
    alert: null, topBtn: null, stepNumBg: '#eab308',
    items: [
      { title:'跌倒或掉下床', tag:'先看意識與呼吸，再看受傷位置',
        desc:'評估清醒程度與受傷部位，嚴重時不要隨意移動。',
        steps:['<strong>先看意識：</strong>有沒有清醒？呼吸正常嗎？','<strong>再看受傷：</strong>頭、胸腹、手腳、髖部哪裡痛？','流血就加壓止血。','腫痛可冰敷；痛或不能站，不要強行扶走。'],
        notices:['叫不醒／呼吸異常／劇烈疼痛／明顯變形／大量出血 ➔ 119＋通報督導、家屬','輕微擦傷／瘀青 ➔ 簡單處理＋通報，持續觀察'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
      { title:'燙傷', tag:'接觸熱水、熱湯造成燙傷',
        desc:'流冷水是最重要的第一步，切勿塗抹偏方。',
        steps:['立刻用流動冷水沖 15～20 分鐘。','衣物若黏住皮膚，不要硬撕。','不要塗牙膏、醬油、萬金油等。'],
        notices:['大面積燙傷 ➔ 撥打 119＋通報督導與家屬','小燙傷 ➔ 處理後通報督導與家屬'],
        calls:[{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
    ]
  },

  'purple': {
    icon: '🟣', title: '個案不見了',
    headerBg: 'bg-white', headerText: 'text-gray-800',
    desc: '個案不在家，或陪同外出時離開視線。',
    alert: null, topBtn: null, stepNumBg: '#9333ea',
    items: [
      { title:'個案不在家或外出走失', tag:'到案時找不到，或外出時離開視線',
        desc:'快速確認常去地點，記錄外觀特徵，不要獨自找太久。',
        steps:['快速查看案家周邊及個案常去的地方，不要獨自找太久。','確認衣著特徵：衣服顏色、鞋子顏色、有無手鍊或包包。','立即通報督導與家屬，說明目前情況。'],
        notices:['確定走失且找不到人 ➔ 通報督導與家屬，由家屬或督導陪同撥打 110 報案（攜帶個案照片與身分資料）'],
        calls:[{num:'110',label:'撥打 110 報案',cls:'bg-gray-700'}] },
    ]
  },

  'blue': {
    icon: '🔵', title: '皮膚或感染問題',
    headerBg: 'bg-white', headerText: 'text-gray-800',
    desc: '出現乾癢、紅腫、破皮、傷口或疑似疥瘡時，先防護再通報。',
    alert: null, topBtn: null, stepNumBg: '#2563eb',
    items: [
      { title:'皮膚乾癢或疑似疥瘡', tag:'疥瘡有傳染性，手指縫、肚臍周圍劇癢',
        desc:'疥瘡傳染性高，需做好個人防護再處理。',
        steps:['乾癢：協助保濕，提醒避免抓破皮。','疑似疥瘡：戴手套、隔離衣，避免直接接觸皮膚。','不要自行擦藥，依醫師指示處理。','衣物與床單先裝入袋中密封，再交由家屬處理。'],
        notices:['疑似疥瘡 ➔ 通報督導與家屬，盡快就醫確認'],
        calls:[] },
    ]
  },

  'attack': {
    icon: '🟥', title: '被罵、威脅或攻擊',
    headerBg: 'bg-white', headerText: 'text-gray-800',
    desc: null,
    alert: '🚨 先保護自己，不搶武器、不硬撐、不自行回到危險現場',
    topBtn: null, stepNumBg: '#dc2626',
    items: [
      { title:'被罵、威脅或攻擊', tag:'被罵、被威脅、被打，或家屬喝醉後情緒失控',
        desc:'確保自身安全是第一優先，不要試圖制止或反擊。',
        steps:['不爭吵、不刺激、不還手。','保持距離，立即停止服務並離開現場。','到安全處後通知督導。','有受傷就拍照記錄並就醫。','記錄事情經過並保留所有證據。'],
        notices:['有立即危險 ➔ <strong>110</strong>','有受傷 ➔ 119 或就醫','安全後 ➔ 通報居服督導及服務單位'],
        calls:[{num:'110',label:'撥打 110',cls:'bg-gray-700'},{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
    ]
  },

  'harass': {
    icon: '🩷', title: '遇到性騷擾',
    headerBg: 'bg-white', headerText: 'text-gray-800',
    desc: null, alert: null, topBtn: null, stepNumBg: '#ec4899',
    items: [
      { title:'遇到性騷擾', tag:'故意觸碰、黃色笑話、要求親密行為或色情訊息',
        desc:'您有權利拒絕任何讓您不舒服的行為，請明確表達並離開。',
        steps:['明確說：「請停止，這讓我不舒服。」','立即停止服務並離開現場。','安全後通知督導。','記錄事情經過，截圖或保留相關證據。','遭到強迫或有危險時，立即打 110。'],
        notices:['安全後 ➔ 通報居服督導及服務單位','有強迫或危險 ➔ <strong>110</strong>','需要諮詢 ➔ <strong>113</strong>（全國保護專線）'],
        calls:[{num:'113',label:'撥打 113 諮詢',cls:'bg-pink-500'},{num:'110',label:'撥打 110',cls:'bg-gray-700'}] },
    ]
  },

  'traffic': {
    icon: '⚫', title: '發生交通事故',
    headerBg: 'bg-white', headerText: 'text-gray-800',
    desc: null, alert: null, topBtn: null, stepNumBg: '#374151',
    items: [
      { title:'發生交通事故', tag:'騎車摔倒、車禍，或陪同外出時遇到事故',
        desc:'先確認人員安全，再處理現場。',
        steps:['立即停車並注意來車，移至安全位置。','有人受傷時不要隨意移動傷者。','撥打 110 報案；有人受傷需救護時再撥 119。','拍照記錄現場、車牌、傷勢，保留相關資料。'],
        notices:['交通事故 ➔ <strong>110</strong>','有人受傷 ➔ <strong>119</strong>','安全後 ➔ 通報居服督導及服務單位'],
        calls:[{num:'110',label:'撥打 110',cls:'bg-gray-700'},{num:'119',label:'撥打 119',cls:'bg-red-600'}] },
    ]
  },
};


// ══════════════════════════════════════════════
// 導覽堆疊控制 (支援直跳與正確返回)
// ══════════════════════════════════════════════
let historyStack = ['s-home'];

function showScreen(id, animClass) {
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  const el = document.getElementById(id);
  el.classList.add('active');
  el.classList.remove('anim-right','anim-left');
  void el.offsetWidth;
  el.classList.add(animClass);
  window.scrollTo(0,0);
}

function nav(screen, key, itemIdx) {
  if (screen === 's-cat') {
    renderCat(key);
    historyStack.push('s-cat');
    showScreen('s-cat', 'anim-right');
  } else if (screen === 's-detail') {
    renderDetail(key, itemIdx);
    historyStack.push('s-detail');
    showScreen('s-detail', 'anim-right');
  }
}

function goBack() {
  if (historyStack.length > 1) {
    historyStack.pop();
    const prev = historyStack[historyStack.length - 1];
    showScreen(prev, 'anim-left');
  } else {
    showScreen('s-home', 'anim-left');
  }
}


// ══════════════════════════════════════════════
// 渲染分類選單頁 (Screen 2)
// ══════════════════════════════════════════════
function renderCat(key) {
  const cat = cats[key];

  // Header 頂部欄
  const hdr = document.getElementById('cat-header');
  hdr.className = `sticky top-0 z-20 shadow-sm ${cat.headerBg}`;
  const btnEl = hdr.querySelector('button');
  btnEl.className = `p-1.5 rounded-full active:bg-black/10 ${cat.headerText}`;
  document.getElementById('cat-icon').textContent  = cat.icon;
  document.getElementById('cat-title').textContent = cat.title;
  document.getElementById('cat-title').className   = `font-bold text-base flex-1 ${cat.headerText}`;

  // 說明文字
  const descEl = document.getElementById('cat-desc');
  if (cat.desc) { descEl.textContent = cat.desc; descEl.classList.remove('hidden'); }
  else { descEl.classList.add('hidden'); }

  // 警告提示
  const alertEl = document.getElementById('cat-alert');
  if (cat.alert) {
    alertEl.innerHTML = `<div class="bg-red-50 border-l-4 border-red-400 rounded-r-2xl px-4 py-3 text-sm text-red-800 font-semibold">${cat.alert}</div>`;
    alertEl.classList.remove('hidden');
  } else { alertEl.classList.add('hidden'); }

  // 頂部按鈕 (如 119 撥號)
  const topBtn = document.getElementById('cat-top-btn');
  if (cat.topBtn) {
    topBtn.innerHTML = `<a href="${cat.topBtn.href}" class="flex items-center justify-center gap-2 ${cat.topBtn.cls} font-bold text-base rounded-2xl py-4 shadow-md active:opacity-80">${cat.topBtn.label}</a>`;
    topBtn.classList.remove('hidden');
  } else { topBtn.innerHTML = ''; }

  // 子項目清單列表
  const list = document.getElementById('cat-list');
  list.innerHTML = cat.items.map((item, i) => `
    <button onclick="nav('s-detail','${key}',${i})"
      class="tap-card w-full text-left bg-white rounded-2xl px-5 py-4 flex items-center gap-4 shadow-sm border border-gray-100">
      <div class="w-8 h-8 rounded-full flex items-center justify-center text-sm font-bold text-white flex-shrink-0"
           style="background:${cat.stepNumBg}">${i+1}</div>
      <div class="flex-1 min-w-0">
        <div class="font-bold text-gray-800 text-sm leading-tight">${item.title}</div>
        <div class="text-gray-400 text-xs mt-0.5 leading-snug truncate">${item.tag}</div>
      </div>
      <svg class="w-5 h-5 text-gray-300 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2.5">
        <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7"/>
      </svg>
    </button>
  `).join('');
}


// ══════════════════════════════════════════════
// 渲染步驟詳細頁 (Screen 3)
// ══════════════════════════════════════════════
function renderDetail(key, idx) {
  const cat  = cats[key];
  const item = cat.items[idx];

  // Header 頂部欄：若只有一項則顯示 emoji，多項則顯示序號
  const numEl = document.getElementById('detail-num');
  if (cat.items.length === 1) {
    numEl.textContent = cat.icon;
    numEl.style.background = 'transparent';
    numEl.className = 'text-2xl flex items-center justify-center flex-shrink-0';
  } else {
    numEl.textContent = idx + 1;
    numEl.style.background = cat.stepNumBg;
    numEl.className = 'w-7 h-7 rounded-full flex items-center justify-center text-xs font-bold text-white flex-shrink-0';
  }
  document.getElementById('detail-title').textContent = item.title;

  // 內容主體
  const body = document.getElementById('detail-body');

  // 安全警示 (如有，置頂顯示)
  const alertBlock = cat.alert ? `
    <div class="bg-red-50 border-l-4 border-red-400 rounded-r-2xl px-4 py-3 text-sm text-red-800 font-semibold">
      ${cat.alert}
    </div>` : '';

  // 情況說明卡片
  const descBlock = item.desc ? `
    <div class="bg-white rounded-2xl px-5 py-4 shadow-sm border border-gray-100">
      <div class="text-xs text-gray-400 font-semibold tracking-wide uppercase mb-1">情況說明</div>
      <p class="text-sm text-gray-600 leading-relaxed">${item.desc}</p>
    </div>` : '';

  // 處理步驟清單
  const stepsHtml = item.steps.map(s => `<li><span class="text-sm text-gray-700 leading-relaxed">${s}</span></li>`).join('');
  const stepsBlock = `
    <div class="bg-white rounded-2xl px-5 py-4 shadow-sm border border-gray-100">
      <div class="text-xs text-gray-400 font-semibold tracking-wide uppercase mb-3">處理步驟</div>
      <ol class="steps">${stepsHtml}</ol>
    </div>`;

  // 通報對象與指引
  const noticeHtml = item.notices.map(n => `
    <div class="flex gap-2 items-start">
      <span class="text-base flex-shrink-0 mt-0.5">▶</span>
      <p class="text-sm text-gray-700 leading-relaxed">${n}</p>
    </div>`).join('');
  const noticeBlock = noticeHtml ? `
    <div class="bg-gray-50 rounded-2xl px-5 py-4 shadow-sm border border-gray-200">
      <div class="text-xs text-gray-400 font-semibold tracking-wide uppercase mb-3">通報與處理方式</div>
      <div class="space-y-3">${noticeHtml}</div>
    </div>` : '';

  // 一鍵撥號按鈕
  const callHtml = item.calls.map(c =>
    `<a href="tel:${c.num}" class="flex-1 flex items-center justify-center gap-2 ${c.cls} text-white font-bold text-base rounded-2xl py-4 shadow-md active:opacity-75">📞 ${c.label}</a>`
  ).join('');
  const callBlock = callHtml ? `<div class="flex gap-3">${callHtml}</div>` : '';

  body.innerHTML = alertBlock + descBlock + stepsBlock + noticeBlock + callBlock;

  // 動態更新步驟數字圓圈顏色
  const styleId = 'step-color-style';
  let styleEl = document.getElementById(styleId);
  if (!styleEl) { styleEl = document.createElement('style'); styleEl.id = styleId; document.head.appendChild(styleEl); }
  styleEl.textContent = `#detail-body ol.steps li::before { background: ${cat.stepNumBg} !important; }`;
}
</script>
</body>
</html>
