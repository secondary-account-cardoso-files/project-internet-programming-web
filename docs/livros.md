# 🌐 Programação para a Internet

<div align="center">

![Programação para a Internet](https://img.shields.io/badge/Programação%20para%20a%20Internet-Unitri-0078D4?style=for-the-badge&logo=azuredevops)
![Disciplina](https://img.shields.io/badge/Disciplina-ADS-4B8BBE?style=for-the-badge&logo=github)
![Professora](https://img.shields.io/badge/Prof-Luciene%20Chagas%20de%20Oliveira-FFCA28?style=for-the-badge&logo=linkedin)

_Instituição:_ [Unitri](https://unitri.edu.br)  
_Curso:_ Análise e Desenvolvimento de Sistemas  
_Disciplina:_ Programação para a Internet  
_Professora:_ [Luciene Chagas de Oliveira, Ph.D](https://www.linkedin.com/in/luciene-chagas-de-oliveira-ph-d-b21b3b31/)

Este repositório contém meus estudos, anotações e exercícios realizados durante a disciplina de Programação para a Internet. O objetivo é registrar o progresso ao longo do semestre, facilitando a inclusão de novos conteúdos conforme as aulas avançam.

</div>

---

# 📚 Catálogo de Livros - Sistema de Aluguel

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![LocalStorage](https://img.shields.io/badge/LocalStorage-4285F4?style=flat&logo=google-chrome&logoColor=white)
![Responsive](https://img.shields.io/badge/Responsive-Design-38B2AC?style=flat&logo=tailwind-css&logoColor=white)

## 📋 Índice

- [📋 Visão Geral](#-visão-geral)
- [📚 Catálogo de Livros](#-catálogo-de-livros)
- [🎯 Sistema de Aluguel](#-sistema-de-aluguel)
- [🔧 Implementação Técnica](#-implementação-técnica)
- [📊 Gestão de Estados](#-gestão-de-estados)
- [🎨 Interface e Cards](#-interface-e-cards)
- [📱 Responsividade](#-responsividade)
- [🔄 Fluxos do Sistema](#-fluxos-do-sistema)
- [📈 Relatórios](#-relatórios)

---

## 📋 Visão Geral

A página de livros (livros.html) é o centro do sistema de aluguel da biblioteca digital, oferecendo um catálogo organizado por categorias, sistema completo de empréstimos e gestão de disponibilidade em tempo real.

### 🎯 Objetivo Principal

Fornecer uma interface intuitiva para navegação no acervo, processo de aluguel simplificado e controle completo do ciclo de vida dos empréstimos.

---

## 📚 Catálogo de Livros

### 📖 Acervo Disponível

- _Total_: 36 livros únicos
- _Categorias_: 3 segmentos distintos
- _Por Categoria_: 12 títulos cada

### 🗂 Categorias Organizadas

#### 🧙‍♂ _Fantasia_ (12 livros)

- Saga Harry Potter completa (7 volumes)
- O Hobbit - J.R.R. Tolkien
- Crônicas de Nárnia - C.S. Lewis
- A Guerra dos Tronos - G.R.R. Martin
- Mistborn: O Império Final - B. Sanderson
- O Nome do Vento - P. Rothfuss

#### 💻 _Tecnologia_ (12 livros)

- Entendendo Algoritmos - A. Bhargava
- Código Limpo - R. Martin
- O Programador Pragmático - D. Thomas
- Clean Architecture - R.C. Martin
- Design Patterns - E. Gamma
- Refactoring - M. Fowler
- JavaScript e Python especializados
- Introduction to Algorithms - T. Cormen

#### 🤔 _Filosofia_ (12 livros)

- A República - Platão
- O Mito da Caverna - Platão
- Sapiens - Y.N. Harari
- Meditações - Marco Aurélio
- Além do Bem e do Mal - Nietzsche
- A Arte da Guerra - Sun Tzu
- Ética - Spinoza
- Crítica da Razão Pura - Kant
- Obras clássicas do pensamento

---

## 🎯 Sistema de Aluguel

### ✅ Funcionalidades Principais

#### 🔄 _Fluxo Completo_

1. _Seleção de Livro_: Click em "Selecionar Cliente"
2. _Escolha do Cliente_: Navegação para lista de clientes
3. _Confirmação_: Validações e efetivação
4. _Controle_: Livro fica indisponível
5. _Devolução_: Sistema de retorno

#### 🛡 _Validações Avançadas_

javascript
// Verificar disponibilidade
const livroJaAlugado = livrosAlugados.some(
(aluguel) => aluguel.livroId === livro.id
);

// Verificar duplicidade por cliente
const jaAlugado = livrosAlugados.some(
(aluguel) => aluguel.livroId === livroId && aluguel.cpf === usuario.cpf
);

#### 📊 _Estados do Livro_

- ✅ _Disponível_: Botão "Alugar"/"Selecionar Cliente"
- ❌ _Alugado_: Badge "Livro Alugado" + visual desabilitado
- ✏ _Editando_: Botão "Substituir Livro"

---

## 🔧 Implementação Técnica

### HTML Structure

html

<div>
  <main>
    <h2>Aluguel de Livros</h2>
    <nav class="book-categories">
      <!-- Links de navegação por categoria -->
    </nav>
    <div id="livros-container">
      <!-- Renderização dinâmica via JavaScript -->
    </div>
  </main>
</div>

### JavaScript Core Functions

#### renderLivrosPage()

javascript
function renderLivrosPage() {
// Carrega dados de clientes e aluguéis
// Processa estados do sistema
// Renderiza interface por categoria
// Aplica validações de disponibilidade
// Configura interações dos cards
}

#### Sistema de Dados

javascript
const livrosPorCategoria = {
fantasia: [
{
id: 1,
titulo: "Harry Potter e a Pedra Filosofal",
autor: "J.K. Rowling",
img: "URL_DA_IMAGEM",
},
// ... mais livros
],
tecnologia: [
/* ... */
],
filosofia: [
/* ... */
],
};

#### Controle de Aluguel

javascript
window.alugarLivroEspecifico = function (livroId, titulo, autor, categoria) {
// Verifica cliente selecionado
// Valida disponibilidade
// Registra aluguel no localStorage
// Atualiza interface em tempo real
};

---

## 📊 Gestão de Estados

### 1. _Estado Inicial_ - Sem Cliente

html

<div style="background: #fff4e5; color: #92400e;">
  Clique em "Selecionar Cliente" em qualquer livro para escolher um cliente.
</div>

### 2. _Cliente Selecionado_

html

<div style="background: #e8f4fd;">
  <strong>Cliente selecionado:</strong> João Silva (000.000.000-00)
</div>

### 3. _Modo Edição de Aluguel_

html

<div style="background: #ede9fe; color: #5b21b6;">
  Editando aluguel: <strong>Harry Potter</strong>. Escolha um novo livro para
  substituir.
</div>

### 4. _Aluguel Pendente_ (Cliente em seleção)

javascript
const pendingRentalBook = localStorage.getItem("pendingRentalBookTitle");
// Interface adaptada para mostrar livro em processo

---

## 🎨 Interface e Cards

### 📱 Card Design

html

<div
  style="height: 370px; display: flex; flex-direction: column; 
            justify-content: space-between;"
>
  <!-- Imagem do livro -->
  <div style="width: 140px; height: 200px;">
    <img src="URL" style="object-fit: cover;" />
  </div>

  <!-- Informações -->
  <p style="font-weight: bold; -webkit-line-clamp: 2;">Título</p>
  <p style="color: #666;">Autor</p>

  <!-- Ação -->

<button onclick="funcaoAluguel()">${textoDoBot}</button>

</div>

### 🎨 Estados Visuais

#### ✅ _Livro Disponível_

css
/_ Hover effect _/
onmouseover="this.style.transform='scale(1.03)'"
/_ Botão ativo _/
background-color: #5a2d82;

#### ❌ _Livro Alugado_

css
/_ Card desabilitado _/
opacity: 0.6;
/_ Badge de status _/
background-color: #dc3545;
color: white;

### 🎨 Grid Responsivo

css
display: grid;
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
gap: 20px;

---

## 📱 Responsividade

### 🖥 _Desktop_ (≥1025px)

- Grid de 5-6 colunas
- Cards com hover effects
- Navegação lateral completa

### 📱 _Tablet_ (481px-768px)

- Grid de 3-4 colunas
- Interface condensada
- Navegação adaptada

### 📱 _Mobile_ (≤480px)

- Grid de 1-2 colunas
- Cards empilhados
- Navegação horizontal
- Fontes otimizadas

---

## 🔄 Fluxos do Sistema

### 1. _Aluguel Direto_ (Cliente já selecionado)

Usuário clica "Alugar" → Validações → Registro → Atualização UI

### 2. _Seleção de Cliente_ (Novo fluxo)

"Selecionar Cliente" → Salva livro pendente → Lista clientes
→ Seleciona cliente → Confirma aluguel → Volta aos livros

### 3. _Edição de Aluguel_

Lista aluguéis → "Editar" → Seleciona cliente → Modo edição
→ Escolhe novo livro → Substitui → Atualiza registro

### 4. _Devolução de Livro_

Lista aluguéis → "Devolver" → Confirmação → Remove registro
→ Libera livro → Atualiza disponibilidade

---

## 📈 Relatórios

### 📊 _Tabela de Aluguéis Ativos_

html

<table class="users-table">
  <thead>
    <tr>
      <th>Cliente</th>
      <th>CPF</th>
      <th>Livro</th>
      <th>Autor</th>
      <th>Categoria</th>
      <th>Data do Aluguel</th>
      <th>Ações</th>
    </tr>
  </thead>
  <tbody>
    <!-- Dados dos aluguéis -->
  </tbody>
</table>

### 📈 _Métricas do Sistema_

- _Livros Alugados_: Contador em tempo real
- _Disponibilidade_: Status por categoria
- _Histórico_: Data e hora dos aluguéis
- _Cliente Ativo_: Quem tem mais livros

### 🔧 _Funções de Gestão_

javascript
// Editar aluguel
window.editarAluguel = function (index) {
// Localiza cliente do aluguel
// Ativa modo edição
// Permite substituição
};

// Devolver livro
window.devolverLivro = function (index) {
// Confirmação do usuário
// Remove do localStorage
// Atualiza interface
// Libera disponibilidade
};

---

## 🚀 Performance e Otimização

### ⚡ _Carregamento Dinâmico_

- Renderização apenas quando necessário
- Cache de dados no localStorage
- Imagens otimizadas via CDN

### 🔄 _Gestão de Estado_

- Estado global via localStorage
- Sincronização entre páginas
- Cleanup automático de índices

### 📱 _Mobile Performance_

- CSS otimizado para touch
- Imagens responsivas
- Lazy loading conceitual

---

## 🔗 Navegação

[![⬅ Voltar ao README](https://img.shields.io/badge/⬅-Voltar_ao_README-blue?style=for-the-badge)](../README.md)
[![📄 Início](https://img.shields.io/badge/📄-Página_Inicial-green?style=for-the-badge)](inicio.md)
[![👤 Cadastro](https://img.shields.io/badge/👤-Sistema_Cadastro-red?style=for-the-badge)](cadastro.md)
[![📊 Clientes](https://img.shields.io/badge/📊-Listagem_Clientes-orange?style=for-the-badge)](table.md)
[![👥 Equipe](https://img.shields.io/badge/👥-Equipe-yellow?style=for-the-badge)](members.md)

---

_Arquivo:_ pages/livros.html  
_Scripts:_ renderLivrosPage(), alugarLivroEspecifico(), solicitarSelecaoCliente() em script/index.js  
_Estilos:_ Cards dinâmicos e .users-table em style/index.css
