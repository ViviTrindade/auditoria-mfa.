
# 🔎 Auditoria MFA – LATAM Airlines  

Esse repositório registra o meu estudo sobre o fluxo de autenticação da LATAM Airlines.  
Usei o Chrome DevTools para entender melhor como o login funciona “por trás da tela”:  
o que o navegador envia, quais cookies são criados, como o site responde aos erros e como o MFA se comporta.

Foi um exercício de prática em análise web, devtools, segurança e QA técnico.

---

# 📁 Estrutura do Projeto
auditoria-mfa/
│
├── README.md                 # Você está aqui
├── .gitignore
│
├── docs/                     # Documentação técnica
│   ├── dicionario_seletores.md
│   ├── tabela_endpoints.md
│   ├── analise_cookies.md
│   └── relatorio_hipoteses.pdf   (Semana 2)
│
├── src/                      # Scripts (usado na Semana 3)
│   └── .gitkeep
│
├── data/                     # logs .HAR e arquivos brutos
│   └── .gitkeep
│
└── assets/prints/            # prints de evidência
└── (telas do DOM, Network, Cookies etc.)

---

# 🧩 O que foi analisado

## 🔹 1. Estrutura do DOM (HTML)  
Mapeei os elementos principais do login, como:

- campo de usuário  
- campo de senha  
- botão de entrar  

E anotei os seletores mais estáveis (CSS e XPath), porque são úteis para automação e testes.

Arquivo completo:  
📄 `docs/dicionario_seletores.md`

---

## 🔹 2. Requisições do Login (Network)  
Depois observei como o navegador conversa com o servidor.  
Algumas respostas importantes apareceram:

- **200** → o identificador do usuário existe  
- **401** → senha errada  
- **201** → etapa relacionada ao antifraude (Akamai)

Também registrei os endpoints envolvidos no fluxo.

Arquivo completo:  
📄 `docs/tabela_endpoints.md`

---

## 🔹 3. Cookies, Local Storage e Persistência  

Listei os cookies criados durante o login. Alguns são de:

- sessão  
- segurança  
- antifraude (Akamai)  
- tracking  
- personalização  

Também olhei o Local Storage e identifiquei valores que indicam “estado” da sessão (captcha, exponea, locks e afins).

Depois zerei tudo (cookies, storage) e testei de novo o login.

Resultado:  
O fluxo reinicia, mas **o MFA não muda**, indicando que a LATAM usa outros sinais além de cookies para avaliar risco (como fingerprinting do Akamai).

Arquivo completo:  
📄 `docs/analise_cookies.md`

---

# 🧠 Resumo do aprendizado

- O login da LATAM é feito com **Auth0**, mas usa **Akamai Bot Manager** para antifraude.  
- Só limpar cookies não muda o “nível de risco”: o servidor ainda reconhece o contexto.  
- Apenas observar a aba Network já mostra muito sobre como uma aplicação web funciona.  
- A análise de DOM ajuda a entender a estrutura interna de páginas feitas com React + Material UI.  
- Cookies, storage e requisições revelam bastante sobre segurança e UX.

---

# 👩‍💻 Sobre mim  
**Vivianne Souza**  
Estudo Engenharia de Software e QA Técnico.  
Este repositório faz parte do meu processo de prática e evolução na área.
