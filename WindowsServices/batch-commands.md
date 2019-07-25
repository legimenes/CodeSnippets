<h1> Batch commands para gerenciar windows services </h1>

```
// Forçar o encerramento de um serviço
taskkill /pid {PID_NUMBER} /f

// Mostrar os serviços executados no momento
sc queryex {SERVICE_NAME}
```
