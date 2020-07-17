<p align="center">
  <a href="https://smartcontacts.com.br/">
    <img alt="Smart Contacts" src="https://smartcontacts.com.br/assets/img/logo.png" width="200" />
  </a>
</p>
<h2 align="center">
Informação sobre tecnologia, dicas, tutoriais, mini-cursos e muito mais.
</h2>

# Gerenciamento de Processos

## Introdução

Processo é um programa rodando no nosso sistema, também considerado um processo do kernel.

Todos os comandos que executamos são identificados pelo kernel (conforme lista abaixo), porém para executar um comando, é necessário que ele tenha permissões de execução e que esteja no caminho de procura de arquivos (PATH).

Por exemplo, o caminho ```/usr/local/bin:/usr/bin:/bin:/usr/bin/X11``` significa que se você digitar o comando ```ls```, o interpretador de comandos iniciará a procura do programa ```ls``` no diretório ```/usr/local/bin```, caso não encontre o arquivo no diretório ```/usr/local/bin``` ele inicia a procura em ```/usr/bin```, até que encontre o arquivo procurado.

As características e conceitos associados com processos incluem:

Lifetime - É o tempo de vida de um processo em execução.

PID - É a identidade de um processo representado por um número inteiro e único.

UID - É um processo associado com um usuário que inicia um processo.

Parent Process - O primeiro processo startado no kernel do sistema é o init. Este processo tem o PID 1 e é o último parente de todos os outros processos no sistema. Seu shell é descendente do init e o processo parente para os comandos é o shell, onde esses são processos filhos ou subprocessos.

Parent Process ID - Este é o PID do processo parente, ou seja, o PID do processo que criou o processo em questão.

Enviroment - Cada processo tem suporte a uma lista de variáveis associados a valores.

Current Working Directory - É um diretório default associado com cada processo.

## Tipos de Execução de comandos/programas

Um programa pode ser executado de duas formas:

1. Primeiro Plano (foreground) - Quando você deve esperar o término da execução de um programa para executar um novo comando (a não ser que utilize outra sessão de terminal simultaneamente).

2. Segundo Plano (background) - Após iniciar um programa em background, é mostrado um número PID (identificação do Processo) e o aviso de comando é novamente mostrado, permitindo o uso normal do sistema.

Para iniciar um programa em primeiro plano, basta digitar seu nome normalmente. Já para iniciar em segundo plano, acrescente o caracter ```&``` após o final do comando.

Os comandos podem ser executados em seqüência (um após o término do outro) se os separarmos com ```;``` (ponto e vírgula).

### ps

Comando usado para listar os programas/processos que estão sendo executados, ordenando-os pelo número de identificação do processo (PID). Exibe ainda qual usuário executou o programa, hora que o processo foi iniciado, etc.

```
ps -[opções]
```

Principais opções:

**a** - Mostra todos os processos, incluindo os processos de outros usuários.

**u** - Fornece o nome do usuário e a hora que o processo foi iniciado.

**x** - Mostra os processos mesmo que estes não estejam associados a nenhum terminal.

### pstree

O comando pstree mostra toda a árvore de processos desde o init até o último processo em execução. Muito útil para identificar a relação entre processo pai e filho.

```
pstree -[opções]
```

Principais opções:

**a** - Mostra a linha de comando utilizada para iniciar os processos.

**c** - Desabilita a função de mesclar os processos idênticos no mesmo nível de hierarquia.

**h** - Destaca os processos ligados ao terminal.

**p** - Mostra o PID dos processos.

### top

Mostra os programas em execução ativos, parados, tempo usado na CPU, detalhes sobre o uso da memória RAM, Swap, disponibilidade para execução de programas no sistema, etc.

top é um programa que continua em execução mostrando continuamente os processos que estão rodando em seu computador e os recursos utilizados por eles. Para sair do top, pressione a tecla q.

```
top -[opções]
```

Principais opções:

**d [tempo]** - Atualiza a tela após o [tempo] (em segundos).

**c** - Mostra a linha de comando ao invés do nome do programa.

Teclas úteis para uso com o ```top```:

espaço - Atualiza imediatamente a tela.

**h** - Mostra a tela de ajuda do programa.

**k** - Finaliza um processo - semelhante ao comando kill. Você será perguntado pelo número de identificação do processo (PID).

**n** - Muda o número de linhas mostradas na tela. Se 0 for especificado, será usada toda a tela para listagem de processos.

**q** - Sai do programa.

### kill

Permite enviar um sinal a um comando/programa. Caso seja usado sem parâmetros, o kill enviará um sinal de término ao processo sendo executado.

```
kill [sinal] [número]
```

Onde:

**número** - É o número de identificação do processo.

**sinal** - Sinal que será enviado ao processo. Se omitido usa -15 como padrão.

Principais sinais usados:

HUP (1) - Pendurar - o processo será terminado após terminar suas atividades.

INT (2) - Interromper – equivale ao CTRL+C enviado pelo usuário por meio do teclado.

KILL (9) - Terminar/Destruir – o processo é interrompido imediatamente. Deve ser usado apenas em situações extremas.

TERM (15) - Sinal enviado por padrão caso não seja enviado nenhum outro. Termina o processo imediatamente, entretanto dá oportunidade para ele fechar todos os arquivos abertos e eliminar arquivos temporários.


## Chegamos ao fim deste post

Se você tiver algo mais que possa agregar ao exposto, deixe seu comentário, será muito bem vindo!


## Links úteis:

[Canal no YouTube](https://www.youtube.com/channel/UCC6ue986efLUHRuqGiIfuwQ/featured?view_as=public)

[Instagram](https://www.instagram.com/smartcontacts/)

[Twitter](https://twitter.com/@ContactsSmart)

[GNU](http://www.gnu.org)

[Guia Foca Linux](https://guiafoca.org/)

[Linux Ubuntu](https://ubuntu.com/)

[Docker](https://docs.docker.com/)
