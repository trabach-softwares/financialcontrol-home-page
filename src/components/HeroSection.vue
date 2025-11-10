<template>
  <section class="hero">
    <div class="container">
      <div class="hero-content">
        <h1 class="hero-title">
          Gerencie suas finanças<br>
          de forma prática e rápida
        </h1>
        
        <p class="hero-description">
          Controle de receitas e despesas para pequenas e médias empresas.<br>
          Visualize seu fluxo de caixa, gere relatórios e tome decisões<br>
          mais inteligentes.
        </p>
        
        <div class="hero-actions">
          <a href="https://app.financialcontrol.com.br/" target="_blank" rel="noopener noreferrer" class="btn btn-primary">
            Começar Gratuitamente
            <svg class="btn-icon" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd" />
            </svg>
          </a>
          <a href="https://app.financialcontrol.com.br/" target="_blank" rel="noopener noreferrer" class="btn btn-secondary">Já tenho conta</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.hero {
  background: linear-gradient(135deg, #F4F5F7 0%, #FFFFFF 100%);
  padding: 5rem 0 6rem;
  text-align: center;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
}

.hero-title {
  font-size: 3rem;
  font-weight: 700;
  color: var(--fc-text-primary);
  line-height: 1.2;
  margin: 0 0 1.5rem;
  letter-spacing: -0.02em;
}

.hero-description {
  font-size: 1.125rem;
  color: var(--fc-text-secondary);
  line-height: 1.7;
  margin: 0 0 2.5rem;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.875rem 2rem;
  border-radius: 6px;
  font-weight: 600;
  font-size: 1rem;
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
  transform: translateY(-2px);
  box-shadow: var(--fc-shadow-lg);
}

.btn-secondary {
  background: transparent;
  color: #2C5F2D;
  border: 2px solid var(--fc-surface-2);
}

.btn-secondary:hover {
  border-color: #2C5F2D;
  color: #2C5F2D;
}

.btn-icon {
  width: 20px;
  height: 20px;
}

@media (max-width: 768px) {
  .hero {
    padding: 3rem 0 4rem;
  }
  
  .hero-title {
    font-size: 2rem;
  }
  
  .hero-description {
    font-size: 1rem;
  }
  
  .hero-description br {
    display: none;
  }
  
  .hero-actions {
    flex-direction: column;
    align-items: stretch;
  }
  
  .btn {
    justify-content: center;
  }
}
</style>
