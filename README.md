# Teste-apache-kafka
Testing Kafka's features

# Comandos para o arquivo compose.yml
# 1° Passo:
Clone o projeto para a sua maquina.

# 2° Passo:
comando para subir o arquivo: docker-compose up -d

# 3° Passo:
Comando para ver se o arquivo subiu: docker-compose ps

# 4° Passo:
Comando para ver os logs gerados e os comando e arquivos que o Kafka gera e que vc vai
precisar para criar os topics e outras configurações: docker-compose logs

# 5° Passo:
Comando para subir o container do kafka:  docker exec -it kafka-kafka-1 bash

# 6° Passo:
Comando para ver como criar topics, excluir, apontar a porta para o container entre outros comandos: kafka-topics

# 7° Passo:
Comando para criar um topic, apontar a porta e outras configurações:
kafka-topics --create --topic=teste --bootstrap-server=localhost:9092 --partitions=3

# 8° Passo:
Comando para listar tudo que foi criado no container:
kafka-topics --list --bootstrap-server=localhost:9092 

# 9° Passo:
Comando para mostrar a lista com as partições criadas e mais algumas informações importantes do container kafka: 
kafka-topics --bootstrap-server=localhost:9092 --topic=teste --describe

# 10° Passo:
Comando para o kafka começar a consumir o topic: 
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste

# 11° Passo:
Comando para criar o producer: kafka-console-producer --bootstrap-server=localhost:9092 --topic=teste
Após dar o comando vc da um enter e digita a mensagem de umn enter que  a mensagem aparecerá no outro consoleque vc está logado.

# 12° Passo:
Se vc derrubar o serviço e continuar enviando mensagens e iniciar o servidor novamente elas não aparecerão, para essas mensagens aparecerem vc precisa digitar esse comando:
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste --from-beginning

# 13° Passo:
Se vc quer trabalhar com grupo para as suas partições deve executar esse comando em cada uma das partições:
kafka-console-consumer --bootstrap-server=localhost:9092 --topic=teste --group=x

# 14° Passo:
Esse comando permite que vc vejaa descrição do que cada partição esá lendo quantas mensagens o ID de cada partição logs
e etc...
kafka-consumer-groups --bootstrap-server=localhost:9092 --group=x --describe

# 15° Passo:
Link da ferramenta Confluent parceira do Kafka onde vc pode acessar e ver os dados do serviço la dentro,
vc vai poder ver os Brokers, consumers, topics entre outros detalhes dos brokers que estão sendo executados:
Link de acesso: http://localhost:9021/clusters

# 16° Passo:
Depois de criar o Dockerfile configurar o go dentro do Dockerfile e atu-
alizar o compose.yml, rodar o comando:
docker-compose up -d
Para subir novamente o kafka e e ele criar as novas configurações que vc fez, da um docker-compose ps para ver se a aplicação está no ar, e um docker logs teste-apache-kafka-kafka-1 para ver se todos os logs sobem sem nenhum erro.

# 17° Passo:
Para rodar o arquivo go digite esse comando dentro da pasta do projeto:
go run cmd/producer/main.go



