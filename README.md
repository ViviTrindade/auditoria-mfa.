MFA Audit – LATAM Airlines

Objetivo
Analisar o comportamento do sistema de autenticação da LATAM Airlines, com foco em MFA (OTP e validação facial), utilizando técnicas de engenharia reversa em ambiente web.

---

Escopo

- Engenharia do DOM (inputs e botões)
- Interceptação de requisições (Network / Status Codes)
- Auditoria de Cookies e Persistência
- Testes de comportamento de autenticação

---

Estrutura

- `docs/` → documentação técnica detalhada
- `src/` → scripts de automação (em desenvolvimento)
- `data/` → logs HAR capturados

---

Principais Insights

- A autenticação não depende apenas de credenciais
- O sistema utiliza múltiplos fatores:
  - Cookies de sessão
  - Fingerprinting
  - Contexto de navegação

- Cookies como `ttcsid` e `PIM-SESSION-ID` participam da validação de segurança

- O comportamento é **não determinístico**, variando conforme:
  - histórico
  - tentativas
  - ambiente

---

Conclusão

Sistemas modernos de autenticação operam com base em análise de risco contextual, onde múltiplos sinais definem o nível de confiança do usuário.

---
 Próximos Passos

- Automação com Playwright
- Testes com variação de região (VPN)
- Geração de hipóteses de segurança

---

 Tags

#QA #SoftwareTesting #WebDev #CyberSecurity #TraineeToJunior
