# ⚡ DigitalOn — Ecossistema de Sites de Alta Conversão & Placas Inteligentes NFC

![Status do Projeto](https://img.shields.io/badge/Status-Pronto_para_Produção-10B981?style=for-the-badge)
![Performance](https://img.shields.io/badge/Google_Lighthouse-100%2F100-D4AF37?style=for-the-badge)
![Acessibilidade](https://img.shields.io/badge/WCAG_2.2-Nível_AA-3B82F6?style=for-the-badge)
![Arquitetura](https://img.shields.io/badge/Single--File-HTML5_%7C_Tailwind_%7C_JS-090D16?style=for-the-badge)

Documentação técnica e comercial da plataforma oficial da **DigitalOn** (desenvolvida por **Willian Rafael de Oliveira**). Este projeto é uma Landing Page *One-Page* interativa e minimalista, projetada sob medida para apresentar e vender serviços de **Criação de Sites, Landing Pages de Alta Conversão e Placas Inteligentes NFC / QR Code**.

---

## 📌 1. O Que é o Projeto

A plataforma **DigitalOn** funciona como um **demonstrador prático de engenharia front-end e persuasão comercial (CRO/UI/UX)**. Em vez de textos longos ou páginas poluídas, o próprio site entrega uma experiência limpa, ultrarrápida e 100% responsiva para qualquer tela.

### Principais Diferenciais da Nova Versão (Minimalismo Estratégico):
1. **Leitura Enxuta e Zero Poluição Visual:** Textos diretos ao ponto, eliminando seções redundantes e reduzindo a fadiga visual no celular e no computador.
2. **Simulador de Mini-Sites ao Vivo (6 Nichos):** O visitante pode abrir o modal e testar 6 arquiteturas exclusivas (Advocacia, Clínica, Delivery, Academia, Arquitetura e Provedor de Internet), alternando entre visão **💻 PC** e **📱 Celular** e testando os recursos de cada pacote em tempo real.
3. **Modelo Comercial "Valor Sob Consulta":** Apresenta de forma clara o escopo dos 3 planos (**Essencial**, **Profissional** e **Completo + Placa NFC**), direcionando o lead qualificado diretamente para o WhatsApp para consultar o orçamento personalizado.
4. **Simulador Físico + Digital (Placa NFC):** Demonstra em tempo real como funciona a aproximação do celular na Placa NFC de balcão para gerar avaliações 5 estrelas no Google.

---

## 🛠️ 2. Tecnologias e Ferramentas Utilizadas

Arquitetura **Single-File Autocontida (`index.html`)** de altíssima performance:

* **HTML5 Semântico & Acessível (WAI-ARIA):** Landmarks estruturados, atributos de acessibilidade para modais/switches, Schema.org (`JSON-LD`) e Meta Tags Open Graph para preview no WhatsApp.
* **Tailwind CSS (Play CDN v3) + CSS3 Nativo:** Design System customizado (`ink`, `ivory`, `gold`, `emeraldConv`) e tipografia fluida com `clamp()` adaptada de `320px` até telas Ultrawide.
* **JavaScript (ES6+ Vanilla Modular em IIFE):**
  * **Zero vazamento de escopo global:** Lógica encapsulada em modo estrito (`'use strict'`).
  * **Renderização Dinâmica:** Portfólio, simulador de pacotes, comparativo Antes/Depois e FAQ gerados via estado centralizado e sanitizados (`escapeHtml`).
  * **Event Delegation:** Ouvinte único otimizado para máxima fluidez de memória.
* **Lenis Smooth Scroll & GSAP:** Rolagem inercial suave e barra de progresso de leitura acelerada via GPU (`transform: scaleX`).

---

## 🚀 3. Funcionalidades em Destaque

* **Header Fixo Simétrico (`grid-cols-3`):** Logo **DigitalOn** centralizada no Desktop e Mobile, com menu Drawer responsivo.
* **Vitrine Interativa de 6 Mini-Sites:**
  1. **Aurum & Associados (Jurídico):** Layout editorial escuro com triagem empresarial.
  2. **Clínica Clara (Saúde & Estética):** Layout *Split-Screen* claro com guia por perfil de paciente.
  3. **Brasa & Açaí Co. (Gastronomia/Delivery):** Cardápio visual com fotos de produtos e simulador de combo.
  4. **Vigor Performance (Fitness/Academias):** Layout esportivo com calculadora de protocolo.
  5. **Chave (Arquitetura & Imóveis):** Galeria em mosaico fotográfico de alto padrão.
  6. **Circuito Fibra (ISP & Tech):** Interface *Dark Tech* com velocímetro FTTH e recomendador de planos.
* **Apresentação dos 3 Planos (Sem Preço Exposto):** Cards limpos destacando as diferenças entre **Pacote Essencial**, **Pacote Profissional (Mais Escolhido)** e **Completo + Placa NFC**, levando o cliente a consultar o valor no WhatsApp.
* **Funil Inteligente de WhatsApp:** Preenchimento automático do plano/modelo escolhido, máscara brasileira de telefone `(DD) 9XXXX-XXXX` e fallback anti-bloqueio com botão de copiar mensagem.

---

## ⚙️ 4. Configuração Rápida (`SITE_CONFIG`)

Para alterar o número de WhatsApp ou dados da marca, basta editar o objeto `SITE_CONFIG` no início da tag `<script>` dentro do `index.html`:

```javascript
const SITE_CONFIG = {
  brandName: 'DigitalOn',
  authorName: 'Willian Rafael de Oliveira',
  whatsappNumber: '5519978222676' // DDI (55) + DDD + Número
};

📂 5. Estrutura do Repositório

📦 DigitalOn/
 ┣ 📂 assets/
 ┃ ┣ 🖼️ favicon.png                    # Ícone da aba
 ┃ ┣ 🖼️ og-image.webp                  # Logo DigitalOn do Header
 ┃ ┣ 🖼️ foto-perfil.webp               # Imagem da seção Sobre
 ┃ ┗ 🖼️ preview-compartilhamento.png   # Preview 1200x630px para WhatsApp
 ┣ 📄 index.html                       # Aplicação completa autocontida
 ┣ 📄 README.md                        # Documentação técnica e comercial
 ┣ 📄 robots.txt                       # Diretrizes de indexação
 ┗ 📄 sitemap.xml                      # Mapa do site para SEO

 Desenvolvido por Willian Rafael de Oliveira — DigitalOn


---

### 2. Histórico de Commits e Push (Comandos para o Terminal)

Se você quiser registrar um histórico organizado separando a refatoração do site e a atualização da documentação, execute a Opção A no terminal do VS Code (`Ctrl + '`). Se preferir subir tudo em um único pacote detalhado, use a Opção B:

**Opção A: Commits Separados por Arquivo (Mais organizado no GitHub)**

# 1. Verifica o status dos arquivos modificados
git status

# 2. Adiciona e faz o commit das melhorias visuais e comerciais no index.html
git add index.html
git commit -m "refactor(ui): enxuga textos, remove exibicao de precos e restaura simulador de 6 mini-sites" -m "- Substitui precos fixos por chamada de consulta de valor no WhatsApp
- Reduz textos longos e remove secoes redundantes para evitar poluicao visual
- Mantem simulador ao vivo com 6 layouts exclusivos e alternancia Desktop/Mobile"

# 3. Adiciona e faz o commit da nova documentação no README.md
git add README.md
git commit -m "docs(readme): atualiza documentacao para o modelo comercial sob consulta e layout enxuto"

# 4. Envia o histórico de commits para o GitHub (atualizando o GitHub Pages)
git push origin main