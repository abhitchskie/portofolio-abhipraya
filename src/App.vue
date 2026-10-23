<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'

const mouseX = ref(0)
const mouseY = ref(0)

const updateSpotlight = (e) => {
  mouseX.value = e.clientX
  mouseY.value = e.clientY
}

onMounted(() => window.addEventListener('mousemove', updateSpotlight))
onUnmounted(() => window.removeEventListener('mousemove', updateSpotlight))

const activeCategory = ref('All')
const categories = ['All', 'UI/UX Design', 'Front-End Web', 'System & Game']

const stackList = [
  'Figma', 'Vue.js 3', 'Vite', 'JavaScript (ES6+)', 'Pinia',
  'Unity UI/UX', 'Oracle Database Foundations', 'Heuristic Evaluation',
  'Wireframing', 'Interactive Prototyping', 'Usability Testing',
  'Android Studio (XML/Java)', 'Python', 'UML Diagrams', 'Game Design (GDD)'
]

const projects = [
  {
    id: '01',
    title: 'SpoJeDy — Web Media Player',
    category: 'Front-End Web',
    year: '2025',
    role: 'UI/UX Designer & Front-End Developer',
    stack: ['Vue.js', 'Vite', 'JavaScript', 'CSS3'],
    image: '/spojedy.png',
    summary: 'Web-based audio and music video player designed with a dark streaming dashboard interface, custom playlist routing, and local playback state.',
    points: [
      'Designed the dashboard layout, sidebar navigation, and media control interface from scratch.',
      'Built modular Vue.js components with Vite for fast page transitions and responsive scaling.',
      'Configured local state management to handle recently played tracks and dark mode toggles.'
    ],
    link: 'https://github.com/abhitchskie/SpoJeDy-Web-Player',
    linkLabel: 'GitHub Repository'
  },
  {
    id: '02',
    title: 'Kecapi Trans — Web Booking Platform',
    category: 'Front-End Web',
    year: '2026',
    role: 'UI/UX Designer & Front-End Developer',
    stack: ['Vue.js', 'Vite', 'Pinia', 'JavaScript'],
    image: '/kecapi-web.png',
    summary: 'End-to-end intercity bus reservation web app covering brand identity, route search, seat selection, and ticket checkout.',
    points: [
      'Created the visual identity, color system, and high-fidelity web wireframes.',
      'Developed the front-end reservation flow using Vue.js and Pinia state management.',
      'Structured dynamic route filtering and departure schedule comparisons.'
    ],
    link: 'https://github.com/abhitchskie/Kecapi-Trans-',
    linkLabel: 'GitHub Repository'
  },
  {
    id: '03',
    title: 'Kecapi Trans Mobile (Facelift)',
    category: 'UI/UX Design',
    year: '2026',
    role: 'UI/UX Designer',
    stack: ['Figma', 'Mobile UI', 'Interactive Prototyping', 'Design System'],
    image: '/kecapi-figma.png',
    summary: 'High-fidelity mobile redesign for the Kecapi Trans booking app, simplifying departure point selection, class filtering, and KPoin loyalty tracking.',
    points: [
      'Redesigned the mobile booking flow across login, city/agency search, and schedule cards.',
      'Applied clear visual hierarchy for ticket pricing, bus classes, and departure timestamps.',
      'Built an interactive Figma prototype to validate screen-to-screen transitions.'
    ],
    link: 'https://www.figma.com/design/Q642YnbfHZuxdMoZm7d007/Kecapi-trans-mobile?node-id=4-183&t=1HDbQPGtPUgmPxVI-0',
    linkLabel: 'Figma Prototype'
  },
  {
    id: '04',
    title: 'ChiMatcha — Beverage App UI',
    category: 'UI/UX Design',
    year: '2026',
    role: 'UI/UX Designer',
    stack: ['Figma', 'Wireframing', 'Mobile Prototyping'],
    image: '/chimatcha.png',
    summary: 'Mobile ordering and loyalty app concept for a contemporary matcha brand, focusing on quick menu customization and reward progress.',
    points: [
      'Designed onboarding, Zen Rewards loyalty cards, and curated drink catalog screens in Figma.',
      'Structured product cards to highlight pricing, ratings, and quick-add actions.',
      'Implemented mobile layout views in Android Studio using XML and Java.'
    ],
    link: 'https://www.figma.com/design/a9SmzDuplEdBXR5p0Kf6zA/UX-AOL-Project?node-id=0-1&t=yZkDEC1UE1KbU5Mb-1',
    linkLabel: 'Figma Preview'
  },
  {
    id: '05',
    title: 'KawanAksi — Volunteer Matching Platform',
    category: 'Front-End Web',
    year: '2026',
    role: 'System Architect, UI/UX & Front-End Developer',
    stack: ['Vue.js', 'Figma', 'UML Diagrams', 'User Flows'],
    image: '/kawanaksi.png',
    summary: 'Social platform connecting student volunteers with community service organizers through structured task flows and role matching.',
    points: [
      'Authored complete UML diagrams and software architecture specifications.',
      'Mapped end-to-end user flows for volunteer onboarding and event registration.',
      'Developed the front-end web interface to streamline community campaign discovery.'
    ],
    link: 'https://github.com/abhitchskie/KawanAksi',
    linkLabel: 'GitHub Repository'
  },
  {
    id: '06',
    title: 'Floradex — Unity Interactive Application',
    category: 'UI/UX Design',
    year: '2026',
    role: 'UI/UX Designer',
    stack: ['Unity', 'UI/UX Design', 'Figma', 'Interactive HUD'],
    image: '/floradex.png',
    summary: 'Designed the user interface, navigation flows, and visual HUD components for Floradex, an interactive Unity-based application.',
    points: [
      'Crafted intuitive in-app navigation menus, information cards, and visual assets tailored for the Unity environment.',
      'Established clear typography and icon hierarchy to keep botanical data readable across interactive views.',
      'Collaborated with the Unity development team to translate UI layouts into responsive canvas components.'
    ],
    link: 'https://www.linkedin.com/safety/go/?url=https%3A%2F%2Flnkd.in%2FgTBz3ps9&urlhash=96mI&mt=uk4gyTJ0TnqBKgF2D5mbwz337DVcdiUV172b_VO7LtKyacxWdRb8FVr15RHrlZTOrSv5-wXYOKgzinQam5KaCjmWewfyGc2WQR2e8QWT4WU5kSHfHwvz-o3pMbk&isSdui=true&lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base%3BQkynhgZeQd6Gk9sahS1wEg%3D%3D',
    linkLabel: 'View Project'
  },
  {
    id: '07',
    title: 'Dodolan BeeL — 3D Billiard Simulation',
    category: 'System & Game',
    year: '2026',
    role: 'Game Designer',
    stack: ['Game Design Document', 'System Flowcharts', '3D Mechanics'],
    image: '/dodolan-beel.png',
    summary: 'Comprehensive Game Design Document (GDD) and state flowcharts for a first-person 3D billiard simulation game.',
    points: [
      'Defined core cue physics rules, aiming mechanics, and first-person camera transitions.',
      'Mapped complete game state flowcharts from main menu to match resolution.',
      'Designed minimalist HUD wireframes for shot power and spin control.'
    ],
    link: '#',
    linkLabel: 'GDD Documentation'
  }
]

const filteredProjects = computed(() => {
  if (activeCategory.value === 'All') return projects
  return projects.filter(item => item.category === activeCategory.value)
})

const publications = [
  {
    index: '01',
    date: 'June 2026',
    venue: 'ICISS 2026 Submission',
    title: 'User Flow Optimization in Mobile Application through Heuristic-Based Interface Design',
    summary: 'Evaluated the Shopee mobile interface using Jakob Nielsen’s 10 Usability Heuristics, identifying feature creep and cognitive load bottlenecks to propose a cleaner checkout flow.',
    link: 'https://drive.google.com/drive/folders/1WV5Hc8y0gee9C_vcoFZ2xEq_5y--Wcee?usp=drive_link',
    cta: 'Read Paper'
  },
  {
    index: '02',
    date: 'December 2025',
    venue: 'Zenodo Publication',
    title: 'Automatic Fan Speed Control System Based on Room Temperature and Humidity Using Tsukamoto Fuzzy Logic',
    summary: 'Developed and tested a rule-based Tsukamoto fuzzy inference model in Python to automate fan speed adjustments based on multi-sensor room data.',
    link: 'https://zenodo.org/records/17954364',
    cta: 'Zenodo Record'
  }
]

const experiences = [
  {
    role: 'External Coordinator',
    org: 'UKM Futsal BINUS University',
    period: 'Jan 2026 – Present',
    detail: 'Leading external communications, inter-university sparring partnerships, and sponsorship outreach.'
  },
  {
    role: 'Equipment Coordinator',
    org: 'Community Service Program (PKM)',
    period: '2025 & 2026',
    detail: 'Planned field logistics, inventory checklists, and equipment readiness for annual community service events.'
  },
  {
    role: 'Equipment Division Head',
    org: 'UKM Futsal Welcoming Party',
    period: 'Oct 2025',
    detail: 'Coordinated venue preparation, sound and sport equipment setup, and on-site logistics for new members.'
  },
  {
    role: 'Equipment Division Staff',
    org: 'UKM Expo First Year Program BINUS',
    period: '2025',
    detail: 'Handled booth construction, inventory transport, and equipment security during freshman orientation.'
  }
]
</script>

<template>
  <div class="page-root">
    <div
      class="spotlight-layer"
      :style="{
        background: `radial-gradient(600px circle at ${mouseX}px ${mouseY}px, rgba(255, 255, 255, 0.045), transparent 40%)`
      }"
    ></div>

    <header class="top-nav">
      <div class="nav-container">
        <a href="#" class="brand-id">
          
          <span class="brand-text">Abhipraya Desta Hanapi</span>
        </a>

        <nav class="nav-links">
          <a href="#works">Works</a>
          <a href="#skills">Capabilities</a>
          <a href="#research">Research</a>
          <a href="#experience">Experience</a>
          <a href="#contact">Contact</a>
        </nav>

        <div class="availability-tag">
          <span class="status-led"></span>
          <span>Available for Internship</span>
        </div>
      </div>
    </header>

    <main class="structural-grid">
      <section class="hero-block">
        <span class="corner-plus top-left">+</span>
        <span class="corner-plus top-right">+</span>

        <div class="hero-split">
          <div class="hero-main">
            <p class="eyebrow-mono">COMPUTER SCIENCE — INTERACTIVE MULTIMEDIA @ BINUS</p>

            <h1 class="hero-display">
              Designing interfaces, <br />
              <span class="serif-italic">connecting humans.</span>
            </h1>

            <p class="hero-paragraph">
              I'm <strong>Abhipraya Desta Hanapi</strong>. Coming from a technical Computer Science background with a strong interest in the social sciences and humanities, I focus on <strong>UI/UX Design</strong>, <strong>UX Research</strong>, and <strong>Front-End Web Development</strong>.
            </p>
            <p class="hero-paragraph muted">
              I build digital products where clean component architecture meets human-centered usability—making sure interfaces don't just run without errors, but genuinely help the people using them.
            </p>

            <div class="hero-cta-row">
              <a href="#works" class="btn-solid">
                View Selected Works
                <svg class="icon-14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
              </a>
              <a href="https://github.com/abhitchskie" target="_blank" class="btn-outline">
                <svg class="icon-16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
                GitHub
              </a>
              <a href="http://www.linkedin.com/in/abhipraya-desta-hanapi-760254330" target="_blank" class="btn-outline">
                <svg class="icon-16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
                LinkedIn
              </a>
            </div>
          </div>

          <aside class="hero-portrait-col">
            <div class="portrait-frame">
              <img :src="'/profile.jpg'" alt="Abhipraya Desta Hanapi" onerror="this.src='https://placehold.co/440x520/121215/a1a1aa?text=Abhipraya+Desta'" />
            </div>
            <div class="portrait-caption">
              <div>
                <span class="caption-label">EDUCATION</span>
                <p>BINUS University (2024–2028)</p>
              </div>
              <div class="text-right">
                <span class="caption-label">FOCUS</span>
                <p>UI/UX & Front-End</p>
              </div>
            </div>
          </aside>
        </div>
      </section>

      <div class="ticker-strip">
        <div class="ticker-track">
          <div v-for="n in 2" :key="n" class="ticker-group">
            <span v-for="item in stackList" :key="item + n" class="ticker-item">
              <span class="ticker-sep">/</span>
              {{ item }}
            </span>
          </div>
        </div>
      </div>

      <section id="works" class="grid-section">
        <span class="corner-plus top-left">+</span>
        <span class="corner-plus top-right">+</span>

        <div class="section-bar">
          <div>
            <p class="eyebrow-mono">SELECTED ARCHIVE (01 — 07)</p>
            <h2 class="section-title">Featured <span class="serif-italic">Projects</span></h2>
          </div>

          <div class="filter-group" role="tablist">
            <button
              v-for="cat in categories"
              :key="cat"
              :class="['filter-pill', { active: activeCategory === cat }]"
              @click="activeCategory = cat"
            >
              {{ cat }}
            </button>
          </div>
        </div>

        <div class="works-stack">
          <article v-for="project in filteredProjects" :key="project.id" class="work-row">
            <div class="work-stage">
              <div class="stage-canvas">
                <img
                  :src="project.image"
                  :alt="project.title"
                  onerror="this.src='https://placehold.co/800x500/121215/71717a?text=Preview+' + project.id"
                />
              </div>
            </div>

            <div class="work-info">
              <div class="work-meta">
                <span class="mono-index">{{ project.id }}</span>
                <span class="meta-sep">•</span>
                <span class="meta-cat">{{ project.category }}</span>
                <span class="meta-year">{{ project.year }}</span>
              </div>

              <h3 class="work-heading">{{ project.title }}</h3>
              <p class="work-role">{{ project.role }}</p>
              <p class="work-summary">{{ project.summary }}</p>

              <ul class="work-points">
                <li v-for="(pt, idx) in project.points" :key="idx">{{ pt }}</li>
              </ul>

              <div class="work-bottom">
                <div class="tech-pills">
                  <span v-for="tech in project.stack" :key="tech">{{ tech }}</span>
                </div>

                <a v-if="project.link !== '#'" :href="project.link" target="_blank" class="work-link">
                  {{ project.linkLabel }}
                  <svg class="icon-14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg>
                </a>
                <span v-else class="work-link-muted">{{ project.linkLabel }}</span>
              </div>
            </div>
          </article>
        </div>
      </section>

      <section id="skills" class="grid-section">
        <span class="corner-plus top-left">+</span>
        <span class="corner-plus top-right">+</span>

        <div class="section-bar">
          <div>
            <p class="eyebrow-mono">TECHNICAL COMPETENCIES</p>
            <h2 class="section-title">Design & <span class="serif-italic">Engineering</span></h2>
          </div>
        </div>

        <div class="capabilities-matrix">
          <div class="matrix-cell">
            <span class="mono-index">01 / DESIGN & RESEARCH</span>
            <h3>Human-Centered UI/UX</h3>
            <p>Structuring intuitive user flows, interactive wireframes, and usability evaluations grounded in heuristic principles.</p>
            <div class="tech-pills">
              <span>Figma</span>
              <span>Canva</span>
              <span>Wireframing</span>
              <span>Interactive Prototyping</span>
              <span>Heuristic Evaluation</span>
              <span>Usability Testing</span>
            </div>
          </div>

          <div class="matrix-cell">
            <span class="mono-index">02 / DEVELOPMENT</span>
            <h3>Front-End, Mobile & Data</h3>
            <p>Translating interface designs into responsive web applications, mobile layouts, and foundational relational database structures.</p>
            <div class="tech-pills">
              <span>Vue.js 3</span>
              <span>Vite</span>
              <span>Pinia</span>
              <span>JavaScript (ES6+)</span>
              <span>HTML5 & CSS3</span>
              <span>Android Studio (XML/Java)</span>
              <span>Oracle Database Foundations</span>
              <span>Python</span>
            </div>
          </div>

          <div class="matrix-cell">
            <span class="mono-index">03 / ARCHITECTURE & INTERACTIVE</span>
            <h3>Systems & Game Engines</h3>
            <p>Mapping software blueprints, UML specifications, Unity interface layouts, and core gameplay mechanics.</p>
            <div class="tech-pills">
              <span>Unity UI/UX</span>
              <span>UML Diagrams</span>
              <span>Task Flow Modeling</span>
              <span>Game Design Document (GDD)</span>
              <span>State Flowcharts</span>
            </div>
          </div>

          <div class="matrix-cell">
            <span class="mono-index">04 / COMMUNICATION</span>
            <h3>Languages & Operations</h3>
            <p>Collaborating across technical and non-technical teams, external partnerships, and event logistics.</p>
            <div class="tech-pills">
              <span>Indonesian (Native)</span>
              <span>English (Intermediate)</span>
              <span>External Relations</span>
              <span>Logistics Coordination</span>
            </div>
          </div>
        </div>
      </section>

      <section id="research" class="grid-section">
        <span class="corner-plus top-left">+</span>
        <span class="corner-plus top-right">+</span>

        <div class="section-bar">
          <div>
            <p class="eyebrow-mono">ACADEMIC INQUIRY</p>
            <h2 class="section-title">Research & <span class="serif-italic">Papers</span></h2>
          </div>
        </div>

        <div class="index-list">
          <a
            v-for="paper in publications"
            :key="paper.index"
            :href="paper.link"
            target="_blank"
            class="index-row"
          >
            <div class="index-left">
              <span class="mono-index">{{ paper.index }}</span>
              <div>
                <span class="row-venue">{{ paper.venue }}</span>
                <span class="row-date">{{ paper.date }}</span>
              </div>
            </div>

            <div class="index-center">
              <h3>{{ paper.title }}</h3>
              <p>{{ paper.summary }}</p>
            </div>

            <div class="index-right">
              <span class="work-link">
                {{ paper.cta }}
                <svg class="icon-14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg>
              </span>
            </div>
          </a>
        </div>
      </section>

      <section id="experience" class="grid-section">
        <span class="corner-plus top-left">+</span>
        <span class="corner-plus top-right">+</span>

        <div class="section-bar">
          <div>
            <p class="eyebrow-mono">TRACK RECORD & CREDENTIALS</p>
            <h2 class="section-title">Education, Certification & <span class="serif-italic">Leadership</span></h2>
          </div>
        </div>

        <div class="exp-split">
          <div class="left-credentials">
            <div class="edu-column">
              <span class="mono-index">ACADEMIC DEGREE</span>
              <h3>Bina Nusantara (BINUS) University</h3>
              <p class="edu-major">Bachelor of Computer Science — Interactive Multimedia</p>
              <p class="edu-period">2024 – 2028</p>
              <p class="edu-desc">Coursework and projects centered on Human-Computer Interaction, UI/UX Design Methodologies, Multimedia Systems, and Front-End Engineering.</p>
            </div>

            <div class="edu-column cert-card">
              <div class="cert-header">
                <span class="mono-index">CERTIFICATION // ORACLE DEV GYM</span>
                <span class="score-pill">Grade: 97%</span>
              </div>
              <h3>Databases for Developers: Foundations</h3>
              <p class="edu-major">Certificate of Excellence — Oracle Corporation</p>
              <p class="edu-desc cert-desc">Awarded for achieving a 97% score in relational database fundamentals and SQL foundations taught by Chris Saxon.</p>
              <a
                href="https://www.linkedin.com/in/abhipraya-desta-hanapi-760254330/overlay/Certifications/1652694339/treasury/?profileId=ACoAAFNUjDgBH3kCiIafsclhqceZXDA9sx-Xv9w"
                target="_blank"
                class="work-link"
              >
                View Credential on LinkedIn
                <svg class="icon-14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M7 17L17 7M17 7H7M17 7V17"/></svg>
              </a>
            </div>
          </div>

          <div class="org-column">
            <div v-for="(item, i) in experiences" :key="i" class="org-row">
              <div class="org-top">
                <h4>{{ item.role }}</h4>
                <span class="mono-index">{{ item.period }}</span>
              </div>
              <p class="org-name">{{ item.org }}</p>
              <p class="org-detail">{{ item.detail }}</p>
            </div>
          </div>
        </div>
      </section>

      <footer id="contact" class="grid-section footer-block">
        <span class="corner-plus top-left">+</span>
        <span class="corner-plus top-right">+</span>

        <div class="footer-head">
          <p class="eyebrow-mono">DIRECT CHANNELS</p>
          <h2 class="footer-title">Let's build something <span class="serif-italic">meaningful.</span></h2>
          <p class="footer-sub">Open for UI/UX Designer, UX Researcher, and Front-End Developer internship roles.</p>
        </div>

        <div class="contact-matrix">
          <a href="https://wa.me/62882001143493" target="_blank" class="contact-cell">
            <div class="contact-top">
              <svg class="icon-18" viewBox="0 0 24 24" fill="currentColor"><path d="M12.031 6.172c-3.181 0-5.767 2.586-5.768 5.766-.001 1.298.38 2.27 1.019 3.287l-.582 2.128 2.182-.573c.978.58 1.911.928 3.145.929 3.178 0 5.767-2.587 5.768-5.766.001-3.187-2.575-5.77-5.764-5.771zm3.392 8.244c-.144.405-.837.774-1.17.824-.299.045-.677.063-1.092-.069-.252-.08-.575-.187-.988-.365-1.739-.751-2.874-2.502-2.961-2.617-.087-.116-.708-.94-.708-1.793s.448-1.273.607-1.446c.159-.173.346-.217.462-.217l.332.006c.106.005.249-.04.39.298.144.347.491 1.2.534 1.287.043.087.072.188.014.304-.058.116-.087.188-.173.289l-.26.304c-.087.086-.177.18-.076.354.101.174.449.741.964 1.201.662.591 1.221.774 1.394.86s.274.072.376-.043c.101-.116.433-.506.549-.68.116-.173.231-.145.39-.087s1.011.477 1.184.564.289.13.332.202c.045.072.045.419-.1.824zm-3.423-14.416c-6.627 0-12 5.373-12 12 0 2.126.556 4.122 1.529 5.854l-1.529 5.586 5.735-1.504c1.693.922 3.633 1.448 5.699 1.448 6.627 0 12-5.373 12-12 0-6.627-5.373-12-12-12z"/></svg>
              <span class="mono-index">WHATSAPP</span>
            </div>
            <strong>0882-0011-43493</strong>
          </a>

          <a href="mailto:abhipraya.hanapi@binus.ac.id" class="contact-cell">
            <div class="contact-top">
              <svg class="icon-18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="2" y="4" width="20" height="16" rx="3"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
              <span class="mono-index">EMAIL</span>
            </div>
            <strong>abhipraya.hanapi@binus.ac.id</strong>
          </a>

          <a href="http://www.linkedin.com/in/abhipraya-desta-hanapi-760254330" target="_blank" class="contact-cell">
            <div class="contact-top">
              <svg class="icon-18" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
              <span class="mono-index">LINKEDIN</span>
            </div>
            <strong>Abhipraya Desta Hanapi</strong>
          </a>

          <a href="https://instagram.com/5abhip" target="_blank" class="contact-cell">
            <div class="contact-top">
              <svg class="icon-18" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
              <span class="mono-index">INSTAGRAM</span>
            </div>
            <strong>@5abhip</strong>
          </a>
        </div>

        <div class="footer-bar">
          <span>© 2026 Abhipraya Desta Hanapi</span>
          <span class="mono-index">BUILT WITH VUE 3 & VITE</span>
        </div>
      </footer>
    </main>
  </div>
</template>

<style scoped>
.page-root {
  position: relative;
  min-height: 100vh;
  background-color: #09090b;
  color: #f4f4f5;
}

.spotlight-layer {
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 1;
}

.serif-italic {
  font-family: 'Instrument Serif', Georgia, serif;
  font-style: italic;
  font-weight: 400;
  color: #e4e4e7;
}

.eyebrow-mono,
.mono-index,
.caption-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.72rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: #71717a;
}

.top-nav {
  position: sticky;
  top: 0;
  z-index: 40;
  background: rgba(9, 9, 11, 0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}

.nav-container {
  max-width: 1040px;
  margin: 0 auto;
  padding: 0 28px;
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-left: 1px solid rgba(255, 255, 255, 0.08);
  border-right: 1px solid rgba(255, 255, 255, 0.08);
}

.brand-id {
  display: flex;
  align-items: center;
  gap: 10px;
  text-decoration: none;
  color: #f4f4f5;
  font-weight: 600;
  font-size: 0.9rem;
}

.brand-monogram {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.7rem;
  padding: 3px 8px;
  background: #18181b;
  border: 1px solid rgba(255, 255, 255, 0.14);
  border-radius: 4px;
}

.nav-links {
  display: flex;
  gap: 24px;
}

.nav-links a {
  text-decoration: none;
  color: #a1a1aa;
  font-size: 0.85rem;
  font-weight: 500;
  transition: color 0.2s;
}

.nav-links a:hover {
  color: #ffffff;
}

.availability-tag {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-size: 0.76rem;
  color: #d4d4d8;
  background: #121215;
  border: 1px solid rgba(255, 255, 255, 0.09);
  padding: 5px 12px;
  border-radius: 999px;
}

.status-led {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: #10b981;
  box-shadow: 0 0 8px rgba(16, 185, 129, 0.6);
}

.structural-grid {
  position: relative;
  z-index: 2;
  max-width: 1040px;
  margin: 0 auto;
  border-left: 1px solid rgba(255, 255, 255, 0.08);
  border-right: 1px solid rgba(255, 255, 255, 0.08);
}

.hero-block,
.grid-section {
  position: relative;
  padding: 72px 40px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}

.corner-plus {
  position: absolute;
  top: -9px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.85rem;
  color: #52525b;
  pointer-events: none;
  user-select: none;
}

.top-left {
  left: -5px;
}

.top-right {
  right: -5px;
}

.hero-split {
  display: grid;
  grid-template-columns: 1.35fr 0.65fr;
  gap: 48px;
  align-items: center;
}

.hero-display {
  font-size: clamp(2.6rem, 4.8vw, 4rem);
  font-weight: 700;
  line-height: 1.06;
  letter-spacing: -0.03em;
  margin: 14px 0 24px;
}

.hero-display .serif-italic {
  font-size: 1.08em;
  font-weight: 400;
}

.hero-paragraph {
  font-size: 1rem;
  color: #e4e4e7;
  margin-bottom: 14px;
  max-width: 580px;
}

.hero-paragraph.muted {
  color: #a1a1aa;
  font-size: 0.94rem;
  margin-bottom: 32px;
}

.hero-cta-row {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.btn-solid {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: #f4f4f5;
  color: #09090b;
  text-decoration: none;
  padding: 11px 20px;
  border-radius: 8px;
  font-size: 0.86rem;
  font-weight: 600;
  min-height: 44px;
  transition: opacity 0.2s, transform 0.2s;
}

.btn-solid:hover {
  opacity: 0.9;
  transform: translateY(-1px);
}

.btn-outline {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: #121215;
  border: 1px solid rgba(255, 255, 255, 0.12);
  color: #e4e4e7;
  text-decoration: none;
  padding: 11px 18px;
  border-radius: 8px;
  font-size: 0.86rem;
  font-weight: 500;
  min-height: 44px;
  transition: border-color 0.2s, background 0.2s;
}

.btn-outline:hover {
  background: #18181c;
  border-color: rgba(255, 255, 255, 0.28);
}

.icon-14 {
  width: 14px;
  height: 14px;
}

.icon-16 {
  width: 16px;
  height: 16px;
}

.icon-18 {
  width: 18px;
  height: 18px;
}

.hero-portrait-col {
  background: #111114;
  border: 1px solid rgba(255, 255, 255, 0.09);
  border-radius: 12px;
  padding: 12px;
}

.portrait-frame {
  border-radius: 8px;
  overflow: hidden;
  background: #09090b;
}

.portrait-frame img {
  width: 100%;
  height: 340px;
  object-fit: cover;
  display: block;
}

.portrait-caption {
  display: flex;
  justify-content: space-between;
  padding-top: 12px;
}

.portrait-caption p {
  font-size: 0.8rem;
  color: #d4d4d8;
  font-weight: 500;
  margin-top: 2px;
}

.text-right {
  text-align: right;
}

.ticker-strip {
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  background: #0c0c0f;
  padding: 14px 0;
  overflow: hidden;
  mask-image: linear-gradient(to right, transparent, black 10%, black 90%, transparent);
}

.ticker-track {
  display: flex;
  width: max-content;
  animation: tickerSlide 30s linear infinite;
}

.ticker-group {
  display: flex;
  gap: 24px;
  padding-right: 24px;
}

.ticker-item {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.78rem;
  color: #a1a1aa;
  white-space: nowrap;
  display: inline-flex;
  align-items: center;
  gap: 10px;
}

.ticker-sep {
  color: #3f3f46;
}

@keyframes tickerSlide {
  from { transform: translateX(0); }
  to { transform: translateX(-50%); }
}

.section-bar {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  flex-wrap: wrap;
  gap: 20px;
  margin-bottom: 40px;
}

.section-title {
  font-size: clamp(1.85rem, 3vw, 2.5rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-top: 6px;
}

.filter-group {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.filter-pill {
  background: #121215;
  border: 1px solid rgba(255, 255, 255, 0.08);
  color: #a1a1aa;
  padding: 8px 14px;
  border-radius: 6px;
  font-size: 0.8rem;
  font-weight: 500;
  min-height: 38px;
  cursor: pointer;
  transition: all 0.2s;
}

.filter-pill.active,
.filter-pill:hover {
  background: #f4f4f5;
  color: #09090b;
  border-color: #f4f4f5;
}

.works-stack {
  display: flex;
  flex-direction: column;
  gap: 32px;
}

.work-row {
  display: grid;
  grid-template-columns: 1.05fr 0.95fr;
  gap: 32px;
  background: #0e0e11;
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 12px;
  padding: 20px;
  align-items: center;
  transition: border-color 0.25s;
}

.work-row:hover {
  border-color: rgba(255, 255, 255, 0.22);
}

.stage-canvas {
  aspect-ratio: 16 / 10;
  width: 100%;
  background: radial-gradient(circle at center, #18181d 0%, #09090b 90%);
  border: 1px solid rgba(255, 255, 255, 0.07);
  border-radius: 8px;
  padding: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.stage-canvas img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  border-radius: 4px;
  transition: transform 0.35s ease;
}

.work-row:hover .stage-canvas img {
  transform: scale(1.02);
}

.work-info {
  display: flex;
  flex-direction: column;
}

.work-meta {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 10px;
}

.meta-sep {
  color: #3f3f46;
}

.meta-cat {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.72rem;
  color: #d4d4d8;
  text-transform: uppercase;
}

.meta-year {
  margin-left: auto;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.72rem;
  color: #71717a;
}

.work-heading {
  font-size: 1.4rem;
  font-weight: 700;
  letter-spacing: -0.02em;
  margin-bottom: 4px;
}

.work-role {
  font-size: 0.84rem;
  color: #a1a1aa;
  margin-bottom: 12px;
}

.work-summary {
  font-size: 0.9rem;
  color: #d4d4d8;
  margin-bottom: 12px;
}

.work-points {
  padding-left: 18px;
  font-size: 0.84rem;
  color: #a1a1aa;
  margin-bottom: 20px;
}

.work-points li {
  margin-bottom: 4px;
}

.work-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 12px;
  padding-top: 14px;
  border-top: 1px solid rgba(255, 255, 255, 0.07);
}

.tech-pills {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.tech-pills span {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.68rem;
  background: #141418;
  border: 1px solid rgba(255, 255, 255, 0.08);
  color: #d4d4d8;
  padding: 4px 9px;
  border-radius: 4px;
}

.work-link {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  color: #f4f4f5;
  text-decoration: none;
  font-size: 0.84rem;
  font-weight: 600;
}

.work-link:hover {
  text-decoration: underline;
}

.work-link-muted {
  font-size: 0.8rem;
  color: #52525b;
}

.capabilities-matrix {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 12px;
  overflow: hidden;
}

.matrix-cell {
  padding: 28px;
  background: #0e0e11;
  border-right: 1px solid rgba(255, 255, 255, 0.08);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}

.matrix-cell:nth-child(2n) {
  border-right: none;
}

.matrix-cell:nth-last-child(-n + 2) {
  border-bottom: none;
}

.matrix-cell h3 {
  font-size: 1.2rem;
  margin: 10px 0 8px;
}

.matrix-cell p {
  font-size: 0.88rem;
  color: #a1a1aa;
  margin-bottom: 18px;
}

.index-list {
  display: flex;
  flex-direction: column;
  border-top: 1px solid rgba(255, 255, 255, 0.08);
}

.index-row {
  display: grid;
  grid-template-columns: 0.45fr 1.2fr 0.35fr;
  gap: 24px;
  padding: 24px 16px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  text-decoration: none;
  color: inherit;
  align-items: start;
  transition: background 0.2s;
}

.index-row:hover {
  background: rgba(255, 255, 255, 0.025);
}

.index-left {
  display: flex;
  gap: 14px;
  align-items: baseline;
}

.row-venue {
  display: block;
  font-size: 0.86rem;
  font-weight: 600;
  color: #e4e4e7;
}

.row-date {
  font-size: 0.78rem;
  color: #71717a;
}

.index-center h3 {
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 6px;
}

.index-center p {
  font-size: 0.88rem;
  color: #a1a1aa;
}

.index-right {
  text-align: right;
}

.exp-split {
  display: grid;
  grid-template-columns: 0.85fr 1.15fr;
  gap: 40px;
}

.left-credentials {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.edu-column {
  background: #0e0e11;
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 12px;
  padding: 26px;
}

.edu-column h3 {
  font-size: 1.25rem;
  margin: 10px 0 4px;
}

.edu-major {
  color: #e4e4e7;
  font-size: 0.88rem;
  font-weight: 500;
}

.edu-period {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.75rem;
  color: #71717a;
  margin: 6px 0 14px;
}

.edu-desc {
  font-size: 0.86rem;
  color: #a1a1aa;
}

.cert-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 8px;
}

.score-pill {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.68rem;
  background: #18181b;
  border: 1px solid rgba(255, 255, 255, 0.14);
  color: #f4f4f5;
  padding: 3px 8px;
  border-radius: 4px;
}

.cert-desc {
  margin: 10px 0 16px;
}

.org-column {
  display: flex;
  flex-direction: column;
  border-top: 1px solid rgba(255, 255, 255, 0.08);
}

.org-row {
  padding: 20px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
}

.org-top {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  gap: 12px;
}

.org-top h4 {
  font-size: 1.02rem;
}

.org-name {
  font-size: 0.86rem;
  color: #d4d4d8;
  margin: 2px 0 6px;
}

.org-detail {
  font-size: 0.86rem;
  color: #a1a1aa;
}

.footer-block {
  border-bottom: none;
}

.footer-head {
  max-width: 540px;
  margin-bottom: 32px;
}

.footer-title {
  font-size: clamp(2rem, 3.6vw, 3rem);
  font-weight: 700;
  letter-spacing: -0.02em;
  margin: 6px 0 10px;
}

.footer-sub {
  color: #a1a1aa;
  font-size: 0.94rem;
}

.contact-matrix {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 12px;
  overflow: hidden;
  margin-bottom: 40px;
}

.contact-cell {
  background: #0e0e11;
  padding: 20px;
  border-right: 1px solid rgba(255, 255, 255, 0.08);
  text-decoration: none;
  color: #f4f4f5;
  display: flex;
  flex-direction: column;
  gap: 12px;
  transition: background 0.2s;
}

.contact-cell:last-child {
  border-right: none;
}

.contact-cell:hover {
  background: #151519;
}

.contact-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  color: #a1a1aa;
}

.contact-cell strong {
  font-size: 0.83rem;
  font-weight: 500;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.footer-bar {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 12px;
  font-size: 0.8rem;
  color: #71717a;
}

@media (max-width: 900px) {
  .hero-block,
  .grid-section {
    padding: 48px 20px;
  }
  .hero-split,
  .work-row,
  .capabilities-matrix,
  .index-row,
  .exp-split,
  .contact-matrix {
    grid-template-columns: 1fr;
  }
  .nav-links {
    display: none;
  }
  .matrix-cell,
  .contact-cell {
    border-right: none;
    border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  }
  .index-right {
    text-align: left;
  }
}
</style>