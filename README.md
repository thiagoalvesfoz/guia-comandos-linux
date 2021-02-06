<h1 align="center">
  <img src="pinguim.png" alt="Comandos úteis para git" width="120">
  <br>
  O Guia de Comandos Linux
</h1>
<p>Esse guia foi criado para ajudar pessoas que querem migrar de sistema operacional para uma distro linux. Sinta-se a vontade para adicionar, fazer correções ou melhorar a descrição de alguns comandos listados aqui</p>

## Linguagem Linux

- **DIRETÓRIOS:** Diferente do Windows, no linux é mais comum utilizar o termo **diretório** do que o termo **pasta** para se referir a uma localização no disco
- **DISTRO LINUX:** O Linux (GNU/Linux) em si, é apenas um kernel de Sistema Operacional. Não existe um Linux S.O oficial, na verdade, o que existem são distribuições feitas em cima do kernel do linux, dentre elas estão o ubuntu, fedora, manjaro, debian, centOS e etc... Todas essas distribuições são conhecidas como **distro linux**, e por serem baseados no kernel linux, essas distros tendem a compartilhar os mesmos comandos de terminal.
- **SUDO:** Alguns comandos requerem que você tenha permissão root para serem executados. A menos que você não esteja no modo root, utilize a palavra **sudo** antes de executar comandos que exigem uma permissão de usuário root.

## Operadores básicos

| COMANDO   | O QUE ELE FAZ                                                              |
| --------- | -------------------------------------------------------------------------- |
| `cd`      | Utilizado para fazer a navegação entre [ pastas / diretórios ]             |
| `ls`      | Utilizado para listar tudo o que tem dentro de um diretório                |
| `cat`     | Utilizado para mostrar o conteúdo dentro do arquivo no terminal            |
| `rm`      | Utilizado para apagar permanentemente algum arquivo ou diretório           |
| `mkdir`   | Utilizado para criar um novo [ **diretório / pasta** ]                     |
| `touch`   | Utilizado para criar arquivos com qualquer extensão.                       |
| `grep`    | procura por padrões e destaca em cores a palavra que o usuário especificar |
| `sudo`    | Utilizado para executar comandos com permissão de usuário root             |
| `history` | Mostra o histórico de comandos utilizados no terminal                      |

## Simbolos Importantes

| SIMBOLO | O QUE SIGNIFICA                                                                                                                                                          |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `$`     | Esse simbolo no inicio do terminal, indica que você está logado como **usuário comum**                                                                                   |
| `#`     | Esse simbolo no inicio do terminal, indica que você está logado como **usuário root**                                                                                    |
| `./`    | significa "o diretório atual / a pasta atual"                                                                                                                            |
| `../`   | significa "o diretório anterior / a pasta anterior"                                                                                                                      |
| `*`     | significa "tudo ou todos" (exemplo: `*.txt`. todos os arquivos que terminem com .txt)                                                                                    |
| &#124;  | Faz o encadeamento de comandos. <br> Ex: ( **ls &#124; grep a** ) primeiro faz a listagem, o resultado cai no segundo comando que filtra todo o conteúdo iniciando com a |

## Comandos úteis para obter informações do S.O

| PROBLEMA                                                                         | COMANDO              |
| -------------------------------------------------------------------------------- | -------------------- |
| Quero ver a data e hora atual                                                    | `date`               |
| Quero ver o tempo que o S.O está ligado                                          | `uptime`             |
| Quero ver qual usuário está logado                                               | `whoami`             |
| Quero ver a versão atual da minha distro                                         | `cat /etc/*-release` |
| Quero entrar no modo usuário root para executar comandos com permissões elevadas | `sudo su`            |

## Comandos básicos de navegação

| PROBLEMA                                                                    | COMANDO                    |
| --------------------------------------------------------------------------- | -------------------------- |
| Quero navegar para pasta raiz do disco                                      | `cd /`                     |
| Quero navegar para pasta raiz do meu usuário                                | `cd ~`                     |
| Quero voltar uma pasta anterior                                             | `cd ..`                    |
| Quero criar uma nova pasta                                                  | `mkdir <nome-da-pasta>`    |
| Quero criar um arquivo                                                      | `touch <arquivo.extensao>` |
| Quero que mostre o diretório atual de onde eu estou                         | `pwd`                      |
| Quero remover uma **pasta vazia**                                           | `rmdir <nome-da-pasta>`    |
| Quero remover uma pasta/diretorio e tudo que tem dentro                     | `rm -r <nome-da-pasta>`    |
| Quero **FORÇAR** a remoção de uma pasta/diretorio com tudo o que tem dentro | `rm -rf <nome-da-pasta>`   |

## Instalação de softwares com o gerenciador de pacotes "apt"

| PROBLEMA                                                                                                       | COMANDO                                               |
| -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| Quero sincronizar meu repositório com a lista de pacotes e programas mais recentes disponíveis para instalação | `apt-get update`                                      |
| Quero atualizar meu sistema, baixar e instalar os pacotes de atualização dos programas instalados.             | `apt-get upgrade`                                     |
| Quero instalar um software na minha distro linux                                                               | `apt-get install <programa>`                          |
| Quero desinstalar um software na minha distro linux                                                            | `apt-get remove <programa>`                           |
| Quero fazer uma pesquisa no repositório                                                                        | `apt-cache search <programa>`                         |
| Quero fazer uma pesquisa no repositório filtrando por palavra-chave                                            | `apt-cache search <programa>` &#124; `grep <palavra>` |

## Instalação de softwares baixados pela internet

| PROBLEMA                                                                                                                                                                                                                                 | COMANDO                                   |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- |
| Quero baixar um arquivo de instalação da internet.                                                                                                                                                                                       | `wget <url.deb>`                          |
| Quero instalar um programa que eu baixei da internet. <br> **OBS:** Se houver problemas de dependências durante a instalação, rode na sequência o comando `apt-get -f install`. (não é necessário o rodar o comando **dpkg** novamente.) | `dpkg -i <diretorio/arquivo-baixado.deb>` |

## Comandos para manipulação de arquivos

| PROBLEMA                                                                                | COMANDO                                   |
| --------------------------------------------------------------------------------------- | ----------------------------------------- |
| Quero copiar um arquivo e enviar para outro diretório (ctrl+c - ctrl + v)               | `cp <arquivo-origem> <diretorio-destino>` |
| Quero que mostre no terminal o conteúdo dentro de um arquivo                            | `cat <arquivo.extensao>`                  |
| Quero que mostre em binário o conteúdo dentro de um arquivo                             | `xxd -b <arquivo.extensao>`               |
| Quero que mostre com paginação o conteúdo dentro de um arquivo.                         | `cat <arquivo.extensao>` &#124; `more`    |
| Quero que mostre com paginação o conteúdo dentro de um arquivo. **²**                   | `less <arquivo.extensao>`                 |
| Preciso filtrar por palavra-chave o conteúdo dentro de um arquivo e mostrar no terminal | `cat <arquivo>` &#124; `grep <palavra>`   |
| Quero ver as últimas linhas do conteúdo de um arquivo no terminal                       | `tail <arquivo>`                          |
| Quero ver as últimas linhas de um arquivo no terminal em tempo real                     | `tail -f <arquivo>`                       |

## Comandos para Pesquisa

| PROBLEMA                                                                                                              | COMANDO                                        |
| --------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| Quero listar todos os arquivos dentro do diretório atual, incluindo os arquivos dentro dos subdiretórios              | `find <diretorio>`                             |
| Quero procurar todos os arquivos em um diretório que possuem um determinado nome                                      | `find <diretorio> -name <nome.extensao>`       |
| Quero listar todos os arquivos que possuem uma determinada extensão dentro de um diretório e seus subdiretórios       | `find <diretorio> -name '*.<extensao>'`        |
| Quero listar tudo o que tem dentro do diretório, mas, limitando o nível de subdiretórios que será exibido no terminal | `find <diretorio> -maxdepth 1`                 |
| Quero procurar todos os arquivos em um diretório que possuem um determinado nome, mas com limite de subdiretórios     | `find <diretorio> -maxdepth 1 -name <arquivo>` |
| Quero mostrar somente arquivos durante a listagem                                                                     | `find <diretorio> -type f -name <arquivo>`     |
| Quero mostrar somente diretórios durante a listagem                                                                   | `find <diretorio> -type d -name <arquivo>`     |

## Permissões

| PROBLEMA                                                                                           | COMANDO                                     |
| -------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| Quero listar os arquivos e diretórios mostrando as permissões                                      | `ls -l`                                     |
| Quero listar todos os arquivos e diretórios mostrando as permissões incluindo as que estão ocultas | `ls -l -a` ou `ls -la`                      |
| Quero alterar a permissão de um arquivo ou pasta                                                   | `chmod <permissao> <diretorio-ou-arquivo>`  |
| Quero adicionar permissão de execução de um arquivo ou pasta para todos                            | `chmod +x <diretorio-ou-arquivo>`           |
| Quero remover permissão de execução de um arquivo ou pasta para todos                              | `chmod -x <diretorio-ou-arquivo>`           |
| Quero alterar o dono de um diretório ou arquivo                                                    | `chown <usuario> <diretorio-ou-arquivo>`    |
| Quero alterar o dono de um diretório e tudo que tem dentro dele                                    | `chown <usuario> -R <diretorio-ou-arquivo>` |

## Manutenção de sistema

| PROBLEMA                                                                           | COMANDO                |
| ---------------------------------------------------------------------------------- | ---------------------- |
| Quero que mostre um resumo das partições do disco                                  | `df`                   |
| Quero um resumo das partições em disco de forma mais amigável                      | `df -h`                |
| Quero todas as partições com inodes mostrando o tamanho em disco de forma amigável | `df -ih` ou `df -i -h` |
| Quero saber o tamanho dos arquivos no diretório atual                              | `du -sh *`             |
| Quero ver informações da memoria ram de forma amigável `-h`                        | `free -h`              |
| Quero ver informações do processador                                               | `lscpu`                |

## Processos e serviços

| PROBLEMA                                                                  | COMANDO                           |
| ------------------------------------------------------------------------- | --------------------------------- |
| Quero ver os processos rodando na minha máquina                           | `ps`                              |
| Quero ver todos os processos com informações detalhadas                   | `ps aux`                          |
| Quero ver todos os processos de um usuário específico                     | `ps -f -u <usuario>`              |
| Quero ver todos os processos filtrados por palavra-chave                  | `ps aux` &#124; `<nome-programa>` |
| Quero que mostre o PID de um programa específico em execução              | `pgrep <nome-programa>`           |
| Quer ver todos os processos em tempo real                                 | `top`                             |
| Quer ver em hierarquia todos os processos em execução                     | `pstree`                          |
| Quer ver em hierarquia todos os processos em execução com os PIDs ao lado | `pstree -p`                       |
| Quero parar um serviço                                                    | `service <serviço> stop`          |
| Quero iniciar um serviço                                                  | `service <serviço> start`         |
| Quero reiniciar um serviço                                                | `service <serviço> restart`       |
| Quer matar um processo pelo código PID                                    | `kill <PID>`                      |

## Rede

| PROBLEMA                                                                                  | COMANDO                   |
| ----------------------------------------------------------------------------------------- | ------------------------- |
| Quero fazer o diagnósticos dos pacotes enviados e perdidos                                | `ping <site-ou-dns>`      |
| Quero rastrear o caminho utilizado até o destino final                                    | `tracepath <site-ou-dns>` |
| Quero fazer o diagnósticos dos pacotes enviados e perdidos, incluindo as rotas utilizadas | `mtr <site-ou-dns>`       |
| Quero que mostre os processos com portas apertas no S.O                                   | `netstat -atunp`          |
| Quero ver informações da minha interface de rede                                          | `ifconfig`                |
| Quero ver informações da minha interface de rede **²**                                    | `ip addr`                 |

## Utilidades para SSH

| PROBLEMA                                                           | COMANDO                                                            |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| Quero copiar um arquivo da minha máquina para uma máquina remota   | `scp <meu-arquivo> <usuario@IP-REMOTO:diretorio/final>`            |
| Quero copiar um arquivo de uma máquina remota para a minha máquina | `scp <usuario@IP-REMOTO:diretorio/arquivo-remoto> <meu-diretorio>` |
| Quero copiar o diretório inteiro                                   | `scp -r <args...>`                                                 |
| Quero copiar um arquivo ou diretório utilizando compactação        | `scp -C <args...>`                                                 |
