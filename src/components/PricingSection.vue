<template>
  <section class="pricing-section" id="planos">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Selecione o plano ideal para suas necessidades</h2>
        <p class="section-subtitle">Comece grátis e expanda conforme seu negócio cresce</p>
      </div>

      <div class="pricing-grid">
        <!-- Loading State -->
        <div v-if="loading" class="loading-container">
          <div class="spinner"></div>
          <p>Carregando planos...</p>
        </div>

        <!-- Error State -->
        <div v-else-if="error" class="error-container">
          <p>⚠️ {{ error }}</p>
        </div>

        <!-- Plans Grid -->
        <template v-else>
          <div 
            v-for="plan in plans" 
            :key="plan.id"
            class="pricing-card"
            :class="{ 
              'featured': plan.isPopular,
              'free': plan.name.toLowerCase() === 'gratuito',
              'pro': plan.name.toLowerCase() === 'pro',
              'premium': plan.name.toLowerCase() === 'premium'
            }"
          >
            <div v-if="plan.isPopular" class="popular-badge">Mais Popular</div>
            
            <div class="card-header">
              <h3 class="plan-name">{{ plan.name }}</h3>
              <p class="plan-description">{{ plan.description }}</p>
            </div>

            <div class="price-container">
              <span class="currency">{{ plan.currency }}</span>
              <span class="price">{{ formatPrice(plan.price) }}</span>
              <span class="period">{{ plan.period }}</span>
            </div>

            <div class="features-container">
              <p class="features-title">O que está incluído:</p>
              <ul class="features-list">
                <li v-for="(feature, index) in plan.features" :key="index">
                  <svg class="check" viewBox="0 0 20 20" fill="currentColor">
                    <path fill-rule="evenodd" d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z" clip-rule="evenodd" />
                  </svg>
                  {{ feature }}
                </li>
              </ul>
            </div>

            <a 
              href="https://app.financialcontrol.com.br/" 
              target="_blank" 
              rel="noopener noreferrer" 
              class="btn"
              :class="`btn-${plan.buttonStyle}`"
            >
              {{ plan.buttonText }}
            </a>
          </div>
        </template>
      </div>

      <div class="pricing-footer">
        <p>💳 Todos os planos incluem 14 dias de teste grátis • Cancele quando quiser</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const plans = ref([])
const loading = ref(true)
const error = ref(null)

// Obter URL da API das variáveis de ambiente
const API_BASE_URL = import.meta.env.VITE_API_BASE_URL

const fetchPlans = async () => {
  try {
    loading.value = true
    const response = await fetch(`${API_BASE_URL}/public/plans`, {
      method: 'GET',
      headers: {
        'Content-Type': 'application/json'
      }
    })
    
    if (!response.ok) {
      throw new Error('Erro ao carregar planos')
    }
    
    const result = await response.json()
    
    // Verificar se a resposta tem a estrutura esperada
    if (result.success && result.data && result.data.plans) {
      // Mapear os dados da API para o formato esperado pelo componente
      plans.value = result.data.plans.map(plan => ({
        ...plan,
        currency: 'R$',
        period: '/mês',
        isPopular: plan.popular || false,
        buttonText: 'Assinar Plano',
        buttonStyle: plan.popular ? 'primary' : 'secondary'
      }))
    } else {
      throw new Error('Formato de resposta inválido')
    }
  } catch (err) {
    console.error('Erro ao buscar planos:', err)
    error.value = err.message
    // Fallback: usar planos estáticos se a API falhar
    plans.value = getStaticPlans()
  } finally {
    loading.value = false
  }
}

const getStaticPlans = () => {
  return [
    {
      id: 'free',
      name: 'Gratuito',
      description: 'Perfeito para começar',
      price: 0,
      currency: 'R$',
      period: '/mês',
      isPopular: false,
      features: [
        'Até 10 transações/mês',
        'Dashboard básico',
        '3 categorias personalizadas',
        'Relatórios básicos',
        'Suporte por email'
      ],
      buttonText: 'Assinar Plano',
      buttonStyle: 'secondary'
    },
    {
      id: 'pro',
      name: 'Pro',
      description: 'Para profissionais',
      price: 6,
      currency: 'R$',
      period: '/mês',
      isPopular: true,
      features: [
        'Transações ilimitadas',
        'Dashboard avançado',
        'Categorias ilimitadas',
        'Gráficos avançados',
        'Exportação PDF/Excel',
        'Metas financeiras',
        'Suporte prioritário'
      ],
      buttonText: 'Assinar Plano',
      buttonStyle: 'primary'
    },
    {
      id: 'premium',
      name: 'Premium',
      description: 'Solução completa',
      price: 89.90,
      currency: 'R$',
      period: '/mês',
      isPopular: false,
      features: [
        'Tudo do Pro, mais:',
        'Integração bancária',
        'Importação automática',
        'IA para categorizações',
        'Relatórios personalizados',
        'API para integrações',
        'Multi-usuários (5 contas)',
        'Suporte 24/7',
        'Manager dedicado'
      ],
      buttonText: 'Assinar Plano',
      buttonStyle: 'secondary'
    }
  ]
}

const formatPrice = (price) => {
  return price.toFixed(2).replace('.', ',')
}

onMounted(() => {
  fetchPlans()
})
</script>

<style scoped>
.pricing-section {
  padding: 6rem 0;
  background: #F4F5F7;
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

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.loading-container,
.error-container {
  grid-column: 1 / -1;
  text-align: center;
  padding: 4rem 2rem;
}

.spinner {
  width: 48px;
  height: 48px;
  margin: 0 auto 1rem;
  border: 4px solid #E5E7EB;
  border-top-color: #2C5F2D;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}

.loading-container p {
  color: var(--fc-text-secondary);
  font-size: 1rem;
}

.error-container p {
  color: #DE350B;
  font-size: 1rem;
}

.pricing-card {
  background: #FFFFFF;
  border: 2px solid #E5E7EB;
  border-radius: 16px;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  position: relative;
  transition: all 0.3s ease;
}

.pricing-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.12);
}

.pricing-card.featured {
  border-color: #2C5F2D;
  border-width: 3px;
}

.popular-badge {
  position: absolute;
  top: -12px;
  left: 50%;
  transform: translateX(-50%);
  background: #2C5F2D;
  color: #FFFFFF;
  padding: 0.5rem 1.5rem;
  border-radius: 20px;
  font-size: 0.875rem;
  font-weight: 600;
}

.plan-badge {
  display: inline-block;
  background: #E3FCEF;
  color: #00A876;
  padding: 0.375rem 0.75rem;
  border-radius: 6px;
  font-size: 0.75rem;
  font-weight: 600;
  margin-bottom: 1rem;
}

.card-header {
  margin-bottom: 1.5rem;
}

.plan-name {
  font-size: 1.75rem;
  font-weight: 700;
  color: var(--fc-text-primary);
  margin: 0 0 0.5rem;
}

.plan-description {
  font-size: 1rem;
  color: var(--fc-text-secondary);
  margin: 0;
}

.price-container {
  display: flex;
  align-items: baseline;
  margin-bottom: 2rem;
}

.currency {
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--fc-text-primary);
}

.price {
  font-size: 3.5rem;
  font-weight: 700;
  color: #2C5F2D;
  margin: 0 0.25rem;
  line-height: 1;
}

.period {
  font-size: 1rem;
  color: var(--fc-text-secondary);
}

.features-container {
  flex: 1;
  margin-bottom: 2rem;
}

.features-title {
  font-size: 0.875rem;
  font-weight: 600;
  color: var(--fc-text-primary);
  margin: 0 0 1rem;
}

.features-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.features-list li {
  display: flex;
  align-items: flex-start;
  gap: 0.75rem;
  font-size: 0.9375rem;
  color: var(--fc-text-secondary);
  line-height: 1.5;
}

.check {
  width: 20px;
  height: 20px;
  color: #2C5F2D;
  flex-shrink: 0;
  margin-top: 2px;
}

.btn {
  width: 100%;
  padding: 1rem;
  border-radius: 8px;
  font-weight: 600;
  font-size: 1rem;
  text-decoration: none;
  text-align: center;
  transition: all 0.2s ease;
  border: none;
  cursor: pointer;
  display: block;
}

.btn-primary {
  background: #2C5F2D;
  color: #FFFFFF;
}

.btn-primary:hover {
  background: #1e4620;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(44, 95, 45, 0.3);
}

.btn-secondary {
  background: #FFFFFF;
  color: #2C5F2D;
  border: 2px solid #2C5F2D;
}

.btn-secondary:hover {
  background: #2C5F2D;
  color: #FFFFFF;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(44, 95, 45, 0.3);
}

.btn-outline {
  background: transparent;
  color: var(--fc-text-secondary);
  border: 2px solid #E5E7EB;
}

.btn-outline:hover {
  border-color: #2C5F2D;
  color: #2C5F2D;
}

.pricing-footer {
  text-align: center;
  padding-top: 2rem;
  border-top: 1px solid #E5E7EB;
}

.pricing-footer p {
  font-size: 1rem;
  color: var(--fc-text-secondary);
  margin: 0;
}

@media (max-width: 968px) {
  .pricing-section {
    padding: 4rem 0;
  }

  .section-title {
    font-size: 2rem;
  }

  .pricing-grid {
    grid-template-columns: 1fr;
    max-width: 500px;
    margin-left: auto;
    margin-right: auto;
  }
}
</style>
