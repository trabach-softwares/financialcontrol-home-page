<template>
  <section class="hero">
    <div class="container">
      <div class="hero-content">
        <!-- Selo de prova social -->
        <!-- <div class="social-proof">
          <span class="proof-badge">⭐ Mais de 5.000 empresas já confiam</span>
        </div> -->

        <h1 class="hero-title">
          Aumente seu lucro com<br>
          controle financeiro inteligente
        </h1>
        
        <p class="hero-description">
          Pare de perder dinheiro por falta de organização. Com o Financial Control,<br>
          você visualiza seu fluxo de caixa em tempo real, identifica gastos<br>
          desnecessários e toma decisões que aumentam sua lucratividade.
        </p>

        <!-- Trust badges -->
        <div class="trust-badges">
          <div class="trust-item">
            <svg class="trust-icon" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
            </svg>
            <span>Sem cartão de crédito</span>
          </div>
          <div class="trust-item">
            <svg class="trust-icon" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
            </svg>
            <span>14 dias grátis</span>
          </div>
          <div class="trust-item">
            <svg class="trust-icon" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M5 9V7a5 5 0 0110 0v2a2 2 0 012 2v5a2 2 0 01-2 2H5a2 2 0 01-2-2v-5a2 2 0 012-2zm8-2v2H7V7a3 3 0 016 0z" clip-rule="evenodd" />
            </svg>
            <span>Segurança bancária</span>
          </div>
        </div>
        
        <div class="hero-actions">
          <a href="https://app.financialcontrol.com.br/" target="_blank" rel="noopener noreferrer" class="btn btn-primary">
            Comece Grátis Agora
            <svg class="btn-icon" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd" />
            </svg>
          </a>
          <a href="https://app.financialcontrol.com.br/" target="_blank" rel="noopener noreferrer" class="btn btn-secondary">
            <svg class="btn-icon-left" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z" clip-rule="evenodd" />
            </svg>
            Fazer Login
          </a>
        </div>

        <p class="cta-subtext">✓ Comece em 2 minutos • Cancele quando quiser</p>
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

.social-proof {
  margin-bottom: 1.5rem;
  animation: fadeInDown 0.6s ease-out;
}

.proof-badge {
  display: inline-block;
  background: linear-gradient(135deg, #2C5F2D 0%, #1e4620 100%);
  color: #FFFFFF;
  padding: 0.5rem 1.25rem;
  border-radius: 50px;
  font-size: 0.875rem;
  font-weight: 600;
  box-shadow: 0 4px 12px rgba(44, 95, 45, 0.2);
}

.hero-title {
  font-size: 3.25rem;
  font-weight: 700;
  color: var(--fc-text-primary);
  line-height: 1.15;
  margin: 0 0 1.5rem;
  letter-spacing: -0.02em;
  animation: fadeInUp 0.6s ease-out 0.1s both;
}

.hero-description {
  font-size: 1.125rem;
  color: #4A5568;
  line-height: 1.7;
  margin: 0 0 2rem;
  animation: fadeInUp 0.6s ease-out 0.2s both;
}

.trust-badges {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-bottom: 2rem;
  flex-wrap: wrap;
  animation: fadeInUp 0.6s ease-out 0.3s both;
}

.trust-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #2C5F2D;
  font-size: 0.9375rem;
  font-weight: 500;
}

.trust-icon {
  width: 20px;
  height: 20px;
  color: #2C5F2D;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
  margin-bottom: 1rem;
  animation: fadeInUp 0.6s ease-out 0.4s both;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 2.25rem;
  border-radius: 8px;
  font-weight: 600;
  font-size: 1.0625rem;
  text-decoration: none;
  transition: all 0.2s ease;
  border: none;
  cursor: pointer;
}

.btn-primary {
  background: linear-gradient(135deg, #2C5F2D 0%, #1e4620 100%);
  color: #FFFFFF;
  box-shadow: 0 4px 14px rgba(44, 95, 45, 0.3);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(44, 95, 45, 0.4);
}

.btn-secondary {
  background: transparent;
  color: #2C5F2D;
  border: 2px solid #2C5F2D;
}

.btn-secondary:hover {
  background: #2C5F2D;
  color: #FFFFFF;
}

.btn-icon {
  width: 20px;
  height: 20px;
}

.btn-icon-left {
  width: 18px;
  height: 18px;
}

.cta-subtext {
  font-size: 0.9375rem;
  color: #718096;
  margin: 0;
  animation: fadeInUp 0.6s ease-out 0.5s both;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInDown {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 768px) {
  .hero {
    padding: 3rem 0 4rem;
  }
  
  .hero-title {
    font-size: 2.25rem;
  }
  
  .hero-description {
    font-size: 1rem;
  }
  
  .hero-description br {
    display: none;
  }

  .trust-badges {
    gap: 1rem;
  }

  .trust-item {
    font-size: 0.875rem;
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
