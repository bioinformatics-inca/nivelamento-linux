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


