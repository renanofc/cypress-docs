# Instalando Cypress

```markdown
O que você vai aprender

- Como instalar Cypress usando `npm`
- Como versionar e rodar Cypress usando `package.json`
```

## Requisitos de sistema

### Sistema Operacional


- macOS 10.9 e superior (somente 64-bit)
- Linux Ubuntu 12.04 e superior, Fedora 21 e Debian 8 (somente 64-bit)
- Windows 7 e superior

### Node.js

Se você está utilizando `npm` para instalar o Cypress, nós suportamos:

- **Node.js** 12 ou 14 e superior

### Linux

Se você estiver usando Linux, você precisará das dependências necessárias
instaladas no seu sistema.


#### Ubuntu/Debian

```bash
apt-get install libgtk2.0-0 libgtk-3-0 libgbm-dev libnotify-dev libgconf-2-4 libnss3 libxss1 libasound2 libxtst6 xauth xvfb
```

#### CentOS

```bash
yum install -y xorg-x11-server-Xvfb gtk2-devel gtk3-devel libnotify-devel GConf2 nss libXScrnSaver alsa-lib
```

## Instalando

### `npm install`

Instale o Cypress usando `npm`:

```shell
cd /caminho/do/projeto
```

```shell
npm install cypress --save-dev
```

Isto vai instalar o Cypress localmente como uma dependência de desenvolvimento em seu projeto.

> Certifique-se que você já rodou `npm init`, ou tenha o diretório
`node_modules`, ou o arquivo `package.json` no diretório raiz do seu projeto
para garantir que o cypress seja instalado no diretório correto.

[Vídeo de exemplo.](https://docs.cypress.io/img/snippets/installing-cli.mp4)



### `yarn add`

Instalando o cypress usando o `yarn`:

```bash
cd /caminho/do/projeto
yarn add cypress --dev
```

## Abrindo o Cypress

Se você usou `npm` para instalação, o Cypress foi instalado
no diretório `./node_modules`, com seus binários executáveis accessíveis
em `./node_modules/.bin`.

Agora você pode abrir o Cypress do seu projeto principal de uma
das seguintes formas:

A forma longa com o caminho completo

```bash
./node_modules/.bin/cypress open
```

Ou com o atalho usando `npm bin`

```bash
$(npm bin)/cypress open
```

Ou usando o `npx`

Obs.: o [npx](https://www.npmjs.com/package/npx) é incluido no npm > v5.2,
ou pode ser instalado separadamente.

```bash
npx cypress open
```

Após um momento, o Cypress Test Runner será aberto.

## Trocando navegadores

O Cypress Test Runner tenta encontrar todos os navegadores compatíveis na
máquina do usuário. O campo de seleção suspenso para selecionar um navegador
diferente pode ser encontrado no topo lateral direito do Test Runner.

[//]: <> (TODO - Adicionar link abrindo navegadores)

Leia [Abrindo navegadores](https://docs.cypress.io/guides/guides/launching-browsers.html) para mais informações
sobre como o Cypress controla um navegador real durante os testes
de ponta-a-ponta.

> Suporte entre navegadores

[//]: <> (TODO - Adicionar link entre navegadores)

> O Cypress atualmente suporta o Firefox e navegadores da família Chrome
(incluindo Edge e Electron). Para executar testes de maneira otimizada
nesses navegadores na integração contínua, confira as estratégias
demonstradas no [guia de teste entre navegadores](https://docs.cypress.io/guides/guides/cross-browser-testing.html).

## Adicionando scripts npm

Embora não haja nada de errado em escrever o caminho completo para o
executável do Cypress a cada momento, é muito mais fácil e claro adicionar
os comandos do Cypress ao campo de scripts em seu arquivo `package.json`.

```json
{
  "scripts": {
    "cypress:open": "cypress open"
  }
}
```

Agora você pode chamar o comando a partir da raiz do projeto, dessa forma:

```bash
npm run cypress:open
```

… e o Cypress irá abrir direto para você.
