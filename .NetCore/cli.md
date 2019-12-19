<h1>Linhas de comando do .NET CLI (Interface de linha de comando) do .NET Core</h1>

```
//Instalar dotnet-ef
dotnet tool install --global dotnet-ef

//Criar solution
dotnet new sln --name {NOME_SOLUTION}

//Criar projeto class library
dotnet new classlib --name {NOME_PROJETO} [-f {netcoreapp2.0|netcoreapp2.1|netcoreapp2.2|netcoreapp3.0}|{netstandard2.0|netstandard2.1}]

//Criar projeto mstest
dotnet new mstest --name {NOME_PROJETO} [-f {netcoreapp2.0|netcoreapp2.1|netcoreapp2.2|netcoreapp3.0}]

//Adicionar referência de um projeto dentro de outro
dotnet add {NOME_PROJETO} reference {NOME_PROJETO_REFERENCIADO}

//Adicionar projeto à solution
dotnet sln add .\{DIRETORIO_PROJETO}\{NOME_PROJETO}.csproj

//Adicionar pacote do nuget
//Ir para a pasta do projeto desejado
dotnet add package {NOME_PACOTE} [--version={NUMERO_VERSAO}]

//Limpar projeto
dotnet clean

//Build
dotnet build [{NOME_SOULUTION.sln|NOME_PROJETO.csproj}] [--configuration Release]

//Publicação
dotnet publish [--configuration Release]
```
