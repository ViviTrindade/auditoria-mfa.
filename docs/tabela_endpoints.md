
# Tabela de Endpoints – Auditoria MFA (LATAM Airlines)

Esta tabela documenta os endpoints capturados no fluxo de autenticação da LATAM durante auditoria técnica (Tarefa 2.2).

---

## Endpoints Observados

| Endpoint                                                        | Método | Status | Descrição                                                                                   |
|----------------------------------------------------------------|--------|--------|-----------------------------------------------------------------------------------------------|
| https://accounts.latamairlines.com/usernamepassword/login      | POST   | 401    | Autenticação falhou: senha incorreta. API retorna erro de credenciais.                       |
| https://accounts.latamairlines.com/usernamepassword/login      | POST   | 200    | Fluxo inicial de validação do alias (email/CPF). Indica que o usuário existe.                |
| https://accounts.latamairlines.com/yBK-ma/s/S/.../VOG4B        | POST   | 201    | Endpoint intermediário de "resource creation" utilizado por Akamai/Flex para antifraude.     |
| (pendente - opcional)                                          | POST   | 403    | Bloqueio de tentativa (pode ocorrer após várias falhas ou por política de risco regional).   |

---

## Observações Técnicas

- O endpoint **/usernamepassword/login** é o core da autenticação.  
- O retorno **401 Unauthorized** confirma que o alias foi aceito, mas a senha está errada.  
- O retorno **200 OK** ocorre na etapa de validação do usuário (fluxo pré-senha).  
- O **201 Created** indica que a LATAM usa um sistema de *interceptação de risco* (Akamai, Flex ou similar).  
- A presença de cookies longos, headers extensos e múltiplos `server-timing` reforça fingerprinting + antifraude.  
