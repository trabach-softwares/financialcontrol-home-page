<template>
  <section class="features" id="recursos">
    <div class="container">
      <div class="features-header">
        <h2 class="features-title">Recursos principais</h2>
        <p class="features-subtitle">Tudo que você precisa para controlar suas finanças</p>
      </div>
      
      <div class="features-grid">
        <div class="feature-card">
          <div class="feature-icon">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect x="3" y="3" width="18" height="18" rx="2" stroke="currentColor" stroke-width="2"/>
              <path d="M3 9h18M9 3v18" stroke="currentColor" stroke-width="2"/>
            </svg>
          </div>
          <h3 class="feature-title">Dashboard Completo</h3>
          <p class="feature-description">
            Visualize receitas, despesas e saldo em gráficos intuitivos
          </p>
        </div>
        
        <div class="feature-card">
          <div class="feature-icon feature-icon-chart">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M13 2L3 14h9l-1 8 10-12h-9l1-8z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <h3 class="feature-title">Relatórios Detalhados</h3>
          <p class="feature-description">
            Filtre por período, categoria e exporte em PDF ou Excel
          </p>
        </div>
        
        <div class="feature-card">
          <div class="feature-icon feature-icon-security">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <h3 class="feature-title">Seguro e Confiável</h3>
          <p class="feature-description">
            Seus dados protegidos com backup automático
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.features {
  padding: 5rem 0;
  background: #FFFFFF;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

.features-header {
  text-align: center;
  margin-bottom: 4rem;
}

.features-title {
  font-size: 2.25rem;
  font-weight: 700;
  color: var(--fc-text-primary);
  margin: 0 0 1rem;
}

.features-subtitle {
  font-size: 1.125rem;
  color: var(--fc-text-secondary);
  margin: 0;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
}

.feature-card {
  background: #FFFFFF;
  border: 1px solid #EBECF0;
  border-radius: 12px;
  padding: 2.5rem 2rem;
  text-align: center;
  transition: all 0.3s ease;
}

.feature-card:hover {
  border-color: var(--fc-primary);
  box-shadow: var(--fc-shadow-md);
  transform: translateY(-4px);
}

.feature-icon {
  width: 56px;
  height: 56px;
  margin: 0 auto 1.5rem;
  background: #F4F5F7;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--fc-text-primary);
}

.feature-icon svg {
  width: 28px;
  height: 28px;
}

.feature-icon-chart {
  background: var(--fc-primary-bg);
  color: var(--fc-primary);
}

.feature-icon-security {
  background: var(--fc-secondary-bg);
  color: var(--fc-secondary);
}

.feature-title {
  font-size: 1.375rem;
  font-weight: 600;
  color: var(--fc-text-primary);
  margin: 0 0 1rem;
}

.feature-description {
  font-size: 1rem;
  color: var(--fc-text-secondary);
  line-height: 1.6;
  margin: 0;
}

@media (max-width: 768px) {
  .features {
    padding: 3rem 0;
  }
  
  .features-header {
    margin-bottom: 2.5rem;
  }
  
  .features-title {
    font-size: 1.75rem;
  }
  
  .features-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .feature-card {
    padding: 2rem 1.5rem;
  }
}
</style>
