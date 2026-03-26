
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


## Botão "Fazer login"

**Função:** Submete o formulário de autenticação após o campo de senha ser preenchido e validado.

**Atributos identificados:**
- `id="primary-button"`
- `data-testid="primary-button-button"`
- `type="submit"`
- Estrutura: `<button>` contendo `<span>` com o texto interno "Fazer login"
- Framework: Material UI (classes como `MuiButton-root`, `MuiButton-containedPrimary`, `MuiButton-fullWidth`)

**Seletores recomendados:**

**CSS (preferencial):**  
`#primary-button`

**CSS alternativo (via data-testid):**  
`button[data-testid="primary-button-button"]`

**XPath (por ID):**  
`//*[@id="primary-button"]`

**XPath (por texto):**  
`//button[span[text()="Fazer login"]]`

**XPath (via test-id):**  
`//button[@data-testid="primary-button-button"]`

**Observação técnica:**  
Embora o botão possua várias classes Material UI, elas não devem ser usadas como seletor por serem voláteis e mudarem a cada build. Os atributos `id` e `data-testid` são os mais estáveis para automação e engenharia reversa.

