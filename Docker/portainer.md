# Gerenciando o Portainer

### Baixar a imagem
```
docker pull portainer/portainer
```

### Criar um container
Flags:</br>
-d = rodar em background</br>
-p = mapeamento das portas (porta local:porta container)</br>
--name = nome do container</br>
--restart = habilita o reinício do container automaticamente</br>
-v /var/run/docker.sock:/var/run/docker.sock = permite gerenciar um ambiente Docker local</br>
-v = volume especificando o diretório de saída do sistema operacional</br>
```
docker run -d -p 9000:9000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v C:\docker\portainer\data:/data portainer/portainer
```
