<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pollution and the Environment | Ahmed Jaballah 9B2</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Nunito', sans-serif; }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 500px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 350px;
        }
        .active-tab {
            background-color: #0d9488;
            color: white;
            border-color: #0d9488;
        }
        .tab-btn {
            transition: all 0.3s ease;
        }
        .fade-in {
            animation: fadeIn 0.5s ease-in;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body class="bg-stone-50 text-stone-800 antialiased selection:bg-teal-200 selection:text-teal-900">

    <!-- Chosen Palette: Earthy & Educational - Stone (Background), Teal (Primary/Nature), Amber (Warning/Pollution), Slate (Text) -->
    <!-- Application Structure Plan: 
         1. Hero Header: Contextualizes the project (Student Name, Class).
         2. "The Basics": Quick definition and global context.
         3. "Pollution Types Explorer": Central interactive hub. Users click tabs (Air, Water, etc.) to toggle content and specific educational charts.
         4. "Tunisia Context": specific section for local relevance using card grids.
         5. "Impact & Solutions": Split view for negative effects vs. positive actions.
         6. "Knowledge Check": Interactive Quiz and Glossary.
         Rationale: This structure breaks the linear report into bite-sized, explorable chunks, making it engaging for 9th graders. -->
    <!-- Visualization & Content Choices: 
         1. Donut Charts (Types Explorer): To visually represent the "Causes" of each pollution type. Goal: Inform/Organize.
         2. Interactive Tabs: To reduce cognitive load, showing only one pollution type at a time.
         3. Quiz Module: To gamify the "Revision" requirement.
         4. Solution Accordions: To organize the "What can we do" lists cleanly.
         5. Unicode Icons: Used throughout for visual cues without external image dependencies (NO SVG). -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->

    <!-- Navigation -->
    <nav class="sticky top-0 z-50 bg-white/90 backdrop-blur-md border-b border-stone-200 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16 items-center">
                <div class="flex items-center gap-2">
                    <span class="text-2xl">🌍</span>
                    <span class="font-bold text-xl tracking-tight text-teal-800">EcoProject 9B2</span>
                </div>
                <div class="hidden md:flex space-x-8">
                    <button onclick="scrollToSection('home')" class="text-stone-600 hover:text-teal-600 font-medium">Home</button>
                    <button onclick="scrollToSection('types')" class="text-stone-600 hover:text-teal-600 font-medium">Types</button>
                    <button onclick="scrollToSection('tunisia')" class="text-stone-600 hover:text-teal-600 font-medium">Tunisia</button>
                    <button onclick="scrollToSection('solutions')" class="text-stone-600 hover:text-teal-600 font-medium">Solutions</button>
                    <button onclick="scrollToSection('quiz')" class="text-stone-600 hover:text-teal-600 font-medium">Quiz</button>
                </div>
                <button onclick="toggleMobileMenu()" class="md:hidden text-2xl text-stone-600">☰</button>
            </div>
        </div>
        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-white border-t border-stone-100 p-4 space-y-3 shadow-lg">
            <button onclick="scrollToSection('home')" class="block w-full text-left text-stone-600 font-medium p-2 hover:bg-teal-50 rounded">Home</button>
            <button onclick="scrollToSection('types')" class="block w-full text-left text-stone-600 font-medium p-2 hover:bg-teal-50 rounded">Types</button>
            <button onclick="scrollToSection('tunisia')" class="block w-full text-left text-stone-600 font-medium p-2 hover:bg-teal-50 rounded">Tunisia</button>
            <button onclick="scrollToSection('solutions')" class="block w-full text-left text-stone-600 font-medium p-2 hover:bg-teal-50 rounded">Solutions</button>
            <button onclick="scrollToSection('quiz')" class="block w-full text-left text-stone-600 font-medium p-2 hover:bg-teal-50 rounded">Quiz</button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="relative bg-gradient-to-br from-teal-50 to-stone-100 pt-12 pb-20">
        <div class="max-w-5xl mx-auto px-4 text-center">
            <div class="inline-block p-2 px-4 bg-teal-100 text-teal-800 rounded-full text-sm font-bold mb-6 shadow-sm">
                School Year 2025–2026
            </div>
            <h1 class="text-4xl md:text-6xl font-extrabold text-stone-800 mb-4 tracking-tight">
                Pollution and the <span class="text-teal-600">Environment</span>
            </h1>
            <p class="text-lg md:text-xl text-stone-600 mb-8 max-w-2xl mx-auto">
                A comprehensive study on the challenges facing our planet and local communities.
            </p>
            
            <div class="bg-white p-6 rounded-2xl shadow-xl max-w-md mx-auto transform hover:-translate-y-1 transition-transform duration-300 border border-stone-100">
                <h3 class="text-stone-400 text-xs font-bold uppercase tracking-wider mb-2">Project Prepared By</h3>
                <div class="text-2xl font-bold text-stone-800">Ahmed Jaballah</div>
                <div class="flex justify-center gap-4 mt-2 text-stone-500 font-medium">
                    <span>Class: <span class="text-teal-600">9B2</span></span>
                    <span>•</span>
                    <span>Tunisia</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Introduction -->
    <section class="py-16 bg-white">
        <div class="max-w-4xl mx-auto px-4">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-stone-800">What is the Problem?</h2>
                <div class="h-1 w-20 bg-teal-500 mx-auto mt-4 rounded-full"></div>
            </div>
            
            <div class="grid md:grid-cols-2 gap-8 items-center">
                <div class="bg-stone-50 p-8 rounded-2xl border-l-4 border-teal-500 shadow-sm">
                    <h3 class="text-xl font-bold mb-3 flex items-center gap-2">
                        <span>📖</span> Definition
                    </h3>
                    <p class="text-stone-700 leading-relaxed">
                        <strong>Pollution</strong> is the introduction of harmful materials into the environment. These harmful materials are called <em class="text-teal-700 font-semibold">pollutants</em>. They can be natural, such as volcanic ash, but most are created by human activity, such as trash or runoff produced by factories.
                    </p>
                </div>
                <div>
                    <h3 class="text-xl font-bold mb-4 text-stone-800">Why is it a Global Crisis?</h3>
                    <ul class="space-y-3">
                        <li class="flex items-start gap-3">
                            <span class="text-red-500 bg-red-100 rounded-full p-1 text-xs mt-1">⚠️</span>
                            <span class="text-stone-600">It damages the quality of air, water, and land we need to survive.</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <span class="text-red-500 bg-red-100 rounded-full p-1 text-xs mt-1">⚠️</span>
                            <span class="text-stone-600">It causes global warming and climate change.</span>
                        </li>
                        <li class="flex items-start gap-3">
                            <span class="text-red-500 bg-red-100 rounded-full p-1 text-xs mt-1">⚠️</span>
                            <span class="text-stone-600">It harms human health and leads to the extinction of animal species.</span>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Interactive Types Explorer -->
    <section id="types" class="py-16 bg-stone-50">
        <div class="max-w-6xl mx-auto px-4">
            <div class="mb-10 text-center">
                <h2 class="text-3xl font-bold text-stone-800">Types of Pollution</h2>
                <p class="text-stone-500 mt-2">Explore the four main types. Click the buttons below to learn more.</p>
            </div>

            <!-- Tabs -->
            <div class="flex flex-wrap justify-center gap-4 mb-8">
                <button onclick="switchTab('air')" id="tab-air" class="tab-btn active-tab px-6 py-3 rounded-xl font-bold border-2 border-stone-200 text-stone-600 hover:border-teal-500 focus:outline-none flex items-center gap-2">
                    💨 Air
                </button>
                <button onclick="switchTab('water')" id="tab-water" class="tab-btn px-6 py-3 rounded-xl font-bold border-2 border-stone-200 text-stone-600 hover:border-blue-500 focus:outline-none flex items-center gap-2">
                    💧 Water
                </button>
                <button onclick="switchTab('soil')" id="tab-soil" class="tab-btn px-6 py-3 rounded-xl font-bold border-2 border-stone-200 text-stone-600 hover:border-amber-600 focus:outline-none flex items-center gap-2">
                    🌱 Soil
                </button>
                <button onclick="switchTab('noise')" id="tab-noise" class="tab-btn px-6 py-3 rounded-xl font-bold border-2 border-stone-200 text-stone-600 hover:border-purple-500 focus:outline-none flex items-center gap-2">
                    🔊 Noise
                </button>
            </div>

            <!-- Content Area -->
            <div class="bg-white rounded-3xl shadow-xl p-6 md:p-10 transition-all duration-300 min-h-[500px]">
                <div class="grid lg:grid-cols-2 gap-10">
                    <!-- Text Content -->
                    <div id="type-content-text" class="fade-in">
                        <!-- Content injected by JS -->
                    </div>

                    <!-- Visualization -->
                    <div class="flex flex-col items-center justify-center bg-stone-50 rounded-2xl p-6">
                        <h4 class="text-sm font-bold text-stone-500 uppercase tracking-wide mb-4">Educational Data: Main Causes</h4>
                        <div class="chart-container">
                            <canvas id="typesChart"></canvas>
                        </div>
                        <p class="text-xs text-stone-400 mt-4 text-center italic">*Data values are illustrative for educational purposes.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Pollution in Tunisia -->
    <section id="tunisia" class="py-16 bg-white border-t border-stone-100">
        <div class="max-w-6xl mx-auto px-4">
            <div class="flex flex-col md:flex-row justify-between items-end mb-12">
                <div>
                    <h2 class="text-3xl font-bold text-stone-800">Pollution in Tunisia 🇹🇳</h2>
                    <p class="text-stone-500 mt-2 max-w-xl">Realistic examples of environmental challenges facing our country.</p>
                </div>
                <div class="mt-4 md:mt-0 px-4 py-2 bg-red-50 text-red-600 rounded-lg text-sm font-bold border border-red-100">
                    Local Focus
                </div>
            </div>

            <div class="grid md:grid-cols-3 gap-6">
                <!-- City Card -->
                <div class="group bg-stone-50 rounded-2xl p-6 hover:bg-stone-100 transition-colors border border-stone-100">
                    <div class="text-4xl mb-4 group-hover:scale-110 transition-transform duration-300">🏙️</div>
                    <h3 class="text-xl font-bold text-stone-800 mb-2">Big Cities</h3>
                    <p class="text-stone-600 text-sm mb-4">
                        Cities like <strong>Tunis, Sfax, and Gabes</strong> suffer from high traffic and industrial zones.
                    </p>
                    <ul class="text-sm text-stone-500 space-y-2">
                        <li>• Heavy car exhaust fumes.</li>
                        <li>• Factory smoke in industrial belts.</li>
                        <li>• Reduced air quality.</li>
                    </ul>
                </div>

                <!-- Sea Card -->
                <div class="group bg-blue-50 rounded-2xl p-6 hover:bg-blue-100 transition-colors border border-blue-100">
                    <div class="text-4xl mb-4 group-hover:scale-110 transition-transform duration-300">🏖️</div>
                    <h3 class="text-xl font-bold text-blue-900 mb-2">Sea & Beaches</h3>
                    <p class="text-blue-800 text-sm mb-4">
                        Many coastal areas face contamination from untreated wastewater and plastic dumping.
                    </p>
                    <ul class="text-sm text-blue-700 space-y-2">
                        <li>• Plastic bottles on shores.</li>
                        <li>• Industrial discharge (e.g., Phosphogypsum).</li>
                        <li>• Harm to marine life.</li>
                    </ul>
                </div>

                <!-- Waste Card -->
                <div class="group bg-amber-50 rounded-2xl p-6 hover:bg-amber-100 transition-colors border border-amber-100">
                    <div class="text-4xl mb-4 group-hover:scale-110 transition-transform duration-300">🗑️</div>
                    <h3 class="text-xl font-bold text-amber-900 mb-2">Waste Problems</h3>
                    <p class="text-amber-800 text-sm mb-4">
                        Waste management is a major challenge, leading to random landfills.
                    </p>
                    <ul class="text-sm text-amber-700 space-y-2">
                        <li>• Overflowing bins in neighborhoods.</li>
                        <li>• Plastic bags flying in fields.</li>
                        <li>• Need for better recycling.</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Effects Grid -->
    <section class="py-16 bg-stone-900 text-white">
        <div class="max-w-6xl mx-auto px-4">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold">The Effects of Pollution</h2>
                <p class="text-stone-400 mt-2">Why we must act now.</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
                <!-- Human Health -->
                <div class="bg-stone-800 p-6 rounded-xl border border-stone-700 hover:border-teal-500 transition-colors">
                    <div class="text-3xl mb-3">😷</div>
                    <h3 class="font-bold text-lg mb-2">Human Health</h3>
                    <p class="text-sm text-stone-400">Causes respiratory diseases like asthma, lung cancer, and skin irritations.</p>
                </div>
                <!-- Animals -->
                <div class="bg-stone-800 p-6 rounded-xl border border-stone-700 hover:border-teal-500 transition-colors">
                    <div class="text-3xl mb-3">🐢</div>
                    <h3 class="font-bold text-lg mb-2">Animals</h3>
                    <p class="text-sm text-stone-400">Destroys habitats. Marine animals mistake plastic for food and die.</p>
                </div>
                <!-- Plants -->
                <div class="bg-stone-800 p-6 rounded-xl border border-stone-700 hover:border-teal-500 transition-colors">
                    <div class="text-3xl mb-3">🥀</div>
                    <h3 class="font-bold text-lg mb-2">Plants</h3>
                    <p class="text-sm text-stone-400">Acid rain damages forests. Soil pollution prevents healthy growth.</p>
                </div>
                <!-- Climate -->
                <div class="bg-stone-800 p-6 rounded-xl border border-stone-700 hover:border-teal-500 transition-colors">
                    <div class="text-3xl mb-3">🌡️</div>
                    <h3 class="font-bold text-lg mb-2">Climate</h3>
                    <p class="text-sm text-stone-400">Greenhouse gases trap heat, leading to global warming and extreme weather.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Solutions -->
    <section id="solutions" class="py-16 bg-teal-50">
        <div class="max-w-5xl mx-auto px-4">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-stone-800">Solutions: We Can Fix This</h2>
                <p class="text-stone-600">Action is needed at every level.</p>
            </div>

            <div class="space-y-4">
                <!-- Individual -->
                <div class="bg-white rounded-xl shadow-sm overflow-hidden">
                    <button class="w-full px-6 py-4 text-left font-bold text-teal-800 bg-teal-100 flex justify-between items-center">
                        <span>👤 What Individuals Can Do</span>
                        <span>▼</span>
                    </button>
                    <div class="p-6 text-stone-700">
                        <ul class="list-disc pl-5 space-y-2">
                            <li><strong>Reduce, Reuse, Recycle:</strong> Don't throw away things that can be used again.</li>
                            <li><strong>Save Energy:</strong> Turn off lights when leaving a room.</li>
                            <li><strong>Use less plastic:</strong> Carry a reusable cloth bag for shopping.</li>
                            <li><strong>Plant trees:</strong> Trees clean the air.</li>
                        </ul>
                    </div>
                </div>

                <!-- Schools -->
                <div class="bg-white rounded-xl shadow-sm overflow-hidden">
                    <button class="w-full px-6 py-4 text-left font-bold text-blue-800 bg-blue-100 flex justify-between items-center">
                        <span>🏫 What Schools Can Do</span>
                        <span>▼</span>
                    </button>
                    <div class="p-6 text-stone-700">
                        <ul class="list-disc pl-5 space-y-2">
                            <li>Organize <strong>clean-up days</strong> for the school yard or nearby beach.</li>
                            <li>Create <strong>eco-clubs</strong> to teach students about the environment.</li>
                            <li>Place separate bins for paper, plastic, and general waste.</li>
                        </ul>
                    </div>
                </div>

                <!-- Government -->
                <div class="bg-white rounded-xl shadow-sm overflow-hidden">
                    <button class="w-full px-6 py-4 text-left font-bold text-stone-800 bg-stone-200 flex justify-between items-center">
                        <span>🏛️ What the Government Can Do</span>
                        <span>▼</span>
                    </button>
                    <div class="p-6 text-stone-700">
                        <ul class="list-disc pl-5 space-y-2">
                            <li>Pass strict <strong>laws</strong> against factories that pollute.</li>
                            <li>Invest in <strong>Renewable Energy</strong> (Solar and Wind power).</li>
                            <li>Improve public transport to reduce the number of cars on the road.</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Quiz & Glossary -->
    <section id="quiz" class="py-16 bg-white">
        <div class="max-w-6xl mx-auto px-4 grid lg:grid-cols-2 gap-12">
            <!-- Glossary -->
            <div>
                <h3 class="text-2xl font-bold text-stone-800 mb-6 flex items-center gap-2">
                    <span>📚</span> Glossary
                </h3>
                <div class="bg-stone-50 rounded-2xl p-6 h-96 overflow-y-auto border border-stone-100 shadow-inner">
                    <div class="space-y-4">
                        <div><span class="font-bold text-teal-700">Environment:</span> The natural world around us (air, water, land).</div>
                        <div><span class="font-bold text-teal-700">Pollutant:</span> A substance that makes something dirty or poisonous.</div>
                        <div><span class="font-bold text-teal-700">Global Warming:</span> The slow increase in the earth's temperature.</div>
                        <div><span class="font-bold text-teal-700">Contamination:</span> Making something impure or harmful.</div>
                        <div><span class="font-bold text-teal-700">Habitat:</span> The natural home of an animal or plant.</div>
                        <div><span class="font-bold text-teal-700">Renewable Energy:</span> Energy that comes from natural sources like sun or wind.</div>
                        <div><span class="font-bold text-teal-700">Recycle:</span> To convert waste into reusable material.</div>
                        <div><span class="font-bold text-teal-700">Extinction:</span> When a species of animal dies out completely.</div>
                        <div><span class="font-bold text-teal-700">Sewage:</span> Waste water and excrement conveyed in sewers.</div>
                        <div><span class="font-bold text-teal-700">Pesticides:</span> Chemicals used to kill insects on crops.</div>
                    </div>
                </div>
            </div>

            <!-- Quiz -->
            <div>
                <h3 class="text-2xl font-bold text-stone-800 mb-6 flex items-center gap-2">
                    <span>📝</span> Revision Quiz
                </h3>
                <div class="bg-teal-600 rounded-2xl p-6 text-white shadow-lg">
                    <div id="quiz-container">
                        <div class="mb-4 flex justify-between items-center">
                            <span class="text-sm font-bold opacity-80" id="question-count">Question 1/5</span>
                            <span class="text-sm font-bold bg-white/20 px-2 py-1 rounded" id="score-display">Score: 0</span>
                        </div>
                        <h4 class="text-xl font-bold mb-6" id="question-text">Loading question...</h4>
                        <div class="space-y-3" id="options-container">
                            <!-- Options injected via JS -->
                        </div>
                        <div id="feedback" class="mt-4 font-bold min-h-[24px]"></div>
                        <button id="next-btn" onclick="nextQuestion()" class="mt-4 w-full bg-white text-teal-800 font-bold py-2 rounded-lg hover:bg-teal-50 transition hidden">Next Question</button>
                    </div>
                    
                    <div id="quiz-complete" class="hidden text-center py-8">
                        <div class="text-5xl mb-4">🏆</div>
                        <h4 class="text-2xl font-bold mb-2">Quiz Complete!</h4>
                        <p class="mb-6">You scored <span id="final-score" class="font-bold text-yellow-300"></span> out of 5.</p>
                        <button onclick="resetQuiz()" class="bg-white text-teal-800 px-6 py-2 rounded-lg font-bold hover:bg-teal-50">Try Again</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Images Section -->
    <section class="py-12 bg-stone-100 text-center">
        <h3 class="text-lg font-bold text-stone-600 mb-4">Useful Image Sources</h3>
        <p class="text-sm text-stone-500 mb-6">Click to view relevant images on Wikipedia:</p>
        <div class="flex flex-wrap justify-center gap-4 text-sm">
            <a href="https://en.wikipedia.org/wiki/File:Air_pollution_in_New_Delhi.jpg" target="_blank" class="px-4 py-2 bg-white rounded shadow text-teal-600 hover:text-teal-800">📸 Air Pollution</a>
            <a href="https://en.wikipedia.org/wiki/File:Water_pollution.jpg" target="_blank" class="px-4 py-2 bg-white rounded shadow text-teal-600 hover:text-teal-800">📸 Water Pollution</a>
            <a href="https://en.wikipedia.org/wiki/File:Plastic_pollution.jpg" target="_blank" class="px-4 py-2 bg-white rounded shadow text-teal-600 hover:text-teal-800">📸 Plastic Waste</a>
            <a href="https://en.wikipedia.org/wiki/File:Factory_smoke.jpg" target="_blank" class="px-4 py-2 bg-white rounded shadow text-teal-600 hover:text-teal-800">📸 Factory Smoke</a>
        </div>
    </section>

    <!-- Conclusion Footer -->
    <footer class="bg-stone-800 text-stone-300 py-12">
        <div class="max-w-4xl mx-auto px-4 text-center">
            <h2 class="text-2xl font-bold text-white mb-4">Conclusion</h2>
            <p class="mb-6 leading-relaxed">
                Protecting the environment is not just a choice; it is a duty. We only have one planet. By understanding pollution and taking small steps in our daily lives, we can ensure a cleaner, healthier future for Tunisia and the world.
            </p>
            <div class="border-t border-stone-700 pt-8 mt-8 text-sm">
                <p>Prepared by <strong>Ahmed Jaballah</strong> • Class <strong>9B2</strong></p>
                <p class="mt-2 text-stone-500">School Year 2025–2026</p>
            </div>
        </div>
    </footer>

    <script>
        // --- Data Handling ---
        const pollutionData = {
            air: {
                title: "Air Pollution 💨",
                definition: "Contamination of the air by harmful gases, dust, and smoke.",
                causes: [
                    "Car exhausts and vehicles.",
                    "Smoke from factories and power plants.",
                    "Burning waste and wood."
                ],
                effects: [
                    "Breathing problems (Asthma).",
                    "Global Warming.",
                    "Acid Rain."
                ],
                chartLabel: "Main Sources",
                chartData: [45, 35, 20], // Illustrative
                chartLabels: ["Transport", "Industry", "Household"],
                chartColors: ['#cbd5e1', '#64748b', '#94a3b8'] // Grey/Blue scale
            },
            water: {
                title: "Water Pollution 💧",
                definition: "When harmful substances enter water bodies like rivers, lakes, and oceans.",
                causes: [
                    "Industrial waste dumped into rivers.",
                    "Sewage and wastewater leaks.",
                    "Oil spills from ships.",
                    "Plastic waste thrown on beaches."
                ],
                effects: [
                    "Death of fish and marine life.",
                    "Unsafe drinking water.",
                    "Spread of diseases like Cholera."
                ],
                chartLabel: "Main Pollutants",
                chartData: [40, 30, 20, 10],
                chartLabels: ["Sewage", "Industry", "Agri-runoff", "Oil"],
                chartColors: ['#bfdbfe', '#3b82f6', '#1d4ed8', '#1e3a8a'] // Blue scale
            },
            soil: {
                title: "Soil Pollution 🌱",
                definition: "Destruction of the earth's land surface, often caused by human activities.",
                causes: [
                    "Pesticides and chemicals used in farming.",
                    "Mining activities.",
                    "Dumping trash in landfills."
                ],
                effects: [
                    "Contaminated food crops.",
                    "Loss of fertile land for farming.",
                    "Harm to animals living underground."
                ],
                chartLabel: "Contributors",
                chartData: [50, 30, 20],
                chartLabels: ["Agriculture", "Waste Dump", "Industry"],
                chartColors: ['#d97706', '#f59e0b', '#fcd34d'] // Earth/Amber scale
            },
            noise: {
                title: "Noise Pollution 🔊",
                definition: "Harmful or annoying levels of noise.",
                causes: [
                    "Traffic and honking cars.",
                    "Construction sites.",
                    "Loud music and airplanes."
                ],
                effects: [
                    "Hearing loss.",
                    "Stress and sleep disturbance.",
                    "High blood pressure."
                ],
                chartLabel: "Noise Sources",
                chartData: [60, 25, 15],
                chartLabels: ["Traffic", "Construction", "Social"],
                chartColors: ['#a855f7', '#c084fc', '#e9d5ff'] // Purple scale
            }
        };

        const quizQuestions = [
            {
                q: "What is pollution?",
                options: ["Planting trees", "Introduction of harmful materials", "Cleaning the ocean", "Recycling paper"],
                a: 1 // Index of correct answer
            },
            {
                q: "Which is a major cause of air pollution?",
                options: ["Fish farming", "Electric cars", "Car exhaust fumes", "Solar panels"],
                a: 2
            },
            {
                q: "How does pollution affect animals?",
                options: ["It destroys their habitats", "It makes them stronger", "It gives them more food", "It has no effect"],
                a: 0
            },
            {
                q: "What is a common pollution problem in Tunisian cities?",
                options: ["Too many trees", "Traffic and factory smoke", "Clean rivers", "Silent streets"],
                a: 1
            },
            {
                q: "What can individuals do to help?",
                options: ["Burn trash", "Use more plastic", "Reduce, Reuse, Recycle", "Leave lights on"],
                a: 2
            }
        ];

        // --- State ---
        let currentChart = null;
        let currentQuizIndex = 0;
        let quizScore = 0;

        // --- Tab Logic ---
        function switchTab(type) {
            // Update UI Buttons
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.classList.remove('active-tab', 'border-teal-500', 'border-blue-500', 'border-amber-600', 'border-purple-500');
                btn.classList.add('border-stone-200');
            });
            const activeBtn = document.getElementById(`tab-${type}`);
            activeBtn.classList.remove('border-stone-200');
            activeBtn.classList.add('active-tab');

            // Get Data
            const data = pollutionData[type];

            // Render Text Content
            const contentDiv = document.getElementById('type-content-text');
            contentDiv.innerHTML = `
                <h3 class="text-2xl font-bold mb-4 text-stone-800">${data.title}</h3>
                <p class="mb-6 text-lg italic text-stone-600 border-l-4 border-stone-300 pl-4">${data.definition}</p>
                
                <div class="mb-6">
                    <h4 class="font-bold text-stone-700 mb-2 flex items-center gap-2">🔥 Causes</h4>
                    <ul class="list-disc pl-5 space-y-1 text-stone-600">
                        ${data.causes.map(c => `<li>${c}</li>`).join('')}
                    </ul>
                </div>

                <div>
                    <h4 class="font-bold text-stone-700 mb-2 flex items-center gap-2">📉 Effects</h4>
                    <ul class="list-disc pl-5 space-y-1 text-stone-600">
                        ${data.effects.map(e => `<li>${e}</li>`).join('')}
                    </ul>
                </div>
            `;

            // Render Chart
            renderChart(data);
        }

        function renderChart(data) {
            const ctx = document.getElementById('typesChart').getContext('2d');
            
            if (currentChart) {
                currentChart.destroy();
            }

            currentChart = new Chart(ctx, {
                type: 'doughnut',
                data: {
                    labels: data.chartLabels,
                    datasets: [{
                        label: data.chartLabel,
                        data: data.chartData,
                        backgroundColor: data.chartColors,
                        borderWidth: 0
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            position: 'bottom',
                            labels: {
                                boxWidth: 12,
                                font: { family: 'Nunito' }
                            }
                        },
                        title: {
                            display: true,
                            text: data.chartLabel,
                            font: { family: 'Nunito', size: 16 }
                        }
                    }
                }
            });
        }

        // --- Quiz Logic ---
        function loadQuizQuestion() {
            const q = quizQuestions[currentQuizIndex];
            document.getElementById('question-count').innerText = `Question ${currentQuizIndex + 1}/${quizQuestions.length}`;
            document.getElementById('question-text').innerText = q.q;
            
            const optionsHtml = q.options.map((opt, index) => `
                <button onclick="checkAnswer(${index})" class="quiz-option w-full text-left p-3 rounded-lg bg-white/10 hover:bg-white/20 border border-white/20 transition-colors font-medium">
                    ${opt}
                </button>
            `).join('');
            
            document.getElementById('options-container').innerHTML = optionsHtml;
            document.getElementById('feedback').innerText = '';
            document.getElementById('next-btn').classList.add('hidden');
        }

        function checkAnswer(selectedIndex) {
            // Disable all buttons
            document.querySelectorAll('.quiz-option').forEach(btn => btn.disabled = true);
            
            const correctIndex = quizQuestions[currentQuizIndex].a;
            
            if (selectedIndex === correctIndex) {
                document.getElementById('feedback').innerHTML = '<span class="text-white bg-green-500 px-2 py-1 rounded">Correct! ✅</span>';
                quizScore++;
            } else {
                document.getElementById('feedback').innerHTML = `<span class="text-white bg-red-500 px-2 py-1 rounded">Incorrect. The answer was: ${quizQuestions[currentQuizIndex].options[correctIndex]}</span>`;
            }

            document.getElementById('score-display').innerText = `Score: ${quizScore}`;
            document.getElementById('next-btn').classList.remove('hidden');
        }

        function nextQuestion() {
            currentQuizIndex++;
            if (currentQuizIndex < quizQuestions.length) {
                loadQuizQuestion();
            } else {
                showQuizResults();
            }
        }

        function showQuizResults() {
            document.getElementById('quiz-container').classList.add('hidden');
            document.getElementById('quiz-complete').classList.remove('hidden');
            document.getElementById('final-score').innerText = quizScore;
        }

        function resetQuiz() {
            currentQuizIndex = 0;
            quizScore = 0;
            document.getElementById('score-display').innerText = 'Score: 0';
            document.getElementById('quiz-complete').classList.add('hidden');
            document.getElementById('quiz-container').classList.remove('hidden');
            loadQuizQuestion();
        }

        // --- Utilities ---
        function scrollToSection(id) {
            const element = document.getElementById(id);
            if(element) {
                element.scrollIntoView({ behavior: 'smooth' });
                document.getElementById('mobile-menu').classList.add('hidden');
            }
        }

        function toggleMobileMenu() {
            document.getElementById('mobile-menu').classList.toggle('hidden');
        }

        // --- Init ---
        document.addEventListener('DOMContentLoaded', () => {
            switchTab('air'); // Load initial tab
            loadQuizQuestion(); // Load initial quiz
        });

    </script>
</body>
</html>
