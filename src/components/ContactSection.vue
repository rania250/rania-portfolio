<template>
  <div>
    <section id="contact" class="section contact-section">
      <div class="container">
        <div class="section-header">
          <p class="section-subtitle">Parlons de votre projet</p>
          <h2 class="section-title">Me contacter</h2>
        </div>

        <p class="contact-intro">
          Vous recrutez une stagiaire développeuse Full-Stack ? Écrivez-moi,
          je serai ravie d’échanger avec vous.
        </p>
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
          <div class="footer-links">
            <a href="#about">À propos</a>
            <a href="#experience">Compétences</a>
            <a href="#projects">Projets</a>
            <a href="#contact">Contact</a>
          </div>
          <p class="footer-text">© {{ new Date().getFullYear() }} Rania Mamou</p>
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
  const subject = encodeURIComponent(`Message de ${form.name}`);
  const body = encodeURIComponent(
    `${form.message}\n\nDe : ${form.name}\nEmail : ${form.email}`,
  );
  window.location.href = `mailto:mamou.rania@proton.me?subject=${subject}&body=${body}`;

  // Réinitialiser le formulaire
  form.name = "";
  form.email = "";
  form.message = "";
};
</script>

<style scoped>
.contact-section {
  color: var(--text-dark);
  position: relative;
  overflow: hidden;
  background: #edf5f1;
}

.contact-section .contact-content {
  max-width: 900px;
}

.contact-section .contact-cards {
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-header {
  margin-bottom: 1.5rem;
}

.contact-section .section-subtitle {
  color: var(--primary-color);
  font-size: 0.78rem;
  letter-spacing: 0.13em;
  text-shadow: none;
}

.contact-section .section-title {
  color: var(--text-dark);
  font-size: clamp(2.1rem, 4vw, 3rem);
  text-shadow: none;
  -webkit-text-fill-color: currentColor;
}

.contact-section .section-title::after {
  width: 52px;
  height: 3px;
  background: var(--accent-color);
  box-shadow: none;
}

.contact-intro {
  max-width: 620px;
  margin: 0 auto 2rem;
  text-align: center;
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
  margin-bottom: 0;
}

.contact-card {
  padding: 1.5rem;
  text-align: center;
  transition: all 0.3s ease;
  color: var(--text-dark);
  text-decoration: none;
  display: block;
  border-radius: 0.9rem;
  box-shadow: var(--shadow-sm);
}

.card-glass {
  background: white;
  border: 1px solid #e1eae5;
  border-radius: 0.9rem;
}

.contact-card:hover {
  transform: translateY(-4px);
  background: white;
  box-shadow: var(--shadow-md);
}

.contact-icon {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  background: #edf5f1;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.5rem;
  color: var(--primary-color);
  box-shadow: none;
  transition: all 0.3s ease;
}

.contact-card:hover .contact-icon {
  transform: scale(1.1) rotate(5deg);
  background: #dcefe7;
}

.contact-card h3 {
  font-size: 1.4rem;
  margin-bottom: 0.5rem;
  color: var(--text-dark);
}

.contact-card p {
  color: var(--text-light);
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
  font-size: 0.9rem;
  color: var(--text-dark);
  text-shadow: none;
  letter-spacing: 0.5px;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 0.85rem 1rem;
  border: 1px solid #d8e4de;
  border-radius: 0.65rem;
  background: #fff;
  color: var(--text-dark);
  font-family: inherit;
  font-size: 1rem;
  font-weight: 400;
  transition: all 0.3s ease;
  box-shadow: none;
}

.form-group input::placeholder,
.form-group textarea::placeholder {
  color: #839397;
  font-weight: 400;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--primary-color);
  background: white;
  color: var(--text-dark);
  box-shadow: 0 0 0 3px rgba(15, 118, 110, 0.12);
}

.btn-submit {
  width: 100%;
  padding: 0.9rem 1.2rem;
  background: var(--primary-color);
  color: white;
  border: none;
  border-radius: 0.7rem;
  font-weight: 600;
  font-size: 1rem;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  transition: all 0.3s ease;
  box-shadow: var(--shadow-sm);
}

.btn-submit:hover {
  transform: translateY(-2px);
  background: var(--secondary-color);
  box-shadow: var(--shadow-md);
}

.footer {
  background: #193238;
  padding: 1.5rem 0;
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

.footer-links a {
  font-size: 0.88rem;
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

  .contact-section .contact-cards {
    grid-template-columns: 1fr;
  }
}
</style>
