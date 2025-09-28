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

# 👤 Sistema de Cadastro - Página de Registro

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![LocalStorage](https://img.shields.io/badge/LocalStorage-4285F4?style=flat&logo=google-chrome&logoColor=white)

## 📋 Índice

- [📋 Visão Geral](#-visão-geral)
- [🎯 Funcionalidades](#-funcionalidades)
- [🔧 Implementação Técnica](#-implementação-técnica)
- [📝 Estrutura do Formulário](#-estrutura-do-formulário)
- [🎨 Design e UX](#-design-e-ux)
- [⚡ Validações](#-validações)
- [🔄 Estados do Sistema](#-estados-do-sistema)
- [📱 Responsividade](#-responsividade)
- [🚀 Fluxo de Execução](#-fluxo-de-execução)

---

## 📋 Visão Geral

A página de cadastro (`cadastro.html`) é o coração do sistema de registro de usuários da biblioteca digital. Implementa um formulário completo com validações avançadas, máscaras automáticas e design responsivo moderno.

### 🎯 Objetivo Principal

Permitir o cadastro seguro e validado de clientes para acesso à biblioteca digital, garantindo integridade dos dados e experiência de usuário otimizada.

---

## 🎯 Funcionalidades

### ✅ Cadastro Completo

- **Dados Pessoais**: Nome completo com validação
- **Documento**: CPF com algoritmo de validação oficial
- **Endereço Completo**: CEP, rua, número, complemento, cidade e UF
- **Data de Nascimento**: Com validação de idade mínima (18 anos)

### ✅ Validações Avançadas

- **CPF**: Algoritmo oficial brasileiro de validação
- **CEP**: Formato e quantidade de dígitos
- **Data**: Formato brasileiro (dd/mm/yyyy) e idade mínima
- **Campos Obrigatórios**: Validação em tempo real

### ✅ Máscaras Automáticas

```javascript
// CPF: 000.000.000-00
// CEP: 00000-000
// Data: dd/mm/yyyy
```

### ✅ Modo Edição

- Preenchimento automático para edição
- Botão dinâmico (Cadastrar/Atualizar)
- Persistência de dados durante edição

---

## 🔧 Implementação Técnica

### HTML Structure

```html
<section class="register-page">
  <header class="register-page__header">
    <!-- Título e descrição -->
  </header>
  <form id="cadastroForm" class="register-form">
    <div class="register-form__grid">
      <!-- Campos do formulário em grid responsivo -->
    </div>
  </form>
</section>
```

### JavaScript Functions

#### `setupCadastroForm()`

```javascript
function setupCadastroForm() {
  // Configuração inicial do formulário
  // Aplicação de máscaras
  // Event listeners para validação
  // Tratamento de modo edição
}
```

#### Sistema de Máscaras

```javascript
const aplicarMascara = (valor, tipo) => {
  // Remove caracteres não numéricos
  // Aplica formatação específica por tipo
  // Retorna valor formatado
};
```

#### Validações

```javascript
const validarCPF = (cpf) => {
  // Algoritmo oficial de validação CPF
  // Verifica dígitos verificadores
  // Rejeita sequências repetidas
};
```

---

## 📝 Estrutura do Formulário

### Grid Responsivo (12 colunas)

```html
<div class="register-form__grid">
  <!-- Nome: span 12 (linha completa) -->
  <div class="form-field form-field--span-12">
    <!-- CPF e CEP: span 6 cada (metade da linha) -->
    <div class="form-field form-field--span-6">
      <!-- Rua: span 9, Número: span 3 -->
      <div class="form-field form-field--span-9">
        <div class="form-field form-field--span-3"></div>
      </div>
    </div>
  </div>
</div>
```

### Campos Implementados

| Campo       | Tipo | Validação         | Máscara        | Obrigatório |
| ----------- | ---- | ----------------- | -------------- | ----------- |
| Nome        | text | min 3 chars       | -              | ✅          |
| CPF         | text | algoritmo oficial | 000.000.000-00 | ✅          |
| CEP         | text | 8 dígitos         | 00000-000      | ✅          |
| Rua         | text | não vazio         | -              | ✅          |
| Número      | text | não vazio         | -              | ✅          |
| Complemento | text | -                 | -              | ❌          |
| Cidade      | text | não vazio         | -              | ✅          |
| Estado      | text | 2 letras          | -              | ✅          |
| Data Nasc.  | text | idade ≥ 18        | dd/mm/yyyy     | ✅          |

---

## 🎨 Design e UX

### Visual Design

- **Background**: Gradient radial moderno
- **Form Container**: Glass morphism effect
- **Cards**: Border radius 28px
- **Colors**: Paleta azul corporativa

### Micro-interações

```css
.register-form button:hover {
  transform: translateY(-2px);
  box-shadow: 0 22px 40px rgba(37, 99, 235, 0.45);
}
```

### Estados Visuais

- **Focus**: Border azul + shadow
- **Error**: Texto vermelho + indicador
- **Success**: Feedback positivo

---

## ⚡ Validações

### 1. **Validação CPF**

```javascript
const validarCPF = (cpf) => {
  // Remove formatação
  cpf = cpf.replace(/\D/g, "");

  // Verifica comprimento e sequências
  if (cpf.length !== 11 || /^(\d)\1+$/.test(cpf)) return false;

  // Calcula primeiro dígito verificador
  let soma = 0;
  for (let i = 0; i < 9; i++) {
    soma += parseInt(cpf.charAt(i)) * (10 - i);
  }
  // ... lógica completa
};
```

### 2. **Validação Data**

```javascript
const validarData = (data) => {
  // Verifica formato dd/mm/yyyy
  // Valida se data é válida
  // Calcula idade mínima 18 anos
  // Considera ano bissexto
};
```

### 3. **Validação Tempo Real**

```javascript
input.addEventListener("input", () => {
  // Aplica máscara durante digitação
  // Valida campo instantaneamente
  // Mostra/esconde mensagens de erro
});
```

---

## 🔄 Estados do Sistema

### 1. **Modo Cadastro** (Padrão)

```html
<button type="submit">Salvar cadastro</button>
```

### 2. **Modo Edição**

```javascript
// Preenche campos automaticamente
form.nome.value = cliente.nome;
// Altera texto do botão
submitBtn.textContent = "Atualizar";
```

### 3. **Estados de Validação**

```html
<!-- Sucesso -->
<div class="error"></div>

<!-- Erro -->
<div class="error">CPF inválido</div>
```

---

## 📱 Responsividade

### Breakpoints

```css
/* Mobile (≤ 480px) */
.register-form__grid {
  grid-template-columns: 1fr;
}

/* Tablet (481px - 768px) */
.register-form__grid {
  grid-template-columns: repeat(8, minmax(0, 1fr));
}

/* Desktop (≥ 1025px) */
.register-form__grid {
  grid-template-columns: repeat(12, minmax(0, 1fr));
}
```

### Adaptações Mobile

- Grid de 1 coluna
- Padding reduzido
- Botões full-width
- Font-size otimizado

---

## 🚀 Fluxo de Execução

### 1. **Carregamento da Página**

```javascript
loadPage('cadastro.html') → setupCadastroForm()
```

### 2. **Aplicação de Máscaras**

```javascript
input.addEventListener("input", () => {
  input.value = aplicarMascara(input.value, "cpf");
});
```

### 3. **Validação no Submit**

```javascript
form.addEventListener("submit", (e) => {
  e.preventDefault();
  // Limpa erros anteriores
  // Coleta todos os dados
  // Executa validações
  // Salva no LocalStorage
});
```

### 4. **Persistência de Dados**

```javascript
localStorage.setItem("clientes", JSON.stringify(clientes));
```

---

## 🔗 Navegação

[![⬅️ Voltar ao README](https://img.shields.io/badge/⬅️-Voltar_ao_README-blue?style=for-the-badge)](../README.md)
[![📄 Início](https://img.shields.io/badge/📄-Página_Inicial-green?style=for-the-badge)](inicio.md)
[![📊 Clientes](https://img.shields.io/badge/📊-Listagem_Clientes-orange?style=for-the-badge)](table.md)
[![📚 Livros](https://img.shields.io/badge/📚-Catálogo_Livros-purple?style=for-the-badge)](livros.md)
[![👥 Equipe](https://img.shields.io/badge/👥-Equipe-yellow?style=for-the-badge)](members.md)

---

**Arquivo:** `pages/cadastro.html`  
**Scripts:** `setupCadastroForm()`, `aplicarMascara()`, `validarCPF()` em `script/index.js`  
**Estilos:** `.register-page`, `.register-form` em `style/index.css`
