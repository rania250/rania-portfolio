<template>
  <section id="hero" class="hero-section">
    <div class="container hero-container">
      <div class="hero-content fade-in-up">
        <p class="hero-eyebrow">
          <span class="availability-dot"></span>
          Recherche un stage de 6 mois · Février 2027
        </p>
        <h1 class="hero-title">Rania Mamou</h1>
        <p class="hero-subtitle">Développeuse Full-Stack Java</p>
        <p class="hero-description">
          Étudiante en Master Informatique et Mobilité à l’Université de
          Haute-Alsace, je conçois des applications web de bout en bout,
          du backend Spring Boot à des interfaces modernes et accessibles.
        </p>

        <div class="hero-buttons">
          <a
            href="#contact"
            @click.prevent="scrollToContact"
            class="btn btn-secondary"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="20"
              height="20"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
            >
              <path
                d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
              ></path>
              <polyline points="22,6 12,13 2,6"></polyline>
            </svg>
            Me Contacter
          </a>
        </div>

        <div class="social-links">
          <a
            href="https://www.linkedin.com/in/rania-mamou-84260b257/"
            target="_blank"
            rel="noopener noreferrer"
            class="social-link"
            title="LinkedIn"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="currentColor"
            >
              <path
                d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
              />
            </svg>
          </a>
          <a
            href="https://github.com/rania250"
            target="_blank"
            rel="noopener noreferrer"
            class="social-link"
            title="GitHub"
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
        </div>
      </div>

      <div class="hero-image float">
        <div class="image-container">
          <div class="glow-effect"></div>
          <img
            src="/assets/DSC_2958 600px-fotor-2024022204551.png"
            alt="Rania Mamou"
            class="profile-image"
          />
          <div class="hero-card">
            <span class="hero-card-icon">JS</span>
            <span><strong>Full-Stack</strong><small>Java · Spring Boot · Web</small></span>
          </div>
        </div>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <button
      class="scroll-indicator"
      type="button"
      aria-label="Faire défiler jusqu’à la section À propos"
      @click="scrollToAbout"
    >
      <div class="mouse">
        <div class="wheel"></div>
      </div>
      <p>Scroll</p>
    </button>
  </section>
</template>

<script setup lang="ts">
const scrollToContact = () => {
  const element = document.getElementById("contact");
  if (element) {
    element.scrollIntoView({ behavior: "smooth" });
  }
};

const scrollToAbout = () => {
  const element = document.getElementById("about");
  if (element) {
    element.scrollIntoView({ behavior: "smooth" });
  }
};

</script>

<style scoped>
.hero-section {
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  min-height: min(820px, 100vh);
  padding: 7.5rem 0 5rem;
  background:
    radial-gradient(ellipse at 82% 25%, rgba(217, 242, 236, 0.9), transparent 38%),
    linear-gradient(135deg, #f7faf8 0%, #eef5f1 100%);
}

.hero-section .hero-container {
  grid-template-columns: 1.15fr 0.85fr;
  gap: clamp(2rem, 7vw, 6rem);
}

.hero-section .hero-content {
  color: var(--text-dark);
}

.hero-eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 0.6rem;
  margin-bottom: 1.5rem;
  padding: 0.55rem 0.85rem;
  border: 1px solid #cfe4db;
  border-radius: 999px;
  background: rgba(255, 255, 255, 0.72);
  color: var(--secondary-color);
  font-size: 0.88rem;
  font-weight: 600;
}

.availability-dot {
  width: 0.55rem;
  height: 0.55rem;
  border-radius: 50%;
  background: #3e9a71;
  box-shadow: 0 0 0 4px rgba(62, 154, 113, 0.13);
}

.hero-section .hero-title {
  margin-bottom: 0.4rem;
  color: var(--text-dark);
  font-size: clamp(3.3rem, 7vw, 5.7rem);
  letter-spacing: -0.065em;
  -webkit-text-fill-color: currentColor;
}

.hero-section .hero-subtitle {
  min-height: 0;
  margin-bottom: 1.25rem;
  color: var(--primary-color);
  font-size: clamp(1.4rem, 3vw, 2.15rem);
  font-weight: 600;
}

.hero-section .hero-description {
  max-width: 590px;
  margin-bottom: 1.8rem;
  color: var(--text-light);
  font-size: 1.08rem;
  line-height: 1.85;
}

.hero-section .hero-buttons {
  gap: 0.75rem;
  margin-bottom: 1.75rem;
}

.hero-section .btn {
  border-radius: 0.7rem;
  padding: 0.9rem 1.25rem;
}

.hero-section .btn-secondary {
  color: var(--text-dark);
  border: 1px solid #cedbd6;
}

.hero-section .btn-secondary:hover {
  background: #edf7f3;
  color: var(--primary-color);
}

.hero-section .social-link {
  width: 42px;
  height: 42px;
  background: #e4efea;
  color: var(--secondary-color);
  box-shadow: none;
}

.hero-section .social-link:hover {
  background: var(--primary-color);
  color: white;
}

.hero-section .hero-image {
  width: 100%;
  animation: none;
}

.hero-section .image-container {
  max-width: 390px;
}

.hero-section .glow-effect {
  background: radial-gradient(circle, rgba(15, 118, 110, 0.16) 0%, transparent 70%);
}

.hero-section .profile-image {
  display: block;
  width: 100%;
  height: auto;
  aspect-ratio: 0.9;
  object-fit: cover;
  border: 10px solid white;
  border-radius: 48% 48% 1.5rem 1.5rem;
  box-shadow: 0 24px 60px rgba(25, 50, 56, 0.16);
  animation: none;
}

.hero-card {
  position: absolute;
  right: -1rem;
  bottom: 1.5rem;
  display: flex;
  align-items: center;
  gap: 0.7rem;
  padding: 0.85rem 1rem;
  border: 1px solid #e7eeeb;
  border-radius: 0.85rem;
  background: white;
  box-shadow: var(--shadow-md);
}

.hero-card-icon {
  display: grid;
  width: 2.5rem;
  height: 2.5rem;
  place-items: center;
  border-radius: 0.7rem;
  background: #eaf5f1;
  color: var(--primary-color);
}

.hero-card strong,
.hero-card small {
  display: block;
}

.hero-card strong {
  color: var(--text-dark);
  font-size: 0.9rem;
}

.hero-card small {
  margin-top: 0.1rem;
  color: var(--text-light);
  font-size: 0.72rem;
}

.hero-section .scroll-indicator {
  bottom: 1.25rem;
  color: var(--text-light);
  border: 0;
  background: transparent;
  font: inherit;
}

.hero-section .mouse {
  width: 23px;
  height: 37px;
  border-color: #9bb1a9;
}

.hero-section .wheel {
  background: var(--primary-color);
}

.hero-section .scroll-indicator p {
  font-size: 0.75rem;
}

.hero-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  position: relative;
  z-index: 1;
}

.hero-content {
  color: white;
}

.hero-title {
  font-size: clamp(3rem, 6vw, 5rem);
  margin-bottom: 1rem;
  color: white;
  background: none;
  -webkit-text-fill-color: white;
}

.hero-subtitle {
  font-size: clamp(1.5rem, 3vw, 2.5rem);
  margin-bottom: 1.5rem;
  font-weight: 600;
  min-height: 3rem;
}

.hero-description {
  font-size: 1.2rem;
  line-height: 1.8;
  margin-bottom: 2rem;
  opacity: 0.95;
  color: rgba(255, 255, 255, 0.9);
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  margin-bottom: 2rem;
  flex-wrap: wrap;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 2rem;
  border-radius: 50px;
  font-weight: 600;
  font-size: 1rem;
  transition: all 0.3s ease;
  cursor: pointer;
  border: none;
}

.btn-primary {
  background: rgba(255, 255, 255, 0.95);
  color: var(--primary-color);
}

.btn-primary:hover {
  background: white;
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
}

.btn-secondary {
  background: transparent;
  color: white;
  border: 2px solid white;
}

.btn-secondary:hover {
  background: white;
  color: var(--primary-color);
  transform: translateY(-3px);
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-link {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: white;
  color: var(--primary-color);
  transform: translateY(-5px) scale(1.1);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

.hero-image {
  position: relative;
}

.image-container {
  position: relative;
  width: 100%;
  max-width: 500px;
  margin: 0 auto;
}

.glow-effect {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 120%;
  height: 120%;
  background: radial-gradient(
    circle,
    rgba(255, 255, 255, 0.3) 0%,
    transparent 70%
  );
  border-radius: 50%;
  animation: pulse 3s ease-in-out infinite;
  z-index: -1;
}

@keyframes pulse {
  0%,
  100% {
    transform: translate(-50%, -50%) scale(1);
    opacity: 0.5;
  }
  50% {
    transform: translate(-50%, -50%) scale(1.1);
    opacity: 0.8;
  }
}

.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  color: white;
  cursor: pointer;
  animation: bounce 2s ease-in-out infinite;
}

@keyframes bounce {
  0%,
  100% {
    transform: translateX(-50%) translateY(0);
  }
  50% {
    transform: translateX(-50%) translateY(-10px);
  }
}

.mouse {
  width: 30px;
  height: 50px;
  border: 2px solid white;
  border-radius: 15px;
  position: relative;
}

.wheel {
  width: 4px;
  height: 10px;
  background: white;
  border-radius: 2px;
  position: absolute;
  top: 8px;
  left: 50%;
  transform: translateX(-50%);
  animation: scroll 2s ease-in-out infinite;
}

@keyframes scroll {
  0% {
    opacity: 1;
    transform: translateX(-50%) translateY(0);
  }
  100% {
    opacity: 0;
    transform: translateX(-50%) translateY(20px);
  }
}

@media (max-width: 968px) {
  .hero-container {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .hero-content {
    order: 1;
  }

  .hero-image {
    order: 2;
    max-width: 400px;
    margin: 0 auto 2rem;
  }

  .hero-buttons {
    justify-content: center;
  }

  .social-links {
    justify-content: center;
  }

  .hero-section {
    padding-bottom: 6rem;
  }

  .hero-section .hero-container {
    gap: 2rem;
  }

  .hero-eyebrow {
    margin-right: auto;
    margin-left: auto;
  }

  .hero-card {
    right: 0;
  }
}

@media (max-width: 600px) {
  .hero-section .hero-container {
    grid-template-columns: 1fr;
  }

  .hero-section .hero-image {
    max-width: 290px;
    margin-bottom: 1rem;
  }

  .hero-section .hero-title {
    font-size: clamp(3rem, 14vw, 4rem);
  }
}
</style>
