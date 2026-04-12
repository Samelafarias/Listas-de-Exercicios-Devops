# 📄 Lista 05 - Análise de Logs no Linux
**Aluna:** Samela Farias

**Disciplina:** DevOPS

**Professor:** Renato William

Resolução das lista de atividades sobre Análise de Logs no Linux
___

## Observação
### 1. Listar os arquivos de log gerados:

```
    ls -l lab_logs/
```

### 2. Acompanhando os logs em tempo real:

```
    tail -f lab_logs/*.log
```

### 3. Explicando o papel dos seguintes serviços:
#### a. systemd 
Tem o papel de gerenciar os serviços do sistema operacional
#### b. node
Tem o papel de executara a aplicação javascript,podendo ser site ou sistema
#### c. mysql
É um banco de dados que tem como pape armazenar as informações
#### d. sshd
Tem como papel permitir o acesso remoto ao servidor


## Análise
### 4. Identifique erros da aplicação:
```
    grep "ERROR" lab_logs/app.log
```

### 5. Identifique falhas no banco:
```
    grep "ERROR" lab_logs/db.log
```

### 6. Detecte ataques SSH:
```
    grep "Failed password" lab_logs/auth.log
```

### 7. Verifique problemas de disco:
```
    grep "No space left" lab_logs/disk.log
```

## Desafio Finaltail
### 1. Crie um script chamado auto-heal.sh que:
- #### Detecte falhas na aplicação
- #### Detecte falhas no banco de dados 
- #### Detecte problemas de disco
- #### Exiba mensagens de alerta 
```
    nano auto-heal.sh
```
```
APP_LOG="lab_logs/app.log"
DB_LOG="lab_logs/db.log"
DISK_LOG="lab_logs/disk.log"

echo "--- Iniciando Verificação de Saúde do Sistema ---"

# 1. Detectar falhas na aplicação Node.js 
if grep -q "ERROR" $APP_LOG; then
    echo "[ALERTA] Erro crítico na aplicação Node.js detectado!" 
else
    echo "[OK] Aplicação operando normalmente."
fi

# 2. Detectar falhas no banco de dados MySQL [cite: 554]
if grep -q "Lost connection" $DB_LOG; then
    echo "[ALERTA] O Banco de Dados MySQL está fora do ar!" 
else
    echo "[OK] Banco de dados conectado."
ficlear

# 3. Detectar problemas de disco [cite: 555]
if grep -q "Disk usage at 98%" $DISK_LOG; then
    echo "[ALERTA] Espaço em disco insuficiente (98%)!" 
else
    echo "[OK] Espaço em disco suficiente."
fi

echo "--- Verificação concluída ---"
```
```
    chmod +x auto-heal.sh
```
```
    ./auto-heal.sh
```

## Questões para Discussão
### 1. Qual tipo de falha é mais crítica?
Dependendo do contexto pode ser a queda no banco de dados ou o disco cheio, pois caso o banco caia a aplcação não consegue salvar os dados, agora se o disco esta cheio o sistema não irá conseguir gerar novos logs.


### 2. Logs ajudam na prevenção de problemas?
Sim, eles vão ajudar a identificar comportamentos anormais antes que o sistema relamente caia.


### 3. Como automatizar respostas a incidentes?
Através de scripts de monitoramento e ferramentas de orquestração.


