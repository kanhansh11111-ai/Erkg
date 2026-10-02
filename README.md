# kanhaj
Coaching classes website
```html
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Apex Academy | Premier Coaching for JEE, NEET & Foundation</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            50: '#eff6ff',
                            100: '#dbeafe',
                            500: '#3b82f6',
                            600: '#2563eb',
                            700: '#1d4ed8',
                            800: '#1e40af',
                            900: '#1e3a8a',
                        },
                        accent: {
                            500: '#f59e0b',
                            600: '#d97706',
                        }
                    }
                }
            }
        }
    </script>
    <style>
        .gradient-text {
            background: linear-gradient(135deg, #1e3a8a 0%, #3b82f6 50%, #d97706 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .hero-bg {
            background: radial-gradient(circle at 10% 20%, rgba(59, 130, 246, 0.08) 0%, rgba(255, 255, 255, 0) 70%),
                        radial-gradient(circle at 90% 80%, rgba(245, 158, 11, 0.08) 0%, rgba(255, 255, 255, 0) 70%);
        }
        .glass-card {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(226, 232, 240, 0.8);
        }
    </style>
</head>
<body class="font-sans bg-slate-50 text-slate-800 antialiased selection:bg-brand-500 selection:text-white">

    <!-- Top Announcement Bar -->
    <div class="bg-brand-900 text-white text-xs sm:text-sm py-2 px-4 text-center font-medium flex justify-between items-center max-w-full overflow-hidden">
        <div class="mx-auto flex items-center gap-2">
            <span class="bg-amber-500 text-slate-900 font-bold px-2 py-0.5 rounded-full text-xs uppercase tracking-wide">New Batch</span>
            <span>Admissions Open for 2026-27 Batches! Get up to 40% Scholarship via Early Test.</span>
        </div>
        <button onclick="openModal('demoModal')" class="hidden md:inline-flex items-center text-xs underline font-semibold hover:text-amber-300 transition">
            Book Seat <i class="fa-solid fa-arrow-right ml-1"></i>
        </button>
    </div>

    <!-- Navigation Header -->
    <header class="sticky top-0 z-40 bg-white/90 backdrop-blur-md border-b border-slate-200/80 transition-all">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <!-- Logo -->
                <a href="#" class="flex items-center gap-3">
                    <div class="w-11 h-11 bg-gradient-to-tr from-brand-900 to-brand-600 rounded-xl flex items-center justify-center text-white shadow-lg shadow-brand-500/20 font-black text-2xl">
                        A
                    </div>
                    <div>
                        <span class="text-2xl font-extrabold tracking-tight text-slate-900">APEX<span class="text-brand-600">.</span></span>
                        <span class="block text-[10px] tracking-widest text-slate-500 uppercase font-semibold -mt-1">ACADEMY OF EXCELLENCE</span>
                    </div>
                </a>

                <!-- Desktop Nav Items -->
                <nav class="hidden lg:flex items-center space-x-8 text-sm font-semibold text-slate-600">
                    <a href="#courses" class="hover:text-brand-600 transition">Courses</a>
                    <a href="#calculator" class="hover:text-brand-600 transition">Fee & Batches</a>
                    <a href="#results" class="hover:text-brand-600 transition">Rankers & Results</a>
                    <a href="#faculty" class="hover:text-brand-600 transition">Top Faculty</a>
                    <a href="#quiz" class="hover:text-brand-600 transition">Free Quiz Demo</a>
                    <a href="#contact" class="hover:text-brand-600 transition">Contact Us</a>
                </nav>

                <!-- Header Actions -->
                <div class="hidden sm:flex items-center space-x-4">
                    <a href="tel:+919876543210" class="text-xs font-bold text-slate-700 hover:text-brand-600 flex items-center gap-2 px-3 py-2 rounded-lg hover:bg-slate-100 transition">
                        <i class="fa-solid fa-phone text-brand-600"></i> +91 98765 43210
                    </a>
                    <button onclick="openModal('demoModal')" class="bg-brand-600 hover:bg-brand-700 text-white px-5 py-2.5 rounded-xl font-bold text-sm shadow-md shadow-brand-600/20 hover:shadow-lg transition transform hover:-translate-y-0.5">
                        Book Free Demo Class
                    </button>
                </div>

                <!-- Mobile Menu Button -->
                <button id="mobileMenuBtn" onclick="toggleMobileMenu()" class="lg:hidden p-2 rounded-lg text-slate-600 hover:bg-slate-100 focus:outline-none">
                    <i class="fa-solid fa-bars text-xl"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Drawer -->
        <div id="mobileMenu" class="hidden lg:hidden bg-white border-b border-slate-200 px-4 pt-2 pb-6 space-y-3">
            <a href="#courses" onclick="toggleMobileMenu()" class="block px-3 py-2 rounded-lg font-medium text-slate-700 hover:bg-slate-50">Courses</a>
            <a href="#calculator" onclick="toggleMobileMenu()" class="block px-3 py-2 rounded-lg font-medium text-slate-700 hover:bg-slate-50">Fee Calculator</a>
            <a href="#results" onclick="toggleMobileMenu()" class="block px-3 py-2 rounded-lg font-medium text-slate-700 hover:bg-slate-50">Rankers & Results</a>
            <a href="#faculty" onclick="toggleMobileMenu()" class="block px-3 py-2 rounded-lg font-medium text-slate-700 hover:bg-slate-50">Faculty</a>
            <a href="#quiz" onclick="toggleMobileMenu()" class="block px-3 py-2 rounded-lg font-medium text-slate-700 hover:bg-slate-50">Free Quiz</a>
            <a href="#contact" onclick="toggleMobileMenu()" class="block px-3 py-2 rounded-lg font-medium text-slate-700 hover:bg-slate-50">Contact Us</a>
            <div class="pt-2 flex flex-col gap-2">
                <button onclick="toggleMobileMenu(); openModal('demoModal')" class="w-full bg-brand-600 text-white font-bold py-2.5 rounded-xl text-center shadow">
                    Book Free Demo Class
                </button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="relative hero-bg pt-12 pb-20 md:pt-20 md:pb-32 overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid lg:grid-cols-12 gap-12 items-center">
                
                <!-- Left Column Text -->
                <div class="lg:col-span-7 space-y-6 text-center lg:text-left">
                    <div class="inline-flex items-center gap-2 bg-brand-50 border border-brand-200 px-3 py-1.5 rounded-full text-brand-700 font-semibold text-xs sm:text-sm">
                        <span class="w-2 h-2 rounded-full bg-brand-600 animate-pulse"></span>
                        Trusted by 15,000+ Successful Aspirants
                    </div>
                    
                    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold text-slate-900 tracking-tight leading-tight">
                        Transform Your Potential into <span class="gradient-text">Top Ranks</span>
                    </h1>
                    
                    <p class="text-slate-600 text-base sm:text-lg max-w-2xl mx-auto lg:mx-0 leading-relaxed">
                        Comprehensive coaching for <strong class="text-slate-800">IIT-JEE, NEET, Board Exams (9th-12th)</strong>, and Olympiads. Learn from Kota's top faculties with personalized mentorship and AI-powered performance analytics.
                    </p>

                    <div class="flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4 pt-2">
                        <button onclick="openModal('demoModal')" class="w-full sm:w-auto bg-brand-600 hover:bg-brand-700 text-white px-8 py-4 rounded-xl font-bold text-base shadow-lg shadow-brand-600/30 hover:shadow-xl transition transform hover:-translate-y-0.5 flex items-center justify-center gap-2">
                            <span>Book Free 3-Day Demo</span>
                            <i class="fa-solid fa-arrow-right"></i>
                        </button>
                        <a href="#courses" class="w-full sm:w-auto bg-white border border-slate-300 hover:border-slate-400 text-slate-800 px-8 py-4 rounded-xl font-bold text-base shadow-sm transition hover:bg-slate-50 text-center">
                            Explore All Courses
                        </a>
                    </div>

                    <!-- Key Badges -->
                    <div class="pt-6 border-t border-slate-200/80 grid grid-cols-3 gap-4 max-w-lg mx-auto lg:mx-0 text-left">
                        <div>
                            <p class="text-2xl sm:text-3xl font-extrabold text-slate-900">98.4%</p>
                            <p class="text-xs sm:text-sm text-slate-500 font-medium">JEE / NEET Qualification</p>
                        </div>
                        <div>
                            <p class="text-2xl sm:text-3xl font-extrabold text-slate-900">1:15</p>
                            <p class="text-xs sm:text-sm text-slate-500 font-medium">Batch Ratio</p>
                        </div>
                        <div>
                            <p class="text-2xl sm:text-3xl font-extrabold text-amber-600">AIR 14</p>
                            <p class="text-xs sm:text-sm text-slate-500 font-medium">Highest Rank 2025</p>
                        </div>
                    </div>
                </div>

                <!-- Right Column Card / Image -->
                <div class="lg:col-span-5">
                    <div class="relative mx-auto max-w-md lg:max-w-none">
                        <!-- Decorative background glow -->
                        <div class="absolute -inset-2 bg-gradient-to-r from-brand-500 to-amber-500 rounded-3xl blur-2xl opacity-20"></div>
                        
                        <!-- Card Container -->
                        <div class="relative glass-card rounded-3xl p-6 sm:p-8 shadow-2xl space-y-6">
                            <div class="flex items-center justify-between border-b border-slate-100 pb-4">
                                <div>
                                    <h3 class="font-bold text-slate-900 text-lg">Instant Seat Reservation</h3>
                                    <p class="text-xs text-slate-500">Get instant call back from our Academic Counselor</p>
                                </div>
                                <span class="bg-emerald-100 text-emerald-800 text-xs font-bold px-2.5 py-1 rounded-md">Live Seats</span>
                            </div>

                            <form id="heroQuickForm" onsubmit="handleFormSubmit(event, 'Quick Form Submitted! Our team will call you within 15 minutes.')" class="space-y-4">
                                <div>
                                    <label class="block text-xs font-bold uppercase tracking-wider text-slate-600 mb-1">Student Name</label>
                                    <input type="text" required placeholder="e.g. Rahul Sharma" class="w-full px-4 py-3 rounded-xl border border-slate-200 focus:ring-2 focus:ring-brand-500 focus:border-brand-500 outline-none text-sm transition bg-white/70">
                                </div>
                                <div>
                                    <label class="block text-xs font-bold uppercase tracking-wider text-slate-600 mb-1">Mobile Number</label>
                                    <input type="tel" pattern="[0-9]{10}" required placeholder="10-digit mobile number" class="w-full px-4 py-3 rounded-xl border border-slate-200 focus:ring-2 focus:ring-brand-500 focus:border-brand-500 outline-none text-sm transition bg-white/70">
                                </div>
                                <div class="grid grid-cols-2 gap-3">
                                    <div>
                                        <label class="block text-xs font-bold uppercase tracking-wider text-slate-600 mb-1">Target Exam</label>
                                        <select required class="w-full px-3 py-3 rounded-xl border border-slate-200 focus:ring-2 focus:ring-brand-500 focus:border-brand-500 outline-none text-sm bg-white/70">
                                            <option value="">Select Target</option>
                                            <option value="JEE">IIT-JEE Main/Adv</option>
                                            <option value="NEET">NEET UG</option>
                                            <option value="Class 11-12">Class 11th - 12th</option>
                                            <option value="Foundation">Class 8th - 10th</option>
                                        </select>
                                    </div>
                                    <div>
                                        <label class="block text-xs font-bold uppercase tracking-wider text-slate-600 mb-1">Mode</label>
                                        <select class="w-full px-3 py-3 rounded-xl border border-slate-200 focus:ring-2 focus:ring-brand-500 focus:border-brand-500 outline-none text-sm bg-white/70">
                                            <option value="Offline">Offline Classroom</option>
                                            <option value="Online">Live Interactive</option>
                                        </select>
                                    </div>
                                </div>
                                <button type="submit" class="w-full bg-slate-900 hover:bg-slate-800 text-white font-bold py-3.5 rounded-xl transition shadow-md flex items-center justify-center gap-2 text-sm">
                                    <i class="fa-solid fa-paper-plane text-xs text-amber-400"></i> Request Free Counseling Call
                                </button>
                            </form>
                            
                            <div class="flex items-center gap-3 text-xs text-slate-500 justify-center">
                                <i class="fa-solid fa-shield-halved text-emerald-600"></i> No Spam. Your privacy is guaranteed.
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Feature Highlights / Why Us Section -->
    <section class="py-16 bg-white border-y border-slate-200/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-12">
                <h2 class="text-xs font-bold text-brand-600 tracking-widest uppercase mb-2">The Apex Advantage</h2>
                <p class="text-3xl sm:text-4xl font-extrabold text-slate-900">Why Top Performers Choose Us</p>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- Feature Card 1 -->
                <div class="p-6 rounded-2xl bg-slate-50 border border-slate-200/80 hover:border-brand-300 hover:shadow-lg transition group">
                    <div class="w-12 h-12 bg-brand-100 rounded-xl flex items-center justify-center text-brand-600 text-xl font-bold mb-4 group-hover:bg-brand-600 group-hover:text-white transition">
                        <i class="fa-solid fa-user-graduate"></i>
                    </div>
                    <h3 class="text-lg font-bold text-slate-900 mb-2">IITian & Doctor Faculty</h3>
                    <p class="text-slate-600 text-sm leading-relaxed">
                        Learn directly from top rankers, IIT graduates, and experienced medical faculty with 12+ years of teaching excellence.
                    </p>
                </div>

                <!-- Feature Card 2 -->
                <div class="p-6 rounded-2xl bg-slate-50 border border-slate-200/80 hover:border-brand-300 hover:shadow-lg transition group">
                    <div class="w-12 h-12 bg-amber-100 rounded-xl flex items-center justify-center text-amber-600 text-xl font-bold mb-4 group-hover:bg-amber-500 group-hover:text-white transition">
                        <i class="fa-solid fa-comments font-bold"></i>
                    </div>
                    <h3 class="text-lg font-bold text-slate-900 mb-2">1-on-1 Daily Doubt Solving</h3>
                    <p class="text-slate-600 text-sm leading-relaxed">
                        Dedicated doubt counters after every class, plus 24/7 online chat support to ensure no query remains unsolved.
                    </p>
                </div>

                <!-- Feature Card 3 -->
                <div class="p-6 rounded-2xl bg-slate-50 border border-slate-200/80 hover:border-brand-300 hover:shadow-lg transition group">
                    <div class="w-12 h-12 bg-emerald-100 rounded-xl flex items-center justify-center text-emerald-600 text-xl font-bold mb-4 group-hover:bg-emerald-600 group-hover:text-white transition">
                        <i class="fa-solid fa-chart-line"></i>
                    </div>
                    <h3 class="text-lg font-bold text-slate-900 mb-2">AI-Driven Test Analytics</h3>
                    <p class="text-slate-600 text-sm leading-relaxed">
                        Weekly Computer-Based Tests (CBT) with detailed percentile reports, speed analysis, and weak-area pinpointing.
                    </p>
                </div>

                <!-- Feature Card 4 -->
                <div class="p-6 rounded-2xl bg-slate-50 border border-slate-200/80 hover:border-brand-300 hover:shadow-lg transition group">
                    <div class="w-12 h-12 bg-purple-100 rounded-xl flex items-center justify-center text-purple-600 text-xl font-bold mb-4 group-hover:bg-purple-600 group-hover:text-white transition">
                        <i class="fa-solid fa-book-open"></i>
                    </div>
                    <h3 class="text-lg font-bold text-slate-900 mb-2">Comprehensive Printed Modules</h3>
                    <p class="text-slate-600 text-sm leading-relaxed">
                        Exhaustive theory, graded exercise sheets (Level 1 to 3), and previous 15 years solved papers.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Courses Section -->
    <section id="courses" class="py-20 bg-slate-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-12">
                <span class="text-xs font-bold text-brand-600 tracking-widest uppercase bg-brand-100 px-3 py-1 rounded-full">Targeted Preparation</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 mt-3">Our Specialized Coaching Programs</h2>
                <p class="text-slate-600 mt-2">Structured curriculum designed to build concept clarity and exam temperament.</p>
            </div>

            <!-- Course Filters / Tabs -->
            <div class="flex flex-wrap justify-center gap-2 mb-10">
                <button onclick="filterCourses('all')" class="course-tab-btn active px-5 py-2.5 rounded-xl font-semibold text-sm transition bg-brand-600 text-white shadow">All Programs</button>
                <button onclick="filterCourses('jee')" class="course-tab-btn px-5 py-2.5 rounded-xl font-semibold text-sm transition bg-white text-slate-600 hover:bg-slate-100 border border-slate-200">IIT-JEE (Main & Adv)</button>
                <button onclick="filterCourses('neet')" class="course-tab-btn px-5 py-2.5 rounded-xl font-semibold text-sm transition bg-white text-slate-600 hover:bg-slate-100 border border-slate-200">NEET (Medical)</button>
                <button onclick="filterCourses('foundation')" class="course-tab-btn px-5 py-2.5 rounded-xl font-semibold text-sm transition bg-white text-slate-600 hover:bg-slate-100 border border-slate-200">Class 9th & 10th</button>
                <button onclick="filterCourses('boards')" class="course-tab-btn px-5 py-2.5 rounded-xl font-semibold text-sm transition bg-white text-slate-600 hover:bg-slate-100 border border-slate-200">11th-12th Boards</button>
            </div>

            <!-- Courses Grid -->
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8" id="coursesGrid">

                <!-- Course Card 1 -->
                <div class="course-card jee bg-white rounded-2xl border border-slate-200 overflow-hidden hover:shadow-xl transition flex flex-col justify-between">
                    <div class="p-6 space-y-4">
                        <div class="flex justify-between items-start">
                            <span class="bg-blue-100 text-blue-800 text-xs font-extrabold px-3 py-1 rounded-full">JEE 2-YEAR PROGRAM</span>
                            <span class="text-xs font-semibold text-slate-400">Class 11th Entry</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-900">Target JEE Advanced (2027)</h3>
                        <p class="text-slate-600 text-sm">Full 2-year rigorous training covering Physics, Chemistry, and Mathematics for JEE Main & Advanced alongside CBSE Board Preparation.</p>
                        <ul class="space-y-2 text-xs font-medium text-slate-700 pt-2">
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> 750+ Hours Live Classroom Sessions</li>
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Weekly All India Test Series (AITS)</li>
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Printed Study Modules & DPPs</li>
                        </ul>
                    </div>
                    <div class="p-6 bg-slate-50 border-t border-slate-100 flex items-center justify-between">
                        <div>
                            <span class="text-xs text-slate-500 block">Starting From</span>
                            <span class="text-lg font-bold text-slate-900">₹65,000 <span class="text-xs font-normal text-slate-500">/ yr</span></span>
                        </div>
                        <button onclick="openModal('demoModal')" class="bg-brand-600 hover:bg-brand-700 text-white text-xs font-bold px-4 py-2.5 rounded-lg transition">
                            Apply Now
                        </button>
                    </div>
                </div>

                <!-- Course Card 2 -->
                <div class="course-card neet bg-white rounded-2xl border border-slate-200 overflow-hidden hover:shadow-xl transition flex flex-col justify-between">
                    <div class="p-6 space-y-4">
                        <div class="flex justify-between items-start">
                            <span class="bg-emerald-100 text-emerald-800 text-xs font-extrabold px-3 py-1 rounded-full">NEET MEDICAL</span>
                            <span class="text-xs font-semibold text-slate-400">Class 11th / 12th / Dropper</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-900">NEET Achievers Batch</h3>
                        <p class="text-slate-600 text-sm">In-depth coverage of NCERT Biology, Physics, & Organic Chemistry with 100+ NCERT-focused mock tests and speed training.</p>
                        <ul class="space-y-2 text-xs font-medium text-slate-700 pt-2">
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> NCERT Line-by-Line Mastery</li>
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> 30,000+ Question Bank Access</li>
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Personal Doctor Mentor Assigned</li>
                        </ul>
                    </div>
                    <div class="p-6 bg-slate-50 border-t border-slate-100 flex items-center justify-between">
                        <div>
                            <span class="text-xs text-slate-500 block">Starting From</span>
                            <span class="text-lg font-bold text-slate-900">₹58,000 <span class="text-xs font-normal text-slate-500">/ yr</span></span>
                        </div>
                        <button onclick="openModal('demoModal')" class="bg-brand-600 hover:bg-brand-700 text-white text-xs font-bold px-4 py-2.5 rounded-lg transition">
                            Apply Now
                        </button>
                    </div>
                </div>

                <!-- Course Card 3 -->
                <div class="course-card foundation bg-white rounded-2xl border border-slate-200 overflow-hidden hover:shadow-xl transition flex flex-col justify-between">
                    <div class="p-6 space-y-4">
                        <div class="flex justify-between items-start">
                            <span class="bg-purple-100 text-purple-800 text-xs font-extrabold px-3 py-1 rounded-full">FOUNDATION (9-10)</span>
                            <span class="text-xs font-semibold text-slate-400">Class 9th & 10th</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-900">Junior Genius Foundation</h3>
                        <p class="text-slate-600 text-sm">Build strong conceptual foundations in Science & Math while preparing for Olympiads (NSEJS, PRMO, NTSE) and school exams.</p>
                        <ul class="space-y-2 text-xs font-medium text-slate-700 pt-2">
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> STEM Activity-Based Learning</li>
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Olympiad & NTSE Special Sessions</li>
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Regular Parent-Teacher Meets</li>
                        </ul>
                    </div>
                    <div class="p-6 bg-slate-50 border-t border-slate-100 flex items-center justify-between">
                        <div>
                            <span class="text-xs text-slate-500 block">Starting From</span>
                            <span class="text-lg font-bold text-slate-900">₹32,000 <span class="text-xs font-normal text-slate-500">/ yr</span></span>
                        </div>
                        <button onclick="openModal('demoModal')" class="bg-brand-600 hover:bg-brand-700 text-white text-xs font-bold px-4 py-2.5 rounded-lg transition">
                            Apply Now
                        </button>
                    </div>
                </div>

                <!-- Course Card 4 -->
                <div class="course-card boards bg-white rounded-2xl border border-slate-200 overflow-hidden hover:shadow-xl transition flex flex-col justify-between">
                    <div class="p-6 space-y-4">
                        <div class="flex justify-between items-start">
                            <span class="bg-amber-100 text-amber-800 text-xs font-extrabold px-3 py-1 rounded-full">BOARD SPECIAL</span>
                            <span class="text-xs font-semibold text-slate-400">Class 12th Board</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-900">Class 12 Board Booster (PCMB)</h3>
                        <p class="text-slate-600 text-sm">Targeted revision program aimed at scoring 95%+ in CBSE/State Boards with subjective answer writing practice.</p>
                        <ul class="space-y-2 text-xs font-medium text-slate-700 pt-2">
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Previous 10 Years Board Papers</li>
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Practical Lab Exam Preparation</li>
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Fast-Track Revision Notes</li>
                        </ul>
                    </div>
                    <div class="p-6 bg-slate-50 border-t border-slate-100 flex items-center justify-between">
                        <div>
                            <span class="text-xs text-slate-500 block">Starting From</span>
                            <span class="text-lg font-bold text-slate-900">₹28,000 <span class="text-xs font-normal text-slate-500">/ yr</span></span>
                        </div>
                        <button onclick="openModal('demoModal')" class="bg-brand-600 hover:bg-brand-700 text-white text-xs font-bold px-4 py-2.5 rounded-lg transition">
                            Apply Now
                        </button>
                    </div>
                </div>

                <!-- Course Card 5 -->
                <div class="course-card jee bg-white rounded-2xl border border-slate-200 overflow-hidden hover:shadow-xl transition flex flex-col justify-between">
                    <div class="p-6 space-y-4">
                        <div class="flex justify-between items-start">
                            <span class="bg-blue-100 text-blue-800 text-xs font-extrabold px-3 py-1 rounded-full">1-YEAR DROPPER BATCH</span>
                            <span class="text-xs font-semibold text-slate-400">12th Pass</span>
                        </div>
                        <h3 class="text-xl font-bold text-slate-900">JEE Repeater Intensive</h3>
                        <p class="text-slate-600 text-sm">Fast-paced 1-year course for students dedicated to improving their percentile and securing an IIT seat in 2026.</p>
                        <ul class="space-y-2 text-xs font-medium text-slate-700 pt-2">
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Intensive Problem Solving</li>
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Daily 6 Hours Focused Classes</li>
                            <li class="flex items-center gap-2"><i class="fa-solid fa-check text-emerald-500"></i> Specialized Rank Improvement Test</li>
                        </ul>
                    </div>
                    <div class="p-6 bg-slate-50 border-t border-slate-100 flex items-center justify-between">
                        <div>
                            <span class="text-xs text-slate-500 block">Starting From</span>
                            <span class="text-lg font-bold text-slate-900">₹72,000 <span class="text-xs font-normal text-slate-500">/ yr</span></span>
                        </div>
                        <button onclick="openModal('demoModal')" class="bg-brand-600 hover:bg-brand-700 text-white text-xs font-bold px-4 py-2.5 rounded-lg transition">
                            Apply Now
                        </button>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Interactive Fee & Scholarship Calculator Section -->
    <section id="calculator" class="py-16 bg-gradient-to-b from-slate-900 to-brand-900 text-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid lg:grid-cols-12 gap-12 items-center">
                
                <div class="lg:col-span-5 space-y-4">
                    <span class="bg-amber-500/20 text-amber-300 text-xs font-bold px-3 py-1 rounded-full uppercase border border-amber-500/30">Instant Estimate</span>
                    <h2 class="text-3xl sm:text-4xl font-extrabold tracking-tight">Interactive Fee & Scholarship Estimator</h2>
                    <p class="text-slate-300 text-sm leading-relaxed">
                        Calculate estimated course fees after applying scholarship discounts based on your academic score or Entrance Scholarship Test (ASAT).
                    </p>
                    
                    <div class="space-y-3 pt-2 text-sm text-slate-300">
                        <div class="flex items-center gap-3">
                            <div class="w-8 h-8 rounded-full bg-brand-700 flex items-center justify-center text-amber-400 font-bold"><i class="fa-solid fa-percent"></i></div>
                            <span>Up to 75% Scholarship via Online Assessment</span>
                        </div>
                        <div class="flex items-center gap-3">
                            <div class="w-8 h-8 rounded-full bg-brand-700 flex items-center justify-center text-amber-400 font-bold"><i class="fa-solid fa-wallet"></i></div>
                            <span>Zero Cost EMI / Easy Installment Plans Available</span>
                        </div>
                    </div>
                </div>

                <!-- Calculator Form Card -->
                <div class="lg:col-span-7 bg-white text-slate-800 rounded-3xl p-6 sm:p-8 shadow-2xl">
                    <div class="grid sm:grid-cols-2 gap-6">
                        
                        <div>
                            <label class="block text-xs font-bold uppercase text-slate-600 mb-2">Select Course</label>
                            <select id="calcCourse" onchange="calculateFee()" class="w-full p-3 rounded-xl border border-slate-300 font-semibold text-sm outline-none focus:ring-2 focus:ring-brand-500">
                                <option value="jee2yr" data-fee="120000">JEE 2-Year Integrated (₹1,20,000)</option>
                                <option value="neet2yr" data-fee="110000">NEET 2-Year Program (₹1,10,000)</option>
                                <option value="jee1yr" data-fee="75000">JEE 1-Year Dropper (₹75,000)</option>
                                <option value="foundation" data-fee="45000">Class 9th / 10th Foundation (₹45,000)</option>
                            </select>
                        </div>

                        <div>
                            <label class="block text-xs font-bold uppercase text-slate-600 mb-2">Learning Mode</label>
                            <select id="calcMode" onchange="calculateFee()" class="w-full p-3 rounded-xl border border-slate-300 font-semibold text-sm outline-none focus:ring-2 focus:ring-brand-500">
                                <option value="1">Offline Classroom Center</option>
                                <option value="0.75">Online Live Interactive (25% Off)</option>
                            </select>
                        </div>

                        <div class="sm:col-span-2">
                            <div class="flex justify-between items-center mb-1">
                                <label class="block text-xs font-bold uppercase text-slate-600">Expected / Previous Exam Score</label>
                                <span id="scoreVal" class="text-sm font-extrabold text-brand-600">85%</span>
                            </div>
                            <input type="range" id="calcScore" min="50" max="100" value="85" oninput="calculateFee()" class="w-full accent-brand-600 cursor-pointer">
                            <div class="flex justify-between text-[11px] text-slate-400 mt-1">
                                <span>50% Score (10% Scholarship)</span>
                                <span>95%+ Score (50% Scholarship)</span>
                            </div>
                        </div>

                    </div>

                    <!-- Calculated Result Output -->
                    <div class="mt-8 p-5 bg-slate-50 rounded-2xl border border-slate-200 flex flex-col sm:flex-row items-center justify-between gap-4">
                        <div>
                            <span class="text-xs font-bold uppercase tracking-wider text-slate-500 block">Estimated Annual Fee</span>
                            <div class="flex items-baseline gap-2">
                                <span id="finalFee" class="text-3xl font-extrabold text-brand-700">₹68,850</span>
                                <span id="originalFee" class="text-sm text-slate-400 line-through">₹1,20,000</span>
                            </div>
                            <span id="discountBadge" class="text-xs font-bold text-emerald-600">You Save ₹51,150 (42% Scholarship Applied)</span>
                        </div>

                        <button onclick="openModal('demoModal')" class="w-full sm:w-auto bg-amber-500 hover:bg-amber-600 text-slate-900 font-extrabold px-6 py-3.5 rounded-xl text-sm transition shadow-md">
                            Claim Scholarship Seat
                        </button>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Rankers & Success Stories Section -->
    <section id="results" class="py-20 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <span class="text-xs font-bold text-amber-600 tracking-widest uppercase bg-amber-100 px-3 py-1 rounded-full">Hall of Fame</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 mt-3">Our Outstanding Top Rankers 2025</h2>
                <p class="text-slate-600 mt-2">Consistent results crafted through dedication, top faculty guidance, and hard work.</p>
            </div>

            <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-8">
                
                <!-- Ranker 1 -->
                <div class="p-6 rounded-2xl bg-slate-50 border border-slate-200 text-center relative group hover:-translate-y-1 transition duration-300 shadow-sm hover:shadow-xl">
                    <div class="absolute top-4 right-4 bg-amber-500 text-slate-900 text-xs font-extrabold px-2.5 py-1 rounded-md">
                        JEE ADV
                    </div>
                    <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&q=80&w=300" alt="Student" class="w-24 h-24 rounded-full mx-auto object-cover ring-4 ring-brand-500/30 mb-4">
                    <h3 class="font-bold text-slate-900 text-lg">Ananya Sen</h3>
                    <p class="text-xs font-bold text-brand-600 uppercase tracking-wider mb-2">AIR 14 - JEE Advanced</p>
                    <p class="text-xs text-slate-500 italic">"The test analytics and teachers' personal mentorship helped me turn my physics weak points into strengths."</p>
                </div>

                <!-- Ranker 2 -->
                <div class="p-6 rounded-2xl bg-slate-50 border border-slate-200 text-center relative group hover:-translate-y-1 transition duration-300 shadow-sm hover:shadow-xl">
                    <div class="absolute top-4 right-4 bg-emerald-500 text-white text-xs font-extrabold px-2.5 py-1 rounded-md">
                        NEET 710/720
                    </div>
                    <img src="https://images.unsplash.com/photo-1539571696357-5a69c17a67c6?auto=format&fit=crop&q=80&w=300" alt="Student" class="w-24 h-24 rounded-full mx-auto object-cover ring-4 ring-emerald-500/30 mb-4">
                    <h3 class="font-bold text-slate-900 text-lg">Rohan Malhotra</h3>
                    <p class="text-xs font-bold text-emerald-600 uppercase tracking-wider mb-2">AIR 42 - NEET UG</p>
                    <p class="text-xs text-slate-500 italic">"Daily doubt counters and NCERT-focused biology modules were the key reasons behind my 710 score."</p>
                </div>

                <!-- Ranker 3 -->
                <div class="p-6 rounded-2xl bg-slate-50 border border-slate-200 text-center relative group hover:-translate-y-1 transition duration-300 shadow-sm hover:shadow-xl">
                    <div class="absolute top-4 right-4 bg-amber-500 text-slate-900 text-xs font-extrabold px-2.5 py-1 rounded-md">
                        JEE MAIN
                    </div>
                    <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&q=80&w=300" alt="Student" class="w-24 h-24 rounded-full mx-auto object-cover ring-4 ring-brand-500/30 mb-4">
                    <h3 class="font-bold text-slate-900 text-lg">Priya Patel</h3>
                    <p class="text-xs font-bold text-brand-600 uppercase tracking-wider mb-2">99.94 Percentile</p>
                    <p class="text-xs text-slate-500 italic">"Apex's disciplined environment and batch size ensured every single student got teacher attention."</p>
                </div>

                <!-- Ranker 4 -->
                <div class="p-6 rounded-2xl bg-slate-50 border border-slate-200 text-center relative group hover:-translate-y-1 transition duration-300 shadow-sm hover:shadow-xl">
                    <div class="absolute top-4 right-4 bg-purple-600 text-white text-xs font-extrabold px-2.5 py-1 rounded-md">
                        CBSE 98.8%
                    </div>
                    <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?auto=format&fit=crop&q=80&w=300" alt="Student" class="w-24 h-24 rounded-full mx-auto object-cover ring-4 ring-purple-500/30 mb-4">
                    <h3 class="font-bold text-slate-900 text-lg">Karan Verma</h3>
                    <p class="text-xs font-bold text-purple-600 uppercase tracking-wider mb-2">Class 12th Board Topper</p>
                    <p class="text-xs text-slate-500 italic">"Balancing Board exams and competitive exams was super seamless thanks to the structured schedule."</p>
                </div>

            </div>
        </div>
    </section>

    <!-- Faculty Showcase -->
    <section id="faculty" class="py-20 bg-slate-50 border-t border-slate-200">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <span class="text-xs font-bold text-brand-600 tracking-widest uppercase bg-brand-100 px-3 py-1 rounded-full">Expert Educators</span>
                <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 mt-3">Learn From Kota & National Top Mentors</h2>
                <p class="text-slate-600 mt-2">Passionate teachers with proven track records of shaping top 100 ranks.</p>
            </div>

            <div class="grid md:grid-cols-3 gap-8">
                
                <!-- Faculty 1 -->
                <div class="bg-white rounded-2xl p-6 border border-slate-200 text-center space-y-4 shadow-sm hover:shadow-md transition">
                    <img src="https://images.unsplash.com/photo-1560250097-0b93528c311a?auto=format&fit=crop&q=80&w=300" alt="Faculty" class="w-28 h-28 rounded-2xl mx-auto object-cover border-2 border-brand-500">
                    <div>
                        <h3 class="font-bold text-slate-900 text-xl">Dr. S. K. Verma</h3>
                        <p class="text-xs font-extrabold text-brand-600 uppercase">Head of Physics Department</p>
                        <p class="text-xs text-slate-500 mt-1">M.Tech (IIT Bombay) | 16+ Yrs Exp.</p>
                    </div>
                    <p class="text-xs text-slate-600">Renowned for simplifying complex Mechanics & Electrodynamics using visual physical analogies.</p>
                </div>

                <!-- Faculty 2 -->
                <div class="bg-white rounded-2xl p-6 border border-slate-200 text-center space-y-4 shadow-sm hover:shadow-md transition">
                    <img src="https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?auto=format&fit=crop&q=80&w=300" alt="Faculty" class="w-28 h-28 rounded-2xl mx-auto object-cover border-2 border-emerald-500">
                    <div>
                        <h3 class="font-bold text-slate-900 text-xl">Dr. Meenakshi Roy</h3>
                        <p class="text-xs font-extrabold text-emerald-600 uppercase">Head of Biology & Medical Division</p>
                        <p class="text-xs text-slate-500 mt-1">MBBS (AIIMS New Delhi) | 14+ Yrs Exp.</p>
                    </div>
                    <p class="text-xs text-slate-600">Guided 200+ students into top government medical colleges with her memory-mnemonic techniques.</p>
                </div>

                <!-- Faculty 3 -->
                <div class="bg-white rounded-2xl p-6 border border-slate-200 text-center space-y-4 shadow-sm hover:shadow-md transition">
                    <img src="https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?auto=format&fit=crop&q=80&w=300" alt="Faculty" class="w-28 h-28 rounded-2xl mx-auto object-cover border-2 border-amber-500">
                    <div>
                        <h3 class="font-bold text-slate-900 text-xl">Prof. Rajesh Gupta</h3>
                        <p class="text-xs font-extrabold text-amber-600 uppercase">Senior Chemistry Mentor</p>
                        <p class="text-xs text-slate-500 mt-1">M.Sc. Chemistry (IIT Delhi) | 12+ Yrs Exp.</p>
                    </div>
                    <p class="text-xs text-slate-600">Expert in Organic Chemistry reaction mechanisms and shortcut problem-solving techniques.</p>
                </div>

            </div>
        </div>
    </section>

    <!-- Interactive Demo Quiz Section -->
    <section id="quiz" class="py-20 bg-white">
        <div class="max-w-4xl mx-auto px-4 sm:px-6">
            <div class="bg-gradient-to-br from-brand-900 to-slate-900 text-white rounded-3xl p-6 sm:p-10 shadow-2xl">
                
                <div class="text-center mb-8">
                    <span class="bg-amber-400 text-slate-900 text-xs font-extrabold px-3 py-1 rounded-full uppercase">Interactive Sample</span>
                    <h2 class="text-2xl sm:text-3xl font-extrabold mt-2">Test Your Skills - 1 Minute Quiz Challenge</h2>
                    <p class="text-slate-300 text-xs sm:text-sm">Try a sample question to experience our concept-clarity methodology.</p>
                </div>

                <div id="quizContainer" class="bg-white/10 backdrop-blur-md rounded-2xl p-6 border border-white/10 space-y-6">
                    <div class="flex justify-between items-center text-xs text-amber-300 font-bold">
                        <span>QUESTION 1 OF 1</span>
                        <span>TARGET: JEE / NEET BASIC</span>
                    </div>

                    <p class="text-base sm:text-lg font-semibold text-white">
                        Q: A projectile is fired at an angle of 45° with the horizontal. At the highest point of its trajectory, what is its vertical velocity component?
                    </p>

                    <div class="grid sm:grid-cols-2 gap-3" id="quizOptions">
                        <button onclick="checkQuizAnswer(this, false)" class="p-3.5 rounded-xl border border-white/20 text-left text-sm font-medium hover:bg-white/10 transition flex items-center justify-between">
                            <span>A) Maximum</span>
                            <i class="fa-regular fa-circle text-slate-400"></i>
                        </button>
                        <button onclick="checkQuizAnswer(this, true)" class="p-3.5 rounded-xl border border-white/20 text-left text-sm font-medium hover:bg-white/10 transition flex items-center justify-between">
                            <span>B) Zero</span>
                            <i class="fa-regular fa-circle text-slate-400"></i>
                        </button>
                        <button onclick="checkQuizAnswer(this, false)" class="p-3.5 rounded-xl border border-white/20 text-left text-sm font-medium hover:bg-white/10 transition flex items-center justify-between">
                            <span>C) Same as initial velocity</span>
                            <i class="fa-regular fa-circle text-slate-400"></i>
                        </button>
                        <button onclick="checkQuizAnswer(this, false)" class="p-3.5 rounded-xl border border-white/20 text-left text-sm font-medium hover:bg-white/10 transition flex items-center justify-between">
                            <span>D) Infinite</span>
                            <i class="fa-regular fa-circle text-slate-400"></i>
                        </button>
                    </div>

                    <div id="quizFeedback" class="hidden p-4 rounded-xl text-sm font-semibold"></div>
                </div>

            </div>
        </div>
    </section>

    <!-- FAQ Section -->
    <section class="py-16 bg-slate-50 border-t border-slate-200">
        <div class="max-w-4xl mx-auto px-4 sm:px-6">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-extrabold text-slate-900">Frequently Asked Questions</h2>
                <p class="text-slate-600 text-sm mt-1">Have questions? We're here to help you make the right choice.</p>
            </div>

            <div class="space-y-4">
                <!-- FAQ Item 1 -->
                <div class="bg-white rounded-xl border border-slate-200 overflow-hidden">
                    <button onclick="toggleFaq(this)" class="w-full text-left p-5 font-bold text-slate-900 flex justify-between items-center text-base focus:outline-none">
                        <span>How can I register for the Free 3-Day Demo Classes?</span>
                        <i class="fa-solid fa-chevron-down text-slate-400 text-sm transition-transform"></i>
                    </button>
                    <div class="faq-answer hidden px-5 pb-5 text-sm text-slate-600 leading-relaxed border-t border-slate-100 pt-3">
                        You can simply click on the "Book Free Demo Class" button on our website, fill in your details, and select your preferred branch or online mode. Our academic team will allocate your demo pass immediately.
                    </div>
                </div>

                <!-- FAQ Item 2 -->
                <div class="bg-white rounded-xl border border-slate-200 overflow-hidden">
                    <button onclick="toggleFaq(this)" class="w-full text-left p-5 font-bold text-slate-900 flex justify-between items-center text-base focus:outline-none">
                        <span>What is the batch strength in offline classes?</span>
                        <i class="fa-solid fa-chevron-down text-slate-400 text-sm transition-transform"></i>
                    </button>
                    <div class="faq-answer hidden px-5 pb-5 text-sm text-slate-600 leading-relaxed border-t border-slate-100 pt-3">
                        We strictly cap our offline batch size to 35-40 students per class to ensure every student gets individual attention and can interact freely with faculty during doubt clearing sessions.
                    </div>
                </div>

                <!-- FAQ Item 3 -->
                <div class="bg-white rounded-xl border border-slate-200 overflow-hidden">
                    <button onclick="toggleFaq(this)" class="w-full text-left p-5 font-bold text-slate-900 flex justify-between items-center text-base focus:outline-none">
                        <span>Is installment payment available for course fees?</span>
                        <i class="fa-solid fa-chevron-down text-slate-400 text-sm transition-transform"></i>
                    </button>
                    <div class="faq-answer hidden px-5 pb-5 text-sm text-slate-600 leading-relaxed border-t border-slate-100 pt-3">
                        Yes! We offer flexible 3 to 6 month no-cost installment plans, as well as education loan assistance at 0% interest with minimal documentation.
                    </div>
                </div>

                <!-- FAQ Item 4 -->
                <div class="bg-white rounded-xl border border-slate-200 overflow-hidden">
                    <button onclick="toggleFaq(this)" class="w-full text-left p-5 font-bold text-slate-900 flex justify-between items-center text-base focus:outline-none">
                        <span>Do you provide online backup recorded lectures?</span>
                        <i class="fa-solid fa-chevron-down text-slate-400 text-sm transition-transform"></i>
                    </button>
                    <div class="faq-answer hidden px-5 pb-5 text-sm text-slate-600 leading-relaxed border-t border-slate-100 pt-3">
                        Yes! All offline classroom lectures are recorded in HD and available on our Apex Student App within 2 hours, so students never miss a topic if they are absent.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact & Center Location Section -->
    <section id="contact" class="py-20 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid lg:grid-cols-12 gap-12">
                
                <!-- Contact Info -->
                <div class="lg:col-span-5 space-y-6">
                    <div>
                        <span class="text-xs font-bold text-brand-600 uppercase tracking-wider">Visit Center</span>
                        <h2 class="text-3xl font-extrabold text-slate-900 mt-1">Get In Touch With Us</h2>
                        <p class="text-slate-600 text-sm mt-2">Have a query or want to visit our campus? Walk in or leave us a message below.</p>
                    </div>

                    <div class="space-y-4 text-sm font-medium">
                        <div class="flex items-start gap-4 p-4 rounded-xl bg-slate-50 border border-slate-200">
                            <div class="w-10 h-10 rounded-lg bg-brand-100 text-brand-600 flex items-center justify-center shrink-0 text-lg">
                                <i class="fa-solid fa-location-dot"></i>
                            </div>
                            <div>
                                <h4 class="font-bold text-slate-900">Main Campus Address</h4>
                                <p class="text-slate-600 text-xs mt-0.5">Plot 42, Education Hub Sector 14, Near Metro Pillar 120, City Center</p>
                            </div>
                        </div>

                        <div class="flex items-start gap-4 p-4 rounded-xl bg-slate-50 border border-slate-200">
                            <div class="w-10 h-10 rounded-lg bg-emerald-100 text-emerald-600 flex items-center justify-center shrink-0 text-lg">
                                <i class="fa-solid fa-phone"></i>
                            </div>
                            <div>
                                <h4 class="font-bold text-slate-900">Admission Helpline</h4>
                                <p class="text-slate-600 text-xs mt-0.5">+91 98765 43210 / +91 98765 43211</p>
                                <p class="text-[11px] text-slate-400">Mon - Sun: 8:00 AM to 8:00 PM</p>
                            </div>
                        </div>

                        <div class="flex items-start gap-4 p-4 rounded-xl bg-slate-50 border border-slate-200">
                            <div class="w-10 h-10 rounded-lg bg-purple-100 text-purple-600 flex items-center justify-center shrink-0 text-lg">
                                <i class="fa-solid fa-envelope"></i>
                            </div>
                            <div>
                                <h4 class="font-bold text-slate-900">Email Enquiries</h4>
                                <p class="text-slate-600 text-xs mt-0.5">admissions@apexacademy.edu</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Detailed Contact Form -->
                <div class="lg:col-span-7 bg-slate-50 p-8 rounded-3xl border border-slate-200">
                    <h3 class="text-xl font-bold text-slate-900 mb-6">Send Us a Direct Message</h3>
                    
                    <form onsubmit="handleFormSubmit(event, 'Message Sent Successfully! Our team will get back to you shorty.')" class="space-y-4">
                        <div class="grid sm:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-xs font-bold text-slate-600 uppercase mb-1">Your Full Name</label>
                                <input type="text" required placeholder="John Doe" class="w-full px-4 py-3 rounded-xl border border-slate-200 outline-none focus:ring-2 focus:ring-brand-500 bg-white text-sm">
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-slate-600 uppercase mb-1">Phone Number</label>
                                <input type="tel" pattern="[0-9]{10}" required placeholder="9876543210" class="w-full px-4 py-3 rounded-xl border border-slate-200 outline-none focus:ring-2 focus:ring-brand-500 bg-white text-sm">
                            </div>
                        </div>

                        <div class="grid sm:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-xs font-bold text-slate-600 uppercase mb-1">Current Class / Grade</label>
                                <select class="w-full px-4 py-3 rounded-xl border border-slate-200 outline-none focus:ring-2 focus:ring-brand-500 bg-white text-sm">
                                    <option>Class 9th</option>
                                    <option>Class 10th</option>
                                    <option>Class 11th</option>
                                    <option>Class 12th</option>
                                    <option>12th Pass (Dropper)</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-xs font-bold text-slate-600 uppercase mb-1">Target Exam</label>
                                <select class="w-full px-4 py-3 rounded-xl border border-slate-200 outline-none focus:ring-2 focus:ring-brand-500 bg-white text-sm">
                                    <option>IIT-JEE Main & Advanced</option>
                                    <option>NEET Medical</option>
                                    <option>Board Exams Only</option>
                                    <option>Olympiad / NTSE</option>
                                </select>
                            </div>
                        </div>

                        <div>
                            <label class="block text-xs font-bold text-slate-600 uppercase mb-1">Message / Question</label>
                            <textarea rows="3" placeholder="Tell us what you'd like to know..." class="w-full px-4 py-3 rounded-xl border border-slate-200 outline-none focus:ring-2 focus:ring-brand-500 bg-white text-sm"></textarea>
                        </div>

                        <button type="submit" class="w-full bg-brand-600 hover:bg-brand-700 text-white font-bold py-3.5 rounded-xl shadow-md transition text-sm">
                            Submit Inquiry
                        </button>
                    </form>
                </div>

            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-slate-900 text-slate-400 py-12 border-t border-slate-800 text-xs sm:text-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-8 pb-12 border-b border-slate-800">
                <div class="col-span-2 md:col-span-1 space-y-3">
                    <span class="text-2xl font-black text-white">APEX<span class="text-brand-500">.</span></span>
                    <p class="text-xs text-slate-400 leading-relaxed">Pioneering quality competitive coaching with modern technology, expert faculty, and personalized mentorship.</p>
                </div>
                <div>
                    <h4 class="text-white font-bold mb-3 text-sm">Quick Links</h4>
                    <ul class="space-y-2">
                        <li><a href="#courses" class="hover:text-white transition">Our Courses</a></li>
                        <li><a href="#calculator" class="hover:text-white transition">Scholarship Test</a></li>
                        <li><a href="#results" class="hover:text-white transition">Top Rankers</a></li>
                        <li><a href="#faculty" class="hover:text-white transition">Faculty Team</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-white font-bold mb-3 text-sm">Target Exams</h4>
                    <ul class="space-y-2">
                        <li><a href="#" class="hover:text-white transition">IIT-JEE Mains</a></li>
                        <li><a href="#" class="hover:text-white transition">JEE Advanced</a></li>
                        <li><a href="#" class="hover:text-white transition">NEET UG</a></li>
                        <li><a href="#" class="hover:text-white transition">CBSE Class 10 & 12</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-white font-bold mb-3 text-sm">Connect With Us</h4>
                    <div class="flex space-x-4 text-base text-slate-300">
                        <a href="#" class="w-9 h-9 rounded-full bg-slate-800 flex items-center justify-center hover:bg-brand-600 hover:text-white transition"><i class="fa-brands fa-facebook-f"></i></a>
                        <a href="#" class="w-9 h-9 rounded-full bg-slate-800 flex items-center justify-center hover:bg-brand-600 hover:text-white transition"><i class="fa-brands fa-instagram"></i></a>
                        <a href="#" class="w-9 h-9 rounded-full bg-slate-800 flex items-center justify-center hover:bg-brand-600 hover:text-white transition"><i class="fa-brands fa-youtube"></i></a>
                        <a href="#" class="w-9 h-9 rounded-full bg-slate-800 flex items-center justify-center hover:bg-brand-600 hover:text-white transition"><i class="fa-brands fa-whatsapp"></i></a>
                    </div>
                </div>
            </div>
            <div class="pt-8 text-center text-xs text-slate-500">
                © 2026 Apex Academy of Excellence. All Rights Reserved. Designed for coaching success.
            </div>
        </div>
    </footer>

    <!-- Booking Modal -->
    <div id="demoModal" class="fixed inset-0 z-50 hidden bg-slate-900/60 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-md w-full p-6 sm:p-8 relative shadow-2xl animate-fade-in">
            <button onclick="closeModal('demoModal')" class="absolute top-4 right-4 text-slate-400 hover:text-slate-600 text-lg p-2">
                <i class="fa-solid fa-xmark"></i>
            </button>
            <div class="text-center mb-6">
                <div class="w-12 h-12 bg-brand-100 text-brand-600 rounded-full flex items-center justify-center mx-auto mb-2 text-xl font-bold">
                    <i class="fa-solid fa-graduation-cap"></i>
                </div>
                <h3 class="text-2xl font-bold text-slate-900">Book Free Demo Seat</h3>
                <p class="text-xs text-slate-500 mt-1">Attend 3 Days Live Classes without paying any fees</p>
            </div>

            <form onsubmit="handleModalSubmit(event)" class="space-y-4">
                <div>
                    <label class="block text-xs font-bold uppercase text-slate-600 mb-1">Student Name</label>
                    <input type="text" required placeholder="Full Name" class="w-full px-4 py-3 rounded-xl border border-slate-200 outline-none focus:ring-2 focus:ring-brand-500 text-sm">
                </div>
                <div>
                    <label class="block text-xs font-bold uppercase text-slate-600 mb-1">Mobile Number</label>
                    <input type="tel" pattern="[0-9]{10}" required placeholder="10-digit phone number" class="w-full px-4 py-3 rounded-xl border border-slate-200 outline-none focus:ring-2 focus:ring-brand-500 text-sm">
                </div>
                <div>
                    <label class="block text-xs font-bold uppercase text-slate-600 mb-1">Preferred Course</label>
                    <select class="w-full px-4 py-3 rounded-xl border border-slate-200 outline-none focus:ring-2 focus:ring-brand-500 text-sm">
                        <option>IIT-JEE (Main & Adv)</option>
                        <option>NEET (Medical)</option>
                        <option>Class 9th & 10th Foundation</option>
                        <option>Class 11th / 12th Board</option>
                    </select>
                </div>
                <button type="submit" class="w-full bg-brand-600 hover:bg-brand-700 text-white font-bold py-3.5 rounded-xl shadow-lg transition text-sm">
                    Confirm Free Demo Booking
                </button>
            </form>
        </div>
    </div>

    <!-- Toast Notification Message -->
    <div id="toast" class="fixed bottom-5 right-5 z-50 hidden bg-slate-900 text-white px-5 py-4 rounded-2xl shadow-2xl flex items-center gap-3 border border-slate-700 text-sm max-w-sm">
        <i class="fa-solid fa-circle-check text-emerald-400 text-xl"></i>
        <span id="toastMsg">Action completed successfully!</span>
    </div>

    <!-- Embedded Interactive JavaScript -->
    <script>
        // Toggle Mobile Navigation Menu
        function toggleMobileMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('hidden');
        }

        // Modal Open/Close Controls
        function openModal(id) {
            document.getElementById(id).classList.remove('hidden');
        }

        function closeModal(id) {
            document.getElementById(id).classList.add('hidden');
        }

        // Course Tab Filtering Logic
        function filterCourses(category) {
            const cards = document.querySelectorAll('.course-card');
            const btns = document.querySelectorAll('.course-tab-btn');

            btns.forEach(btn => {
                btn.classList.remove('bg-brand-600', 'text-white', 'shadow');
                btn.classList.add('bg-white', 'text-slate-600');
            });

            event.target.classList.add('bg-brand-600', 'text-white', 'shadow');
            event.target.classList.remove('bg-white', 'text-slate-600');

            cards.forEach(card => {
                if (category === 'all' || card.classList.contains(category)) {
                    card.style.display = 'flex';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        // Dynamic Fee & Scholarship Calculator Logic
        function calculateFee() {
            const courseSelect = document.getElementById('calcCourse');
            const selectedOption = courseSelect.options[courseSelect.selectedIndex];
            const baseFee = parseFloat(selectedOption.getAttribute('data-fee')) || 100000;
            
            const modeMultiplier = parseFloat(document.getElementById('calcMode').value) || 1;
            const score = parseInt(document.getElementById('calcScore').value) || 85;

            document.getElementById('scoreVal').innerText = score + '% Marks';

            // Calculate scholarship percentage based on score
            let scholarshipPercent = 10;
            if (score >= 95) scholarshipPercent = 50;
            else if (score >= 90) scholarshipPercent = 35;
            else if (score >= 80) scholarshipPercent = 25;
            else if (score >= 70) scholarshipPercent = 15;

            // Final Fee calculation
            const feeAfterMode = baseFee * modeMultiplier;
            const discountAmount = feeAfterMode * (scholarshipPercent / 100);
            const finalFee = feeAfterMode - discountAmount;

            document.getElementById('finalFee').innerText = '₹' + Math.round(finalFee).toLocaleString('en-IN');
            document.getElementById('originalFee').innerText = '₹' + Math.round(baseFee).toLocaleString('en-IN');
            document.getElementById('discountBadge').innerText = `You Save ₹${Math.round(discountAmount).toLocaleString('en-IN')} (${scholarshipPercent}% Scholarship Applied)`;
        }

        // Quiz Option Checking Logic
        function checkQuizAnswer(button, isCorrect) {
            const feedback = document.getElementById('quizFeedback');
            const options = document.querySelectorAll('#quizOptions button');

            options.forEach(opt => {
                opt.disabled = true;
                opt.classList.add('opacity-50');
            });

            feedback.classList.remove('hidden', 'bg-emerald-500/20', 'text-emerald-300', 'bg-rose-500/20', 'text-rose-300');

            if (isCorrect) {
                button.classList.add('bg-emerald-600', 'text-white');
                feedback.classList.add('bg-emerald-500/20', 'text-emerald-300');
                feedback.innerHTML = '<i class="fa-solid fa-circle-check mr-2"></i> <strong>Spot On!</strong> At the apex point of projectile motion, vertical speed becomes zero while horizontal velocity remains constant.';
            } else {
                button.classList.add('bg-rose-600', 'text-white');
                feedback.classList.add('bg-rose-500/20', 'text-rose-300');
                feedback.innerHTML = '<i class="fa-solid fa-circle-xmark mr-2"></i> <strong>Incorrect!</strong> The vertical velocity reduces to zero at maximum height before pulling the projectile downwards.';
            }
        }

        // FAQ Accordion Toggle
        function toggleFaq(btn) {
            const answer = btn.nextElementSibling;
            const icon = btn.querySelector('i');
            
            answer.classList.toggle('hidden');
            icon.classList.toggle('rotate-180');
        }

        // Form Submit Handler with Custom Toast
        function handleFormSubmit(event, successMsg) {
            event.preventDefault();
            event.target.reset();
            showToast(successMsg);
        }

        function handleModalSubmit(event) {
            event.preventDefault();
            closeModal('demoModal');
            showToast('Demo class pass generated! Check your phone SMS shortly.');
            event.target.reset();
        }

        function showToast(message) {
            const toast = document.getElementById('toast');
            const toastMsg = document.getElementById('toastMsg');
            toastMsg.innerText = message;
            toast.classList.remove('hidden');
            setTimeout(() => {
                toast.classList.add('hidden');
            }, 4000);
        }

        // Initialize Calculator Default state
        calculateFee();
    </script>
</body>
</html>
```
