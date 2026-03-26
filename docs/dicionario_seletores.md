
### Campo de Login (Email, CPF ou Número de Cliente)

**Função:** campo onde o usuário insere o identificador para autenticação.

**Atributos encontrados:**
- `id="form-input--alias"`
- `name="alias"`
- `data-testid="form-input--alias-textfield-input"`
- `placeholder="Email, CPF ou Número de cliente"`
- Framework: Material UI (classes MUI)

**Seletores recomendados:**

**CSS (preferencial):**
`#form-input--alias`

**CSS alternativo (via data-testid):**
`input[data-testid="form-input--alias-textfield-input"]`

**XPath (por ID):**
`//*[@id="form-input--alias"]`

**XPath (por placeholder):**
`//input[@placeholder="Email, CPF ou Número de cliente"]`

**Observação técnica:**
O uso de `data-testid` indica suporte a frameworks de testes e estabilidade de seletor. Classes do Material UI mudam a cada build, portanto não são recomendadas como seletores.
