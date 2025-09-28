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

# 📊 Listagem de Clientes - Sistema CRUD

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![LocalStorage](https://img.shields.io/badge/LocalStorage-4285F4?style=flat&logo=google-chrome&logoColor=white)
![CSV Export](https://img.shields.io/badge/CSV-Export-28a745?style=flat&logo=microsoft-excel&logoColor=white)

## 📋 Índice

- [📋 Visão Geral](#-visão-geral)
- [🎯 Funcionalidades](#-funcionalidades)
- [🔧 Implementação Técnica](#-implementação-técnica)
- [📊 Estrutura da Tabela](#-estrutura-da-tabela)
- [⚙️ Operações CRUD](#️-operações-crud)
- [📥 Sistema de Exportação](#-sistema-de-exportação)
- [🔄 Gerenciamento de Estados](#-gerenciamento-de-estados)
- [📱 Responsividade](#-responsividade)
- [🚀 Fluxo de Dados](#-fluxo-de-dados)

---

## 📋 Visão Geral

A página de listagem (`table.html`) é o centro de controle do sistema, oferecendo uma interface completa para gerenciar todos os clientes cadastrados. Implementa operações CRUD, exportação de dados e controle de estados avançado.

### 🎯 Objetivo Principal

Fornecer uma interface administrativa completa para visualizar, editar, excluir e exportar dados dos clientes cadastrados no sistema.

---

## 🎯 Funcionalidades

### ✅ Visualização de Dados

- **Tabela Completa**: Todos os campos dos clientes
- **Livros Alugados**: Integração com sistema de aluguéis
- **Status do Cliente**: Indicador visual de seleção
- **Contador**: Total de clientes cadastrados

### ✅ Operações CRUD

- **Create**: Botão para novo cadastro
- **Read**: Visualização tabular organizada
- **Update**: Edição inline de registros
- **Delete**: Exclusão com confirmação

### ✅ Exportação de Dados

- **Formato CSV**: Compatível com Excel/Sheets
- **Dados Completos**: Todos os campos exportados
- **Download Automático**: Geração client-side

### ✅ Sistema de Estados

- **Cliente Selecionado**: Para operações de aluguel
- **Aluguel Pendente**: Fluxo de seleção de livros
- **Modo Edição**: Transição para formulário

---

## 🔧 Implementação Técnica

### HTML Dinâmico

```html
<div id="table-container">
  <!-- Conteúdo renderizado dinamicamente -->
  <!-- via renderTablePage() -->
</div>
```

### JavaScript Functions

#### `renderTablePage()`

```javascript
function renderTablePage() {
  // Carrega dados do localStorage
  // Processa informações de aluguel
  // Renderiza interface responsiva
  // Configura estados do sistema
}
```

#### Sistema de Estados

```javascript
const clienteSelecionado = localStorage.getItem("clienteSelecionado");
const pendingRentalBook = localStorage.getItem("pendingRentalBookTitle");
const livrosAlugados = JSON.parse(
  localStorage.getItem("livrosAlugados") || "[]"
);
```

#### Exportação CSV

```javascript
window.exportarCSV = function () {
  // Gera conteúdo CSV
  // Cria blob para download
  // Inicia download automático
};
```

---

## 📊 Estrutura da Tabela

### Layout Responsivo

```html
<div style="overflow-x: auto;">
  <table class="users-table">
    <thead>
      <!-- Cabeçalhos das colunas -->
    </thead>
    <tbody>
      <!-- Dados dos clientes -->
    </tbody>
  </table>
</div>
```

### Colunas da Tabela

| Coluna              | Tipo    | Descrição           | Responsivo |
| ------------------- | ------- | ------------------- | ---------- |
| Nome                | String  | Nome completo       | ✅         |
| CPF                 | String  | Documento formatado | ✅         |
| CEP                 | String  | Código postal       | ✅         |
| Rua                 | String  | Logradouro          | 📱 Hidden  |
| Nº                  | String  | Número residencial  | 📱 Hidden  |
| Complemento         | String  | Info adicional      | 📱 Hidden  |
| Cidade              | String  | Localidade          | ✅         |
| UF                  | String  | Estado              | ✅         |
| Data Nasc.          | String  | Nascimento          | 📱 Abrev.  |
| **Livros Alugados** | Array   | Lista de títulos    | ✅         |
| **Status**          | String  | Estado de seleção   | ✅         |
| Ações               | Buttons | CRUD operations     | ✅         |

---

## ⚙️ Operações CRUD

### 1. **Create** - Novo Cadastro

```html
<button onclick="loadPage('cadastro.html')" style="background: #28a745;">
  Novo Cadastro
</button>
```

### 2. **Read** - Visualização

```javascript
clients.forEach((client, index) => {
  // Renderiza linha da tabela
  // Inclui dados de aluguel
  // Aplica formatação visual
});
```

### 3. **Update** - Edição

```javascript
window.editClient = function (index) {
  localStorage.setItem("editingClientIndex", index);
  loadPage("cadastro.html");
};
```

### 4. **Delete** - Exclusão

```javascript
window.deleteClient = function (index) {
  if (!confirm("Deseja realmente excluir este cliente?")) return;

  // Remove cliente
  clientes.splice(index, 1);

  // Remove aluguéis associados
  const atualizados = livrosAlugados.filter(
    (aluguel) => aluguel.cpf !== clienteRemovido.cpf
  );

  // Atualiza localStorage
  localStorage.setItem("clientes", JSON.stringify(clientes));
  localStorage.setItem("livrosAlugados", JSON.stringify(atualizados));
};
```

---

## 📥 Sistema de Exportação

### Geração CSV

```javascript
const csvContent = [
  // Cabeçalho
  [
    "Nome",
    "CPF",
    "CEP",
    "Rua",
    "Número",
    "Complemento",
    "Cidade",
    "UF",
    "Data Nascimento",
  ].join(","),

  // Dados dos clientes
  ...clientes.map((c) =>
    [
      c.nome,
      c.cpf,
      c.cep,
      c.rua,
      c.numero,
      c.complemento || "",
      c.cidade,
      c.estado,
      c.dataNascimento,
    ].join(",")
  ),
].join("\n");
```

### Download Client-Side

```javascript
const blob = new Blob([csvContent], { type: "text/csv" });
const url = window.URL.createObjectURL(blob);
const a = document.createElement("a");
a.href = url;
a.download = "clientes.csv";
a.click();
window.URL.revokeObjectURL(url);
```

---

## 🔄 Gerenciamento de Estados

### 1. **Estado Padrão**

```html
<button class="action-btn rent-btn" onclick="alugarLivro(index)">
  Alugar Livro
</button>
```

### 2. **Aluguel Pendente**

```html
<!-- Indicador visual -->
<div style="background: #eef2ff; border: 1px solid #c7d2fe;">
  <h3>📚 Aluguel em Andamento</h3>
  <p>Selecione um cliente para alugar: <strong>Título do Livro</strong></p>
</div>

<!-- Botão especializado -->
<button
  class="action-btn rent-btn"
  onclick="selecionarClienteParaAluguel(index)"
>
  ✓ Selecionar
</button>
```

### 3. **Cliente Selecionado**

```javascript
const statusLabel =
  clienteSelecionado !== null && Number(clienteSelecionado) === index
    ? "Selecionado"
    : "—";
```

---

## 📱 Responsividade

### Desktop Layout

```css
.users-table {
  width: 100%;
  border-collapse: collapse;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
}
```

### Mobile Adaptations

```css
@media (max-width: 480px) {
  .users-table {
    font-size: 0.85rem;
  }

  .users-table th,
  .users-table td {
    padding: 10px 8px;
  }
}
```

### Scroll Horizontal

```html
<div style="overflow-x: auto;">
  <table class="users-table">
    <!-- Conteúdo da tabela -->
  </table>
</div>
```

---

## 🚀 Fluxo de Dados

### 1. **Carregamento Inicial**

```javascript
loadPage('table.html') → renderTablePage()
```

### 2. **Processamento de Dados**

```javascript
// Carrega clientes do localStorage
const clients = JSON.parse(localStorage.getItem("clientes") || "[]");

// Processa informações de aluguel
const livrosAlugados = JSON.parse(
  localStorage.getItem("livrosAlugados") || "[]"
);
const rentalsByCpf = livrosAlugados.reduce((map, aluguel) => {
  if (!map[aluguel.cpf]) map[aluguel.cpf] = [];
  map[aluguel.cpf].push(aluguel.livro);
  return map;
}, {});
```

### 3. **Renderização da Interface**

```javascript
// Estados vazios
if (clients.length === 0) {
  section.innerHTML = `<div>Nenhum cliente cadastrado</div>`;
  return;
}

// Construção da tabela
let tableHTML = `<table class="users-table">...`;
clients.forEach((client, index) => {
  // Renderiza cada linha
});
```

### 4. **Integração com Outros Módulos**

```javascript
// Navegação para cadastro
onclick = "loadPage('cadastro.html')";

// Integração com sistema de livros
onclick = "alugarLivro(index)";

// Exportação de dados
onclick = "exportarCSV()";
```

---

## 🎨 Interface e UX

### Visual Indicators

```html
<!-- Status do cliente -->
<td>
  <span style="color: ${statusLabel === 'Selecionado' ? '#28a745' : '#6c757d'}">
    ${statusLabel}
  </span>
</td>
```

### Action Buttons

```css
.action-btn {
  padding: 6px 12px;
  border-radius: 4px;
  font-size: 0.95rem;
  cursor: pointer;
  transition: background 0.2s;
}

.edit-btn {
  background: #fbbf24;
}
.delete-btn {
  background: #ef4444;
}
.rent-btn {
  background: #2563eb;
}
```

### Feedback Visual

- **Loading States**: Indicadores de carregamento
- **Empty States**: Mensagens quando não há dados
- **Success States**: Confirmações de ações
- **Error States**: Tratamento de erros

---

## 🔗 Navegação

[![⬅️ Voltar ao README](https://img.shields.io/badge/⬅️-Voltar_ao_README-blue?style=for-the-badge)](../README.md)
[![📄 Início](https://img.shields.io/badge/📄-Página_Inicial-green?style=for-the-badge)](inicio.md)
[![👤 Cadastro](https://img.shields.io/badge/👤-Sistema_Cadastro-red?style=for-the-badge)](cadastro.md)
[![📚 Livros](https://img.shields.io/badge/📚-Catálogo_Livros-purple?style=for-the-badge)](livros.md)
[![👥 Equipe](https://img.shields.io/badge/👥-Equipe-yellow?style=for-the-badge)](members.md)

---

**Arquivo:** `pages/table.html`  
**Scripts:** `renderTablePage()`, `editClient()`, `deleteClient()`, `exportarCSV()` em `script/index.js`  
**Estilos:** `.users-table`, `.action-btn` em `style/index.css`
