## Cookies Identificados

| Nome | Tipo | Função | Observação |
|------|------|--------|------------|
| PIM-SESSION-ID | string | Sessão | Relacionado ao controle de login |
| ttcsid | string | Segurança | Possível fingerprinting |
| _abck | string | Anti-bot | Proteção contra automação |
| bm_sz | string | Segurança | Relacionado a proteção de sessão |

---

## Testes Realizados

### Teste 1 – Remoção de ttcsid

Resultado:
Sistema apresentou erro em tentativa inicial.

### Teste 2 – Nova sessão limpa

Resultado:
Login funcionou normalmente.

---

## Análise

- O comportamento do sistema varia conforme contexto.
- Cookies não atuam isoladamente.
- O sistema utiliza múltiplos fatores para validação.

---

## Conclusão

A autenticação depende de:
- Cookies
- Fingerprinting
- Histórico de navegação
- Comportamento do usuário
