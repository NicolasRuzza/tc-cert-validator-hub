# Sistema de Gestão e Validação de Certificados Digitais

![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![NodeJS](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/NGINX-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Debian](https://img.shields.io/badge/Debian-A81D33?style=for-the-badge&logo=debian&logoColor=white)

> **Resumo:** Projeto desenvolvido em equipe visando a modernização e segurança do fluxo de entrega de certificados de qualidade industrial. O sistema substituiu processos manuais por uma solução automatizada integrada ao ecossistema Microsoft, garantindo integridade de dados e eficiência operacional.

## Código-Fonte e Módulos

Este repositório atua como documentação central da arquitetura. O código-fonte da aplicação web está desacoplado nos repositórios abaixo:

| Módulo | Tecnologia | Responsabilidade | Link |
| :--- | :--- | :--- | :--- |
| **Frontend (Secure Viewer)** | Angular, TypeScript | Visualização protegida com marca d'água dinâmica e travas contra cópia. | [📂 Acessar Frontend](https://github.com/NicolasRuzza/tc-pdf-viewer) |
| **Backend (API)** | Node.js, MS Graph | Orquestração de segurança, comunicação com SharePoint e autenticação. | [📂 Acessar Backend](https://github.com/NicolasRuzza/tc-pdf-obtainer) |

> **Nota sobre Infraestrutura:** Os arquivos de orquestração (`docker-compose.yml`) e configuração de proxy reverso (`nginx.conf`) encontram-se versionados dentro dos repositórios acima, facilitando o deploy isolado ou conjunto.

## Arquitetura da Solução

O sistema foi projetado para garantir uma **Single Source of Truth (Fonte Única da Verdade)**, utilizando o SharePoint como base de dados e garantindo acesso seguro via aplicação customizada.

### 1. Visualizador Seguro (Frontend)

Interface web desenvolvida em **Angular** responsável pela exibição protegida dos documentos.

* **Segurança:** Implementação de renderização individual de páginas.
* **Marca D'água Dinâmica:** Inserção de data/hora e identificador do usuário em tempo real sobre o documento.
* **DLP (Data Loss Prevention):** Travas lógicas (via JS e CSS) para impedir cópias, impressão e downloads não autorizados.

### 2. Integração e API (Backend)

API estruturada em **Node.js (TypeScript)** que atua como middleware seguro entre o usuário e os dados.

* Orquestração da comunicação com **Microsoft Graph API**.
* Gerenciamento de requisições e controle de acesso aos certificados na nuvem.

### 3. Engenharia de Dados & Automação (Ecossistema)

Além da aplicação web, o projeto envolveu processos de estruturação de dados:

* **SharePoint Governance:** Reestruturação da taxonomia das informações para permitir consumo automatizado.
* **Gerador de Etiquetas (Python):** Script auxiliar que gera QR Codes dinâmicos vinculando máquinas físicas às suas pastas digitais correspondentes.

## Infraestrutura e Deploy

O ambiente de produção foi configurado focando em segurança de rede e performance.

* **Servidor:** Máquina Virtual Debian Linux.
* **Containerização:** Aplicação totalmente "dockerizada".
* **Web Server:** Implementação do **NGINX** atuando como:
  * *Reverse Proxy*
  * *Load Balancer*
  * Terminação SSL/TLS

## Stack Tecnológica Completa

* **Linguagens:** TypeScript, Python, JavaScript.
* **Frameworks:** Angular, Node.js.
* **Integrações:** Microsoft Graph API, SharePoint.
* **DevOps/Infra:** Docker, NGINX, Linux (Debian).

## Autores

Projeto desenvolvido em equipe

* **Post no linkedin para mais detalhes e integrantes** - [LinkedIn](https://www.linkedin.com/in/n%C3%ADcolas-ruzza-334a3826a/details/projects/)
