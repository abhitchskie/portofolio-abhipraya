<script setup>
import { ref, computed } from 'vue'

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
    summary: 'Evaluated the Shopee mobile interface using Jakob Nielsen\'s 10 Usability Heuristics, identifying feature creep and cognitive load bottlenecks to propose a cleaner checkout flow.',
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
  <div class="dossier-root">
    <!-- Header / Navigation -->
    <header class="dossier-header">
      <div class="header-container">
        <div class="brand-section">
          <div class="brand-badge">
            <span class="badge-seal">●</span>
            <span class="badge-text">ABHIPRAYA DESTA HANAPI</span>
          </div>
          <p class="brand-subtitle">UI/UX DESIGNER • FRONT-END DEVELOPER</p>
        </div>

        <nav class="header-nav">
          <a href="#works" class="nav-link">WORKS</a>
          <a href="#skills" class="nav-link">CAPABILITIES</a>
          <a href="#research" class="nav-link">RESEARCH</a>
          <a href="#experience" class="nav-link">EXPERIENCE</a>
          <a href="#contact" class="nav-link">CONTACT</a>
        </nav>

        <div class="status-badge">
          <span class="dot"></span>
          <span class="text">AVAILABLE</span>
        </div>
      </div>
      <div class="header-divider"></div>
    </header>

    <!-- Main Content -->
    <main class="dossier-content">
      <!-- Hero Section -->
      <section class="hero-section">
        <div class="hero-grid">
          <div class="hero-text">
            <p class="overline">COMPUTER SCIENCE — INTERACTIVE MULTIMEDIA</p>
            <h1 class="hero-title">Designing <br/>interfaces that <br/>connect.</h1>
            <p class="hero-intro">I'm Abhipraya Desta Hanapi, a UI/UX designer and front-end engineer from BINUS University. I create digital products where clean architecture meets human-centered design—ensuring interfaces don't just work, but genuinely serve the people using them.</p>
            
            <div class="hero-cta">
              <a href="#works" class="btn-primary">View Works</a>
              <a href="https://github.com/abhitchskie" target="_blank" class="btn-secondary">GitHub</a>
              <a href="https://www.linkedin.com/in/abhipraya-desta-hanapi-760254330" target="_blank" class="btn-secondary">LinkedIn</a>
            </div>
          </div>

          <aside class="hero-aside">
            <div class="profile-container">
              <img :src="'/profile.jpg'" alt="Abhipraya Desta Hanapi" class="profile-image" />
            </div>
            <div class="profile-meta">
              <div class="meta-item">
                <span class="meta-label">EDUCATION</span>
                <p class="meta-value">BINUS University (2024–2028)</p>
              </div>
              <div class="meta-item right">
                <span class="meta-label">FOCUS</span>
                <p class="meta-value">UI/UX & Front-End</p>
              </div>
            </div>
          </aside>
        </div>
      </section>

      <!-- Skills Ticker -->
      <section class="ticker-section">
        <div class="ticker-content">
          <div class="ticker-track">
            <div v-for="n in 2" :key="n" class="ticker-loop">
              <span v-for="skill in stackList" :key="skill + n" class="ticker-item">
                <span class="ticker-slash">/</span>
                {{ skill }}
              </span>
            </div>
          </div>
        </div>
      </section>

      <!-- Works Section -->
      <section id="works" class="works-section">
        <div class="section-header">
          <div>
            <p class="overline">SELECTED ARCHIVE</p>
            <h2 class="section-title">Featured Projects</h2>
          </div>

          <div class="filter-tabs">
            <button
              v-for="cat in categories"
              :key="cat"
              :class="['tab-btn', { active: activeCategory === cat }]"
              @click="activeCategory = cat"
            >
              {{ cat }}
            </button>
          </div>
        </div>

        <div class="works-list">
          <article v-for="project in filteredProjects" :key="project.id" class="project-card">
            <div class="project-image">
              <img
                :src="project.image"
                :alt="project.title"
                onerror="this.src='https://placehold.co/800x500/1a1a2e/71717a?text=' + project.id"
              />
            </div>

            <div class="project-body">
              <div class="project-meta">
                <span class="meta-id">{{ project.id }}</span>
                <span class="meta-cat">{{ project.category }}</span>
                <span class="meta-year">{{ project.year }}</span>
              </div>

              <h3 class="project-title">{{ project.title }}</h3>
              <p class="project-role">{{ project.role }}</p>
              <p class="project-summary">{{ project.summary }}</p>

              <ul class="project-points">
                <li v-for="(pt, idx) in project.points" :key="idx">{{ pt }}</li>
              </ul>

              <div class="project-footer">
                <div class="tech-stack">
                  <span v-for="tech in project.stack" :key="tech">{{ tech }}</span>
                </div>

                <a v-if="project.link !== '#'" :href="project.link" target="_blank" class="link-arrow">
                  {{ project.linkLabel }} →
                </a>
                <span v-else class="link-disabled">{{ project.linkLabel }}</span>
              </div>
            </div>
          </article>
        </div>
      </section>

      <!-- Skills Section -->
      <section id="skills" class="skills-section">
        <div class="section-header">
          <div>
            <p class="overline">TECHNICAL COMPETENCIES</p>
            <h2 class="section-title">Design & Engineering</h2>
          </div>
        </div>

        <div class="skills-grid">
          <div class="skill-card">
            <span class="card-number">01 / DESIGN & RESEARCH</span>
            <h3>Human-Centered UI/UX</h3>
            <p>Structuring intuitive user flows, interactive wireframes, and usability evaluations grounded in heuristic principles.</p>
            <div class="skill-tags">
              <span>Figma</span>
              <span>Wireframing</span>
              <span>Interactive Prototyping</span>
              <span>Heuristic Evaluation</span>
              <span>Usability Testing</span>
            </div>
          </div>

          <div class="skill-card">
            <span class="card-number">02 / DEVELOPMENT</span>
            <h3>Front-End, Mobile & Data</h3>
            <p>Translating interface designs into responsive web applications, mobile layouts, and foundational relational database structures.</p>
            <div class="skill-tags">
              <span>Vue.js 3</span>
              <span>Vite</span>
              <span>JavaScript (ES6+)</span>
              <span>HTML5 & CSS3</span>
              <span>Android Studio</span>
              <span>Oracle Database</span>
            </div>
          </div>

          <div class="skill-card">
            <span class="card-number">03 / ARCHITECTURE & INTERACTIVE</span>
            <h3>Systems & Game Engines</h3>
            <p>Mapping software blueprints, UML specifications, Unity interface layouts, and core gameplay mechanics.</p>
            <div class="skill-tags">
              <span>Unity UI/UX</span>
              <span>UML Diagrams</span>
              <span>Task Flow Modeling</span>
              <span>Game Design Document</span>
              <span>State Flowcharts</span>
            </div>
          </div>

          <div class="skill-card">
            <span class="card-number">04 / COMMUNICATION</span>
            <h3>Languages & Operations</h3>
            <p>Collaborating across technical and non-technical teams, external partnerships, and event logistics.</p>
            <div class="skill-tags">
              <span>Indonesian (Native)</span>
              <span>English (Intermediate)</span>
              <span>External Relations</span>
              <span>Logistics Coordination</span>
            </div>
          </div>
        </div>
      </section>

      <!-- Research Section -->
      <section id="research" class="research-section">
        <div class="section-header">
          <div>
            <p class="overline">ACADEMIC INQUIRY</p>
            <h2 class="section-title">Research & Publications</h2>
          </div>
        </div>

        <div class="publication-list">
          <a
            v-for="paper in publications"
            :key="paper.index"
            :href="paper.link"
            target="_blank"
            class="publication-row"
          >
            <div class="pub-left">
              <span class="pub-index">{{ paper.index }}</span>
              <div class="pub-meta">
                <span class="pub-venue">{{ paper.venue }}</span>
                <span class="pub-date">{{ paper.date }}</span>
              </div>
            </div>

            <div class="pub-center">
              <h3>{{ paper.title }}</h3>
              <p>{{ paper.summary }}</p>
            </div>

            <div class="pub-right">
              <span class="link-arrow">{{ paper.cta }} →</span>
            </div>
          </a>
        </div>
      </section>

      <!-- Experience Section -->
      <section id="experience" class="experience-section">
        <div class="section-header">
          <div>
            <p class="overline">TRACK RECORD & CREDENTIALS</p>
            <h2 class="section-title">Education, Certification & Leadership</h2>
          </div>
        </div>

        <div class="exp-grid">
          <div class="credentials-col">
            <div class="education-block">
              <span class="block-label">ACADEMIC DEGREE</span>
              <h3>Bina Nusantara (BINUS) University</h3>
              <p class="degree-major">Bachelor of Computer Science — Interactive Multimedia</p>
              <p class="degree-period">2024 – 2028</p>
              <p class="degree-desc">Coursework and projects centered on Human-Computer Interaction, UI/UX Design Methodologies, Multimedia Systems, and Front-End Engineering.</p>
            </div>

            <div class="cert-block">
              <div class="cert-header">
                <span class="block-label">CERTIFICATION // ORACLE DEV GYM</span>
                <span class="cert-badge">Grade: 97%</span>
              </div>
              <h3>Databases for Developers: Foundations</h3>
              <p class="cert-issuer">Certificate of Excellence — Oracle Corporation</p>
              <p class="cert-desc">Awarded for achieving a 97% score in relational database fundamentals and SQL foundations taught by Chris Saxon.</p>
              <a
                href="https://www.linkedin.com/in/abhipraya-desta-hanapi-760254330/overlay/Certifications/1652694339/treasury/?profileId=ACoAAFNUjDgBH3kCiIafsclhqceZXDA9sx-Xv9w"
                target="_blank"
                class="link-arrow"
              >
                View Credential →
              </a>
            </div>
          </div>

          <div class="leadership-col">
            <div v-for="(exp, i) in experiences" :key="i" class="leadership-item">
              <div class="item-header">
                <h4>{{ exp.role }}</h4>
                <span class="item-period">{{ exp.period }}</span>
              </div>
              <p class="item-org">{{ exp.org }}</p>
              <p class="item-desc">{{ exp.detail }}</p>
            </div>
          </div>
        </div>
      </section>

      <!-- Contact Section -->
      <section id="contact" class="contact-section">
        <div class="contact-head">
          <p class="overline">DIRECT CHANNELS</p>
          <h2 class="section-title">Let's build something meaningful.</h2>
          <p class="contact-sub">Open for UI/UX Designer, UX Researcher, and Front-End Developer internship roles.</p>
        </div>

        <div class="contact-grid">
          <a href="https://wa.me/62882001143493" target="_blank" class="contact-link">
            <span class="link-label">WHATSAPP</span>
            <strong>0882-0011-43493</strong>
          </a>

          <a href="mailto:abhipraya.hanapi@binus.ac.id" class="contact-link">
            <span class="link-label">EMAIL</span>
            <strong>abhipraya.hanapi@binus.ac.id</strong>
          </a>

          <a href="http://www.linkedin.com/in/abhipraya-desta-hanapi-760254330" target="_blank" class="contact-link">
            <span class="link-label">LINKEDIN</span>
            <strong>Abhipraya Desta Hanapi</strong>
          </a>

          <a href="https://instagram.com/5abhip" target="_blank" class="contact-link">
            <span class="link-label">INSTAGRAM</span>
            <strong>@5abhip</strong>
          </a>
        </div>

        <div class="footer-bar">
          <span>© 2026 Abhipraya Desta Hanapi</span>
          <span class="footer-tech">BUILT WITH VUE 3 & VITE</span>
        </div>
      </section>
    </main>
  </div>
</template>

<style scoped>
/* Color Variables */
:root {
  --navy-dark: #0a0e27;
  --navy-medium: #1a1f3a;
  --navy-light: #2a2f4a;
  --maroon-deep: #3d1f2a;
  --maroon-accent: #6b2d3a;
  --off-white: #f5f3f0;
  --text-primary: #e8e8e8;
  --text-secondary: #b0b0b0;
  --border-light: rgba(255, 255, 255, 0.08);
  --border-medium: rgba(255, 255, 255, 0.14);
  --accent: #c41e3a;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  background-color: var(--navy-dark);
  color: var(--text-primary);
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  line-height: 1.6;
  letter-spacing: 0.5px;
}

.dossier-root {
  position: relative;
  min-height: 100vh;
}

/* Header */
.dossier-header {
  position: sticky;
  top: 0;
  z-index: 50;
  background: rgba(10, 14, 39, 0.95);
  backdrop-filter: blur(8px);
  border-bottom: 1px solid var(--border-light);
}

.header-container {
  max-width: 1280px;
  margin: 0 auto;
  padding: 20px 40px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 40px;
}

.brand-section {
  flex-shrink: 0;
}

.brand-badge {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-primary);
}

.badge-seal {
  width: 6px;
  height: 6px;
  background: var(--accent);
  border-radius: 50%;
  display: inline-block;
}

.brand-subtitle {
  font-size: 0.65rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--text-secondary);
  margin-top: 4px;
}

.header-nav {
  flex: 1;
  display: flex;
  gap: 32px;
  justify-content: center;
}

.nav-link {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-secondary);
  text-decoration: none;
  transition: color 0.3s ease;
  border-bottom: 1px solid transparent;
}

.nav-link:hover {
  color: var(--accent);
  border-bottom-color: var(--accent);
}

.status-badge {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-secondary);
  padding: 6px 12px;
  border: 1px solid var(--border-light);
  border-radius: 2px;
  flex-shrink: 0;
}

.dot {
  width: 5px;
  height: 5px;
  background: #10b981;
  border-radius: 50%;
  display: inline-block;
  box-shadow: 0 0 6px rgba(16, 185, 129, 0.5);
}

.header-divider {
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--border-medium), transparent);
}

/* Main Content */
.dossier-content {
  max-width: 1280px;
  margin: 0 auto;
  padding: 0 40px;
}

/* Hero Section */
.hero-section {
  padding: 80px 0;
  border-bottom: 1px solid var(--border-light);
}

.hero-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.hero-text {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.overline {
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--text-secondary);
}

.hero-title {
  font-size: 3rem;
  font-weight: 700;
  line-height: 1.2;
  color: var(--off-white);
  letter-spacing: -1px;
}

.hero-intro {
  font-size: 0.95rem;
  line-height: 1.7;
  color: var(--text-secondary);
  max-width: 480px;
}

.hero-cta {
  display: flex;
  gap: 16px;
  align-items: center;
  flex-wrap: wrap;
}

.btn-primary,
.btn-secondary {
  font-size: 0.8rem;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  text-decoration: none;
  padding: 12px 28px;
  border-radius: 2px;
  transition: all 0.3s ease;
  display: inline-block;
  cursor: pointer;
  border: none;
}

.btn-primary {
  background: var(--accent);
  color: var(--off-white);
}

.btn-primary:hover {
  background: #a01830;
  transform: translateY(-2px);
}

.btn-secondary {
  background: transparent;
  color: var(--text-primary);
  border: 1px solid var(--border-medium);
}

.btn-secondary:hover {
  border-color: var(--accent);
  color: var(--accent);
}

.hero-aside {
  display: flex;
  flex-direction: column;
  gap: 32px;
}

.profile-container {
  aspect-ratio: 3/4;
  overflow: hidden;
  border: 1px solid var(--border-medium);
  border-radius: 2px;
  background: var(--navy-medium);
}

.profile-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.profile-meta {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.meta-item {
  padding: 16px;
  border: 1px solid var(--border-light);
  border-radius: 2px;
  background: rgba(26, 31, 58, 0.5);
}

.meta-item.right {
  text-align: right;
}

.meta-label {
  font-size: 0.65rem;
  font-weight: 600;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--text-secondary);
  display: block;
  margin-bottom: 6px;
}

.meta-value {
  font-size: 0.85rem;
  color: var(--text-primary);
  font-weight: 500;
}

/* Ticker Section */
.ticker-section {
  padding: 40px 0;
  border-bottom: 1px solid var(--border-light);
  overflow: hidden;
}

.ticker-content {
  position: relative;
}

.ticker-track {
  display: flex;
  animation: scroll-ticker 40s linear infinite;
}

.ticker-loop {
  display: flex;
  gap: 0;
  white-space: nowrap;
  min-width: max-content;
}

.ticker-item {
  font-size: 0.8rem;
  color: var(--text-secondary);
  padding: 0 20px;
  display: inline-flex;
  align-items: center;
  gap: 8px;
}

.ticker-slash {
  color: var(--maroon-accent);
}

@keyframes scroll-ticker {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}

/* Works Section */
.works-section {
  padding: 80px 0;
  border-bottom: 1px solid var(--border-light);
}

.section-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 40px;
  margin-bottom: 60px;
}

.section-title {
  font-size: 2rem;
  font-weight: 700;
  color: var(--off-white);
  letter-spacing: -0.5px;
  margin-top: 8px;
}

.filter-tabs {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
  justify-content: flex-end;
}

.tab-btn {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  background: transparent;
  color: var(--text-secondary);
  border: 1px solid var(--border-light);
  padding: 8px 16px;
  border-radius: 2px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.tab-btn:hover {
  border-color: var(--border-medium);
  color: var(--text-primary);
}

.tab-btn.active {
  background: var(--accent);
  color: var(--off-white);
  border-color: var(--accent);
}

.works-list {
  display: flex;
  flex-direction: column;
  gap: 60px;
}

.project-card {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  align-items: stretch;
  padding-bottom: 60px;
  border-bottom: 1px solid var(--border-light);
}

.project-card:last-child {
  border-bottom: none;
  padding-bottom: 0;
}

.project-image {
  overflow: hidden;
  border-radius: 2px;
  border: 1px solid var(--border-medium);
  aspect-ratio: 4/3;
  background: var(--navy-medium);
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.02);
}

.project-body {
  display: flex;
  flex-direction: column;
  gap: 16px;
  justify-content: space-between;
}

.project-meta {
  display: flex;
  align-items: center;
  gap: 12px;
  font-size: 0.75rem;
}

.meta-id {
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-secondary);
}

.meta-cat {
  color: var(--accent);
}

.meta-year {
  color: var(--text-secondary);
}

.project-title {
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--off-white);
  line-height: 1.3;
}

.project-role {
  font-size: 0.8rem;
  color: var(--text-secondary);
  font-weight: 500;
}

.project-summary {
  font-size: 0.9rem;
  color: var(--text-secondary);
  line-height: 1.6;
}

.project-points {
  list-style: none;
  font-size: 0.85rem;
  color: var(--text-secondary);
  line-height: 1.8;
}

.project-points li {
  padding-left: 20px;
  position: relative;
}

.project-points li:before {
  content: "→";
  position: absolute;
  left: 0;
  color: var(--maroon-accent);
}

.project-footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  padding-top: 16px;
  border-top: 1px solid var(--border-light);
}

.tech-stack {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.tech-stack span {
  font-size: 0.7rem;
  padding: 4px 10px;
  background: rgba(61, 31, 42, 0.5);
  color: var(--text-secondary);
  border-radius: 2px;
  font-weight: 500;
  letter-spacing: 0.05em;
}

.link-arrow {
  font-size: 0.8rem;
  font-weight: 600;
  color: var(--accent);
  text-decoration: none;
  transition: gap 0.3s ease;
}

.link-arrow:hover {
  gap: 4px;
}

.link-disabled {
  font-size: 0.8rem;
  color: var(--text-secondary);
}

/* Skills Section */
.skills-section {
  padding: 80px 0;
  border-bottom: 1px solid var(--border-light);
}

.skills-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 32px;
}

.skill-card {
  padding: 32px;
  border: 1px solid var(--border-light);
  background: linear-gradient(135deg, rgba(26, 31, 58, 0.5), rgba(61, 31, 42, 0.3));
  border-radius: 2px;
  display: flex;
  flex-direction: column;
  gap: 16px;
  transition: all 0.3s ease;
}

.skill-card:hover {
  border-color: var(--border-medium);
  background: linear-gradient(135deg, rgba(26, 31, 58, 0.7), rgba(61, 31, 42, 0.5));
}

.card-number {
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-secondary);
}

.skill-card h3 {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--off-white);
}

.skill-card p {
  font-size: 0.85rem;
  color: var(--text-secondary);
  line-height: 1.6;
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.skill-tags span {
  font-size: 0.7rem;
  padding: 4px 10px;
  background: rgba(107, 45, 58, 0.6);
  color: var(--text-secondary);
  border-radius: 2px;
}

/* Research Section */
.research-section {
  padding: 80px 0;
  border-bottom: 1px solid var(--border-light);
}

.publication-list {
  display: flex;
  flex-direction: column;
  gap: 32px;
}

.publication-row {
  display: grid;
  grid-template-columns: 120px 1fr auto;
  gap: 40px;
  align-items: flex-start;
  padding: 32px;
  border: 1px solid var(--border-light);
  background: linear-gradient(135deg, rgba(26, 31, 58, 0.3), rgba(61, 31, 42, 0.2));
  border-radius: 2px;
  text-decoration: none;
  transition: all 0.3s ease;
}

.publication-row:hover {
  border-color: var(--border-medium);
  background: linear-gradient(135deg, rgba(26, 31, 58, 0.5), rgba(61, 31, 42, 0.3));
}

.pub-left {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.pub-index {
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-secondary);
}

.pub-meta {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.pub-venue {
  font-size: 0.7rem;
  color: var(--accent);
  font-weight: 600;
}

.pub-date {
  font-size: 0.7rem;
  color: var(--text-secondary);
}

.pub-center h3 {
  font-size: 0.95rem;
  font-weight: 600;
  color: var(--off-white);
  margin-bottom: 8px;
}

.pub-center p {
  font-size: 0.8rem;
  color: var(--text-secondary);
  line-height: 1.6;
}

.pub-right {
  text-align: right;
}

/* Experience Section */
.experience-section {
  padding: 80px 0;
  border-bottom: 1px solid var(--border-light);
}

.exp-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
}

.credentials-col {
  display: flex;
  flex-direction: column;
  gap: 32px;
}

.education-block,
.cert-block {
  padding: 32px;
  border: 1px solid var(--border-light);
  background: rgba(26, 31, 58, 0.5);
  border-radius: 2px;
}

.block-label {
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-secondary);
  display: block;
  margin-bottom: 12px;
}

.education-block h3,
.cert-block h3 {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--off-white);
  margin-bottom: 8px;
}

.degree-major,
.cert-issuer {
  font-size: 0.8rem;
  color: var(--accent);
  font-weight: 500;
  margin-bottom: 4px;
}

.degree-period {
  font-size: 0.75rem;
  color: var(--text-secondary);
  margin-bottom: 12px;
}

.degree-desc,
.cert-desc {
  font-size: 0.85rem;
  color: var(--text-secondary);
  line-height: 1.6;
  margin-bottom: 12px;
}

.cert-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
}

.cert-badge {
  font-size: 0.7rem;
  font-weight: 600;
  color: #10b981;
  background: rgba(16, 185, 129, 0.1);
  padding: 4px 10px;
  border-radius: 2px;
}

.leadership-col {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.leadership-item {
  padding: 24px 0;
  border-bottom: 1px solid var(--border-light);
}

.leadership-item:last-child {
  border-bottom: none;
}

.item-header {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin-bottom: 8px;
}

.item-header h4 {
  font-size: 0.95rem;
  font-weight: 600;
  color: var(--off-white);
}

.item-period {
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--text-secondary);
}

.item-org {
  font-size: 0.8rem;
  color: var(--accent);
  font-weight: 500;
  margin-bottom: 6px;
}

.item-desc {
  font-size: 0.8rem;
  color: var(--text-secondary);
  line-height: 1.6;
}

/* Contact Section */
.contact-section {
  padding: 80px 0;
}

.contact-head {
  margin-bottom: 60px;
  max-width: 600px;
}

.contact-sub {
  font-size: 0.9rem;
  color: var(--text-secondary);
  margin-top: 16px;
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
  margin-bottom: 60px;
}

.contact-link {
  padding: 24px;
  border: 1px solid var(--border-light);
  background: linear-gradient(135deg, rgba(26, 31, 58, 0.5), rgba(61, 31, 42, 0.3));
  border-radius: 2px;
  text-decoration: none;
  display: flex;
  flex-direction: column;
  gap: 8px;
  transition: all 0.3s ease;
}

.contact-link:hover {
  border-color: var(--border-medium);
  background: linear-gradient(135deg, rgba(26, 31, 58, 0.7), rgba(61, 31, 42, 0.5));
  transform: translateY(-2px);
}

.link-label {
  font-size: 0.65rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--text-secondary);
}

.contact-link strong {
  font-size: 0.95rem;
  color: var(--text-primary);
  font-weight: 600;
}

.footer-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 40px;
  border-top: 1px solid var(--border-light);
  font-size: 0.75rem;
  color: var(--text-secondary);
  font-weight: 500;
}

.footer-tech {
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

/* Responsive */
@media (max-width: 1024px) {
  .header-container {
    padding: 16px 24px;
    gap: 20px;
  }

  .header-nav {
    gap: 16px;
  }

  .hero-grid {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .section-header {
    flex-direction: column;
    gap: 20px;
  }

  .filter-tabs {
    justify-content: flex-start;
  }

  .project-card {
    grid-template-columns: 1fr;
    gap: 24px;
  }

  .skills-grid {
    grid-template-columns: 1fr;
  }

  .publication-row {
    grid-template-columns: 1fr;
    gap: 16px;
  }

  .pub-right {
    text-align: left;
  }

  .exp-grid {
    grid-template-columns: 1fr;
  }

  .contact-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 768px) {
  .dossier-content {
    padding: 0 20px;
  }

  .hero-section {
    padding: 48px 0;
  }

  .hero-title {
    font-size: 2rem;
  }

  .hero-cta {
    flex-direction: column;
    align-items: flex-start;
  }

  .btn-primary,
  .btn-secondary {
    width: 100%;
    text-align: center;
  }

  .works-section,
  .skills-section,
  .research-section,
  .experience-section,
  .contact-section {
    padding: 48px 0;
  }

  .section-title {
    font-size: 1.5rem;
  }

  .project-title {
    font-size: 1.1rem;
  }

  .ticker-item {
    font-size: 0.7rem;
    padding: 0 12px;
  }
}
</style>
