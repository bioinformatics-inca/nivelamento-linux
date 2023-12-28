# Transferencia de arquivos entre computadores

## rsync
- Sincronização de arquivos remotos e locais
- Vantagem: apenas os arquivos diferentes são transferidos

~~~
rsync (opções) origem destino
rsync -av /tmp/backups/ ~/Documents/backups/
rsync -r aluno@algprog:~/Downloads/curso .
rsync --dry-run /tmp/bla.txt aluno@algprog:~/
~~~

## SCP
- É o comando cp por SSH. Segue a sintaxe do cp
- Pode copiar arquivos do seu computador local para uma máquina remota, da remota para o local, e de remota para outra remota.

~~~
scp (opções) origem destino
scp bla.txt user@IPservidor:/tmp/
scp -r aluno@algprog:~/Downloads/curso .
scp user@IPservidor:/tmp/bla.txt aluno@algprog:~/
~~~


