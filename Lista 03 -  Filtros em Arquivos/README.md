# 📄 Lista 03 - Filtros em Arquivos
**Aluna:** Samela Farias

**Disciplina:** DevOPS

**Professor:** Renato William

Resolução das lista de atividades sobre filtros em arquivos
___

## 1. Alguém acaba de doar um laptop para sua escola e você deseja instalar Linux nele. 
### a. Usando os comandos grep e wc, exiba o número de processadores presentes.

```
  grep "processor" /proc/cpuinfo | wc -l
```

### b. Faça o mesmo com sed em vez de grep.

```
  sed -n '/processor/p' /proc/cpuinfo | wc -l
```

## 2. Explore seu arquivo local /etc/passwd com os comandos grep, sed, head e tail de acordo com as tarefas descritas abaixo:
### a. Quais usu ́arios tˆem acesso a um shell Bash?
```
  grep "/bin/bash" /etc/passwd 
```

### b. Muitos dos usu ́arios de seu sistema existem para lidar com programas específicos ou para fins administrativos. Eles não têm acesso a um shell. Quantos deles estão presentes no sistema?
```
  grep -v "/bin/bash" /etc/passwd | wc -l
```

### c. Quantos usu ́arios e grupos existem em seu sistema (lembre-se: use apenas o arquivo /etc/passwd)?
```
  wc -l /etc/passwd
```

### d. Liste apenas a primeira, a  ́ultima e a d ́ecima linha do arquivo /etc/passw
```
  (head -n 1 /etc/passwd; sed -n '10p' /etc/passwd; tail -n 1 /etc/passwd)
```

## 3. Considere este arquivo de exemplo /etc/passwd. Copie as linhas abaixo para um arquivo local chamado ‘mypasswd para este exercício.
### a. Liste todos os usu ́arios no grupo 1000 (use sed para selecionar apenas o campo apropriado) do arquivo mypasswd.
```
  sed -n '/:1000:/p' mypasswd
```
### b. Liste apenas o nome completo de todos os usu ́arios deste grupo (use sed e cut).
```
  grep ":1000:" mypasswd | cut -d: -f5
```

## 4. Usando novamente o arquivo mypasswd dos exercícios anteriores, imagine um comando Bash que selecione um indivíduo do Main Office para ganhar uma rifa. Use o comando sed para imprimir apenas as linhas do Main Office e, em seguida, uma sequência de comando cut para recuperar o primeiro nome de cada usuário a partir dessas linhas. Depois, classifique esses nomes aleatoriamente e imprima apenas onome principal da lista.
```
  sed -n '/Main Office/p' mypasswd | cut -d: -f5 | cut -d' ' -f1 | shuf -n 1
```
