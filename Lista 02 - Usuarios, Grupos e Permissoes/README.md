
# 📄 Lista 02 - Usuários, Grupos e Permissões
**Aluna:** Samela Farias

**Disciplina:** DevOPS

**Professor:** Renato William

Resolução das lista de atividades sobre usuários, grupos e permissões
___

## 1. Cadastre os usu ́arios alice, bob, carlos, daniel e erica.

```
	sudo adduser alice
	sudo adduser bob
	sudo adduser carlos
	sudo adduser daniel
	sudo adduser erica
```

## 2. Crie no seu diret ́orio home os diret ́orios producao, rh, financeiro e ti.

```
	mkdir ~/producao ~/rh ~/financeiro ~/ti
```

## 3. Cadastre os grupos funcionarios, gerentes e informatica.

```
	sudo groupadd funcionarios
	sudo groupadd gerentes
	sudo groupadd informatica
```
## 4. Colocar os usu ́arios dentro do grupo conforme abaixo:

```
	sudo usermod -aG funcionarios alice && sudo usermod -aG funcionarios daniel && sudo usermod -aG funcionarios erica
	sudo usermod -aG gerentes bob && sudo usermod -aG gerentes carlos
	sudo usermod -aG informatica carlos && sudo usermod -aG informatica alice
```
## 5. Alterar o usu ́ario dono dos diret ́orios conforme abaixo:

```
	sudo chown bob:funcionarios ~/producao
	sudo chown erica:gerentes ~/rh
	sudo chown bob:gerentes ~/financeiro
	sudo chown carlos:informatica ~/ti
```

## 6. Altere as permiss ̃oes dos diret ́orios conforme abaixo:
- **Produção -**

  - Modo octal - `sudo chmod 474 ~/producao`
  - Modo literal - `sudo chmod u=r,g=rwx,o=r ~/producao`
- **RH -**

  - Modo octal - `sudo chmod 070 ~/rh`
  - Modo literal - `sudo chmod u-rwx,g=rwx,o-rwx ~/rh`
- **Financeiro -**

  - Modo octal - `sudo chmod 430 ~/financeiro`
  - Modo literal - `sudo chmod u=r,g=wx,o-rwx ~/financeiro`
- **TI -**

  - Modo octal - `sudo chmod 740 ~/ti`
  - Modo literal - `sudo chmod u=rwx,g=r,o-rwx ~/ti`

   
## 7.Supondo os detalhes dos arquivos pertencentes a um determinado diret ́orio, analise
a figura 1 e responda o que se pede:
### a. Quais os nomes dos diret ́orios contidos nessa relacão? Qual o nome do arquivos contidos nesta relacão?
- Diretórios (começam com 'd'): `pgms, teste1, teste2, Faturamento.`
- Arquivos (começam com '-'): `Controle, mbox, exemplo, Linux. `
### b. Existe algum usu ́ario do mesmo grupo de Rui? Caso positivo, qual?
- Sim: Rui, Pedro e Tiago pertencem ao grupo `Contab`.
### c. Qual o tamanho do arquivo Controle?
- 1565 bytes
### d. Quais as permiss ̃oes de acesso que os usu ́arios do mesmo grupo de Jo ̃ao possuem para acessar o arquivo Controle?
- O grupo de João é `Financ`. No arquivo Controle, as permissões do grupo (rw-) permitem Leitura e Gravação (Escrita).
### e. Eu sou do grupo do usu ́ario Pedro, que permissões tenho com relacão ao arquivo exemplo?
- O grupo de Pedro é `Contab`. No arquivo exemplo, o grupo tem permissões `r-x`, ou seja, Leitura e Execução. 
### f. Diga o comando completo para permitir que os usu ́arios do mesmo grupo de Rui possam ler e gravar, mas n ̃ao possam executar o arquivo Linux.
- `chmod g=rw,g-x Linux` ou `chmod 764 Linux` (considerando que o dono mantém rwx e outros r).
### g. Qual o c ́odigo octal para a permissão de acesso do arquivo exemplo.
- As permissões são `-rwxr-xr-x`, que equivalem a 755.
### h. Qual o c ́odigo literal para a permiss ̃ao de acesso do arquivo exemplo.
- `rwxr-xr-x.`
### i. Altere o dono do arquivo Linux para Rui.
- `sudo chown Rui Linux`
### j. Altere o grupo do arquivo Linux para Staff.
- `sudo chgrp staff Linux`
