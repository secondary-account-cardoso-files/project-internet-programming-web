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

## 📚 Sistema de Biblioteca Digital

Este projeto implementa um sistema completo de gerenciamento de biblioteca digital com funcionalidades de cadastro de usuários, aluguel de livros e administração de clientes.

### 🎯 Funcionalidades Principais

- **Cadastro de Usuários**: Sistema completo com validação de CPF, CEP e dados pessoais
- **Gerenciamento de Clientes**: CRUD completo com exportação para CSV
- **Catálogo de Livros**: Organização por categorias (Fantasia, Tecnologia, Filosofia)
- **Sistema de Aluguel**: Controle de empréstimos com validações e histórico
- **Interface Responsiva**: Design adaptativo para diferentes dispositivos
- **API Integration**: Integração com GitHub API para exibição da equipe

### 🗂️ Estrutura do Projeto

```
📦 project-internet-programming-web
├── 📄 index.html              # Página principal
├── 📁 pages/                  # Páginas do sistema
│   ├── inicio.html            # Dashboard inicial
│   ├── cadastro.html          # Formulário de cadastro
│   ├── table.html             # Listagem de clientes
│   ├── livros.html            # Catálogo e aluguel
│   └── members.html           # Equipe do projeto
├── 📁 script/                 # Scripts JavaScript
│   └── index.js               # Lógica principal
├── 📁 style/                  # Estilos CSS
│   └── index.css              # Estilos principais
└── 📁 docs/                   # Documentação
    ├── inicio.md              # Doc. página inicial
    ├── cadastro.md            # Doc. sistema de cadastro
    ├── table.md               # Doc. listagem de clientes
    ├── livros.md              # Doc. catálogo de livros
    └── members.md             # Doc. página da equipe
```

### 🛠️ Tecnologias Utilizadas

- **HTML5**: Estrutura semântica das páginas
- **CSS3**: Estilização e responsividade
- **JavaScript ES6+**: Lógica de negócio e interatividade
- **LocalStorage**: Persistência de dados local
- **Fetch API**: Requisições HTTP
- **GitHub API**: Integração com dados da equipe

### ⚡ Funcionalidades Avançadas

#### Sistema de Validação

- Validação de CPF com algoritmo oficial
- Máscaras automáticas para CPF, CEP e data
- Validação de idade mínima (18 anos)
- Validação de formato de dados em tempo real

#### Gestão de Aluguéis

- Controle de disponibilidade de livros
- Histórico de empréstimos por cliente
- Sistema de edição e devolução
- Validação de duplicidade de aluguéis

#### Interface Responsiva

- Layout adaptativo (mobile-first)
- Breakpoints para diferentes dispositivos:
  - Mobile: até 480px
  - Tablet: 481px a 768px
  - Desktop: a partir de 1025px

### 📋 Como Executar

1. Clone o repositório
2. Abra o arquivo `index.html` em um servidor local ou navegador
3. Navegue pelas diferentes funcionalidades usando o menu lateral

### 📖 Documentação Detalhada

- [📄 Página Inicial](docs/inicio.md) - Dashboard e visão geral
- [👤 Sistema de Cadastro](docs/cadastro.md) - Formulário de usuários
- [📊 Listagem de Clientes](docs/table.md) - CRUD e exportação
- [📚 Catálogo de Livros](docs/livros.md) - Sistema de aluguel
- [👥 Equipe do Projeto](docs/members.md) - Informações da equipe

### 🎨 Design System

O projeto utiliza um design system consistente com:

- Paleta de cores moderna
- Componentes reutilizáveis
- Animações e transições suaves
- Feedback visual para interações

### 🔄 Fluxo de Dados

1. **Entrada**: Formulários com validação em tempo real
2. **Processamento**: JavaScript para lógica de negócio
3. **Armazenamento**: LocalStorage para persistência
4. **Apresentação**: Interface dinâmica e responsiva

---

**Desenvolvido por:** [João Batista](https://github.com/Cardosofiles), [João Vitor](https://github.com/joaoatelie), [Marcos Lima](https://github.com/marcoslima5789)  
**Orientadora:** [Prof. Luciene Chagas de Oliveira, Ph.D](https://www.linkedin.com/in/luciene-chagas-de-oliveira-ph-d-b21b3b31/)
