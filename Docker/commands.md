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

### Criar um container
Flags:</br>
-d = rodar em background (sem esperar comandos no prompt)
-it = modo interativo (aguarda interação)
```
docker run [-d|-it] --name {container_name} {image_name}
```

### Inicializar um container específico
```
docker start {container_name}
```

### Exibir a data de um container específico
```
docker exec -it {container_id} date
```

### Executar o shell de um container que possua o recurso
```
docker run -it {container_id} sh
```

### Remover imagens, containeres, volumes, e redes que estão pendentes (não associados a um container)
Flags:</br>
-a = remove adicionalmente quaisquer containeres e todas as imagens não utilizadas (não apenas imagens pendentes)
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

### Remover um container específico
```
docker container rm {container_id}
```

