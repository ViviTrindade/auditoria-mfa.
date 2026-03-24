#  MFA Audit – LATAM Airlines

##  Objetivo
Analisar o comportamento do sistema de autenticação da LATAM Airlines, focando em MFA (OTP e validação facial), utilizando engenharia reversa em ambiente web.

---

##  Escopo da Análise

- Engenharia do DOM (inputs e botões)
- Interceptação de requisições (Network / Status Codes)
- Auditoria de Cookies e Persistência
- Testes de comportamento de autenticação

---

## Estrutura do Projeto

- `docs/` → Documentação técnica
- `src/` → Scripts de automação (em desenvolvimento)
- `data/` → Logs HAR

---

## 🔍 Principais Descobertas

- O sistema utiliza múltiplos fatores para autenticação:
  - Cookies de sessão
  - Fingerprinting
  - Comportamento do usuário

- Cookies como `ttcsid` e `PIM-SESSION-ID` influenciam o fluxo de login.

- O comportamento não é determinístico:
  - O mesmo teste pode gerar respostas diferentes (bloqueio, MFA ou acesso normal).

---

## Conclusão

A autenticação moderna não depende apenas de login e senha, mas de um conjunto de sinais que definem o nível de confiança do usuário.

---

#QA #SoftwareTesting #WebDev #CyberSecurity #TraineeToJunior
