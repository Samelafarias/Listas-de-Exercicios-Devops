# 📄 Lista 04 - Shell Script para Automação
**Aluna:** Samela Farias

**Disciplina:** DevOPS

**Professor:** Renato William

Resolução das lista de atividades sobre Shell Script para Automação
___

## Exercícios
### 1. Monitorar uso de disco

```
 #!/bin/bash
 df -h
```

### 2. Listar usuários logados

```
  #!/bin/bash
  who
```

### 3. Atualizar sistema
```
  #!/bin/bash
  sudo apt update && sudo apt upgrade -y
```

### 4. Menu interativo
```
  nano menu.sh

  #!/bin/bash
    while true; do
        echo "1- Listar Arquivos | 2- Data | 0- Sair"
        read opcao
        case $opcao in
            1) ls ;;
            2) date ;;
            0) break ;;
            *) echo "Opção inválida" ;;
        esac
    done
```
```
  chmod +x menu.sh

  ./menu.sh
```

### 5. Verificar site online
```
  nano questao05.sh

    #!/bin/bash
    read -p "Digite a URL: " site
    if ping -c 1 $site > /dev/null; then
        echo "O site $site está ONLINE"
    else
        echo "O site $site está OFFLINE"
    fi
```
```
  chmod +x questao05.sh

  ./questao05.sh
```

## Desafio
### 1. Desafio
```
nano desafio.sh

  #!/bin/bash

    DATA=$(date "+%Y-%m-%d %H:%M") 
    LOG_FILE="monitoramento.log"

    echo "--- Relatório de $DATA ---" >> $LOG_FILE

    # Monitorar CPU, Memória e Disco 
    echo "Uso de CPU:" >> $LOG_FILE
    top -bn1 | grep "Cpu(s)" >> $LOG_FILE

    echo "Uso de Memória:" >> $LOG_FILE
    free -h >> $LOG_FILE

    echo "Uso de Disco:" >> $LOG_FILE
    df -h / >> $LOG_FILE

    echo "Log gerado com sucesso em $LOG_FILE"
```

```
  chmod +x desafio.sh

  ./desafio.sh

  cat monitoramento.log
```

## Discussão
### 1. Onde usar automacão?
Em tarefas repetitivas, backups automáticos, deploys de código e configuração de novos servidores.

### 2. Qual script você usaria?
Os scripts de limpeza de logs antigos, verificação de segurança ou provisionamento de ambiente de desenvolvimento.

## 3. Como isso se aplica ao DevOps?
O Shell Script é a "cola" que integra diferentes ferramentas. Ele permite a redução de erros humanos, facilita a integração com CI/CD e garante que o gerenciamento de servidores seja escalável e previsível.
