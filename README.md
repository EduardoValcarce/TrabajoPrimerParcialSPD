# TrabajoPrimerParcialSPD
## Integrantes
-Lautaro Muller

-Julián Nario

-Eduardo Prina Valcarce
## Proyecto: Primer Parcial SPD
(Imagenes/ContadorArduino.PNG)
## Descripcion
El proyecto consiste de dos displays de siete segmentos conectados a una placa arduino los cuales cumplen con la funcion de mostrar los numeros del 0 al 99 gracias a dos botones que aumentan o disminuyen su valor. Ademas, cuenta con un boton de reset para volver a empezar desde el 0.
## Funcion Principal
En esta funcion analizamos que boton presiona el usuario y el codigo actua en consecuencia. Tiene la opcion de apretar tres botones y cada uno realizara distintas funciones dentro del codigo siempre afectando al contador CountDigit. Puede aumentar, disminuir o devolver a 0 al contador.
~~~ C (lenguaje en el que esta escrito)
void loop()
{
  int pressed = keypressed();//SUBE,BAJA,RESET,CERO
  if(pressed==SUBE)
    // si es igual a SUBE aumenta el contador
  {
    countDigit++;
    if(countDigit>99)
      //si el marcador llego a 99 lo devuelve a 0
      countDigit=0;
  }
  else if(pressed==BAJA)
  {
    countDigit--;
    if(countDigit<0)
      countDigit=99;
  }
  else if(pressed==RESET)
    //Si es igual a RESET devuelve el contador a 0
  {
    countDigit=0;
  }
  
  printCount(countDigit);
  //paso el valor de countDigit a printCount
}
~~~
## Link al proyecto
- [Proyecto](https://www.tinkercad.com/things/iAHjCldsvFA)
