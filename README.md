# TrabajoPrimerParcialSPD
## Integrantes
-Lautaro Muller

-Julián Nario

-Eduardo Prina Valcarce
## Proyecto: Primer Parcial SPD
![Tinkercad](https://github.com/EduardoValcarce/TrabajoPrimerParcialSPD/blob/19f5b60005a732311d3d2505ae2bd3239108108d/Imagenes/ProyectoSPD.PNG)
## Descripcion
El proyecto consiste de dos displays de siete segmentos conectados a una placa arduino los cuales cumplen con la funcion de mostrar los numeros del 00 al 99 gracias a dos botones que aumentan o disminuyen su valor. Ademas, cuenta con un boton deslizante (switch) que hace que cambie de funcion, ya sea aumentar o disminuir el numero mostrado en uno o puede hacer que muestre solamente los numeros primos. El proyecto cuenta ademas con un sensor de temperatura el cual enciende o apaga tres leds dependiendo de la temperatura seleccionada.
## Funciones Principales
Esta funcion es el loop principal del codigo. En ella analizamos los datos que nos provee el usuario y el codigo actua en consecuencia. Nos indica cuando el usuario aprieta alguno de los botones para aumentar o disminuir el numero mostrado en los displays y guardamos el dato en un contador. Ademas, nos indica si el switch de los numeros primos esta activado o no y tambien hace uso de la funcion del sensor de temperatura.
~~~ C
void loop()
{
  int pressed = keypressed();//SUBE-BAJA-0
  if(pressed==SUBE)
  {
    countDigit++;
    if(countDigit>99)//si pasa 99 lo ponemos en 0
      countDigit=0;
  }
  else if(pressed==BAJA)
  {
    countDigit--;
    if(countDigit<0)//si pasa 0 lo ponemos en 99
      countDigit=99;
  }
  interruptor = digitalRead(INTERRUPTOR);
  if(interruptor==1)
  //Si el interruptor esta en 1 tenemos que mostrar solo los primos
  {
  	countDigit = esPrimo(countDigit,pressed);
    //Pasamos el contador actual y el boton que se apreto y nos devuelve el nuevo valor a mostrar
  }
  printCount(countDigit);//Le pasamos el valor del contador a printCount para que indique que mostrar

  sensorTemperatura();
}
~~~
## Link al proyecto
- [Proyecto](https://www.tinkercad.com/things/a064HU8mD1E)
