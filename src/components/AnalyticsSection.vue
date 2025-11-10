<template>
  <section class="analytics-section">
    <div class="container">
      <div class="section-content">
        <div class="content-text">
          <span class="badge">Analytics Avançado</span>
          <h2>Acompanhe a evolução do seu negócio</h2>
          <p>Gráficos interativos que mostram receitas, despesas e saldo final ao longo do tempo. Filtre por período e tome decisões baseadas em dados reais.</p>
          
          <ul class="features-list">
            <li>
              <svg class="check-icon" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              <span>Visualização por período (7 dias, 30 dias, 3 meses, 6 meses, 1 ano)</span>
            </li>
            <li>
              <svg class="check-icon" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              <span>Gráficos de linha com receitas, despesas e saldo final</span>
            </li>
            <li>
              <svg class="check-icon" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              <span>Exportação de relatórios em PDF e Excel</span>
            </li>
            <li>
              <svg class="check-icon" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
              </svg>
              <span>Análise detalhada por categoria de gastos</span>
            </li>
          </ul>
        </div>

        <div class="chart-mockup">
          <div class="chart-header">
            <div class="chart-title">
              <div class="chart-icon">📈</div>
              <div>
                <h3>Evolução Financeira</h3>
                <p>Acompanhe suas receitas e despesas ao longo do tempo</p>
              </div>
            </div>
            <div class="period-filters">
              <button class="period-btn active">Este mês</button>
              <button class="period-btn">7 dias</button>
              <button class="period-btn">30 dias</button>
              <button class="period-btn">3 meses</button>
            </div>
          </div>

          <div class="chart-container">
            <svg class="chart-svg" viewBox="0 0 600 300" preserveAspectRatio="none">
              <!-- Grid lines -->
              <line x1="0" y1="50" x2="600" y2="50" stroke="#E5E7EB" stroke-width="1"/>
              <line x1="0" y1="100" x2="600" y2="100" stroke="#E5E7EB" stroke-width="1"/>
              <line x1="0" y1="150" x2="600" y2="150" stroke="#E5E7EB" stroke-width="1"/>
              <line x1="0" y1="200" x2="600" y2="200" stroke="#E5E7EB" stroke-width="1"/>
              <line x1="0" y1="250" x2="600" y2="250" stroke="#E5E7EB" stroke-width="1"/>
              
              <!-- Receitas (green line) -->
              <polyline points="50,200 150,150 250,100 350,120 450,140 550,160" fill="none" stroke="#2C5F2D" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
              
              <!-- Despesas (red line) -->
              <polyline points="50,220 150,180 250,140 350,160 450,170 550,180" fill="none" stroke="#DE350B" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
              
              <!-- Saldo (green line) -->
              <polyline points="50,230 150,210 250,170 350,180 450,190 550,200" fill="none" stroke="#2C5F2D" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>

          <div class="chart-legend">
            <div class="legend-item">
              <span class="legend-color income"></span>
              <div>
                <span class="legend-label">RECEITAS</span>
                <span class="legend-value">R$ 18.500,00</span>
              </div>
            </div>
            <div class="legend-item">
              <span class="legend-color expense"></span>
              <div>
                <span class="legend-label">DESPESAS</span>
                <span class="legend-value">R$ 12.300,00</span>
              </div>
            </div>
            <div class="legend-item">
              <span class="legend-color balance"></span>
              <div>
                <span class="legend-label">SALDO FINAL</span>
                <span class="legend-value positive">R$ 6.200,00</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
.analytics-section {
  padding: 6rem 0;
  background: #FFFFFF;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

.section-content {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 4rem;
  align-items: center;
}

.badge {
  display: inline-block;
  background: var(--fc-primary-bg);
  color: var(--fc-primary);
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.875rem;
  font-weight: 600;
  margin-bottom: 1.5rem;
}

.content-text h2 {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--fc-text-primary);
  margin: 0 0 1.5rem;
  line-height: 1.2;
}

.content-text > p {
  font-size: 1.125rem;
  color: var(--fc-text-secondary);
  line-height: 1.7;
  margin: 0 0 2rem;
}

.features-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.features-list li {
  display: flex;
  align-items: flex-start;
  gap: 0.75rem;
  font-size: 1rem;
  color: var(--fc-text-secondary);
  line-height: 1.6;
}

.check-icon {
  width: 24px;
  height: 24px;
  color: #2C5F2D;
  flex-shrink: 0;
  margin-top: 2px;
}

.chart-mockup {
  background: #FFFFFF;
  border: 1px solid #E5E7EB;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
}

.chart-header {
  padding: 1.5rem;
  border-bottom: 1px solid #E5E7EB;
}

.chart-title {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.5rem;
}

.chart-icon {
  width: 48px;
  height: 48px;
  background: linear-gradient(135deg, #2C5F2D 0%, #1e4620 100%);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
}

.chart-title h3 {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--fc-text-primary);
  margin: 0;
}

.chart-title p {
  font-size: 0.875rem;
  color: var(--fc-text-secondary);
  margin: 0.25rem 0 0;
}

.period-filters {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.period-btn {
  padding: 0.5rem 1rem;
  border: 1px solid #E5E7EB;
  background: #FFFFFF;
  border-radius: 6px;
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--fc-text-secondary);
  cursor: pointer;
  transition: all 0.2s ease;
}

.period-btn:hover {
  border-color: var(--fc-primary);
  color: var(--fc-primary);
}

.period-btn.active {
  background: #2C5F2D;
  color: #FFFFFF;
  border-color: #2C5F2D;
}

.chart-container {
  padding: 2rem 1.5rem;
  background: #F9FAFB;
}

.chart-svg {
  width: 100%;
  height: 200px;
}

.chart-legend {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
  padding: 1.5rem;
  background: #F9FAFB;
  border-top: 1px solid #E5E7EB;
}

.legend-item {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.legend-color {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  flex-shrink: 0;
}

.legend-color.income {
  background: #2C5F2D;
}

.legend-color.expense {
  background: #DE350B;
}

.legend-color.balance {
  background: #2C5F2D;
}

.legend-item > div {
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}

.legend-label {
  font-size: 0.75rem;
  font-weight: 600;
  color: var(--fc-text-tertiary);
  letter-spacing: 0.5px;
}

.legend-value {
  font-size: 1.125rem;
  font-weight: 700;
  color: var(--fc-text-primary);
}

.legend-value.positive {
  color: #2C5F2D;
}

@media (max-width: 968px) {
  .section-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .content-text h2 {
    font-size: 2rem;
  }

  .chart-legend {
    grid-template-columns: 1fr;
  }

  .period-filters {
    justify-content: center;
  }
}
</style>
