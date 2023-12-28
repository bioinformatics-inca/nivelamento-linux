# Donos, grupos e outros usuários

O princípio da segurança no sistema de arquivos GNU/Linux é definir o acesso aos arquivos por donos, grupos e outros usuários:
- dono
  -  É a pessoa que criou o arquivo ou o diretório. Somente o dono pode modificar as permissões de acesso do arquivo.
  -  Um usuário é definido pelo seu UID (user ID).
- grupo
  - Cada usuário pode fazer parte de um ou mais grupos e acessar arquivos que pertençam ao mesmo grupo que o seu (mesmo que estes arquivos tenham outro dono).
  - Cada grupo é definido no sistema pelo seu GID (group ID).
- outros
  - É a categoria de usuários que não são donos ou não pertencem ao grupo do arquivo.
    
~~~
$  groups
$  id
~~~

## Criando grupos e adicionando usuários

- Verificando UID, GID e grupos
~~~
$  id
$  groups  aluno
~~~

- Criando usuarios com UID específico
~~~
$  sudo  adduser  --uid 1015  aluno15
~~~

- Criando grupo e adicionando usuários
~~~
$  sudo  addgroup  --gid 3001  alunos
Adding group `alunos' (GID 3001) ...

$  sudo  adduser  aluno15  alunos
~~~

- Listando usuários
~~~
$  getent  passwd 
aluno:x:1000:1000:Aluno,,,:/home/aluno:/bin/bash
diego:x:1001:1001:Diego,,,:/home/diego:/bin/bash
dentz:x:1002:1002:Dentz,,,:/home/dentz:/bin/bash
~~~

- Listando grupos
~~~
$  getent  group
aluno:x:1000:
sambashare:x:124:aluno,diego,dentz
diego:x:1001:
dentz:x:1002:
alunos:x:3001:aluno,aluno15

$  id  aluno
uid=1000(aluno) gid=1000(aluno) groups=1000(aluno),4(adm),
24(cdrom),27(sudo),30(dip),46(plugdev),109(lpadmin),124(sambashare),3001(alunos)
~~~



## comando ``getent passwd``
~~~
$  getent passwd  #(lê arquivo /etc/passwd)
diego:x:1001:1001:Diego,,,:/home/diego:/bin/bash
~~~

- Cada campo é separado pelo caracter ``:``
  - ``diego`` – Nome de Login do usuário
  - ``x`` – Indica que a senha do usuário está localizada no arquivo /etc/shadow
  - ``1001`` – UID do usuário
  - ``1001`` – GID do usuário
  - ``Diego,,,`` – Informações do usuário, tais como Nome, Telefone. Observe que neste exemplo algumas informações não foram preenchidas.
  - ``/home/diego`` – Diretório HOME do usuário. 
  - ``/bin/bash`` – Shell do usuário, ou seja, o programa que irá enterpretar os comandos que o usuário executar.

(Adaptado de: http://www.profissionaisti.com.br/2011/09/usuarios-e-grupos-no-linux/ )

