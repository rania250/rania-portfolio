<template>
  <section id="experience" class="section experience-section">
    <div class="container">
      <div class="section-header">
        <p class="section-subtitle">Ma boîte à outils</p>
        <h2 class="section-title">Compétences techniques</h2>
      </div>

      <div class="skills-grid">
        <div v-for="(category, index) in skillsCategories" :key="index" class="skill-category card">
          <h3 class="category-title">{{ category.title }}</h3>
          <div class="skills-list">
            <span v-for="skill in category.skills" :key="skill" class="skill-chip">
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const skillsCategories = [
  {
    title: 'Langages',
    skills: ['Java', 'C/C++', 'JavaScript', 'PHP', 'Python'],
  },
  {
    title: 'Front-end',
    skills: ['HTML/CSS', 'JavaScript', 'Intégration web', 'Interfaces adaptatives'],
  },
  {
    title: 'Back-end',
    skills: ['Spring Boot', 'Symfony 6', 'Node.js', 'API REST'],
  },
  {
    title: 'Bases de données',
    skills: ['MySQL', 'PostgreSQL', 'MongoDB', 'Modélisation relationnelle'],
  },
  {
    title: 'DevOps & outils',
    skills: ['Git / GitHub', 'Docker', 'Kubernetes', 'Scrum', 'Netlify', 'Jira'],
  },
  {
    title: 'Langues',
    skills: ['Français : courant', 'Anglais : intermédiaire'],
  },
]
</script>

<style scoped>
.experience-section {
  background: #fff;
  position: relative;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-header {
  margin-bottom: 3rem;
}

.section-subtitle {
  color: var(--primary-color);
  font-size: 0.78rem;
  letter-spacing: 0.13em;
}

.section-title {
  color: var(--text-dark);
  font-size: clamp(2.1rem, 4vw, 3rem);
}

.section-title::after {
  width: 52px;
  height: 3px;
  background: var(--accent-color);
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
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 260px), 1fr));
  gap: 1rem;
  max-width: 1100px;
  margin: 0 auto;
}

.skill-category {
  padding: 1.5rem;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  position: relative;
  overflow: visible;
  border-radius: 0.9rem;
  box-shadow: var(--shadow-sm);
}

.category-icon {
  display: none;
}

.skill-category::before {
  display: none;
}

.category-title {
  margin-bottom: 1rem;
  color: var(--text-dark);
  font-size: 1.15rem;
  background: none;
  -webkit-text-fill-color: currentColor;
}

.skills-list {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 0.55rem;
}

.skill-chip {
  padding: 0.42rem 0.7rem;
  border: 1px solid #dce9e3;
  border-radius: 999px;
  background: #f4f8f6;
  color: #35545a;
  font-size: 0.82rem;
  font-weight: 500;
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
    grid-template-columns: repeat(2, minmax(0, 1fr));
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

.skill-category::before {
  display: none;
}

.category-title {
  margin-bottom: 1rem;
  color: var(--text-dark);
  font-size: 1.15rem;
  background: none;
  -webkit-text-fill-color: currentColor;
}

.skills-list {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 0.55rem;
}
</style>
