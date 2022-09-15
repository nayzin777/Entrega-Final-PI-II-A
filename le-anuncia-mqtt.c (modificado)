#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main (void) {
   char linha[100];
   int compara;

   while (1){
   	scanf ("%[^\n]", linha);
   	setbuf(stdin, NULL);
   	compara = strcmp (linha, "/nomes");

   	if (compara == 0){
       		system("mosquitto_pub -h broker.emqx.io -t pi2anaydson/nomes -m Naydson");
	}
   }
   return EXIT_SUCCESS;
}
