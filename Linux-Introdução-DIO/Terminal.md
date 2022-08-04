# Terminal

Root - adm sudo

**man -** Manual do comando (ex: man ls)

**( - uma letra da opção, ex: -a, o u - - all )**

**—help** (arquivo de ajuda, ptbr ex: ls —help)

**pwd -** Mostra diretório atual (caminho absoluto, universal, em relação ao pc).

**ls/dir(ws) -** Lista diretorio - (ls Documentos)

**-l** (detalhes)

**-a** (arq e dir ocultos)

**cd (change directory)**

**.. (**retorna diretorio**)**

**/** (direciona para /)

**~** (pasta pessoal)

**mkdir** (cria diretorio)

**history** (de comandos)

**!!** (executa ultimo comando)

- **Atalhos**
    
    ctrl+c - cancela comando atual
    
    ctrl+z - pausa o comando atual, em primeio plano ou segundo plano.
    
    ctrl+d (exit) - faz o logout da sessão atual
    
    ctrl+u - apaga a linha inteira
    
    ctrl+r - busca um comando recente
    

**mv (**funcoes principais: mover ou renomear, ex mv nomedapasta renomeadopasta, mv pasta1 pasta2) - **mv pasta1 ~**

**touch (cria arquivos vazios)** 

**cp (copia arquivos) -** cp arquivo.txt /home/usuario

**rm -r pasta*** (exclui todos os arquivo que começam com ‘pasta’) ****

**rmdir (remover dir)**

**‘>’ Redireciona a saída de um comando para outro comando ou arquivo**

**‘>>’ red. saída e adiciona a mesma para um comando ou arq**

**‘<’ Direiciona a entrada de um arquivo para saída de um comando**

>> **jogar dentro de arquivos**

**cat - tac - head - tail (ex: head teste.txt > teste2.txt)**

cal - date - 

**‘|’ envia a saida de um comando para entrada de outro**

‘|’  **grep** (busca dentro de arquivo texto)

‘|’  **more** (mostrar paginado - **less**)

**& Perimite usar dois comando e separar usas saídas no terminal**

**&& Dois comando só sejam executados se o primeiro for executado com sucesso**

whatis (saida do que faz o comando)

**find (busca e tras caminho arquivo) ( find ~ -name listanomes.txt )**

**lspci** (lista dispositivos PCI)

**lsusb, lscpu, lshw** (lista de todos os hardwares), **.** 

**arch** (arquitetura do sistema - kernel)

**uname** (nome do kernel) - **uname -r** (versao kernel) **-m** (arq. kernel)

**free** (saida de memória fisica e swap)

**du -h ~ (quanto diretorio pessoal utiliza do hd) =** utilização do hd em relação aos diretorios **( - h = human )**

**echo -e** (escrever no terminal com formatação \n)

---

**REDES**

**ifconfig  -** (informaçoes sobre rede ipv4(inet,inet6), loopback.

**hostname -** informações sobre host (nome computador na rede). **hostname -I** (endereço ip).

**who** (como estou logado na rede) **whoami**

**ping (faz parte do protocolo icmp: envia msg de controle p/ determinado host verifica se esta ativo)** ex: ping [www.google.com](http://www.google.com) (recebe sequecia de bytes do ip, envia um ping [pacode de requisição] e recebe as resposta ‘ping-pong’). ‘ex: ping www.google.com -w 4’

**dig** (informações sobre DNS) ex: dig [www.google.com](http://www.google.com) , saida gera informações sobre DNS (caminhos de rede) ip do google.

**traceroute** (traçar rota de rede, nós [caminhos] ate www.com) ex: traceroute www.google.com,       dig **+short somente endereço dns.**

**whois** (mais informações sobre determinado site, host).

**finger** (mostra toda inf. do usuário que esta logado no host).

---

**USUÁRIOS**

**adduser nomedousuario** (add usuario) ex: sudo adduser samuel

**sudo su** (troca para usuário root)

**su nomedousuario** (Trocar de usuário)

**passwd nomedousuário** (Altera a senha)

**lastlog** (exibe informações de login de usuários)

**last** (listagem de entrada e saída do usuário no sistema)

**logname** (nome do usuário atual)

**id** (todos os identificadores do usuário - grupos)

**cat/etc/passwd** (dir que exib todos os usuários)

**userdel nomedousuario** (remove usuário) **[ -r ] (userdel -r nome -** remove usuario e papsta pessoal do mesmo**)**

**GRUPOS - Permitem organizar os usuários e definir as permissões de acesso a  arquivos e diretórios de forma mais fácil.**

**Controle de grupos - cat /etc/group** (exibir todos os grupos do sistema)

**groups** (grupos usuario pertence)

**addgroup** (cria grupo)

**adduser ususario grupo (gpasswd -a)** - usuario que executa precisa estar no sudoers.

**gpasswd ‘-d’ usuario grupo** (remove usuario do grupo).

**groupdel grupo** (remove grupo)

---

### Permissões

Permissões em arquivos e diretórios servem para restringir acessos com: leitura, escrita e execução, onde **r - read (leitura), w - write (escrita), x - eXecution (execução).** 

  (owner)

    Dono | Grupo | outros

d   rwx     r-x           r-x

**Ex:**

drwxr-xr-x 2 samuel samuel 4,0K jun 30 22:57 'Área de trabalho'
-rw-r--r-- 1 samuel samuel    0 jul  3 19:10  arquivo.txt

**CONTROLE DE PERMISSÔES**

**ls -lh** (verificar permissões em um diretório)

- **Modo Octal**
    
    A máscara octal é composta por números sob a base 8 (0 - 7) onde:
    
    - O **primeiro** dígito representa o dono do ficheiro/diretório **(u)**
    - O **segundo** dígito representa o grupo **(g)**
    - O **terceiro** dígito representa os outros **(o)**
    - As permissões são especificadas para cada grupo

User (owner)  Gruoup       Other

r   w   x            r   w   x       r   w   x

4   2   1            4   2   1      4   2   1

**obs: mais de uma permissão basta somar.** 

**chmod** (Mudar a permissão de um arquivo ou diretório) ex: *chmod 100 arquivo.txt*

---

**COMPACTAÇÂO, DESCOMPACTAÇÂO E ARQUIVAMENTO**

 - Compactadores são programas que diminuem o tamanho de um arquivo ou diretório.

 - Extensões identificam o tipo de um arquivo, quando um arquivo é compactado uma extensão é adicionada ao nome do arquivo.

COMPACTADORES

- **gzip -** Compactador muito usado, possui uma taxa excelente de compactação. ex:           gzip arquivo.txt **( gzip -9 arquivo.txt - usa a compactação máxima).**
    
    **gunzip - Descompactação** ex: gunzip arquivo.txt.gz
    
- **zip -** zip arquivo.zip arquivo.txt teste.txt…
    
    **unzip arquivo.zip - Descompactação**
    
- **bzip2 -** bzip2 arquivo
    
    **bzip2 -d** arquivo.bz2 - **Descompactação**
    
- **rar (**necessita instalação)                       **rar a arquivo.rar arquivo** (a = opc ação)
    
    **rar x arquivo.rar - x = Descompactação**
    

ARQUIVADORES: Junta vários arquivos em um só, mas pode ser usado em conjunto com um compactador para armazenar arquvos compactados.

- **tar -** arquivador usado ate no sistema
    
    **tar -cf arquivo.txt.tar  arquivo.txt**
    
     - **Descompactação** - **tambem retira  arquivamento, na descompactação comum manten-se o arquivamento** (gzip arquvios.tar = **tar.gz**).
    
     ****- **tar -xvf arquivo.tar.gz** (-xvf = descompacta)
    
    **-C ~/Documentos** (opção para escolher diretório, usado no final)
    
    ---
    
    ### Pacotes
    
    *São programas colocados dentro de um arquivo identificados por sua extensão, e incluem arquivos necessários para a insalação de programa.* 
    
    **Gerenciadores** de Pacotes são sistemas que possume resolução automática de dependência entre pacotes, método fácil de instalação de pacotes. (dpkg, pat e yum)
    
    - **apt**
        
        sudo apt install pacote
        
        sudo apt upgrade pacote
        
        sudo apt remove pacote
        
        **ATUALIZAÇÂO DO SISTEMA (**bibliotecas, arquivos, programas)
        
        **apt update && apt upgrade**
        
        SITES DE PACOTES
        
        - **pkgs.org**
        - **rpm.pbone.net**
        
    - **dpkg** (gerenciador pacotes que serve para insalar .deb)
        
        **sudo dpkg -i** (instalar pacotes)
        
        **sudo dpkg -I pacote.deb** (info do pacote)
        
        **sudo dpkg -r nomedopacote** (remoção do pacote sem o ‘.deb’ no nome)
        
    
    ---
    
    **DIVERSOS**
    
    **alias** (apelidos) ex: alias hh=’history’
    
    **nl** (numbers of line) ex: nl texto.txt
    
    **wc -l** texto.txt (conta linhas e espaços, **-w**[conta palavras] )
    
    **cmp** (comparação arquivos texto) 
    
    **diff** (diferença arq textk)
    **sort -n** (organiza saida de arquivo texto em ordem numerica)
    
    **last reboot** (info de reinicialização do sistema)
    
    **route -n** (mostra todas as tabelas de roteamento IP do kernel)
    
    **time** (mostra o tempo de um processo) ex: time treceroute www.google.com.b r
    
    **uptime** (tempo que o sistema esta rodando) 
    
    **cowsay -d -g -f“ “ xcowsay**
    
    REINICIAR - **reboot, shutdown -r, init 0, telinit 0, halt**
    
    **seq** (imprime sequencia de numeros, ex: seq 1 10)
    
    **whereis** (exibe caminho do program e manual)
    
    **which** (exibe caminho de um programa)
    
    **logout** (finaliza sessão)
    
    ---
    
    ---
    
    ## Fedora .rmp
    
    getfedora.org/pt_BR/
    
    - **rpm -ivh pacote.rpm -** Instalação
        
         - **FALHA NAS DEPENDÊNCIAS - - nodeps**
        
        (rmp -ivh —nodeps)
        
        **rpm -U pacote.rpm** - Atualização
        
        **rpm -e pacote.rpm** - Remoção
        
    - **yum install pacote** - Instalação (gerenciador - download e inst)
        
        **yum update pacote** - atualização
        
        **yum remove pacote** - remoção
