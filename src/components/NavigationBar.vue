<template>
  <nav :class="['navbar', { 'navbar-scrolled': isScrolled }]">
    <div class="container navbar-content">
      <div class="logo" @click="scrollToTop">
        <span class="logo-text">Rania Mamou</span>
        <span class="logo-dot">.</span>
      </div>

      <!-- Desktop Navigation -->
      <ul class="nav-links desktop-nav">
        <li v-for="link in navLinks" :key="link.id">
          <a
            :href="`#${link.id}`"
            @click.prevent="scrollToSection(link.id)"
            class="nav-link"
          >
            {{ link.label }}
          </a>
        </li>
      </ul>

      <!-- Mobile Menu Button -->
      <button
        class="mobile-menu-btn"
        @click="toggleMobileMenu"
        aria-label="Toggle menu"
      >
        <span :class="['hamburger', { active: isMobileMenuOpen }]"></span>
      </button>
    </div>

    <!-- Mobile Navigation -->
    <transition name="slide-fade">
      <div v-if="isMobileMenuOpen" class="mobile-nav">
        <ul class="mobile-nav-links">
          <li v-for="link in navLinks" :key="link.id">
            <a
              :href="`#${link.id}`"
              @click.prevent="handleMobileClick(link.id)"
              class="mobile-nav-link"
            >
              {{ link.label }}
            </a>
          </li>
        </ul>
      </div>
    </transition>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";

const isScrolled = ref(false);
const isMobileMenuOpen = ref(false);

const navLinks = [
  { id: "about", label: "À propos" },
  { id: "experience", label: "Expériences" },
  { id: "projects", label: "Projets" },
  { id: "contact", label: "Contact" },
];

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
};

const scrollToSection = (id: string) => {
  const element = document.getElementById(id);
  if (element) {
    element.scrollIntoView({ behavior: "smooth", block: "start" });
  }
};

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: "smooth" });
};

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

const handleMobileClick = (id: string) => {
  scrollToSection(id);
  isMobileMenuOpen.value = false;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  padding: 1.5rem 0;
  transition: all 0.3s ease;
  background: transparent;
}

.navbar-scrolled {
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(20px);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  padding: 1rem 0;
}

.navbar-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-family: "Space Grotesk", sans-serif;
  font-size: 1.5rem;
  font-weight: 700;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 0.2rem;
}

.logo-text {
  background: var(--primary-gradient);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  transition: all 0.3s ease;
}

.logo-dot {
  color: var(--accent-color);
  font-size: 2rem;
  line-height: 0.5;
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%,
  100% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.5;
    transform: scale(1.2);
  }
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 2.5rem;
  align-items: center;
}

.nav-link {
  font-weight: 500;
  font-size: 1rem;
  color: var(--text-dark);
  position: relative;
  padding: 0.5rem 0;
  transition: color 0.3s ease;
}

.nav-link::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--primary-gradient);
  transition: width 0.3s ease;
}

.nav-link:hover {
  color: var(--primary-color);
}

.nav-link:hover::after {
  width: 100%;
}

/* Mobile Menu */
.mobile-menu-btn {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  z-index: 1001;
}

.hamburger {
  display: block;
  width: 30px;
  height: 2px;
  background: var(--text-dark);
  position: relative;
  transition: all 0.3s ease;
}

.hamburger::before,
.hamburger::after {
  content: "";
  position: absolute;
  width: 30px;
  height: 2px;
  background: var(--text-dark);
  transition: all 0.3s ease;
}

.hamburger::before {
  top: -8px;
}

.hamburger::after {
  top: 8px;
}

.hamburger.active {
  background: transparent;
}

.hamburger.active::before {
  top: 0;
  transform: rotate(45deg);
}

.hamburger.active::after {
  top: 0;
  transform: rotate(-45deg);
}

.mobile-nav {
  position: fixed;
  top: 70px;
  left: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.98);
  backdrop-filter: blur(20px);
  padding: 2rem;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.mobile-nav-links {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.mobile-nav-link {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--text-dark);
  display: block;
  padding: 0.5rem 0;
  transition: all 0.3s ease;
}

.mobile-nav-link:hover {
  color: var(--primary-color);
  transform: translateX(10px);
}

/* Transitions */
.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.3s ease-in;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateY(-20px);
  opacity: 0;
}

/* Responsive */
@media (max-width: 768px) {
  .desktop-nav {
    display: none;
  }

  .mobile-menu-btn {
    display: block;
  }
}

@media (min-width: 769px) {
  .mobile-nav {
    display: none;
  }
}
</style>
