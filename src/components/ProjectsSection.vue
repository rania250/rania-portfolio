<template>
  <section id="projects" class="section projects-section">
    <div class="container">
      <div class="section-header">
        <p class="section-subtitle">Parcourir Mes Récents</p>
        <h2 class="section-title">Projets</h2>
      </div>

      <div class="projects-grid">
        <div
          v-for="(project, index) in projects"
          :key="index"
          class="project-card card"
        >
          <div class="project-image">
            <img :src="project.image" :alt="project.title" />
            <div class="project-overlay">
              <div class="project-links">
                <a
                  :href="project.github"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="project-link"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="currentColor"
                  >
                    <path
                      d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
                    />
                  </svg>
                </a>
                <a
                  :href="project.demo"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="project-link"
                >
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                  >
                    <path
                      d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"
                    ></path>
                    <polyline points="15 3 21 3 21 9"></polyline>
                    <line x1="10" y1="14" x2="21" y2="3"></line>
                  </svg>
                </a>
              </div>
            </div>
          </div>
          <div class="project-content">
            <h3 class="project-title">{{ project.title }}</h3>
            <p class="project-description">{{ project.description }}</p>
            <div class="project-tags">
              <span v-for="tag in project.tags" :key="tag" class="tag">
                {{ tag }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Project {
  title: string;
  description: string;
  tags: string[];
  image: string;
  github: string;
  demo: string;
}

const projects: Project[] = [
  {
    title: "Lecteur d'Écran Accessible",
    description:
      "Application complète d'accessibilité numérique avec APIs Windows avancées, synthèse vocale temps réel et architecture modulaire 3-niveaux.",
    tags: ["Python", "APIs Windows", "Threading", "Accessibilité"],
    image: "/assets/captureLecteruDecran.png",
    github: "https://github.com/rania250/Lecteur-d-cran-accessible-",
    demo: "https://github.com/rania250/Lecteur-d-cran-accessible-",
  },
  {
    title: "Blog Application",
    description:
      "Application web complète de blog avec système de gestion de contenu, authentification et interface dynamique.",
    tags: ["PHP", "Symfony", "Vue.js", "Twig"],
    image: "/assets/blog-project.svg",
    github: "https://github.com/rania250/Blog",
    demo: "https://blog-kappa-seven-68.vercel.app/",
  },
  {
    title: "CSP Library Extension",
    description:
      "Projet de programmation impérative en C - Extension de bibliothèque pour la résolution de problèmes de satisfaction de contraintes.",
    tags: ["C", "Algorithmes"],
    image: "/assets/csp-project.svg",
    github: "https://github.com/rania250/CSP-Library-Extension",
    demo: "https://github.com/rania250/CSP-Library-Extension",
  },
  {
    title: "Foodie",
    description:
      "Site web moderne pour un restaurant avec menu interactif et système de réservation.",
    tags: ["HTML", "CSS"],
    image: "/assets/foodie.PNG",
    github: "https://github.com/rania250/Foodie",
    demo: "https://ranmamou-foodie.netlify.app/",
  },
  {
    title: "Bankist",
    description:
      "Application bancaire interactive avec gestion de comptes et transactions.",
    tags: ["HTML", "CSS", "JavaScript"],
    image: "/assets/Capturebankist.PNG",
    github: "https://github.com/rania250/Bankist",
    demo: "https://rania250.github.io/Bankist/",
  },
  {
    title: "Guess My Number",
    description:
      "Jeu interactif de devinette de nombres avec système de score.",
    tags: ["HTML", "CSS", "JavaScript"],
    image: "/assets/guessmynumber.PNG",
    github: "https://github.com/rania250/Guess-My-Number",
    demo: "https://rania250.github.io/Guess-My-Number/",
  },
  {
    title: "Roll Dice",
    description:
      "Jeu de dés multijoueur avec animations et gestion des scores.",
    tags: ["HTML", "CSS", "JavaScript"],
    image: "/assets/roll-dice.PNG",
    github: "https://github.com/rania250/Roll-Dice",
    demo: "https://rania250.github.io/Roll-Dice/",
  },
  {
    title: "Mapty",
    description:
      "Application de suivi d'activités sportives avec intégration de carte interactive.",
    tags: ["HTML", "CSS", "JavaScript"],
    image: "/assets/mapty.PNG",
    github: "https://github.com/rania250/Mapty",
    demo: "https://rania250.github.io/Mapty/",
  },
];
</script>

<style scoped>
.projects-section {
  background: var(--bg-light);
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
  content: "";
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 4px;
  background: var(--primary-gradient);
  border-radius: 2px;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
  gap: 2rem;
}

.project-card {
  padding: 0;
  overflow: hidden;
  cursor: pointer;
  position: relative;
}

.project-image {
  position: relative;
  width: 100%;
  height: 250px;
  overflow: hidden;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.5s ease;
}

.project-card:hover .project-image img {
  transform: scale(1.1);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(102, 126, 234, 0.95);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-links {
  display: flex;
  gap: 1rem;
}

.project-link {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: white;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--primary-color);
  transition: all 0.3s ease;
}

.project-link:hover {
  transform: translateY(-5px) scale(1.1);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.project-content {
  padding: 1.5rem;
}

.project-title {
  font-size: 1.5rem;
  color: var(--text-dark);
  margin-bottom: 0.75rem;
  background: var(--primary-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.project-description {
  color: var(--text-light);
  line-height: 1.6;
  margin-bottom: 1rem;
  font-size: 0.95rem;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tag {
  padding: 0.4rem 1rem;
  background: rgba(102, 126, 234, 0.1);
  color: var(--primary-color);
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 600;
  transition: all 0.3s ease;
}

.tag:hover {
  background: var(--primary-gradient);
  color: white;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 1200px) and (min-width: 769px) {
  .projects-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
