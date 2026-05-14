<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crypto Profit Calculator</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.9.3/dist/confetti.browser.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Philosopher:wght@400;700&family=Space+Mono:wght@400;700&display=swap');
        
        body {
            font-family: 'Inter', sans-serif;
            background-color: #23292F; 
            overflow-x: hidden;
            transition: background-color 0.5s ease;
            color: #dde0f0;
        }

        .font-philosopher { font-family: 'Philosopher', sans-serif; }
        .font-mono-custom { font-family: 'Space Mono', monospace; }
        
        /* --- HARVARD UI FIX: Remove browser arrows --- */
        input::-webkit-inner-spin-button,
        input::-webkit-outer-spin-button {
            -webkit-appearance: none;
            margin: 0;
        }

        /* --- OS Dropdown Visibility Fix --- */
        select option {
            background-color: #1f2937;
            color: #ffffff;
        }
        
        /* General Cards */
        .crypto-card {
            background-color: #e4e7ec;
            border: 1px solid rgba(255, 255, 255, 0.6);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        }
        
        .input-field {
            background-color: #f8fafc;
            font-size: 1.125rem !important;
            color: #111827 !important;
            letter-spacing: 0.025em;
            transition: all 0.2s ease-in-out;
        }

        .input-field:focus {
            transform: translateY(-1px);
            background-color: #ffffff;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }

        /* Animations */
        @keyframes levitate {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        @keyframes pulseGlow {
            0%, 100% { transform: scale(1); opacity: 0.7; }
            50% { transform: scale(1.05); opacity: 0.95; }
        }

        .aura-circle {
            transform-origin: 200px 180px;
            animation: pulseGlow 6s infinite ease-in-out;
        }

        .monkey-bg {
            position: fixed;
            top: 20px;
            right: 2vw;
            width: 350px;
            height: 350px;
            z-index: 0;
            pointer-events: none;
            filter: drop-shadow(0 15px 25px rgba(0,0,0,0.25));
        }

        .monkey-bg svg {
            animation: levitate 6s infinite ease-in-out;
            overflow: visible;
        }

        /* Number Rain Canvas - Covers Entire Screen */
        #matrix-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -1; 
            pointer-events: none;
            background-color: #000000;
            display: none; 
        }

        /* Premium Glassmorphism */
        .glass-card {
            background: rgba(17, 19, 24, 0.7);
            backdrop-filter: blur(24px);
            -webkit-backdrop-filter: blur(24px);
            border: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: 0 30px 60px -12px rgba(0, 0, 0, 1);
        }

        /* PERP specific UI styles */
        .perp-input {
            background: #181a21;
            border: 1px solid #282b3a;
            color: white;
            transition: all 0.2s ease;
        }
        .perp-input:focus {
            border-color: #6366f1; /* Indigo 500 */
            box-shadow: 0 0 0 2px rgba(99, 102, 241, 0.2);
            outline: none;
        }
        
        .perp-range {
            -webkit-appearance: none;
            width: 100%;
            height: 4px;
            border-radius: 2px;
            background: #282b3a;
            outline: none;
        }
        .perp-range::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 16px; height: 16px;
            border-radius: 50%;
            background: #6366f1;
            border: 2px solid #0b0c10;
            box-shadow: 0 0 8px rgba(99,102,241,0.6);
            cursor: pointer;
            transition: transform 0.1s;
        }
        .perp-range::-webkit-slider-thumb:hover { transform: scale(1.2); }

        .dir-btn { transition: all 0.2s ease; }
        .dir-btn.long.active { background: rgba(16, 185, 129, 0.15); color: #34d399; border-color: rgba(16, 185, 129, 0.4); box-shadow: 0 0 15px rgba(16, 185, 129, 0.1); }
        .dir-btn.short.active { background: rgba(244, 63, 94, 0.15); color: #fb7185; border-color: rgba(244, 63, 94, 0.4); box-shadow: 0 0 15px rgba(244, 63, 94, 0.1); }
    </style>
</head>
<body class="min-h-screen p-6 md:p-12 relative">

    <!-- Global Matrix Canvas -->
    <canvas id="matrix-canvas"></canvas>

    <!-- Bitcoin Symbol -->
    <div id="btc-logo-main" class="fixed top-6 left-6 md:top-8 md:left-8 z-50 text-[#F7931A] drop-shadow-[0_4px_8px_rgba(0,0,0,0.5)] cursor-pointer hover:scale-110 transition-transform" title="Bitcoin">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32" class="w-12 h-12 md:w-14 md:h-14 fill-current">
            <path d="M23.94 13.56c.4-2.68-1.63-4.13-4.39-5.07l.9-3.6-2.19-.55-.89 3.56c-.57-.14-1.16-.28-1.75-.41l.89-3.56-2.19-.55-.9 3.6c-.48-.11-.95-.23-1.4-.35l.01-.04-3.02-.75-.58 2.33s1.62.38 1.59.39c.89.22 1.05.81 1.02 1.28l-1.02 4.1c.06.01.14.04.22.08-.07-.02-.15-.03-.22-.05l-1.43 5.73c-.11.27-.39.68-1.01.53.02.01-1.6-.4-1.6-.4l-1.1 2.53 2.85.71c.53.13 1.05.27 1.57.4l-.9 3.63 2.19.55.9-3.61c.6.16 1.18.3 1.74.43l-.9 3.62 2.19.55.91-3.65c3.75.71 6.57.43 7.37-2.92.65-2.68-.07-4.24-1.92-5.25 1.37-.32 2.4-1.32 2.67-3.32zm-2.45 6.94c-.67 2.68-5.18 1.24-6.64.88l1.18-4.73c1.46.36 6.16 1.07 5.46 3.85zm.6-6.85c-.61 2.45-4.38 1.2-5.59.9l1.07-4.3c1.21.3 5.16.85 4.52 3.4z"/>
        </svg>
    </div>

    <!-- Monkey Container -->
    <div id="monkey-container" class="monkey-bg hidden md:block">
        <svg viewBox="0 0 400 400" xmlns="http://www.w3.org/2000/svg">
            <defs>
                <linearGradient id="robeBase" x1="0%" y1="0%" x2="100%" y2="100%"><stop offset="0%" stop-color="#f39c12"/><stop offset="50%" stop-color="#d35400"/><stop offset="100%" stop-color="#a04000"/></linearGradient>
                <linearGradient id="robeDark" x1="0%" y1="100%" x2="0%" y2="0%"><stop offset="0%" stop-color="#873600"/><stop offset="100%" stop-color="#d35400"/></linearGradient>
                <radialGradient id="furGrad" cx="50%" cy="50%" r="50%"><stop offset="0%" stop-color="#5d4037"/><stop offset="80%" stop-color="#3e2723"/><stop offset="100%" stop-color="#1b100b"/></radialGradient>
                <radialGradient id="skinGrad" cx="50%" cy="50%" r="50%"><stop offset="0%" stop-color="#e3b98c"/><stop offset="70%" stop-color="#c49a6c"/><stop offset="100%" stop-color="#8d6e63"/></radialGradient>
                <filter id="shadow" x="-10%" y="-10%" width="120%" height="120%"><feDropShadow dx="0" dy="5" stdDeviation="4" flood-opacity="0.4"/></filter>
            </defs>
            <circle class="aura-circle" cx="200" cy="180" r="140" fill="#ffecb3" />
            <path d="M 40 330 C 40 380, 360 380, 360 330 C 360 290, 300 290, 200 290 C 100 290, 40 290, 40 330 Z" fill="#873600" filter="url(#shadow)"/>
            <path d="M 60 330 C 60 365, 340 365, 340 330 C 340 300, 280 290, 200 290 C 120 290, 60 300, 60 330 Z" fill="url(#robeBase)"/>
            <path d="M 100 310 Q 150 340 200 340 Q 250 340 300 310" fill="none" stroke="#a04000" stroke-width="4" stroke-linecap="round"/>
            <path d="M 120 200 L 280 200 L 300 310 C 250 330, 150 330, 100 310 Z" fill="url(#robeDark)"/>
            <path d="M 110 240 C 90 280, 140 300, 180 315" stroke="url(#furGrad)" stroke-width="22" stroke-linecap="round" fill="none"/>
            <path d="M 290 240 C 310 280, 260 300, 220 315" stroke="url(#furGrad)" stroke-width="22" stroke-linecap="round" fill="none"/>
            <ellipse cx="200" cy="318" rx="28" ry="14" fill="url(#skinGrad)" filter="url(#shadow)"/>
            <ellipse cx="200" cy="140" rx="60" ry="65" fill="url(#furGrad)" filter="url(#shadow)"/>
            <path d="M 160 125 C 160 100, 240 100, 240 125 C 240 160, 220 185, 200 185 C 180 185, 160 160, 160 125 Z" fill="url(#skinGrad)" filter="url(#shadow)"/>
        </svg>
    </div>

    <!-- Landing Page (Initial View) -->
    <div id="landing-page" class="flex flex-col items-center justify-center min-h-[80vh] relative z-20 transition-all duration-500 transform scale-100">
        <h1 class="text-5xl md:text-7xl font-bold font-philosopher text-transparent bg-clip-text bg-gradient-to-r from-orange-400 via-emerald-400 to-blue-400 mb-10 tracking-tight text-center drop-shadow-lg leading-tight uppercase">
            Crypto Profit
        </h1>
        <div class="flex flex-col gap-4 items-center">
            <button onclick="openCalculator()" class="group flex items-center gap-4 px-12 py-5 w-full bg-gradient-to-r from-blue-600 to-purple-600 hover:from-blue-500 hover:to-purple-500 text-white text-2xl font-bold rounded-2xl shadow-[0_0_20px_rgba(139,92,246,0.4)] hover:-translate-y-1 transition-all duration-300">
                <i class="fa-solid fa-calculator group-hover:rotate-12 transition-transform"></i> Calculator
            </button>
            <button onclick="openWhatIf()" class="group flex items-center gap-4 px-12 py-5 w-full bg-gradient-to-r from-amber-500 to-orange-600 hover:from-amber-400 hover:to-orange-500 text-white text-2xl font-bold rounded-2xl shadow-[0_0_20px_rgba(245,158,11,0.3)] hover:-translate-y-1 transition-all duration-300">
                <i class="fa-solid fa-clock-rotate-left group-hover:-rotate-12 transition-transform"></i> WHAT IF
            </button>
            <p class="mt-2 text-gray-400 text-xs font-bold uppercase tracking-[0.2em] text-center drop-shadow-md">
                Stay Rational. <span class="text-amber-500">Don't get FOMO'd in.</span>
            </p>
            <button onclick="openGymSchedule()" class="group flex items-center gap-4 px-12 py-5 w-full bg-gradient-to-r from-emerald-600 to-teal-600 hover:from-emerald-500 hover:to-teal-500 text-white text-2xl font-bold rounded-2xl shadow-[0_0_20px_rgba(16,185,129,0.3)] hover:-translate-y-1 transition-all duration-300 mt-2">
                <i class="fa-solid fa-dumbbell group-hover:-rotate-12 transition-transform"></i> GYM SCHEDULE
            </button>
            
            <!-- NEW: PERP BUTTON -->
            <button onclick="openPerp()" class="group flex items-center gap-4 px-12 py-5 w-full bg-gradient-to-r from-indigo-600 to-blue-700 hover:from-indigo-500 hover:to-blue-600 text-white text-2xl font-bold rounded-2xl shadow-[0_0_20px_rgba(99,102,241,0.3)] hover:-translate-y-1 transition-all duration-300">
                <i class="fa-solid fa-bolt group-hover:scale-110 transition-transform text-amber-300"></i> PERP
            </button>
        </div>
    </div>

    <!-- Main Content Wrapper (Calculator App) -->
    <div id="calculator-app" class="hidden opacity-0 translate-y-4 max-w-4xl mx-auto space-y-6 relative z-10 transition-all duration-700">
        <button onclick="goBackToLanding()" class="group flex items-center gap-2 px-4 py-2 bg-white/5 hover:bg-white/10 text-gray-400 hover:text-white rounded-xl transition-all border border-white/5 focus:outline-none">
            <i class="fa-solid fa-chevron-left text-xs transition-transform group-hover:-translate-x-1"></i>
            <span class="text-xs font-black uppercase tracking-widest">Back to Menu</span>
        </button>

        <div class="text-center mb-10">
            <h1 class="text-4xl md:text-5xl font-bold font-philosopher text-transparent bg-clip-text bg-gradient-to-r from-orange-400 via-emerald-400 to-blue-400 mb-4 tracking-tight uppercase">Analysis Suite</h1>
            <div class="flex justify-center gap-2 flex-wrap">
                <button onclick="highlightCard('btc')" class="px-4 py-1.5 bg-[#F7931A] text-white rounded-lg text-sm font-bold shadow-sm transition-all hover:-translate-y-1">BTC</button>
                <button onclick="highlightCard('eth')" class="px-4 py-1.5 bg-blue-400 text-white rounded-lg text-sm font-bold shadow-sm transition-all hover:-translate-y-1">ETH</button>
                <button onclick="highlightCard('sol')" class="px-4 py-1.5 bg-[#4ade80] text-emerald-950 rounded-lg text-sm font-bold shadow-sm transition-all hover:-translate-y-1">SOL</button>
                <button onclick="highlightCard('hype')" class="px-4 py-1.5 bg-[#97FCE4] text-gray-800 rounded-lg text-sm font-bold shadow-sm transition-all hover:-translate-y-1">HYPE</button>
                <button onclick="highlightCard('link')" class="px-4 py-1.5 bg-[#2A5ADA] text-white rounded-lg text-sm font-bold shadow-sm transition-all hover:-translate-y-1">LINK</button>
                <button onclick="highlightCard('fiat')" class="px-4 py-1.5 bg-slate-600 text-white rounded-lg text-sm font-bold shadow-sm transition-all hover:-translate-y-1 uppercase">Fiat</button>
                <button onclick="highlightCard('dca')" class="px-4 py-1.5 bg-[#8B5CF6] text-white rounded-lg text-sm font-bold shadow-sm transition-all hover:-translate-y-1">DCA</button>
            </div>
        </div>

        <div id="calculator-containers" class="space-y-6 pb-20">
            <!-- BTC Card -->
            <div id="card-btc" class="crypto-card rounded-2xl p-6 md:p-8 transition-all duration-300 relative" style="background-color: #F7931A;">
                <div class="flex flex-wrap md:flex-nowrap justify-between items-center mb-6 gap-4">
                    <h2 class="text-xl font-bold text-white flex items-center gap-2 md:w-1/4"><i class="fa-brands fa-bitcoin text-orange-200"></i> BTC</h2>
                    <div class="flex-1 flex justify-center items-center gap-3">
                        <div id="btc-live-container" class="bg-black/10 border border-black/5 rounded-xl px-4 py-1.5 flex flex-col items-center justify-center transition-all duration-300 backdrop-blur-sm">
                            <span class="text-[9px] text-white/70 uppercase tracking-widest font-extrabold mb-0.5 text-center">Live Price</span>
                            <div class="flex items-baseline gap-1"><span class="text-white/80 text-sm font-bold">$</span><span id="live-btc-price" class="text-white font-bold text-lg tracking-wide">...</span></div>
                        </div>
                        <button onclick="refreshSingleLivePrice('btc')" class="text-white/70 hover:text-white p-2 transition-all hover:rotate-180"><i class="fa-solid fa-arrows-rotate"></i></button>
                    </div>
                    <div class="md:w-1/4 flex justify-end"><button onclick="resetCard('btc')" class="text-xs font-bold bg-white/30 hover:bg-white/50 text-orange-950 px-4 py-2 rounded-lg transition-colors">Reset</button></div>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-6">
                    <div><label class="block text-xs font-extrabold text-orange-950 mb-2 uppercase">Entry Price</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="btc-initial" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-16 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><button onclick="useLivePrice('btc')" class="absolute right-2 top-1/2 -translate-y-1/2 text-[10px] font-bold uppercase bg-orange-500/20 text-orange-900 hover:bg-orange-500/40 px-2 py-1 rounded transition-colors">LIVE</button></div></div>
                    <div><label class="block text-xs font-extrabold text-orange-950 mb-2 uppercase">Target Price</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="btc-target" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-20 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><div class="absolute right-2 top-1/2 -translate-y-1/2"><select onchange="if(this.value) { setInputVal('btc-target', this.value); this.value=''; }" class="text-[10px] font-bold uppercase bg-orange-500/20 text-orange-900 px-2 py-1 rounded outline-none border-none cursor-pointer"><option value="" disabled selected>TGT</option><option value="70000">70k</option><option value="80000">80k</option><option value="90000">90k</option><option value="100000">100k</option><option value="120000">120k</option><option value="150000">150k</option></select></div></div></div>
                    <div><label class="block text-xs font-extrabold text-orange-950 mb-2 uppercase">Invest</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="btc-investment" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-20 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><div class="absolute right-2 top-1/2 -translate-y-1/2"><select onchange="if(this.value) { setInvestment('btc', this.value); this.value=''; }" class="text-[10px] font-bold uppercase bg-orange-500/20 text-orange-900 px-2 py-1 rounded outline-none border-none cursor-pointer"><option value="" disabled selected>AMT</option><option value="500">500</option><option value="1000">1k</option><option value="5000">5k</option></select></div></div></div>
                </div>
                <div class="results-box rounded-xl p-5 flex flex-col md:flex-row items-start md:items-center gap-6 md:gap-12 border border-orange-200/50">
                    <div class="flex items-center gap-3 w-full md:w-1/2"><span class="text-sm font-bold text-orange-900 uppercase">% Increase:</span><span id="btc-increase" class="font-bold text-gray-900 text-lg">--</span></div>
                    <div class="hidden md:block w-px h-6 bg-orange-300"></div>
                    <div class="flex items-center gap-3 w-full md:w-1/2"><span class="text-sm font-bold text-orange-900 uppercase">$ Profit:</span><span id="btc-profit" class="font-bold text-gray-900 text-lg">--</span></div>
                </div>
            </div>

            <!-- ETH Card -->
            <div id="card-eth" class="crypto-card rounded-2xl p-6 md:p-8 transition-all duration-300 relative" style="background-color: #93c5fd;">
                <div class="flex flex-wrap md:flex-nowrap justify-between items-center mb-6 gap-4">
                    <h2 class="text-xl font-bold text-blue-900 flex items-center gap-2 md:w-1/4"><i class="fa-brands fa-ethereum text-blue-700"></i> ETH</h2>
                    <div class="flex-1 flex justify-center items-center gap-3">
                        <div id="eth-live-container" class="bg-black/5 border border-black/5 rounded-xl px-4 py-1.5 flex flex-col items-center justify-center transition-all duration-300 backdrop-blur-sm shadow-sm">
                            <span class="text-[9px] text-blue-900/70 uppercase tracking-widest font-extrabold mb-0.5 text-center">Live Price</span>
                            <div class="flex items-baseline gap-1"><span class="text-blue-800 text-sm font-bold">$</span><span id="live-eth-price" class="text-blue-950 font-bold text-lg tracking-wide">...</span></div>
                        </div>
                        <button onclick="refreshSingleLivePrice('eth')" class="text-blue-800 hover:text-blue-950 p-2 transition-all hover:rotate-180"><i class="fa-solid fa-arrows-rotate"></i></button>
                    </div>
                    <div class="md:w-1/4 flex justify-end"><button onclick="resetCard('eth')" class="text-xs font-bold bg-white/40 hover:bg-white/60 text-blue-950 px-4 py-2 rounded-lg transition-colors">Reset</button></div>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-6">
                    <div><label class="block text-xs font-extrabold text-blue-900 mb-2 uppercase">Entry Price</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="eth-initial" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-16 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><button onclick="useLivePrice('eth')" class="absolute right-2 top-1/2 -translate-y-1/2 text-[10px] font-bold uppercase bg-blue-500/20 text-blue-900 hover:bg-blue-500/40 px-2 py-1 rounded transition-colors">LIVE</button></div></div>
                    <div><label class="block text-xs font-extrabold text-blue-900 mb-2 uppercase">Target Price</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="eth-target" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-20 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><div class="absolute right-2 top-1/2 -translate-y-1/2"><select onchange="if(this.value) { setInputVal('eth-target', this.value); this.value=''; }" class="text-[10px] font-bold uppercase bg-blue-500/20 text-blue-900 px-2 py-1 rounded outline-none border-none cursor-pointer"><option value="" disabled selected>TGT</option><option value="2500">2.5k</option><option value="3500">3.5k</option><option value="5500">5.5k</option></select></div></div></div>
                    <div><label class="block text-xs font-extrabold text-blue-900 mb-2 uppercase">Invest</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="eth-investment" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-20 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><div class="absolute right-2 top-1/2 -translate-y-1/2"><select onchange="if(this.value) { setInvestment('eth', this.value); this.value=''; }" class="text-[10px] font-bold uppercase bg-blue-500/20 text-blue-900 px-2 py-1 rounded outline-none border-none cursor-pointer"><option value="" disabled selected>AMT</option><option value="500">500</option><option value="1000">1k</option><option value="5000">5k</option></select></div></div></div>
                </div>
                <div class="results-box rounded-xl p-5 flex flex-col md:flex-row items-start md:items-center gap-6 md:gap-12 border border-blue-200/50">
                    <div class="flex items-center gap-3 w-full md:w-1/2"><span class="text-sm font-bold text-blue-900 uppercase">% Increase:</span><span id="eth-increase" class="font-bold text-gray-900 text-lg">--</span></div>
                    <div class="hidden md:block w-px h-6 bg-blue-300"></div>
                    <div class="flex items-center gap-3 w-full md:w-1/2"><span class="text-sm font-bold text-blue-900 uppercase">$ Profit:</span><span id="eth-profit" class="font-bold text-gray-900 text-lg">--</span></div>
                </div>
            </div>

            <!-- SOL Card -->
            <div id="card-sol" class="crypto-card rounded-2xl p-6 md:p-8 transition-all duration-300 relative" style="background-color: #4ade80;">
                <div class="flex flex-wrap md:flex-nowrap justify-between items-center mb-6 gap-4">
                    <h2 class="text-xl font-bold text-emerald-950 flex items-center gap-2 md:w-1/4">
                        <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-emerald-700 fill-current" viewBox="0 0 394 308"><path d="M68.5 119C71.4 116.1 75.3 114.5 79.3 114.5H388.6C395.3 114.5 398.7 122.7 393.9 127.5L329.1 192.3C326.3 195.2 322.4 196.8 318.3 196.8H9.1C2.3 196.8 -1.1 188.6 3.7 183.8L68.5 119Z"/><path d="M68.5 3.7C71.4 0.9 75.3 -0.8 79.3 -0.8H388.6C395.3 -0.8 398.7 7.4 393.9 12.2L329.1 77C326.3 79.9 322.4 81.5 318.3 81.5H9.1C2.3 81.5 -1.1 73.3 3.7 68.5L68.5 3.7Z"/><path d="M329.1 229.8C326.3 226.9 322.4 225.3 318.3 225.3H9.1C2.3 225.3 -1.1 233.5 3.7 238.3L68.5 303.1C71.4 306 75.3 307.6 79.3 307.6H388.6C395.3 307.6 398.7 299.4 393.9 294.6L329.1 229.8Z"/></svg> SOL
                    </h2>
                    <div class="flex-1 flex justify-center items-center gap-3">
                        <div id="sol-live-container" class="bg-black/5 border border-black/5 rounded-xl px-4 py-1.5 flex flex-col items-center justify-center transition-all duration-300 backdrop-blur-sm shadow-sm">
                            <span class="text-[9px] text-emerald-900/70 uppercase tracking-widest font-extrabold mb-0.5 text-center">Live Price</span>
                            <div class="flex items-baseline gap-1"><span class="text-emerald-800 text-sm font-bold">$</span><span id="live-sol-price" class="text-emerald-950 font-bold text-lg tracking-wide">...</span></div>
                        </div>
                        <button onclick="refreshSingleLivePrice('sol')" class="text-emerald-800 hover:text-emerald-950 p-2 transition-all hover:rotate-180"><i class="fa-solid fa-arrows-rotate"></i></button>
                    </div>
                    <div class="md:w-1/4 flex justify-end"><button onclick="resetCard('sol')" class="text-xs font-bold bg-emerald-600/20 hover:bg-emerald-600/30 text-emerald-950 px-4 py-2 rounded-lg transition-colors">Reset</button></div>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-6">
                    <div><label class="block text-xs font-extrabold text-emerald-900 mb-2 uppercase">Entry Price</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="sol-initial" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-16 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><button onclick="useLivePrice('sol')" class="absolute right-2 top-1/2 -translate-y-1/2 text-[10px] font-bold uppercase bg-emerald-600/20 text-emerald-900 hover:bg-emerald-600/40 px-2 py-1 rounded transition-colors">LIVE</button></div></div>
                    <div><label class="block text-xs font-extrabold text-emerald-900 mb-2 uppercase">Target Price</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="sol-target" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-20 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><div class="absolute right-2 top-1/2 -translate-y-1/2"><select onchange="if(this.value) { setInputVal('sol-target', this.value); this.value=''; }" class="text-[10px] font-bold uppercase bg-emerald-600/20 text-emerald-950 px-2 py-1 rounded outline-none border-none cursor-pointer"><option value="" disabled selected>TGT</option><option value="90">90</option><option value="150">150</option><option value="250">250</option><option value="400">400</option></select></div></div></div>
                    <div><label class="block text-xs font-extrabold text-emerald-900 mb-2 uppercase">Invest</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="sol-investment" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-20 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><div class="absolute right-2 top-1/2 -translate-y-1/2"><select onchange="if(this.value) { setInvestment('sol', this.value); this.value=''; }" class="text-[10px] font-bold uppercase bg-emerald-600/20 text-emerald-950 px-2 py-1 rounded outline-none border-none cursor-pointer"><option value="" disabled selected>AMT</option><option value="500">500</option><option value="1000">1k</option><option value="5000">5k</option></select></div></div></div>
                </div>
                <div class="results-box rounded-xl p-5 flex flex-col md:flex-row items-start md:items-center gap-6 md:gap-12 border border-emerald-200/50">
                    <div class="flex items-center gap-3 w-full md:w-1/2"><span class="text-sm font-bold text-emerald-800 uppercase">% Increase:</span><span id="sol-increase" class="font-bold text-gray-900 text-lg">--</span></div>
                    <div class="hidden md:block w-px h-6 bg-emerald-300"></div>
                    <div class="flex items-center gap-3 w-full md:w-1/2"><span class="text-sm font-bold text-emerald-800 uppercase">$ Profit:</span><span id="sol-profit" class="font-bold text-gray-900 text-lg">--</span></div>
                </div>
            </div>

            <!-- HYPE Card -->
            <div id="card-hype" class="crypto-card rounded-2xl p-6 md:p-8 transition-all duration-300 relative" style="background-color: #97FCE4;">
                <div class="flex flex-wrap md:flex-nowrap justify-between items-center mb-6 gap-4">
                    <h2 class="text-xl font-bold text-teal-900 flex items-center gap-2 md:w-1/4">
                        <img src="https://s2.coinmarketcap.com/static/img/coins/64x64/32196.png" alt="HYPE Logo" class="w-6 h-6 rounded-full shadow-sm"> HYPE
                    </h2>
                    <div class="flex-1 flex justify-center items-center gap-3">
                        <div id="hype-live-container" class="bg-black/5 border border-black/5 rounded-xl px-4 py-1.5 flex flex-col items-center justify-center transition-all duration-300 backdrop-blur-sm shadow-sm">
                            <span class="text-[9px] text-teal-900/70 uppercase tracking-widest font-extrabold mb-0.5 text-center">Live Price</span>
                            <div class="flex items-baseline gap-1"><span class="text-teal-800 text-sm font-bold">$</span><span id="live-hype-price" class="text-teal-950 font-bold text-lg tracking-wide">...</span></div>
                        </div>
                        <button onclick="refreshSingleLivePrice('hype')" class="text-teal-800 hover:text-teal-950 p-2 transition-all hover:rotate-180"><i class="fa-solid fa-arrows-rotate"></i></button>
                    </div>
                    <div class="md:w-1/4 flex justify-end"><button onclick="resetCard('hype')" class="text-xs font-bold bg-teal-600/10 hover:bg-teal-600/20 text-teal-950 px-4 py-2 rounded-lg transition-colors">Reset</button></div>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-6">
                    <div><label class="block text-xs font-extrabold text-teal-900 mb-2 uppercase">Entry Price</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="hype-initial" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-16 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><button onclick="useLivePrice('hype')" class="absolute right-2 top-1/2 -translate-y-1/2 text-[10px] font-bold uppercase bg-teal-600/10 text-teal-900 hover:bg-teal-600/30 px-2 py-1 rounded transition-colors">LIVE</button></div></div>
                    <div><label class="block text-xs font-extrabold text-teal-900 mb-2 uppercase">Target Price</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="hype-target" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-20 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><div class="absolute right-2 top-1/2 -translate-y-1/2"><select onchange="if(this.value) { setInputVal('hype-target', this.value); this.value=''; }" class="text-[10px] font-bold uppercase bg-teal-600/10 text-teal-950 px-2 py-1 rounded outline-none border-none cursor-pointer"><option value="" disabled selected>TGT</option><option value="40">40</option><option value="60">60</option></select></div></div></div>
                    <div><label class="block text-xs font-extrabold text-teal-900 mb-2 uppercase">Invest</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="hype-investment" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-20 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><div class="absolute right-2 top-1/2 -translate-y-1/2"><select onchange="if(this.value) { setInvestment('hype', this.value); this.value=''; }" class="text-[10px] font-bold uppercase bg-teal-600/10 text-teal-950 px-2 py-1 rounded outline-none border-none cursor-pointer"><option value="" disabled selected>AMT</option><option value="500">500</option><option value="1000">1k</option><option value="5000">5k</option></select></div></div></div>
                </div>
                <div class="results-box rounded-xl p-5 flex flex-col md:flex-row items-start md:items-center gap-6 md:gap-12 border border-teal-200/50">
                    <div class="flex items-center gap-3 w-full md:w-1/2"><span class="text-sm font-bold text-teal-900 uppercase">% Increase:</span><span id="hype-increase" class="font-bold text-gray-900 text-lg">--</span></div>
                    <div class="hidden md:block w-px h-6 bg-teal-300"></div>
                    <div class="flex items-center gap-3 w-full md:w-1/2"><span class="text-sm font-bold text-teal-900 uppercase">$ Profit:</span><span id="hype-profit" class="font-bold text-gray-900 text-lg">--</span></div>
                </div>
            </div>

            <!-- LINK Card -->
            <div id="card-link" class="crypto-card rounded-2xl p-6 md:p-8 transition-all duration-300 relative" style="background-color: #2A5ADA;">
                <div class="flex flex-wrap md:flex-nowrap justify-between items-center mb-6 gap-4">
                    <h2 class="text-xl font-bold text-white flex items-center gap-2 md:w-1/4"><i class="fa-solid fa-link text-blue-200"></i> LINK</h2>
                    <div class="flex-1 flex justify-center items-center gap-3">
                        <div id="link-live-container" class="bg-black/10 border border-black/5 rounded-xl px-4 py-1.5 flex flex-col items-center justify-center transition-all duration-300 backdrop-blur-sm shadow-sm">
                            <span class="text-[9px] text-white/70 uppercase tracking-widest font-extrabold mb-0.5 text-center">Live Price</span>
                            <div class="flex items-baseline gap-1"><span class="text-white/80 text-sm font-bold">$</span><span id="live-link-price" class="text-white font-bold text-lg tracking-wide">...</span></div>
                        </div>
                        <button onclick="refreshSingleLivePrice('link')" class="text-white/70 hover:text-white p-2 transition-all hover:rotate-180"><i class="fa-solid fa-arrows-rotate"></i></button>
                    </div>
                    <div class="md:w-1/4 flex justify-end"><button onclick="resetCard('link')" class="text-xs font-bold bg-white/20 hover:bg-white/30 text-white px-4 py-2 rounded-lg transition-colors">Reset</button></div>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-6">
                    <div><label class="block text-xs font-extrabold text-white mb-2 uppercase">Entry Price</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="link-initial" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-16 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><button onclick="useLivePrice('link')" class="absolute right-2 top-1/2 -translate-y-1/2 text-[10px] font-bold uppercase bg-white/20 text-blue-900 hover:bg-white/40 px-2 py-1 rounded transition-colors">LIVE</button></div></div>
                    <div><label class="block text-xs font-extrabold text-white mb-2 uppercase">Target Price</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="link-target" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-20 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><div class="absolute right-2 top-1/2 -translate-y-1/2"><select onchange="if(this.value) { setInputVal('link-target', this.value); this.value=''; }" class="text-[10px] font-bold uppercase bg-white/20 text-white px-2 py-1 rounded outline-none border-none cursor-pointer"><option value="" disabled selected>TGT</option><option value="30">30</option><option value="50">50</option><option value="100">100</option></select></div></div></div>
                    <div><label class="block text-xs font-extrabold text-white mb-2 uppercase">Invest</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-500 font-medium">$</span><input type="text" inputmode="decimal" id="link-investment" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-20 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"><div class="absolute right-2 top-1/2 -translate-y-1/2"><select onchange="if(this.value) { setInvestment('link', this.value); this.value=''; }" class="text-[10px] font-bold uppercase bg-white/20 text-white px-2 py-1 rounded outline-none border-none cursor-pointer"><option value="" disabled selected>AMT</option><option value="500">500</option><option value="1000">1k</option><option value="5000">5k</option></select></div></div></div>
                </div>
                <div class="results-box rounded-xl p-5 flex flex-col md:flex-row items-start md:items-center gap-6 md:gap-12 border border-blue-400/50">
                    <div class="flex items-center gap-3 w-full md:w-1/2"><span class="text-sm font-bold text-white uppercase">% Increase:</span><span id="link-increase" class="font-bold text-gray-900 text-lg">--</span></div>
                    <div class="hidden md:block w-px h-6 bg-blue-400"></div>
                    <div class="flex items-center gap-3 w-full md:w-1/2"><span class="text-sm font-bold text-white uppercase">$ Profit:</span><span id="link-profit" class="font-bold text-gray-900 text-lg">--</span></div>
                </div>
            </div>

            <!-- USD/INR Card -->
            <div id="card-fiat" class="crypto-card rounded-2xl p-6 md:p-8 transition-all duration-300 relative" style="background-color: #475569;">
                <div class="flex flex-wrap md:flex-nowrap justify-between items-center mb-6 gap-4">
                    <h2 class="text-xl font-bold text-white flex items-center gap-2 md:w-1/4"><i class="fa-solid fa-money-bill-transfer text-slate-300"></i> USD / INR</h2>
                    <div class="flex-1 flex justify-center items-center gap-3">
                        <div id="fiat-live-container" class="bg-black/10 border border-black/5 rounded-xl px-4 py-1.5 flex flex-col items-center justify-center transition-all duration-300 backdrop-blur-sm shadow-sm">
                            <span class="text-[9px] text-slate-300 uppercase tracking-widest font-extrabold mb-0.5 text-center">Live Rate</span>
                            <div class="flex items-baseline gap-1"><span class="text-slate-300 text-sm font-bold">₹</span><span id="live-fiat-price" class="text-white font-bold text-lg tracking-wide">...</span></div>
                        </div>
                        <button onclick="fetchLiveFiatPrice()" class="text-slate-300 hover:text-white transition-all hover:rotate-180 p-2"><i class="fa-solid fa-arrows-rotate"></i></button>
                    </div>
                    <div class="md:w-1/4 flex justify-end"><button onclick="resetFiat()" class="text-xs font-bold bg-white/10 hover:bg-white/20 text-white px-4 py-2 rounded-lg transition-colors">Reset</button></div>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-2">
                    <div><label class="block text-xs font-extrabold text-slate-200 mb-2 uppercase">USD Amount</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-slate-500 font-medium">$</span><input type="text" inputmode="decimal" id="fiat-usd" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-4 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"></div></div>
                    <div><label class="block text-xs font-extrabold text-slate-200 mb-2 uppercase">INR Amount</label><div class="relative group"><span class="absolute left-4 top-1/2 -translate-y-1/2 text-slate-500 font-medium">₹</span><input type="text" inputmode="decimal" id="fiat-inr" onfocus="this.select()" class="input-field w-full rounded-xl py-3 pl-8 pr-4 text-gray-800 font-bold outline-none focus:ring-4 focus:ring-white/50" placeholder="0.00"></div></div>
                </div>
            </div>

            <!-- DCA Card -->
            <div id="card-dca" class="crypto-card rounded-2xl p-6 md:p-8 transition-all duration-300 relative" style="background-color: #8B5CF6;">
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-xl font-bold text-white flex items-center gap-2"><i class="fa-solid fa-layer-group text-purple-200"></i> DCA CALCULATOR</h2>
                    <button onclick="resetDCA()" class="text-xs font-bold bg-white/20 hover:bg-white/30 text-white px-4 py-2 rounded-lg transition-colors">Reset</button>
                </div>
                <div id="dca-entries" class="space-y-3 mb-6"></div>
                <button onclick="addDCAEntry()" class="w-full mb-8 px-6 py-3 bg-purple-700/50 hover:bg-purple-700/80 text-white text-sm font-bold rounded-xl border border-purple-400/30 border-dashed flex justify-center items-center transition-colors"><i class="fa-solid fa-plus mr-2"></i> ADD BUY</button>
                <div id="dca-chart-container" class="w-full h-72 mb-6 hidden bg-purple-900/20 p-4 rounded-xl relative"><canvas id="dcaChart"></canvas></div>
                <div class="results-box rounded-xl p-5 flex flex-col md:flex-row items-center justify-between gap-6 border border-purple-400/50">
                    <div class="text-center w-full md:w-1/3"><span class="block text-xs font-bold text-purple-900 mb-1 uppercase">Invested</span><span id="dca-total-invested" class="font-bold text-gray-900 text-xl">$0.00</span></div>
                    <div class="text-center w-full md:w-1/3"><span class="block text-xs font-bold text-purple-900 mb-1 uppercase">Avg Price</span><span id="dca-average-price" class="font-bold text-green-700 text-2xl">$0.00</span></div>
                    <div class="text-center w-full md:w-1/3"><span class="block text-xs font-bold text-purple-900 mb-1 uppercase">Total Coins</span><span id="dca-total-coins" class="font-bold text-gray-900 text-lg">0.00</span></div>
                </div>
            </div>
        </div>
    </div>

    <!-- WHAT IF App Wrapper -->
    <div id="what-if-app" class="hidden opacity-0 translate-y-4 max-w-2xl mx-auto space-y-6 relative z-10 transition-all duration-700 text-white text-center">
        <div class="flex justify-start mb-6">
            <button onclick="goBackToLanding()" class="group flex items-center gap-2 px-5 py-2.5 bg-white/5 hover:bg-white/10 text-gray-300 hover:text-white rounded-xl transition-all border border-white/10 backdrop-blur-md focus:outline-none">
                <i class="fa-solid fa-chevron-left text-xs group-hover:-translate-x-1 transition-transform"></i>
                <span class="text-xs font-black uppercase tracking-widest">Back to Menu</span>
            </button>
        </div>

        <div class="glass-card p-6 md:p-8 rounded-[2.5rem] shadow-2xl mx-auto max-w-sm relative overflow-hidden">
            <h2 class="text-3xl font-extrabold mb-1 font-philosopher text-amber-400 uppercase">Time Machine</h2>
            <p class="text-gray-400 mb-6 text-[10px] font-medium uppercase tracking-widest">Investment Simulation</p>
            
            <div class="space-y-4 mb-8">
                <div class="flex gap-2 justify-center">
                    <select id="wi-day" class="bg-white/10 border border-white/10 rounded-lg py-2 px-1 text-white font-bold outline-none text-xs text-center w-14 hover:bg-white/20 transition-colors cursor-pointer"></select>
                    <select id="wi-month" class="bg-white/10 border border-white/10 rounded-lg py-2 px-1 text-white font-bold outline-none text-xs text-center w-20 hover:bg-white/20 transition-colors cursor-pointer">
                        <option value="01">Jan</option><option value="02">Feb</option><option value="03">Mar</option>
                        <option value="04">Apr</option><option value="05">May</option><option value="06">Jun</option>
                        <option value="07">Jul</option><option value="08">Aug</option><option value="09">Sep</option>
                        <option value="10">Oct</option><option value="11">Nov</option><option value="12">Dec</option>
                    </select>
                    <select id="wi-year" class="bg-white/10 border border-white/10 rounded-lg py-2 px-1 text-white font-bold outline-none text-xs text-center w-16 hover:bg-white/20 transition-colors cursor-pointer"></select>
                </div>
                
                <div class="text-[10px] font-black uppercase tracking-widest text-gray-500">
                    HISTORICAL PRICE: <span id="wi-hist-price" class="text-white">...</span>
                </div>

                <div class="relative group mt-4">
                    <span class="absolute left-4 top-1/2 -translate-y-1/2 text-lg text-amber-400 font-bold">$</span>
                    <input type="text" id="wi-amount" inputmode="decimal" class="w-full bg-white/10 border border-white/10 rounded-xl py-3 pl-10 pr-4 text-xl text-white font-black outline-none focus:ring-2 focus:ring-amber-500/30 transition-all text-center" placeholder="Amount">
                </div>
            </div>

            <div class="grid grid-cols-2 gap-3 text-left">
                <div class="bg-black/40 p-3 rounded-xl border border-white/5">
                    <span class="block text-[7px] font-black text-gray-500 mb-1 uppercase">BTC Owned</span>
                    <span id="res-btc-owned" class="text-xs font-black text-white">0.000000</span>
                </div>
                <div class="bg-black/40 p-3 rounded-xl border border-white/5">
                    <span class="block text-[7px] font-black text-gray-500 mb-1 uppercase">Value Now</span>
                    <span id="res-val-today" class="text-xs font-black text-amber-400">$0.00</span>
                </div>
                <div class="bg-black/40 p-3 rounded-xl border border-white/5">
                    <span class="block text-[7px] font-black text-gray-500 mb-1 uppercase">Net P/L</span>
                    <span id="res-pnl" class="text-xs font-black text-green-400">$0.00</span>
                </div>
                <div class="bg-black/40 p-3 rounded-xl border border-white/5">
                    <span class="block text-[7px] font-black text-gray-500 mb-1 uppercase">Gain</span>
                    <span id="res-perc" class="text-xs font-black text-green-400">0%</span>
                </div>
            </div>
        </div>
    </div>

    <!-- GYM SCHEDULE App Wrapper -->
    <div id="gym-schedule-app" class="hidden opacity-0 translate-y-4 w-full max-w-6xl mx-auto space-y-6 relative z-10 transition-all duration-700 font-inter">
        <div class="flex justify-start mb-2">
            <button onclick="goBackToLanding()" class="group flex items-center gap-2 px-4 py-2 bg-[#18181B] hover:bg-[#27272A] text-[#A1A1AA] hover:text-white rounded-lg transition-all focus:outline-none border border-[#27272A]">
                <i class="fa-solid fa-chevron-left text-xs group-hover:-translate-x-1 transition-transform"></i>
                <span class="text-xs font-semibold tracking-wide">Back to Menu</span>
            </button>
        </div>

        <div class="bg-[#18181B] border border-[#27272A] rounded-2xl p-6 md:p-10 shadow-2xl mx-auto w-full relative overflow-hidden text-left border-t-emerald-500/30">
            <h2 class="text-4xl md:text-5xl font-extrabold mb-2 font-philosopher text-transparent bg-clip-text bg-gradient-to-r from-emerald-400 to-teal-400 drop-shadow-sm uppercase text-center">Weekly Routine</h2>
            <p class="text-gray-400 mb-10 text-[10px] font-medium uppercase tracking-widest text-center">Full Week Training Schedule</p>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Monday -->
                <div class="gym-card bg-[#09090B] p-5 rounded-xl border border-[#27272A] transition-all duration-300 flex flex-col" data-day="Monday">
                    <div class="mb-4 cursor-pointer group-hover:opacity-80 transition-opacity" onclick="selectDayOfWeek('Monday')">
                        <span class="text-[10px] font-bold text-[#A1A1AA] uppercase tracking-widest">Monday</span>
                        <h3 class="text-lg font-semibold text-white mt-1">Legs & Stomach</h3>
                    </div>
                    <ul class="text-[#D4D4D8] text-xs space-y-3 font-medium flex-1">
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 0)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Barbell Squats</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 1)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Leg Press</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 2)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Leg Ext/Curls</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH/PULL</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 3)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Cable Crunches</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">CORE</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 4)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Hanging Leg Raises</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">CORE</span>
                        </li>
                    </ul>
                </div>

                <!-- Tuesday -->
                <div class="gym-card bg-[#09090B] p-5 rounded-xl border border-[#27272A] transition-all duration-300 flex flex-col" data-day="Tuesday">
                    <div class="mb-4 cursor-pointer group-hover:opacity-80 transition-opacity" onclick="selectDayOfWeek('Tuesday')">
                        <span class="text-[10px] font-bold text-[#A1A1AA] uppercase tracking-widest">Tuesday</span>
                        <h3 class="text-lg font-semibold text-white mt-1">Shoulders</h3>
                    </div>
                    <ul class="text-[#D4D4D8] text-xs space-y-3 font-medium flex-1">
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 0)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Military Press</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 1)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Lateral Raises</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 2)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Front Raises</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 3)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Reverse Pec Deck</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 4)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Dumbbell Shrugs</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                    </ul>
                </div>

                <!-- Wednesday -->
                <div class="gym-card bg-[#09090B] p-5 rounded-xl border border-[#27272A] transition-all duration-300 flex flex-col" data-day="Wednesday">
                    <div class="mb-4 cursor-pointer group-hover:opacity-80 transition-opacity" onclick="selectDayOfWeek('Wednesday')">
                        <span class="text-[10px] font-bold text-[#A1A1AA] uppercase tracking-widest">Wednesday</span>
                        <h3 class="text-lg font-semibold text-white mt-1">Chest</h3>
                    </div>
                    <ul class="text-[#D4D4D8] text-xs space-y-3 font-medium flex-1">
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 0)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Flat Bench Press</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 1)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Incline DB Press</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 2)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Cable Crossovers</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 3)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Chest Dips</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 4)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Machine Flyes</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PUSH</span>
                        </li>
                    </ul>
                </div>

                <!-- Thursday -->
                <div class="gym-card bg-[#09090B] p-5 rounded-xl border border-[#27272A] transition-all duration-300 flex flex-col" data-day="Thursday">
                    <div class="mb-4 cursor-pointer group-hover:opacity-80 transition-opacity" onclick="selectDayOfWeek('Thursday')">
                        <span class="text-[10px] font-bold text-[#A1A1AA] uppercase tracking-widest">Thursday</span>
                        <h3 class="text-lg font-semibold text-white mt-1">Holiday</h3>
                    </div>
                    <ul class="text-[#D4D4D8] text-xs space-y-3 font-medium flex-1">
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 0)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Active Recovery</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">REST</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 1)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Light Stretching</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">REST</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 2)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Hydration</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">REST</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 3)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Muscle Recovery</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">REST</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 4)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Adequate Sleep</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">REST</span>
                        </li>
                    </ul>
                </div>

                <!-- Friday -->
                <div class="gym-card bg-[#09090B] p-5 rounded-xl border border-[#27272A] transition-all duration-300 flex flex-col" data-day="Friday">
                    <div class="mb-4 cursor-pointer group-hover:opacity-80 transition-opacity" onclick="selectDayOfWeek('Friday')">
                        <span class="text-[10px] font-bold text-[#A1A1AA] uppercase tracking-widest">Friday</span>
                        <h3 class="text-lg font-semibold text-white mt-1">Holiday</h3>
                    </div>
                    <ul class="text-[#D4D4D8] text-xs space-y-3 font-medium flex-1">
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 0)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Active Recovery</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">REST</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 1)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Light Stretching</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">REST</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 2)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Hydration</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">REST</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 3)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Muscle Recovery</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">REST</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 4)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Adequate Sleep</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">REST</span>
                        </li>
                    </ul>
                </div>

                <!-- Saturday -->
                <div class="gym-card bg-[#09090B] p-5 rounded-xl border border-[#27272A] transition-all duration-300 flex flex-col" data-day="Saturday">
                    <div class="mb-4 cursor-pointer group-hover:opacity-80 transition-opacity" onclick="selectDayOfWeek('Saturday')">
                        <span class="text-[10px] font-bold text-[#A1A1AA] uppercase tracking-widest">Saturday</span>
                        <h3 class="text-lg font-semibold text-white mt-1">Biceps</h3>
                    </div>
                    <ul class="text-[#D4D4D8] text-xs space-y-3 font-medium flex-1">
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 0)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Barbell Curls</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 1)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Hammer Curls</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 2)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Preacher Curls</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 3)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Incline DB Curls</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 4)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Concentration Curls</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                    </ul>
                </div>

                <!-- Sunday -->
                <div class="gym-card bg-[#09090B] p-5 rounded-xl border border-[#27272A] transition-all duration-300 flex flex-col md:col-span-2 lg:col-span-2" data-day="Sunday">
                    <div class="mb-4 cursor-pointer group-hover:opacity-80 transition-opacity" onclick="selectDayOfWeek('Sunday')">
                        <span class="text-[10px] font-bold text-[#A1A1AA] uppercase tracking-widest">Sunday</span>
                        <h3 class="text-lg font-semibold text-white mt-1">Back</h3>
                    </div>
                    <ul class="text-[#D4D4D8] text-xs space-y-3 font-medium flex-1 grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-3 content-start">
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 0)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Deadlifts</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 1)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Lat Pulldowns</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 2)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Barbell Rows</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 3)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Seated Cable Rows</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                        <li class="flex justify-between items-center group transition-colors py-0.5" onclick="toggleExercise(this, 4)">
                            <div class="flex items-center gap-3">
                                <div class="w-4 h-4 rounded border border-[#3F3F46] flex items-center justify-center exercise-checkbox transition-colors flex-shrink-0"><i class="fa-solid fa-check text-[10px] text-transparent transition-colors"></i></div>
                                <span class="truncate exercise-name transition-all text-[#D4D4D8] select-none text-xs">Pull-ups</span>
                            </div>
                            <span class="text-[8px] font-bold bg-[#27272A] text-[#A1A1AA] px-1.5 py-0.5 rounded tracking-wider flex-shrink-0 ml-2">PULL</span>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- 365 Tracker -->
            <div class="bg-[#09090B] p-6 rounded-xl border border-[#27272A]">
                <div class="flex flex-wrap justify-between items-end mb-6 gap-4">
                    <div>
                        <h3 class="text-base font-semibold text-white">Annual Consistency</h3>
                        <p class="text-xs text-[#A1A1AA] mt-1">365-Day Activity Log</p>
                    </div>
                    <div class="flex gap-6 text-sm">
                        <div class="flex flex-col text-right">
                            <span class="text-[#A1A1AA] text-[10px] uppercase tracking-wider font-bold mb-1">Completed</span>
                            <span id="tracker-completed" class="text-xl font-bold text-emerald-500 leading-none">0</span>
                        </div>
                        <div class="flex flex-col text-right">
                            <span class="text-[#A1A1AA] text-[10px] uppercase tracking-wider font-bold mb-1">Missed</span>
                            <span id="tracker-missed" class="text-xl font-bold text-red-500 leading-none">0</span>
                        </div>
                    </div>
                </div>
                <div id="consistency-grid" class="flex flex-wrap gap-1 h-32 md:h-auto overflow-y-auto md:overflow-visible content-start rounded"></div>
            </div>

        </div>
    </div>

    <!-- PERP App Wrapper -->
    <div id="perp-app" class="hidden opacity-0 translate-y-4 w-full max-w-4xl mx-auto space-y-6 relative z-10 transition-all duration-700 font-inter">
        <div class="flex justify-start mb-2">
            <button onclick="goBackToLanding()" class="group flex items-center gap-2 px-4 py-2 bg-[#18181B] hover:bg-[#27272A] text-[#A1A1AA] hover:text-white rounded-lg transition-all focus:outline-none border border-[#27272A]">
                <i class="fa-solid fa-chevron-left text-xs group-hover:-translate-x-1 transition-transform"></i>
                <span class="text-xs font-semibold tracking-wide">Back to Menu</span>
            </button>
        </div>

        <div class="bg-[#09090B] border border-white/5 rounded-3xl p-6 md:p-10 shadow-2xl relative overflow-hidden backdrop-blur-xl">
            <!-- Glow background -->
            <div class="absolute -top-40 -right-40 w-96 h-96 bg-indigo-500/10 rounded-full blur-[100px] pointer-events-none"></div>
            
            <div class="flex items-center justify-between mb-8 relative z-10">
                <div class="flex items-center gap-3">
                    <div class="w-2.5 h-2.5 rounded-full bg-indigo-500 shadow-[0_0_12px_rgba(99,102,241,0.8)] animate-pulse"></div>
                    <h2 class="text-sm font-bold font-mono-custom tracking-[0.15em] uppercase text-white">Perp Calc</h2>
                </div>
                <div class="px-3 py-1.5 bg-[#181a21] border border-white/10 rounded-md text-[10px] font-mono-custom text-gray-400 tracking-widest uppercase">
                    BTC-USDC PERP
                </div>
            </div>

            <!-- Direction Toggle -->
            <div class="grid grid-cols-2 bg-[#111318] border border-[#1f2130] rounded-xl overflow-hidden mb-8 p-1 gap-1 relative z-10">
                <button id="perp-btn-long" onclick="perpSetDir('long')" class="perp-dir-btn active bg-emerald-500/15 text-emerald-400 border border-emerald-500/30 py-3 text-xs font-bold font-mono-custom uppercase tracking-wider rounded-lg transition-all shadow-[0_0_15px_rgba(16,185,129,0.1)]">▲ Long</button>
                <button id="perp-btn-short" onclick="perpSetDir('short')" class="perp-dir-btn bg-transparent text-gray-500 border border-transparent hover:bg-white/5 py-3 text-xs font-bold font-mono-custom uppercase tracking-wider rounded-lg transition-all">▼ Short</button>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 relative z-10">
                <!-- Left Column: Inputs -->
                <div class="space-y-6">
                    <div class="bg-[#111318] border border-[#1f2130] rounded-2xl p-6">
                        <h3 class="text-[10px] font-bold font-mono-custom text-gray-500 tracking-widest uppercase mb-5">Position Setup</h3>
                        
                        <div class="space-y-4">
                            <div class="flex flex-col gap-1.5">
                                <label class="text-[10px] text-gray-400 font-medium tracking-wide">Entry Price</label>
                                <div class="relative">
                                    <input type="number" id="perp-entry" placeholder="65000" oninput="perpCalc()" class="w-full bg-[#181a21] border border-[#282b3a] rounded-xl py-3 pl-4 pr-8 text-sm font-bold font-mono-custom text-white placeholder-gray-600 focus:border-indigo-500 focus:ring-1 focus:ring-indigo-500 transition-all outline-none">
                                    <span class="absolute right-4 top-1/2 -translate-y-1/2 text-xs text-gray-500 font-mono-custom">$</span>
                                </div>
                            </div>
                            
                            <div class="flex flex-col gap-1.5">
                                <label class="text-[10px] text-gray-400 font-medium tracking-wide">Margin (Collateral)</label>
                                <div class="relative">
                                    <input type="number" id="perp-margin" placeholder="1000" oninput="perpCalc()" class="w-full bg-[#181a21] border border-[#282b3a] rounded-xl py-3 pl-4 pr-8 text-sm font-bold font-mono-custom text-white placeholder-gray-600 focus:border-indigo-500 focus:ring-1 focus:ring-indigo-500 transition-all outline-none">
                                    <span class="absolute right-4 top-1/2 -translate-y-1/2 text-xs text-gray-500 font-mono-custom">$</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="bg-[#111318] border border-[#1f2130] rounded-2xl p-6">
                        <h3 class="text-[10px] font-bold font-mono-custom text-gray-500 tracking-widest uppercase mb-5">Exit Conditions</h3>
                        
                        <div class="grid grid-cols-2 gap-4">
                            <div class="flex flex-col gap-1.5">
                                <label class="text-[10px] text-emerald-500/80 font-medium tracking-wide">Take Profit</label>
                                <div class="relative">
                                    <input type="number" id="perp-tp" placeholder="70000" oninput="perpCalc()" class="w-full bg-[#181a21] border border-[#282b3a] rounded-xl py-3 pl-3 pr-7 text-sm font-bold font-mono-custom text-emerald-400 placeholder-gray-600 focus:border-emerald-500/50 outline-none transition-all">
                                    <span class="absolute right-3 top-1/2 -translate-y-1/2 text-[10px] text-gray-500 font-mono-custom">$</span>
                                </div>
                            </div>
                            <div class="flex flex-col gap-1.5">
                                <label class="text-[10px] text-rose-500/80 font-medium tracking-wide">Stop Loss</label>
                                <div class="relative">
                                    <input type="number" id="perp-sl" placeholder="62000" oninput="perpCalc()" class="w-full bg-[#181a21] border border-[#282b3a] rounded-xl py-3 pl-3 pr-7 text-sm font-bold font-mono-custom text-rose-400 placeholder-gray-600 focus:border-rose-500/50 outline-none transition-all">
                                    <span class="absolute right-3 top-1/2 -translate-y-1/2 text-[10px] text-gray-500 font-mono-custom">$</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="bg-[#111318] border border-[#1f2130] rounded-2xl p-6">
                        <div class="flex justify-between items-end mb-5">
                            <div class="text-[10px] font-bold font-mono-custom text-gray-500 tracking-widest uppercase">Leverage</div>
                            <div class="text-2xl font-bold font-mono-custom text-indigo-400 leading-none"><span id="perp-lev-display">10</span><sup class="text-xs ml-0.5">x</sup></div>
                        </div>
                        
                        <div class="flex justify-between gap-2 mb-5">
                            <button class="perp-lev-btn px-3 py-1.5 text-[10px] font-bold font-mono-custom bg-[#181a21] border border-[#282b3a] rounded-lg text-gray-400 hover:border-indigo-500/50 hover:text-indigo-400 transition-all flex-1" onclick="perpSetLev(2)">2x</button>
                            <button class="perp-lev-btn px-3 py-1.5 text-[10px] font-bold font-mono-custom bg-[#181a21] border border-[#282b3a] rounded-lg text-gray-400 hover:border-indigo-500/50 hover:text-indigo-400 transition-all flex-1" onclick="perpSetLev(5)">5x</button>
                            <button class="perp-lev-btn active-lev px-3 py-1.5 text-[10px] font-bold font-mono-custom bg-indigo-500/10 border border-indigo-500 rounded-lg text-indigo-400 transition-all flex-1 shadow-[0_0_10px_rgba(99,102,241,0.2)]" onclick="perpSetLev(10)">10x</button>
                            <button class="perp-lev-btn px-3 py-1.5 text-[10px] font-bold font-mono-custom bg-[#181a21] border border-[#282b3a] rounded-lg text-gray-400 hover:border-indigo-500/50 hover:text-indigo-400 transition-all flex-1" onclick="perpSetLev(20)">20x</button>
                            <button class="perp-lev-btn px-3 py-1.5 text-[10px] font-bold font-mono-custom bg-[#181a21] border border-[#282b3a] rounded-lg text-gray-400 hover:border-indigo-500/50 hover:text-indigo-400 transition-all flex-1" onclick="perpSetLev(50)">50x</button>
                        </div>
                        
                        <input type="range" id="perp-slider" min="1" max="100" value="10" oninput="perpSliderLev(this.value)" class="w-full h-1.5 bg-[#282b3a] rounded-lg appearance-none cursor-pointer accent-indigo-500">
                    </div>
                </div>

                <!-- Right Column: Results -->
                <div class="space-y-4">
                    <div id="perp-empty-state" class="h-full border border-dashed border-white/10 rounded-2xl flex flex-col items-center justify-center p-10 text-center opacity-50 min-h-[300px]">
                        <i class="fa-solid fa-chart-line text-3xl text-gray-500 mb-4"></i>
                        <p class="text-xs font-mono-custom text-gray-400 tracking-widest uppercase">Enter entry & margin<br>to see projection</p>
                    </div>

                    <div id="perp-results-section" class="hidden space-y-4 h-full flex flex-col">
                        
                        <!-- Top KPI Cards -->
                        <div class="grid grid-cols-2 gap-4">
                            <div class="bg-emerald-500/5 border border-emerald-500/20 rounded-2xl p-5 flex flex-col items-center justify-center text-center relative overflow-hidden group">
                                <div class="absolute top-0 left-0 w-full h-[2px] bg-gradient-to-r from-transparent via-emerald-500 to-transparent opacity-50"></div>
                                <span class="text-[9px] font-bold font-mono-custom text-emerald-500/80 uppercase tracking-widest mb-2">Expected Profit</span>
                                <span id="res-perp-profit-usd" class="text-xl font-black font-mono-custom text-emerald-400 mb-1">—</span>
                                <span id="res-perp-profit-roe" class="text-[10px] font-mono-custom text-emerald-500/60">—</span>
                            </div>

                            <div class="bg-rose-500/5 border border-rose-500/20 rounded-2xl p-5 flex flex-col items-center justify-center text-center relative overflow-hidden">
                                <div class="absolute top-0 left-0 w-full h-[2px] bg-gradient-to-r from-transparent via-rose-500 to-transparent opacity-50"></div>
                                <span class="text-[9px] font-bold font-mono-custom text-rose-500/80 uppercase tracking-widest mb-2">Expected Loss</span>
                                <span id="res-perp-loss-usd" class="text-xl font-black font-mono-custom text-rose-400 mb-1">—</span>
                                <span id="res-perp-loss-roe" class="text-[10px] font-mono-custom text-rose-500/60">—</span>
                            </div>
                        </div>

                        <!-- Liquidation Alert Card -->
                        <div id="perp-liq-card" class="bg-orange-500/5 border border-orange-500/20 rounded-2xl p-5 flex items-center justify-between relative overflow-hidden transition-all">
                            <div class="absolute left-0 top-0 bottom-0 w-[3px] bg-orange-500 opacity-50"></div>
                            <div>
                                <span class="block text-[9px] font-bold font-mono-custom text-orange-500/80 uppercase tracking-widest mb-1">Liquidation Price</span>
                                <span id="res-perp-liq-dist" class="text-[10px] font-mono-custom text-orange-500/60">—</span>
                            </div>
                            <span id="res-perp-liq" class="text-2xl font-black font-mono-custom text-orange-400">—</span>
                        </div>

                        <!-- Data Breakdown -->
                        <div class="bg-[#111318] border border-[#1f2130] rounded-2xl p-5 flex-1">
                            <div class="space-y-3">
                                <div class="flex justify-between items-center text-xs font-mono-custom border-b border-white/5 pb-2">
                                    <span class="text-gray-500">Notional Size</span>
                                    <span id="res-perp-size" class="text-white font-bold">—</span>
                                </div>
                                <div class="flex justify-between items-center text-xs font-mono-custom border-b border-white/5 pb-2">
                                    <span class="text-gray-500">BTC Amount</span>
                                    <span id="res-perp-btc" class="text-white font-bold">—</span>
                                </div>
                                <div class="flex justify-between items-center text-xs font-mono-custom pt-1">
                                    <span class="text-gray-500">Risk/Reward</span>
                                    <span id="res-perp-rr" class="text-gray-300 font-bold px-2 py-1 rounded bg-white/5">—</span>
                                </div>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        const coins = ['btc', 'eth', 'sol', 'hype', 'link'];
        let livePrices = { btc: 0, eth: 0, sol: 0, hype: 39.36, link: 0 };
        let currentUsdInrRate = 0;
        
        let matrixInterval = null;
        let drops = []; 

        let historicalPriceBtc = 0;
        let histFetchTimeout = null;

        // Ensure gymState is declared exactly once globally
        let gymState = { log: {}, exercises: {} }; 
        
        // PERP State
        let perpState = { dir: 'long', lev: 10 };

        function getTodayString() {
            const d = new Date();
            return `${d.getFullYear()}-${String(d.getMonth() + 1).padStart(2, '0')}-${String(d.getDate()).padStart(2, '0')}`;
        }
        
        // --- GYM SCHEDULE FUNCTIONS ---
        function selectDayOfWeek(targetDayName) {
            const dayNames = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
            const targetDayIndex = dayNames.indexOf(targetDayName);
            if (targetDayIndex === -1) return;

            const datePicker = document.getElementById('gym-date-picker');
            let baseDate = new Date();
            if (datePicker && datePicker.value) {
                const parts = datePicker.value.split('-');
                baseDate = new Date(parts[0], parts[1]-1, parts[2]);
            }

            const currentDayIndex = baseDate.getDay();
            const distance = targetDayIndex - currentDayIndex;
            
            baseDate.setDate(baseDate.getDate() + distance);
            
            const dateStr = `${baseDate.getFullYear()}-${String(baseDate.getMonth() + 1).padStart(2, '0')}-${String(baseDate.getDate()).padStart(2, '0')}`;
            
            if (datePicker) {
                datePicker.value = dateStr;
                updateGymUI();
            }
        }
        
        function toggleExercise(liEl, index) {
            const card = liEl.closest('.gym-card');
            if (!card.classList.contains('border-zinc-400')) return; 
            
            const dateStr = document.getElementById('gym-date-picker').value;
            if (!gymState.exercises) gymState.exercises = {};
            if (!gymState.exercises[dateStr]) gymState.exercises[dateStr] = {};
            
            const isCurrentlyChecked = gymState.exercises[dateStr][index] === true;
            gymState.exercises[dateStr][index] = !isCurrentlyChecked;
            
            const allLis = card.querySelectorAll('li');
            let allChecked = true;
            allLis.forEach((li, idx) => {
                if (!gymState.exercises[dateStr][idx]) allChecked = false;
            });
            
            if (allChecked) {
                gymState.log[dateStr] = 'completed';
            } else {
                if (gymState.log[dateStr] === 'completed') {
                    delete gymState.log[dateStr];
                }
            }
            
            updateGymUI();
        }

        function toggleWorkoutDay(status) {
            const dateStr = document.getElementById('gym-date-picker').value;
            if (!dateStr) return;
            
            if (gymState.log[dateStr] === status) {
                delete gymState.log[dateStr];
                if(status === 'completed') {
                    if(gymState.exercises && gymState.exercises[dateStr]) {
                        delete gymState.exercises[dateStr];
                    }
                }
            } else {
                gymState.log[dateStr] = status;
                
                if (status === 'completed') {
                    if (!gymState.exercises) gymState.exercises = {};
                    gymState.exercises[dateStr] = {};
                    
                    const dateParts = dateStr.split('-');
                    const dateObj = new Date(dateParts[0], dateParts[1] - 1, dateParts[2]);
                    const dayNames = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
                    const dayName = dayNames[dateObj.getDay()];
                    
                    const card = document.querySelector(`.gym-card[data-day="${dayName}"]`);
                    if (card) {
                        card.querySelectorAll('li').forEach((li, idx) => {
                            gymState.exercises[dateStr][idx] = true;
                        });
                    }
                } else if (status === 'missed') {
                    if(gymState.exercises && gymState.exercises[dateStr]) {
                        delete gymState.exercises[dateStr];
                    }
                }
            }
            updateGymUI();
        }

        function updateGymUI() {
            const datePicker = document.getElementById('gym-date-picker');
            if (!datePicker) return;
            
            let dateStr = datePicker.value;
            if (!dateStr) {
                dateStr = getTodayString();
                datePicker.value = dateStr;
            }

            const dateParts = dateStr.split('-');
            const dateObj = new Date(dateParts[0], dateParts[1] - 1, dateParts[2]);
            const dayNames = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
            const dayName = dayNames[dateObj.getDay()];
            
            document.querySelectorAll('.gym-card').forEach(card => {
                const isHighlighted = card.dataset.day === dayName;
                const lis = card.querySelectorAll('li');
                
                if(isHighlighted) {
                    card.classList.add('border-zinc-400', 'opacity-100');
                    card.classList.remove('border-[#27272A]', 'opacity-40');
                } else {
                    card.classList.remove('border-zinc-400', 'opacity-100');
                    card.classList.add('border-[#27272A]', 'opacity-40');
                }
                
                lis.forEach((li, idx) => {
                    const checkbox = li.querySelector('.exercise-checkbox');
                    const checkIcon = li.querySelector('.exercise-checkbox i');
                    const nameEl = li.querySelector('.exercise-name');
                    
                    if (isHighlighted) {
                        li.classList.add('cursor-pointer', 'hover:opacity-80');
                        const isChecked = (gymState.exercises && gymState.exercises[dateStr] && gymState.exercises[dateStr][idx]) || gymState.log[dateStr] === 'completed';
                        
                        if (isChecked) {
                            checkbox.classList.add('bg-emerald-500', 'border-emerald-500');
                            checkbox.classList.remove('border-[#3F3F46]');
                            checkIcon.classList.remove('text-transparent');
                            checkIcon.classList.add('text-white');
                            nameEl.classList.add('line-through', 'text-[#A1A1AA]');
                            nameEl.classList.remove('text-[#D4D4D8]');
                        } else {
                            checkbox.classList.remove('bg-emerald-500', 'border-emerald-500');
                            checkbox.classList.add('border-[#3F3F46]');
                            checkIcon.classList.add('text-transparent');
                            checkIcon.classList.remove('text-white');
                            nameEl.classList.remove('line-through', 'text-[#A1A1AA]');
                            nameEl.classList.add('text-[#D4D4D8]');
                        }
                    } else {
                        li.classList.remove('cursor-pointer', 'hover:opacity-80');
                        checkbox.classList.remove('bg-emerald-500', 'border-emerald-500');
                        checkbox.classList.add('border-[#3F3F46]');
                        checkIcon.classList.add('text-transparent');
                        checkIcon.classList.remove('text-white');
                        nameEl.classList.remove('line-through', 'text-[#A1A1AA]');
                        nameEl.classList.add('text-[#D4D4D8]');
                    }
                });
            });

            const currentStatus = gymState.log[dateStr];
            const btnComp = document.getElementById('btn-mark-comp');
            const btnMiss = document.getElementById('btn-mark-miss');
            
            if (currentStatus === 'completed') {
                btnComp.classList.replace('bg-[#27272A]', 'bg-emerald-600');
                btnComp.classList.replace('text-[#A1A1AA]', 'text-white');
                btnMiss.classList.replace('bg-red-600', 'bg-[#27272A]');
                btnMiss.classList.replace('text-white', 'text-[#A1A1AA]');
            } else if (currentStatus === 'missed') {
                btnMiss.classList.replace('bg-[#27272A]', 'bg-red-600');
                btnMiss.classList.replace('text-[#A1A1AA]', 'text-white');
                btnComp.classList.replace('bg-emerald-600', 'bg-[#27272A]');
                btnComp.classList.replace('text-white', 'text-[#A1A1AA]');
            } else {
                btnComp.classList.replace('bg-emerald-600', 'bg-[#27272A]');
                btnComp.classList.replace('text-white', 'text-[#A1A1AA]');
                btnMiss.classList.replace('bg-red-600', 'bg-[#27272A]');
                btnMiss.classList.replace('text-white', 'text-[#A1A1AA]');
            }

            let comp = 0, miss = 0;
            for(let key in gymState.log) {
                if(gymState.log[key] === 'completed') comp++;
                if(gymState.log[key] === 'missed') miss++;
            }
            const trackerCompEl = document.getElementById('tracker-completed');
            const trackerMissEl = document.getElementById('tracker-missed');
            if(trackerCompEl) trackerCompEl.textContent = comp;
            if(trackerMissEl) trackerMissEl.textContent = miss;

            const grid = document.getElementById('consistency-grid');
            if(!grid) return;
            grid.innerHTML = '';
            
            const today = new Date();
            const start = new Date(today);
            start.setDate(today.getDate() - 364);
            
            for(let i=0; i<365; i++) {
                const d = new Date(start);
                d.setDate(start.getDate() + i);
                const dStr = `${d.getFullYear()}-${String(d.getMonth() + 1).padStart(2, '0')}-${String(d.getDate()).padStart(2, '0')}`;
                
                const square = document.createElement('div');
                square.className = 'w-3 h-3 rounded-[2px] flex-shrink-0 cursor-pointer transition-all duration-200';
                
                if (gymState.log[dStr] === 'completed') {
                    square.classList.add('bg-emerald-500', 'shadow-[0_0_4px_rgba(16,185,129,0.3)]');
                } else if (gymState.log[dStr] === 'missed') {
                    square.classList.add('bg-red-500', 'shadow-[0_0_4px_rgba(239,68,68,0.3)]');
                } else {
                    square.classList.add('bg-[#27272A]', 'hover:bg-[#3F3F46]');
                }

                if (dStr === dateStr) {
                    square.classList.add('ring-2', 'ring-zinc-300', 'ring-offset-2', 'ring-offset-[#09090B]');
                }
                
                square.title = dStr;
                square.onclick = () => {
                    datePicker.value = dStr;
                    updateGymUI();
                };
                grid.appendChild(square);
            }
        }

        // --- PERP CALCULATOR FUNCTIONS ---
        function perpSetDir(dir) {
            perpState.dir = dir;
            const btnLong = document.getElementById('perp-btn-long');
            const btnShort = document.getElementById('perp-btn-short');
            
            if (dir === 'long') {
                btnLong.className = 'perp-dir-btn active bg-emerald-500/15 text-emerald-400 border border-emerald-500/30 py-3 text-xs font-bold font-mono-custom uppercase tracking-wider rounded-lg transition-all shadow-[0_0_15px_rgba(16,185,129,0.1)]';
                btnShort.className = 'perp-dir-btn bg-transparent text-gray-500 border border-transparent hover:bg-white/5 py-3 text-xs font-bold font-mono-custom uppercase tracking-wider rounded-lg transition-all';
            } else {
                btnShort.className = 'perp-dir-btn active bg-rose-500/15 text-rose-400 border border-rose-500/30 py-3 text-xs font-bold font-mono-custom uppercase tracking-wider rounded-lg transition-all shadow-[0_0_15px_rgba(244,63,94,0.1)]';
                btnLong.className = 'perp-dir-btn bg-transparent text-gray-500 border border-transparent hover:bg-white/5 py-3 text-xs font-bold font-mono-custom uppercase tracking-wider rounded-lg transition-all';
            }
            perpCalc();
        }

        function perpSetLev(val) {
            perpState.lev = parseInt(val);
            document.getElementById('perp-lev-display').textContent = perpState.lev;
            document.getElementById('perp-slider').value = perpState.lev;
            
            document.querySelectorAll('.perp-lev-btn').forEach(btn => {
                if (parseInt(btn.textContent) === perpState.lev) {
                    btn.className = 'perp-lev-btn active-lev px-3 py-1.5 text-[10px] font-bold font-mono-custom bg-indigo-500/10 border border-indigo-500 rounded-lg text-indigo-400 transition-all flex-1 shadow-[0_0_10px_rgba(99,102,241,0.2)]';
                } else {
                    btn.className = 'perp-lev-btn px-3 py-1.5 text-[10px] font-bold font-mono-custom bg-[#181a21] border border-[#282b3a] rounded-lg text-gray-400 hover:border-indigo-500/50 hover:text-indigo-400 transition-all flex-1';
                }
            });
            perpCalc();
        }

        function perpSliderLev(val) {
            perpSetLev(val);
        }

        function perpFmt(n, dec=2) {
            if (isNaN(n) || !isFinite(n)) return '—';
            return n.toLocaleString('en-US', { minimumFractionDigits: dec, maximumFractionDigits: dec });
        }

        function perpCalc() {
            const entry = parseFloat(document.getElementById('perp-entry').value);
            const margin = parseFloat(document.getElementById('perp-margin').value);
            const tp = parseFloat(document.getElementById('perp-tp').value);
            const sl = parseFloat(document.getElementById('perp-sl').value);

            const hasBase = entry > 0 && margin > 0;
            const hasTP = tp > 0;
            const hasSL = sl > 0;

            if (!hasBase) {
                document.getElementById('perp-empty-state').classList.remove('hidden');
                document.getElementById('perp-results-section').classList.add('hidden');
                return;
            }
            
            document.getElementById('perp-empty-state').classList.add('hidden');
            document.getElementById('perp-results-section').classList.remove('hidden');

            const notional = margin * perpState.lev;
            const btcAmt = notional / entry;

            // Liquidation logic
            const MM = 0.005; 
            const liqPrice = perpState.dir === 'long' 
                ? entry * (1 - 1/perpState.lev + MM) 
                : entry * (1 + 1/perpState.lev - MM);

            // TP Logic
            let tpPnl = NaN, tpRoe = NaN;
            if (hasTP) {
                const diff = perpState.dir === 'long' ? (tp - entry) : (entry - tp);
                tpPnl = (diff / entry) * notional;
                tpRoe = (tpPnl / margin) * 100;
                
                document.getElementById('res-perp-profit-usd').textContent = (tpPnl >= 0 ? '+' : '') + '$' + perpFmt(tpPnl);
                document.getElementById('res-perp-profit-roe').textContent = (tpRoe >= 0 ? '+' : '') + perpFmt(tpRoe) + '% ROE';
            } else {
                document.getElementById('res-perp-profit-usd').textContent = '—';
                document.getElementById('res-perp-profit-roe').textContent = 'Set TP';
            }

            // SL Logic
            let slPnl = NaN, slRoe = NaN;
            if (hasSL) {
                const diff = perpState.dir === 'long' ? (sl - entry) : (entry - sl);
                slPnl = (diff / entry) * notional; // typically negative
                slRoe = (slPnl / margin) * 100;
                
                document.getElementById('res-perp-loss-usd').textContent = '$' + perpFmt(slPnl);
                document.getElementById('res-perp-loss-roe').textContent = perpFmt(slRoe) + '% ROE';
            } else {
                document.getElementById('res-perp-loss-usd').textContent = '—';
                document.getElementById('res-perp-loss-roe').textContent = 'Set SL';
            }

            // General outputs
            document.getElementById('res-perp-liq').textContent = '$' + perpFmt(liqPrice, 0);
            const distPct = Math.abs((liqPrice - entry) / entry * 100);
            document.getElementById('res-perp-liq-dist').textContent = perpFmt(distPct, 1) + '% from entry';
            
            // Pulse liquidation card if high risk
            const liqCard = document.getElementById('perp-liq-card');
            if(perpState.lev >= 20) {
                liqCard.classList.add('shadow-[0_0_20px_rgba(249,115,22,0.15)]', 'animate-pulse');
            } else {
                liqCard.classList.remove('shadow-[0_0_20px_rgba(249,115,22,0.15)]', 'animate-pulse');
            }

            document.getElementById('res-perp-size').textContent = '$' + perpFmt(notional, 0);
            document.getElementById('res-perp-btc').textContent = btcAmt.toFixed(4) + ' BTC';

            // R:R
            const rrEl = document.getElementById('res-perp-rr');
            if (hasTP && hasSL && slPnl !== 0 && !isNaN(tpPnl) && !isNaN(slPnl)) {
                const rr = Math.abs(tpPnl / slPnl);
                rrEl.textContent = rr.toFixed(2) + ' : 1';
                if(rr >= 1.5) {
                    rrEl.className = 'text-emerald-400 font-bold px-2 py-1 rounded bg-emerald-500/10';
                } else {
                    rrEl.className = 'text-rose-400 font-bold px-2 py-1 rounded bg-rose-500/10';
                }
            } else {
                rrEl.textContent = '—';
                rrEl.className = 'text-gray-500 font-bold px-2 py-1 rounded bg-white/5';
            }
        }

        // --- GLOBAL INITIALIZATION ---
        window.addEventListener('load', () => {
            // Setup Date Pickers
            const daySel = document.getElementById('wi-day');
            if(daySel) {
                for(let i=1; i<=31; i++) daySel.add(new Option(i.toString().padStart(2,'0'), i.toString().padStart(2,'0')));
            }
            const yearSel = document.getElementById('wi-year');
            if(yearSel) {
                for(let i=new Date().getFullYear(); i>=2013; i--) yearSel.add(new Option(i, i));
            }
            
            if(daySel) daySel.value = "01"; 
            const monthSel = document.getElementById('wi-month');
            if(monthSel) monthSel.value = "01"; 
            if(yearSel) yearSel.value = "2020";

            fetchAllLivePrices(); 
            fetchLiveFiatPrice(); 
            
            setTimeout(fetchHistoricalPrice, 500);
            
            setInterval(() => { fetchAllLivePrices(); fetchLiveFiatPrice(); }, 3600000);

            // Debounce Date changes 
            ['wi-day', 'wi-month', 'wi-year'].forEach(id => {
                const el = document.getElementById(id);
                if(el) {
                    el.addEventListener('change', () => {
                        const statusEl = document.getElementById('wi-hist-price');
                        if(statusEl) {
                            statusEl.textContent = "Waiting...";
                            statusEl.className = "text-gray-500 animate-pulse";
                        }
                        clearTimeout(histFetchTimeout);
                        histFetchTimeout = setTimeout(fetchHistoricalPrice, 600);
                    });
                }
            });
            
            const wiAmtInp = document.getElementById('wi-amount');
            if(wiAmtInp) {
                wiAmtInp.addEventListener('input', (e) => {
                    const clean = e.target.value.replace(/,/g, '');
                    if(!isNaN(clean) && clean !== "") {
                        e.target.value = parseFloat(clean).toLocaleString('en-US');
                    }
                    runSimulation();
                });
            }
            
            coins.forEach(coin => {
                const ids = [`${coin}-initial`, `${coin}-target`, `${coin}-investment`];
                ids.forEach(id => {
                    const el = document.getElementById(id);
                    if (el) el.addEventListener('input', () => {
                        const initEl = document.getElementById(`${coin}-initial`);
                        const targEl = document.getElementById(`${coin}-target`);
                        const invEl = document.getElementById(`${coin}-investment`);
                        
                        const startVal = initEl ? initEl.value.replace(/,/g, '') : '';
                        const targetVal = targEl ? targEl.value.replace(/,/g, '') : '';
                        const investVal = invEl ? invEl.value.replace(/,/g, '') : '';
                        
                        const start = parseFloat(startVal), target = parseFloat(targetVal), invest = parseFloat(investVal);
                        const incEl = document.getElementById(`${coin}-increase`), profEl = document.getElementById(`${coin}-profit`);
                        
                        if (start > 0 && !isNaN(target) && !isNaN(invest) && incEl && profEl) {
                            const inc = ((target - start) / start) * 100;
                            const prof = invest * (inc / 100);
                            incEl.textContent = (inc >= 0 ? '+' : '') + inc.toLocaleString('en-US', {minimumFractionDigits: 2, maximumFractionDigits: 2}) + '%';
                            profEl.textContent = (prof >= 0 ? '$' : '-$') + Math.abs(prof).toLocaleString('en-US', {minimumFractionDigits: 2, maximumFractionDigits: 2});
                            incEl.className = profEl.className = inc >= 0 ? 'font-bold text-green-700 text-lg' : 'font-bold text-red-600 text-lg';
                        } else if (incEl && profEl) {
                            incEl.textContent = '--';
                            profEl.textContent = '--';
                            incEl.className = 'font-bold text-gray-900 text-lg';
                            profEl.className = 'font-bold text-gray-900 text-lg';
                        }
                    });
                });
            });
            
            const fUsd = document.getElementById('fiat-usd');
            const fInr = document.getElementById('fiat-inr');
            if(fUsd) fUsd.addEventListener('input', () => handleFiatConversion('usd'));
            if(fInr) fInr.addEventListener('input', () => handleFiatConversion('inr'));
            
            const dcaContainer = document.getElementById('dca-entries');
            if(dcaContainer) {
                resetDCA();
            }

            const gymDatePicker = document.getElementById('gym-date-picker');
            if(gymDatePicker) {
                gymDatePicker.value = getTodayString();
                gymDatePicker.addEventListener('change', updateGymUI);
                updateGymUI();
            }

            // Init Perp
            perpCalc();
        });

        // --- FETCH HISTORICAL BTC PRICE ---
        async function fetchHistoricalPrice() {
            const dayEl = document.getElementById('wi-day');
            const monthEl = document.getElementById('wi-month');
            const yearEl = document.getElementById('wi-year');
            
            if(!dayEl || !monthEl || !yearEl) return;
            
            const day = dayEl.value;
            const month = monthEl.value;
            const year = yearEl.value;
            
            const statusEl = document.getElementById('wi-hist-price');
            
            if(statusEl) {
                statusEl.textContent = "Loading...";
                statusEl.className = "text-amber-500 animate-pulse";
            }

            try {
                // Check if future date or today
                const selectedDate = new Date(`${year}-${month}-${day}T00:00:00`);
                const now = new Date();
                
                if (selectedDate > now) {
                    historicalPriceBtc = livePrices.btc;
                    if(statusEl) {
                        statusEl.textContent = `(Live) $${(historicalPriceBtc||0).toLocaleString('en-US', {minimumFractionDigits: 2})}`;
                        statusEl.className = "text-white font-black";
                    }
                    runSimulation();
                    return;
                }

                let fetchedPrice = 0;
                
                // Calculate Unix Timestamp for Fallbacks
                const unixMs = new Date(`${year}-${month}-${day}T00:00:00Z`).getTime();
                const unixSec = Math.floor(unixMs / 1000);

                // API 1: Binance Historical Klines (Extremely reliable, but only > 2017)
                if (parseInt(year) >= 2018) {
                    try {
                        const res = await fetch(`https://api.binance.com/api/v3/klines?symbol=BTCUSDT&interval=1d&startTime=${unixMs}&limit=1`);
                        if (res.ok) {
                            const data = await res.json();
                            if (data && data.length > 0) fetchedPrice = parseFloat(data[0][4]); // Close price
                        }
                    } catch(e) { console.log('Binance API skipped'); }
                }

                // API 2: CryptoCompare (Fallback for older dates, free and fast)
                if (!fetchedPrice || fetchedPrice <= 0) {
                    try {
                        const fallbackRes = await fetch(`https://min-api.cryptocompare.com/data/pricehistorical?fsym=BTC&tsyms=USD&ts=${unixSec}`);
                        if (fallbackRes.ok) {
                            const fbData = await fallbackRes.json();
                            if (fbData && fbData.BTC && fbData.BTC.USD) {
                                fetchedPrice = parseFloat(fbData.BTC.USD);
                            }
                        }
                    } catch(e) { console.log('CryptoCompare API skipped'); }
                }
                
                // API 3: CoinGecko (Absolute last resort due to strict limits)
                if (!fetchedPrice || fetchedPrice <= 0) {
                    try {
                        const dateParam = `${day}-${month}-${year}`;
                        const res = await fetch(`https://api.coingecko.com/api/v3/coins/bitcoin/history?date=${dateParam}&localization=false`);
                        if (res.ok) {
                            const data = await res.json();
                            if (data && data.market_data && data.market_data.current_price) {
                                fetchedPrice = parseFloat(data.market_data.current_price.usd);
                            }
                        }
                    } catch(e) { console.log('CoinGecko API skipped'); }
                }

                if (fetchedPrice > 0) {
                    historicalPriceBtc = fetchedPrice;
                    if(statusEl) {
                        statusEl.textContent = `$${historicalPriceBtc.toLocaleString('en-US', {minimumFractionDigits: 2})}`;
                        statusEl.className = "text-white font-black";
                    }
                } else if (parseInt(year) < 2013 || (parseInt(year) === 2013 && parseInt(month) < 4)) {
                    if(statusEl) {
                        statusEl.textContent = "Before BTC Trading";
                        statusEl.className = "text-red-500 font-black text-[9px]";
                    }
                    historicalPriceBtc = 0;
                } else {
                    if(statusEl) {
                        statusEl.textContent = "Approx $13.50";
                        statusEl.className = "text-gray-400 font-black";
                    }
                    historicalPriceBtc = 13.50; 
                }
                
                runSimulation();
            } catch (e) { 
                if(statusEl) {
                    statusEl.textContent = "ERROR"; 
                    statusEl.className = "text-red-500 font-black";
                }
                historicalPriceBtc = 0; 
                runSimulation();
            }
        }

        // --- TIME MACHINE SIMULATION ---
        function runSimulation() {
            const amtEl = document.getElementById('wi-amount');
            if(!amtEl) return;
            
            const val = parseFloat(amtEl.value.replace(/,/g, ''));
            const resBtc = document.getElementById('res-btc-owned'), resVal = document.getElementById('res-val-today');
            const resPnl = document.getElementById('res-pnl'), resPerc = document.getElementById('res-perc');

            if (isNaN(val) || val <= 0 || historicalPriceBtc <= 0 || livePrices.btc <= 0) {
                if(resBtc) resBtc.textContent = "0.000000"; 
                if(resVal) resVal.textContent = "$0.00"; 
                if(resPnl) { resPnl.textContent = "$0.00"; resPnl.className = `text-xs font-black text-gray-500`; }
                if(resPerc) { resPerc.textContent = "0%"; resPerc.className = `text-xs font-black text-gray-500`; }
                return;
            }

            const btcOwned = val / historicalPriceBtc;
            const valTodayUsd = btcOwned * livePrices.btc;
            const pnlUsd = valTodayUsd - val;
            const perc = ((livePrices.btc - historicalPriceBtc) / historicalPriceBtc) * 100;

            if(resBtc) resBtc.textContent = btcOwned.toLocaleString('en-US', {maximumFractionDigits: 6});
            if(resVal) resVal.textContent = `$${valTodayUsd.toLocaleString('en-US', {maximumFractionDigits: 0})}`;
            if(resPnl) resPnl.textContent = `${pnlUsd >= 0 ? '+' : '-'}$${Math.abs(pnlUsd).toLocaleString('en-US', {maximumFractionDigits: 0})}`;
            if(resPerc) resPerc.textContent = `${perc >= 0 ? '+' : ''}${perc.toFixed(0)}%`;
            
            const color = pnlUsd >= 0 ? 'text-green-400' : 'text-red-400';
            if(resPerc) resPerc.className = `text-xs font-black ${color}`;
            if(resPnl) resPnl.className = `text-xs font-black ${color}`;
        }

        // --- NUMBER RAIN ANIMATION ---
        function startMatrixEffect() {
            const canvas = document.getElementById('matrix-canvas');
            if(!canvas) return;
            const ctx = canvas.getContext('2d');
            canvas.style.display = 'block';
            
            function setupCanvas() {
                canvas.width = window.innerWidth; 
                canvas.height = window.innerHeight;
                const columns = Math.ceil(canvas.width / 14);
                if (columns > drops.length) {
                    drops.push(...Array(columns - drops.length).fill(0));
                }
            }
            
            setupCanvas();
            window.onresize = setupCanvas;

            function draw() {
                ctx.fillStyle = "rgba(0, 0, 0, 0.2)"; 
                ctx.fillRect(0, 0, canvas.width, canvas.height);
                
                ctx.fillStyle = "#F7931A"; 
                ctx.font = "14px monospace";
                
                drops.forEach((y, i) => {
                    ctx.fillText(Math.floor(Math.random()*10), i * 14, y * 14);
                    if (y * 14 > canvas.height && Math.random() > 0.99) drops[i] = 0;
                    drops[i]++;
                });
            }
            
            if(matrixInterval) clearInterval(matrixInterval);
            matrixInterval = setInterval(draw, 100);
        }

        // --- HELPER: HIDE ALL APPS ---
        function hideAllApps() {
            document.getElementById('calculator-app')?.classList.add('hidden');
            document.getElementById('what-if-app')?.classList.add('hidden');
            document.getElementById('gym-schedule-app')?.classList.add('hidden');
            document.getElementById('perp-app')?.classList.add('hidden');
            
            const canvas = document.getElementById('matrix-canvas');
            if(canvas) canvas.style.display = 'none'; 
            if(matrixInterval) clearInterval(matrixInterval);
        }

        // --- NAVIGATION ---
        function openCalculator() { 
            document.body.style.backgroundColor = '#23292F'; 
            hideAllApps();
            
            const monkey = document.getElementById('monkey-container');
            if(monkey) monkey.classList.remove('!hidden'); 
            
            document.getElementById('landing-page').classList.add('hidden'); 
            const app = document.getElementById('calculator-app');
            if(app) {
                app.classList.remove('hidden'); 
                setTimeout(() => app.classList.remove('opacity-0'), 50); 
            }
            confetti({ particleCount: 150, zIndex: 1000 }); 
        }
        
        function openWhatIf() { 
            document.body.style.backgroundColor = '#000000'; 
            hideAllApps();
            
            const monkey = document.getElementById('monkey-container');
            if(monkey) monkey.classList.add('!hidden'); 
            
            document.getElementById('landing-page').classList.add('hidden'); 
            
            const wiApp = document.getElementById('what-if-app');
            if(wiApp) {
                wiApp.classList.remove('hidden'); 
                setTimeout(() => { 
                    wiApp.classList.remove('opacity-0'); 
                    startMatrixEffect(); 
                }, 50);
            }
        }

        function openGymSchedule() { 
            document.body.style.backgroundColor = '#23292F'; 
            hideAllApps();
            
            const monkey = document.getElementById('monkey-container');
            if(monkey) monkey.classList.add('!hidden'); 
            
            document.getElementById('landing-page').classList.add('hidden'); 
            
            const gymApp = document.getElementById('gym-schedule-app');
            if(gymApp) {
                gymApp.classList.remove('hidden'); 
                setTimeout(() => {
                    gymApp.classList.remove('opacity-0', 'translate-y-4'); 
                }, 50);
            }
        }

        function openPerp() {
            document.body.style.backgroundColor = '#000000';
            hideAllApps();
            
            const monkey = document.getElementById('monkey-container');
            if(monkey) monkey.classList.add('!hidden');
            
            document.getElementById('landing-page').classList.add('hidden');
            
            const perpApp = document.getElementById('perp-app');
            if(perpApp) {
                perpApp.classList.remove('hidden');
                setTimeout(() => perpApp.classList.remove('opacity-0', 'translate-y-4'), 50);
                perpCalc();
            }
        }
        
        function goBackToLanding() { 
            document.body.style.backgroundColor = '#23292F'; 
            hideAllApps();
            
            const monkey = document.getElementById('monkey-container');
            if(monkey) monkey.classList.remove('!hidden'); 
            
            const landing = document.getElementById('landing-page');
            if(landing) landing.classList.remove('hidden'); 
        }

        // --- GLOBAL APIS ---
        async function fetchLivePrice(id, symbol) {
            try {
                let p = 0;
                if (id === 'hype') {
                    p = 39.36 + (Math.random() * 1.5 - 0.75);
                } else { 
                    try {
                        const r = await fetch(`https://api.binance.com/api/v3/ticker/price?symbol=${symbol}`); 
                        if (!r.ok) throw new Error('API limit');
                        const d = await r.json(); 
                        p = parseFloat(d.price); 
                    } catch(e) {
                        const kucoinSymbol = symbol.replace('USDT', '-USDT');
                        const r2 = await fetch(`https://api.kucoin.com/api/v1/market/orderbook/level1?symbol=${kucoinSymbol}`);
                        const d2 = await r2.json();
                        p = parseFloat(d2.data.price);
                    }
                }
                if (p > 0) { 
                    livePrices[id] = p; 
                    const el = document.getElementById(`live-${id}-price`); 
                    if(el) el.textContent = p.toLocaleString('en-US', {minimumFractionDigits: 2, maximumFractionDigits: 2}); 
                    if(id === 'btc') runSimulation();
                }
            } catch (e) {
                const el = document.getElementById(`live-${id}-price`); 
                if (el && el.textContent === '...') el.textContent = 'Error';
            }
        }
        
        function fetchAllLivePrices() { 
            [{id:'btc',s:'BTCUSDT'},{id:'eth',s:'ETHUSDT'},{id:'sol',s:'SOLUSDT'},{id:'hype',s:'HYPEUSDT'},{id:'link',s:'LINKUSDT'}].forEach(c => fetchLivePrice(c.id, c.s)); 
        }
        
        function refreshSingleLivePrice(id) { 
            const cfg = {btc:'BTCUSDT',eth:'ETHUSDT',sol:'SOLUSDT',hype:'HYPEUSDT',link:'LINKUSDT'}; 
            fetchLivePrice(id, cfg[id]); 
            const icon = document.querySelector(`button[onclick*="refreshSingleLivePrice('${id}')"] i`);
            if (icon) { icon.classList.add('animate-spin'); setTimeout(() => icon.classList.remove('animate-spin'), 500); }
        }
        
        async function fetchLiveFiatPrice() { 
            try { 
                const r = await fetch('https://open.er-api.com/v6/latest/USD'); 
                const d = await r.json(); 
                if(d.rates.INR) {
                    currentUsdInrRate = d.rates.INR; 
                    const el = document.getElementById('live-fiat-price');
                    if(el) el.textContent = currentUsdInrRate.toLocaleString('en-US', {minimumFractionDigits:2});
                }
            } catch(e){} 
        }

        // --- CALCULATOR UI HELPERS ---
        function setInputVal(id, val) { 
            const el = document.getElementById(id); 
            if(el) { 
                el.value = parseFloat(val).toLocaleString(); 
                el.dispatchEvent(new Event('input')); 
            } 
        }
        function setInvestment(c, v) { setInputVal(`${c}-investment`, v); }
        
        function useLivePrice(id) { 
            const pEl = document.getElementById(`live-${id}-price`);
            if(!pEl) return;
            const p = pEl.textContent; 
            const i = document.getElementById(`${id}-initial`); 
            if(i && p !== '...' && p !== 'Error') { 
                i.value = p; 
                i.dispatchEvent(new Event('input')); 
            } 
        }
        
        function resetCard(c) { 
            [`${c}-initial`, `${c}-target`, `${c}-investment`].forEach(id => { 
                const el = document.getElementById(id); 
                if(el) el.value = ''; 
            }); 
            const initEl = document.getElementById(`${c}-initial`);
            if(initEl) initEl.dispatchEvent(new Event('input')); 
        }
        
        function highlightCard(c) { 
            document.querySelectorAll('.crypto-card').forEach(card => { 
                card.style.boxShadow = ''; 
                card.style.transform = ''; 
            }); 
            const sel = document.getElementById(`card-${c}`); 
            if(sel) { 
                sel.style.boxShadow = '0 0 0 9px #F7931A'; 
                sel.scrollIntoView({ behavior: 'smooth', block: 'center' }); 
            } 
        }

        function handleFiatConversion(source) {
            if(!currentUsdInrRate) return;
            const usd = document.getElementById('fiat-usd'), inr = document.getElementById('fiat-inr');
            if(!usd || !inr) return;
            
            if (source === 'usd') {
                const v = parseFloat(usd.value.replace(/,/g, ''));
                inr.value = isNaN(v) ? '' : (v * currentUsdInrRate).toLocaleString('en-US', {minimumFractionDigits:2});
            } else {
                const v = parseFloat(inr.value.replace(/,/g, ''));
                usd.value = isNaN(v) ? '' : (v / currentUsdInrRate).toLocaleString('en-US', {minimumFractionDigits:2});
            }
        }
        function resetFiat() { 
            const usd = document.getElementById('fiat-usd');
            const inr = document.getElementById('fiat-inr');
            if(usd) usd.value = ''; 
            if(inr) inr.value = ''; 
        }

        // --- DCA CALCULATOR ---
        function calculateDCA() {
            const entries = document.querySelectorAll('.dca-entry');
            let ti = 0, tc = 0, pr = [], ap = [], inv = [];
            
            entries.forEach(e => {
                const pEl = e.querySelector('.dca-price');
                const aEl = e.querySelector('.dca-amount');
                if(!pEl || !aEl) return;
                
                const pStr = pEl.value.replace(/,/g, '');
                const aStr = aEl.value.replace(/,/g, '');
                const p = parseFloat(pStr), a = parseFloat(aStr);
                if (p > 0 && a > 0) { 
                    ti += a; 
                    tc += (a / p); 
                    pr.push(p); 
                    inv.push(a); 
                    ap.push(ti / tc); 
                }
            });
            
            const totalInvEl = document.getElementById('dca-total-invested');
            const totalCoinsEl = document.getElementById('dca-total-coins');
            const avgPriceEl = document.getElementById('dca-average-price');
            
            if(totalInvEl) totalInvEl.textContent = '$' + ti.toLocaleString('en-US');
            if(totalCoinsEl) totalCoinsEl.textContent = tc.toLocaleString('en-US', {maximumFractionDigits:6});
            if(avgPriceEl) avgPriceEl.textContent = '$' + (tc > 0 ? (ti / tc).toLocaleString('en-US', {minimumFractionDigits:2, maximumFractionDigits:2}) : '0.00');
            
            const chartContainer = document.getElementById('dca-chart-container');
            if(chartContainer) {
                if (pr.length > 0) { 
                    chartContainer.classList.remove('hidden'); 
                    updateDCAChart(pr, ap, inv); 
                }
                else { 
                    chartContainer.classList.add('hidden'); 
                }
            }
        }

        let dcaChart = null;
        function updateDCAChart(prices, avgPrices, investments) {
            const canvasEl = document.getElementById('dcaChart');
            if(!canvasEl) return;
            
            const ctx = canvasEl.getContext('2d');
            if (dcaChart) dcaChart.destroy();
            
            dcaChart = new Chart(ctx, {
                type: 'line',
                data: {
                    labels: prices.map((_, i) => `Buy ${i + 1}`),
                    datasets: [
                        { label: 'Avg Price ($)', data: avgPrices, borderColor: '#4ade80', backgroundColor: '#4ade80', borderWidth: 3, tension: 0.3, yAxisID: 'y', order: 1 },
                        { type: 'bar', label: 'USDC', data: investments, backgroundColor: 'rgba(167, 139, 250, 0.4)', yAxisID: 'y1', order: 3 }
                    ]
                },
                options: { 
                    responsive: true, 
                    maintainAspectRatio: false, 
                    scales: { 
                        x: { ticks: { color: 'white' } }, 
                        y: { ticks: { color: 'white' } }, 
                        y1: { position: 'right', grid: { display: false }, ticks: { color: 'white' } } 
                    }, 
                    plugins: { legend: { labels: { color: 'white' } } } 
                }
            });
        }
        
        function resetDCA() { 
            const container = document.getElementById('dca-entries'); 
            if(!container) return; 
            container.innerHTML = ''; 
            addDCAEntry(true); 
            addDCAEntry(); 
            calculateDCA();
            
            container.removeEventListener('input', dcaInputHandler);
            container.addEventListener('input', dcaInputHandler);
        }
        
        function dcaInputHandler(e) {
            if(e.target.tagName === 'INPUT') {
                const clean = e.target.value.replace(/,/g, '');
                if(!isNaN(clean) && clean !== "") {
                    const pos = e.target.selectionStart;
                    const oldLen = e.target.value.length;
                    
                    e.target.value = parseFloat(clean).toLocaleString('en-US');
                    
                    const newLen = e.target.value.length;
                    e.target.setSelectionRange(pos + (newLen - oldLen), pos + (newLen - oldLen));
                }
            }
            calculateDCA();
        }
        
        window.removeDCAEntry = function(btn) {
            const entry = btn.closest('.dca-entry');
            if(entry) {
                entry.remove();
                calculateDCA();
            }
        };
        
        function addDCAEntry(isFirst = false) {
            const container = document.getElementById('dca-entries'); 
            if(!container) return;
            
            const html = `
                <div class="dca-entry flex flex-col md:flex-row gap-4 items-end bg-purple-900/10 p-4 rounded-xl border border-purple-400/20">
                    <div class="w-full">
                        <label class="block text-xs font-bold text-white mb-1 uppercase">Price</label>
                        <input type="text" inputmode="decimal" class="dca-price input-field w-full rounded-xl py-2 px-4" placeholder="0.00">
                    </div>
                    <div class="w-full">
                        <label class="block text-xs font-bold text-white mb-1 uppercase">USDC</label>
                        <input type="text" inputmode="decimal" class="dca-amount input-field w-full rounded-xl py-2 px-4" placeholder="0.00">
                    </div>
                    ${isFirst ? '<div class="w-10"></div>' : '<button onclick="window.removeDCAEntry(this)" class="p-2 text-red-400 hover:text-red-300 transition-colors"><i class="fa-solid fa-trash"></i></button>'}
                </div>
            `;
            container.insertAdjacentHTML('beforeend', html);
        }
    </script>
</body>
</html>
