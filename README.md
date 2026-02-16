# Laboratorio 1 Electronica Digital
<p text-align:center>
  
# Comparacion entre tencologias TTL y CMOS

<h3>1.Comparacion entre las especificaciones tecnicas del negador TTL 74LS04 y CMOS CD4069</h3>
Hay varios aspectos claves a comparar en los negadores debido a sus estructuras, la principal y mas importante es que el TTL se basa en transistores tipo BJT y los CMOS se basan en transistores MOSFET, a partir de ahi podes extraer varias diferencias mas claves

<h4>Volatje de operacion</h4>
CMOS CD4069:Tiene un amplio rango de operacion de voltaje, siendo este de entre 3V hasta 15V, siendo muy versatil para cualquier dispositivo
TTL 74LS04:Tiene una operacion muy estricta, siendo este de 5V, y si esto se sobrepasa, se dañara el chip

<h4>Consumo de energia</h4>
CMOS CD4069:Tiene un consumo de corriente estatico de unos cuantos micro-amperios, siendo de entre 1 a 4 μA
TTL 74LS04:Llega a tener un consumo de corriente estatico de hasta 33 mA

<h4>Velocidad de respuesta</h4>
CMOS CD4069:El tiempo de retardo de propagacion a 5V puede llegar a ser 90 ns, lo cual no disminuye mucho al llegar a 10V, que llega a ser 30 ns
TTL 74LS04:Puede llegar a tener un retardo de propagacion de 12 ns

<h4>Capacidad de manejo de corriente</h4>
CMOS CD4069:Es capaz de tener una corriente de drenaje de hasta 16mA,
TTL 74LS04:A un voltaje de 5V, solo puede llegar a tener una corriente de salida de 0.44mA, siendo esta muy baja incluso para intentar encender un LED

<h3>2.Comparacion entre los circuitos basados en el negador TTL 74LS04 y CMOS CD4069</h3>
<h4>CMOS CD4069</h4>

![image](https://github.com/JOUNAL/Laboratorio-1-Digital/blob/main/Imagenes/Negador%20CMOS.png)
Por como se compone este circuito, podemos observar que se compone de dos transistores MOSFET, uno con canal P y otro con canal N, y se interpreta de la siguiente de la manera, si se introduce una señal, el transistor con canal tipo P se apaga, impidiendo el paso de señal, sacando un 0 logico, y si se resive una señal baja, el transistor con canal N se prende, permitiendo la señal, sacando un 1 logico
</p>
<h4>TTL 74LS068 CD4069</h4>

![image](https://github.com/JOUNAL/Laboratorio-1-Digital/blob/main/Imagenes/Negador%20TTL.png)
El comportamiento del inveror tipo TTL es simple, si se introduce una señal baja, el transistor NPN no se prende, por lo que toda la corriente se va por la resistencia de salida, y si se envia una señal, el transistor se prende, por lo que genera un corto para la resistencia de salida, provocando un 0 logico

<h3>3.Mediciones teoricas y practicas para diferentes voltajes de cada uno de los inversores</h3>
Para observar los voltajes de salida vamos a ver una comparacion entre el montaje experimental y teorico con el inversor CMOS CD4069
A continuacion se ve el montaje experimental:

![image](https://github.com/JOUNAL/Laboratorio-1-Digital/blob/main/Imagenes/CMOS_montaje.jpg)
Para los voltajes de salida y de entrada se observo lo siguiente

![image](https://github.com/JOUNAL/Laboratorio-1-Digital/blob/main/Imagenes/CMOS_VOHL.jpg)
Se puede evidenciar un voltaje VOH = 5V y un voltaje VOL = 0V, comprobando un funcionamiento correcto del inversor
Y voltajes VIH = 4.24V y un voltaje VIL = 0.52V, observando que tiene un rango algo corto para cambiar de estado logico

<h3>4.Mediciones de diferentes tiempos</h3>

![image](https://github.com/JOUNAL/Laboratorio-1-Digital/blob/main/Imagenes/CMOS_TR.jpg)
Se obtiene el primer timepo conocido como el tiempo de subida que nos indica cuanto tiempo tarda de pasar del 10% al 90% en el voltaje de salida al introducir un 0 logico, dando como resultado un tiempo de 383 ns

![image](https://github.com/JOUNAL/Laboratorio-1-Digital/blob/main/Imagenes/CMOS_TF.jpg)
Para el segundo tiempo conocido como tiempo de bajada que nos indica cuanto tiempo tarda de pasar del 90% al 10% en el voltaje de salida al introducir un 1 logico, dando como resultado un tiempo de 156 ns

Ahora con las graficas obtenidas vemos dos tiempos mas, los tiempos de retardo, que son cuando cada una de las curvas pasa del 50%, ya sea subiendo o bajando, lo cual nos da dos tiempos, tplh = 100 ns y tphl = 77 ns


<h3>5.Determinacion de Fan-in y Fan-out de cada uno de los dispositivos</h3>
Para el CMOS CD4069:
Fan-in(Carga de entrada): Tecnicamente es 0 gracias a su alta impedancia, lo que hace que solo llegue a consumir picoamperios
Fan-out(capacidad de salida): Pueden llegar a conectarse 50, ya que las entradas no consumen corriente, pero mas lentos seran los francos de subida y de bajada entre mas se conecten

Para el TTL 74LS04:
Fan-in(Carga de entrada): Una carga unitaria, que es alrededor de 1.6 mA, y esto lo tiene que consumir por que la entrada emite corriente hacia afuera, algo que la etapa anterior debe drenar
Fan-out(capacidad de salida): Un TTL estandar puede drenar hasta 16 mA de corriente en estado bajo sin que el voltaje suba demasiado, por lo que puede conectarse hasta a otros 10 sin afectarlo mucho

<h3>6.Determinar la potencia disipada</h3>
CMOS CD4069: El inversor a base de tecnologia CMOS solo consume energia cuando cambia de estado logico, y cuando esta en estado estatico su consumo es infimo
Estado estatico: Consume alrededor de 1 μA a temperatura ambiente, dando como resultado si se usa un voltaje directo de 5Vcc de 5 V x 1 μA = 5 μW
Estado dinamico: En este estado, depdende mucho de la frecuencia a la cual se esta manejando el dispositivo usando la siguiente ecuacion Pd = (Cpd + Cl) * Vdd^2 * f, donde Cpd es la capacitancia interna de dispipacion (12 pF), Cl es la suma de todas las capacitancias externas, y f es la frecuencia que se esta manejando, lo que nos puede dar potencias disipadas de 0.01 mW para velocidades bajas (1kHz) hasta de 100 mW para velocidades altas (10 mHz)

TTL 74LS04:La potencia consumida del TTL es constante, ya que consume corriente incluso si no esta haciendo ningun trabajo, ya que los transistores BJT y resistencias estan constantemente consumiendo corriente, la corriente suele rondar los 33 mA, lo que nos da una potencia disipada, teniendo en cuenta 5 Vcc, de 165 mW y esto es independiente de la frecuencia a la cual este trabajando

<h3>7.Determinar la potencia disipada</h3>

<h3>8.Comportamiento de las compuertas al tener un pin al "aire"</h3>
TTL 74LS04: Se interpreta como un 1 logico ya que la estar al aire, la corriente no puede salir, haciendo que el voltaje interno suba y el circuito asuma un nivel alto
CMOS CD4069: Debido a su impedancia casi infinita, se comporta como un condensador altamente sensible, capaz de actuar como una antena y por ende captar cual tipo de señal del entorno, lo que hace eque pueda entrar a señal alta o baja dependiendo del ruido externo
