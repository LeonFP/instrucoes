# Instruções para criação de aplicação web React

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
* ```public/manifest.json```

#### Arquivo public/index.html
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
### Configuração ESLint, Prettier e EditorConfig(VSCode)
Abra o arquivo package.json e exclua as linhas de configuração do eslint.
```js
"eslintConfig": {
    "extends": "react-app"
  },
```
