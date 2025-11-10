<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-logo">
          <img src="/ControleFinanceiro.svg" alt="Financial Control" class="logo-icon">
          <span class="logo-text">Financial Control</span>
        </div>
        
        <div class="footer-copyright">
          © 2025 Financial Control. Todos os direitos reservados.
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
</script>

<style scoped>
.footer {
  background: #F4F5F7;
  padding: 2rem 0;
  margin-top: auto;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 2rem;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.logo-icon {
  width: 28px;
  height: 28px;
}

.logo-text {
  font-weight: 600;
  font-size: 1rem;
  color: var(--fc-text-primary);
}

.footer-copyright {
  color: var(--fc-text-tertiary);
  font-size: 0.875rem;
}

@media (max-width: 768px) {
  .footer-content {
    flex-direction: column;
    text-align: center;
  }
}
</style>
