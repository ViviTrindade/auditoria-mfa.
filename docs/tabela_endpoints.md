
# Tabela de Endpoints – Auditoria MFA (LATAM Airlines)

| Endpoint                                                        | Método | Status | Descrição                                                                 |
|----------------------------------------------------------------|--------|--------|----------------------------------------------------------------------------|
| https://accounts.latamairlines.com/usernamepassword/login      | POST   | 401    | Retorna erro de autenticação por senha incorreta.                         |
| https://accounts.latamairlines.com/usernamepassword/login      | POST   | 200    | Validação de credenciais quando o alias (email/CPF) está correto.         |
| (aguardando captura)                                           | POST   | 403    | Resposta de bloqueio por política de segurança (opcional).               |

---

## Observações Técnicas

- O endpoint **/usernamepassword/login** é o principal responsável pelo fluxo de autenticação da LATAM.
- O **401 Unauthorized** confirma que o alias é válido, mas a senha enviada está incorreta.
- O **200 OK** ocorre normalmente na etapa anterior (validação do alias), antes da senha.
- O **403 Forbidden** pode aparecer após várias tentativas erradas ou em fluxos regionais de risco.
