# Agroconnect: Conectando o Campo ao Futuro

**Visão Geral:**

Agroconnect é uma plataforma web projetada para conectar agricultores e fortalecer comunidades rurais, facilitando o compartilhamento e a gestão de recursos agrícolas. A aplicação permite que usuários cadastrem, visualizem, reservem e gerenciem diversos tipos de recursos, desde sementes e ferramentas até mão de obra e consultoria. O sistema visa impulsionar o desenvolvimento rural sustentável, criando uma rede de colaboração e crescimento para o agricultor familiar.

**Propósito do Projeto (Foco em Aprendizado):**

Este trabalho foi desenvolvido primariamente para fins de estudo e como um projeto prático para aprendizado e aplicação de novas tecnologias e técnicas no desenvolvimento front-end. O foco principal foi a exploração e integração de:

* **Firebase:** Utilização de Firebase Authentication para gerenciamento de usuários e Firestore como banco de dados NoSQL em tempo real para a gestão de recursos.
* **Tailwind CSS:** Aplicação do framework CSS utilitário para a criação de uma interface de usuário moderna e responsiva.
* **Novas Bibliotecas e Padrões:** Experimentação com bibliotecas JavaScript modernas (como Font Awesome para ícones) e padrões de desenvolvimento web, incluindo manipulação de DOM, eventos, e consumo de APIs (Firebase SDK).

O desenvolvimento foi embasado em pesquisas, estudos de caso e inspiração em designs de plataformas similares, buscando aplicar conceitos de UI/UX para uma experiência de usuário intuitiva.

## Principais Funcionalidades

* **Landing Page Informativa:** Apresenta a proposta de valor da Agroconnect, seus benefícios e como funciona.
* **Cadastro de Usuários:** Permite que novos usuários criem contas para acessar a plataforma.
* **Login de Usuários:** Autentica usuários existentes para acesso à área de gestão de recursos.
* **Gestão de Recursos Agrícolas (`agroconnect_resource_management_v1.html`):**
    * **Visualização de Recursos:** Exibe os recursos disponíveis em formato de cards, com detalhes como nome, categoria, descrição, quantidade, localização, informações de contato e imagem.
    * **Adição de Novos Recursos:** Usuários autenticados podem cadastrar novos recursos, especificando suas características.
    * **Reserva de Recursos:** Usuários podem reservar unidades de um recurso disponível.
    * **Exclusão de Recursos:** Usuários podem excluir os recursos que eles mesmos adicionaram.
    * **Autenticação Firebase:** Integração com Firebase para autenticação de usuários (anônima e potencialmente com provedores) e persistência de dados no Firestore.
    * **Interface Responsiva:** Utiliza Tailwind CSS para uma experiência de usuário adaptável a diferentes tamanhos de tela.
    * **Notificações e Feedback:** Exibe mensagens de sucesso, erro e carregamento para orientar o usuário.

---

## Detalhamento das Páginas

### 1. `index.html` - Landing Page

Esta é a página inicial da plataforma Agroconnect.

* **Objetivo:** Apresentar a Agroconnect, explicar seus objetivos, como funciona e seus benefícios.
* **Seções Principais:**
    * **Cabeçalho:** Navegação com links para seções da página ("Como Funciona", "Benefícios", "Contato"), um link para a página de "Ver Recursos" (`agroconnect_resource_management_v1.html`) e um botão de "Login" (`login.html`).
    * **Seção Hero:** Chamada principal destacando o propósito da plataforma.
    * **Como Funciona:** Explica os passos básicos para usar a plataforma (Encontre Recursos, Compartilhe e Colabore, Conecte-se).
    * **Benefícios:** Detalha as vantagens para pequenos agricultores e para fornecedores/comunidade.
    * **Contato (Chamada para Ação):** Incentiva o usuário a entrar em contato ou acessar a plataforma de recursos.
* **Tecnologias:** HTML, Tailwind CSS, Font Awesome, JavaScript (para scroll suave).

### 2. `cadastro.html` - Página de Cadastro

Permite que novos usuários criem uma conta na Agroconnect.

* **Objetivo:** Coletar informações do usuário para registro na plataforma.
* **Funcionalidades:**
    * Formulário com campos para "Nome Completo", "Email", "Senha" e "Confirmar Senha".
    * Validação de campos (todos obrigatórios, senhas devem coincidir, senha com no mínimo 6 caracteres).
    * Toggle para visualização de senha.
    * Armazenamento local (`localStorage`) dos dados do usuário (nome, email e timestamp do cadastro). **Nota:** O armazenamento de senhas em `localStorage` não é uma prática segura para produção.
    * Feedback visual para o usuário sobre o processo de cadastro (sucesso/erro).
    * Redirecionamento para a página de login (`login.html`) após cadastro bem-sucedido.
* **Tecnologias:** HTML, Tailwind CSS, Font Awesome, JavaScript.

### 3. `login.html` - Página de Login

Permite que usuários cadastrados acessem a plataforma.

* **Objetivo:** Autenticar usuários para acesso à área de gestão de recursos.
* **Funcionalidades:**
    * Formulário com campos para "Email" e "Senha".
    * Toggle para visualização de senha.
    * Verificação dos dados de login contra os usuários armazenados em `localStorage`. **Nota:** A verificação de senha contra `localStorage` não é segura.
    * Armazenamento dos dados do usuário logado em `sessionStorage`.
    * Feedback visual para o usuário sobre o processo de login.
    * Redirecionamento para a página de gestão de recursos (`agroconnect_resource_management_v1.html`) após login bem-sucedido.
* **Tecnologias:** HTML, Tailwind CSS, Font Awesome, JavaScript.

### 4. `agroconnect_resource_management_v1.html` - Gestão de Recursos Agrícolas

Esta é a página central da aplicação, onde os usuários interagem com os recursos agrícolas.

* **Objetivo:** Permitir que usuários visualizem, adicionem, reservem e gerenciem recursos agrícolas utilizando Firebase.
* **Funcionalidades Detalhadas:**
    * **Integração com Firebase:** Autenticação (anônima/customizada) e Firestore para persistência de dados.
    * **Exibição de Recursos:** Cards responsivos com informações detalhadas, ordenados por data.
    * **Adicionar Novo Recurso:** Formulário completo para cadastro de novos itens no Firestore.
    * **Reservar Recurso:** Decrementa a quantidade do recurso via transação no Firestore.
    * **Excluir Recurso:** Permite que o criador do recurso o remova do Firestore.
    * **Interface do Usuário:** Indicador de carregamento, mensagens de feedback e modal de confirmação.
* **Tecnologias:** HTML, Tailwind CSS, Font Awesome, Firebase (Auth, Firestore, App, Analytics), JavaScript (módulos).

---

## Tecnologias Utilizadas

* **Frontend:**
    * HTML5
    * CSS3 (com Tailwind CSS)
    * JavaScript (ES6+ Modules)
* **Backend & Database (via Firebase):**
    * Firebase Authentication
    * Firebase Firestore
    * Firebase App, Analytics
* **Ícones:**
    * Font Awesome
* **Fontes:**
    * Google Fonts (Inter)

---

## Para Desenvolvedores (Considerações)

* **Configuração do Firebase:** As configurações do Firebase estão diretamente no arquivo `agroconnect_resource_management_v1.html`. Para produção, movê-las para variáveis de ambiente é recomendado.
* **Segurança:** As páginas `cadastro.html` e `login.html` usam `localStorage` para uma simulação de autenticação, o que não é seguro para senhas. A autenticação robusta com Firebase Auth está em `agroconnect_resource_management_v1.html`. Idealmente, o sistema de autenticação deveria ser unificado.

---

## Possíveis Melhorias Futuras

* Unificar o sistema de autenticação usando Firebase Auth para todas as páginas (`login.html`, `cadastro.html`).
* Implementar a funcionalidade "Esqueceu sua senha?".
* Paginação ou scroll infinito para a lista de recursos.
* Filtros e busca avançada para recursos.
* Upload direto de imagens.

---

Este documento visa fornecer uma base para entender o projeto Agroconnect, destacando seu caráter de aprendizado e as tecnologias exploradas.
