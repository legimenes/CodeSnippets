<h2>Linhas de comando do .NET CLI (Interface de linha de comando) do .NET Core</h2>

<b>Criar solution</b><br>
dotnet new sln --name {NOME_SOLUTION}

<b>Criar projeto class library</b><br>
dotnet new classlib --name {NOME_PROJETO} [-f {netcoreapp2.0|netcoreapp2.1}|netstandard2.0]

<b>Adicionar referência de um projeto dentro de outro</b><br>
dotnet add {NOME_PROJETO} reference {NOME_PROJETO_REFERENCIADO}

<b>Adicionar projeto à solution</b><br>
dotnet sln add .\{DIRETORIO_PROJETO}\{NOME_PROJETO}.csproj

<b>Adicionar pacote do nuget</b><br>
<i>Ir para a pasta do projeto desejado</i>
dotnet add package {NOME_PACOTE} [--version={NUMERO_VERSAO}]

<b>Build da solution</b><br>
dotnet build {NOME_SOULUTION}.sln
