# Escrevendo o Primeiro Teste


[Vídeo de exemplo.](https://www.youtube.com/watch?v=F8nRh4bGAfY)

## Adicione um arquivo de teste

Assumindo que você tenha [instalado](installing-cypress.md#instalando) e 
[aberto](installing-cypress.md#abrindo-o-cypress) o Cypress Test Runner, 
chegou a hora de escrever o primeiro teste. Vamos então:

1. Criar um arquivo `exemplo.spec.js` para versões mais antigas e para mais atuais `exemplo.cy.js`.
2. Checar que o Cypress atualizou a lista de arquivos de teste.
3. Executar o Cypress Test Runner.

Vamos criar um novo arquivo na pasta `cypress/integration` para versões mais antigas e para mais atuais `cypress/e2e`, a qual já foi criada:



Uma vez que o arquivo tenha sido criado, o Cypress Test Runner deve exibi-lo na lista de testes 
de integração. O Cypress monitora mudanças em seus arquivos de teste e os exibe imediatamente.

Mesmo que ainda não tenha escrito nenhum teste - tudo bem - clique em `exemplo_spec.js` ou `exemplo.cy.js` e veja o 
Cypress iniciar o navegador.

> O Cypress abre o teste em um navegador previamente instalado em seu sistema operacional.



[//]: <> (TODO - Adicionar link Test Runner quando for traduzido)
Agora estamos oficialmente no 
[Test Runner](https://docs.cypress.io/guides/core-concepts/test-runner.html). 
É nele onde vamos gastar a maioria do tempo testando.

> Note que o Cypress exibe a mensagem que não pode encontrar nenhum teste. 
Isso é normal - testes ainda não foram escritos! Você verá essa mensagem também caso exista algum
 erro ao analisar os arquivos de teste. Você pode abrir o Dev Tools para inspecionar o console e 
 buscar por erros de sintaxe que impediu o Cypress de ler seus arquivos de testes.

## Escreva seu primeiro teste

Chegou a hora de escrever o nosso primeiro teste. Vamos então:

1. Escrever nosso primeiro teste com sucesso.
2. Escrever nosso primeiro teste com falha.
3. Ver o Cypress recarregar o teste em tempo real.

A medida que salvamos nosso novo teste, veremos que o navegador recarrega automaticamente em tempo 
real.

Abra sua IDE favorita e adicione o código abaixo no arquivo de teste `exemplo.spec.js` ou `exemplo.cy.js`.

```javascript
describe('Meu primeiro teste', () => {
  it('Meu primeiro teste...', () => {
    expect(true).to.equal(true)
  })
})
```

Quando salvar esse arquivo você deve ver o navegador recarregar.

Embora não faça nada, esse é nosso primeiro teste com sucesso!


### Agora vamos escrever nosso primeiro teste com falha.

```javascript
describe('Meu primeiro teste', () => {
  it('Meu primeiro teste...', () => {
    expect(true).to.equal(false)
  })
})
```

Quando você salvar, poderá observar que o Cypress exibe o teste com falha em vermelho, uma vez 
que `true` não é igual a `false`.


## Escreva um teste real


### Passo 1: Visitar uma página web


Podemos passar a URL que queremos visitar para o `cy.visit()`. Vamos substituir nosso teste 
anterior pelo teste abaixo que de fato visita uma página:

```javascript
describe('Meu primeiro teste', () => {
  it('Visitar site de exemplo do Cypress', () => {
    cy.visit('https://example.cypress.io')
  })
})
```

Salve o arquivo e retorne ao Cypress Test Runner. Você vai perceber algumas coisas:

[//]: <> (TODO - Adicionar Command Log e Pré visualização links)

1. O Log de Comandos
agora exibe a nova ação `visit`.
2. A aplicação de exemplo foi carregada no painel de 
pré visualização da aplicação.
3. O teste está verde.

### Passo 2: Consultar um elemento

Agora que temos a página web carregada, precisamos fazer algo nela. Porque não clicamos em um link?
Parece ser fácil, vamos ver qual deles gostamos... que tal `type`?

Para encontrar esse elemento pelo seu conteúdo, usamos `cy.contains()`.

Vamos adicionar isso em nosso teste e ver o que acontece:

```javascript
describe('Meu primeiro teste', () => {
    it('Visitar site de exemplo do Cypress', () => {
    cy.visit('https://example.cypress.io')

    cy.contains('type')
  })
})
```

Agora o teste deve exibir o comando `CONTAINS` e ainda estar verde.

[//]: <> (TODO - Adicionar link Default Assertions quando for traduzido)
Mesmo sem adicionar um assert, sabemos que está tudo certo! Isso acontece pois muitos dos comandos
do Cypress são construídos para falhar caso não encontram o que é esperado.

Para confirmar, substitua `type` por qualquer palavra que não esteja na página, como `exemplo`.
Perceba que o teste falha.

### Passo 3: Clicar em um elemento

Ok, agora queremos clicar no link que encontramos. Como fazer isso? Adicione o comando `.click()`
no final do comando anterior, como abaixo:

```javascript
describe('Meu primeiro teste', () => {
    it('Visitar site de exemplo do Cypress', () => {
    cy.visit('https://example.cypress.io')

    cy.contains('type').click()
  })
})
```

#### Adicionando mais comandos e asserts


[//]: <> (TODO - Adicionar link cy.get, .type e .should quando traduzidos)

Podemos usar [`cy.get()`](https://docs.cypress.io/api/commands/get.html)
para selecionar um elemento baseado em uma classe CSS.Então, podemos usar o comando
[`.type()`](https://docs.cypress.io/api/commands/type.html)
para inserir texto no campo de entrada de texto selecionado. Por fim, podemos verificar que o valor
do campo de entrada de texto reflete o texto que foi digitado com outro
[`.should()`](https://docs.cypress.io/api/commands/should.html).

```javascript
describe('Meu primeiro teste', () => {
  it('Gets, types and asserts', () => {
    cy.visit('https://example.cypress.io')

    cy.contains('type').click()

    // Should be on a new URL which includes '/commands/actions'
    cy.url().should('include', '/commands/actions')

    // Get an input, type into it and verify that the value has been updated
    cy.get('.action-email')
      .type('fake@email.com')
      .should('have.value', 'fake@email.com')
  })
})
```

E aí está: um breve teste no Cypress que visita uma página, encontra e clica em um link, verifica a URL e,
em seguida, verifica o comportamento de um elemento na nova página.