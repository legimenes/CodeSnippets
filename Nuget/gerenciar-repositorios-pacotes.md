<h1>Gerenciamento de repositórios e pacotes nuget</h1>

<h2>Listar os repositórios configurados</h2>

```
nuget sources
```

<h2>Criar um repositório local</h2>

```
nuget sources add -name {NOME_REPOSITORIO} -Source {PATH_REPOSITORIO}
```

<h2>Remover um repositório local</h2>

```
nuget sources remove -name {NOME_REPOSITORIO}
```

<h2>Criar um pacote através do cli</h2>
Manter pelo menos as principais propriedades do projeto preenchidas para gerar o arquivo nuspec. Exemplo de nuspec:

```
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
    <AssemblyVersion>1.0.0.0</AssemblyVersion>
    <Authors>Leandro</Authors>
    <Company>LGG</Company>
    <Description>Data access component.</Description>
    <FileVersion>1.0.0.0</FileVersion>
    <PackageId>LGG.Framework.ADO</PackageId>
    <Product>LGG.Framework.ADO</Product>
    <Version>1.0.0</Version>
  </PropertyGroup>

</Project>
```

Empacotar em release:

```
dotnet pack --configuration Release
```

<h2>Publicar o pacote em um repositório local</h2>

```
nuget add {NOME_PACOTE.0.0.0.nupkg} -source {PATH_REPOSITORIO}
```

<h2>Remover o pacote de um repositório local</h2>

```
nuget delete {NOME_PACOTE} {NUMERO_VERSAO} -source {PATH_REPOSITORIO}
```

<h2>Adicionar referência de um pacote de repositório local através do cli</h2>

```
dotnet add package {NOME_PACOTE} [--version {NUMERO_VERSAO}] -s {PATH_REPOSITORIO}
```

<h2>Remover referência de um pacote de repositório local através do cli</h2>

```
dotnet remove package {NOME_PACOTE}
```
