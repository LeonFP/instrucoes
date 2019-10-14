# Instruções para criação de aplicação web React
Versão do react utilizada 16.10.2

## Criação do projeto
### Criação da estrutura do projeto
Navegue até a pasta onde pretende criar o projeto e rode o seguinte comando.
```
yarn create react-app NOME_DO_PROJETO
```

### Limpeza de ambiente
#### Exclusão de arquivos
Exclua os seguintes arquivos
* ```README.md```
* ```public/manifest.json e robots.txt```
* ```src/App.css , index.css , App.test.js , logo.svg , serviceWorker.js```

#### public/index.html
Nesse arquivo exclua todas as linhas referentes a comentários.
Exclua a linha referente ao manifest.
O código final deve se parecer com isso.
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <link rel="apple-touch-icon" href="logo192.png" />
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
    <title>React App</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
  </body>
</html>
```

#### src/index.js
Exclua as linhas relacionadas ao serviceWorker, incluindo a importação.
Exclua a importação do index.css
O arquivo final vai ficar parecido com isso.
```js
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";

ReactDOM.render(<App />, document.getElementById("root"));
```

### src/App.js
Exclua as linhas de importação da logo e do App.css
Dentro da className="App" coloque um simples Hello World.
O arquivo ficará parecido com isso.
```jsx
import React from "react";

function App() {
  return (
    <div className="App">
      <h1>Hello World</h1>
    </div>
  );
}

export default App;
```

### Configuração ESLint, Prettier e EditorConfig(VSCode)
#### Pré requisitos
* Extensão **EditorConfig for VS Code** instalada no VS Code
Abra o arquivo package.json e exclua as linhas de configuração do eslint.
```json
"eslintConfig": {
    "extends": "react-app"
  },
```
#### Criação do arquivo .editorconfig
Clique com o botão direito na pasta do projeto e escolha a opção **Generate .editorconfig** essã opção só parecerá caso você possua a extensão instalada.
Deixe o arquivo da seguinte maneira.
```bat
root = true

[*]
indent_style = lf
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```
#### ESLint
Adicione o ESLint como dependencia de desenvolvimento.
```
yarn add eslint -D
yarn eslint --init
```
Siga as instruçoes do ESLint.
exclua o arquivo ```package-lock.json``` e execute ```yarn``` na pasta

Instalação do prettier
```yarn add prettier eslint-config-prettier eslint-plugin-prettier babel-eslint -D```

Arquivo .eslintrc.js
```js
module.exports = {
  env: {
    browser: true,
    es6: true
  },
  extends: ["airbnb", "prettier", "prettier/react"],
  globals: {
    Atomics: "readonly",
    SharedArrayBuffer: "readonly"
  },
  parser: "babel-eslint",

  parserOptions: {
    ecmaFeatures: {
      jsx: true
    },
    ecmaVersion: 2018,
    sourceType: "module"
  },
  plugins: ["react", "prettier"],
  rules: {
    "prettier/prettier": "error",
    "react/jsx-filename-extension": ["warn", { extensions: [".jsx", ".js"] }],
    "import/prefer-default-export": "off"
  }
};
```

Crie um arquivo chamado .prettierrc
```js
{
  "singleQuote": true,
  "trailingComma": "es5"
}
```
