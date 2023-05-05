<h2>Tuturial para rodar um servidor usando node.js</h2>
<hr>
<p>Esse código é um exemplo de um servidor HTTP básico escrito em Node.js. Ele utiliza o módulo http do Node.js para criar um servidor que escuta conexões na porta 3000 do endereço IP local 127.0.0.1.</p>

<strong>esse código cria um servidor web simples que responde com a mensagem "TESTANDO" para qualquer requisição HTTP feita na porta e endereço IP definidos.</strong>
<hr>
<h4>Vamos analisar o código em detalhes:</h4><br>

<p>A primeira linha importa o módulo http do Node.js. Este módulo fornece funcionalidades para criar servidores HTTP e fazer solicitações HTTP.</p>

```javascript
const http = require("http");
```
<p>As duas linhas seguintes definem o endereço IP e a porta em que o servidor irá escutar as conexões.</p>

```javascript
const hostname = "127.0.0.1";
const port = 3000;
```
```javascript
const server = http.createServer((req,res) =>{
   res.statusCode = 200;
   res.setHeader("Content-Type","text/plain");
   res.end("TESTANDO")
});
```
<p>Aqui,criamos um servidor HTTP,utilizando a função createServer() do módulo http. Essa função recebe uma função de callback que é executada cada vez que uma solicitação HTTP é recebida pelo servidor. A função de callback recebe dois parâmetros, req e res.

O req contém informações sobre a solicitação HTTP recebida, como a URL solicitada e os cabeçalhos HTTP, e o res é um objeto que representa a resposta HTTP que será enviada de volta para o cliente.

Nesse exemplo, a função de callback simplesmente configura a resposta do servidor com um status de código 200 (OK), define o tipo de conteúdo como text/plain e envia a mensagem "TESTANDO" como corpo da resposta.</p>

```javascript
server.listen(port,hostname,() =>{
  console.log("Server Rodando")
})
```
<p>Chamamos a função listen do objeto servidor para iniciar o servidor e começar a escutar as conexões. Esta função recebe três argumentos: a porta em que o servidor deve escutar, o endereço IP em que o servidor deve escutar e uma função de callback opcional que é executada quando o servidor começa a escutar as conexões.

Neste exemplo, o servidor está configurado para escutar as conexões na porta 3000 do endereço IP local 127.0.0.1. Quando o servidor começa a escutar as conexões, a função de callback simplesmente imprime a mensagem Server Rodando no console.</p>

