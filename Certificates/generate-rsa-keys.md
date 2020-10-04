# Gerar chaves RSA

### Gerar chave privada
```
openssl genpkey -algorithm RSA -out private_key.pem -pkeyopt rsa_keygen_bits:2048
```

### Gerar chave pública
```
openssl rsa -pubout -in private_key.pem -out public_key.pem
```
