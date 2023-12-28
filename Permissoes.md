# Permissões de acesso a arquivos e diretórios

- A permissão de acesso protege o sistema de arquivos Linux do acesso indevido de pessoas ou programas não autorizados.

- A permissão de acesso do GNU/Linux também impede que um programa mal intencionado, por exemplo, apague um arquivo que não deve, envie arquivos para outra pessoa ou forneça acesso da rede para que outros usuários invadam o sistema.
(http://pt.wikibooks.org/wiki/Guia_do_Linux/)


## Donos, grupos e outros usuários

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

### Criando grupos e adicionando usuários

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



### comando ``getent passwd``
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



## Permissões


- representação
~~~
    - | rw- | r-- | r--
__________________________
 tipo |  u  |  g  |  o   
~~~

- tipo de objeto (arq. comum -, diretório d, link simbólico l)
  - u – permissões do dono do arquivo (user)
  - g – permissões do grupo
  - o – permissões dos outros

~~~
$  ls  -l
drwxr-xr-x  2 nicole nicole  4096 2011-06-20 14:10 Desktop
drwxr-xr-x 13 nicole nicole  4096 2011-06-20 14:10 Documents
drwxr-xr-x  4 nicole nicole  4096 2011-06-29 10:37 Downloads
-rw-r--r--  1 nicole nicole   179 2011-02-22 14:10 examples.desktop
~~~

- Tipo de arquivo – ``d, l, -``
- Permissões
  - Permissão de leitura – ``r``
  - Permissão de escrita – ``w``   (escrita/alteração/remoção)
  - Permissão de execução – ``x`` 



### modificar a permissão dos arquivos e diretórios

~~~
$  mkdir  Exemplos      ### criar diretório
$  ls -l
$  chmod  g+w  Exemplos
$  ls -l
~~~
                                       x    	permissão de execução
                                       w      	permissão de gravação
                                       r       	permissão de leitura
                                       rwx   	soma de todas as permissões



- valores numéricos (base binária)
  - x – execução de arquivos/acesso a diretórios  -->  1
  - w – (write) criação/alteração/deleção         -->  2
  - r – (read) leitura de arquivos diretórios     -->  4
  - \- – nada                                     -->  0


- modificar a permissão dos arquivos e diretórios com códigos numéricos
~~~
$  chmod  774  Exemplos
~~~


                                       0  (zero) permissão negada
                                       1   permissão de execução
                                       2   permissão de gravação
                                       3   permissão de gravação e execução
                                       4   permissão de leitura
                                       5   permissão de leitura e execução
                                       6   permissão de leitura e gravação
                                       7   soma de todas as permissões


