# 🌐 Programação para a Internet

<div align="center">

![Programação para a Internet](https://img.shields.io/badge/Programação%20para%20a%20Internet-Unitri-0078D4?style=for-the-badge&logo=azuredevops)
![Disciplina](https://img.shields.io/badge/Disciplina-ADS-4B8BBE?style=for-the-badge&logo=github)
![Professora](https://img.shields.io/badge/Prof-Luciene%20Chagas%20de%20Oliveira-FFCA28?style=for-the-badge&logo=linkedin)

**Instituição:** [Unitri](https://unitri.edu.br)  
**Curso:** Análise e Desenvolvimento de Sistemas  
**Disciplina:** Programação para a Internet  
**Professora:** [Luciene Chagas de Oliveira, Ph.D](https://www.linkedin.com/in/luciene-chagas-de-oliveira-ph-d-b21b3b31/)

Este repositório contém meus estudos, anotações e exercícios realizados durante a disciplina de Programação para a Internet. O objetivo é registrar o progresso ao longo do semestre, facilitando a inclusão de novos conteúdos conforme as aulas avançam.

</div>

---

# 🏠 Página Inicial - Dashboard

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![GitHub API](https://img.shields.io/badge/GitHub-API-181717?style=flat&logo=github&logoColor=white)
![Fetch API](https://img.shields.io/badge/Fetch-API-FF6B6B?style=flat&logo=javascript&logoColor=white)

## 📋 Índice

- [📋 Visão Geral](#-visão-geral)
- [🎯 Funcionalidades](#-funcionalidades)
- [🔧 Implementação Técnica](#-implementação-técnica)
- [🌐 Integração GitHub API](#-integração-github-api)
- [🎨 Design dos Cards](#-design-dos-cards)
- [📊 Estados da Interface](#-estados-da-interface)
- [📱 Responsividade](#-responsividade)
- [🚀 Performance](#-performance)
- [🔄 Fluxo de Execução](#-fluxo-de-execução)

---

## 📋 Visão Geral

A página inicial (`inicio.html`) serve como dashboard principal do sistema, oferecendo uma visão geral da biblioteca digital e apresentando a equipe de desenvolvimento através da integração dinâmica com a GitHub API.

### 🎯 Objetivo Principal

Fornecer uma landing page atrativa que apresente o projeto e demonstre integração com APIs externas, carregando dinamicamente os perfis dos desenvolvedores.

---

## 🎯 Funcionalidades

### ✅ **Dashboard Principal**

- Apresentação do sistema de biblioteca digital
- Interface clean e moderna com navegação intuitiva
- Ponto de entrada para todas as funcionalidades

### ✅ **Integração com GitHub API**

- Carregamento dinâmico dos perfis da equipe
- Exibição automática de avatars e informações
- Links diretos para perfis dos desenvolvedores

### ✅ **Design Responsivo**

- Layout adaptativo para diferentes dispositivos
- Cards organizados em grid responsivo
- Otimização específica para mobile, tablet e desktop

### ✅ **Estados de Carregamento**

- Feedback visual durante requisições API
- Tratamento elegante de erros de conexão
- Fallbacks informativos para problemas de rede

---

## 🔧 Implementação Técnica

### HTML Structure

```html
<div>
  <main>
    <h1>Bem-vindo à Biblioteca Digital</h1>
    <div id="collaborators">
      <!-- Cards renderizados dinamicamente -->
    </div>
  </main>
</div>
```

### JavaScript Core Functions

#### `renderCollaborators()`

```javascript
function renderCollaborators() {
  const container = document.getElementById("collaborators");
  // Exibe estado de carregamento
  // Executa requisições paralelas para GitHub API
  // Renderiza cards dinamicamente
  // Trata erros e estados de falha
}
```

#### `projectCollaboratorsGithub()`

```javascript
function projectCollaboratorsGithub() {
  // Múltiplas requisições paralelas usando Promise.all
  const cardosofiles = fetch("https://api.github.com/users/cardosofiles");
  const joaoatelie = fetch("https://api.github.com/users/joaoatelie");
  const marcosLima = fetch("https://api.github.com/users/marcoslima5789");

  return Promise.all([cardosofiles, joaoatelie, marcosLima]);
}
```

---

## 🌐 Integração GitHub API

### 📡 **Requisições API**

```javascript
// Endpoints utilizados
const endpoints = [
  "https://api.github.com/users/cardosofiles",
  "https://api.github.com/users/joaoatelie",
  "https://api.github.com/users/marcoslima5789",
];
```

### 🔄 **Processamento de Dados**

```javascript
.then((users) => {
  const cards = users.map((user) => {
    const nome = user.name || "(sem nome)";
    const login = user.login || "";
    const avatar = user.avatar_url || "";
    const url = user.html_url || `https://github.com/${login}`;

    return `<article class="collab-card">...</article>`;
  }).join("");
});
```

### 🛡️ **Tratamento de Erros**

- **Network Errors**: Mensagem amigável de erro
- **API Limits**: Graceful degradation
- **Data Missing**: Fallbacks para campos vazios

---

## 🎨 Design dos Cards

### 🎴 **Estrutura Visual**

```html
<article class="collab-card">
  <img src="AVATAR_URL" alt="Nome do desenvolvedor" />
  <h4 title="Nome completo">Nome</h4>
  <p>@username</p>
  <a href="GITHUB_URL" target="_blank">Ver perfil</a>
</article>
```

### 🎨 **Estilização CSS**

```css
.collab-card {
  background: #ffffff;
  border: 1px solid #e5e7eb;
  border-radius: 12px;
  padding: 22px;
  text-align: center;
  box-shadow: 0 3px 12px rgba(0, 0, 0, 0.06);
}

.collab-card img {
  width: 96px;
  height: 96px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid #e5e7eb;
}
```

### ✨ **Micro-interações**

```css
.collab-card a:hover {
  background: #1d4ed8;
  transform: translateY(-1px);
}
```

---

## 📊 Estados da Interface

### 1. **Estado de Carregamento**

```html
<p style="text-align:center;color:#6b7280;">Carregando colaboradores...</p>
```

### 2. **Estado de Sucesso**

```html
<div class="collab-grid">
  <article class="collab-card">
    <!-- Dados carregados da API -->
  </article>
</div>
```

### 3. **Estado de Erro**

```html
<p style="text-align:center;color:#dc2626;">
  Não foi possível carregar os colaboradores agora.
</p>
```

---

## 📱 Responsividade

### 🖥️ **Desktop** (≥1025px)

```css
.collab-grid {
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 20px;
}
```

### 📱 **Tablet** (481px-768px)

```css
.collab-grid {
  grid-template-columns: repeat(2, minmax(0, 1fr));
}
```

### 📱 **Mobile** (≤480px)

```css
.collab-grid {
  grid-template-columns: 1fr;
}
```

### 🎯 **Adaptive Features**

- **Images**: Responsive avatar sizing
- **Typography**: Scalable font sizes
- **Layout**: Flexible grid system
- **Touch**: Optimized tap targets

---

## 🚀 Performance

### ⚡ **Otimizações Implementadas**

- **Parallel Requests**: Promise.all para requisições simultâneas
- **Image Optimization**: Avatars em resolução adequada
- **Caching**: Navegador cache das requisições API
- **Lazy Loading**: Conceitual para futuras implementações

### 📊 **Métricas Esperadas**

- **Load Time**: ~2-3 segundos (dependente da rede)
- **API Response**: ~500-800ms por requisição
- **Render Time**: ~100-200ms pós-carregamento

---

## 🔄 Fluxo de Execução

### 1. **Inicialização**

```javascript
document.addEventListener("DOMContentLoaded", function () {
  loadPage("inicio.html");
});
```

### 2. **Carregamento da Página**

```javascript
loadPage("inicio.html") → renderCollaborators()
```

### 3. **Requisições API**

```javascript
renderCollaborators() → projectCollaboratorsGithub() → fetch() × 3
```

### 4. **Processamento de Dados**

```javascript
Promise.all([...]) → .then(users => processData) → renderCards
```

### 5. **Renderização Final**

```javascript
container.innerHTML = generatedHTML;
```

---

## 🎪 Características Especiais

### 🌟 **User Experience**

- Loading states informativos
- Error handling elegante
- Links externos com `target="_blank"`
- Indicadores visuais claros

### 🔧 **Developer Experience**

- Código modular e reutilizável
- Comments explicativos
- Estrutura escalável
- Debug-friendly

### 🔒 **Segurança**

- Links com `rel="noopener"`
- Sanitização de dados da API
- Fallbacks para dados ausentes

---

## 🎨 Visual Design System

### 🌈 **Color Palette**

- **Background**: `#ffffff` (cards)
- **Borders**: `#e5e7eb` (subtle borders)
- **Text Primary**: `#111827` (headings)
- **Text Secondary**: `#6b7280` (descriptions)
- **Accent**: `#2563eb` (links)

### 📏 **Spacing System**

- **Card Padding**: 22px
- **Grid Gap**: 20px
- **Avatar Size**: 96×96px
- **Border Radius**: 12px (cards), 50% (avatars)

---

## 🔗 Navegação

[![⬅️ Voltar ao README](https://img.shields.io/badge/⬅️-Voltar_ao_README-blue?style=for-the-badge)](../README.md)
[![👤 Cadastro](https://img.shields.io/badge/👤-Sistema_Cadastro-red?style=for-the-badge)](cadastro.md)
[![📊 Clientes](https://img.shields.io/badge/📊-Listagem_Clientes-orange?style=for-the-badge)](table.md)
[![📚 Livros](https://img.shields.io/badge/📚-Catálogo_Livros-purple?style=for-the-badge)](livros.md)
[![👥 Equipe](https://img.shields.io/badge/👥-Equipe-yellow?style=for-the-badge)](members.md)

---

**Arquivo:** Renderizado dinamicamente via `loadPage("inicio.html")`  
**Scripts:** `renderCollaborators()`, `projectCollaboratorsGithub()` em `script/index.js`  
**Estilos:** `.collab-grid`, `.collab-card` em `style/index.css`
