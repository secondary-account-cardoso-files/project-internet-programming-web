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

# 👥 Equipe do Projeto - Apresentação

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![Responsive](https://img.shields.io/badge/Responsive-Design-38B2AC?style=flat&logo=tailwind-css&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Integration-181717?style=flat&logo=github&logoColor=white)

## 📋 Índice

- [📋 Visão Geral](#-visão-geral)
- [👩‍🏫 Professora Orientadora](#-professora-orientadora)
- [👨‍💻 Equipe de Desenvolvimento](#-equipe-de-desenvolvimento)
- [🔧 Estrutura HTML](#-estrutura-html)
- [🎨 Design System](#-design-system)
- [📱 Responsividade](#-responsividade)
- [🌟 Destaques Visuais](#-destaques-visuais)
- [🔗 Integrações](#-integrações)

---

## 📋 Visão Geral

A página de membros (`members.html`) apresenta a equipe completa do projeto de forma elegante e profissional, destacando tanto a professora orientadora quanto os desenvolvedores, com design moderno e totalmente responsivo.

### 🎯 Objetivo Principal

Apresentar de forma visualmente atrativa e informativa todos os membros envolvidos no projeto, criando conexões e destacando competências individuais.

---

## 👩‍🏫 Professora Orientadora

### 🎓 **Prof. Luciene Chagas de Oliveira, Ph.D**

![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)

#### 📋 Informações

- **Cargo**: Professora Orientadora
- **Disciplina**: Programação para Internet
- **Formação**: Ph.D (Doutorado)
- **Instituição**: Unitri - Centro Universitário do Triângulo

#### 🎨 Card Design Especial

```html
<header class="mentor-card">
  <div class="mentor-card__photo">
    <img src="LINKEDIN_PHOTO" alt="Foto da Professora" />
  </div>
  <div class="mentor-card__content">
    <p class="mentor-card__eyebrow">Professora Orientadora</p>
    <h1>Luciene Chagas de Oliveira, Ph.D</h1>
    <p class="mentor-card__description">...</p>
    <a class="button button--light" href="LINKEDIN">LinkedIn</a>
  </div>
</header>
```

#### 🌈 Visual Design

- **Background**: Gradient radial azul-roxo
- **Layout**: Grid 2 colunas (foto + conteúdo)
- **Tipografia**: Hierarchy clara com eyebrow text
- **CTA**: Botão LinkedIn com glass morphism

---

## 👨‍💻 Equipe de Desenvolvimento

### 🚀 **Time de 3 Desenvolvedores**

#### 👤 **João Batista** - Backend Developer

![GitHub](https://img.shields.io/badge/GitHub-Cardosofiles-181717?style=flat&logo=github)
![LinkedIn](https://img.shields.io/badge/LinkedIn-cardosofiles-0077B5?style=flat&logo=linkedin)

**Especializações:**

- Arquitetura de sistemas
- APIs e integração
- Lógica de negócio
- Validações e segurança

#### 🎨 **João Vitor** - UI/UX Designer

![GitHub](https://img.shields.io/badge/GitHub-joaoatelie-181717?style=flat&logo=github)
![LinkedIn](https://img.shields.io/badge/LinkedIn-joaoatelie-0077B5?style=flat&logo=linkedin)

**Especializações:**

- Interface design
- User experience
- Design systems
- Prototipagem

#### 💻 **Marcos Lima** - Full Stack Developer

![GitHub](https://img.shields.io/badge/GitHub-marcoslima5789-181717?style=flat&logo=github)
![LinkedIn](https://img.shields.io/badge/LinkedIn-marcos_codding-0077B5?style=flat&logo=linkedin)

**Especializações:**

- Desenvolvimento completo
- Frontend + Backend
- Integração de sistemas
- DevOps básico

---

## 🔧 Estrutura HTML

### 📐 Layout Principal

```html
<section class="members-page">
  <!-- Card da professora -->
  <header class="mentor-card">
    <!-- Grid com foto e conteúdo -->
  </header>

  <!-- Seção da equipe -->
  <section class="team-section">
    <h2>Equipe de Desenvolvimento</h2>
    <div class="team-grid">
      <!-- Cards dos desenvolvedores -->
    </div>
  </section>
</section>
```

### 🎯 Componentes

#### **Mentor Card** (Professora)

```html
<header class="mentor-card">
  <div class="mentor-card__photo">
    <img src="..." alt="..." />
  </div>
  <div class="mentor-card__content">
    <p class="mentor-card__eyebrow">CATEGORIA</p>
    <h1>NOME COMPLETO</h1>
    <p class="mentor-card__description">DESCRIÇÃO</p>
    <a class="button button--light">LINK</a>
  </div>
</header>
```

#### **Member Card** (Desenvolvedores)

```html
<article class="member-card">
  <img class="member-card__photo" src="..." alt="..." />
  <h3>NOME</h3>
  <p>FUNÇÃO</p>
  <div class="member-card__links">
    <a href="...">LinkedIn</a>
    <a href="...">GitHub</a>
  </div>
</article>
```

---

## 🎨 Design System

### 🌈 **Mentor Card** (Professora)

```css
.mentor-card {
  /* Grid layout 2 colunas */
  display: grid;
  grid-template-columns: minmax(0, 320px) minmax(0, 1fr);
  gap: clamp(1.5rem, 4vw, 3rem);

  /* Background gradient */
  background: radial-gradient(circle at top left, #4f46e5 0%, #312e81 100%);

  /* Spacing e visual */
  padding: clamp(1.5rem, 4vw, 3rem);
  border-radius: 24px;
  color: #fff;
  box-shadow: 0 25px 60px rgba(49, 46, 129, 0.25);
}
```

### 🎴 **Member Cards** (Desenvolvedores)

```css
.member-card {
  /* Layout centralizado */
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;

  /* Background gradiente sutil */
  background: linear-gradient(180deg, #ffffff 0%, #f8fafc 100%);

  /* Visual moderno */
  border-radius: 24px;
  padding: clamp(1.5rem, 3vw, 2rem);
  box-shadow: 0 20px 40px rgba(15, 23, 42, 0.08);
  border: 1px solid rgba(148, 163, 184, 0.18);
}
```

### 🖼️ **Fotos de Perfil**

```css
/* Professora - Quadrada com bordas */
.mentor-card__photo img {
  width: clamp(180px, 24vw, 240px);
  aspect-ratio: 1;
  border-radius: 24px;
  border: 4px solid rgba(255, 255, 255, 0.35);
}

/* Desenvolvedores - Circulares */
.member-card__photo {
  width: 110px;
  aspect-ratio: 1;
  border-radius: 50%;
  border: 3px solid rgba(59, 130, 246, 0.15);
}
```

---

## 📱 Responsividade

### 🖥️ **Desktop** (≥1025px)

```css
.mentor-card {
  grid-template-columns: minmax(0, 320px) minmax(0, 1fr);
  align-items: center;
}

.team-grid {
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: clamp(1.5rem, 3vw, 2.5rem);
}
```

### 📱 **Tablet** (481px-768px)

```css
.mentor-card {
  grid-template-columns: minmax(0, 260px) minmax(0, 1fr);
  align-items: flex-start;
}

.team-grid {
  grid-template-columns: repeat(2, minmax(0, 1fr));
}
```

### 📱 **Mobile** (≤480px)

```css
.mentor-card {
  /* Empilhamento vertical */
  grid-template-columns: 1fr;
  text-align: center;
  gap: 1.5rem;
}

.mentor-card__content {
  align-items: center;
}

.team-grid {
  grid-template-columns: 1fr;
}
```

---

## 🌟 Destaques Visuais

### ✨ **Micro-animações**

```css
/* Hover nos botões */
.button--light:hover {
  transform: translateY(-2px);
  box-shadow: 0 16px 30px rgba(15, 23, 42, 0.28);
}

/* Links dos desenvolvedores */
.member-card__links a:hover {
  background: rgba(29, 78, 216, 0.18);
  transform: translateY(-1px);
}
```

### 🎨 **Typography Hierarchy**

```css
/* Título principal */
.mentor-card h1 {
  font-size: clamp(2rem, 3.2vw, 3rem);
  margin: 0 0 1rem;
}

/* Eyebrow text */
.mentor-card__eyebrow {
  text-transform: uppercase;
  letter-spacing: 0.12em;
  font-size: 0.8rem;
  opacity: 0.8;
}
```

### 🌈 **Color Palette**

- **Primary Blue**: `#4f46e5`
- **Deep Purple**: `#312e81`
- **Light Background**: `#f8fafc`
- **Text Primary**: `#0f172a`
- **Text Secondary**: `#475569`

---

## 🔗 Integrações

### 🌐 **Links Externos**

```html
<!-- LinkedIn da Professora -->
<a
  href="https://www.linkedin.com/in/luciene-chagas-de-oliveira-ph-d-b21b3b31/"
  target="_blank"
  rel="noopener"
>
  <!-- GitHub dos Desenvolvedores -->
  <a href="https://github.com/Cardosofiles" target="_blank" rel="noopener">
    <!-- LinkedIn dos Desenvolvedores -->
    <a
      href="https://www.linkedin.com/in/cardosofiles/"
      target="_blank"
      rel="noopener"
    ></a></a
></a>
```

### 🖼️ **Fontes das Imagens**

- **Professora**: LinkedIn profile photo
- **Desenvolvedores**: GitHub avatars diretos via API

### 🔒 **SEO e Acessibilidade**

```html
<!-- Alt texts descritivos -->
<img alt="Foto da Professora Luciene Chagas de Oliveira" />
<img alt="Foto de João Batista" />

<!-- Links com rel noopener para segurança -->
<a target="_blank" rel="noopener">
  <!-- Estrutura semântica -->
  <header>
    ,
    <section>
      ,
      <article></article>
    </section></header
></a>
```

---

## 🎯 Características Especiais

### 💫 **Glass Morphism**

- Efeito vidro no botão da professora
- Background semi-transparente
- Blur effects sutis

### 🎨 **Design Tokens**

- Espaçamentos com `clamp()`
- Typography responsiva
- Color system consistente

### ⚡ **Performance**

- CSS otimizado
- Imagens em tamanhos adequados
- Transitions performáticas

---

## 🔗 Navegação

[![⬅️ Voltar ao README](https://img.shields.io/badge/⬅️-Voltar_ao_README-blue?style=for-the-badge)](../README.md)
[![📄 Início](https://img.shields.io/badge/📄-Página_Inicial-green?style=for-the-badge)](inicio.md)
[![👤 Cadastro](https://img.shields.io/badge/👤-Sistema_Cadastro-red?style=for-the-badge)](cadastro.md)
[![📊 Clientes](https://img.shields.io/badge/📊-Listagem_Clientes-orange?style=for-the-badge)](table.md)
[![📚 Livros](https://img.shields.io/badge/📚-Catálogo_Livros-purple?style=for-the-badge)](livros.md)

---

**Arquivo:** `pages/members.html` (estático)  
**Estilos:** `.members-page`, `.mentor-card`, `.member-card` em `style/index.css`  
**Integrações:** Links diretos para LinkedIn e GitHub dos membros
