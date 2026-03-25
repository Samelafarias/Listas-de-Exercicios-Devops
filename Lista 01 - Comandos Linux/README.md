# 📄 Lista 01 - Comandos Linux
**Aluna:** Samela Farias

**Disciplina:** DevOPS

**Professor:** Renato William

Resolução das lista de atividades sobre comandos linux
___

## 1 - Execute os comandos solicitados em cada item:
### a) COMANDOS PARA REINICIALIZAR OU DESLIGAR O COMPUTADOR
- i. Execute dois comandos para reinicializar o computador de forma imediata.
  
  `sudo shutdown -r now`
  
- ii. Agende o desligamento do seu PC em uma hora específica.
  
  `sudo shutdown -h 23:00`

- iii. Desligue seu PC depois de alguns minutos ou horas.]
  
  `sudo shutdown -h +5`
  
- iv. Desligue seu PC em um prazo de cinco minutos e informe através de uma mensagem a todos os usuários do sistema.
  
  `sudo shutdown -h +5 "O sistema será desligado em 5 minutos. Favor ficar atento!!!"`

### b) COMANDOS DE NAVEGAÇÃO
- i. Exiba o diretório corrente.
  
  `pwd`
  
- ii. Exiba o conteúdo do diretório do usuário corrente.

  `ls ~`
  
- iii. Exiba o Conteúdo do diretório corrente com uma listagem completa incluindo os arquivos ocultos.

  `la -la`
  
- iv. Exiba a árvore de diretórios do /etc/network.

  `tree/etc/network`

- v. Exiba uma lista completa e recursiva do diretório /etc/network.

  `ls -R /etc/network`

- vi. listagem longa do diretório home, com detalhes. O que significa cada coluna da listagem ?

  `ls -l ~`

- vii. listagem longa de "/etc", ordenada alfabeticamente

  `ls -l /etc`

- viii. listagem curta de "/usr", recursiva e ordenada por tamanho

  `ls -R /usr`

- ix. Suba um nível no diretório corrente.

  `cd ..`

- x. Retorne ao diretório do usuário

  `cd ~`

- xi. Mude para o diretório raiz

  `cd/`

- xii. Retorne de forma imediata ao diretório anterior

  `cd -`

### c) COMANDOS PARA LOCALIZAÇÃO DE ARQUIVOS
- i. Utilize o find para localizar um ou vários arquivos como o nome interfaces em/etc.

  `find /etc -name "interfaces"`
  
- ii. Use o comando find para encontrar todos os links simbólicos presentes em /usr.

  `find /usr -type l`
  
- iii. Repita o item anterior utilizando o comando locate.

  `locate /usr | grep -l`


### d) COMANDOS DE MANIPULAÇÃO DE ARQUIVOS E DIRETÓRIOS

- i. e ii. Criar a estrutura de diretórios (Figura 1) com o mínimo de comandos:

  `mkdir -p diretorio01/diretorio01_1 diretorio01/diretorio01_2 diretorio02/diretorio02_1 diretorio02/diretorio02_2/diretorio02_21 diretorio02/diretorio02_2/diretorio02_22 diretorio02/diretorio02_2/diretorio02_23`

- iii. Criar um arquivo chamado numeros.txt.

  `touch numeros.txt`

- iv. Inserir os seguintes números dentro do arquivo numeros.txt: 10. 100. 50. 34. 25. 1. 2. 56.
  
  `echo -e "10\n100\n50\n34\n25\n1\n2\n56" > numeros.txt`

- v. Criar um arquivo chamado disciplinas.txt.

  `touch disciplinas.txt`

- vi. Inserir os seguintes nomes dentro do arquivo disciplinas.txt: Gerência de Redes, Laboratório de Desenvolvimento de Sistemas, Lógica de Programação, Sistemas Operacionais, Governança de Tecnologia da Informação, Redes de Computadores

  `echo -e "Gerência de Redes\nLaboratório de Desenvolvimento de Sistemas\nLógica de Programação\nSistemas Operacionais\nGovernança de Tecnologia da Informação\nRedes de Computadores" > disciplinas.txt` 

- vii. Criar um arquivo chamado Lista Disciplinas.txt: 1. 2. 4. 6. 5.

  `echo -e "1.\n2.\n4.\n6.\n5." > Lista_Disciplinas.txt`

- viii. Duplicar o arquivo numeros.txt para numeros1.1.txt, numeros2.1.txt e numeros2.2.1.txt.

  ```
  
  cp numeros.txt numeros1.1.txt
  cp numeros.txt numeros2.1.txt
  cp numeros.txt numeros2.2.1.txt
  ```
  
- ix. Duplicar o arquivo numeros.txt para numeros1.1.num, numeros2.1.num e numeros2.2.1.num.

  ```
  cp numeros.txt numeros1.1.num
  cp numeros.txt numeros2.1.num
  cp numeros.txt numeros2.2.1.num
  ```

- x. Duplicar o arquivos disciplinas.txt para disciplinas1.txt, disciplinas2.txt e disciplinas2.2.3.txt.

  ```
  cp disciplinas.txt disciplinas1.txt
  cp disciplinas.txt disciplinas2.txt
  cp disciplinas.txt disciplinas2.2.3.txt
  ```
  
- xi. Mova os arquivos numeros1.1.num, numeros2.1.num e numeros2.2.1.num para os respectivos diretórios criados. Ex: numeros1.1.num para diretório 1.1.

  ```
  mv numeros1.1.num diretorio01/diretorio01_1/
  mv numeros2.1.num diretorio02/diretorio02_1/
  mv numeros2.2.1.num diretorio02/diretorio02_2/diretorio02_21/
  ```

- xii. Mova os arquivos numeros1.1.txt, numeros2.1.txt e numeros2.2.1.txt para os respectivos diretórios criados. Ex: numeros1.1.txt para diretório1.1.
  
  ```
  mv numeros1.1.txt diretorio01/diretorio01_1/
  mv numeros2.1.txt diretorio02/diretorio02_1/
  mv numeros2.2.1.txt diretorio02/diretorio02_2/diretorio02_21/
  ```
  
- xiii. Mova os arquivos disciplinas1.txt, disciplinas2.txt e disciplinas2.2.3.txt, faça da mesma forma da questão anterior.

  ```
  mv disciplinas1.txt diretorio01/
  mv disciplinas2.txt diretorio02/
  mv disciplinas2.2.3.txt diretorio02/diretorio02_2/diretorio02_23/
  ```
  
- xiv. Faça uma cópia de todos os diretórios e arquivos do diretório /etc/network para o diretorio01.
  
  `cp -r /etc/network/* diretorio01/`
  
- xv. Faça a renomeação do arquivo numeros.txt para numeros Atualizados.txt.

  `mv numeros.txt "numeros Atualizados.txt"`
  
- xvi. Execute o seguinte comando ping -c10 ww.google.com.br > request.txt

  `ping -c10 www.google.com.br > request.txt`
  
- xvii. Utilizando o comando rmdir tente remover o diretório1.2 e o diretório2.1, apresente o resultado.

  ```
  rmdir diretorio01/diretorio01_2
  rmdir diretorio02/diretorio02_1
  ```
  
- xviii. Remova todos os arquivos que terminem com num, faça isso de forma recursiva e exibindo o nome de cada arquivo antes de elimina-lo.

  `rm -rv *.num`

### e) COMANDOS DE FILTRAGEM E PAGINAÇÃO

- i. Mostre o conteúdo total do arquivo request.txt.

  `cat request.txt`
  
- ii. Mostre as primeiras cinco linhas do arquivo request.txt.

  `head -n 5 request.txt`
  
- iii. Mostre apenas a última linha do arquivo request.txt.

  `tail -n 1 request.txt`
  
- iv. Conte o número de linhas do arquivo request.txt.
  
  `wc -l request.txt`
  
- v. Mostre a quantidade de palavras do arquivo request.txt.

  `wc -w request.txt`
  
- vi. Substitua letras minúsculas por maiúsculas no arquivo disciplinas.txt, e numa mesma linha de execução faça essa substituição criando um novo arquivo chamado disciplinas-Maiusculas.txt.

  `tr '[:lower:]' '[:upper:]' < disciplinas.txt > disciplinasMaiusculas.txt`
  
- vii. Organize na ordem crescente os arquivos numeros Atualizados.txt e numa mesma linha de execução crie um arquivo chamado numeros Ordem Crescente.txt.

  `sort -n "numeros Atualizados.txt" > numeros_OrdemCrescente.txt`
  
- viii. Organize na ordem descrescente o arquivo numeros Atualizados.txt e numa mesma linha de execução crie um arquivo chamado numeros Ordem Des Crescente.txt.

   `sort -n "numeros Atualizados.txt" > numeros_OrdemDecrescente.txt`

- ix. Organize na ordem crescente o arquivo disciplinas.txt e numa mesma linha de execução crie um arquivo chamado disciplinas OrdemCrescente.txt.

  `sort disciplinas.txt > disciplinas_OrdemCrescente.txt`
  
- x. Organize na ordem crescente o arquivo Lista Disciplinas.txt e numa mesma linha de execução crie um arquivo chamado Lista Disciplinas Atualizada.txt.
  
  `sort Lista_Disciplinas.txt > Lista_Disciplinas_Atualizada.txt`
  
- xi. Cole o conteúdo do arquivo Lista Disciplinas.txt com o conteúdo do arquivo disciplinas.txt e gere um novo arquivo chamado listanumerada.txt.

  `paste Lista_Disciplinas.txt disciplinas.txt > listanumerada.txt`
  
- xii. Mostre apenas a primeira coluna do arquivo request.txt.

  `awk '{print $1}' request.txt`
  
- xiii. Mostre apenas a coluna que contém os tempos de cada requisição ping do arquivo request.txt.

  `grep "time=" request.txt | awk -F'time=' '{print $2}' | awk '{print $1}'`
  
- xiv. Mostre apenas a coluna que contém o endereço ip do arquivo request.txt.

  `grep -oE "\b([0-9]{1,3}\.){3}[0-9]{1,3}\b" request.txt`


## 2 - Nas distribuições Linux, as principais bibliotecas de sistema e os arquivos de configuração e scripts de inicialização ficam armazenados em quais diretórios?
As configurações e script de inicialização constumam ficar em `/etc` e as bibliotcas do sistema constuma ficar em `/lib` ou `/usr/lib`

## 3 - Descreva o que é o ping e em que casos ele é utilizado ?
O ping é um utilitário que usa o protocolo ICMP para testar a conectividade entre nós de uma rede. Ele é utilizado para verificar se um host está ativo e medir o tempo de latência (RTT).

## 4 - Na Figura 3 é apresentada uma LAN, com dispositivos finais e um Switch, defina um endereço ip para cada um dos dispositivos finais, seguindo o que se pede abaixo:

### Atribuição de Endereços 
#### Sub-rede de Computadores
* **PC 01:** 192.168.100.10
* **PC 02:** 192.168.100.11
* **PC 03:** 192.168.100.12
* **Máscara:** 255.255.255.128

#### Sub-rede de Telefones 
* **Telefone IP 01:** 192.168.100.130
* **Máscara:** 255.255.255.128

#### Servidor 
* **Servidor:** 192.168.100.1
* **Função:** Atua como Gateway Padrão para permitir que os dispositivos das duas sub-redes se comuniquem entre si e com a Internet.


