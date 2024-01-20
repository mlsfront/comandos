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

### Criar a migration acrescentar a coluna nomeColuna
```
npx sequelize-cli migration:generate --name alter-nomeTabela-add-nomeColuna
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

## Adicionando Dados Inicais para Tabelas

### Criar seeders
```
npx sequelize-cli seed:generate --name demo-nomeSeed
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

