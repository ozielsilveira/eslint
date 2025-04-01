# ESLint - Linter para JavaScript/TypeScript

### 1. Instruções de Instalação

#### Passo 1: Instalar o ESLint

O ESLint pode ser instalado globalmente ou localmente em seu projeto. A instalação local é recomendada, pois garante que todos no time usem a mesma versão da ferramenta. 

```bash
# Instalação local no projeto
npm install --save-dev eslint
```

A flag `--save-dev` indica que o ESLint será instalado como uma dependência de desenvolvimento, ou seja, ele será usado apenas durante o processo de desenvolvimento e não será necessário em produção.

#### Passo 2: Inicializar o ESLint

Depois de instalado, o ESLint precisa ser configurado. Isso pode ser feito com o comando `--init`. Ele cria o arquivo de configuração do ESLint, que pode ser `.eslintrc.json`, `.eslintrc.js`, `.eslintrc.yml`, ou outro, dependendo da escolha do desenvolvedor.

```bash
npx eslint --init
```

Ao rodar esse comando, você será perguntado sobre:

- **Como você quer usar o ESLint?** (ex: para Node.js ou para o frontend)
- **Qual estilo de código você prefere?** (ex: Airbnb, Google, Standard)
- **Quais ferramentas você está usando?** (ex: TypeScript, React, etc.)

Esse processo cria um arquivo `.eslintrc.json` com a configuração inicial do ESLint.

### 2. Integração com o Ambiente de Desenvolvimento

#### Visual Studio Code (VSCode)

O **VSCode** tem uma excelente integração com o ESLint. Você pode instalar a extensão ESLint diretamente na loja de extensões do VSCode.

Após instalar a extensão, o ESLint começa a verificar automaticamente o código à medida que você digita, destacando erros e avisos no editor.

1. Instale a extensão ESLint no VSCode.
2. Quando você abrir seu projeto, o ESLint já começará a exibir os problemas de estilo no código diretamente no editor.

#### Outros Editores

Para outros editores como Sublime Text ou Atom, você pode instalar plugins específicos para integrar o ESLint e obter feedback em tempo real sobre os problemas de estilo no código.

### 3. Estilização Automática

#### Comando `--fix`

Uma das funcionalidades mais poderosas do ESLint é a capacidade de corrigir automaticamente certos tipos de erros de estilo no código. Isso é feito através do comando `--fix`.

Imagine que você tenha o seguinte código:

```javascript
const myVar=42
```

Rodando o comando `eslint --fix` vai corrigir o código automaticamente para:

```javascript
const myVar = 42;
```

Para rodar a correção automática em todos os arquivos do seu projeto, use o seguinte comando:

```bash
npx eslint . --fix
```

O `.` indica que o ESLint deve ser executado em todos os arquivos do diretório atual e seus subdiretórios.

### 4. Guias de Estilo Utilizados

O ESLint pode seguir diferentes guias de estilo para garantir que o código esteja sempre padronizado. Os mais comuns incluem:

- **Airbnb JavaScript Style Guide**: Muito popular e amplamente utilizado. Ele segue convenções detalhadas sobre organização de código, uso de espaços, quebras de linha, etc.
  
  Para usar o guia de estilo do Airbnb, adicione o seguinte ao seu arquivo `.eslintrc.json`:

  ```json
  {
    "extends": "airbnb-base"
  }
  ```

- **Standard JavaScript Style**: Um guia mais simples, que elimina algumas regras mais complexas do Airbnb, como o uso obrigatório de ponto e vírgula.

  Para usar o guia "Standard", use:

  ```json
  {
    "extends": "standard"
  }
  ```

- **Google JavaScript Style Guide**: O guia de estilo usado pelo Google, com foco em clareza e legibilidade.

  Para usá-lo, adicione:

  ```json
  {
    "extends": "google"
  }
  ```

### 5. Regras de Estilo Configuráveis

O ESLint permite que você configure regras específicas para o seu projeto. Aqui estão três exemplos comuns de regras configuráveis:

#### 1. **Indentação**

A indentação é um dos aspectos mais importantes para garantir a legibilidade do código. O ESLint pode ser configurado para exigir uma quantidade específica de espaços ou tabs para a indentação.

```json
{
  "indent": ["error", 2]
}
```

Isso garante que o código use **2 espaços** para a indentação, gerando um erro caso algo diferente seja encontrado.

#### 2. **Uso de ponto e vírgula**

Por padrão, o ESLint pode exigir o uso de ponto e vírgula no final de cada linha de código. Você pode configurar isso assim:

```json
{
  "semi": ["error", "always"]
}
```

Isso fará com que o ESLint gere um erro caso você esqueça de colocar o ponto e vírgula.

#### 3. **Espaços ao redor de operadores**

A seguinte regra exige que haja um espaço em torno de operadores (como `+`, `=`, `==`, etc.):

```json
{
  "space-infix-ops": ["error", { "int32Hint": false }]
}
```

Essa configuração garante que a expressão:

```javascript
let x=5+3;
```

seja corrigida para:

```javascript
let x = 5 + 3;
```

### 6. Exemplo de Código a Ser Estilizado

#### Código Original

Aqui está um exemplo de código desorganizado que pode ser corrigido com o ESLint:

```javascript
function greet(name){
console.log('Hello, ' + name)
}
greet('Alice')
```

#### Código Após Correção

Depois de rodar o comando `eslint --fix`, o código será corrigido automaticamente para:

```javascript
function greet(name) {
  console.log('Hello, ' + name);
}

greet('Alice');
```

As correções incluem:
- Adição de espaços após `function` e antes de `()`.
- Colocação de um ponto e vírgula no final da linha `console.log`.
- Correção na indentação.

---

### 7. Conclusão

O ESLint é uma ferramenta indispensável para qualquer projeto JavaScript ou TypeScript. Ele ajuda a garantir que o código siga boas práticas de estilo e que os desenvolvedores evitem erros comuns, além de melhorar a legibilidade e a manutenibilidade do código.

Configurando o ESLint, você pode automatizar a correção de problemas simples, reduzir a quantidade de erros em revisão de código e garantir que todos os desenvolvedores sigam as mesmas convenções de estilo.
