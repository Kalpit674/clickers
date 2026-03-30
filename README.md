<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ore Clicker - Mine Your Way to Riches</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            primary: '#1A2E4A',
            accent: '#F5A623'
          }
        }
      }
    }
  </script>
  <style>
    html { scroll-behavior: smooth; }
    .stagger-1 { animation: fadeInUp 0.8s ease-out 0.1s both; }
    .stagger-2 { animation: fadeInUp 0.8s ease-out 0.2s both; }
    .stagger-3 { animation: fadeInUp 0.8s ease-out 0.3s both; }
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .hover-lift { transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); }
    .hover-lift:hover { transform: translateY(-4px); }
    .count-anim { transition: all 0.5s ease-out; }
  </style>
</head>
<body class="bg-gradient-to-br from-slate-50 to-slate-100 text-slate-800 font-sans antialiased">

  <!-- STICKY NAVIGATION -->
  <nav class="sticky top-0 z-50 bg-white/95 backdrop-blur-md border-b border-slate-200 shadow-sm">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center py-4">
        <!-- Logo -->
        <a href="#hero" class="flex items-center space-x-2 group">
          <div class="w-10 h-10 bg-gradient-to-r from-primary to-accent rounded-xl shadow-lg flex items-center justify-center">
            <div class="w-6 h-6 bg-white/20 rounded-full"></div>
          </div>
          <span class="text-2xl font-bold bg-gradient-to-r from-primary to-accent bg-clip-text text-transparent">Ore Clicker</span>
        </a>

        <!-- Desktop Links -->
        <div class="hidden md:flex items-center space-x-6">
          <a href="#hero" class="text-lg font-medium text-slate-700 hover:text-primary transition-colors">Play</a>
          <a href="#how-to-play" class="text-lg font-medium text-slate-700 hover:text-primary transition-colors">How to Play</a>
          <a href="#leaderboard" class="text-lg font-medium text-slate-700 hover:text-primary transition-colors">Leaderboard</a>
          <a href="#blog" class="text-lg font-medium text-slate-700 hover:text-primary transition-colors">Blog</a>
        </div>

        <!-- Save Progress Button -->
        <button id="saveBtn" class="md:flex hidden bg-accent text-primary px-6 py-2 rounded-xl font-semibold shadow-lg hover:shadow-xl hover:scale-105 transition-all duration-300">
          Save Progress
        </button>

        <!-- Mobile Menu Button -->
        <button id="mobileMenuBtn" class="md:hidden p-2 -mr-1 rounded-lg hover:bg-slate-100 focus:outline-none focus:shadow-outline">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
        </button>
      </div>

      <!-- Mobile Menu -->
      <div id="mobileMenu" class="md:hidden hidden pb-4 space-y-2">
        <a href="#hero" class="block px-4 py-2 text-lg font-medium text-slate-700 hover:text-primary hover:bg-slate-100 rounded-lg">Play</a>
        <a href="#how-to-play" class="block px-4 py-2 text-lg font-medium text-slate-700 hover:text-primary hover:bg-slate-100 rounded-lg">How to Play</a>
        <a href="#leaderboard" class="block px-4 py-2 text-lg font-medium text-slate-700 hover:text-primary hover:bg-slate-100 rounded-lg">Leaderboard</a>
        <a href="#blog" class="block px-4 py-2 text-lg font-medium text-slate-700 hover:text-primary hover:bg-slate-100 rounded-lg">Blog</a>
        <button id="saveBtnMobile" class="w-full bg-accent text-primary px-6 py-3 rounded-xl font-semibold shadow-lg hover:shadow-xl hover:scale-105 transition-all duration-300">
          Save Progress
        </button>
      </div>
    </div>
  </nav>

  <!-- HERO — GAME EMBED -->
  <section id="hero" class="pt-24 pb-20 bg-gradient-to-b from-primary/5 to-slate-100">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
      <h1 class="text-5xl md:text-7xl font-black bg-gradient-to-r from-primary via-slate-800 to-accent bg-clip-text text-transparent mb-6 stagger-1">
        Ore Clicker
      </h1>
      <p class="text-xl md:text-2xl text-slate-600 mb-12 max-w-2xl mx-auto stagger-2">
        Mine endless riches with one click. Become the ultimate ore tycoon.
      </p>
      
      <!-- Game Iframe -->
      <div class="max-w-4xl mx-auto mb-12 stagger-3">
        <iframe 
          src="game.html" 
          class="w-full h-[500px] md:h-[600px] rounded-3xl border-4 border-accent shadow-2xl bg-slate-200"
          title="Ore Clicker Game"
        ></iframe>
      </div>

      <!-- Live Stats -->
      <div class="flex flex-col sm:flex-row gap-8 justify-center items-center mb-12">
        <div id="playersOnline" class="text-2xl md:text-3xl font-bold text-slate-700 count-anim">
          Players online: 1,247
        </div>
        <div class="w-px h-12 bg-slate-300 hidden sm:block"></div>
        <div id="totalClicks" class="text-2xl md:text-3xl font-bold text-slate-700 count-anim">
          Total clicks today: 84,203,910
        </div>
      </div>

      <!-- CTA Button -->
      <a href="#hero" class="inline-block bg-accent text-primary px-12 py-6 text-2xl font-bold rounded-3xl shadow-2xl hover:shadow-3xl hover:scale-105 transition-all duration-300 hover:-translate-y-1 stagger-3">
        Start Clicking Free
      </a>
    </div>
  </section>

  <!-- FEATURES STRIP -->
  <section class="py-24 bg-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <!-- Feature 1 -->
        <div class="text-center p-8 rounded-3xl bg-gradient-to-b from-slate-50 to-white shadow-xl hover:shadow-2xl transition-all duration-300 hover:-translate-y-2">
          <div class="w-20 h-20 mx-auto mb-6 bg-gradient-to-r from-accent to-yellow-500 rounded-3xl flex items-center justify-center shadow-lg">
            <div class="w-8 h-8 bg-white rounded-full shadow-md"></div>
          </div>
          <h3 class="text-2xl font-bold text-slate-800 mb-4">Instant Play</h3>
          <p class="text-slate-600">No download, no sign-up. Start mining riches immediately.</p>
        </div>

        <!-- Feature 2 -->
        <div class="text-center p-8 rounded-3xl bg-gradient-to-b from-slate-50 to-white shadow-xl hover:shadow-2xl transition-all duration-300 hover:-translate-y-2">
          <div class="w-20 h-20 mx-auto mb-6 bg-gradient-to-r from-accent to-yellow-500 rounded-3xl flex items-center justify-center shadow-lg">
            <svg class="w-8 h-8 text-primary" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M5 2a1 1 0 011 1v1h1a1 1 0 010 2H6v1a1 1 0 01-2 0V6H3a1 1 0 010-2h1V3a1 1 0 011-1zm0 10a1 1 0 011 1v1h1a1 1 0 110 2H6v1a1 1 0 11-2 0v-1H3a1 1 0 110-2h1v-1a1 1 0 011-1zM12 2a1 1 0 01.967.744L14.146 7.2 17.5 9.134a1 1 0 010 1.732l-3.354 1.935-1.18 4.455a1 1 0 01-1.933 0L9.854 12.67 6.5 10.866a1 1 0 010-1.732l3.354-1.935 1.18-4.455A1 1 0 0112 2z" clip-rule="evenodd"></path>
            </svg>
          </div>
          <h3 class="text-2xl font-bold text-slate-800 mb-4">100+ Upgrades</h3>
          <p class="text-slate-600">Passive income, multipliers, and prestige systems to skyrocket your earnings.</p>
        </div>

        <!-- Feature 3 -->
        <div class="text-center p-8 rounded-3xl bg-gradient-to-b from-slate-50 to-white shadow-xl hover:shadow-2xl transition-all duration-300 hover:-translate-y-2">
          <div class="w-20 h-20 mx-auto mb-6 bg-gradient-to-r from-accent to-yellow-500 rounded-3xl flex items-center justify-center shadow-lg">
            <div class="w-3 h-3 bg-white rounded-full relative">
              <div class="w-3 h-3 bg-white rounded-full absolute -top-1 -right-1"></div>
              <div class="w-3 h-3 bg-white rounded-full absolute -bottom-1 -left-1"></div>
            </div>
          </div>
          <h3 class="text-2xl font-bold text-slate-800 mb-4">Global Leaderboard</h3>
          <p class="text-slate-600">Compete with players worldwide and claim your spot at the top.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- HOW TO PLAY -->
  <section id="how-to-play" class="py-24 bg-gradient-to-b from-slate-50 to-primary/5">
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
      <h2 class="text-4xl md:text-5xl font-black text-center text-slate-800 mb-20 bg-gradient-to-r from-slate-800 to-primary bg-clip-text text-transparent">
        Master Ore Mining in 3 Steps
      </h2>
      <div class="grid grid-cols-1 lg:grid-cols-3 gap-8 items-stretch">
        <!-- Step 1 -->
        <div class="group bg-white rounded-3xl p-10 shadow-xl hover:shadow-2xl transition-all duration-300 hover:-translate-y-4 flex flex-col">
          <div class="w-20 h-20 bg-accent text-primary text-3xl font-black rounded-3xl flex items-center justify-center shadow-2xl mb-6 group-hover:scale-110 transition-transform duration-300">1</div>
          <h3 class="text-2xl font-bold text-slate-800 mb-4">Click Ore</h3>
          <p class="text-slate-600 flex-1">Click the giant ore to earn ore instantly. Every click counts toward your fortune.</p>
        </div>

        <!-- Step 2 -->
        <div class="group bg-white rounded-3xl p-10 shadow-xl hover:shadow-2xl transition-all duration-300 hover:-translate-y-4 flex flex-col lg:before:hidden lg:after:hidden">
          <div class="w-20 h-20 bg-accent text-primary text-3xl font-black rounded-3xl flex items-center justify-center shadow-2xl mb-6 group-hover:scale-110 transition-transform duration-300">2</div>
          <h3 class="text-2xl font-bold text-slate-800 mb-4">Buy Upgrades</h3>
          <p class="text-slate-600 flex-1">Spend your ore on miners, drills, and factories that generate passive income automatically.</p>
        </div>

        <!-- Step 3 -->
        <div class="group bg-white rounded-3xl p-10 shadow-xl hover:shadow-2xl transition-all duration-300 hover:-translate-y-4 flex flex-col">
          <div class="w-20 h-20 bg-accent text-primary text-3xl font-black rounded-3xl flex items-center justify-center shadow-2xl mb-6 group-hover:scale-110 transition-transform duration-300">3</div>
          <h3 class="text-2xl font-bold text-slate-800 mb-4">Prestige Reset</h3>
          <p class="text-slate-600 flex-1">Reset your progress for permanent multipliers that make every future click worth exponentially more.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- LEADERBOARD TEASER -->
  <section id="leaderboard" class="py-24 bg-white">
    <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-black text-slate-800 mb-4 bg-gradient-to-r from-slate-800 to-primary bg-clip-text text-transparent">
          Top Clickers This Week
        </h2>
        <p class="text-xl text-slate-600">See where you rank among the mining elite</p>
      </div>

      <!-- Leaderboard Table -->
      <div class="bg-gradient-to-b from-slate-50 to-white rounded-3xl shadow-2xl overflow-hidden">
        <table class="w-full">
          <thead>
            <tr class="bg-gradient-to-r from-primary to-accent text-white">
              <th class="px-8 py-6 text-left font-bold">#</th>
              <th class="px-8 py-6 text-left font-bold">Player</th>
              <th class="px-8 py-6 text-left font-bold">Ore Mined</th>
              <th class="px-8 py-6 text-left font-bold">Badge</th>
            </tr>
          </thead>
          <tbody class="divide-y divide-slate-200">
            <tr class="bg-accent/20 hover:bg-accent/30 transition-colors">
              <td class="px-8 py-6 font-black text-2xl text-accent">1</td>
              <td class="px-8 py-6 font-bold text-slate-800">DeepMinerX</td>
              <td class="px-8 py-6 font-bold text-2xl">2.4T</td>
              <td class="px-8 py-6">
                <div class="w-8 h-8 bg-gradient-to-r from-yellow-400 to-yellow-600 rounded-full shadow-lg flex items-center justify-center">
                  <div class="w-3 h-3 bg-white rounded-full"></div>
                </div>
              </td>
            </tr>
            <tr class="hover:bg-slate-50 transition-colors">
              <td class="px-8 py-6 font-bold text-slate-600">2</td>
              <td class="px-8 py-6 font-semibold">OreLord99</td>
              <td class="px-8 py-6 font-bold">1.8T</td>
              <td class="px-8 py-6">
                <div class="w-8 h-8 bg-gradient-to-r from-emerald-400 to-emerald-600 rounded-full shadow-lg"></div>
              </td>
            </tr>
            <tr class="hover:bg-slate-50 transition-colors">
              <td class="px-8 py-6 font-bold text-slate-600">3</td>
              <td class="px-8 py-6 font-semibold">DrillMaster</td>
              <td class="px-8 py-6 font-bold">1.5T</td>
              <td class="px-8 py-6">
                <div class="w-8 h-8 bg-gradient-to-r from-purple-400 to-purple-600 rounded-full shadow-lg"></div>
              </td>
            </tr>
            <tr class="hover:bg-slate-50 transition-colors">
              <td class="px-8 py-6 font-bold text-slate-600">4</td>
              <td class="px-8 py-6 font-semibold">GoldVein</td>
              <td class="px-8 py-6 font-bold">1.2T</td>
              <td class="px-8 py-6">
                <div class="w-8 h-8 bg-gradient-to-r from-blue-400 to-blue-600 rounded-full shadow-lg"></div>
              </td>
            </tr>
            <tr class="hover:bg-slate-50 transition-colors">
              <td class="px-8 py-6 font-bold text-slate-600">5</td>
              <td class="px-8 py-6 font-semibold">RockSmasher</td>
              <td class="px-8 py-6 font-bold">1.0T</td>
              <td class="px-8 py-6">
                <div class="w-8 h-8 bg-gradient-to-r from-orange-400 to-orange
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: 0.2s;
        }
        #clickButton:hover {
            background-color: #218838;
        }
        #clickButton:active {
            transform: scale(0.95);
        }
    </style>
</head>
<body>

    <h1>Tap Tap Clicker Game</h1>
    <p id="score">Score: 0</p>
    <button id="clickButton">Tap to Earn Points</button>

    <script>
        let score = 0;
        const scoreDisplay = document.getElementById("score");
        const button = document.getElementById("clickButton");

        button.addEventListener("click", function() {
            score++;
            scoreDisplay.innerText = "Score: " + score;
        });
    </script>

</body>
</html># clickers
game to pass the time long journeys
