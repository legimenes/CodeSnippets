# Git commands

### Clonando um repositório do Github
1) Criar o repositório no Github
2) Selecionar "Clone or Download" no Github e copiar o link do repositório 
- se o repositorio for público, copiar o HTTPS
- se o repositorio for privado, copiar o SSH e aplicar os passos para gerar a chave SSH
3) No prompt de comando, ir para a pasta raíz dos projetos (vai ser criada uma pasta com o nome do projeto no Github)
```
git clone {URL from repository}
```

### Branches
#### Criar branch
```
git checkout -b {branch_name}
```
Obs.: Esse comando é um atalho para:
```
git branch {branch_name}
git checkout {branch_name}
```

### Mudar de branch
```
git checkout {branch_name}
```

### Remover branch
```
git branch -d {branch_name}
```
Obs.: Fetch para remover referências não usadas
```
git fetch --prune
```

### Publicar uma branch remotamente
```
git push -u origin {branch_name}
```

### Merge de branches
Mudar para a branch que vai receber o merge
```
git merge {branch_name}
```

### Exibir status da branch de trabalho
```
git status
```

### Fazendo commit e pull
```
git add .
git commit -m "commit description"
git pull {URL from repository}
```
