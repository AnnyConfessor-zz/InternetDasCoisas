<!DOCTYPE html>
<html>
  <head>
    <title>Internet das Coisas</title>
  </head>
  <body>

    <h1>Bem vindos ao meu primeiro site com IoT</h1>
    <p>Em breve adicionarei informações de vários sensores</p>
    <a href="http://www.google.com">Ir para página de busca</a>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/QSIPNhOiMoE" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


<!DOCTYPE html>
<html>
  <head>
    <title>IoT ECT</title>
    <script>
        //criar váriavel global
        var count=1;
        //definição de função para envio de dados para o thinkspeak
        function sendToAPI(lux) {
          //gera um número randomico entre 1 e 100
          count=Math.floor((Math.random() * 100) + 1);
          //criar um objeto capaz de enviar dados via requisição HTTP GET
          const http = new XMLHttpRequest()
          //prepara um GET passando a váriavel lux como ultimo paramentro do link
          http.open("GET", "https://api.thingspeak.com/update?api_key=OYUIUNJVJ995AK6C&field1="+lux)
          //envia um GET
          http.send()
          //quando a requisição retornar ele chama o console e imprime o valor gerado
          http.onload = console.log(http.responseText+" "+lux)
        }
        //a função de envio de dados é chamada de 3 em 3 segundos
        setInterval( function() { sendToAPI(count) }, 3000);

    </script>
  </head>

  <body>

  <h1>Praticando Javascript com Iot</h1>
  <p>De 3 em 3 segundos enviando número randomico para o thinkspeak</p>
  <iframe width="450" height="260" style="border: 1px solid #cccccc;" src="https://thingspeak.com/channels/709914/charts/1?bgcolor=%23ffffff&color=%23d62020&dynamic=true&results=60&type=line"></iframe>
  </body>
</html>