# Acesso remoto a outros computadores

## Protocolo SSH
- Secure Shell é um protocolo de rede criptográfico para operação de serviços de rede de forma segura sobre uma rede insegura.

~~~
$  ssh usuario@IPservidor
$  ssh aluno@labinfo-01
~~~

### preparando o seu computador para ser acessado
- qual seu IP?
- instalando o openssh-server
  - precisa ter privilégios de administrador (sudo)
  - Obs.:  sudo == super user do

~~~
$  ifconfig
$  apt show openssh-server
$  sudo apt install openssh-server
~~~


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


