# 💰 Controle Financeiro - Landing Page

Landing page moderna e responsiva para o sistema de Controle Financeiro, desenvolvida com Vue.js 3 e Vite.

![Preview](https://img.shields.io/badge/Vue.js-3.4-4FC08D?style=flat&logo=vue.js)
![Vite](https://img.shields.io/badge/Vite-5.1-646CFF?style=flat&logo=vite)

## 🎨 Design

- **Paleta de Cores**: Finance Trust (Paleta 1)
- **Cores Principais**: 
  - Primary: `#0052CC` (Azul corporativo)
  - Secondary: `#00A876` (Verde crescimento)
  - Texto: `#172B4D` (Azul escuro)
- **Tipografia**: System fonts (-apple-system, Segoe UI, Roboto)
- **Acessibilidade**: Contraste WCAG AAA (7.2:1+)

## 🚀 Tecnologias

- **Vue.js 3** - Framework progressivo
- **Vite** - Build tool ultrarrápido
- **CSS Modules** - Scoped styles
- **SVG Icons** - Ícones inline otimizados

## 📦 Instalação

```bash
# Instalar dependências
npm install

# Configurar variáveis de ambiente
cp .env.example .env
# Edite o arquivo .env se necessário

# Executar em modo desenvolvimento
npm run dev

# Build para produção
npm run build

# Preview do build de produção
npm run preview
```

## ⚙️ Configuração

### Variáveis de Ambiente

Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:

```bash
# URL base da API
VITE_API_BASE_URL=https://app.financialcontrol.com.br
```

**Nota**: No Vite, todas as variáveis de ambiente acessíveis pelo cliente devem começar com `VITE_`.

## 📁 Estrutura do Projeto

```
financialcontrol-home-page/
├── src/
│   ├── components/
│   │   ├── Header.vue           # Cabeçalho com navegação
│   │   ├── HeroSection.vue      # Seção principal com CTAs
│   │   ├── FeaturesSection.vue  # Cards de recursos
│   │   └── Footer.vue           # Rodapé com copyright
│   ├── App.vue                  # Componente raiz
│   ├── main.js                  # Entry point
│   └── style.css                # Design tokens e estilos globais
├── index.html
├── vite.config.js
└── package.json
```

## 🎯 Recursos Implementados

### ✅ Header
- Logo com ícone SVG
- Menu de navegação (Recursos, Planos, Entrar)
- Botão CTA "Começar Grátis"
- Sticky no scroll
- Responsivo (menu mobile simplificado)

### ✅ Hero Section
- Título principal impactante
- Descrição do produto
- 2 CTAs (Começar Gratuitamente + Já tenho conta)
- Gradiente de fundo sutil
- Totalmente responsivo

### ✅ Features Section
- 3 cards de recursos principais:
  - 📊 Dashboard Completo
  - ⚡ Relatórios Detalhados
  - 🔒 Seguro e Confiável
- Ícones SVG customizados
- Efeito hover com elevação
- Grid responsivo

### ✅ Footer
- Logo e nome da empresa
- Copyright 2025
- Layout flexível responsivo

## 🎨 Paleta de Cores (Finance Trust)

```css
--fc-primary: #0052CC;         /* Azul corporativo */
--fc-secondary: #00A876;       /* Verde crescimento */
--fc-accent: #6554C0;          /* Roxo insights */
--fc-positive: #36B37E;        /* Verde sucesso */
--fc-negative: #DE350B;        /* Vermelho alerta */
--fc-text-primary: #172B4D;    /* Texto principal */
--fc-text-secondary: #5E6C84;  /* Texto secundário */
```

## 📱 Responsividade

- **Desktop**: Layout completo com 3 colunas
- **Tablet**: Grid adaptativo 2 colunas
- **Mobile**: Layout empilhado 1 coluna
- Breakpoint principal: `768px`

## ♿ Acessibilidade

- ✅ Contraste WCAG AAA em textos principais
- ✅ Contraste WCAG AA em todos os elementos
- ✅ Focus visible em todos os elementos interativos
- ✅ Navegação por teclado funcional
- ✅ Scroll suave (smooth scroll)

## 🔧 Customização

### Variáveis de Ambiente

Para alterar a URL da API, edite o arquivo `.env`:

```bash
VITE_API_BASE_URL=https://app.financialcontrol.com.br
```

### Cores

Para alterar as cores, edite as variáveis CSS em `src/style.css`:

```css
:root {
  --fc-primary: #0052CC;
  --fc-secondary: #00A876;
  /* ... outras variáveis */
}
```

## 🔌 Integração com API

### Endpoint de Planos

A seção de preços consome o endpoint:

```bash
POST {VITE_API_BASE_URL}/api/public/plans
Content-Type: application/json
Body: ""
```

**Estrutura de resposta esperada:**

```json
{
  "success": true,
  "data": {
    "plans": [
      {
        "id": "3c25d559-fb8a-436c-a414-e4991e6e6f4c",
        "name": "Gratuito",
        "description": "Perfeito para começar",
        "price": 0,
        "features": [
          "Até 10 transações/mês",
          "Dashboard básico"
        ],
        "maxTransactions": 10,
        "recommended": false,
        "popular": false
      }
    ],
    "total": 3
  },
  "message": "Planos recuperados com sucesso"
}
```

**Mapeamento automático:**
- `currency`: "R$" (adicionado automaticamente)
- `period`: "/mês" (adicionado automaticamente)
- `isCurrent`: `true` se `price === 0`
- `isPopular`: baseado em `popular`
- `buttonText`: "Plano Ativo" para gratuito, "Assinar Plano" para pagos
- `buttonStyle`: `outline` para gratuito, `primary` para popular, `secondary` para outros

**Fallback**: Se a API falhar, o componente usa planos estáticos padrão.

## 🚀 Deploy

### Vercel
```bash
npm install -g vercel
vercel
```

### Netlify
```bash
npm run build
# Fazer upload da pasta dist/
```

### GitHub Pages
```bash
npm run build
# Configurar GitHub Pages para servir a pasta dist/
```

## 📄 Licença

© 2025 Controle Financeiro. Todos os direitos reservados.

## 👨‍💻 Desenvolvedor

Desenvolvido com ❤️ usando Vue.js 3 + Vite

---

**Status**: ✅ Pronto para produção
Repositorio para Home Page do financial control
