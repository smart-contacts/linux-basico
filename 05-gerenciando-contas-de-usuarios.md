<p align="center">
  <a href="https://smartcontacts.com.br/">
    <img alt="Smart Contacts" src="https://smartcontacts.com.br/assets/img/logo.png" width="200" />
  </a>
</p>
<h2 align="center">
Informação sobre tecnologia, dicas, tutoriais, mini-cursos e muito mais.
</h2>

## Videoaula no Youtube

[Link do Vídeo no Youtube](https://youtu.be/rSKeRvrqWEE)

## Comandos para gerenciamento de usuários e grupos

### Administração de Usuários e Grupos

Em sistemas multiusuário, é necessário existir mecanismos para proteger os usuários, de forma que seus arquivos privativos fiquem seguros, inacessíveis aos outros. Outro aspecto é em relação aos recursos do sistema reservados: não deve ser possível a um usuário criar arquivos que ocupem todo o espaço do disco, por exemplo, e assim, indiretamente, proibir todos os outros usuários de salvarem seus próprios arquivos.

Atingimos esse objetivo criando contas, que representam todos os recursos e informações pertencentes a um determinado usuário. A cada usuário é destinado um nome de login, senha, UID, GID, nome do diretório home e shell inicial.

Um grupo é um conjunto de usuários. Cada grupo possui uma identificação única no sistema, um nome e um número. Por padrão, quando criamos um usuário no sistema, automaticamente é criado um novo grupo com o mesmo nome do usuário, do qual ele é o único membro.

Os dados do usuário são colocados no arquivo /etc/passwd após sua criação e os dados do grupo são colocados no arquivo /etc/group.

Caso esteja usando senhas ocultas (shadow passwords), as senhas dos usuários serão colocadas no arquivo /etc/shadow e as senhas dos grupos no arquivo /etc/gshadow. Isto aumenta mais a segurança do sistema porque somente o usuário root pode ter acesso a estes arquivos, ao contrário do arquivo /etc/passwd que
possui os dados de usuários e deve ser lidos por todos.

#### adduser ou useradd

Comandos para criação de novos usuários. Por padrão, quando um novo usuário é adicionado, é criado um grupo com o mesmo nome do usuário. Será criado um diretório home com o nome do usuário (a não ser que o novo usuário criado seja um usuário do sistema) e este receberá uma identificação. A identificação do usuário (UID) escolhida será a primeira disponível no sistema especificada de acordo com a faixa de UIDS de usuários permitidas no arquivo de configuração /etc/adduser.conf. Este é o arquivo que contém os padrões para a criação de novos usuários no sistema. Sintaxe:

```
# adduser [opções] [usuário/grupo]
```

opções:

--group - Cria um novo grupo ao invés de um novo usuário. A criação de grupos também pode ser feita pelo comando addgroup.

-uid [num] - Cria um novo usuário com a identificação [num] ao invés de procurar o próximo UID disponível.

--home [dir] - Usa o diretório [dir] para a criação do diretório home do usuário ao invés de usar o especificado no arquivo de configuração **/etc/adduser.conf**.

--system - Cria um usuário de sistema ao invés de um usuário normal.

--shell - Definir o shell de login do usuário.

Exemplo:

```
# adduser torvalds
```

#### passwd

Comando utilizado para alteração de senha de usuários e também outros parametros. Um usuário somente pode alterar a senha de sua conta, mas o superusuário (root) pode alterar a senha de qualquer conta de usuário, inclusive a data de validade da conta, etc. Os donos de grupos também podem alterar a senha do grupo com este comando. Os dados da conta do usuário como nome, endereço, telefone, também podem ser alterados com este comando. Sintaxe:

```
# passwd [usuário] [opções]
```

opções:

e - Força a expiração de senha para a conta especificada.

x [dias] - Especifica o número máximo de dias que a senha poderá ser usada. Após terminar o prazo, a senha deverá ser modificada.

i - Desativa a conta caso o usuário não tenha alterado sua senha após o tempo especificado por -x.

w [num] - Número de dias antecedentes que o usuário receberá o alerta para mudar sua senha. O alerta ocorre [num] dias antes do limite da opção -x, avisando ao usuários quantos dias restam para a troca de sua senha.

l [nome] - Bloqueia a conta do usuário [nome]. Deve ser usada pelo root. O bloqueio da conta é feito acrescentando um caracter a senha para que não confira com a senha original.

u [nome] - Desbloqueia a conta de um usuário bloqueada com a opção -l.

S [nome] - Mostra o status da conta do usuário [nome]. A primeira parte é o nome do usuário seguido de L(conta bloqueada), NP (sem senha), ou P (com senha), a terceira parte é a data da última modificação da senha, a quarta parte é a período mínimo, máximo, alerta e o período de inatividade para a senha.

#### usermod

Esse comando possibilita alterar informações do usuário, entre elas, grupos os quais o usuário pertence, seu login, seu diretório de trabalho. Sintaxe:

```
# usermod -[opções] [usuário]
```

opções:

d - Fornece o caminho completo do diretório home do usuário.

c - Grava um comentário para a conta do usuário.

g - Fornece o grupo padrão da conta do usuário.

s - Fornece o caminho completo do shell a ser utilizado pelo usuário. Ex.: /bin/bash.

l - Alterar o nome de login do usuário.

Exemplos:

```
# usermod -c “Joao do micro” joao
Altera o nome do usuário joao.

# usermod -l mjoao joao
Altera o login do joao para mjoao.
```

#### userdel

Comando utilizado para deletar um usuário do sistema. Sintaxe:

```
# userdel <opções> [usuário]
```

opções:

r - Apaga também o diretório HOME do usuário.

#### addgroup ou groupadd

Adiciona um novo grupo de usuários no sistema. As opções usadas são as mesmas do “adduser”.

```
# addgroup alunos
```

#### gpasswd

Modifica parametros e senha de grupo. Um usuário somente pode alterar a senha de seu grupo, mas o superusuário (root) pode alterar a senha de qualquer grupo de usuário, inclusive definir o administrador do grupo. Sintaxe:

```
# gpasswd [opções] [usuario] [grupo]
```

opções:

r usuario grupo - Remove a senha de grupo.

a usuario grupo - Adiciona o usuário no grupo especificado.

d usuario grupo - Apaga o usuário do gurpo especificado.

A [usuario] [grupo] - Define que o [usuario] será o administrador do [grupo].

> Você deve ser o dono da conta para poder modificar a senhas. O usuário root pode modificar/apagar a senha de qualquer usuário.

Exemplo:

```
# gpasswd -a jose alunos
```

#### groupdel

Apaga um grupo do sistema. Quando é usado, este comando apaga todos os dados do grupo especificado dos arquivos de contas do sistema. Sintaxe:

```
# groupdel [grupo]
```

Tenha certeza que não existem arquivos/diretórios criados com o grupo apagado.

> Nota: Você não pode remover o grupo primário de um usuário. Remova o usuário primeiro.

#### groups

Este comando mostra a quais grupos um usuário faz parte.

```
# groups jose
```

#### chage

O comando chage é usado para manipular a data de expiração da conta de usuário no sistema. A data fica gravada no arquivo /etc/shadow. Sintaxe:

```
# chage -[opções] [usuário]
```

opcões:

l - Exibe informações de expiração de senha de um usuário.

M <num_dias> - Força o usuário a mudar a senha daqui a <num> dias.

W <num_dias> - O valor <num> representa a quantidade de vezes que o usuário será avisado antes de expirar a senha.

E <data> - Especifica a data de expiração da senha, no formato (MM/DD/YYYY).

Exemplos:

```
#change joao -l
Exibe as informações sobre a expiração da senha do usuário joao.

# chage -M 30 joao
Exige que o usuário joao mude a senha daqui a 30 dias.

# chage -W 5 joao
O usuário joao receberá 5 avisos antes de expirar.

# chage -E 11/30/2020 joao
A conta do usuário joao irá expirar no dia 30 de novembro de 2020.
```

#### sudo

Concede temporariamente ao usuário atual, permissão para executar uma tarefa administrativa mediante digitação de senha. Sintaxe:

```
sudo [comando_a_ser_executado]
```

#### users

Exibe os usuários ativos no sistema.

#### w

Exibe os usuários conectados ao sistema e o que estão fazendo.

#### who

Exibe quem está utilizando os terminais.

#### whoami

Exibe o ID efetivo do usuário.


Se você tiver algo mais que possa agregar ao exposto, deixe seu comentário, será muito bem vindo!

Obrigado pela leitura.


### Links úteis:

[Canal no YouTube](https://www.youtube.com/channel/UCC6ue986efLUHRuqGiIfuwQ/featured?view_as=public)

[Instagram](https://www.instagram.com/smartcontacts/)

[Twitter](https://twitter.com/@ContactsSmart)

[GNU](http://www.gnu.org)

[Linux Ubuntu](https://ubuntu.com/)
