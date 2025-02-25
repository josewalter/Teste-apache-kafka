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

