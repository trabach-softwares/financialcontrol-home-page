<template>
  <section class="pricing-section" id="planos">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Escolha seu plano e comece a economizar hoje</h2>
        <p class="section-subtitle">Todos os planos incluem 14 dias grátis • Cancele quando quiser • Sem pegadinhas</p>
      </div>

      <div class="pricing-grid">
        <!-- Plans Grid - Sempre mostra planos estáticos -->
        <template>
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
            <div v-if="plan.isPopular" class="popular-badge">🔥 MAIS ESCOLHIDO</div>
            
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

            <div v-if="plan.savings" class="savings-badge">
              💰 {{ plan.savings }}
            </div>

            <a 
              href="https://app.financialcontrol.com.br/" 
              target="_blank" 
              rel="noopener noreferrer" 
              class="btn"
              :class="`btn-${plan.buttonStyle}`"
            >
              {{ plan.buttonText }}
              <svg v-if="plan.isPopular" class="btn-icon" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd" />
              </svg>
            </a>
          </div>
        </template>
      </div>

      <div class="pricing-footer">
        <div class="guarantees">
          <div class="guarantee-item">
            <span class="guarantee-icon">✓</span>
            <span>14 dias grátis sem cartão</span>
          </div>
          <div class="guarantee-item">
            <span class="guarantee-icon">✓</span>
            <span>Cancele a qualquer momento</span>
          </div>
          <div class="guarantee-item">
            <span class="guarantee-icon">✓</span>
            <span>Suporte em português</span>
          </div>
          <div class="guarantee-item">
            <span class="guarantee-icon">✓</span>
            <span>Seus dados 100% seguros</span>
          </div>
        </div>
        <p class="pricing-note">Mais de 5.000 empresas já confiam no Financial Control</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

// Usar planos estáticos por padrão (sem chamada de API que causa CORS)
const plans = ref([
  {
    id: 'free',
    name: 'Gratuito',
    description: 'Ideal para começar hoje mesmo',
    price: 0,
    currency: 'R$',
    period: '/mês',
    isPopular: false,
    features: [
      '✨ Até 50 transações por mês',
      '📊 Dashboard básico em tempo real',
      '📁 3 categorias personalizadas',
      '📈 Relatórios mensais',
      '✉️ Suporte por email'
    ],
    buttonText: 'Começar Grátis',
    buttonStyle: 'secondary'
  },
  {
    id: 'pro',
    name: 'Profissional',
    description: 'Para quem quer resultados sérios',
    price: 29.90,
    currency: 'R$',
    period: '/mês',
    isPopular: true,
    features: [
      '🚀 Transações ilimitadas',
      '📊 Dashboard avançado com IA',
      '📁 Categorias ilimitadas',
      '📈 Gráficos e análises avançadas',
      '💾 Exportação PDF e Excel',
      '🎯 Metas financeiras automáticas',
      '⚡ Suporte prioritário',
      '📱 App mobile completo'
    ],
    buttonText: 'Começar Teste Grátis',
    buttonStyle: 'primary',
    savings: 'Economize até 30% nos gastos'
  },
  {
    id: 'premium',
    name: 'Empresarial',
    description: 'Solução completa para sua empresa',
    price: 89.90,
    currency: 'R$',
    period: '/mês',
    isPopular: false,
    features: [
      '⭐ Tudo do Profissional, mais:',
      '🏦 Integração bancária automática',
      '🤖 IA para categorização inteligente',
      '📋 Relatórios personalizados',
      '🔌 API para integrações',
      '👥 Até 10 usuários simultâneos',
      '🛡️ Backup diário automático',
      '👨‍💼 Gerente de conta dedicado',
      '📞 Suporte 24/7 prioritário'
    ],
    buttonText: 'Falar com Especialista',
    buttonStyle: 'secondary'
  }
])

const formatPrice = (price) => {
  if (price === 0) return 'Grátis'
  return price.toFixed(2).replace('.', ',')
}

// Comentado: chamada de API que causa erro CORS
// Usando planos estáticos definidos acima
/*
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
*/
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
  box-shadow: 0 8px 24px rgba(44, 95, 45, 0.15);
  transform: scale(1.05);
}

.pricing-card.featured:hover {
  transform: scale(1.05) translateY(-8px);
}

.popular-badge {
  position: absolute;
  top: -14px;
  left: 50%;
  transform: translateX(-50%);
  background: linear-gradient(135deg, #FF6B35 0%, #FF8C42 100%);
  color: #FFFFFF;
  padding: 0.5rem 1.5rem;
  border-radius: 20px;
  font-size: 0.875rem;
  font-weight: 700;
  box-shadow: 0 4px 12px rgba(255, 107, 53, 0.4);
  letter-spacing: 0.5px;
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

.savings-badge {
  background: linear-gradient(135deg, #FFF4E6 0%, #FFE7CC 100%);
  border: 2px solid #FF8C42;
  color: #CC5500;
  padding: 0.75rem 1rem;
  border-radius: 8px;
  text-align: center;
  font-weight: 700;
  font-size: 0.9375rem;
  margin-bottom: 1.5rem;
}

.btn {
  width: 100%;
  padding: 1rem 1.5rem;
  border-radius: 8px;
  font-weight: 700;
  font-size: 1rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  text-decoration: none;
  text-align: center;
  transition: all 0.2s ease;
  border: none;
  cursor: pointer;
}

.btn-icon {
  width: 20px;
  height: 20px;
}

.btn-primary {
  background: linear-gradient(135deg, #2C5F2D 0%, #1e4620 100%);
  color: #FFFFFF;
  box-shadow: 0 4px 12px rgba(44, 95, 45, 0.25);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(44, 95, 45, 0.35);
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
  padding-top: 3rem;
  margin-top: 3rem;
  border-top: 1px solid #E5E7EB;
}

.guarantees {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.guarantee-item {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  font-size: 0.9375rem;
  color: var(--fc-text-secondary);
}

.guarantee-icon {
  width: 24px;
  height: 24px;
  background: #2C5F2D;
  color: #FFFFFF;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 0.875rem;
  flex-shrink: 0;
}

.pricing-note {
  font-size: 1.0625rem;
  color: var(--fc-text-primary);
  font-weight: 600;
  margin: 0;
}

@media (max-width: 968px) {
  .pricing-section {
    padding: 4rem 0;
  }

  .section-title {
    font-size: 2rem;
  }
  
  .section-subtitle {
    font-size: 1rem;
  }

  .pricing-grid {
    grid-template-columns: 1fr;
    max-width: 500px;
    margin-left: auto;
    margin-right: auto;
  }
  
  .pricing-card.featured {
    transform: scale(1);
  }
  
  .pricing-card.featured:hover {
    transform: translateY(-8px);
  }
  
  .guarantees {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
}
</style>
