
### Teste de Persistência – Resultado Final

Após remover manualmente todos os cookies, localStorage e sessionStorage do domínio `accounts.latamairlines.com`, a página de autenticação da LATAM foi recarregada e o fluxo de login foi reiniciado.

No entanto, ao realizar uma nova tentativa de login, o comportamento do fluxo de MFA **não se alterou**. A página exibiu novamente o estado estándar de erro de senha incorreta, sem solicitar OTP adicional, CAPTCHA reforçado ou reconhecimento facial.

**Conclusão técnica:**  
A remoção de dados locais (cookies e storage) não é suficiente para alterar o comportamento do mecanismo de MFA da LATAM. Isso indica que:

- A LATAM utiliza **fingerprinting avançado** via Akamai Bot Manager.  
- Parte da avaliação de risco ocorre **fora do navegador**, possivelmente baseada em:  
  - reputação de IP,  
  - análise de dispositivo via fingerprint externo,  
  - integridade comportamental,  
  - parâmetros criptográficos do cookie `_abck` reconstruídos pelo servidor.

Assim, mesmo após “resetar” o ambiente no navegador, o sistema ainda reconhece o contexto como válido e mantém o fluxo padrão de autenticação.
