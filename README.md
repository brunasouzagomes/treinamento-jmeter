# treinamento-jmeter

Treinamento presencial Testing Dojo UAI - 27/04

Analogia do garçom.

Testes de carga - avaliar os limites de processamento de um software.

Test Plan - conceito de container e iniciar inclusão de elementos:
- Thread Group - número de usuários, período de intervalo e qtde de loops
- Http Authorization Manager -  autenticação
- Http Request (sub Thread Group) - protocolo, nome servidor, parâmetros, body para Post (Json)

-----------------------------------------
# Parâmetros

Request com parâmetros no endpoint
Test Plan/Add/Config Element/User Defined Variables
No Endpoint usar: ${VARIAVEL}
SERVER NAME OR IP: ENDPOINT
PATH: RESOURCE


# POST Request
- Thread Group
- Http Header Manager - incluir Content-Type e Accept
- Criar Body com parâmetros

Validação de retorno de request: Sub Http Request (Add/Listener)
 - Validar o status retornado, header de retorno; body do response;
 - Aggregate Report: agrupa os testes
 - Result Tree
 - Summary Report

-----------------------------------------
# Randomizar variáveis no body

Opção 1: gerar variavel dinâmica
Thread Group/Add/Config Element/ Random Variable
- Exemplo: "email": "testesaymon_${RANDOM_EMAIL}@gmail.com"

Opção 2: JSR223 PreProcessor 

Banco de dados: JDBC Connector no Thread Group
- MongoDB, MySQL, Oracle, SQLServer etc...


------------------------------------------
# Command line running

C:\Jmeter\apache-jmeter-5.1.1\bin>jmeter -f -n -t "C:\Repositorio de Projetos\ApiDeTarefas.jmx" -l ApiDeTarefas.jtl -e -o "C:\JMeter_Report"

https://jmeter.apache.org/usermanual/get-started.html
https://www.blazemeter.com/blog/5-ways-launch-jmeter-test-without-using-jmeter-gui
