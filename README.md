# 🧪 Curso de Testes Automatizados e Quality Assurance com Cypress

Este repositório faz parte do curso de **Testes e Quality Assurance (QA)**, com foco em **automação de testes end-to-end (E2E)** utilizando o **Cypress**, integração contínua e boas práticas modernas de qualidade de software.

---

## 🎯 Objetivos do Curso

Ao final deste curso, você será capaz de:

* ✅ Automatizar testes **E2E com Cypress** para garantir a qualidade do software
* 🔄 Implementar **pipelines de Integração Contínua (CI)** com **GitHub Actions**
* ☁️ Integrar o **Cypress Cloud** para facilitar a colaboração em testes
* 🧬 Utilizar **faker.js** e plugins para gerar dados realísticos nos cenários de teste
* 🤖 Aplicar **Inteligência Artificial** para melhorar a escrita e eficiência dos testes
* 📈 Adotar **boas práticas de QA** para aumentar a produtividade em automação

---

## 🧰 Tecnologias Utilizadas

* **Node.js** (versão **20.11.1**)
* **Cypress** 13.7.2
* **Mochawesome** 7.1.3
* **faker.js**
* **Git & GitHub**
* **GitHub Actions**
* **Visual Studio Code (VSC)**

---

## 📋 Pré-requisitos

Antes de iniciar, certifique-se de ter instalado:

* [Node.js](https://nodejs.org/) (versão **20.11.1**)
* [Visual Studio Code](https://code.visualstudio.com/)
* Git

### 🔎 Verificando a versão do Node.js

No terminal, execute:

```bash
node -v
```

Se não possuir a versão correta, recomenda-se o uso do **NVM (Node Version Manager)**.

> 💡 **Windows:** é altamente recomendado o uso do **WSL (Windows Subsystem for Linux)** para melhor compatibilidade.

---

## 🚀 Instalação do Cypress

Abra o terminal integrado do VS Code (**Ctrl + J**) e execute:

```bash
npm install cypress@13.7.2 --save-dev
```

### 📊 Instalação do Mochawesome (Reporter)

```bash
npm install mochawesome@7.1.3 --save-dev
```

---

## ⚙️ Configuração do Cypress

No arquivo `cypress.config.js`, utilize a seguinte configuração:

```js
const { defineConfig } = require("cypress");

module.exports = defineConfig({
  e2e: {
    setupNodeEvents(on, config) {
      // implement node event listeners here
    },
    video: true,
    reporter: 'mochawesome',
    reporterOptions: {
      reportDir: 'cypress/results',
      overwrite: false,
      html: true,
      json: false,
      timestamp: "mmddyyyy_HHMMss"
    },
  }
}););
```

Os relatórios de teste serão gerados automaticamente na pasta:

```
cypress/results
```

---

## 🏥 Projeto do Curso

O projeto utilizado no curso é a plataforma **Vollmed**, um sistema de gerenciamento de clínicas médicas que conecta médicos especialistas a pacientes.

### 📦 Repositórios do Projeto

* **Front-end:** Client Vollmed
* **Back-end:** Servidor Vollmed

---

## 🗂️ Estrutura do Projeto

Na raiz do projeto Cypress, organize da seguinte forma:

```text
vollmecypress/
├── cypress/
├── web/        # Front-end
├── server/     # Back-end
├── cypress.config.js
├── package.json
```

---

## 🔐 Configuração do Back-end

Dentro da pasta `server`, crie um arquivo `.env` com o seguinte conteúdo:

```env
DB_HOST="localhost"
DB_PORT=3306
DB_USER=root
DB_PASSWORD=suasenha
DB_DATABASE=testemed
SERVER_PORT=8080
SECRET=qualquercoisa
SECRET_KEY="qualquertextoaqui"
```

---

## ▶️ Executando o Projeto

Dentro das pastas `web` e `server`, execute:

```bash
npm install
npm start
```

Acesse:

* 🌐 **Front-end:** [http://localhost:3000/](http://localhost:3000/)
* 🔌 **Back-end:** [http://localhost:8080/](http://localhost:8080/)

---

## 🧪 Executando os Testes

### Modo interativo:

```bash
npx cypress open
```

### Modo headless:

```bash
npx cypress run
```

---

## 📌 Observações Importantes

* Arquivos de resultados (`cypress/results`, `videos`, `screenshots`) devem estar no `.gitignore`
* Este projeto segue boas práticas utilizadas em ambientes reais de QA
* Projeto desenvolvido para fins educacionais no curso de **Testes Automatizados e Quality Assurance com Cypress**.

🚀 Bons testes e boa automação!
