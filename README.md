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

