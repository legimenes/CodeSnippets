# Comandos para o Entity Framework Core

### Atualizar ferramenta
```
dotnet tool update --global dotnet-ef
```

### Criar migração
```
dotnet ef migrations add {migration_name} [-o {/Data/Migrations}] [--verbose]
```

### Atualizar banco de dados
```
dotnet ef database update [--verbose]
```
### Remover ultima migração
```
dotnet ef migrations remove [--verbose]
```
