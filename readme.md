


// First, run RabbitMQ in docker

▶ docker run -itd --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.9-management


http://localhost:15672/

User: guest
Pass: guest






// Then, install amqp using go get:

▶ go mod init Golang-RabbitMQ

▶ go get github.com/rabbitmq/amqp091-go





// Now, send the message to the channel

▶ go run send.go                       
2022/01/26 11:58:32  [x] Sent Hello World!


// And, receive the message from the channel

▶ go run receive.go 
2022/01/26 12:17:38  [*] Waiting for messages. To exit press CTRL+C
2022/01/26 12:17:38 Received a message: Hello World!
