###### Responsável: Naydson A. V. Ayres
###### Curso: Análise e Desenvolvimento de Sistemas

 Todos os códigos foram adaptados e/ou rodados no próprio Prompt de Comando do Linux Mint.                  
 
### Trajetória/Resumo das atividades:

* Primeiramente abra o terminal e vamos compilar todos os codigos que precisamos.
* Faça o login com os dados.
* Acesse a pasta particular.
* Agora vamos inserir o código fornecido chamado "le-anuncia-mqtt.c"
* Para isso colocamos no cmd o comando ***nano le-anuncia-mqtt.c***
* Ja dentro do editor botamos o codigo correspondente, alteramos o topico, a mensagem e o comando de ativação; salvamos e fechamos.
* Agora compilarmos nosso código usamos: ***gcc le-anuncia-mqtt.c -o le-anuncia-mqtt***.
* Após, inserimos o comando ***nano publica-mqtt.c***.
* Dentro do editor coloque o código correspondente e altere o tópico e a mensagem, salve e feche.
* Compilamos com: ***gcc publica-mqtt.c -o publica-mqtt***.
* Colocamos a linha ***nano publica-frase-mqtt.c***
* Na parte interna do editor vamos editar somente o tópico; salvamos e saimos.
* Por fim, compilamos com o comando ***gcc publica-frase-mqtt.c -o publica-frase-mqtt***
#
#### Etapas 1 e 2 
  * Para ver o codigo funcionando ditamos ***mosquitto_sub -h broker.emqx.io -t pi2anaydson/comandos | ./le-anuncia-mqtt*** em um primeiro terminal.
  * Abra um segundo terminal e escreva: ***mosquitto_sub -h broker.emqx.io -t pi2anaydson/nomes*** para subscrever no tópico.
  * Agora por fim após abrir o terceiro terminal (logado), publique o comando ***./publica-mqtt***.
  * Veremos que no segundo terminal aparecera o nomes dos que estiverem logados. 
  
<div align="center">
<img src="https://user-images.githubusercontent.com/113566443/191646049-8d3328fa-d3ba-45be-9691-23f918614feb.png"width="700px" />
</div>
  
#
#### Etapas 3 e 4 
  * Abra um terminal e coloque o comando ***mosquitto_sub -h broker.emqx.io -t pi2anaydson/msgs***, para subscrever-se.
  * Abra outro terminal e após logar, escreva ***mosquitto_sub -h broker.emqx.io -t pi2anaydson/msgs | grep naydson*** (aqui podera ser usado qualquer palavra), para filtrar mensagens que contenham só a palavra **_naydson_**
  * Abra um terceiro terminal e logado, coloque ***./publica-frase-mqtt UCPel localiza-se em Pelotas***.
  * Notamos que esta mensagem aparecerá só no primeiro terminal, mas no segundo não; porque ela não caiu no nosso _grep_ (fitro), pois não foi escrito uma frase contendo a palavra **naydson**.
  * Vamos mudar o final do codigo, tente escrever: ***./publica-frase-mqtt naydson é aluno da ucpel***.
  * Agora sim ela aparecerá destacada no segundo terminal, porque a frase escrita continha a nossa palavra do filtro.

<div align="center">
<img src="https://user-images.githubusercontent.com/113566443/191892058-04bf35d7-d955-4963-a5ee-6a28676eb2f5.png"width="700px" />
</div>

##
##### link para acessar o video de apresentação do projeto:
[![foto entrega final](https://user-images.githubusercontent.com/113566443/192075182-f240b60b-6b3d-4b0b-9072-4a124f68d823.png)](https://youtu.be/nZZ_hliDKSc)

