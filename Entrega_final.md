###### Responsável: Naydson A. V. Ayres
###### Curso: Análise e Desenvolvimento de Sistemas

 Todos os códigos foram adaptados e/ou rodados no próprio Prompt de Comando do Linux Mint.                  
 
### Trajetória:

* Primeiramente abrimos nosso Cmd.
* Realizamos o login com os dados.
* Acessamos nossa pasta particular.
* Agora vamos inserir o código fornecido chamado "le-anuncia-mqtt.c"
* Para isso colocamos no cmd o comando **nano le-anuncia-mqtt.c*
* Ja dentro do editor botamos o codigo correspondente, alteramos o topico, a mensagem e o comando de ativação; salvamos e fechamos.
* Agora compilamos nosso código com: **gcc le-anuncia-mqtt.c -o le-anuncia-mqtt**, continuamos e na proxima linha colocamos **./le-anuncia-mqtt**
* Abriremos o nano com o comando **nano publica-mqtt.c**.
* Dentro do editor coloca-se o código correspondente e alteramos o tópico e a mensagem.
* Compilamos com: **gcc publica-mqtt.c -o publica-mqtt**, na proxima linha inserimos **./publica-mqtt**.
#
#### Ver participantes ativos
  * Para vermos o codigo funcionando ditamos **mosquitto_sub -h broker.emqx.io -t pi2anaydson/comandos | ./le-anuncia-mqtt** em um primeiro terminal.
  * Abrimos um segundo terminal e escrevemos: **mosquitto_sub -h broker.emqx.io -t pi2anaydson/nomes** para subscrever no broker.
  * Agora por fim após abrir o terceiro terminal, vamos publicar a mensagem **_/nomes_**, com isso usamos o código: **mosquitto_pub -h broker.emqx.io -t pi2anaydson/comandos -m /nomes**.
  * Veremos que no segundo terminal aparecera o nomes dos que estiverem logados. 
#
*
