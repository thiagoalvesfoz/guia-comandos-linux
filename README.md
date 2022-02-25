<h1 align="center">
  <img src="pinguim-mini.png" alt="Comandos legais de linux" width="180px">
  <br>
  O Guia de Comandos Linux
</h1>
<p>Esse guia foi criado para ajudar pessoas que querem migrar de sistema operacional para uma distro linux. Sinta-se a vontade para adicionar, fazer correções ou melhorar a descrição de alguns comandos listados aqui</p>

> Fiz também um guia de comandos para se dar bem com GIT, você pode acessar [por aqui](https://github.com/thiagoalvesfoz/comandos-git)

## Linguagem Linux

- **DIRETÓRIOS:** Diferente do Windows, no linux é mais comum utilizar o termo **diretório** do que o termo **pasta** para se referir a uma localização no disco

- **DISTRO LINUX:** O Linux (GNU/Linux) em si, é apenas um kernel de Sistema Operacional. Não existe um Linux S.O oficial, na verdade, o que existe são distribuições feitas em cima do kernel do linux, dentre elas estão o ubuntu, fedora, manjaro, debian, centOS e etc... Todas essas distribuições são conhecidas como **distro linux**, e por serem baseados no kernel do linux, essas distros tendem a compartilhar os mesmos comandos no terminal.

- **SUDO:** Alguns comandos requerem que você tenha permissão root para serem executados. A menos que você não esteja no modo root, utilize a palavra **sudo** antes de executar comandos que exigem uma permissão de usuário root.

## Sumário

1. <a href="#operators">Operadores básicos</a>
2. <a href="#simbols">Símbolos Importantes</a>
3. <a href="#atalhos">Atalhos do terminal</a>
4. <a href="#so">Comandos úteis para obter informações do S.O</a>
5. <a href="#navigation">Comandos básicos de navegação no terminal</a>
6. <a href="#package-manager">Instalação de softwares com o gerenciador de pacotes "apt"</a>
7. <a href="#install">Instalação de softwares baixados pela internet</a>
8. <a href="#file">Manipulação de arquivos</a>
9. <a href="#search">Comandos para pesquisa</a>
10. <a href="#users-controls">Controle de usuários</a>
11. <a href="#permission">Alterando permissões</a>
12. <a href="#maintenance">Manutenção do sistema</a>
13. <a href="#process">Processos e serviços</a>
14. <a href="#network">Comandos de rede</a>
15. <a href="#ssh">Utilidades para o SSH</a>
16. <a href="#permission-tutorial">Entendendo as permissões no linux</a>
    1. <a href="#permission-table">Tabela de permissões</a>
    2. <a href="#chmod">Comando chmod explicado</a>
    3. <a href="#structure">Estrutura das permissões mostrada no terminal</a>

<h2 id="operators">Operadores básicos</h2>

| COMANDO   | O QUE ELE FAZ                                                              |
| --------- | -------------------------------------------------------------------------- |
| `cd`      | Utilizado para fazer a navegação entre [ pastas / diretórios ]             |
| `ls`      | Utilizado para listar tudo o que tem dentro de um diretório                |
| `cat`     | Utilizado para mostrar o conteúdo dentro do arquivo no terminal            |
| `rm`      | Utilizado para apagar permanentemente algum arquivo ou diretório           |
| `mkdir`   | Utilizado para criar um novo [ **diretório / pasta** ]                     |
| `touch`   | Utilizado para criar arquivos com qualquer extensão.                       |
| `grep`    | Procura por padrões e destaca em cores a palavra que o usuário especificar |
| `sudo`    | Utilizado para executar comandos com permissão de usuário root             |
| `history` | Mostra o histórico de comandos utilizados no terminal                      |
| `clear`   | Limpa o terminal                                                           |
| `exit`    | encerra a sessão atual no terminal                                         |

<h2 id="simbols">Símbolos Importantes</h2>

| SIMBOLO | O QUE SIGNIFICA                                                                                                                                                          |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `$`     | Esse simbolo no inicio do terminal, indica que você está logado como **usuário comum**                                                                                   |
| `#`     | Esse simbolo no inicio do terminal, indica que você está logado como **usuário root**                                                                                    |
| `./`    | Significa "o diretório atual / a pasta atual"                                                                                                                            |
| `../`   | Significa "o diretório anterior / a pasta anterior"                                                                                                                      |
| `*`     | Significa "tudo ou todos" (exemplo: `*.txt`. todos os arquivos que terminem com .txt)                                                                                    |
| &#124;  | Faz o encadeamento de comandos. <br> Ex: ( **ls &#124; grep a** ) primeiro faz a listagem, o resultado cai no segundo comando que filtra todo o conteúdo iniciando com a |
| `>`     | Redireciona a saida de um comando para outro comando ou arquivo                                                                                                          |
| `>>`    | Redireciona a saida e adiciona a mesma para um comando ou arquivo                                                                                                        |
| `&`     | Permite usar dois comandos e separar suas saidas no terminal                                                                                                             |
| `&&`    | Usado para que dois comandos só sejam executados se o primeiro for executado com sucesso.                                                                                |

<h2 id="atalhos">Atalhos do terminal</h2>

| ATALHO           | O QUE ELE FAZ                                         |
| ---------------- | ----------------------------------------------------- |
| `CTRL + ALT + T` | Abre o terminal linux                                 |
| `CTRL + C`       | Cancela o comando atual em funcionamento              |
| `CTRL + W`       | Apaga a palavra digitada da linha de comando          |
| `CTRL + U`       | Apaga a linha inteira                                 |
| `CTRL + L`       | equivalente ao comando `clear`, limpa a tela          |
| `CTRL + R`       | Busca um comando recente                              |
| `CTRL + D`       | equivalente ao comando `exit`, encerra a sessão atual |

<h2 id="so">Comandos úteis para obter informações do S.O</h2>

| PROBLEMA                                                                         | COMANDO              |
| -------------------------------------------------------------------------------- | -------------------- |
| Quero ver a data e hora atual                                                    | `date`               |
| Quero ver o tempo que o S.O está ligado                                          | `uptime`             |
| Quero ver qual usuário está logado                                               | `whoami`             |
| Quero ver a versão atual da minha distro                                         | `cat /etc/*-release` |
| Quero entrar no modo usuário root para executar comandos com permissões elevadas | `sudo su`            |

<h2 id="navigation">Comandos básicos de navegação no terminal</h2>

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

<h2 id="package-manager">Instalação de softwares com o gerenciador de pacotes "apt"</h2>

| PROBLEMA                                                                                                       | COMANDO                                               |
| -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| Quero sincronizar meu repositório com a lista de pacotes e programas mais recentes disponíveis para instalação | `apt-get update`                                      |
| Quero atualizar meu sistema, baixar e instalar os pacotes de atualização dos programas instalados.             | `apt-get upgrade`                                     |
| Quero instalar um software na minha distro linux                                                               | `apt-get install <programa>`                          |
| Quero desinstalar um software na minha distro linux                                                            | `apt-get remove <programa>`                           |
| Quero fazer uma pesquisa no repositório                                                                        | `apt-cache search <programa>`                         |
| Quero fazer uma pesquisa no repositório filtrando por palavra-chave                                            | `apt-cache search <programa>` &#124; `grep <palavra>` |

<h2 id="install">Instalação de softwares baixados pela internet</h2>

| PROBLEMA                                                                                                                                                                                                                                 | COMANDO                                   |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- |
| Quero baixar um arquivo de instalação da internet.                                                                                                                                                                                       | `wget <url.deb>`                          |
| Quero instalar um programa que eu baixei da internet. <br> **OBS:** Se houver problemas de dependências durante a instalação, rode na sequência o comando `apt-get -f install`. (não é necessário o rodar o comando **dpkg** novamente.) | `dpkg -i <diretorio/arquivo-baixado.deb>` |

<h2 id="file">Manipulação de arquivos</h2>

| PROBLEMA                                                                                | COMANDO                                   |
| --------------------------------------------------------------------------------------- | ----------------------------------------- |
| Quero **RENOMEAR** um arquivo                                                           | `mv <nome-atual> <novo-nome>`             |
| Quero **MOVER** um arquivo para outro diretório                                         | `mv <arquivo-origem> <diretorio-destino>` |
| Quero **COPIAR** um arquivo e enviar para outro diretório (ctrl+c - ctrl + v)           | `cp <arquivo-origem> <diretorio-destino>` |
| Quero que mostre no terminal o conteúdo dentro de um arquivo                            | `cat <arquivo.extensao>`                  |
| Quero que mostre no terminal o conteúdo dentro de um arquivo em ordem inversa           | `tac <arquivo.extensao>`                  |
| Quero que mostre em binário o conteúdo dentro de um arquivo                             | `xxd -b <arquivo.extensao>`               |
| Quero que mostre com paginação o conteúdo dentro de um arquivo.                         | `cat <arquivo.extensao>` &#124; `more`    |
| Quero que mostre com paginação o conteúdo dentro de um arquivo. **²**                   | `less <arquivo.extensao>`                 |
| Preciso filtrar por palavra-chave o conteúdo dentro de um arquivo e mostrar no terminal | `cat <arquivo>` &#124; `grep <palavra>`   |
| Quero ver as 10 primerias linhas do conteúdo de um arquivo no terminal                  | `head <arquivo>`                          |
| Quero ver as 10 últimas linhas do conteúdo de um arquivo no terminal                    | `tail <arquivo>`                          |
| Quero ver as últimas linhas de um arquivo no terminal em tempo real                     | `tail -f <arquivo>`                       |

<h2 id="search">Comandos para Pesquisa</h2>

| PROBLEMA                                                                                                              | COMANDO                                        |
| --------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| Quero listar todos os arquivos dentro do diretório atual, incluindo os arquivos dentro dos subdiretórios              | `find <diretorio>`                             |
| Quero procurar todos os arquivos em um diretório que possuem um determinado nome                                      | `find <diretorio> -name <nome.extensao>`       |
| Quero listar todos os arquivos que possuem uma determinada extensão dentro de um diretório e seus subdiretórios       | `find <diretorio> -name '*.<extensao>'`        |
| Quero listar tudo o que tem dentro do diretório, mas, limitando o nível de subdiretórios que será exibido no terminal | `find <diretorio> -maxdepth 1`                 |
| Quero procurar todos os arquivos em um diretório que possuem um determinado nome, mas com limite de subdiretórios     | `find <diretorio> -maxdepth 1 -name <arquivo>` |
| Quero mostrar somente arquivos durante a listagem                                                                     | `find <diretorio> -type f -name <arquivo>`     |
| Quero mostrar somente diretórios durante a listagem                                                                   | `find <diretorio> -type d -name <arquivo>`     |

<h2 id="users-controls">Controle de usuários</h2>

| PROBLEMA                                          | COMANDO                                                       |
| ------------------------------------------------- | ------------------------------------------------------------- |
| Quero adicionar um novo usuário                   | `adduser <nome-usuario>`                                      |
| Quero remover um usuário mantendo a pasta pessoal | `userdel <nome-usuario>`                                      |
| Quero remover um usuário e a pasta pessoal        | `userdel -r <nome-usuario>`                                   |
| Quero trocar de usuário                           | `sudo <usuario>`                                              |
| Quero trocar a senha do meu usuário               | `passwd <nova-senha>`                                         |
| Quero ver todos usuários                          | `cat /etc/passwd`                                             |
| Quero ver todos os grupos                         | `cat /etc/group`                                              |
| Quero adicionar um usuário em um grupo            | `adduser <usuario> <grupo>` ou `gpasswd -a <usuario> <grupo>` |
| Quero remover um usuário de um grupo              | `gpasswd -d <usuario> <grupo>`                                |
| Quero remover um grupo                            | `groupdel <grupo>`                                            |
| Quero verificar o meu nome de usuário             | `whoami`                                                      |
| Quero ver os dados do meu usuário e seus grupos   | `id`                                                          |
| Quero o número de identificação do meu usuário    | `id -u`                                                       |
| Quero saber a quais grupo meu usuário pertence    | `groups`                                                      |
| Quero saber a quais grupo um usuário pertence     | `groups <usuario>`                                            |

<h2 id="permission"> Alterando permissões <a href="#permission-tutorial" style="font-size:16px">Ver tutorial </a></h2>

| PROBLEMA                                                                                           | COMANDO                                     |
| -------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| Quero listar os arquivos e diretórios mostrando as permissões                                      | `ls -lh`                                    |
| Quero listar todos os arquivos e diretórios mostrando as permissões incluindo as que estão ocultas | `ls -lha`                                   |
| Quero alterar a permissão de um arquivo ou pasta                                                   | `chmod <permissao> <diretorio-ou-arquivo>`  |
| Quero adicionar permissão de execução de um arquivo ou pasta para todos                            | `chmod +x <diretorio-ou-arquivo>`           |
| Quero remover permissão de execução de um arquivo ou pasta para todos                              | `chmod -x <diretorio-ou-arquivo>`           |
| Quero alterar o dono de um diretório ou arquivo                                                    | `chown <usuario> <diretorio-ou-arquivo>`    |
| Quero alterar o dono de um diretório e tudo que tem dentro dele                                    | `chown <usuario> -R <diretorio-ou-arquivo>` |

<h2 id="maintenance">Manutenção do sistema</h2>

| PROBLEMA                                                                           | COMANDO                |
| ---------------------------------------------------------------------------------- | ---------------------- |
| Quero que mostre um resumo das partições do disco                                  | `df`                   |
| Quero um resumo das partições em disco de forma mais amigável                      | `df -h`                |
| Quero todas as partições com inodes mostrando o tamanho em disco de forma amigável | `df -ih` ou `df -i -h` |
| Quero saber o tamanho dos arquivos no diretório atual                              | `du -sh *`             |
| Quero ver informações da memoria ram de forma amigável `-h`                        | `free -h`              |
| Quero ver informações do processador                                               | `lscpu`                |

<h2 id="process">Processos e serviços</h2>

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

<h2 id="network">Comandos de rede</h2>

| PROBLEMA                                                                                  | COMANDO                   |
| ----------------------------------------------------------------------------------------- | ------------------------- |
| Quero fazer o diagnósticos dos pacotes enviados e perdidos                                | `ping <site-ou-dns>`      |
| Quero rastrear o caminho utilizado até o destino final                                    | `tracepath <site-ou-dns>` |
| Quero fazer o diagnósticos dos pacotes enviados e perdidos, incluindo as rotas utilizadas | `mtr <site-ou-dns>`       |
| Quero que mostre os processos com portas apertas no S.O                                   | `netstat -atunp`          |
| Quero ver informações da minha interface de rede                                          | `ifconfig`                |
| Quero ver informações da minha interface de rede **²**                                    | `ip addr`                 |

<h2 id="ssh">Utilidades para o SSH</h2>

| PROBLEMA                                                           | COMANDO                                                            |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| Quero copiar um arquivo da minha máquina para uma máquina remota   | `scp <meu-arquivo> <usuario@IP-REMOTO:diretorio/final>`            |
| Quero copiar um arquivo de uma máquina remota para a minha máquina | `scp <usuario@IP-REMOTO:diretorio/arquivo-remoto> <meu-diretorio>` |
| Quero copiar o diretório inteiro                                   | `scp -r <args...>`                                                 |
| Quero copiar um arquivo ou diretório utilizando compactação        | `scp -C <args...>`                                                 |

<br>
<br>
<h2 id="permission-tutorial"> Entendendo as permissões no linux </h2>

<h3 id="permission-table">Tabela de permissões</h3>

| CHAR | BINARIO | DECIMAL | PERMISSÃO          |
| ---- | ------- | ------- | ------------------ |
| ---  | 000     | 0       | Nenhuma permissão  |
| --x  | 001     | 1       | Execução           |
| -w-  | 010     | 2       | Escrita            |
| -wx  | 011     | 3       | Escrita e execucão |
| r--  | 100     | 4       | Leitura            |
| r-x  | 101     | 5       | Leitura e execução |
| rw-  | 110     | 6       | Leitura e escrita  |
| rwx  | 111     | 7       | Permissao total    |

<h3 id="chmod">Comando chmod explicado</h3>

| COMANDO | PROPRIETÁRIO | GRUPO | OUTROS | ARQUIVO               | O QUE FAZ                                                                                                                                                                                     |
| ------- | ------------ | ----- | ------ | --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `chmod` | `7`          | `5`   | `1`    | `<diretorio/arquivo>` | O primeiro número da permissão total para o dono. <br> O segundo número dá permissão de leitura e execução para o grupo. <br> O terceiro número dá permissão de execução para outros usuários |

<h3 id="structure">Estrutura das permissões mostrada no terminal</h3>

| TIPO | PROPRIETÁRIO | GRUPO | OUTROS | ARQUIVO               |
| ---- | ------------ | ----- | ------ | --------------------- |
| -    | ---          | ---   | ---    | Ex: Nenhuma permissão |
| -    | rwx          | r-x   | --x    | texto.txt             |
| d    | rwx          | r-x   | --x    | /diretorio            |
| i    | rwx          | r-x   | --x    | atalhos               |

> O primeiro hífen faz referência ao tipo, em seguida há 3 hífens agrupados por tipos de usuários.

- `text.tx` tem permissão total para o dono do arquivo, leitura e execução para o grupo e somente execução para outros usuários.
- `/diretorio` possui as mesmas permissões que o texto.txt
- `atalho ou link simbolico` possui as mesmas permissões que o arquivo texto.txt
