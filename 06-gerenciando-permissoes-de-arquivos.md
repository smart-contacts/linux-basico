<p align="center">
  <a href="https://smartcontacts.com.br/">
    <img alt="Smart Contacts" src="https://smartcontacts.com.br/assets/img/logo.png" width="200" />
  </a>
</p>
<h2 align="center">
Informação sobre tecnologia, dicas, tutoriais, mini-cursos e muito mais.
</h2>

## Videoaula no Youtube

[Link do Vídeo no Youtube](https://youtu.be/In_SFGwZdGY)

## Gerenciamento de Permissões de Arquivos e Diretórios

O gerenciamento de permissões permite ao administrador do sistema definir políticas para acesso dos usuários e grupos aos arquivos, diretórios e programas executáveis do sistema.

O princípio da segurança no sistema de arquivos GNU/Linux é definir o acesso aos arquivos por **donos**, **grupos** e **outros** usuários:

**dono** - É a pessoa que criou o arquivo ou o diretório. Somente o dono pode modificar as permissões de acesso do arquivo. As permissões de acesso do dono de um arquivo somente se aplicam ao dono do arquivo/diretório. A identificação do dono também é chamada de user id (UID).

> A identificação de usuário e o nome do grupo que pertence são armazenadas respectivamente nos arquivos ```/etc/passwd``` e ```/etc/group```.

**grupo** - Para permitir que vários usuários diferentes tenham acesso a um mesmo arquivo. Cada usuário pode fazer parte de um ou mais grupos e então acessar arquivos que pertençam ao mesmo grupo que o seu (mesmo que estes arquivos tenham outro dono). Por padrão, quando um novo usuário é criado, o grupo que ele pertencerá será o seu grupo primário. A identificação do grupo é chamada de group id (GID).

**outros** - É a categoria de usuários que não são donos ou não pertencem ao grupo do arquivo. Cada um dos tipos acima possuem três tipos básicos de permissões de acesso que serão vistas adiante.

#### Permissões básicas:

**r** - Permissão de leitura para arquivos. Caso for um diretório, permite listar seu conteúdo (através do comando ls, por exemplo).

**w** - Permissão de gravação para arquivos. Caso for um diretório, permite a gravação de arquivos ou outros diretórios dentro dele. Para que um arquivo/diretório possa ser apagado, é necessário o acesso a gravação.

**x** - Permite executar um arquivo (caso seja um programa executável). Caso seja um diretório, permite que seja acessado através do comando cd.

> Para visualizar as permissões de arquivos e diretórios use o comando ```ls -l```.

Normalmente utilizamos a tabela abaixo para definirmos as permissões:

4 - leitura

2 - gravação

1 - execução

![Definições de permissões](https://smartcontacts.com.br/assets/img/permissoes.png)

#### Permissões Especiais:

As permissões de arquivos e diretórios são gravadas de forma binária com 12 bits de tamanho.

![Definições de permissões](https://smartcontacts.com.br/assets/img/permissoes_especiais.png)

As permissões especiais estão representadas pelos três primeiros bits, onde cada um desses três bits tem uma função específica. Veja abaixo:

**1o bit – Set User ID (SUID)** – afeta somente os arquivos executáveis. O SUID faz com que o programa rode sempre com as permissões do usuário dono, independente de qual usuário esteja executando. (Normalmente programas rodam com as permissões do usuário que o chamou).

**2o bit – Set Group ID (SGID)** – Análogo ao SUID. Ele faz com os programas rodem sob as permissões do grupo do dono do arquivo.

**3o bit – Sticky** – O bit especial faz com que os programas permaneçam na memória mesmo depois de terminados, fazendo com que rodem mais rapidamente em uma próxima chamada. Este bit quando aplicado em diretórios faz com que somente o dono do diretório, o dono do arquivo ou o root possam renomear ou apagar arquivos neste diretório.

Os bits de permissões especiais são representados pela letra “s” no lugar da letra “x” para os bits SUID e SGID nas classes de dono e grupo, e pela letra “t” no lugar da letra “x” para o bit Sticky na classe de outros.

Executando o comando ```ls -l```, teremos uma lista de arquivos, com a exibição de todo o esquema de permissões. Temos as permissões exibidas nos dez caracteres exibidos na primeira coluna da saída do comando. O primeiro caracter representa o tipo de arquivo. As nove posições seguintes representam as chaves de permissão. Os principais tipos de arquivos são:

**- (traço)** - Arquivos comuns.

**d** - Diretórios/pastas.

**l** - Links simbólicos.

**c** - Dispositivos de caracteres.

**b** - Dispositivos de blocos.

**s** - Soquetes.

#### chmod

Comando utilizado para alterar as permissões de um arquivo/diretório. O chmod também aceita a representação das  permissões através de letras, conforme mostrado abaixo:

**u** - Refere-se as permissões para o dono.

**g** - Refere-se as permissões para o grupo.

**o** - Refere-se as permissões para o outros.

**a** - Refere-se as permissões para todos os usuários.

O sinal “+” indica adição de permissão às permissões já existentes.

O sinal “–” indica remoção de permissão das permissões já existentes.

O sinal “=” indica substituição das permissões existentes pelas indicadas após o sinal.

Exemplos:

```
# chmod 755 aula05.txt
Altera as permissões do arquivo aula05.txt para rwx para o dono, r-x para o grupo do dono e r-x para outros.

# chmod 4755 /sbin/mkfs.ntfs
Dando permissão de SUID bit ao programa mkfs.ntfs.

# chmod u=rwx,go=rx aula05.txt
O mesmo que o primeiro exemplo.

# chmod g+w aula05.txt
Adiciona a gravação para o grupo do dono.
```

#### chown

Muda o dono de um arquivo/diretório. Opcionalmente pode também ser usado para mudar o grupo. Sintaxe:

```
chown -[opções] [dono.grupo] [diretório/arquivo]
```

opção:

**R** - Muda o dono de todos os arquivos e diretórios recursivamente dentro da hieraquia.

Exemplos:

```
# chown torvalds.desenv aula05.txt
Altera o dono do arquivo para torvalds e o grupo para desenv.

# chown antonio leiame.txt
Altera o dono do arquivo.

# chown .pesquisa aula05.txt
Altera somente o grupo do arquivo para o grupo pesquisa.
```

#### chgrp

Utilizado para mudar apenas o grupo de um arquivo/diretório. Sintaxe:

```
chgrp -[opções] [grupo] [diretório/arquivo]
```

opção:

**R** - Muda o grupo de todos os arquivos e diretórios recursivamente dentro da hieraquia.

Exemplo:

```
# chgrp -R desenv /home/torvalds
Altera recursivamente o grupo de todos os arquivos e diretórios dentro de /home/torvalds.
```

### Chegamos ao fim deste post

Se você tiver algo mais que possa agregar ao exposto, deixe seu comentário, será muito bem vindo!

Obrigado pela leitura.


### Links úteis:

[Canal no YouTube](https://www.youtube.com/channel/UCC6ue986efLUHRuqGiIfuwQ/featured?view_as=public)

[Instagram](https://www.instagram.com/smartcontacts/)

[Twitter](https://twitter.com/@ContactsSmart)

[GNU](http://www.gnu.org)

[Linux Ubuntu](https://ubuntu.com/)

[Docker](https://docs.docker.com/)
