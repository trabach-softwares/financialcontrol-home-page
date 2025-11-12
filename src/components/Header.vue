<template>
  <header class="header">
    <div class="container">
      <div class="header-content">
        <a href="/" class="logo">
          <img src="/ControleFinanceiro.svg" alt="Financial Control" class="logo-icon">
          <span class="logo-text">Financial Control</span>
        </a>
        
        <nav class="nav">
          <a href="#recursos" class="nav-link">Recursos</a>
          <a href="#planos" class="nav-link">Planos</a>
          <a href="https://app.financialcontrol.com.br/" target="_blank" rel="noopener noreferrer" class="nav-link nav-login">Entrar</a>
          <a href="https://app.financialcontrol.com.br/" target="_blank" rel="noopener noreferrer" class="btn btn-primary">
            Teste Grátis
            <svg class="btn-icon" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd" />
            </svg>
          </a>
        </nav>

        <!-- Mobile menu button -->
        <button class="mobile-menu-btn" @click="toggleMobileMenu" aria-label="Menu">
          <svg v-if="!mobileMenuOpen" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M3 12h18M3 6h18M3 18h18" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          <svg v-else viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M6 18L18 6M6 6l12 12" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </button>
      </div>

      <!-- Mobile menu -->
      <div v-if="mobileMenuOpen" class="mobile-menu">
        <a href="#recursos" class="mobile-link" @click="closeMobileMenu">Recursos</a>
        <a href="#planos" class="mobile-link" @click="closeMobileMenu">Planos</a>
        <a href="https://app.financialcontrol.com.br/" target="_blank" rel="noopener noreferrer" class="mobile-link">Entrar</a>
        <a href="https://app.financialcontrol.com.br/" target="_blank" rel="noopener noreferrer" class="btn btn-primary btn-mobile">
          Teste Grátis por 14 Dias
        </a>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const mobileMenuOpen = ref(false)

const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const closeMobileMenu = () => {
  mobileMenuOpen.value = false
}
</script>

<style scoped>
.header {
  background: #FFFFFF;
  border-bottom: 1px solid #EBECF0;
  padding: 1rem 0;
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

.header-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  font-weight: 600;
  font-size: 1.125rem;
  color: var(--fc-text-primary);
  text-decoration: none;
  transition: opacity 0.2s ease;
}

.logo:hover {
  opacity: 0.8;
}

.logo-icon {
  width: 32px;
  height: 32px;
}

.logo-text {
  color: var(--fc-text-primary);
}

.nav {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.nav-link {
  color: var(--fc-text-secondary);
  text-decoration: none;
  font-weight: 500;
  font-size: 0.9375rem;
  transition: color 0.2s ease;
  position: relative;
}

.nav-link:hover {
  color: var(--fc-primary);
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--fc-primary);
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 100%;
}

.nav-login {
  color: #2C5F2D;
  font-weight: 600;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.75rem 1.75rem;
  border-radius: 8px;
  font-weight: 600;
  font-size: 0.9375rem;
  text-decoration: none;
  transition: all 0.2s ease;
  border: none;
  cursor: pointer;
  white-space: nowrap;
}

.btn-primary {
  background: linear-gradient(135deg, #2C5F2D 0%, #1e4620 100%);
  color: #FFFFFF;
  box-shadow: 0 2px 8px rgba(44, 95, 45, 0.25);
}

.btn-primary:hover {
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(44, 95, 45, 0.35);
}

.btn-icon {
  width: 16px;
  height: 16px;
}

.mobile-menu-btn {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  color: var(--fc-text-primary);
}

.mobile-menu-btn svg {
  width: 24px;
  height: 24px;
}

.mobile-menu {
  display: none;
  flex-direction: column;
  gap: 0.75rem;
  padding: 1.5rem 0;
  border-top: 1px solid #EBECF0;
  margin-top: 1rem;
}

.mobile-link {
  color: var(--fc-text-secondary);
  text-decoration: none;
  font-weight: 500;
  font-size: 1rem;
  padding: 0.75rem 0;
  transition: color 0.2s ease;
}

.mobile-link:hover {
  color: var(--fc-primary);
}

.btn-mobile {
  width: 100%;
  justify-content: center;
  margin-top: 0.5rem;
}

@media (max-width: 768px) {
  .nav {
    display: none;
  }
  
  .mobile-menu-btn {
    display: block;
  }

  .mobile-menu {
    display: flex;
  }
}
</style>
