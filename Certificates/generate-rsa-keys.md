# Gerar chaves RSA

Executar openssl

### Gerar chave privada
```
genpkey -algorithm RSA -out private_key.pem -pkeyopt rsa_keygen_bits:2048
```

### Gerar chave pública
```
rsa -pubout -in private_key.pem -out public_key.pem
```
