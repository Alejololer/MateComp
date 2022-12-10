# MateComp
## Sistemas
Determinista: Se sabe con toda certeza lo que pasará

Probabilístico: Tiene patrones de comportamiento que se pueden usar para predecir

Aleatorio: Sin patrones de comportamiento que se puedan usar, impredecible
##Lenguajes Formales
Consisten en la matematización de los instintos
##Resolución de problemas
-Estado inicial
-Función sucesor (devuelve los posibles estados siguientes)
-Espacio de estados (conjunto de todos los estados alcanzables)
-Estado objetivo
-Camino (secuencia de estados que comienza en el estado inicial)
-Una solución de un problema es un camino que parte del estado inicial y acaba en un estado objetivo)

Se tiene dos jarras de agua, una de 4l y otra de 3l sin escala de medición. Se desea tener 2l de agua en la jarra de 4l.

Las siguientes operaciones son válidas:
-Llenar totalmente una jarra;
-Tirar totalmente el agua de una jarra
-Pasar agua de una jarra a otra hasta que la primera esté vacía o hasta que la segunda esté llena

Sol1    Sol2
4L 3L   4L 3L
0 0     0 0
0 3     4 0
3 0     1 3 
3 3     1 0
4 2     0 1
0 2     4 1 
2 0     2 3

##Formalización de problemas
El espacio de estados se define como: ((X,Y):X son los litros en la jarra de 4L con 0<=x<=4 y Y son los litros en la jarra de 3L)

1.Llenar la jarra de 4L:  Si (X,Y) AND x<4 ==>(4,Y)

2.Llenar la jarra de 3L:  Si (X,Y) AND Y=3 ==>(X,3)

3.Vaciar la jarra de 4L:  Si (X,Y) AND X>0 ==>(0,Y)

4.Vaciar la jarra de 3L:  Si (Z,Y) AND Y>0 ==>(X,0)

5.Pasar agua de la jarra de 4L a la jarra de 3L hasta llenarla: Si (X,Y) AND X>0 AND X+Y>=3 ==>(X-(3-Y),3)

6.Pasar agua de la jarra de 3L a la jarra de 4L hasta llenarla: Si (X,Y) AND Y>0 AND X+Y>=4 ==>(4,Y-(4-x))

7.Pasar toda el agua de la jarra el 4L a la jarra de 3L: Si (X,Y) AND X>0 AND X+Y<3 ==>(0,X+Y)

8.Pasar toda el agua de la jarra de 3L a la jarra de 4L: Si (X,Y) AND Y>0 ANDX+Y<4 ==>(X+Y,0)

Tipos de búsqueda para la solución:

Búsqueda primero en anchura

### Maquina de estados / Autómata finitos
Sea A={a,b} B={S0,S1,S2)-
Sea F de A en B.
F   a   b
S0  S0  S1
S1  S0  S2
S2  S2  S2

![image](https://user-images.githubusercontent.com/42527062/206855210-80f57152-2500-4277-9465-fdfd6dc3710f.png)

>No deterministas
Determinista pero mas de dos soluciones posibles.

Estado con doble circulo= Estado objetivo.
