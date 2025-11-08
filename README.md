## 🗓️ Agenda Actions

Este projeto demonstra como configurar um **workflow automatizado de release** usando **GitHub Actions**.
O objetivo é criar uma pipeline que execute automaticamente sempre que houver um push na branch `main` ou a criação de uma nova **tag semântica** (ex: `v1.0.0`).

---

### 🚀 Funcionalidades

* ✅ **Integração contínua (CI)** com GitHub Actions
* 🏷️ **Criação de releases automáticas** baseadas em tags semver
* ⚙️ **Instalação de dependências Node.js** via `npm install`
* 🔐 Uso de **GitHub Token** para autenticação segura
* 🧩 Estrutura simples e fácil de expandir

---

### 📂 Estrutura do Projeto

```
agenda-actions/
├── .github/
│   └── workflows/
│       └── release.yml     # Workflow de release automatizada
├── package.json            # Configuração do projeto Node.js
└── README.md               # Documentação do projeto
```

---

### ⚙️ Como funciona o Workflow

O arquivo `.github/workflows/release.yml` contém as instruções do GitHub Actions para automatizar o processo de release.

#### 🔹 Gatilhos

O workflow é executado automaticamente quando ocorre:

```yaml
on:
  push:
    branches:
      - main
    tags:
      - 'v*.*.*'
```

Ou seja:

* Quando você envia um novo commit para `main`, ou
* Quando cria uma tag como `v1.0.0`, `v1.2.3`, etc.

#### 🔹 Etapas do Workflow

1. **Exemplo de uso do token**

   * Demonstra como acessar o token de autenticação.
2. **Checkout do código**

   * Baixa o conteúdo do repositório.
3. **Configurar Node.js**

   * Define a versão 18 do Node.
4. **Instalar dependências**

   * Executa `npm install` (usa o `package.json`).
5. **Criar Release**

   * Etapa simbólica que imprime “Release criada com sucesso!”

---

### 🧠 Exemplo de uso

#### 1️⃣ Criar um commit

```bash
git add .
git commit -m "fix: ajustar fluxo de release"
git push origin main
```

#### 2️⃣ Criar uma tag semver

```bash
git tag -a v1.0.0 -m "Versão inicial automatizada"
git push origin v1.0.0
```

Isso aciona o workflow e executa a pipeline de release.

---

### 🔐 Autenticação

O workflow utiliza o token padrão do GitHub Actions (`secrets.GITHUB_TOKEN`), que é gerado automaticamente a cada execução — não é necessário criar um token manual.

---

### 📜 Logs e Execuções

Você pode visualizar os resultados e logs das execuções na aba **Actions** do repositório.

---

### ✨ Autor

**Arthur ACM**
Desenvolvedor e entusiasta de automações com GitHub Actions 🚀
[github.com/arthuracmm](https://github.com/arthuracmm)

---

### 🏁 Próximos passos

* Adicionar testes automatizados (`npm test`)
* Criar releases com changelogs automáticos
* Publicar pacotes (ex: no npm ou GitHub Packages)

