<template>
  <section class="security-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Seus dados estão seguros conosco</h2>
        <p class="section-subtitle">Segurança de nível bancário para proteger suas informações financeiras</p>
      </div>

      <div class="security-grid">
        <div class="security-card">
          <div class="security-icon">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <h3>Padrão Bancário</h3>
          <p>Mesmos protocolos de segurança usados por grandes instituições financeiras</p>
        </div>

        <div class="security-card">
          <div class="security-icon">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect x="3" y="11" width="18" height="11" rx="2" stroke="currentColor" stroke-width="2"/>
              <path d="M7 11V7a5 5 0 0110 0v4" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
            </svg>
          </div>
          <h3>Criptografia 256-bit</h3>
          <p>Todos os dados são criptografados em trânsito e em repouso</p>
        </div>

        <div class="security-card">
          <div class="security-icon">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <h3>ISO 27001</h3>
          <p>Certificação internacional em gestão de segurança da informação</p>
        </div>

        <div class="security-card">
          <div class="security-icon">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <h3>Dados Protegidos</h3>
          <p>Backup automático diário com redundância geográfica</p>
        </div>

        <div class="security-card">
          <div class="security-icon">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <h3>Anti-Fraude</h3>
          <p>Monitoramento 24/7 contra atividades suspeitas e fraudes</p>
        </div>

        <div class="security-card">
          <div class="security-icon">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <h3>Certificado SSL</h3>
          <p>Conexão segura HTTPS em todas as páginas do sistema</p>
        </div>
      </div>

      <div class="compliance-badges">
        <div class="badge-item">
          <div class="badge-icon">🏦</div>
          <span>Padrão Bancário</span>
        </div>
        <div class="badge-item">
          <div class="badge-icon">✓</div>
          <span>ISO 27001</span>
        </div>
        <div class="badge-item">
          <div class="badge-icon">🔒</div>
          <span>Anti-Fraude</span>
        </div>
        <div class="badge-item">
          <div class="badge-icon">🛡️</div>
          <span>SSL/TLS</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.security-section {
  padding: 6rem 0;
  background: linear-gradient(180deg, #FFFFFF 0%, #F9FAFB 100%);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--fc-text-primary);
  margin: 0 0 1rem;
}

.section-subtitle {
  font-size: 1.25rem;
  color: var(--fc-text-secondary);
  margin: 0;
}

.security-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.security-card {
  background: #FFFFFF;
  border: 1px solid #E5E7EB;
  border-radius: 12px;
  padding: 2rem;
  text-align: center;
  transition: all 0.3s ease;
}

.security-card:hover {
  border-color: #2C5F2D;
  transform: translateY(-4px);
  box-shadow: 0 8px 24px rgba(44, 95, 45, 0.1);
}

.security-icon {
  width: 64px;
  height: 64px;
  margin: 0 auto 1.5rem;
  background: linear-gradient(135deg, #2C5F2D 0%, #1e4620 100%);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #FFFFFF;
}

.security-icon svg {
  width: 32px;
  height: 32px;
}

.security-card h3 {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--fc-text-primary);
  margin: 0 0 0.75rem;
}

.security-card p {
  font-size: 1rem;
  color: var(--fc-text-secondary);
  line-height: 1.6;
  margin: 0;
}

.compliance-badges {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 3rem;
  padding: 2rem;
  background: #FFFFFF;
  border-radius: 12px;
  border: 1px solid #E5E7EB;
  flex-wrap: wrap;
}

.badge-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}

.badge-icon {
  width: 48px;
  height: 48px;
  background: #F4F5F7;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
}

.badge-item span {
  font-size: 0.875rem;
  font-weight: 600;
  color: var(--fc-text-primary);
}

@media (max-width: 768px) {
  .security-section {
    padding: 4rem 0;
  }

  .section-title {
    font-size: 2rem;
  }

  .security-grid {
    grid-template-columns: 1fr;
  }

  .compliance-badges {
    gap: 1.5rem;
  }
}
</style>
