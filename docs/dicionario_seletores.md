
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


## Campo de Senha (Password)

**Função:** Campo onde o usuário insere sua senha após validação do identificador (email/CPF/Número LATAM Pass).

**Atributos identificados:**
- `id="form-input--password"`
- `name="password"`
- `placeholder="Senha"`
- `type="password"`
- `data-testid="form-input--password-textfield-input"`
- Classes Material UI: `MuiInputBase-input`, `MuiOutlinedInput-input`, `MuiInputBase-inputAdornedEnd`

**Seletores recomendados:**

**CSS (preferencial):**  
`#form-input--password`

**CSS alternativo (via data-testid):**  
`input[data-testid="form-input--password-textfield-input"]`

**XPath (por ID):**  
`//*[@id="form-input--password"]`

**XPath (por placeholder):**  
`//input[@placeholder="Senha"]`

**Observação técnica:**  
O campo de senha só é renderizado após validação do campo "alias". Isso indica renderização condicional via React + Material UI. Classes MUI não são recomendadas como seletores devido à volatilidade entre builds.

