#  React + Firebase Auth

Projeto de autenticação completo com **React**, **Vite** e **Firebase Authentication**. Permite cadastro e login de usuários com e-mail e senha, com interface moderna e responsiva.

---

##  Funcionalidades

- Cadastro de usuários com e-mail e senha
- Login com e-mail e senha
- Logout
- Escuta em tempo real do estado de autenticação (`onAuthStateChanged`)
- Mensagens de erro em português
- Tela protegida: exibe o painel apenas para usuários logados

---

##  Estrutura do Projeto

```
React-projeto-firebase/
├── index.html
├── vite.config.js
├── package.json
└── src/
    ├── main.jsx               # Entrada da aplicação
    ├── App.jsx                # Lógica principal e roteamento por estado de auth
    ├── App.css                # Estilos da tela logada
    ├── index.css              # Reset global
    ├── firebase.js            # Inicialização do Firebase
    ├── services/
    │   └── auth.js            # Funções: login, register, logout
    └── components/
        ├── AuthForm.jsx       # Formulário de login/cadastro
        └── AuthForm.css       # Estilos do formulário
```

---

##  Pré-requisitos

- [Node.js](https://nodejs.org/) v18 ou superior
- Conta no [Firebase](https://firebase.google.com/)
- Projeto criado no Firebase Console com **Authentication** habilitado

---

##  Como rodar o projeto

### 1. Clone ou extraia o projeto

```bash
# Se clonou via Git:
git clone https://github.com/seu-usuario/react-projeto-firebase.git
cd react-projeto-firebase

# Se extraiu o ZIP, entre na pasta:
cd React-projeto-firebase
```

### 2. Instale as dependências

```bash
npm install
```

> Isso instala o **Firebase**, React, Vite e todas as outras dependências listadas no `package.json`.

### 3. Configure o Firebase

Abra o arquivo `src/firebase.js` e substitua os valores pelas credenciais do seu projeto:

```js
const firebaseConfig = {
  apiKey: "SUA_API_KEY",
  authDomain: "SEU_PROJECT.firebaseapp.com",
  projectId: "SEU_PROJECT_ID",
  storageBucket: "SEU_PROJECT.appspot.com",
  messagingSenderId: "SEU_MESSAGING_ID",
  appId: "SEU_APP_ID"
};
```

>  Você encontra essas credenciais em: **Firebase Console → Seu Projeto → Configurações → Seus aplicativos → SDK do Firebase**

### 4. Rode o servidor de desenvolvimento

```bash
npm run dev
```

Acesse em: [http://localhost:5173](http://localhost:5173)

---

##  Configurando o Firebase Authentication

1. Acesse o [Firebase Console](https://console.firebase.google.com/)
2. Selecione seu projeto
3. No menu lateral, clique em **Authentication**
4. Clique em **Começar**
5. Na aba **Sign-in method**, habilite **E-mail/senha**
6. Salve

---

## Scripts disponíveis

| Comando | Descrição |
|---|---|
| `npm run dev` | Inicia o servidor de desenvolvimento |
| `npm run build` | Gera o build de produção na pasta `dist/` |
| `npm run preview` | Visualiza o build de produção localmente |
| `npm run lint` | Executa o ESLint para análise de código |

---

## 🛠️ Tecnologias utilizadas

| Tecnologia | Versão | Função |
|---|---|---|
| [React](https://react.dev/) | 19 | Interface do usuário |
| [Vite](https://vitejs.dev/) | 6 | Bundler e servidor de desenvolvimento |
| [Firebase](https://firebase.google.com/) | 11 | Autenticação de usuários |

---

## Detalhamento dos arquivos principais

### `src/firebase.js`
Inicializa o app Firebase e exporta a instância do `auth` para ser usada em todo o projeto.

### `src/services/auth.js`
Contém as três funções de autenticação:
- `register(email, password)` — cria um novo usuário
- `login(email, password)` — autentica um usuário existente
- `logout()` — encerra a sessão atual

### `src/App.jsx`
Componente raiz que observa o estado de autenticação em tempo real. Exibe o `AuthForm` para usuários não logados e o painel de boas-vindas para usuários autenticados.

### `src/components/AuthForm.jsx`
Formulário com alternância entre os modos **Entrar** e **Cadastrar**. Trata os principais erros do Firebase e exibe mensagens amigáveis em português.

---

##  Erros comuns

| Erro | Causa | Solução |
|---|---|---|
| `Failed to resolve import "firebase/auth"` | Firebase não instalado | Execute `npm install` |
| `auth/invalid-credential` | E-mail ou senha incorretos | Verifique as credenciais |
| `auth/email-already-in-use` | E-mail já cadastrado | Use outro e-mail ou faça login |
| `auth/weak-password` | Senha com menos de 6 caracteres | Use uma senha mais longa |
| Tela em branco sem erros | Credenciais do Firebase incorretas | Verifique o `firebase.js` |

---

##  Prints
<img width="1919" height="1031" alt="image" src="https://github.com/user-attachments/assets/61862a89-c0fa-4856-9c72-0b08ed5d133c" />
<img width="1916" height="1031" alt="image" src="https://github.com/user-attachments/assets/d5ca15ed-c6a4-4e27-8372-0f583cfa27b1" />




