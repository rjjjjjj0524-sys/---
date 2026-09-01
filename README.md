<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的全新網站</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
</head>
<body class="bg-gray-50 text-gray-800 font-sans antialiased">

    <!-- 1. 導覽列 (Navigation Bar) -->
    <header class="sticky top-0 z-50 bg-white/90 backdrop-blur-md shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <!-- Logo -->
                <div class="flex-shrink-0 flex items-center">
                    <a href="#" class="text-2xl font-bold text-indigo-600">MyBrand</a>
                </div>
                
                <!-- 選單項目 (桌面版) -->
                <nav class="hidden md:flex space-x-8">
                    <a href="#features" class="text-gray-600 hover:text-indigo-600 transition">服務特色</a>
                    <a href="#about" class="text-gray-600 hover:text-indigo-600 transition">關於我們</a>
                    <a href="#contact" class="text-gray-600 hover:text-indigo-600 transition">聯絡資訊</a>
                </nav>

                <!-- 動作按鈕 -->
                <div class="hidden md:flex items-center">
                    <a href="#contact" class="px-4 py-2 rounded-lg bg-indigo-600 text-white font-medium hover:bg-indigo-700 transition">立即開始</a>
                </div>
            </div>
        </div>
    </header>

    <!-- 2. 主視覺區塊 (Hero Section) -->
    <section class="py-20 bg-gradient-to-b from-indigo-50 to-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <h1 class="text-4xl sm:text-6xl font-extrabold text-gray-900 tracking-tight">
                打造屬於你的 <span class="text-indigo-600">專業網站</span>
            </h1>
            <p class="mt-4 text-lg sm:text-xl text-gray-600 max-w-2xl mx-auto">
                這是透過 HTML 與 Tailwind CSS 打造的靜態網頁，可以完全免費託管在 GitHub Pages 上。
            </p>
            <div class="mt-8 flex justify-center gap-4">
                <a href="#features" class="px-6 py-3 rounded-lg bg-indigo-600 text-white font-medium shadow-md hover:bg-indigo-700 transition">探索更多</a>
                <a href="https://github.com" target="_blank" class="px-6 py-3 rounded-lg bg-white text-gray-700 font-medium border border-gray-300 hover:bg-gray-50 transition">前往 GitHub</a>
            </div>
        </div>
    </section>

    <!-- 3. 特色區塊 (Features) -->
    <section id="features" class="py-16">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-gray-900">網站核心優勢</h2>
                <p class="text-gray-500 mt-2">輕量、快速且支援所有現代裝置</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- 卡片 1 -->
                <div class="p-6 bg-white rounded-xl shadow-sm border border-gray-100 hover:shadow-md transition">
                    <div class="w-12 h-12 bg-indigo-100 text-indigo-600 rounded-lg flex items-center justify-center text-xl mb-4">
                        <i class="fa-solid font-bold fa-bolt"></i>
                    </div>
                    <h3 class="text-xl font-semibold text-gray-800">超高載入速度</h3>
                    <p class="text-gray-600 mt-2">靜態網頁結構無伺服器延遲，載入順暢無負擔。</p>
                </div>

                <!-- 卡片 2 -->
                <div class="p-6 bg-white rounded-xl shadow-sm border border-gray-100 hover:shadow-md transition">
                    <div class="w-12 h-12 bg-indigo-100 text-indigo-600 rounded-lg flex items-center justify-center text-xl mb-4">
                        <i class="fa-solid fa-mobile-screen"></i>
                    </div>
                    <h3 class="text-xl font-semibold text-gray-800">響應式設計</h3>
                    <p class="text-gray-600 mt-2">自動適應手機、平板與電腦螢幕解析度。</p>
                </div>

                <!-- 卡片 3 -->
                <div class="p-6 bg-white rounded-xl shadow-sm border border-gray-100 hover:shadow-md transition">
                    <div class="w-12 h-12 bg-indigo-100 text-indigo-600 rounded-lg flex items-center justify-center text-xl mb-4">
                        <i class="fa-solid fa-cloud-arrow-up"></i>
                    </div>
                    <h3 class="text-xl font-semibold text-gray-800">GitHub 免費託管</h3>
                    <p class="text-gray-600 mt-2">只需將程式碼推送至儲存庫即可自動部署上線。</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 4. 頁尾 (Footer) -->
    <footer class="bg-gray-900 text-gray-400 py-8 border-t border-gray-800">
        <div class="max-w-7xl mx-auto px-4 text-center">
            <p>© 2026 MyBrand. All rights reserved. Hosted on GitHub Pages.</p>
        </div>
    </footer>

</body>
</html>
