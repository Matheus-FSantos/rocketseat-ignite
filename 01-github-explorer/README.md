# Github Explorer&nbsp;&nbsp;<img src="https://cdn-icons-png.flaticon.com/512/1183/1183621.png" width="50" height="auto" align="center">&nbsp;&nbsp;<img src="https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png" width="50" height="auto" align="center">

### 🚀 - RocketSeat Ignite

Nesta sessão iramos adentrar um pouco mais no ecossistema React e entender como funciona o comando ```npx create-react-app <project-name>```, entenderemos toda a arquitetura de pastas de uma WebApp, para que no final de tudo isso, possemos implementar SPAs utilizando as melhores praticas do mercado e de forma fácil/limpa.

> OBS.: Nessa sequencia de estudos, estou utilizando o gerenciador de pacotes YARN, caso você não tenha ele instalado, rode o seguinte comando: ```npm install --global yarn``` para instar-lo globalmente em sua máquina, a grande maioria dos comandos eu informo o que usei, com yarn, e a sua possivel conversão para o npm, porém, não é sempre que eu lembro 🤡🤡🤡

<a name="navegação"></a>

###### Navegação:
É possivel que parte da nevagação ainda não esteja funcionando, porém, relevem.

- [Aula 01 - Arquitetura do REACT](#arquitetura)
- [Aula 02 - Babel](#babeljs)
- [Aula 03 - Webpack](#webpack)

<a name="arquitetura"></a>

##### ⚙️ - Arquitetura do REACT (Aula 01)

Para esse estudo, é de suma importancia entender a estrutura de cada comando e, obviamente, o que cada um deles fazem, dentro de seus respectivos contextos.

Até o momento, foi apresentado 3 comandos, que são eles:

- ```yarn init -y```
- ```yarn add react```
- ```yarn add react-dom```

A respeito do: **yarn init -y**, ou no npm: ```npm init -y``` esse comando é o **PONTAPÉ INICIAL DE TODA APLICAÇÃO QUE UTILIZA JAVASCRIPT**, utilizando esse comando você criará um arquivo: "package.json" que dentro dele irá conter todas as informações de seus projeto e, como ponto chave, salvará todas as informações de dependencias do projeto, funciona semelhantemente ao POM.XML do Java, onde é registrada todas as informações do projeto, como nome, pacote raiz, autor, dependencias e entre outras configurações.

> OBS.: Ao subir uma aplicação no GitHub, por padrão você deve ter o .gitignore para informar quais arquivos/pastas o Git deve ignorar, afinal, são arquivos desnecessários e que aumentam, drasticamente, o tamanho, em GBs, do repositório remoto. Você provavelmente irá se deparar, em repositorios onde o produto final está sendo implementado com tecnologias JavaScript, ou somente um produto dele (isso não importa), que, por exemplo, o diretório "node_modules" não irá entrar, ao se deparar com isso, clonando o repositorio em sua máquina, para que você possa instalar todas as dependencias que o projeto utiliza, e, consequentemente, conseguir utilizar o projeto localmente em seu computador, deve-se utilizar o comando ```yarn install``` ou ```npm install```, lembre-se de estar na pasta raiz do projeto, com esses comandos, seja la com qual gerenciador de dependencias você estiver utilizando, você será capaz de baixar todas as dependencias em seu computador e conseguirá utilizar o projeto e implementar novas features ou corrigir alguns bugs que você encontrou.

Avançando para o comando seguinte desse, encontramos: ```yarn add react```, ou caso utilize npm: ```npm install react```, se não me falha a memória, com esse comando você adicionará a dependencia do React no seu projeto, informando ao package JSON que você, em algum momento de sua aplicação, irá utilizar o React para desenvolver componentes e entre outros, **está basicamente informando que esse projeto irá utilizar o React**.

O último comando dessa lista é o: ```yarn add react-dom```, caso esteja usando npm será: ```npm install react-dom```, esse comando **informa para o seu projeto que você irá trabalhar com web**, esse DOM é justamente o Document do JavaScript, onde é possivel manipular o HTML, pegando elementos do próprio código HTML, e manipulando com o JavaScript/JQuery/Ajax e etc.

> OBS.: Como estamos desenvolvendo com REACT para WEB então se faz necessário baixar essa dependencia que citamos acima, porém, se estivesse criando a arquitetura do 0, como foi proposto nesse repositorio, e estivesse criando um projeto REACT para MOBILE, ao invés de baixar o yarn add react você substituiria por yarn add react-native, já que com React Native você é capaz de criar aplicações mobile fantásticas de forma muito eficiente e produtiva e com uma curva de aprendizado fantástica.

Até então é isso, essa foi a primeira aula da Trilha Ignite da RocketSeat onde, como principal objetivo, podemos análisar, de forma superficial, como funciona a arquitetura do REACT. Provavelmente em aulas futuras, ou até mesmo posterior a essa, continuaremos explorando essa arquitetura.

<a name="babeljs"></a>

##### 🌐 - Entendendo BABEL (Aula 02)

Essa aula tem como principal objetivo entender, e compreender realmente, como funciona o **babel** precisamos saber como isso aparece na Biblia. A torre de **babel** foi uma torre que o povo antigo tentou criar onde, resumidamente, eles acreditavam que se construissem uma torre muito alta, a ponto de passar das nuvens, eles conseguiriam chegar ao paraíso, porém, segundo a biblia, Deus separou o povo com linguas distintas para que essa construção não fosse concluida e é dai que vem o conceito de Babel do JavaScript.

###### 📖 - Conceito

O *babel* ele serve para **converter o nosso código para uma maneira que todos os navegadores/ambiente da aplicação consiga entender** todos os códigos escritos.

###### ❓ - Porque ele é necessário?

Pelo JavaScript ser uma linguagem que se atualiza constantemente, usando o próprio **REACT** como base, possa ser que, em alguma versão atual da biblioteca, existam maneiras de escrever o HTML dentro do código JS, por exemplo, de uma maneira que os navegadores ainda não entendem, **é ai que entra o babel!**

De acordo com esse cenário apresentado acima, o babel vai entrar em ação para converter esse código escrito para uma maneira que todos os navegadores mais modernos consigam entender, reduzindo assim (ou até mesmo acabando) com possiveis erro de compatibilidade, se é que eu posso dizer assim.

###### 📁 - Instalação

Para instalar o bebel em seu projeto, deve-se rodar o seguinte comando: ```yarn add @babel/core @babel/cli @babel/preset-env -D``` ou, caso esteja usando npm, deve-se utilizar: ```npm install @babel/core @babel/cli @babel/preset-env -D```.

> OBS.: A flag (bandeira) **-D** é utilizada para informar ao gerenciador de dependencias/pacotes que aquele(s) comando(s) irá(ão) ser instalado(s) como **dependencia de desenvolvimento**. O que isso significa? Significa que aquela dependencia não entrará em vigor quando o sistema subir para produção, a aplicação só irá precisar dele quando estiver no ambiente de desenvolvimento. 

A respeito dos comandos instalados, abaixo vai uma breve descrição de cada um deles, explicando o que eles representam:

- ```@babel/core```: É o coração do babel, sua biblioteca principal, básicamente 99% das funcionalidades do babel estão contidas dentro dela;
- ```@babel/cli```: É utilizada para o programador conseguir executar o babel atraves da linha de comando (caso queira testar, é possivel utilizar o comando ```yarn babel -h``` para abrir o menu de ajuda do babel no seu terminal **dentro do seu projeto, obviamente**)
- ```@babel/preset-env```: É uma biblioteca do babel que identifica qual ambiente a aplicação está sendo executada para converter o código da melhor maneira possivel.

> OBS.: Lembre-se de sempre que utilizar o babel criar o arquivo **babel.config.js** para que essa configuração realmente possa entrar em vigor.

###### 🧑‍💻 - Arquivo babel.config.js

Dentro do arquivo babel.config.js deve estar presente, pelo menos, o seguinte conteúdo:

~~~javascript
module.exports = {
    presets: [
        '@babel/preset-env'
    ]
};
~~~

Como explicado acima, o preset-env irá identificar em qual ambiente a nossa aplicação JavaScript está rodando e irá converter, da melhor forma possivel, o nosso código.

###### ❓ - É possivel converter algum código com babel para ver ele funcionando?

Sim! Isso é plenamente possivel, para converter um codigo JS com babel é possivel da seguinte maneira:

1. Crie um diretório *./src* em seu projeto, **caso ele não exista**;
2. Adicione um arquivo *index.js* (ou qualquer outro nome de sua preferencia) e salve-o;
3. Abra o terminal e digite o seguinte comando: ```yarn babel ./src/index.js --out-file dist/bundle.js```;
4. Seja feliz!

> Destrinchando o código de "compilação" do babel: o comando inicial, obviamente, chamando o babel: "yarn babel ..." e passando logo após isso o caminho do arquivo que você, programador, quer compilar, no meu caso "./src/index.js", o comando inteiro ficou, até o momento: "yarn babel ./src/index.js". Logo após isso, informeu a flag "--out-file", que poderia ser minimizada para -o, e em sequencia o diretório de onde quero guardar o arquivo compilado, passando também o seu futuro nome: "./dist/bundle.js", **bundle.js** é uma convenção utilizada entre os desenvolvedores para códigos que foram gerados a partir do babel, e **dist** está informando que é a pasta de distribuição, obviamente é so uma sigla do inglês. O codigo final é: "yarn babel ./src/index --out-file ./dist/bundle.js"

Caso você tenha o minimo de conhecimento em React, irá vir a seguinte pergunta em sua mente: *"Se eu posso transformar códigos JavaScript atuais para versões mais padronizados que o navegador possa entender, o que será que iria acontecer se eu simplesmente criasse um componente e pedisse para ele rodar?"*

E provavelmente você iria atualizar o arquivo index.js para algo mais ou menos assim:

~~~javascript
import React from "react";

const helloComponent = () => {
    return <>Hello world!<>
};
~~~

e quando você rodasse o comando: ```yarn babel ./src/index.js --out-file ./dist/bundle.js``` iria, exatamente, dar uma exception!

Kkkkkk, exatamente, uma exception, e é ai que sua mente buga: *"Se o babel serve para interpretar códigos javascript, atuais, em códigos javascript que todos os navegadores entender, porque eu não consigo "compilar" um código React, que é bastante atual, em um código que qualquer navegador entenda? **Propaganda enganosa?**"*

Ele até consegue fazer isso, porém, quando estavamos baixando todas as dependencias do babel não baixamos também uma dependencia para fazer com que ele compile codigos React.js, então ele irá tentar compilar com o preset-env padrão que baixamos e não irá ter sucesso. Para conseguir obter êxito na conversão de arquivos React com o babel, deve-se instalar o seguinte comando: ```yarn add @babel/preset-react -D```, não preciso explicar o que ele faz, certo?

> Para desencargo de consciencia: **yarn add** irá adicionar algum pacote em seu projeto, no nosso caso o pacote **@babel/preset-react** que servirá para compilar arquivos React e transformar-los em código *JavaScript* e a flag **-D** é para indicar, como já falado, que é uma dependencia de desenvolvimento.

Após instalar essa dependencia nova no projeto, se faz necessário informar, no arquivo **babel.config.js** que é para ele utilizar esse preset novo, então para isso, altere o arquivo **babel.config.js** para o abaixo:

~~~javascript
module.exports = {
    presets: [
        '@babel/preset-env',
        '@babel/preset-react'
    ]
};
~~~

E pronto! Ao tentar rodar o index.js ele já estará convertendo e retornando algo mais ou menos assim:

~~~javascript
"use strict";

var _react = _interopRequireDefault(require("react"));

function _interopRequireDefault(obj) { return obj && obj.__esModule ? obj : { "default": obj }; }

var app = function app() {
  return /*#__PURE__*/_react["default"].createElement(_react["default"].Fragment, null, "Hello world!");
};
~~~

**????????????????????????????????, Uma loucura do C@#$&ho!!!**
Não vá esperando que eu adicione o que esse código está fazendo linha por linha, eu só sei que no final irá aparecer o Hello World na tela igual fizemos no componente KKKK, porém, por mais que esse código fique bastante extenso tem coisas piores por vir!

<a name="webpack"></a>

##### 🌎📦 - Entendendo Webpack (Aula 03)

Dentro de sua aplicação, no código JavaScript, atualmente, você pode importar outros arquivos JS dentro dele, mas com React, ou em outras libs, você não irá importar somente arquivos JS, obviamente, você acaba tendo a necessidade de importar arquivos SCSS, CSS, Imagem (png, jpg, svg) e entre outros arquivos (qualquer tipo de arquivo literalmente), e o ***webpack*** vai basicamente definir algumas configurações, que chamamos de ***LOADERS***, que *vai ensinar a aplicação como ele deve tratar cada tipo de arquivo importado e ele irá pegar cada tipo desses arquivos e irá converter para um padrão que os browsers entendem*. **O webpack trabalha semelhantemente ao babel**.

> Resumidamente: O Babel e o webpack irão trabalhar em conjunto para fazer garantir que sua aplicação seja entendida por todos os navegadores!

###### 📁 - Instalação

Para instalar o ***webpack*** em seu projeto, deve-se rodar o seguinte comando: ```yarn add webpack webpack-cli babel-loader -D``` ou, caso esteja usando npm, deve-se utilizar: ```npm install webpack webpack-cli babel-loader -D```.

E assim como o babel, deve-se criar um arquivo, no root do projeto, com o nome: **webpack.config.js**

Dentro dele você irá definir algumas configurações obviamente, e no fim, ele irá ficar mais ou menos assim:

~~~ javascript
const path = require('path');

module.exports = {
    entry: path.resolve(__dirname, 'src', 'index.jsx'),
    output: {
        path: path.resolve(__dirname, 'dist'),
        filename: 'bundle.js'
    },
    resolve: {
        extensions: ['.js', '.jsx'],
    },
    module: {
        rules: [
            {
                test: /\.jsx$/,
                exclude: /node_modules/,
                use: 'babel-loader'
            }
        ],
    }
};
~~~

> Destrinchando o código: Na primeira linha ***se faz necessário importar o 'path' para que,*** a partir do seu sistema operacional, ***o JavaScript possa trabalhar com os diretorios da maneira correta.***

> Seguindo mais um pouco, exporto um modulo que de cara ***defino um entrypoint***, dentro desse entrypoint é necessiário informar qual é o arquivo inicial da aplicação, '__dirname' *(para informar que, é a partir do diretorio desse arquivo que ele deve acionar os proximos diretorios)*, 'src' *(para informar que deve entrar em src)* e 'index.jsx' *(para informar que esse é o arquivo procurado).*

> Abaixo dele tem a propriedade ***output***, que, como o nome ja diz, informa qual será o caminho e o nome do arquivo, quando ele for "compilado".

> Na sequencia temos o ***resolve*** que informamos dentro de *"extensions"* quais arquivos o webapp pode ler, por padrão é somente ".js", porém, vamos informar que ele pode ler também ".jsx" (ou um ou outro). 

> Depois deve-se informar um ***module***, e dentro dele nós configuramos justamente como a aplicação deve se comportar quando estiversos importando cada um dos tipos de arquivos citados anteriormente *(.css, .jpg, .scss, .svg e etc)*, definimos uma propriedade rules (um array de regras) e definimos um objeto, no código acima defino somente a regra para arquivos que terminam com ".jsx". Dentro da propriedade *"test"* definimos uma expressão regular (regex) para verificar se o arquivo é um arquivo javascript ou não, basicamente ele só ira verificar a extensão dele, o que vem depois do ".", exemplo: "blabla.img" não é javascript, porém, "blabla.jsx" é. Na linha seguinte, com o *exclude*, informo que **DEVE SER EXCLUIDO (ou ignorado) TODA A PASTA NODE MODULES** e logo após informo que ele deve usar o babel-loader (que é a integração do webpack co o babel), e ele basicamente faz o seguinte: Ao tentar importar um arquivo .jsx ele chama o babel-loader e converte esse arquivo ".jsx" para ".js" e joga la no .dist/bundle.js.

Para testar todas essas configs acima, você pode criar um arquivo: App.jsx dentro do diretório *./src* com qualquer código, o meu está assim:

~~~ javascript
import React from "react";

export function App() {
    return <h1>Hello world!</h1>
}
~~~

e dentro do index.jsx (o meu arquivo principal configurado no webpack) eu tenho:

~~~ javascript
import React from "react";
import { App } from "./App";
~~~

> Note que ao importar o arquivo App.jsx eu não preciso informar se ele é .jsx ou js, já que no arquivo ***webpack.config.js*** configuramos a propriedade ***resolve*** que já identifica, automaticamente, que o tipo desse arquivo *./App* é ".jsx"

ao rodar o comando: ```yarn webpack```, ou ```npm webpack``` *(ACREDITO QUE SEJA ESSE, POSSO ESTAR ERRADO)*, no terminal ele gerará a pasta ./dist com o arquivo index.jsx "compilado", dentro dele o código ficará assim:

~~~ javascript
/*! For license information please see bundle.js.LICENSE.txt */
(()=>{"use strict";var t={408:(t,e)=>{Symbol.for("react.element"),Symbol.for("react.portal"),Symbol.for("react.fragment"),Symbol.for("react.strict_mode"),Symbol.for("react.profiler"),Symbol.for("react.provider"),Symbol.for("react.context"),Symbol.for("react.forward_ref"),Symbol.for("react.suspense"),Symbol.for("react.memo"),Symbol.for("react.lazy"),Symbol.iterator;var o={isMounted:function(){return!1},enqueueForceUpdate:function(){},enqueueReplaceState:function(){},enqueueSetState:function(){}},r=Object.assign,a={};function n(t,e,r){this.props=t,this.context=e,this.refs=a,this.updater=r||o}function c(){}function p(t,e,r){this.props=t,this.context=e,this.refs=a,this.updater=r||o}n.prototype.isReactComponent={},n.prototype.setState=function(t,e){if("object"!=typeof t&&"function"!=typeof t&&null!=t)throw Error("setState(...): takes an object of state variables to update or a function which returns an object of state variables.");this.updater.enqueueSetState(this,t,e,"setState")},n.prototype.forceUpdate=function(t){this.updater.enqueueForceUpdate(this,t,"forceUpdate")},c.prototype=n.prototype;var s=p.prototype=new c;s.constructor=p,r(s,n.prototype),s.isPureReactComponent=!0;Array.isArray,Object.prototype.hasOwnProperty},294:(t,e,o)=>{o(408)}},e={};!function o(r){var a=e[r];if(void 0!==a)return a.exports;var n=e[r]={exports:{}};return t[r](n,n.exports,o),n.exports}(294)})();
~~~

**????????????????????????????????, Uma loucura do C@#$&ho novamente!!!**

Esse é simplesmente impossivel de saber o que está fazendo ASHUASHUA, porém, boas noticias, **o webpack já está funcionando e está integrado com o babel!**

> OBS.: O comando ```yarn webpack```, ou ```npm webpack```, pode gerar alguns alertas, parte desses alertas é por não ter definido um cenário para as configurações do webpack (no caso só existe duas possiveis, produção e desenvolvimento), mas, isso não é muito relevante e pode ser ignorado por agora.

##### <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/1150px-React-icon.svg.png" width="20px" height="auto"> - React.JS (Aula 04)

Bom, a partir desse momento já temos uma boa base sobre como funciona o Babel e como as aplicações web (no javascript) utilizam, conjuntamente, o babel e o webpack, podemos seguir para o React.JS em si.

React.JS é uma biblioteca baseada no JavaScript, acredito eu que é a mais produtiva que existe no mercado, com ela, o programador, tem uma curva de aprendizado muito grande, afinal, é uma *lib* muito boa e fácil de aprender, caso você já tenha uma certa baguagem com programação.

Na estrutura React, podemos perceber que tudo é trabalhado atraves de componentes, e que só existe somente 1 arquivo *.html* em todo projeto, que é o *index.html*, cujo está preenchido por:

~~~ html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <link rel="stylesheet" href="./scss/global.css">

    <title>Document</title>
</head>
<body>
    <div id="root"></div>
    <script src="../dist/bundle.js"></script>
</body>
</html>
~~~

> Destrinchando o código: Acima está o código html padrão de todas as aplicações React, obviamente tirando as partes que mudei que é o caso do import do meu *global.css* e a linguagem que coloquei *pt-BR*.

> É possivel notar a div que contém o id igual a ***root***, explicarei mais em breve como tudo funciona, porém, o que você deve saber até o momento é que: Nela irá estar contido todo os seus componentes, afinal, ela é a div principal da aplicação.

> Abaixo da div com id root tem o import do arquivo bundle.js, que na sessão de webpack (e na de babel também) explico um pouco mais sobre esse arquivo.

Agora você deve estar se perguntando, "Pô, se eu tenho uma div com id root, e você informou que dentro dessa div irá conter todo os meus componentes, logo é so eu usar o getElementById do javascript e pronto, não?"

Se você pensou isso, você está completamente correto! O React é JavaScript, logo, tudo que você faz no JavaScript você faz exatamente igual com ele, logo, se eu quero adicionar algo nessa div, algum componente, eu posso simplesmente fazer dessa seguinte maneira:

~~~ javascript
import React from "react";
import { render } from "react-dom";

/* Components */
import { App } from "./App";

render(<p>Hello world!</p>, document.getElementById("root"));
~~~

Você até pode passar aquele componente App que criamos anteriormente, porém, no lugar de: 

~~~ javascript
render(<p>Hello world!</p>, document.getElementById("root"));
~~~

você colocaria:

~~~ javascript
render(<App/>, document.getElementById("root"));
~~~

> OBS.: Por convenção é importante você sempre colocar o nome dos componentes em letra maiuscula para diferenciar os componentes dos elementos html

> Destrinchando o código: Se você parar para analisar o codigo acima, eu simplesmente estou usando o getElementById, do **DOM** (caso você não saiba o que é, recomendo dar uma pesquisada sobre ele, já que é a base do JavaScript), para renderizar o que eu quero, nesse caso é um Hello World!.

> OBS.: Para renderizarmos algo com React, deve-se obrigatóriamente importar o React e o método render, que vem la do react-dom (obviamente), na sessão de "Arquitetura do React" eu explico mais sobre ele, e usando esse método você deve passar dois parametros: o primeiro seria o que você deseja renderizar, e o segundo é onde você deseja renderizar, no meu caso, eu quero renderizar Hello World! na div com id root.

> Note também que estou importando o arquivo *bundle.js*, isso representa que eu preciso dar um ```yarn webpack``` para salvar as alterações que irão ser apresentadas no *HTML*.

Como dito anteriomente, em toda aplicação React você deve, obrigatóriamente, importar:

~~~ javascript
import React from "react";
~~~

porém, a uma forma de fazer com que, em tempo de compilação, o babel simplesmente faça isso para você, caso o React não esteja importado, para isso, você deve alterar o babel.config.js (falo mais sobre ele na sessão de babel) para o seguinte:

~~~ javascript
module.exports = {
    presets: [
        '@babel/preset-env',
        ['@babel/preset-react', {
            runtime: 'automatic'
        }]
    ]
};
~~~

> Destrinchando o código: Note que a única alteração realizada foi no preset-react, para passar alguma configuração para algum preset, definido no babel.config.js, você deve envolver esse preset entre chaves, adicionar uma virgula após a string e passar um objeto como "segundo parametro". Nesse caso, passo *runtime: 'automatic'*, que ele faz basicamente o que tinha dito acima, caso você não importou o React em seu componente, ele importa para você sem nenhum problema.

Agora, por fim, como sempre acabaremos utilizando o webpack, e as vezes ele pode ser demorado demais, podemos definir uma configuração dentro do webpack.config.js (explico mais sobre ele na sessão de webpack) para tornar a compilação mais rápida, no caso podemos adicionar: ```mode: 'development'```, no arquivo ficaria mais ou menos assim:

~~~ javascript
const path = require('path');

module.exports = {
    mode: 'development',
    entry: path.resolve(__dirname, 'src', 'index.jsx'),
    output: {
        path: path.resolve(__dirname, 'dist'),
        filename: 'bundle.js'
    },
    resolve: {
        extensions: ['.js', '.jsx'],
    },
    module: {
        rules: [
            {
                test: /\.jsx$/,
                exclude: /node_modules/,
                use: 'babel-loader'
            }
        ],
    }
};
~~~

esse modo só funciona em cenário de desenvolvimento e ele basicamente evita de fazer algumas configurações nos arquivos do *./dist* para compilar consideravelmente mais rápido, o efeito colateral mais visivel é que, ele não otimiza o código gerado, por exemplo. Enfim, nada a se preocupar por agora.

###### 🔨 - Melhorando o arquivo estático (index.html)

Caso você tenha notádo, no index.html estamos referenciando o arquivo bundle da aplicação de forma *hard code*, porém, se por um motivo do além nos mudassemos esse arquivo, o nome dele, a aplicação pararia de funcionar, para tornar isso mais seguro, previnir um erro desse, existe um plugin do webpack que injeta esse arquivo compilado no nosso HTML para que nós não precisemos nós preocupar com isso.

Para baixar esse plugin, devemos rodar o seguinte comando: ```yarn add html-webpack-plugin```, caso use npm acredito que seja: ```npm install html-webpack-plugin```.

e para configurar ele é muito simples, deve-se importar esse plugin, dentro do arquivo webpack.config.js, da seguinte maneira:

~~~ javascript
const HtmlWebpackPlugin = require('html-webpack-plugin');
~~~

e na sequencia informar o template padrão para essa configuração do webpack (lembrando que esse webpack é o que transformar o nosso index.jsx em bundle.js então ele meio que sabe que tu quer adicionar o bundle dentro do template informado), dessa seguinte maneira:

~~~ javascript
plugins: [
        new HtmlWebpackPlugin({template: path.resolve(__dirname, 'public', 'index.html')
    })
]
~~~

o que irá resultar em um arquivo webpack.config.js mais ou menos assim:

~~~ javascript
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
    mode: 'development',
    entry: path.resolve(__dirname, 'src', 'index.jsx'),
    output: {
        path: path.resolve(__dirname, 'dist'),
        filename: 'bundle.js'
    },
    resolve: {
        extensions: ['.js', '.jsx'],
    },
    plugins: [
        new HtmlWebpackPlugin({
            template: path.resolve(__dirname, 'public', 'index.html')
        })
    ],
    module: {
        rules: [
            {
                test: /\.jsx$/,
                exclude: /node_modules/,
                use: 'babel-loader'
            }
        ],
    }
};
~~~

e quando tu der novamente um ```yarn webpack``` ele irá gerar um index.html dentro da pasta *./dist* que, dentro dele, conterá justamente o arquivo bundle.js como um passe de mágica!

**CLEAN DEMAIS 👌!!!** 

> OBS.: Quando for abrir o index.html, abra o da pasta ./dist e não o da pasta ./public


###### 🔄 - Adicionando o dev server (para auto-reload)

Caso você tenha notado, a cada alteração do nosso projeto devemos rodar o ```yarn webpack``` para recarregar o arquivo bundle.js e ai sim ser adicionado, no index.html (do diretório ./dist), as novas alterações. Para tornar isso mais prático, podemos adicionar o ***webpack-dev-server***, que irá funcionar igual ao ***DevTools*** do Spring. Ele irá ficar monitorando a sua aplicação e quando você, como programador, alterar algo, em seu código fonte, o webpack já irá recarregar automaticamente, perfeito demais se ta doido!

Para isso, deve-se instalar o dev-server, com o seguinte comando: ```yarn add webpack-dev-server -D```, caso esteja no npm acredito eu que seja: ```npm install webpack-dev-server -D```, e ele irá fazer justamente o que falei acima, recarregar sua aplicação automaticamente, quando tiver uma alteração em cenário de desenvolvimento.

Para configurar ele, deve-se adicionar a seguinte instrução, dentro do webpack.config.js:

~~~ javascript
devServer: {
    static: path.resolve(__dirname, 'public')
} 
~~~

deixando arquivo webpack.config.js mais ou menos assim:

~~~ javascript
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
    mode: 'development',
    entry: path.resolve(__dirname, 'src', 'index.jsx'),
    output: {
        path: path.resolve(__dirname, 'dist'),
        filename: 'bundle.js'
    },
    resolve: {
        extensions: ['.js', '.jsx'],
    },
    devServer: {
        static: path.resolve(__dirname, 'public')
    },
    plugins: [
        new HtmlWebpackPlugin({
            template: path.resolve(__dirname, 'public', 'index.html')
        })
    ],
    module: {
        rules: [
            {
                test: /\.jsx$/,
                exclude: /node_modules/,
                use: 'babel-loader'
            }
        ],
    }
};
~~~

Referente ao código de configuração, ele basicamente irá informar aonde que fica a pasta do arquivo index.html da nossa aplicação.

Ao rodar o comando ```yarn webpack serve``` o dev-server já deve estar funcionando, para saber se funcionou, rode o seguinte comando e abra o navegador na porta: localhost:8080 (geralmente aparece essa mesma porta na primeira linha após tu rodar o comando webpack serve).

###### 🗺️ - Configurando o source-map

O Source map basicamente é uma forma da gente, como programador, conseguir visualizar o código original da aplicação, mesmo quando todo o código da aplicação está embaralhado por conta do bundle.js.

Caso sua aplicação retorne um erro, da maneira que está hoje, e tu for verificar, pelo navegador, onde está dando erro, ele irá aparecer de uma forma muito enconveniente, exemplo: no componente abaixo adicionei um erro, proposital, de forma estática

~~~ javascript
export default function App() {
    throw new Error('Ops!!!')
    return <h1>Hello world!</h1>
}
~~~

vendo o código fonte é muito nitido que o erro está na linha 2, logo, é so remover-lo que o erro irá sair, porém, se nós abrirmos o console, ele irá informar o seguinte:

![Alt text](image.png)

Informou que aconteceu um erro na linha 2 do arquivo App.jsx (essa linha geralmente diverge), e ao dar um clique em *App.jsx:2* ele deveria retornar o código exatamente como o abaixo

~~~ javascript
export default function App() {
    throw new Error('Ops!!!')
    return <h1>Hello world!</h1>
}
~~~

afinal, é o que contem nele, certo? Errado, ele irá retornar:

~~~ javascript
__webpack_require__.r(__webpack_exports__);
/* harmony export */ __webpack_require__.d(__webpack_exports__, {
/* harmony export */   "default": () => (/* binding */ App)
/* harmony export */ });
/* harmony import */ var react_jsx_runtime__WEBPACK_IMPORTED_MODULE_0__ = __webpack_require__(/*! react/jsx-runtime */ "./node_modules/react/jsx-runtime.js");

function App() {
  throw new Error('Ops!!!');
  return /*#__PURE__*/(0,react_jsx_runtime__WEBPACK_IMPORTED_MODULE_0__.jsx)("h1", {
    children: "Hello world!"
  });
}//# sourceURL=[module]
//# sourceMappingURL=data:application/json;charset=utf-8;base64,eyJ2ZXJzaW9uIjozLCJmaWxlIjoiLi9zcmMvQXBwLmpzeCIsIm1hcHBpbmdzIjoiOzs7Ozs7QUFBZSxTQUFTQSxHQUFHQSxDQUFBLEVBQUc7RUFDMUIsTUFBTSxJQUFJQyxLQUFLLENBQUMsUUFBUSxDQUFDO0VBQ3pCLG9CQUFPQyxzREFBQTtJQUFBQyxRQUFBLEVBQUk7RUFBWSxDQUFJLENBQUM7QUFDaEMiLCJzb3VyY2VzIjpbIndlYnBhY2s6Ly8wMS1naXRodWItZXhwbG9yZXIvLi9zcmMvQXBwLmpzeD8xNTkxIl0sInNvdXJjZXNDb250ZW50IjpbImV4cG9ydCBkZWZhdWx0IGZ1bmN0aW9uIEFwcCgpIHtcbiAgICB0aHJvdyBuZXcgRXJyb3IoJ09wcyEhIScpXG4gICAgcmV0dXJuIDxoMT5IZWxsbyB3b3JsZCE8L2gxPlxufVxuIl0sIm5hbWVzIjpbIkFwcCIsIkVycm9yIiwiX2pzeCIsImNoaWxkcmVuIl0sInNvdXJjZVJvb3QiOiIifQ==
//# sourceURL=webpack-internal:///./src/App.jsx
~~~

Isso acontece porque o código foi compilado pelo webpack e, obviamente, esse código acima é o código que ele gerou a partir da nossa aplicação. Para isso que adicionamos o source map, para podermos visualizar o código da nossa aplicação da forma que ele realmente é.

Para configurar o source map deve-se adicionar a seguinte instrução dentro do webpack.config.js:

~~~ javascript
devtool: 'eval-source-map',
~~~

O que resultará em um webpack.config.js mais ou menos assim:

~~~ javascript
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
    mode: 'development',
    devtool: 'eval-source-map',
    entry: path.resolve(__dirname, 'src', 'index.jsx'),
    output: {
        path: path.resolve(__dirname, 'dist'),
        filename: 'bundle.js'
    },
    resolve: {
        extensions: ['.js', '.jsx'],
    },
    devServer: {
        static: path.resolve(__dirname, 'public')
    },
    plugins: [
        new HtmlWebpackPlugin({
            template: path.resolve(__dirname, 'public', 'index.html')
        })
    ],
    module: {
        rules: [
            {
                test: /\.jsx$/,
                exclude: /node_modules/,
                use: 'babel-loader'
            }
        ],
    }
};
~~~

e ao rodar novamente o código, sem alterar o erro, ao verificar novamente o arquivo, irá aparecer da seguinte forma:

![Alt text](image-1.png)

Exatamente igual ao componente do projeto!!!

###### 🏭 - Ambiente de Desenvolvimento e Produção

Nessa sessão iremos configurar os ambientes da nossa aplicação, porque, caso seja de desenvolvimento ela irá se comportar de uma forma e se for produção se comportará de outra forma.

Dentro do arquivo webpack.config.js deve-se conter a seguinte instrução:

~~~ javascript
const isDevelopment = process.env.NODE_ENV !== 'production';
~~~

e atualizar os campos ```mode``` e ```devtool``` deixando eles da seguinte maneira:

~~~ javascript
mode: isDevelopment ? 'development' : 'production',
devtool: isDevelopment ? 'eval-source-map' : 'source-map',
~~~

deixando o arquivo webpack.config.js mais ou menos assim:

~~~ javascript
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

const isDevelopment = process.env.NODE_ENV !== 'production';

module.exports = {
    mode: isDevelopment ? 'development' : 'production',
    devtool: isDevelopment ? 'eval-source-map' : 'source-map',
    entry: path.resolve(__dirname, 'src', 'index.jsx'),
    output: {
        path: path.resolve(__dirname, 'dist'),
        filename: 'bundle.js'
    },
    resolve: {
        extensions: ['.js', '.jsx'],
    },
    devServer: {
        static: path.resolve(__dirname, 'public')
    },
    plugins: [
        new HtmlWebpackPlugin({
            template: path.resolve(__dirname, 'public', 'index.html')
        })
    ],
    module: {
        rules: [
            {
                test: /\.jsx$/,
                exclude: /node_modules/,
                use: 'babel-loader'
            }
        ],
    }
};
~~~

Porém, se notarmos bem, a variavel *isDevelopment* está puxando uma configuração presente dentro do .env da nossa aplicação, porém, não existe nenhum .env na aplicação, então, devemos criar ele da seguinte maneira:

Caso esteja em um ambiente unix (linux e mac) so de dar o seguinte comando: ```NODE_ENV=production``` e concatenar com o comando ```yarn webpack``` se tornando assim: ```NODE_ENV=production yarn webpack``` ele já funcionará acionando o modo de produção em sua aplicação, já no windows é diferente.

Geralmente quando tu roda o comando acima ele gera um ***bundle.js.map***, em desenvolvimento ele já omite esse arquivo.

Para padronizar a aplicação, iremos baixar a dependencia cross-env. Para baixar essa dependencia deve-se rodar o seguinte comando: ```yarn add cross-env -D```, ou: ```npm install cross-env -D```.

Esse cross-env serve para você, como programador, definir variáveis de ambiente independente do sistema operacional da pessoa.

Vá até o *package.json* e adicione alguns scripts bases para o projeto (semelhantemente aos do nodemon), eles devem ficar da seguinte maneira:

~~~ json
"scripts": {
    "dev": "webpack serve",
    "build": "cross-env NODE_ENV=production webpack"
}
~~~

onde, quando você der o comando ```yarn run dev``` ele irá executar exatamente os scripts que estão ao lado, ou seja: ```webpack serve``` que irá executar, como contrapartida, o ***webpack-dev-server***.

O arquivo package.json ficará basicamente assim:

~~~ json
{
  "name": "01-github-explorer",
  "version": "1.0.0-SNAPSHOT",
  "description": "Start of trail \"ignite\".",
  "main": "index.js",
  "author": "Matheus Ferreira Santos",
  "license": "MIT",
  "scripts": {
    "dev": "webpack serve",
    "build": "cross-env NODE_ENV=production webpack"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "@babel/cli": "^7.22.10",
    "@babel/core": "^7.22.11",
    "@babel/preset-env": "^7.22.10",
    "@babel/preset-react": "^7.22.5",
    "babel-loader": "^9.1.3",
    "cross-env": "^7.0.3",
    "html-webpack-plugin": "^5.5.3",
    "webpack": "^5.88.2",
    "webpack-cli": "^5.1.4",
    "webpack-dev-server": "^4.15.1"
  }
}
~~~

> Destrinchando o código: o código ```cross-env NODE_ENV=production webpack``` utiliza o cross-env para criar uma variável *NODE_ENV* que conterá como valor: *production*, executa o webpack (apenas para compilar todo o código gerado) e gerar uma versão de produção do seu sistema, mamão com açúcar!

[Voltar para a sessão de navegação.](#navegação)

##### ❓ - Informações
> Nome: Matheus Ferreira Santos.
> Trilha: RocketSeat Ignite - Trilha REACT JS.
> Data Inicial: Quinta-Feira, 24 de agosto de 2023. 