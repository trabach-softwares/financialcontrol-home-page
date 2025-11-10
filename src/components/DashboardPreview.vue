<template>
  <section class="dashboard-preview">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Visualize suas finanças em tempo real</h2>
        <p class="section-subtitle">Dashboard intuitivo com todas as informações que você precisa</p>
      </div>

      <div class="preview-container">
        <div class="mockup-browser">
          <div class="browser-header">
            <div class="browser-dots">
              <span class="dot red"></span>
              <span class="dot yellow"></span>
              <span class="dot green"></span>
            </div>
            <div class="browser-url">app.financialcontrol.com.br</div>
          </div>
          
          <div class="dashboard-content">
            <div class="welcome-banner">
              <div class="welcome-text">
                <h3>Olá, <strong>Maria Silva</strong> 👋</h3>
                <p>Seu controle financeiro em tempo real</p>
              </div>
              <div class="action-buttons">
                <button class="btn-income">+ Receita</button>
                <button class="btn-expense">- Despesa</button>
              </div>
            </div>

            <div class="metrics-grid">
              <div class="metric-card income">
                <div class="metric-icon">↑</div>
                <div class="metric-info">
                  <span class="metric-label">RECEITAS</span>
                  <span class="metric-value">R$ 15.450,00</span>
                  <span class="metric-change positive">+12.5%</span>
                </div>
              </div>

              <div class="metric-card expense">
                <div class="metric-icon">↓</div>
                <div class="metric-info">
                  <span class="metric-label">DESPESAS</span>
                  <span class="metric-value">R$ 8.230,00</span>
                  <span class="metric-change neutral">0.0%</span>
                </div>
              </div>

              <div class="metric-card balance">
                <div class="metric-icon">💰</div>
                <div class="metric-info">
                  <span class="metric-label">SALDO TOTAL</span>
                  <span class="metric-value highlight">R$ 7.220,00</span>
                  <span class="metric-badge">Posição Atual</span>
                </div>
              </div>

              <div class="metric-card transactions">
                <div class="metric-icon">📊</div>
                <div class="metric-info">
                  <span class="metric-label">TRANSAÇÕES</span>
                  <span class="metric-value">28</span>
                  <span class="metric-badge">Este mês</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="features-highlight">
        <div class="highlight-item">
          <div class="highlight-icon">⚡</div>
          <h4>Atualização Instantânea</h4>
          <p>Veja suas finanças atualizarem em tempo real</p>
        </div>
        <div class="highlight-item">
          <div class="highlight-icon">📱</div>
          <h4>Acesso Multiplataforma</h4>
          <p>Desktop, tablet e mobile sempre sincronizados</p>
        </div>
        <div class="highlight-item">
          <div class="highlight-icon">🎯</div>
          <h4>Insights Inteligentes</h4>
          <p>Análises automáticas para decisões melhores</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.dashboard-preview {
  padding: 6rem 0;
  background: linear-gradient(180deg, #FFFFFF 0%, #F4F5F7 100%);
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

.preview-container {
  margin-bottom: 4rem;
}

.mockup-browser {
  background: #FFFFFF;
  border-radius: 12px;
  box-shadow: 0 20px 60px rgba(9, 30, 66, 0.15);
  overflow: hidden;
}

.browser-header {
  background: #E8EAED;
  padding: 0.75rem 1rem;
  display: flex;
  align-items: center;
  gap: 1rem;
  border-bottom: 1px solid #D1D5DB;
}

.browser-dots {
  display: flex;
  gap: 0.5rem;
}

.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}

.dot.red { background: #FF5F56; }
.dot.yellow { background: #FFBD2E; }
.dot.green { background: #27C93F; }

.browser-url {
  flex: 1;
  background: #FFFFFF;
  padding: 0.4rem 1rem;
  border-radius: 6px;
  font-size: 0.875rem;
  color: var(--fc-text-tertiary);
  text-align: center;
}

.dashboard-content {
  padding: 2rem;
  background: #F9FAFB;
}

.welcome-banner {
  background: linear-gradient(135deg, #2C5F2D 0%, #1e4620 100%);
  color: #FFFFFF;
  padding: 2rem;
  border-radius: 12px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
  box-shadow: 0 4px 12px rgba(44, 95, 45, 0.3);
}

.welcome-text h3 {
  font-size: 1.75rem;
  margin: 0 0 0.5rem;
  font-weight: 600;
}

.welcome-text p {
  margin: 0;
  opacity: 0.9;
  font-size: 1rem;
}

.action-buttons {
  display: flex;
  gap: 1rem;
}

.btn-income, .btn-expense {
  padding: 0.75rem 1.5rem;
  border-radius: 8px;
  font-weight: 600;
  font-size: 1rem;
  border: none;
  cursor: pointer;
  transition: all 0.2s ease;
}

.btn-income {
  background: #FFFFFF;
  color: #2C5F2D;
  font-weight: 700;
}

.btn-income:hover {
  background: #f0f9f0;
  transform: translateY(-2px);
}

.btn-expense {
  background: rgba(255, 255, 255, 0.2);
  color: #FFFFFF;
  border: 2px solid #FFFFFF;
}

.btn-expense:hover {
  background: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
}

.metrics-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.5rem;
}

.metric-card {
  background: #FFFFFF;
  border-radius: 12px;
  padding: 1.5rem;
  display: flex;
  align-items: center;
  gap: 1rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
  transition: transform 0.2s ease;
}

.metric-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.12);
}

.metric-icon {
  width: 56px;
  height: 56px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.75rem;
  flex-shrink: 0;
}

.metric-card.income .metric-icon {
  background: #E3FCEF;
  color: #2C5F2D;
}

.metric-card.expense .metric-icon {
  background: #FFEBE6;
  color: #DE350B;
}

.metric-card.balance .metric-icon {
  background: #DEEBFF;
}

.metric-card.transactions .metric-icon {
  background: #EAE6FF;
}

.metric-info {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.metric-label {
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--fc-text-tertiary);
  letter-spacing: 0.5px;
}

.metric-value {
  font-size: 1.5rem;
  font-weight: 700;
  color: var(--fc-text-primary);
}

.metric-value.highlight {
  color: #2C5F2D;
}

.metric-change {
  font-size: 0.875rem;
  font-weight: 600;
}

.metric-change.positive {
  color: #2C5F2D;
}

.metric-change.neutral {
  color: var(--fc-text-tertiary);
}

.metric-badge {
  font-size: 0.75rem;
  color: #6554C0;
  font-weight: 600;
}

.features-highlight {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  margin-top: 3rem;
}

.highlight-item {
  text-align: center;
  padding: 2rem 1.5rem;
}

.highlight-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.highlight-item h4 {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--fc-text-primary);
  margin: 0 0 0.5rem;
}

.highlight-item p {
  font-size: 1rem;
  color: var(--fc-text-secondary);
  margin: 0;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .dashboard-preview {
    padding: 3rem 0;
  }

  .section-title {
    font-size: 1.75rem;
  }

  .section-subtitle {
    font-size: 1rem;
  }

  .welcome-banner {
    flex-direction: column;
    text-align: center;
    gap: 1.5rem;
  }

  .action-buttons {
    width: 100%;
    flex-direction: column;
  }

  .btn-income, .btn-expense {
    width: 100%;
  }

  .dashboard-content {
    padding: 1rem;
  }

  .metrics-grid {
    grid-template-columns: 1fr;
  }
}
</style>
