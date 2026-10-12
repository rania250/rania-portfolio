<template>
  <section id="about" class="section about-section">
    <div class="container">
      <div class="section-header">
        <p class="section-subtitle">Mon parcours</p>
        <h2 class="section-title">À propos</h2>
      </div>

      <div class="about-content">
        <div class="about-text">
          <p>
            Étudiante en <strong>Master Informatique et Mobilité</strong> à
            l’Université de Haute-Alsace, je suis développeuse Full-Stack avec
            un intérêt particulier pour Java, Spring Boot et la conception
            d’applications web utiles.
          </p>

          <p>
            J’aime prendre part à toutes les étapes d’un projet : concevoir des
            API, structurer les données, intégrer des interfaces et automatiser
            le déploiement. Mes projets m’ont permis d’explorer différents
            langages et outils du développement web, du backend à l’interface
            utilisateur.
          </p>

          <p>
            <strong
              >Je recherche un stage de 6 mois à partir de février 2027</strong
            >
            pour contribuer à une équipe de développement et progresser sur
            des projets concrets. Mobile partout en France, je suis disponible
            pour échanger sur vos besoins.
          </p>
          <div class="certifications">
            <h3>Formations Complémentaires (Udemy)</h3>
            <ul>
              <li>
                <a
                  href="https://www.udemy.com/certificate/UC-746c30a1-e74f-4da1-83ff-2280da053d92/"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  Algorithmes & structures de données - Novembre 2024
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="16"
                    height="16"
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
              </li>
              <li>
                <a
                  href="https://www.udemy.com/certificate/UC-ed901cf0-d435-4e95-9576-a155e69739ef/"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  Vue.js 3 - Juin 2024
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="16"
                    height="16"
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
              </li>
              <li>
                <a
                  href="https://www.udemy.com/certificate/UC-3fc4d4ca-e252-40eb-970d-c15fe5770a9d/"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  Formation développeur Symfony 6 - Avril 2024
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="16"
                    height="16"
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
              </li>
              <li>
                <a
                  href="https://www.udemy.com/certificate/UC-be219666-b82f-4442-b01c-64d5efa1fd75/"
                  target="_blank"
                  rel="noopener noreferrer"
                >
                  JavaScript - Août 2023
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="16"
                    height="16"
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
              </li>
            </ul>
          </div>
        </div>

        <div class="education-timeline">
          <div
            v-for="(edu, index) in education"
            :key="index"
            class="timeline-item card"
          >
            <div class="timeline-dot"></div>
            <div class="timeline-content">
              <div class="education-header">
                <img :src="edu.logo" :alt="edu.school" class="school-logo" />
                <div class="education-info">
                  <h3>{{ edu.school }}</h3>
                  <h4>{{ edu.degree }}</h4>
                  <div class="education-meta">
                    <span class="location">
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="16"
                        height="16"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                      >
                        <path
                          d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"
                        ></path>
                        <circle cx="12" cy="10" r="3"></circle>
                      </svg>
                      {{ edu.location }}
                    </span>
                    <span class="date">
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="16"
                        height="16"
                        viewBox="0 0 24 24"
                        fill="none"
                        stroke="currentColor"
                        stroke-width="2"
                      >
                        <rect
                          x="3"
                          y="4"
                          width="18"
                          height="18"
                          rx="2"
                          ry="2"
                        ></rect>
                        <line x1="16" y1="2" x2="16" y2="6"></line>
                        <line x1="8" y1="2" x2="8" y2="6"></line>
                        <line x1="3" y1="10" x2="21" y2="10"></line>
                      </svg>
                      {{ edu.date }}
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Education {
  school: string;
  degree: string;
  location: string;
  date: string;
  logo: string;
}

const education: Education[] = [
  {
    school: "Université de Haute-Alsace",
    degree: "Master 2 - Informatique et Mobilité",
    location: "Mulhouse, France",
    date: "Sept 2026 - Juin 2027",
    logo: "/assets/uha-mulhouse.png",
  },
  {
    school: "Université de Haute-Alsace Mulhouse",
    degree: "Master 1 - Informatique et Mobilité",
    location: "Mulhouse, France",
    date: "Sept 2025 - Juin 2026",
    logo: "/assets/uha-mulhouse.png",
  },
  {
    school: "La Rochelle Université",
    degree: "Licence 2 - Informatique",
    location: "La Rochelle, France",
    date: "Sept 2023 - Juin 2025",
    logo: "/assets/LaRochelleUniversitéHD-fotor-2024022204730.png",
  },
  {
    school: "Université M'Hamed Bougara Boumerdes",
    degree: "Licence - Développement Web et Infographie (Bac+3)",
    location: "Boumerdes, Algérie",
    date: "Nov 2020 - Juillet 2023",
    logo: "/assets/Logo-umbb-crsic.png",
  },
  {
    school: "Lycée Aïn-Zaouïa",
    degree: "BAC en Mathématiques",
    location: "Aïn-Zaouïa, Tizi-Ouzou, Algérie",
    date: "Sept 2020",
    logo: "/assets/lyceeAinZaouia-fotor-2024022204825.png",
  },
];
</script>

<style scoped>
.about-section {
  background: var(--bg-light);
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

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.about-text p {
  margin-bottom: 1.5rem;
  font-size: 1.1rem;
  line-height: 1.9;
}

.about-text p {
  font-size: 1.02rem;
  line-height: 1.85;
}

.about-text strong {
  color: var(--text-dark);
}

.about-section .certifications {
  background: #edf5f1;
  border-left-color: var(--primary-color);
  border-radius: 0.85rem;
}

.about-section .certifications {
  border-left-color: var(--primary-color);
}

.about-section .certifications h3,
.about-section .education-info h3 {
  color: var(--text-dark);
  background: none;
  -webkit-text-fill-color: currentColor;
}

.about-section .certifications h3 {
  font-size: 1.1rem;
}

.certifications {
  margin-top: 2rem;
  padding: 1.5rem;
  background: #edf5f1;
  border-radius: var(--radius-lg);
  border-left: 4px solid var(--primary-color);
}

.certifications h3 {
  font-size: 1.3rem;
  color: var(--primary-color);
  margin-bottom: 1rem;
}

.certifications ul {
  list-style: none;
  padding: 0;
}

.certifications li {
  padding: 0.5rem 0;
  font-size: 1rem;
}

.certifications li a {
  color: var(--text-light);
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  transition: all 0.3s ease;
  padding: 0.5rem;
  border-radius: 8px;
}

.certifications li a:hover {
  color: var(--primary-color);
  background: #e3f0ea;
  transform: translateX(5px);
}

.certifications li a svg {
  opacity: 0;
  transition: opacity 0.3s ease;
}

.certifications li a:hover svg {
  opacity: 1;
}

.education-timeline {
  position: relative;
}

.education-timeline::before {
  content: "";
  position: absolute;
  left: 20px;
  top: 0;
  bottom: 0;
  width: 2px;
  background: #cfe4db;
}

.timeline-item {
  position: relative;
  padding-left: 60px;
  margin-bottom: 1rem;
  border-radius: 0.9rem;
  box-shadow: var(--shadow-sm);
}

.timeline-dot {
  position: absolute;
  left: 11px;
  top: 20px;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: var(--primary-color);
  box-shadow:
    0 0 0 4px var(--bg-light),
    0 0 0 8px rgba(15, 118, 110, 0.12);
  z-index: 1;
}

.timeline-content {
  padding: 1rem 1.1rem;
}

.education-header {
  display: flex;
  gap: 1.5rem;
  align-items: flex-start;
}

.school-logo {
  width: 64px;
  height: 64px;
  object-fit: contain;
  border-radius: 0.7rem;
  background: white;
  padding: 0.5rem;
  box-shadow: var(--shadow-sm);
}

.education-info h3 {
  font-size: 1.05rem;
  color: var(--text-dark);
  margin-bottom: 0.5rem;
}

.education-info h4 {
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--text-light);
  margin-bottom: 1rem;
}

.education-meta {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  font-size: 0.95rem;
  color: var(--text-light);
}

.education-meta span {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.education-meta svg {
  color: var(--primary-color);
}

@media (max-width: 968px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .timeline-item {
    padding-left: 50px;
  }

  .education-timeline::before {
    left: 15px;
  }

  .timeline-dot {
    left: 6px;
  }

  .education-header {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .school-logo {
    width: 100px;
    height: 100px;
  }
}

@media (max-width: 640px) {
  .school-logo {
    width: 70px;
    height: 70px;
  }

  .education-info h3 {
    font-size: 1.2rem;
  }

  .education-info h4 {
    font-size: 0.9rem;
  }
}

.about-section .section-header {
  margin-bottom: 3rem;
}

.about-section .section-subtitle {
  font-size: 0.78rem;
  letter-spacing: 0.13em;
}

.about-section .section-title {
  font-size: clamp(2.1rem, 4vw, 3rem);
}

.about-section .section-title::after {
  width: 52px;
  height: 3px;
  background: var(--accent-color);
}
</style>
