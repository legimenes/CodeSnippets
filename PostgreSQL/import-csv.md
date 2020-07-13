<h1>Importação de csv</h1>

```
COPY {TABELA}[campos]
FROM {'path'} DELIMITER {'DELIMITER'} CSV HEADER;
```

Exemplo

```
COPY public.users(name, email)
FROM 'C:/temp/users.csv' DELIMITER ';' CSV HEADER;
```
