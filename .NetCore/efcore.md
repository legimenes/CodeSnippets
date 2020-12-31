# Comandos para o Entity Framework Core

### Atualizar ferramenta
```
dotnet tool update --global dotnet-ef
```

### Criar migração
```
dotnet ef migrations add {migration_name} [-o {/Data/Migrations}]
```

### Atualizar banco de dados
```
dotnet ef database update
```
### Remover ultima migração
```
dotnet ef migrations remove
```
