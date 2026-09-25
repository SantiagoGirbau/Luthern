---
aliases:
  - Tendón
  - Arco de Carroña
tags:
  - Arma
  - Objeto
  - Hombrew
Estado: Terminado
---
[[Objeto Mágico]] 
*Bonificador de +1 al ataque.*
**Arco de Carroña** _Arma (arco), poco común_
**Requisito de uso:** 13 de Fue.

_Este macabro arco, tensado con tendones resecos y fabricado a partir de huesos, ha sido diseñado específicamente para disparar flechas talladas en restos óseos de animales. Su tensión es tan extrema que proyecta la munición a velocidades letales._

**Tiro Perforante.** Las flechas disparadas por este arco viajan con una fuerza brutal, atravesando al objetivo. Cuando impactas a una criatura, la flecha continúa su trayectoria e impacta a la siguiente criatura que se encuentre directamente detrás de la primera, infligiéndole el mismo daño, siempre y cuando el total de tu tirada de ataque original menos 2 (-2) iguale o supere la Clase de Armadura (CA) del siguiente objetivo. este proceso se repite para cualquier cantidad de criaturas alineadas siempre que el ataque no falle.
En caso de que el ataque sea un crítico atraviesa a todos las criaturas que hayan en la trayectoria del mismo.

```
paraPegar = 1d20 + jugador.Dex + jugador.EsComp(Tendón.Tipo)*jugador.Comp + 1
While (tiradaDeAtaque >= enemigo[n].AC && isNotNull(Enemigo[n])){
	int daño = Tendón.tirarDadosDaño(jugador);
	enemigo[n].vidaRestante -= daño;
	tiradaDeAtaque -= 2;
	n++;
	}
	
// jugador.EsComp(arma.Tipo) recibe un tipo de arma y devuelve 1 si el jugador es competente con tipo de arma y 0 en caso contrario
// arma.tirarDadosDaño() recibe a un jugador y calcula automáticamente el daño del arma en base al daño máximo y bonificadores (Mal acoplamiento)
//dios mío me puse a pensar soluciones para el acoplamiento refactorizando los cálculos de daño y ataque en métodos dentro de la clase enemigo y jugador. Tengo problemas.
```

||**Pasiva, Extensión de mi carne:** Al sintonizarte con este arco, tu cuerpo piensa que el arco forma parte de él. Al tensarlo y manipularlo, puedes sentir cómo el arco forma parte de tu cuerpo. Este arco está maldito y no puede de-sintonizarse de ella sin utilizar un hechizo para retirar la maldición.||