<template>
  <div>
    <section id="contact" class="section contact-section gradient-bg">
      <div class="container">
        <div class="section-header">
          <p class="section-subtitle">Prendre Contact</p>
          <h2 class="section-title">Contactez-moi</h2>
        </div>

        <div class="contact-content">
          <div class="contact-cards">
            <a
              href="mailto:mamou.rania@proton.me"
              class="contact-card card-glass"
            >
              <div class="contact-icon">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="32"
                  height="32"
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
              </div>
              <h3>Email</h3>
              <p>mamou.rania@proton.me</p>
            </a>

            <a href="tel:+33764473167" class="contact-card card-glass">
              <div class="contact-icon">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="32"
                  height="32"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <path
                    d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"
                  ></path>
                </svg>
              </div>
              <h3>Téléphone</h3>
              <p>07 64 47 31 67</p>
            </a>
            <a
              href="https://www.linkedin.com/in/rania-mamou-84260b257/"
              target="_blank"
              rel="noopener noreferrer"
              class="contact-card card-glass"
            >
              <div class="contact-icon">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="32"
                  height="32"
                  viewBox="0 0 24 24"
                  fill="currentColor"
                >
                  <path
                    d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
                  />
                </svg>
              </div>
              <h3>LinkedIn</h3>
              <p>Rania Mamou</p>
            </a>
          </div>

          <div class="contact-form-wrapper">
            <form
              @submit.prevent="handleSubmit"
              class="contact-form card-glass"
            >
              <div class="form-group">
                <label for="name">Nom</label>
                <input
                  type="text"
                  id="name"
                  v-model="form.name"
                  placeholder="Votre nom"
                  required
                />
              </div>

              <div class="form-group">
                <label for="email">Email</label>
                <input
                  type="email"
                  id="email"
                  v-model="form.email"
                  placeholder="votre.email@exemple.com"
                  required
                />
              </div>

              <div class="form-group">
                <label for="message">Message</label>
                <textarea
                  id="message"
                  v-model="form.message"
                  placeholder="Votre message..."
                  rows="5"
                  required
                ></textarea>
              </div>

              <button type="submit" class="btn btn-submit">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="20"
                  height="20"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                >
                  <line x1="22" y1="2" x2="11" y2="13"></line>
                  <polygon points="22 2 15 22 11 13 2 9 22 2"></polygon>
                </svg>
                Envoyer le message
              </button>
            </form>
          </div>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <p class="footer-text">© 2024 Rania Mamou. Tous droits réservés.</p>
          <div class="footer-links">
            <a href="#about">À propos</a>
            <a href="#experience">Expériences</a>
            <a href="#projects">Projets</a>
            <a href="#contact">Contact</a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { reactive } from "vue";

interface Form {
  name: string;
  email: string;
  message: string;
}

const form = reactive<Form>({
  name: "",
  email: "",
  message: "",
});

const handleSubmit = () => {
  // Créer un lien mailto avec les informations du formulaire
  const subject = `Message de ${form.name}`;
  const body = `${form.message}%0D%0A%0D%0ADe: ${form.name}%0D%0AEmail: ${form.email}`;
  window.location.href = `mailto:mamou.rania@proton.me?subject=${subject}&body=${body}`;

  // Réinitialiser le formulaire
  form.name = "";
  form.email = "";
  form.message = "";
};
</script>

<style scoped>
.contact-section {
  color: white;
  position: relative;
  overflow: hidden;
  background: linear-gradient(
    135deg,
    #667eea 0%,
    #764ba2 50%,
    #f093fb 100%
  ) !important;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-subtitle {
  color: white;
  font-weight: 600;
  font-size: 1.1rem;
  margin-bottom: 0.5rem;
  text-transform: uppercase;
  letter-spacing: 2px;
  text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
}

.section-title {
  color: white;
  font-size: clamp(2.5rem, 4vw, 3.5rem);
  position: relative;
  display: inline-block;
  background: none;
  -webkit-text-fill-color: white;
  text-shadow: 0 2px 20px rgba(0, 0, 0, 0.3);
}

.section-title::after {
  content: "";
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 4px;
  background: white;
  border-radius: 2px;
  box-shadow: 0 2px 10px rgba(255, 255, 255, 0.5);
}

.contact-content {
  max-width: 1000px;
  margin: 0 auto;
}

.contact-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin-bottom: 3rem;
}

.contact-card {
  padding: 2.5rem;
  text-align: center;
  transition: all 0.3s ease;
  color: white;
  text-decoration: none;
  display: block;
  border-radius: 30px;
}

.card-glass {
  background: rgba(255, 255, 255, 0.25);
  backdrop-filter: blur(20px);
  border: 2px solid rgba(255, 255, 255, 0.4);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
  border-radius: 30px;
}

.contact-card:hover {
  transform: translateY(-10px);
  background: rgba(255, 255, 255, 0.35);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.3);
}

.contact-icon {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.3);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.5rem;
  color: white;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
  transition: all 0.3s ease;
}

.contact-card:hover .contact-icon {
  transform: scale(1.1) rotate(5deg);
  background: rgba(255, 255, 255, 0.4);
}

.contact-card h3 {
  font-size: 1.4rem;
  margin-bottom: 0.5rem;
  color: white;
}

.contact-card p {
  color: rgba(255, 255, 255, 0.9);
  font-size: 1rem;
}

.contact-form-wrapper {
  max-width: 600px;
  margin: 0 auto;
}

.contact-form {
  padding: 3rem;
  border: 2px solid rgba(255, 255, 255, 0.4);
  background: rgba(255, 255, 255, 0.2);
  border-radius: 35px;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.75rem;
  font-weight: 700;
  font-size: 1.15rem;
  color: white;
  text-shadow: 0 2px 10px rgba(0, 0, 0, 0.6);
  letter-spacing: 0.5px;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 1.2rem 1.5rem;
  border: 2px solid rgba(255, 255, 255, 0.5);
  border-radius: 25px;
  background: rgba(255, 255, 255, 0.9);
  color: #1e1e2e;
  font-family: inherit;
  font-size: 1rem;
  font-weight: 500;
  transition: all 0.3s ease;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

.form-group input::placeholder,
.form-group textarea::placeholder {
  color: rgba(30, 30, 46, 0.5);
  font-weight: 400;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: white;
  background: white;
  color: #1e1e2e;
  box-shadow: 0 4px 20px rgba(255, 255, 255, 0.4);
  transform: translateY(-2px);
}

.btn-submit {
  width: 100%;
  padding: 1.3rem 2rem;
  background: white;
  color: var(--primary-color);
  border: none;
  border-radius: 50px;
  font-weight: 700;
  font-size: 1.1rem;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  transition: all 0.3s ease;
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
}

.btn-submit:hover {
  transform: translateY(-5px) scale(1.02);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
}

.footer {
  background: var(--text-dark);
  padding: 2rem 0;
  color: white;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.footer-text {
  color: rgba(255, 255, 255, 0.8);
  font-size: 0.95rem;
}

.footer-links {
  display: flex;
  gap: 2rem;
}

.footer-links a {
  color: rgba(255, 255, 255, 0.8);
  font-weight: 500;
  transition: color 0.3s ease;
}

.footer-links a:hover {
  color: white;
}

@media (max-width: 768px) {
  .contact-cards {
    grid-template-columns: 1fr;
  }

  .contact-form {
    padding: 1.5rem;
  }

  .footer-content {
    flex-direction: column;
    text-align: center;
  }

  .footer-links {
    flex-direction: column;
    gap: 1rem;
  }
}
</style>
