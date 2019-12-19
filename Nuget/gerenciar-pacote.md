<h1>Gerenciamento de pacote nuget</h1>

<h2>Criar um pacote</h2>
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
nuget pack -Properties Configuration=Release
```

<h2>Publicar o pacote em um repositório local</h2>

```
nuget add NomeDoPacote.1.0.0.nupkg -source c:\repo\nuget\
```

<h2>Remover o pacote de um repositório local</h2>

```
nuget delete NomeDoPacote 1.0.0 -source c:\repo\nuget\
```
