<h1>Procedimentos para fazer backup e restore (Windows)</h1>

Abrir o prompt de comando como administrador, navegar até a pasta bin onde está instalado o Postgre.

<h2>Backup</h2>

```
pg_dump.exe –h {NOME_SERVIDOR} –p {PORTA} –U {USUARIO} –F t –f {PATH_DESTINO}
```

<h2>Restore</h2>

```
pg_dump.exe –h {NOME_SERVIDOR} –p 5432 –U {USUARIO} –F t –f {PATH_DESTINO}
pg_restore.exe –h {NOME_SERVIDOR} –p {PORTA} –U {USUARIO} -d {NOME_DATABASE} {PATH_DESTINO}
```
