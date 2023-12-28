# Permissões de acesso a arquivos e diretórios

- A permissão de acesso protege o sistema de arquivos Linux do acesso indevido de pessoas ou programas não autorizados.

- A permissão de acesso do GNU/Linux também impede que um programa mal intencionado, por exemplo, apague um arquivo que não deve, envie arquivos para outra pessoa ou forneça acesso da rede para que outros usuários invadam o sistema.

(Fonte: http://pt.wikibooks.org/wiki/Guia_do_Linux/)


.

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


.


## modificar a permissão dos arquivos e diretórios

- atribuindo permissões por código alfabético

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


