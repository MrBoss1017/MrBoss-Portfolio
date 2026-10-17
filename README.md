<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MrBoss | Developer, Mod Creator, Robotics & Gaming Hub</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Inter & JetBrains Mono -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=JetBrains+Mono:ital,wght@0,400;0,500;0,600;0,700;1,400&display=swap" rel="stylesheet">
    <!-- Font Awesome 6 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        mono: ['JetBrains Mono', 'monospace'],
                    }
                }
            }
        }
    </script>

    <style>
        /* ==========================================
           CYBER-TECH THEME VARIABLES
           ========================================== */
        :root {
            --bg-primary: #090d16;
            --bg-secondary: #0c1220;
            --bg-card: rgba(15, 23, 42, 0.72);
            --bg-terminal: rgba(8, 12, 22, 0.92);
            --accent-primary: #00f2fe;
            --accent-primary-rgb: 0, 242, 254;
            --accent-secondary: #7c3aed;
            --accent-secondary-rgb: 124, 58, 237;
            --accent-tertiary: #10b981;
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --border-glow: rgba(0, 242, 254, 0.28);
            --card-border: rgba(148, 163, 184, 0.14);
            --hero-gradient: linear-gradient(135deg, #00f2fe 0%, #38bdf8 45%, #7c3aed 100%);
            --badge-bg: rgba(0, 242, 254, 0.1);
        }

        body {
            background-color: var(--bg-primary);
            color: var(--text-main);
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
        }

        /* Background Cyber Grid */
        .cyber-grid {
            background-size: 42px 42px;
            background-image: 
                linear-gradient(to right, rgba(var(--accent-primary-rgb), 0.04) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(var(--accent-secondary-rgb), 0.04) 1px, transparent 1px);
        }

        /* Glassmorphism Cards */
        .glass-card {
            background: var(--bg-card);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid var(--card-border);
            transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .glass-card:hover {
            border-color: var(--border-glow);
            box-shadow: 0 12px 35px -10px rgba(var(--accent-primary-rgb), 0.16),
                        0 0 20px -5px rgba(var(--accent-secondary-rgb), 0.12);
            transform: translateY(-4px);
        }

        .glass-static {
            background: var(--bg-card);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid var(--card-border);
            transition: border-color 0.3s ease, box-shadow 0.3s ease;
        }

        /* Dynamic Accent Utilities */
        .text-accent {
            color: var(--accent-primary);
            transition: color 0.3s ease;
        }
        .text-accent-secondary {
            color: var(--accent-secondary);
            transition: color 0.3s ease;
        }
        .bg-accent {
            background-color: var(--accent-primary);
            transition: background-color 0.3s ease;
        }
        .border-accent {
            border-color: var(--accent-primary);
            transition: border-color 0.3s ease;
        }
        .gradient-text {
            background: var(--hero-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .btn-primary-glow {
            background: var(--hero-gradient);
            color: #050811;
            font-weight: 700;
            box-shadow: 0 0 24px rgba(var(--accent-primary-rgb), 0.35);
            transition: all 0.25s ease;
        }
        .btn-primary-glow:hover {
            box-shadow: 0 0 32px rgba(var(--accent-primary-rgb), 0.6), 0 0 15px rgba(var(--accent-secondary-rgb), 0.5);
            transform: translateY(-2px) scale(1.01);
        }

        .btn-outline-glow {
            background: rgba(var(--accent-primary-rgb), 0.07);
            border: 1px solid rgba(var(--accent-primary-rgb), 0.35);
            color: var(--text-main);
            transition: all 0.25s ease;
        }
        .btn-outline-glow:hover {
            background: rgba(var(--accent-primary-rgb), 0.16);
            border-color: var(--accent-primary);
            box-shadow: 0 0 20px rgba(var(--accent-primary-rgb), 0.25);
            transform: translateY(-2px);
        }

        /* Progress / Telemetry Bars */
        .telemetry-bar-fill {
            background: var(--hero-gradient);
            box-shadow: 0 0 12px rgba(var(--accent-primary-rgb), 0.5);
            transition: width 0.8s cubic-bezier(0.22, 1, 0.36, 1);
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-primary);
        }
        ::-webkit-scrollbar-thumb {
            background: rgba(var(--accent-primary-rgb), 0.35);
            border-radius: 9999px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent-primary);
        }

        /* Terminal Cursor Blink */
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }
        .cursor-blink {
            animation: blink 1s step-end infinite;
        }

        /* Spooky Float Animation */
        @keyframes floatGhost {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-6px) rotate(4deg); }
        }
        .ghost-float {
            display: inline-block;
            animation: floatGhost 2.6s ease-in-out infinite;
        }

        /* Ambient Orbs */
        .ambient-orb-1 {
            background: radial-gradient(circle, rgba(var(--accent-primary-rgb), 0.16) 0%, transparent 70%);
        }
        .ambient-orb-2 {
            background: radial-gradient(circle, rgba(var(--accent-secondary-rgb), 0.16) 0%, transparent 70%);
        }

        /* Active Filter Pill */
        .filter-btn.active {
            background: var(--hero-gradient);
            color: #060911;
            font-weight: 700;
            border-color: transparent;
            box-shadow: 0 0 18px rgba(var(--accent-primary-rgb), 0.35);
        }

        /* Hardware Tab Active */
        .hw-tab.active {
            background: rgba(var(--accent-primary-rgb), 0.15);
            border-color: var(--accent-primary);
            color: var(--accent-primary);
            box-shadow: 0 0 20px rgba(var(--accent-primary-rgb), 0.2);
        }
    </style>
</head>
<body class="cyber-grid min-h-screen relative selection:bg-cyan-400 selection:text-slate-950">

    <!-- Interactive Ambient Particle Canvas -->
    <canvas id="bg-canvas" class="fixed inset-0 pointer-events-none z-0 opacity-60"></canvas>

    <!-- Ambient Glow Orbs -->
    <div class="fixed top-[-10%] left-[-10%] w-[520px] h-[520px] rounded-full ambient-orb-1 pointer-events-none z-0 blur-3xl"></div>
    <div class="fixed bottom-[-10%] right-[-10%] w-[520px] h-[520px] rounded-full ambient-orb-2 pointer-events-none z-0 blur-3xl"></div>

    <!-- ==========================================
         STICKY NAVIGATION BAR
         ========================================== -->
    <header class="sticky top-0 z-50 border-b border-slate-800/80 bg-slate-950/80 backdrop-blur-xl">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between gap-3">
            <!-- Brand Logo -->
            <a href="#hero" class="flex items-center gap-3 group focus:outline-none">
                <div id="brand-icon-box" class="w-11 h-11 rounded-xl flex items-center justify-center bg-slate-900 border border-slate-700/80 group-hover:border-accent transition-all shadow-lg">
                    <span id="brand-emoji" class="font-mono font-extrabold text-lg gradient-text">MB</span>
                </div>
                <div>
                    <div class="flex items-center gap-2">
                        <span class="font-extrabold text-xl tracking-tight text-white">MrBoss</span>
                    </div>
                    <p class="text-xs font-mono text-slate-400">DEV // MODDER // FTC // STREAMER</p>
                </div>
            </a>

            <!-- Desktop Navigation Links -->
            <nav class="hidden md:flex items-center gap-1 lg:gap-2 font-medium text-sm text-slate-300">
                <a href="#projects" class="px-3.5 py-2 rounded-lg hover:text-white hover:bg-slate-800/60 transition">Projects</a>
                <a href="#skills" class="px-3.5 py-2 rounded-lg hover:text-white hover:bg-slate-800/60 transition">Tech Stack</a>
                <a href="#command-center" class="px-3.5 py-2 rounded-lg hover:text-white hover:bg-slate-800/60 transition">Command Center</a>
                <a href="#socials" class="px-3.5 py-2 rounded-lg hover:text-white hover:bg-slate-800/60 transition">Socials Hub</a>
            </nav>

            <!-- Mobile Menu Button -->
            <div class="flex items-center gap-2.5 md:hidden">
                <button id="mobile-menu-btn" onclick="toggleMobileMenu()" aria-label="Open Navigation Menu"
                    class="p-2.5 rounded-xl bg-slate-900 border border-slate-700 text-slate-300 hover:text-white">
                    <i id="mobile-menu-icon" class="fa-solid fa-bars text-lg"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Menu Dropdown -->
        <div id="mobile-menu" class="hidden md:hidden border-t border-slate-800/80 bg-slate-950/95 px-4 pt-3 pb-5 space-y-2">
            <a href="#projects" onclick="toggleMobileMenu()" class="block px-4 py-2.5 rounded-xl text-slate-200 hover:bg-slate-800/70 font-medium">
                <i class="fa-solid fa-code-branch w-6 text-accent"></i> Featured Projects
            </a>
            <a href="#skills" onclick="toggleMobileMenu()" class="block px-4 py-2.5 rounded-xl text-slate-200 hover:bg-slate-800/70 font-medium">
                <i class="fa-solid fa-microchip w-6 text-accent"></i> Technical Skills & Stack
            </a>
            <a href="#command-center" onclick="toggleMobileMenu()" class="block px-4 py-2.5 rounded-xl text-slate-200 hover:bg-slate-800/70 font-medium">
                <i class="fa-solid fa-server w-6 text-accent"></i> The Command Center Rig
            </a>
            <a href="#socials" onclick="toggleMobileMenu()" class="block px-4 py-2.5 rounded-xl text-slate-200 hover:bg-slate-800/70 font-medium">
                <i class="fa-solid fa-share-nodes w-6 text-accent"></i> Socials & Creator Hub
            </a>
        </div>
    </header>

    <!-- ==========================================
         MAIN CONTENT CONTAINER
         ========================================== -->
    <main class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 pt-8 pb-24 space-y-28">

        <!-- ==========================================
             1. HERO SECTION & INTERACTIVE TERMINAL
             ========================================== -->
        <section id="hero" class="pt-4 lg:pt-8">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 lg:gap-10 items-center">
                
                <!-- Left Column: Dynamic Greeting & Action Buttons -->
                <div class="lg:col-span-7 space-y-6">
                    <!-- Status Telemetry Pill -->
                    <div class="inline-flex flex-wrap items-center gap-2.5 px-3.5 py-1.5 rounded-full glass-static text-xs font-mono">
                        <span class="relative flex h-2.5 w-2.5">
                            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
                            <span class="relative inline-flex rounded-full h-2.5 w-2.5 bg-emerald-500"></span>
                        </span>
                        <span id="hero-status-badge" class="text-slate-200 font-semibold">SYSTEM ONLINE // LENOVO LEGION 5i GEN 8</span>
                        <span class="text-slate-600">|</span>
                        <span id="hero-mode-indicator" class="text-accent font-bold">CYBER-TECH OS v2.6</span>
                    </div>

                    <!-- Dynamic Hero Title -->
                    <div class="space-y-3">
                        <p class="font-mono text-sm sm:text-base text-accent tracking-wider uppercase flex items-center gap-2">
                            <i class="fa-solid fa-terminal text-xs"></i>
                            <span id="hero-greeting-prefix">Welcome to the Digital Command Center of</span>
                        </p>
                        <h1 class="text-5xl sm:text-6xl lg:text-7xl font-black tracking-tight leading-none">
                            <span class="gradient-text">MrBoss</span>
                        </h1>
                        <p class="text-lg sm:text-xl font-semibold text-slate-200 pt-1 flex flex-wrap items-center gap-x-2.5 gap-y-1">
                            <span>Game Developer</span>
                            <span class="text-accent">•</span>
                            <span>Mod Creator</span>
                            <span class="text-accent">•</span>
                            <span>FTC Robotics Programmer</span>
                            <span class="text-accent">•</span>
                            <span>Multi-Platform Streamer</span>
                        </p>
                    </div>

                    <!-- Bio Summary -->
                    <p id="hero-bio-text" class="text-slate-300 text-base sm:text-lg leading-relaxed max-w-2xl">
                        Developing custom mods in <span class="text-white font-semibold">Minecraft Java</span>, scripting games in <span class="text-white font-semibold">Roblox Luau</span>, programming <span class="text-white font-semibold">FTC Robotics</span> in Java, and streaming live from a dual-platform Command Center.
                    </p>

                    <!-- Quick Action Buttons -->
                    <div class="flex flex-wrap items-center gap-3.5 pt-2">
                        <a href="#projects" class="btn-primary-glow px-6 py-3.5 rounded-xl text-sm sm:text-base inline-flex items-center gap-2.5">
                            <i class="fa-solid fa-layer-group"></i>
                            <span>View Featured Projects</span>
                        </a>
                        <a href="#command-center" class="btn-outline-glow px-5 py-3.5 rounded-xl text-sm sm:text-base font-semibold inline-flex items-center gap-2.5">
                            <i class="fa-solid fa-microchip text-accent"></i>
                            <span>Inspect Hardware Rig</span>
                        </a>
                        <button onclick="focusTerminal()" class="btn-outline-glow px-5 py-3.5 rounded-xl text-sm sm:text-base font-mono inline-flex items-center gap-2.5">
                            <i class="fa-solid fa-GreaterThan text-accent">_</i>
                            <span>Launch CLI</span>
                        </button>
                    </div>

                    <!-- Quick Metric Highlights -->
                    <div class="grid grid-cols-2 sm:grid-cols-4 gap-3 pt-4">
                        <div class="glass-static p-3.5 rounded-xl">
                            <div class="text-xs font-mono text-slate-400">FEATURED BUILDS</div>
                            <div class="text-2xl font-extrabold text-white mt-0.5">4 <span class="text-xs font-mono text-accent font-normal">LIVE</span></div>
                        </div>
                        <div class="glass-static p-3.5 rounded-xl">
                            <div class="text-xs font-mono text-slate-400">CORE STACK</div>
                            <div class="text-2xl font-extrabold text-white mt-0.5">6 <span class="text-xs font-mono text-accent font-normal">LANGUAGES</span></div>
                        </div>
                        <div class="glass-static p-3.5 rounded-xl">
                            <div class="text-xs font-mono text-slate-400">PRIMARY RIG</div>
                            <div class="text-2xl font-extrabold text-white mt-0.5">RTX 4060 <span class="text-xs font-mono text-accent font-normal">+ PS5 PRO</span></div>
                        </div>
                        <div class="glass-static p-3.5 rounded-xl">
                            <div class="text-xs font-mono text-slate-400">MEDIA STANCE</div>
                            <div class="text-2xl font-extrabold text-white mt-0.5">100% <span class="text-xs font-mono text-accent font-normal">PHYSICAL</span></div>
                        </div>
                    </div>
                </div>

                <!-- Right Column: Interactive Command Terminal Widget -->
                <div class="lg:col-span-5">
                    <div id="terminal-container" class="rounded-2xl overflow-hidden border border-slate-700/80 shadow-2xl transition-all duration-300" style="background: var(--bg-terminal);">
                        <!-- Terminal Title Bar -->
                        <div class="px-4 py-3 bg-slate-900/95 border-b border-slate-800 flex items-center justify-between">
                            <div class="flex items-center gap-2">
                                <span class="w-3 h-3 rounded-full bg-rose-500 inline-block"></span>
                                <span class="w-3 h-3 rounded-full bg-amber-400 inline-block"></span>
                                <span class="w-3 h-3 rounded-full bg-emerald-500 inline-block"></span>
                                <span id="terminal-window-title" class="ml-2 font-mono text-xs text-slate-300 font-semibold">mrboss@legion-5i:~ (zsh)</span>
                            </div>
                            <div class="flex items-center gap-2">
                                <button onclick="runTerminalCommand('clear')" class="text-[11px] font-mono px-2 py-0.5 rounded bg-slate-800 hover:bg-slate-700 text-slate-300 transition" title="Clear Terminal">
                                    clear
                                </button>
                                <span class="text-[11px] font-mono text-accent px-2 py-0.5 rounded bg-slate-800/90 border border-slate-700">INTERACTIVE</span>
                            </div>
                        </div>

                        <!-- Quick Command Click Chips -->
                        <div class="px-4 py-2.5 bg-slate-950/70 border-b border-slate-800/80 flex items-center gap-1.5 overflow-x-auto no-scrollbar">
                            <span class="text-[11px] font-mono text-slate-400 shrink-0 mr-1">Try:</span>
                            <button onclick="runTerminalCommand('help')" class="px-2.5 py-1 rounded-md text-xs font-mono bg-slate-800/90 hover:bg-slate-700 text-cyan-300 border border-slate-700 shrink-0 transition">help</button>
                            <button onclick="runTerminalCommand('projects')" class="px-2.5 py-1 rounded-md text-xs font-mono bg-slate-800/90 hover:bg-slate-700 text-cyan-300 border border-slate-700 shrink-0 transition">projects</button>
                            <button onclick="runTerminalCommand('specs')" class="px-2.5 py-1 rounded-md text-xs font-mono bg-slate-800/90 hover:bg-slate-700 text-cyan-300 border border-slate-700 shrink-0 transition">specs</button>
                            <button onclick="runTerminalCommand('socials')" class="px-2.5 py-1 rounded-md text-xs font-mono bg-slate-800/90 hover:bg-slate-700 text-cyan-300 border border-slate-700 shrink-0 transition">socials</button>
                            <button onclick="runTerminalCommand('games')" class="px-2.5 py-1 rounded-md text-xs font-mono bg-slate-800/90 hover:bg-slate-700 text-cyan-300 border border-slate-700 shrink-0 transition">games</button>
                        </div>

                        <!-- Terminal Output Scroll Area -->
                        <div id="terminal-output" onclick="focusTerminal()" class="p-4 h-80 sm:h-96 overflow-y-auto font-mono text-xs sm:text-sm space-y-2.5 cursor-text leading-relaxed">
                            <!-- Populated dynamically via JS on load -->
                        </div>

                        <!-- Terminal Input Prompt -->
                        <form id="terminal-form" onsubmit="handleTerminalSubmit(event)" class="px-4 py-3 bg-slate-900/90 border-t border-slate-800 flex items-center gap-2 font-mono text-xs sm:text-sm">
                            <span id="terminal-prompt-label" class="text-accent font-bold shrink-0">mrboss@hub:~$</span>
                            <input id="terminal-input" type="text" autocomplete="off" spellcheck="false"
                                placeholder="Type 'help', 'projects', 'specs', 'games'..."
                                class="w-full bg-transparent text-white placeholder-slate-500 focus:outline-none font-mono" />
                            <button type="submit" class="px-2.5 py-1 rounded bg-slate-800 hover:bg-slate-700 text-slate-300 text-xs shrink-0 transition">
                                Enter ↵
                            </button>
                        </form>
                    </div>
                </div>

            </div>
        </section>

        <!-- ==========================================
             2. FEATURED PROJECTS PORTFOLIO
             ========================================== -->
        <section id="projects" class="scroll-mt-24 space-y-8">
            <div class="flex flex-col md:flex-row md:items-end justify-between gap-4 border-b border-slate-800/80 pb-6">
                <div>
                    <div class="inline-flex items-center gap-2 font-mono text-xs uppercase tracking-widest text-accent mb-2">
                        <i class="fa-solid fa-cubes"></i>
                        <span>01 // FEATURED BUILDS</span>
                    </div>
                    <h2 class="text-3xl sm:text-4xl font-extrabold tracking-tight text-white">
                        Featured Projects Portfolio
                    </h2>
                </div>

                <!-- Category Filter Buttons -->
                <div class="flex flex-wrap items-center gap-2" role="tablist" aria-label="Project Category Filter">
                    <button onclick="filterProjects('all')" data-filter="all" class="filter-btn active px-4 py-2 rounded-xl font-mono text-xs sm:text-sm border border-slate-700 bg-slate-900/80 text-slate-300 transition">
                        All (4)
                    </button>
                    <button onclick="filterProjects('Minecraft Mod')" data-filter="Minecraft Mod" class="filter-btn px-4 py-2 rounded-xl font-mono text-xs sm:text-sm border border-slate-700 bg-slate-900/80 text-slate-300 hover:border-slate-500 transition">
                        <i class="fa-brands fa-github mr-1.5"></i>Minecraft Mods (2)
                    </button>
                    <button onclick="filterProjects('Roblox Game')" data-filter="Roblox Game" class="filter-btn px-4 py-2 rounded-xl font-mono text-xs sm:text-sm border border-slate-700 bg-slate-900/80 text-slate-300 hover:border-slate-500 transition">
                        <i class="fa-solid fa-gamepad mr-1.5"></i>Roblox Games (2)
                    </button>
                </div>
            </div>

            <!-- Projects Grid -->
            <div id="projects-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
                <!-- Populated dynamically via JS -->
            </div>
        </section>

        <!-- ==========================================
             3. TECHNICAL SKILLS & STACK SHOWCASE
             ========================================== -->
        <section id="skills" class="scroll-mt-24 space-y-8">
            <div class="flex flex-col md:flex-row md:items-end justify-between gap-4 border-b border-slate-800/80 pb-6">
                <div>
                    <div class="inline-flex items-center gap-2 font-mono text-xs uppercase tracking-widest text-accent mb-2">
                        <i class="fa-solid fa-code"></i>
                        <span>02 // LANGUAGES, ENGINES & CREATOR PIPELINE</span>
                    </div>
                    <h2 class="text-3xl sm:text-4xl font-extrabold tracking-tight text-white">
                        Technical Skills & Stack
                    </h2>
                </div>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
                <!-- Column 1: Languages & Code -->
                <div class="glass-static rounded-2xl p-6 sm:p-7 space-y-6">
                    <div class="flex items-center justify-between">
                        <div class="flex items-center gap-3">
                            <div class="w-10 h-10 rounded-xl bg-slate-900 border border-slate-700 flex items-center justify-center text-accent">
                                <i class="fa-solid fa-terminal text-lg"></i>
                            </div>
                            <h3 class="text-xl font-bold text-white">Languages & Code</h3>
                        </div>
                        <span class="font-mono text-xs px-2.5 py-1 rounded-full bg-slate-900 border border-slate-800 text-slate-300">6 Languages</span>
                    </div>

                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3.5" id="languages-grid">
                        <!-- Populated via JS -->
                    </div>
                </div>

                <!-- Column 2: Tools, Engines & Creative Suite -->
                <div class="glass-static rounded-2xl p-6 sm:p-7 space-y-6">
                    <div class="flex items-center justify-between">
                        <div class="flex items-center gap-3">
                            <div class="w-10 h-10 rounded-xl bg-slate-900 border border-slate-700 flex items-center justify-center text-accent-secondary">
                                <i class="fa-solid fa-screwdriver-wrench text-lg"></i>
                            </div>
                            <h3 class="text-xl font-bold text-white">Tools, Engines & CAD</h3>
                        </div>
                        <span class="font-mono text-xs px-2.5 py-1 rounded-full bg-slate-900 border border-slate-800 text-slate-300">7 Core Suites</span>
                    </div>

                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3.5" id="tools-grid">
                        <!-- Populated via JS -->
                    </div>
                </div>
            </div>
        </section>

        <!-- ==========================================
             4. "THE COMMAND CENTER" HARDWARE & GAMING RIG
             ========================================== -->
        <section id="command-center" class="scroll-mt-24 space-y-8">
            <div class="flex flex-col lg:flex-row lg:items-end justify-between gap-4 border-b border-slate-800/80 pb-6">
                <div>
                    <div class="inline-flex items-center gap-2 font-mono text-xs uppercase tracking-widest text-accent mb-2">
                        <i class="fa-solid fa-server"></i>
                        <span>03 // BATTLE STATION & GAMING LIBRARY</span>
                    </div>
                    <h2 class="text-3xl sm:text-4xl font-extrabold tracking-tight text-white">
                        "The Command Center" Hardware & Gaming Rig
                    </h2>
                </div>

                <!-- Interactive Section View Switcher -->
                <div class="flex flex-wrap gap-2">
                    <button onclick="switchCommandTab('all')" id="hw-tab-all" class="hw-tab active px-4 py-2 rounded-xl font-mono text-xs sm:text-sm border border-slate-700 bg-slate-900/80 text-slate-300 transition">
                        <i class="fa-solid fa-table-columns mr-1.5"></i>Full Overview
                    </button>
                    <button onclick="switchCommandTab('pc')" id="hw-tab-pc" class="hw-tab px-4 py-2 rounded-xl font-mono text-xs sm:text-sm border border-slate-700 bg-slate-900/80 text-slate-300 transition">
                        <i class="fa-solid fa-desktop mr-1.5"></i>Legion 5i PC Rig
                    </button>
                    <button onclick="switchCommandTab('console')" id="hw-tab-console" class="hw-tab px-4 py-2 rounded-xl font-mono text-xs sm:text-sm border border-slate-700 bg-slate-900/80 text-slate-300 transition">
                        <i class="fa-solid fa-compact-disc mr-1.5"></i>PS5 Pro & RPCS3
                    </button>
                    <button onclick="switchCommandTab('games')" id="hw-tab-games" class="hw-tab px-4 py-2 rounded-xl font-mono text-xs sm:text-sm border border-slate-700 bg-slate-900/80 text-slate-300 transition">
                        <i class="fa-solid fa-trophy mr-1.5"></i>Top Rotation (21)
                    </button>
                </div>
            </div>

            <!-- Hardware Panels Wrapper -->
            <div class="space-y-8">
                
                <!-- ROW 1: PC RIG + CONSOLE SETUP -->
                <div id="hw-row-machines" class="grid grid-cols-1 lg:grid-cols-12 gap-8">
                    
                    <!-- PC SPECS CARD (Lenovo Legion Tower 5i Gen 8 - Specs Only) -->
                    <div id="hw-panel-pc" class="lg:col-span-7 glass-static rounded-2xl p-6 sm:p-8 space-y-6 relative overflow-hidden">
                        <div class="flex items-center gap-3.5 border-b border-slate-800 pb-5">
                            <div class="w-12 h-12 rounded-2xl bg-slate-900 border border-slate-700 flex items-center justify-center text-accent shrink-0 shadow-inner">
                                <i class="fa-solid fa-tower-broadcast text-xl"></i>
                            </div>
                            <h3 class="text-xl sm:text-2xl font-extrabold text-white">Lenovo Legion Tower 5i Gen 8</h3>
                        </div>

                        <!-- Clean Spec Rows Only (No Graphs or Descriptions) -->
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <!-- CPU -->
                            <div class="p-4 rounded-xl bg-slate-900/85 border border-slate-800 flex items-center gap-3.5 sm:col-span-2">
                                <div class="w-10 h-10 rounded-lg bg-slate-950 border border-slate-800 flex items-center justify-center text-accent shrink-0">
                                    <i class="fa-solid fa-microchip"></i>
                                </div>
                                <div>
                                    <div class="text-xs font-mono text-slate-400">CPU</div>
                                    <div class="text-sm sm:text-base font-bold text-white">Intel i5-14400F (2.50 GHz Base / 4.00 GHz Avg)</div>
                                </div>
                            </div>

                            <!-- GPU -->
                            <div class="p-4 rounded-xl bg-slate-900/85 border border-slate-800 flex items-center gap-3.5">
                                <div class="w-10 h-10 rounded-lg bg-slate-950 border border-slate-800 flex items-center justify-center text-accent shrink-0">
                                    <i class="fa-solid fa-vr-cardboard"></i>
                                </div>
                                <div>
                                    <div class="text-xs font-mono text-slate-400">GPU</div>
                                    <div class="text-sm sm:text-base font-bold text-white">NVIDIA GeForce RTX 4060 8GB VRAM</div>
                                </div>
                            </div>

                            <!-- RAM -->
                            <div class="p-4 rounded-xl bg-slate-900/85 border border-slate-800 flex items-center gap-3.5">
                                <div class="w-10 h-10 rounded-lg bg-slate-950 border border-slate-800 flex items-center justify-center text-accent shrink-0">
                                    <i class="fa-solid fa-memory"></i>
                                </div>
                                <div>
                                    <div class="text-xs font-mono text-slate-400">RAM</div>
                                    <div class="text-sm sm:text-base font-bold text-white">32GB DDR5 @ 4400 MT/s</div>
                                </div>
                            </div>

                            <!-- Storage -->
                            <div class="p-4 rounded-xl bg-slate-900/85 border border-slate-800 flex items-center gap-3.5">
                                <div class="w-10 h-10 rounded-lg bg-slate-950 border border-slate-800 flex items-center justify-center text-accent shrink-0">
                                    <i class="fa-solid fa-hard-drive"></i>
                                </div>
                                <div>
                                    <div class="text-xs font-mono text-slate-400">STORAGE</div>
                                    <div class="text-sm sm:text-base font-bold text-white">1TB NVMe M.2</div>
                                </div>
                            </div>

                            <!-- Network -->
                            <div class="p-4 rounded-xl bg-slate-900/85 border border-slate-800 flex items-center gap-3.5">
                                <div class="w-10 h-10 rounded-lg bg-slate-950 border border-slate-800 flex items-center justify-center text-accent shrink-0">
                                    <i class="fa-solid fa-network-wired"></i>
                                </div>
                                <div>
                                    <div class="text-xs font-mono text-slate-400">NETWORK</div>
                                    <div class="text-sm sm:text-base font-bold text-white">2 Ethernet Cables + Wi-Fi</div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- CONSOLE & EMULATION SETUP CARD (Titles Only, No Descriptions) -->
                    <div id="hw-panel-console" class="lg:col-span-5 glass-static rounded-2xl p-6 sm:p-8 flex flex-col justify-between space-y-6">
                        <div class="space-y-5">
                            <div class="flex items-center gap-3 border-b border-slate-800 pb-5">
                                <div class="w-12 h-12 rounded-2xl bg-slate-900 border border-slate-700 flex items-center justify-center text-accent-secondary shrink-0">
                                    <i class="fa-brands fa-playstation text-2xl"></i>
                                </div>
                                <h3 class="text-xl font-extrabold text-white">Console & Emulation</h3>
                            </div>

                            <!-- PS5 Pro Showcase -->
                            <div class="p-5 rounded-2xl bg-slate-900/90 border border-slate-800 space-y-2.5">
                                <div class="flex items-center justify-between">
                                    <span class="text-xs font-mono uppercase tracking-wider px-2.5 py-0.5 rounded-md bg-indigo-500/20 text-indigo-300 border border-indigo-500/30 font-semibold">
                                        FLAGSHIP CONSOLE
                                    </span>
                                    <span class="text-xs font-mono text-amber-400 flex items-center gap-1 font-bold">
                                        <i class="fa-solid fa-compact-disc animate-spin" style="animation-duration: 6s;"></i> DISC EDITION
                                    </span>
                                </div>
                                <h4 class="text-lg font-bold text-white">PlayStation 5 Pro + Physical Disc Drive</h4>
                            </div>

                            <!-- RPCS3 Emulation Showcase -->
                            <div class="p-5 rounded-2xl bg-slate-900/90 border border-slate-800 space-y-2.5">
                                <div class="flex items-center justify-between">
                                    <span class="text-xs font-mono uppercase tracking-wider px-2.5 py-0.5 rounded-md bg-purple-500/20 text-purple-300 border border-purple-500/30 font-semibold">
                                        EMULATION
                                    </span>
                                    <span class="text-xs font-mono text-slate-400">PS3</span>
                                </div>
                                <h4 class="text-lg font-bold text-white">RPCS3 PlayStation 3 Emulation on PC</h4>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- ROW 2: TOP ROTATION GAMES LIBRARY -->
                <div id="hw-panel-games" class="glass-static rounded-2xl p-6 sm:p-8 space-y-6">
                    <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 border-b border-slate-800 pb-5">
                        <div class="flex items-center gap-2.5">
                            <i class="fa-solid fa-fire-flame-curved text-accent text-xl"></i>
                            <h3 class="text-xl sm:text-2xl font-extrabold text-white">Top Rotation Gaming Library</h3>
                        </div>

                        <!-- Platform Filter for Games -->
                        <div class="flex flex-wrap gap-1.5 font-mono text-xs">
                            <button onclick="filterGames('all')" data-game-filter="all" class="game-filter-btn active filter-btn px-3 py-1.5 rounded-lg border border-slate-700 bg-slate-900 text-slate-300 transition">All (21)</button>
                            <button onclick="filterGames('PC')" data-game-filter="PC" class="game-filter-btn filter-btn px-3 py-1.5 rounded-lg border border-slate-700 bg-slate-900 text-slate-300 transition">PC</button>
                            <button onclick="filterGames('PS5')" data-game-filter="PS5" class="game-filter-btn filter-btn px-3 py-1.5 rounded-lg border border-slate-700 bg-slate-900 text-slate-300 transition">PS5</button>
                            <button onclick="filterGames('PS4')" data-game-filter="PS4" class="game-filter-btn filter-btn px-3 py-1.5 rounded-lg border border-slate-700 bg-slate-900 text-slate-300 transition">PS4</button>
                            <button onclick="filterGames('RPCS3')" data-game-filter="RPCS3" class="game-filter-btn filter-btn px-3 py-1.5 rounded-lg border border-slate-700 bg-slate-900 text-slate-300 transition">RPCS3</button>
                        </div>
                    </div>

                    <!-- 21 Games Responsive Grid (No Descriptions) -->
                    <div id="games-rotation-grid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
                        <!-- Populated via JS -->
                    </div>
                </div>

            </div>
        </section>

        <!-- ==========================================
             5. SOCIALS & CREATOR HUB
             ========================================== -->
        <section id="socials" class="scroll-mt-24 space-y-8">
            <div class="flex flex-col md:flex-row md:items-end justify-between gap-4 border-b border-slate-800/80 pb-6">
                <div>
                    <div class="inline-flex items-center gap-2 font-mono text-xs uppercase tracking-widest text-accent mb-2">
                        <i class="fa-solid fa-satellite-dish"></i>
                        <span>04 // MULTI-PLATFORM NETWORK & DIRECT LINKS</span>
                    </div>
                    <h2 class="text-3xl sm:text-4xl font-extrabold tracking-tight text-white">
                        Socials & Creator Hub
                    </h2>
                </div>
                <div class="flex items-center gap-3">
                    <button onclick="copyLinktreeUrl()" class="btn-outline-glow px-4 py-2 rounded-xl font-mono text-xs flex items-center gap-2">
                        <i class="fa-regular fa-copy text-accent"></i>
                        <span>Copy Linktree URL</span>
                    </button>
                </div>
            </div>

            <!-- 9 Verified Social Cards Grid -->
            <div id="socials-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-5">
                <!-- Populated via JS with all 9 exact links and target="_blank" -->
            </div>
        </section>

    </main>

    <!-- ==========================================
         CUSTOM TOAST NOTIFICATION (NO ALERT)
         ========================================== -->
    <div id="toast-notification" class="fixed bottom-6 right-6 z-50 pointer-events-none opacity-0 translate-y-4 transition-all duration-300">
        <div class="glass-static px-5 py-3.5 rounded-2xl border border-accent shadow-2xl flex items-center gap-3">
            <span id="toast-icon" class="text-lg">✨</span>
            <div>
                <div id="toast-title" class="text-xs font-mono font-bold text-accent uppercase">System Notification</div>
                <div id="toast-message" class="text-sm font-medium text-white">Action completed!</div>
            </div>
        </div>
    </div>

    <!-- ==========================================
         FOOTER
         ========================================== -->
    <footer class="relative z-10 border-t border-slate-800/80 bg-slate-950/90 py-10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col sm:flex-row items-center justify-between gap-4 text-xs font-mono text-slate-400">
            <div class="flex items-center gap-2">
                <span class="w-2 h-2 rounded-full bg-accent"></span>
                <span>© 2026 <strong class="text-white">MrBoss</strong> (MrBoss1017). All rights reserved.</span>
            </div>
            <div class="flex flex-wrap items-center gap-4">
                <a href="#hero" class="hover:text-white transition">Back to Top ↑</a>
            </div>
        </div>
    </footer>

    <!-- ==========================================
         APPLICATION JAVASCRIPT & DATA ENGINE
         ========================================== -->
    <script>
        // ==========================================
        // 1. PORTFOLIO DATA DEFINITIONS
        // ==========================================
        let currentProjectFilter = 'all';
        let commandHistory = [];
        let historyIndex = -1;

        const projectsData = [
            {
                id: 'ruby-mod',
                title: 'Ruby Mod',
                category: 'Minecraft Mod',
                platformLabel: 'GitHub Repository',
                icon: 'fa-brands fa-github',
                url: 'https://github.com/MrBoss1017/Ruby-Mod'
            },
            {
                id: 'nexus',
                title: 'NEXUS',
                category: 'Minecraft Mod',
                platformLabel: 'GitHub Repository',
                icon: 'fa-brands fa-github',
                url: 'https://github.com/MrBoss1017/NEXUS'
            },
            {
                id: 'the-time-game',
                title: 'The Time Game',
                category: 'Roblox Game',
                platformLabel: 'Roblox Experience',
                icon: 'fa-solid fa-gamepad',
                url: 'https://www.roblox.com/games/116685161437597/The-Time-Game'
            },
            {
                id: 'npc-waves-test',
                title: 'Npc Waves Test',
                category: 'Roblox Game',
                platformLabel: 'Roblox Experience',
                icon: 'fa-solid fa-gamepad',
                url: 'https://www.roblox.com/games/90885143205549/Npc-Waves-Test'
            }
        ];

        const languagesData = [
            { name: 'Luau', icon: 'fa-solid fa-bolt' },
            { name: 'Java', icon: 'fa-brands fa-java' },
            { name: 'JavaScript', icon: 'fa-brands fa-js' },
            { name: 'HTML5', icon: 'fa-brands fa-html5' },
            { name: 'CSS3', icon: 'fa-brands fa-css3-alt' },
            { name: 'Python', icon: 'fa-brands fa-python' }
        ];

        const toolsData = [
            { name: 'Roblox Studio', icon: 'fa-solid fa-cubes-stacked' },
            { name: 'Visual Studio Code', icon: 'fa-solid fa-laptop-code' },
            { name: 'Autodesk Fusion 360', icon: 'fa-solid fa-compass-drafting' },
            { name: 'Git / GitHub', icon: 'fa-brands fa-git-alt' },
            { name: 'OBS Studio', icon: 'fa-solid fa-video' },
            { name: 'Premiere Pro', icon: 'fa-solid fa-film' },
            { name: 'Photoshop', icon: 'fa-solid fa-image' }
        ];

        const gamesRotationData = [
            { title: 'Minecraft', platform: 'PC', icon: 'fa-solid fa-cube' },
            { title: 'Roblox', platform: 'PC', icon: 'fa-solid fa-gamepad' },
            { title: 'Fortnite', platform: 'PC', icon: 'fa-solid fa-crosshairs' },
            { title: 'Counter-Strike 2', platform: 'PC', icon: 'fa-solid fa-shield' },
            { title: 'BeamNG.drive', platform: 'PC', icon: 'fa-solid fa-car-burst' },
            { title: 'Grand Theft Auto V', platform: 'PC', icon: 'fa-solid fa-city' },
            { title: 'A BRAZILIAN BOOMER SHOOTER GAME MADE USING THE ID TECH 2 ENGINE! SHOOT, JUMP, EMBARK ON A JOURNEY THROUGHOUT THE STATE OF RIO DE JANEIRO, HELL AND EVEN HEAVEN! SAVE BRAZIL!', platform: 'PC', icon: 'fa-solid fa-fire' },
            { title: "Garry's Mod", platform: 'PC', icon: 'fa-solid fa-screwdriver-wrench' },
            { title: 'NBA 2K', platform: 'PC', icon: 'fa-solid fa-basketball' },
            { title: 'Undertale', platform: 'PC', icon: 'fa-solid fa-heart' },
            { title: 'Rainbow Six Siege', platform: 'PC', icon: 'fa-solid fa-user-shield' },
            { title: 'Geometry Dash', platform: 'PC', icon: 'fa-solid fa-shapes' },
            { title: 'Deadlock', platform: 'PC', icon: 'fa-solid fa-bolt' },
            { title: 'Apex Legends', platform: 'PC', icon: 'fa-solid fa-parachute-box' },
            { title: "Marvel's Spider-Man 2", platform: 'PS5', icon: 'fa-solid fa-spider' },
            { title: 'Astro Bot', platform: 'PS5', icon: 'fa-solid fa-robot' },
            { title: 'Call of Duty', platform: 'PS5', icon: 'fa-solid fa-skull' },
            { title: 'War Thunder', platform: 'PS5', icon: 'fa-solid fa-jet-fighter' },
            { title: 'The Last of Us Remastered (2018)', platform: 'PS4', icon: 'fa-solid fa-leaf' },
            { title: 'God of War (2018)', platform: 'PS4', icon: 'fa-solid fa-khanda' },
            { title: 'God of War III', platform: 'RPCS3', icon: 'fa-solid fa-khanda' }
        ];

        const socialsData = [
            {
                name: 'Linktree',
                handle: '@MrBoss1017',
                desc: 'All-in-one creator directory & rapid links',
                url: 'https://linktr.ee/MrBoss1017',
                icon: 'fa-solid fa-link',
                badge: 'CENTRAL HUB',
                accentClass: 'hover:border-emerald-400/60'
            },
            {
                name: 'GitHub',
                handle: 'github.com/MrBoss1017',
                desc: 'Ruby Mod, NEXUS & open-source repositories',
                url: 'https://github.com/MrBoss1017',
                icon: 'fa-brands fa-github',
                badge: 'CODE REPOS',
                accentClass: 'hover:border-cyan-400/60'
            },
            {
                name: 'YouTube',
                handle: '@mr.ceoman',
                desc: 'Devlogs, gameplay showcases & tech videos',
                url: 'https://www.youtube.com/@mr.ceoman',
                icon: 'fa-brands fa-youtube',
                badge: 'VIDEO & STREAM',
                accentClass: 'hover:border-rose-500/60'
            },
            {
                name: 'Twitch',
                handle: 'twitch.tv/mrboss1017',
                desc: 'Live coding, Multi-RTMP gaming & community',
                url: 'https://www.twitch.tv/mrboss1017',
                icon: 'fa-brands fa-twitch',
                badge: 'LIVE STREAM',
                accentClass: 'hover:border-purple-400/60'
            },
            {
                name: 'Steam',
                handle: 'id/MrBoss1017',
                desc: 'PC library, CS2, BeamNG.drive & achievements',
                url: 'https://steamcommunity.com/id/MrBoss1017/',
                icon: 'fa-brands fa-steam',
                badge: 'PC GAMING',
                accentClass: 'hover:border-sky-400/60'
            },
            {
                name: 'Roblox',
                handle: 'User #1186485535',
                desc: 'The Time Game & Npc Waves Test creator profile',
                url: 'https://www.roblox.com/users/1186485535/profile',
                icon: 'fa-solid fa-cubes',
                badge: 'LUAU DEV',
                accentClass: 'hover:border-red-400/60'
            },
            {
                name: 'X (Twitter)',
                handle: '@Mrceoman10171',
                desc: 'Real-time updates, patch notes & announcements',
                url: 'https://x.com/Mrceoman10171',
                icon: 'fa-brands fa-x-twitter',
                badge: 'UPDATES',
                accentClass: 'hover:border-slate-300/60'
            },
            {
                name: 'Spotify',
                handle: 'MrBoss Official Playlists',
                desc: 'Coding focus, synthwave & late-night gaming mixes',
                url: 'https://open.spotify.com/user/31fhno52c732dlwymxkxrksqoza4',
                icon: 'fa-brands fa-spotify',
                badge: 'AUDIO VIBE',
                accentClass: 'hover:border-green-400/60'
            },
            {
                name: 'Pinterest',
                handle: '@MrBossGaming1017',
                desc: 'Setup inspiration, UI boards & gaming aesthetics',
                url: 'https://ca.pinterest.com/MrBossGaming1017/?invite_code=9f03ba7e1adc47f9a738d6a7e50b840a&sender=987344055715522372',
                icon: 'fa-brands fa-pinterest',
                badge: 'DESIGN BOARDS',
                accentClass: 'hover:border-pink-400/60'
            }
        ];

        // ==========================================
        // 2. INTERACTIVE MINI TERMINAL ENGINE
        // ==========================================
        function initTerminal() {
            const output = document.getElementById('terminal-output');
            output.innerHTML = `
                <div class="text-slate-400">
                    <span class="text-emerald-400 font-bold">✔</span> Booting <span class="text-white font-bold">MrBoss</span> Interactive Shell v2.6.0...
                </div>
                <div class="text-slate-300">
                    Type <span class="text-accent font-semibold">'help'</span> or click a quick command above to inspect projects, PC specs, socials, or games.
                </div>
            `;
        }

        function focusTerminal() {
            const input = document.getElementById('terminal-input');
            if (input) input.focus();
        }

        function appendTerminalBlock(commandText, responseHTML) {
            const output = document.getElementById('terminal-output');
            const promptUser = 'mrboss@hub:~$';

            const block = document.createElement('div');
            block.className = 'space-y-1.5 pt-1 border-t border-slate-800/50';
            block.innerHTML = `
                <div class="flex items-center gap-2">
                    <span class="text-accent font-bold">${promptUser}</span>
                    <span class="text-white font-semibold">${escapeHtml(commandText)}</span>
                </div>
                <div class="text-slate-300 pl-2 border-l-2 border-slate-700/80 space-y-1">
                    ${responseHTML}
                </div>
            `;
            output.appendChild(block);
            output.scrollTop = output.scrollHeight;
        }

        function escapeHtml(str) {
            return str.replace(/[&<>"']/g, function(m) {
                return ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', '"': '&quot;', "'": '&#039;' })[m];
            });
        }

        function handleTerminalSubmit(e) {
            e.preventDefault();
            const input = document.getElementById('terminal-input');
            const rawCmd = input.value.trim();
            if (!rawCmd) return;

            commandHistory.unshift(rawCmd);
            historyIndex = -1;
            input.value = '';
            runTerminalCommand(rawCmd);
        }

        function runTerminalCommand(rawCmd) {
            const cmd = rawCmd.toLowerCase().trim();

            if (cmd === 'clear' || cmd === 'cls') {
                initTerminal();
                return;
            }

            let response = '';
            switch (cmd) {
                case 'help':
                    response = `
                        <div class="text-white font-bold">Available System Commands:</div>
                        <div><span class="text-accent font-semibold w-20 inline-block">projects</span> → List featured GitHub & Roblox projects</div>
                        <div><span class="text-accent font-semibold w-20 inline-block">specs</span> → Inspect Lenovo Legion 5i Gen 8 + PS5 Pro hardware</div>
                        <div><span class="text-accent font-semibold w-20 inline-block">socials</span> → Print verified creator & developer links</div>
                        <div><span class="text-accent font-semibold w-20 inline-block">games</span> → Show active rotation games</div>
                        <div><span class="text-slate-400 font-semibold w-20 inline-block">neofetch</span> → Display system summary</div>
                        <div><span class="text-slate-400 font-semibold w-20 inline-block">clear</span> → Reset terminal buffer</div>
                    `;
                    break;

                case 'projects':
                    response = `
                        <div class="text-white font-bold">Featured Projects:</div>
                        <div>1. <a href="https://github.com/MrBoss1017/Ruby-Mod" target="_blank" rel="noopener noreferrer" class="text-accent font-semibold hover:underline">Ruby Mod ↗</a> — https://github.com/MrBoss1017/Ruby-Mod</div>
                        <div>2. <a href="https://github.com/MrBoss1017/NEXUS" target="_blank" rel="noopener noreferrer" class="text-accent font-semibold hover:underline">NEXUS ↗</a> — https://github.com/MrBoss1017/NEXUS</div>
                        <div>3. <a href="https://www.roblox.com/games/116685161437597/The-Time-Game" target="_blank" rel="noopener noreferrer" class="text-accent font-semibold hover:underline">The Time Game ↗</a> — https://www.roblox.com/games/116685161437597/The-Time-Game</div>
                        <div>4. <a href="https://www.roblox.com/games/90885143205549/Npc-Waves-Test" target="_blank" rel="noopener noreferrer" class="text-accent font-semibold hover:underline">Npc Waves Test ↗</a> — https://www.roblox.com/games/90885143205549/Npc-Waves-Test</div>
                        <div class="pt-1"><a href="#projects" class="text-emerald-400 underline">↓ Jump to Interactive Portfolio Grid</a></div>
                    `;
                    break;

                case 'specs':
                    response = `
                        <div class="text-white font-bold">Lenovo Legion Tower 5i Gen 8 Specs:</div>
                        <div>• <span class="text-accent">CPU:</span> Intel i5-14400F (2.50 GHz Base / 4.00 GHz Avg)</div>
                        <div>• <span class="text-accent">GPU:</span> NVIDIA GeForce RTX 4060 8GB VRAM</div>
                        <div>• <span class="text-accent">RAM:</span> 32GB DDR5 @ 4400 MT/s</div>
                        <div>• <span class="text-accent">Storage:</span> 1TB NVMe M.2</div>
                        <div>• <span class="text-accent">Network:</span> 2 Ethernet Cables + Wi-Fi</div>
                        <div>• <span class="text-accent">Console:</span> PlayStation 5 Pro + Physical Disc Drive & RPCS3</div>
                    `;
                    break;

                case 'socials':
                    response = `
                        <div class="text-white font-bold">Verified Creator & Dev Links (Click to Open):</div>
                        <div class="grid grid-cols-2 gap-1 pt-1">
                            <a href="https://linktr.ee/MrBoss1017" target="_blank" rel="noopener noreferrer" class="text-accent hover:underline">↗ Linktree</a>
                            <a href="https://github.com/MrBoss1017" target="_blank" rel="noopener noreferrer" class="text-accent hover:underline">↗ GitHub</a>
                            <a href="https://www.youtube.com/@mr.ceoman" target="_blank" rel="noopener noreferrer" class="text-accent hover:underline">↗ YouTube</a>
                            <a href="https://www.twitch.tv/mrboss1017" target="_blank" rel="noopener noreferrer" class="text-accent hover:underline">↗ Twitch</a>
                            <a href="https://steamcommunity.com/id/MrBoss1017/" target="_blank" rel="noopener noreferrer" class="text-accent hover:underline">↗ Steam</a>
                            <a href="https://www.roblox.com/users/1186485535/profile" target="_blank" rel="noopener noreferrer" class="text-accent hover:underline">↗ Roblox</a>
                        </div>
                    `;
                    break;

                case 'games':
                    response = `
                        <div class="text-white font-bold">Top Rotation Games Library (21):</div>
                        <div><span class="text-accent">[PC]</span> Minecraft, Roblox, Fortnite, Counter-Strike 2, BeamNG.drive, GTA V, Brazilian Boomer Shooter (id Tech 2), Garry's Mod, NBA 2K, Undertale, Rainbow Six Siege, Geometry Dash, Deadlock, Apex Legends</div>
                        <div><span class="text-purple-400">[PS5]</span> Marvel's Spider-Man 2, Astro Bot, Call of Duty, War Thunder</div>
                        <div><span class="text-indigo-400">[PS4]</span> The Last of Us Remastered (2018), God of War (2018)</div>
                        <div><span class="text-emerald-400">[RPCS3]</span> God of War III</div>
                    `;
                    break;

                case 'whoami':
                case 'neofetch':
                    response = `
                        <div class="text-accent font-bold">MrBoss (MrBoss1017)</div>
                        <div>Role: Game Developer, Mod Creator, FTC Robotics Programmer & Streamer</div>
                        <div>Stack: Luau, Java, JS, HTML5, CSS3, Python | Roblox Studio, VS Code, Fusion 360, Premiere Pro, Photoshop</div>
                    `;
                    break;

                default:
                    response = `
                        <div class="text-rose-400">Command not recognized: <span class="font-bold">'${escapeHtml(rawCmd)}'</span></div>
                        <div>Type <span class="text-accent font-bold">'help'</span> to view available system commands.</div>
                    `;
            }

            appendTerminalBlock(rawCmd, response);
        }

        // Up/Down arrow history support in terminal input
        document.addEventListener('DOMContentLoaded', () => {
            const input = document.getElementById('terminal-input');
            input.addEventListener('keydown', (e) => {
                if (e.key === 'ArrowUp') {
                    e.preventDefault();
                    if (historyIndex < commandHistory.length - 1) {
                        historyIndex++;
                        input.value = commandHistory[historyIndex];
                    }
                } else if (e.key === 'ArrowDown') {
                    e.preventDefault();
                    if (historyIndex > 0) {
                        historyIndex--;
                        input.value = commandHistory[historyIndex];
                    } else {
                        historyIndex = -1;
                        input.value = '';
                    }
                }
            });
        });

        // ==========================================
        // 3. RENDER FEATURED PROJECTS & FILTERING
        // ==========================================
        function renderProjects(filter = 'all') {
            currentProjectFilter = filter;
            const grid = document.getElementById('projects-grid');
            const filtered = filter === 'all'
                ? projectsData
                : projectsData.filter(p => p.category === filter);

            grid.innerHTML = filtered.map(proj => `
                <a href="${proj.url}" target="_blank" rel="noopener noreferrer"
                   class="glass-card rounded-2xl p-6 flex flex-col justify-between space-y-6 relative group">
                    <div class="space-y-4">
                        <div class="flex items-center justify-between gap-2">
                            <span class="px-3 py-1 rounded-full text-[11px] font-mono font-bold tracking-wider uppercase" style="background: var(--badge-bg); color: var(--accent-primary);">
                                ${proj.category}
                            </span>
                            <span class="font-mono text-xs text-slate-400">${proj.platformLabel}</span>
                        </div>

                        <div class="flex items-center gap-3.5 pt-1">
                            <div class="w-11 h-11 rounded-xl bg-slate-900 border border-slate-700/80 flex items-center justify-center text-accent shrink-0 group-hover:scale-110 transition-transform">
                                <i class="${proj.icon} text-lg"></i>
                            </div>
                            <h3 class="text-xl font-extrabold text-white group-hover:text-accent transition-colors leading-snug">
                                ${proj.title}
                            </h3>
                        </div>
                    </div>

                    <div class="pt-4 border-t border-slate-800/80 flex items-center justify-between">
                        <span class="font-mono text-xs text-accent font-bold group-hover:underline">Open Project</span>
                        <div class="w-8 h-8 rounded-lg bg-slate-900 border border-slate-800 flex items-center justify-center text-slate-400 group-hover:text-white group-hover:border-accent transition-all">
                            <i class="fa-solid fa-arrow-up-right-from-square text-xs"></i>
                        </div>
                    </div>
                </a>
            `).join('');
        }

        function filterProjects(category) {
            document.querySelectorAll('#projects .filter-btn').forEach(btn => {
                if (btn.getAttribute('data-filter') === category) {
                    btn.classList.add('active');
                } else {
                    btn.classList.remove('active');
                }
            });
            renderProjects(category);
        }

        // ==========================================
        // 4. RENDER SKILLS (TITLES ONLY, NO DESCRIPTIONS)
        // ==========================================
        function renderSkills() {
            const langGrid = document.getElementById('languages-grid');
            langGrid.innerHTML = languagesData.map(lang => `
                <div class="p-4 rounded-xl bg-slate-900/85 border border-slate-800 hover:border-accent transition-all group flex items-center gap-3.5">
                    <div class="w-9 h-9 rounded-lg bg-slate-950 border border-slate-800 flex items-center justify-center text-accent shrink-0 group-hover:scale-110 transition-transform">
                        <i class="${lang.icon} text-base"></i>
                    </div>
                    <span class="font-bold text-white text-base group-hover:text-accent transition-colors">${lang.name}</span>
                </div>
            `).join('');

            const toolsGrid = document.getElementById('tools-grid');
            toolsGrid.innerHTML = toolsData.map(tool => `
                <div class="p-4 rounded-xl bg-slate-900/85 border border-slate-800 hover:border-accent transition-all group flex items-center gap-3.5">
                    <div class="w-9 h-9 rounded-lg bg-slate-950 border border-slate-800 flex items-center justify-center text-accent shrink-0 group-hover:scale-110 transition-transform">
                        <i class="${tool.icon} text-base"></i>
                    </div>
                    <span class="font-bold text-white text-sm sm:text-base group-hover:text-accent transition-colors">${tool.name}</span>
                </div>
            `).join('');
        }

        // ==========================================
        // 5. HARDWARE RIG TABS & GAMES (NO DESCRIPTIONS)
        // ==========================================
        function switchCommandTab(tab) {
            document.querySelectorAll('.hw-tab').forEach(b => b.classList.remove('active'));
            document.getElementById(`hw-tab-${tab}`).classList.add('active');

            const rowMachines = document.getElementById('hw-row-machines');
            const panelPc = document.getElementById('hw-panel-pc');
            const panelConsole = document.getElementById('hw-panel-console');
            const panelGames = document.getElementById('hw-panel-games');

            if (tab === 'all') {
                rowMachines.classList.remove('hidden');
                panelPc.classList.remove('hidden');
                panelConsole.classList.remove('hidden');
                panelGames.classList.remove('hidden');
                panelPc.className = 'lg:col-span-7 glass-static rounded-2xl p-6 sm:p-8 space-y-6 relative overflow-hidden';
                panelConsole.className = 'lg:col-span-5 glass-static rounded-2xl p-6 sm:p-8 flex flex-col justify-between space-y-6';
            } else if (tab === 'pc') {
                rowMachines.classList.remove('hidden');
                panelPc.classList.remove('hidden');
                panelConsole.classList.add('hidden');
                panelGames.classList.add('hidden');
                panelPc.className = 'lg:col-span-12 glass-static rounded-2xl p-6 sm:p-8 space-y-6 relative overflow-hidden';
            } else if (tab === 'console') {
                rowMachines.classList.remove('hidden');
                panelPc.classList.add('hidden');
                panelConsole.classList.remove('hidden');
                panelGames.classList.add('hidden');
                panelConsole.className = 'lg:col-span-12 glass-static rounded-2xl p-6 sm:p-8 flex flex-col justify-between space-y-6';
            } else if (tab === 'games') {
                rowMachines.classList.add('hidden');
                panelGames.classList.remove('hidden');
            }
        }

        function renderGames(platformFilter = 'all') {
            const grid = document.getElementById('games-rotation-grid');
            const filtered = platformFilter === 'all'
                ? gamesRotationData
                : gamesRotationData.filter(g => g.platform === platformFilter);

            grid.innerHTML = filtered.map(game => `
                <div class="glass-card rounded-xl p-4 flex items-center justify-between gap-3 group">
                    <div class="flex items-center gap-3 min-w-0">
                        <div class="w-9 h-9 rounded-lg bg-slate-900 border border-slate-700/80 flex items-center justify-center text-accent shrink-0 group-hover:scale-110 transition-transform">
                            <i class="${game.icon}"></i>
                        </div>
                        <h4 class="font-bold text-white text-xs sm:text-sm leading-snug group-hover:text-accent transition-colors break-words">${game.title}</h4>
                    </div>
                    <span class="px-2.5 py-1 rounded font-mono text-[10px] font-bold bg-slate-900 text-slate-300 border border-slate-700 shrink-0">
                        ${game.platform}
                    </span>
                </div>
            `).join('');
        }

        function filterGames(platform) {
            document.querySelectorAll('.game-filter-btn').forEach(btn => {
                if (btn.getAttribute('data-game-filter') === platform) {
                    btn.classList.add('active');
                } else {
                    btn.classList.remove('active');
                }
            });
            renderGames(platform);
        }

        // ==========================================
        // 6. RENDER SOCIALS & CREATOR HUB
        // ==========================================
        function renderSocials() {
            const grid = document.getElementById('socials-grid');
            grid.innerHTML = socialsData.map(soc => `
                <a href="${soc.url}" target="_blank" rel="noopener noreferrer"
                   class="glass-card rounded-2xl p-5 flex items-start justify-between gap-4 group ${soc.accentClass}">
                    <div class="flex items-start gap-4 min-w-0">
                        <div class="w-12 h-12 rounded-xl bg-slate-900 border border-slate-700/80 flex items-center justify-center text-xl text-accent shrink-0 group-hover:scale-110 transition-transform">
                            <i class="${soc.icon}"></i>
                        </div>
                        <div class="min-w-0 space-y-1">
                            <div class="flex items-center gap-2">
                                <h3 class="font-extrabold text-white text-base group-hover:text-accent transition-colors">${soc.name}</h3>
                                <span class="text-[10px] font-mono px-2 py-0.5 rounded bg-slate-900 text-slate-400 border border-slate-800">
                                    ${soc.badge}
                                </span>
                            </div>
                            <div class="font-mono text-xs text-accent truncate">${soc.handle}</div>
                            <p class="text-xs text-slate-400 line-clamp-1">${soc.desc}</p>
                        </div>
                    </div>
                    <div class="w-8 h-8 rounded-lg bg-slate-900/90 border border-slate-800 flex items-center justify-center text-slate-400 group-hover:text-white group-hover:translate-x-0.5 group-hover:-translate-y-0.5 transition-all shrink-0">
                        <i class="fa-solid fa-arrow-up-right-from-square text-xs"></i>
                    </div>
                </a>
            `).join('');
        }

        // ==========================================
        // 7. CLIPBOARD & TOAST UTILITIES
        // ==========================================
        function copyLinktreeUrl() {
            const url = 'https://linktr.ee/MrBoss1017';
            const tempInput = document.createElement('textarea');
            tempInput.value = url;
            document.body.appendChild(tempInput);
            tempInput.select();
            document.execCommand('copy');
            document.body.removeChild(tempInput);

            showToast('🔗', 'Link Copied to Clipboard', 'https://linktr.ee/MrBoss1017 ready to share!');
        }

        let toastTimeout;
        function showToast(icon, title, message) {
            const toast = document.getElementById('toast-notification');
            document.getElementById('toast-icon').textContent = icon;
            document.getElementById('toast-title').textContent = title;
            document.getElementById('toast-message').textContent = message;

            toast.classList.remove('opacity-0', 'translate-y-4');
            toast.classList.add('opacity-100', 'translate-y-0');

            clearTimeout(toastTimeout);
            toastTimeout = setTimeout(() => {
                toast.classList.add('opacity-0', 'translate-y-4');
                toast.classList.remove('opacity-100', 'translate-y-0');
            }, 3400);
        }

        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            const icon = document.getElementById('mobile-menu-icon');
            menu.classList.toggle('hidden');
            icon.className = menu.classList.contains('hidden')
                ? 'fa-solid fa-bars text-lg'
                : 'fa-solid fa-xmark text-lg';
        }

        // ==========================================
        // 8. AMBIENT CYBER PARTICLE CANVAS
        // ==========================================
        function initParticles() {
            const canvas = document.getElementById('bg-canvas');
            const ctx = canvas.getContext('2d');
            let width, height;
            let particles = [];

            function resize() {
                width = canvas.width = window.innerWidth;
                height = canvas.height = window.innerHeight;
            }
            window.addEventListener('resize', resize);
            resize();

            const count = Math.min(45, Math.floor(window.innerWidth / 32));
            for (let i = 0; i < count; i++) {
                particles.push({
                    x: Math.random() * width,
                    y: Math.random() * height,
                    r: Math.random() * 2.2 + 0.8,
                    vx: (Math.random() - 0.5) * 0.45,
                    vy: (Math.random() - 0.5) * 0.45,
                    alpha: Math.random() * 0.55 + 0.15
                });
            }

            function animateParticles() {
                ctx.clearRect(0, 0, width, height);
                const primaryColor = '0, 242, 254';
                const secondaryColor = '124, 58, 237';

                for (let i = 0; i < particles.length; i++) {
                    const p = particles[i];
                    p.x += p.vx;
                    p.y += p.vy;

                    if (p.x < 0) p.x = width;
                    if (p.x > width) p.x = 0;
                    if (p.y < 0) p.y = height;
                    if (p.y > height) p.y = 0;

                    ctx.beginPath();
                    ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
                    ctx.fillStyle = `rgba(${i % 2 === 0 ? primaryColor : secondaryColor}, ${p.alpha})`;
                    ctx.fill();
                }

                requestAnimationFrame(animateParticles);
            }
            animateParticles();
        }

        // ==========================================
        // 9. INITIALIZE ON WINDOW LOAD
        // ==========================================
        window.onload = function () {
            initTerminal();
            renderProjects('all');
            renderSkills();
            renderGames('all');
            renderSocials();
            initParticles();
        };
    </script>
</body>
</html>
