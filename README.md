# Integrantes:
Gonzalez Ana.
Gonzalez Iara.
Kevarkian Candela.
# Proyecto: Contador de números y contador de números primos.
![Captura de Pantalla 2023-10-19 a la(s) 11 11 06](https://github.com/iaragonzalezzz/Parcial-SPD.-2/assets/123982656/810268d1-32fd-4e4d-809f-30d81dc2ef12)
# Descripción:
Se va a sustituir uno de los botones por un interruptor (switch) de dos posiciones.
Dependiendo de la posición del interruptor, el display va a mostrar el contador de los números comunes o los números primos en el rango de 0 a 99.
# Función principal:
esta función se encarga de (dependiendo de que lado este el interruptor del switch) aumente o disminuye el valor de los números comunes o de los números primos.

void loop()
 { 
  //Declaramos las variables que vamos a usar
  int estado_switch = digitalRead(SWITCH) ;
  int apretado = boton_apretado();
  int sensor_fuerza = analogRead(FUERZA);
  
  
  //Si la fuerza que detecta el sensor es mayor a 4N
  aproximadamente el contador vuelve a 0*/
  if(sensor_fuerza > 80){
    contador = 0;
    }

 //Evalua si el switch esta del lado derecho, y se ejecuta el 
  contador, disminuyendo o aumentando el numero, 
  dependiendo del pulsador seleccionado 
  
  if(estado_switch == 0){
    
	if(apretado == PULSADOR_SUBE){
    	contador++;
      	if(contador > 99){
        	contador = 0;
        }
    }
  	else if(apretado == PULSADOR_BAJA)
    {
    	contador--;
      	if(contador < 0){
        	contador = 99;
        }
    }
    
   }
   // Si el switch esta del lado izquierdo, va a mostrar solo los
   numeros primos, en orden creiente o decreciente 
   segun el pulsador seleccionado 
   
  else {
    int divisores_totales = 0;
    
    if(apretado == PULSADOR_SUBE){
    	contador++;
      for(int i = 1; i <=contador; i++){ 
      	if (contador% i == 0){ 
          divisores_totales++;
       	 }
      }
      /*Si el numero tiene mas de dos divisores, o uno solo,
      y por lo tanto no es primo, el contador aumenta para mostar
      el siguiente numero primo */
      while (divisores_totales == 1 || divisores_totales > 2){
        if(apretado == PULSADOR_SUBE){
          contador++;
          }
      	if(contador > 97){
        	contador = 0;
         }
        divisores_totales = 0;
        for(int i = 1; i <=contador; i++){ 
      	if (contador% i == 0){ 
          divisores_totales++;
       	 }
      }
        
    }
       }
    else if(apretado == PULSADOR_BAJA){
    	contador--;
      
      for(int i = 1; i <=contador; i++){ 
      	if (contador% i == 0){ 
          divisores_totales++;
       	 }
      }
      while ( divisores_totales > 2 || divisores_totales == 1){
        if(apretado == PULSADOR_BAJA){
          contador--;
        }
         if(contador < 0){
           	contador = 97;
          }
        divisores_totales = 0;
        for(int i = 1; i <=contador; i++){ 
      		if (contador% i == 0){ 
          		divisores_totales++;
       	 	}
     	 }
        
      }
 
   		}
  
  }
  
  display_contador(contador);
}


# 🫡 Link del proyecto:
https://www.tinkercad.com/things/d7kpLeFhFGI

#Imagen con el motor
![Captura de Pantalla 2023-10-19 a la(s) 11 39 15](https://github.com/iaragonzalezzz/Parcial-SPD.-2/assets/123982656/439e2d3c-f4e4-4c08-a054-f59abf77a987)

