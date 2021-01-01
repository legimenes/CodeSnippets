# Comandos o Docker

### Exibir detalhes do Docker
```
docker info
```

### Listar todas as imagens
```
docker images -a
```

### Listar todos os containers
```
docker ps -a
```

### Exibir informações detalhadas de uma imagem específica
```
docker image inpect {image_name}
```

### Remover imagens, contêineres, volumes, e redes que estão pendentes (não associados a um contêiner)
Flags:
-a = remove adicionalmente quaisquer contêineres e todas as imagens não utilizadas (não apenas imagens pendentes)
```
docker system prune [-a]
```

### Remover uma imagem específica
```
docker image rm {image_name}
```

### Remover imagens pendentes (camadas que não têm relação com nenhuma imagem marcada)
```
docker images purge
```

