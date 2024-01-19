# Commits Semânticos 

Conteúdo completo você encontra na pagina através do link, ou nesta mesma página logo abaixo do resumo inicial que contém apenas parte do conteúdo.

Commit semântico é uma prática de versionamento de código que incentiva o desenvolvedor a escrever mensagens de commit significativas e descritivas.

Ao escrever mensagens de commit semânticas, o desenvolvedor deve incluir informações detalhadas sobre o que foi alterado, por que foi alterado e como foi alterado.

Estas mensagens de commit também devem ser curtas e diretas, para que outros desenvolvedores possam entender rapidamente o que foi alterado. 

## Benefícios

1. Maior clareza e transparência: Mensagens de commit semânticas fornecem informações detalhadas sobre o que foi alterado, por que foi alterado e como foi alterado. Isso ajuda outros desenvolvedores a entender rapidamente o que foi alterado e por quê.

2. Maior facilidade de manutenção: Mensagens de commit semânticas fornecem informações detalhadas sobre o que foi alterado, o que torna mais fácil para outros desenvolvedores localizar e corrigir problemas.

3. Maior produtividade: Mensagens de commit semânticas ajudam a economizar tempo, pois outros desenvolvedores não precisam gastar tempo tentando entender o que foi alterado.

## Tipo e Descrição

O commit semântico possui os elementos estruturais abaixo (tipos), que informam a intenção do seu commit ao utilizador(a) de seu código.
```
    feat- Commits do tipo feat indicam que seu trecho de código está incluindo um novo recurso (se relaciona com o MINOR do versionamento semântico).

    fix - Commits do tipo fix indicam que seu trecho de código commitado está solucionando um problema (bug fix), (se relaciona com o PATCH do versionamento semântico).

    docs - Commits do tipo docs indicam que houveram mudanças na documentação, como por exemplo no Readme do seu repositório. (Não inclui alterações em código).

    test - Commits do tipo test são utilizados quando são realizadas alterações em testes, seja criando, alterando ou excluindo testes unitários. (Não inclui alterações em código)

    build - Commits do tipo build são utilizados quando são realizadas modificações em arquivos de build e dependências.

    perf - Commits do tipo perf servem para identificar quaisquer alterações de código que estejam relacionadas a performance.

    style - Commits do tipo style indicam que houveram alterações referentes a formatações de código, semicolons, trailing spaces, lint... (Não inclui alterações em código).

    refactor - Commits do tipo refactor referem-se a mudanças devido a refatorações que não alterem sua funcionalidade, como por exemplo, uma alteração no formato como é processada determinada parte da tela, mas que manteve a mesma funcionalidade, ou melhorias de performance devido a um code review.

    chore - Commits do tipo chore indicam atualizações de tarefas de build, configurações de administrador, pacotes... como por exemplo adicionar um pacote no gitignore. (Não inclui alterações em código)

    ci - Commits do tipo ci indicam mudanças relacionadas a integração contínua (continuous integration).
```
