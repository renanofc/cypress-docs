# Por que Cypress?

```markdown
O que você vai aprender

- O que é o Cypress e porque você deveria usá-lo
- Nossa missão e no que acreditamos
- Funcionalidades-chave do Cypress
```

[![Cypress em poucas palavras](http://img.youtube.com/vi/LcGHiFnBh3Y/0.jpg)](http://www.youtube.com/watch?v=LcGHiFnBh3Y")

## Em poucas palavras

O Cypress é uma ferramenta de teste de front end de última geração, criada para
a web moderna. Abordamos os principais pontos problemáticos que desenvolvedores
e engenheiros de QA enfrentam ao testar aplicações modernas.


O Cypress é mais frequentemente comparado ao Selenium; no entanto, o Cypress
é fundamentalmente e arquiteturalmente diferente. O Cypress não é restringido
pelas mesmas restrições que o Selenium.

Isso permite que você escreva testes **mais rápidos**, **fáceis**
e **confiáveis**.

## Quem usa o Cypress?

Nossos usuários normalmente são desenvolvedores ou engenheiros de QA que criam
aplicações web usando modernos frameworks JavaScript.

O Cypress permite que você escreva todos os tipos de testes:

- Testes end to end (ou testes de ponta-a-ponta)
- Testes de integração
- Testes de unidade

O Cypress pode testar tudo que é executado em um navegador.

## O ecossistema do Cypress

O Cypress consiste de um Test Runner (executor de testes) grátis, [open source](https://github.com/cypress-io/cypress),
[instalado localmente](../getting-started/installing-cypress.md) **e** um painel como serviço, 
para gravar seus testes.

- ***Primeiro:*** O Cypress torna fácil configurar e começar a escrever testes
todos os dias enquanto você cria sua aplicação localmente. *TDD no seu melhor!*
- ***Então:*** Depois de criar um conjunto de testes e integrar o Cypress ao
seu provedor de integração contínua (CI), nosso Painel como serviço pode gravar
suas execuções de teste. 
Você nunca terá que se perguntar: *por que isso falhou?*

## Funcionalidades

O Cypress vem totalmente pronto, com tudo que você precisa. Aqui está uma lista 
de coisas que ele pode fazer que nenhum outro framework de teste pode:

[//]: <> (TODO - Adicionar link log de comandos)

- **Viagem no tempo:** O Cypress tira *snapshots* enquanto seus testes 
são executados. Basta passar o mouse sobre os comandos no [log de comandos](https://docs.cypress.io/guides/core-concepts/test-runner.html#Command-Log)
para ver exatamente o que aconteceu em cada etapa.

[//]: <> (TODO - Adicionar link depure diretamente)

- **Depuração:** Pare de adivinhar por que seus testes estão falhando. 
[Depure diretamente](https://docs.cypress.io/guides/overview/why-cypress.html#Features) através de
ferramentas familiares como o Chrome DevTools. 
Nossos erros legíveis e *stack trace* tornam a depuração rápida.

[//]: <> (TODO - Adicionar link espera automaticamente)

- **Espera automatica:** Nunca adicione esperas ou sleeps aos seus testes. 
O Cypress [espera automaticamente](https://docs.cypress.io/guides/core-concepts/introduction-to-cypress.html#Cypress-is-Not-Like-jQuery)
por comandos e asserções antes de prosseguir. Chega de *async hell*.

[//]: <> (TODO - Adicionar link controle o comportamento)

- **Spies, Stubs, e Clocks:** Verifique e
[controle o comportamento](https://docs.cypress.io/guides/guides/stubs-spies-and-clocks.html) de funções,
respostas do servidor ou timers. A mesma funcionalidade que você adora no teste
de unidade está na ponta dos seus dedos.

[//]: <> (TODO - Adicionar link edge cases)

- **Controle de tráfego de rede:** Facilmente [controle, limite e teste 
*edge cases*](https://docs.cypress.io/guides/guides/network-requests.html)
sem envolver seu servidor. Você pode limitar o tráfego de rede como quiser.

- **Resultados consistentes:** Nossa arquitetura não usa o Selenium ou 
o WebDriver. Diga olá aos testes rápidos, consistentes e confiáveis que
são *flaky free* (livres de "fraquesas").

- **Screenshots e vídeos:** Veja capturas de tela tiradas automaticamente
em caso de falha ou vídeos de todo o seu conjunto de testes quando executado
a partir da interfáce de linha de comando.

- **Suporte entre navegadores:** Rode testes no Firefox e navegadores da família Chrome
(incluindo Edge e Electron) localmente e otimizado na *pipeline* de integração contínua.