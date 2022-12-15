# Configurando o Allure no Cypress

```markdown
Requisitos: 

- Java 8 (necessário para executar o Allure)
- Node instalado
```

```markdown
Usando NPM:

npm i -D @shelex/cypress-allure-plugin
npm install -g allure-commandline --save-dev
```

# Configurar
• (Antes do Cypress 10) Coloque o código abaixo na pasta index.js caminho: `cypress/plugins/index.js` Leve em consideração que o Cypress gera o arquivo de plugins module.exportsna primeira inicialização, sendo assim você pode inserir abaixo do mesmo.

```markdown
const allureWriter = require('@shelex/cypress-allure-plugin/writer');
// import allureWriter from "@shelex/cypress-allure-plugin/writer";

module.exports = (on, config) => {
allureWriter(on, config);
return config;
};
```

• (Depois do Cypress 10) Use `defineConfig` e `setupNodeEvents` dentro dos arquivos config.js\config.ts:

```markdown
const allureWriter = require('@shelex/cypress-allure-plugin/writer');
// import allureWriter from "@shelex/cypress-allure-plugin/writer";

module.exports = defineConfig({
    e2e: {
        setupNodeEvents(on, config) {
            allureWriter(on, config);
            return config;
        }
    }
});

```

• Coloque os import no arquivo `cypress/support/index.js` (ou `cypress/support/e2e.js` para Cypress 10+):

• Com import
```markdown
import '@shelex/cypress-allure-plugin';
```

• Com require
```markdown
require('@shelex/cypress-allure-plugin');
```

# Execução

```markdown
npx cypress run --config video=false --env allure=true
allure generate allure-results
allure open allure-report

```

