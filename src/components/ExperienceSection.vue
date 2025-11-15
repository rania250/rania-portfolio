<template>
  <section id="experience" class="section experience-section">
    <div class="container">
      <div class="section-header">
        <p class="section-subtitle">Explorez Mes</p>
        <h2 class="section-title">Compétences</h2>
      </div>

      <div class="skills-grid">
        <div v-for="(category, index) in skillsCategories" :key="index" class="skill-category card">
          <div class="category-icon">
            <component :is="category.icon" />
          </div>
          <h3 class="category-title">{{ category.title }}</h3>
          <div class="skills-list">
            <div 
              v-for="skill in category.skills" 
              :key="skill.name" 
              class="skill-item"
            >
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-level">{{ skill.level }}</span>
              </div>
              <div class="skill-bar">
                <div 
                  class="skill-progress" 
                  :style="{ width: getSkillWidth(skill.level) }"
                ></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { h } from 'vue'

interface Skill {
  name: string
  level: string
}

interface SkillCategory {
  title: string
  icon: any
  skills: Skill[]
}

const CodeIcon = () => h('svg', {
  xmlns: 'http://www.w3.org/2000/svg',
  width: '40',
  height: '40',
  viewBox: '0 0 24 24',
  fill: 'none',
  stroke: 'currentColor',
  'stroke-width': '2'
}, [
  h('polyline', { points: '16 18 22 12 16 6' }),
  h('polyline', { points: '8 6 2 12 8 18' })
])

const DatabaseIcon = () => h('svg', {
  xmlns: 'http://www.w3.org/2000/svg',
  width: '40',
  height: '40',
  viewBox: '0 0 24 24',
  fill: 'none',
  stroke: 'currentColor',
  'stroke-width': '2'
}, [
  h('ellipse', { cx: '12', cy: '5', rx: '9', ry: '3' }),
  h('path', { d: 'M21 12c0 1.66-4 3-9 3s-9-1.34-9-3' }),
  h('path', { d: 'M3 5v14c0 1.66 4 3 9 3s9-1.34 9-3V5' })
])

const skillsCategories: SkillCategory[] = [
  {
    title: 'Front-end',
    icon: CodeIcon,
    skills: [
      { name: 'HTML/CSS', level: 'Expérimentée' },
      { name: 'JavaScript', level: 'Expérimentée' },
      { name: 'Vue.js 3', level: 'Expérimentée' },
      { name: 'Bootstrap', level: 'Expérimentée' },
      { name: 'Sass', level: 'Intermédiaire' }
    ]
  },
  {
    title: 'Back-end',
    icon: DatabaseIcon,
    skills: [
      { name: 'PHP', level: 'Expérimentée' },
      { name: 'Symfony 6', level: 'Expérimentée' },
      { name: 'C/C++', level: 'Intermédiaire' },
      { name: 'Java', level: 'Intermédiaire' },
      { name: 'Python', level: 'Intermédiaire' }
    ]
  },
  {
    title: 'Base de Données',
    icon: DatabaseIcon,
    skills: [
      { name: 'MySQL', level: 'Expérimentée' },
      { name: 'PostgreSQL', level: 'Intermédiaire' },
      { name: 'PhpMyAdmin', level: 'Expérimentée' }
    ]
  },
  {
    title: 'Gestion de Projets & Outils',
    icon: CodeIcon,
    skills: [
      { name: 'Git/GitHub', level: 'Expérimentée' },
      { name: 'Scrum', level: 'Intermédiaire' },
      { name: 'Netlify', level: 'Intermédiaire' }
    ]
  },
  {
    title: 'Conception & CMS',
    icon: CodeIcon,
    skills: [
      { name: 'Figma', level: 'Expérimentée' },
      { name: 'WordPress', level: 'Intermédiaire' },
      { name: 'Illustrator', level: 'Intermédiaire' }
    ]
  },
  {
    title: 'Réseau & Sécurité',
    icon: DatabaseIcon,
    skills: [
      { name: 'HTTPS/SSH', level: 'Intermédiaire' },
      { name: 'Routage VLSM', level: 'Intermédiaire' },
      { name: 'Firewalls', level: 'Basique' }
    ]
  },
  {
    title: 'Mobile',
    icon: CodeIcon,
    skills: [
      { name: 'Android Studio', level: 'Basique' }
    ]
  }
]

const getSkillWidth = (level: string): string => {
  const levels: Record<string, string> = {
    'Expérimentée': '90%',
    'Intermédiaire': '70%',
    'Basique': '50%'
  }
  return levels[level] || '50%'
}
</script>

<style scoped>
.experience-section {
  background: white;
  position: relative;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-subtitle {
  color: var(--primary-color);
  font-weight: 600;
  font-size: 1.1rem;
  margin-bottom: 0.5rem;
  text-transform: uppercase;
  letter-spacing: 2px;
}

.section-title {
  color: var(--text-dark);
  font-size: clamp(2.5rem, 4vw, 3.5rem);
  position: relative;
  display: inline-block;
}

.section-title::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 4px;
  background: var(--primary-gradient);
  border-radius: 2px;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
}

.skill-category {
  padding: 2.5rem;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.skill-category::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: var(--primary-gradient);
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.skill-category:hover::before {
  transform: scaleX(1);
}

.category-icon {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: var(--primary-gradient);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
  color: white;
}

.category-title {
  font-size: 1.6rem;
  color: var(--text-dark);
  margin-bottom: 2rem;
  background: var(--primary-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.skills-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.skill-item {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.skill-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.skill-name {
  font-weight: 600;
  color: var(--text-dark);
  font-size: 1.05rem;
}

.skill-level {
  font-size: 0.9rem;
  color: var(--text-light);
  font-weight: 500;
}

.skill-bar {
  height: 8px;
  background: rgba(102, 126, 234, 0.1);
  border-radius: 10px;
  overflow: hidden;
  position: relative;
}

.skill-progress {
  height: 100%;
  background: var(--primary-gradient);
  border-radius: 10px;
  transition: width 1s ease;
  position: relative;
}

.skill-progress::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(
    90deg,
    transparent,
    rgba(255, 255, 255, 0.3),
    transparent
  );
  animation: shimmer 2s infinite;
}

@keyframes shimmer {
  0% {
    transform: translateX(-100%);
  }
  100% {
    transform: translateX(100%);
  }
}

@media (max-width: 968px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 640px) {
  .skill-category {
    padding: 1.5rem;
  }

  .category-icon {
    width: 60px;
    height: 60px;
  }

  .category-title {
    font-size: 1.4rem;
  }

  .skills-grid {
    grid-template-columns: 1fr;
  }
}
</style>
