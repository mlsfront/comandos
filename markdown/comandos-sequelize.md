## Configurando Inicial

### Sequelize é uma biblioteca Javascript que facilita o gerenciamento do banco de dados SQL
```
npm install --save sequelize
```

### Instalar o drive do banco de dados "no projeto foi usado mysql2"
```
npm install --save mysql2
```

### Sequelize-cli interface de linha de comando usada para criar modelos, configurações e arquivos de migração para bancos de dados
```
npm install --save-dev sequelize-cli
```

### Iniciar o Sequelize-cli e criar o arquivo config
```
npx sequelize-cli init
```

### Manipular variáveis de ambiente
```
npm install dotenv --save
```

### Criar o arquivo de configuracao [.sequelizerc](https://sequelize.org/docs/v6/other-topics/migrations/#the-sequelizerc-file) para indicar o cominho dos arquivos e diretorios.
```
.sequelizerc
```

* Usando o arquivo de configuração `.sequelizerc` ao criar models, migrations, ou seeders, elas serão salvas em seus devidos repositórios

## Criando e Alterando Tabelas

### Criar a migration da página home do conteúdo do nomeTabela 
```
npx sequelize-cli migration:generate --name create-nomeTabela
```

Modelo Migration:
```
'use strict';

/** @type {import('sequelize-cli').Migration} */

// Exportar o obejeto como modulo
module.exports = {
 // Criando a tabela 'Clientes'
 async up(queryInterface, Sequelize) {
  await queryInterface.createTable('Clientes', {
   id: {
    allowNull: false,
    autoIncrement: true,
    primaryKey: true,
    type: Sequelize.INTEGER
   },
   nome: {
    type: Sequelize.STRING
   },
   email: {
    type: Sequelize.STRING
   },
   contato: {
    type: Sequelize.STRING
   },
   createdAt: {
    allowNull: false,
    type: Sequelize.DATE
   },
   updatedAt: {
    allowNull: false,
    type: Sequelize.DATE
   }
  });
 },

 // Executar down - rollback - Permite que seja desfeita a migration, permitindo a gestão das alterações do banco de dados e versionamento.
 async down(queryInterface, Sequelize) {
  await queryInterface.dropTable('Clientes');
 }
}; 
```

### Criar a migration acrescentar a coluna nomeColuna
```
npx sequelize-cli migration:generate --name alter-nomeTabela-add-nomeColuna
```

Modelo Alteração Migration:
```

'use strict';

/** @type {import('sequelize-cli').Migration} */
module.exports = {
 async up (queryInterface, Sequelize) {
  await queryInterface.addColumn('Clientes', 'sobrenome', {
   type: Sequelize. DataTypes.STRING, after: "nome"
  });
 },

 async down (queryInterface, Sequelize) {
  await queryInterface.removeColumn('Clientes'), ('sobrenome');
 }
};
```

## Subundo as tabelas para o Banco de Dados

### Executar as migrations
```
npx sequelize-cli db:migrate
```

### Executar down - rollback - Permite que seja desfeita a migration, permitindo a gestão das alterações do banco de dados e versionamento.
```
npx sequelize-cli db:migrate:undo --name nome-da-migration.js
```

### Criar a Models da página do seu conteúdo
```
npx sequelize-cli model:generate --name nomeModels --attributes primeiroConteudo:string,segundoConteudo:string,terceiroConteudo:text,quartoConteudo:integer, quintoConteudo:float
```

Modelo de Models
```
'use strict';

// Incluir as bibliotecas
// Criar a constante para receber a MODEL do Sequelize para usar como herança na classe
const { Model } = require('sequelize');

// Exportar a função como modulo
module.exports = (sequelize, DataTypes) => {
 // Criar a classe com o nome da tabela herdando a 'Model' importada acima
 class Clientes extends Model {
  /**
   * Helper method for defining associations.
   * This method is not a part of Sequelize lifecycle.
   * The `models/index` file will call this method automatically.
   */
  static associate(models) {
  // define association here
  }
 }
 
 // Criala as colunas que a `Models` pode manipular
 Clientes.init({
  nome: DataTypes.STRING,
  email: DataTypes.STRING,
  sobrenome: DataTypes.STRING,
  contato: DataTypes.STRING
 }, {
  sequelize,
  modelName: 'Clientes',
 });

 // Retornar a classe `Clientes`
 return Clientes;
}; 
```

## Adicionando Dados Inicais para Tabelas

### Criar seeders
```
npx sequelize-cli seed:generate --name demo-nomeSeed
```

Modelo Seed:
```
'use strict';

/** @type {import('sequelize-cli').Migration} */

// Exportar o objeto como modulo
module.exports = {
 :// Cadastrar o registro na tabela "Clientes"
 :async up (queryInterface) {
  return queryInterface.bulkInsert ('Clientes', [
   {
    nome: 'Web App',
    sobrenome: "Agendamento",
    email: 'alunos@orange.com',
    contato: '7198542-4286',
    createdAt: new Date(),
    updatedAt: new Date(),
   },
   {
    nome: 'Atendimento',
    sobrenome: "WebApp",
    email: 'orange@discord.com',
    contato: '7197823-4876',
    createdAt: new Date(),
    updatedAt: new Date(),
   },
  ])
 :},

 :// Limpar os registros da tebela 'Clientes'
 :async down (queryInterface) {
  await queryInterface.bulkDelete ('Clientes', null, {});
 :}
}; 
```

### Executar as seeders
```
npx sequelize-cli db:seed:all
```

### Executar uma seed
```
npx sequelize-cli db:seed --seed nomeSeed.js
```

### Executar down - rollback - Permite que seja desfeita todas as seed, permitindo a gestão das alterações do banco de dados e versionamento.
```
npx sequelize-cli db:seed:undo
```

### Executar down - rollback - Permite que seja desfeita uma única seed, permitindo a gestão das alterações do banco de dados e versionamento.
```
npx sequelize-cli db:seed:undo --seed nomeSeed.js
```

