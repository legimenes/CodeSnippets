<h1>Linhas de comando no IIS</h1>

<h2>Diretório para executar os comandos</h2>

```
cd %systemroot%\system32\inetsrv
```

<h3>Criar Appication Pool</h3>

```
appcmd add apppool /name:{APLICATIONPOOL_NAME} /managedRuntimeVersion:{VERSION} /managedPipelineMode:{Basic|Integrated}
```

Exemplo:
```
appcmd add apppool /name:PoolSite1 /managedRuntimeVersion:v4.0 /managedPipelineMode:Integrated
```

<h3>Deletar Application Pool</h3>

```
appcmd delete apppool {APLICATIONPOOL_NAME}
```

<h3>Criar Website</h3>

```
appcmd add site /name:{WEBSITE_NAME} /physicalPath:{SITE_PATH} /bindings:{PROTOCOL_PORT}
```

Exemplo:
```
appcmd add site /name:site1 /physicalPath: c:\site1 /bindings:http/*:85:
```

<h3>Alterar Application Pool do Website criado</h3>

```
appcmd set app {WEBSITE_NAME}/ /applicationPool:{APLICATIONPOOL_NAME}
```

Exemplo:
```
appcmd set app site1/ /applicationPool:PoolSite1
```

<h3>Criar Aplicação Virtual dentro do Website</h3>

```
appcmd add app /site.name:{WEBSITE_NAME} /path:/{VIRTUALAPPLICATION_NAME} /physicalPath:C:\BitBiz\TMS
```

Exemplo:
```
appcmd add app /site.name:site1 /path:/sitecliente1 /physicalPath:c:\sitecliente1
```

<h3>Alterar o Application Pool da Aplicação Virtual criada</h3>

```
appcmd set app {WEBSITE_NAME}/{VIRTUALAPPLICATION_NAME} /applicationPool:{APLICATIONPOOL_NAME}
```

Exemplo:
```
appcmd set app cliente1/tmscliente1 /applicationPool:PoolCliente1
```
