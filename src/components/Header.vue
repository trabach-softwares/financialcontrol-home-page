<template>
  <header class="header">
    <div class="container">
      <div class="header-content">
        <div class="logo">
          <img src="/ControleFinanceiro.svg" alt="Financial Control" class="logo-icon">
          <span class="logo-text">Financial Control</span>
        </div>
        
        <nav class="nav">
          <a href="#recursos" class="nav-link">Recursos</a>
          <a href="#planos" class="nav-link">Planos</a>
          <a href="https://app.financialcontrol.com.br/" target="_blank" rel="noopener noreferrer" class="nav-link">Entrar</a>
          <a href="https://app.financialcontrol.com.br/" target="_blank" rel="noopener noreferrer" class="btn btn-primary">Começar Grátis</a>
        </nav>
      </div>
    </div>
  </header>
</template>

<script setup>
</script>

<style scoped>
.header {
  background: #FFFFFF;
  border-bottom: 1px solid #EBECF0;
  padding: 1rem 0;
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: var(--fc-shadow-sm);
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
}

.nav-link:hover {
  color: var(--fc-primary);
}

.btn {
  padding: 0.625rem 1.5rem;
  border-radius: 6px;
  font-weight: 600;
  font-size: 0.9375rem;
  text-decoration: none;
  transition: all 0.2s ease;
  border: none;
  cursor: pointer;
}

.btn-primary {
  background: #2C5F2D;
  color: #FFFFFF;
}

.btn-primary:hover {
  background: #1e4620;
  transform: translateY(-1px);
  box-shadow: var(--fc-shadow-md);
}

@media (max-width: 768px) {
  .nav {
    gap: 1rem;
  }
  
  .nav-link {
    display: none;
  }
  
  .nav-link:last-child {
    display: block;
  }
}
</style>
