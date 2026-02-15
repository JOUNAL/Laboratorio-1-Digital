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

<h3>1.Comparacion entre los circuitos basados en el negador TTL 74LS04 y CMOS CD4069</h3>
<h4>CMOS CD4069</h4>

![image](https://github.com/JOUNAL/Laboratorio-1-Digital/blob/main/Imagenes/Negador%20CMOS.png)
Por como se compone este circuito, podemos observar que se compone de dos transistores MOSFET, uno con canal P y otro con canal N, y se interpreta de la siguiente de la manera, si se introduce una señal, el transistor con canal tipo P se apaga, impidiendo el paso de señal, sacando un 0 logico, y si se resive una señal baja, el transistor con canal N se prende, permitiendo la señal, sacando un 1 logico
</p>
<h4>TTL 74LS068 CD4069</h4>

![image](https://github.com/JOUNAL/Laboratorio-1-Digital/blob/main/Imagenes/Negador%20TTL.png)
El comportamiento del inveror tipo TTL es simple, si se introduce una señal baja, el transistor NPN no se prende, por lo que toda la corriente se va por la resistencia de salida, y si se envia una señal, el transistor se prende, por lo que genera un corto para la resistencia de salida, provocando un 0 logico
