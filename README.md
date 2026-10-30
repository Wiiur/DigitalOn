# ⚡ DigitalOn — Ecossistema de Sites de Alta Conversão & Placas Inteligentes NFC

![Status do Projeto](https://img.shields.io/badge/Status-Pronto_para_Produção-10B981?style=for-the-badge)
![Performance](https://img.shields.io/badge/Google_Lighthouse-100%2F100-D4AF37?style=for-the-badge)
![Acessibilidade](https://img.shields.io/badge/WCAG_2.2-Nível_AA-3B82F6?style=for-the-badge)
![Arquitetura](https://img.shields.io/badge/Single--File-HTML5_%7C_Tailwind_%7C_JS-090D16?style=for-the-badge)

Documentação técnica e comercial da plataforma oficial da **DigitalOn** (desenvolvida por **Willian Rafael de Oliveira**). Este projeto é uma Landing Page *One-Page* interativa, projetada sob medida para apresentar e vender serviços de **Criação de Sites, Landing Pages de Alta Conversão e Placas Inteligentes NFC / QR Code**.

---

## 📌 1. O Que é o Projeto

A plataforma **DigitalOn** foi concebida não apenas como um site institucional, mas como um **demonstrador prático de engenharia front-end e persuasão comercial (CRO)**. Em vez de apenas prometer qualidade, o próprio site funciona como prova viva de velocidade, interatividade e experiência do usuário.

### Principais Problemas de Mercado Resolvidos pelo Projeto:
1. **Tangibilização antes da compra:** Clientes pequenos e médios costumam ter dificuldade em imaginar como ficará o site de seu nicho ou qual a diferença real entre um plano básico e um plano avançado. O projeto resolve isso com um **Simulador de Mini-Sites ao Vivo** integrado.
2. **Conexão do Físico ao Digital:** Demonstra em tempo real como funciona a **Placa Inteligente NFC + QR Code** no balcão da empresa para multiplicar avaliações 5 estrelas no Google Meu Negócio.
3. **Qualificação Automática de Leads:** Conecta todas as interações da página (escolha de modelo, escolha de pacote e simulador) diretamente ao formulário e ao link dinâmico do WhatsApp.

---

## 🛠️ 2. Tecnologias e Ferramentas Utilizadas

O projeto foi construído seguindo uma arquitetura **Single-File Autocontida (`index.html`)** de altíssima resiliência (*Fail-Safe*), sem necessidade de etapas complexas de *build* para hospedagem imediata:

* **HTML5 Semântico & Acessível (WAI-ARIA):**
  * Uso rigoroso de *landmarks* (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`).
  * Atributos programáticos de acessibilidade (`role="dialog"`, `aria-modal`, `role="tablist"`, `role="switch"`, `aria-expanded`, `aria-live="polite"`).
  * Dados estruturados **Schema.org (`JSON-LD`)** para `ProfessionalService` e **Meta Tags Open Graph** para pré-visualização rica no WhatsApp e redes sociais.
* **Tailwind CSS (Play CDN v3) + CSS3 Nativo Moderno:**
  * Configuração customizada de Design System via `tailwind.config`.
  * *Critical Fallback CSS* embutido no `<style>` para garantir integridade visual mesmo em conexões instáveis.
  * Tipografia fluida com `clamp()` calibrada para resoluções desde `320px` (iPhone SE) até `3440px` (Ultrawide).
* **JavaScript (ES6+ Vanilla Modular & Encapsulado em IIFE):**
  * **Zero vazamento de escopo global:** Toda a lógica roda dentro de uma *Immediately Invoked Function Expression* em modo estrito (`'use strict'`).
  * **Arquitetura Orientada a Dados (`DATA_STORE`):** Os 6 mini-sites, etapas da anatomia, nichos e perguntas frequentes são renderizados dinamicamente a partir de objetos estruturados e sanitizados contra XSS (`escapeHtml`).
  * **Delegação de Eventos Centralizada (*Event Delegation*):** Máxima performance de memória, mantendo eventos ativos mesmo após filtragens e re-renderizações do DOM.
* **Motor de Animação e Rolagem Suave (Degradação Graciosa):**
  * **Lenis Smooth Scroll (`@1.1.13`):** Rolagem inercial suave sincronizada com navegação por âncoras e travamento automático de scroll (*Scroll Lock*) quando modais ou menus estão abertos.
  * **GSAP (`@3.12.5`) + ScrollTrigger:** Preparado para animações aceleradas por GPU (`transform`, `scaleX`, `translate3d`).
* **Tipografia Google Fonts:**
  * `'Plus Jakarta Sans'` (Interface moderna, títulos limpos e leitura de alta legibilidade).
  * `'Instrument Serif'` (Destaques em itálico editorial sofisticado).
  * `'JetBrains Mono'` (Indicadores técnicos, métricas de velocidade e etiquetas de código).

---

## 🎨 3. Design System & Identidade Visual

O projeto passou por uma evolução estética completa: saiu de um modelo quadrado/rígido para uma **interface moderna, leve, orgânica e fluida** (inspirada em referências como *Apple*, *Stripe* e *Linear*).

### Paleta de Cores (Contraste Auditado WCAG 2.2 AA/AAA)
| Token | Cor Hex | Aplicação Principal |
| :--- | :--- | :--- |
| `ink.DEFAULT` | `#090D16` | Fundo principal escuro profundo (OLED Dark) |
| `ink.surface` | `#111827` | Superfície de cards escuros e barra de navegação |
| `ivory.DEFAULT` | `#F8FAFC` | Fundo claro leve para alternância de ritmo visual |
| `ivory.card` | `#FFFFFF` | Cards brancos flutuantes com sombra difusa (`shadow-soft`) |
| `gold.DEFAULT` | `#D4AF37` | Dourado principal para CTAs, selos e destaques em fundo escuro |
| `gold.dark` | `#9A7B1C` | Dourado escuro de alto contraste exclusivo para fundos claros |
| `emeraldConv` | `#10B981` | Verde esmeralda para status online, sucesso e indicadores de lucro |
| `crimsonErr` | `#EF4444` | Vermelho para alertas de comparação e validação de erros |

---

## 🚀 4. O Que Foi Construído (Funcionalidades Detalhadas)

### 4.1. Header Fixo Ponta a Ponta com Logo Centralizada
* Barra superior fixa (`top-0 left-0 right-0 w-full`) com efeito translúcido (`backdrop-blur-xl`).
* **Grid de 3 colunas simétricas (`grid-cols-3`):** Garante que a logo **DigitalOn** permaneça matematicamente centralizada tanto no Desktop quanto no Mobile.
* **Drawer Mobile Acessível:** Menu expansível para telas menores com bloqueio de rolagem de fundo e fechamento automático por tecla `ESC` ou redimensionamento de tela.

### 4.2. Hero Section com Mockup 3D & Barra de Progresso GPU
* Barra superior de progresso de leitura animada via `transform: scaleX()` (zero *Layout Thrashing*).
* Composição visual 3D (Janela de Navegador Desktop + Smartphone Mobile-First + Notificação flutuante de novo lead no WhatsApp) com efeito *parallax* suave ao movimento do mouse em desktops.

### 4.3. Anatomia Interativa da Conversão & Simulador "Antes vs. Depois"
* **Inspecionador de Dobras (Seção 02):** 5 abas interativas acessíveis via clique ou setas do teclado (`ArrowUp`/`ArrowDown`) que explicam o papel psicológico de cada parte de uma Landing Page.
* **Chave Seletora de Cenário (Seção 03):** Alterna em tempo real as métricas de um negócio dependente apenas de Instagram/Linktree versus um negócio com estrutura própria + Placa NFC.

### 4.4. Vitrine de 6 Mini-Sites Únicos com Simulador de Pacotes ao Vivo (Seção 04)
Cada um dos 6 conceitos possui **layout, fotografia e estrutura de código próprios**, permitindo ao cliente abrir o modal e **rolar um mini-site completo por dentro**:
1. **Aurum & Associados (Jurídico/Consultoria):** Hero *Full-Bleed* com fotografia escura de fundo, tipografia clássica e triagem empresarial.
2. **Clínica Clara (Saúde/Fonoaudiologia/Estética):** Layout *Split-Screen* claro com foto lateral da especialista, consultório e selo `5.0 ★`.
3. **Brasa & Açaí Co. (Gastronomia/Delivery):** Cardápio visual interativo com fotos individuais de produtos, preços e simulador de cupom para pedido direto sem taxas.
4. **Vigor Performance (Fitness/Academias):** Layout esportivo de alto impacto com comparativo de planos (Mensal vs. Trimestral) e calculadora de protocolo.
5. **Chave (Arquitetura & Imóveis de Alto Padrão):** Galeria em mosaico fotográfico de residências em condomínio com metragem e filtro de escopo.
6. **Circuito Fibra (Provedores de Internet & Tech):** Interface *Dark Cyber* com velocímetro FTTH (`1000 Mega / 3ms Ping`) e recomendador de planos Wi-Fi 6.

> **Diferencial de Vendas no Simulador:** Dentro do modal de qualquer modelo, o cliente pode clicar nos botões **1. Essencial**, **2. Profissional** e **3. Completo + Placa NFC** para ver os recursos (como o simulador interativo do nicho e a página rápida de balcão NFC) sendo ativados ou bloqueados ao vivo na tela, além de alternar entre visualização **💻 Desktop** e **📱 Celular**.

### 4.5. Laboratório Interativo da Placa NFC (Seção 07)
* Simulação visual onde clicar em `"Simular Aproximação NFC"` move o smartphone ilustrado até a placa física, dispara ondas de sinal concêntricas (*ripple effect*) e acende a tela do aparelho com a avaliação 5 estrelas do Google.

### 4.6. Comparativo Transparente de Planos & Tabela de Entregáveis (Seção 08)
* Apresentação clara dos 3 níveis de serviço (**Essencial R$ 990**, **Profissional R$ 1.690** e **Completo + Placa NFC R$ 2.190**) com lista explícita do que está incluso e do que não está incluso em cada faixa, acompanhada de tabela comparativa direta.

### 4.7. Funil Inteligente de WhatsApp com Persistência e Anti-Bloqueio (Seção 10)
* **Ponte Contextual:** Clicar em *"Quero Este"* em qualquer modelo ou pacote fecha o modal, desliza suavemente até o formulário final, seleciona automaticamente a opção no `<select>` e exibe um *badge* de confirmação.
* **Máscara Brasileira de Telefone & Validação On-Blur:** Formata automaticamente `(DD) 9XXXX-XXXX` sem travar a tecla `Backspace`.
* **Auto-Save (`sessionStorage`):** Preserva os dados digitados caso o usuário recarregue a página acidentalmente no celular.
* **Box de Sucesso com Fallback:** Além de disparar a abertura do WhatsApp com a mensagem formatada, exibe um painel com link direto e botão `"Copiar Mensagem"` caso o navegador interno do Instagram/iOS bloqueie pop-ups.

---

## ⚙️ 5. Como Configurar e Personalizar Rapidamente

Toda a configuração de negócio do site está centralizada em um único objeto JavaScript (`SITE_CONFIG`) localizado no início da tag `<script>`. Não é necessário procurar textos espalhados pelo HTML:

```javascript
const SITE_CONFIG = {
  brandName: 'DigitalOn',
  authorName: 'Willian Rafael de Oliveira',
  authorPhotoUrl: 'assets/foto-perfil.webp', // Caminho da sua foto ou logo
  whatsappNumber: '5519999999999',           // Seu número com DDI (55) + DDD + Número
  city: 'Nova Odessa / Região de Campinas - SP',
  email: 'contato@digitalon.com.br',
  prices: {
    essencial: 'R$ 990',
    profissional: 'R$ 1.690',
    completo: 'R$ 2.190'
  }
};
```

### Configurando o Ícone da Aba (Favicon) e Preview do Link (WhatsApp)
No `<head>` do arquivo `index.html`, certifique-se de apontar para os arquivos da pasta `assets/`:

```html
<!-- Ícone da Aba do Navegador (Favicon) -->
<link rel="icon" href="assets/favicon.png" type="image/png" />

<!-- Preview quando compartilhado no WhatsApp / Redes Sociais -->
<meta property="og:title" content="DigitalOn — Sites Modernos, Landing Pages & Placas NFC" />
<meta property="og:description" content="Transforme sua presença digital. Sites ultra-rápidos, Landing Pages de alta conversão e Placas NFC sem mensalidades." />
<meta property="og:image" content="https://seudominio.com.br/assets/preview-compartilhamento.jpg" />
<meta property="og:url" content="https://seudominio.com.br" />
```

---

## 📂 6. Estrutura Recomendada de Pastas para Publicação

```text
📦 projeto-digitalon/
 ┣ 📂 assets/
 ┃ ┣ 🖼️ favicon.png                 # Logo abstrata quadrada (32x32 ou 192x192px)
 ┃ ┣ 🖼️ foto-perfil.webp            # Sua foto ou logo quadrada DigitalOn
 ┃ ┗ 🖼️ preview-compartilhamento.jpg # Imagem 1200x630px para preview no WhatsApp
 ┣ 📄 index.html                    # Aplicação completa autocontida
 ┗ 📄 README.md                     # Documentação do projeto
```

---

## 🚀 7. Como Publicar (Deploy Gratuito com HTTPS e CDN Global)

Como o projeto é estático e autocontido, pode ser publicado gratuitamente em menos de 2 minutos com nota máxima de velocidade em qualquer uma das plataformas abaixo:
1. **Vercel** (Arraste a pasta ou conecte ao GitHub — *Recomendado*).
2. **Netlify** (Deploy via *Drag & Drop* ou GitHub).
3. **Cloudflare Pages** ou **GitHub Pages**.

---

**Desenvolvido com rigor técnico e foco em conversão por Willian Rafael de Oliveira — DigitalOn.**