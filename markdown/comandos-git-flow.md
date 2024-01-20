# Git Flow

[Trabalhando em equipe com Git Flow](https://www.youtube.com/watch?v=394mc6PV8t8&t=1s)

## Comandos que foram apresentados na vídeo aula

### Iniciando controle para projeto em equipe
```
git flow init
```

#### Após iniciar oGit Floe, seu repositório de trabalho será o develop

## Criando uma feature (nova branch) a partir da develop

### Criando feature
```
git flow feature start nome_feature
```

### Subindo feature para origin
```
git push origin feature/nome_feature
```

### Finalizando feature
```
git flow feature finish nome_feature
```

### iniciando release 
```
git flow release start 1.0
```

### finalizando release
```
git flow release finish 1.0
```

### verificando versões 
```
git tag
```

### pequenas aletrações na versãoa atual
```
git flow hotfix start 1.1
```

### aleterações finalizadas
```
git flow hotfix finish 1.1
```

### fazendo push em todas as branchs 
```
git push --all 
```
