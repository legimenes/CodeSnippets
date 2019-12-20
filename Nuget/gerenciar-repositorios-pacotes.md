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

<h2>Criar um pacote através do nuget</h2>
Gerar um build de release e dentro da pasta onde se encontra o csproj criar o pacote:

```
nuget pack -Properties Configuration=Release
```

<h2>Criar um pacote através do cli</h2>
Manter pelo menos as principais propriedades do projeto preenchidas para gerar o arquivo nuspec. Exemplo de nuspec:

```
<?xml version="1.0" encoding="utf-8"?>
<package xmlns="http://schemas.microsoft.com/packaging/2013/05/nuspec.xsd">
  <metadata>
    <id>LGG.Framework.ADO</id>
    <version>1.0.0</version>
    <authors>Leandro</authors>
    <owners>LGG</owners>
    <requireLicenseAcceptance>false</requireLicenseAcceptance>
    <description>LGG framework</description>
    <dependencies>
      <group targetFramework=".NETStandard2.1">
        <dependency id="LGG.Framework.OtherLibrary" version="1.0.0" exclude="Build,Analyzers" />
      </group>
    </dependencies>
  </metadata>
</package>
```

Gerar um build de release e dentro da pasta onde se encontra o csproj criar o pacote:

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