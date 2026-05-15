# Actividad-6.1-Seguimiento-de-Trayectorias-

En esta actividad se implementó un código en MATLAB en el que un robot diferencial debe de seguir una trayectoria definida por una función la cual debe seguir a lazo cerrado, controlando las ganancias de su velocidad lineal y angular.

Para que el robot siga la trayectoria con la mayor precisión posible, se siguieron los siguientes pasos:

- Primero, para el caluclo de velocidad se debe caluclar la derivada de la trayectoria, para optimizar el proceso, se utilizó la función `gradient` la cual asegura que las velocidades de referencia sean exactas con respecto al tiempo de muestro que se definió en todas las trayectorias de 0.01.
- Para realizar el hexágono el cual a diferencia de las demás trayectorias es un poligono, se usa la función `interp1`. Esto genera un camino continuo de puntos entre los vértices, permitiendo que el controlador siempre tenga un objetivo intermedio y no salte a otro vértice.
- Se utilizó la pseudoinversa de Moore-Penrose para resolver la cinemática inversa con la función `pinv`.
- Para trayectorias con curvas cerradas, se ajustaron los valores de la matriz de ganancias K, la cual se encontraron los valores optimos de 25 para la velocidad lineal y 5 para la velocidad angular. Estos valores funcionaron para la mayoría de las trayectorias. 

Trayectoria 1

```
tf=31.5
ts=0.01

hxd=2*cos(0.2*t);
hyd=2*sin(0.4*t);

hxdp=-2*0.2*sin(0.2*t);
hydp=2*0.4*cos(0.4*t);
```

<img width="805" height="804" alt="Screenshot from 2026-05-12 16-17-23" src="https://github.com/user-attachments/assets/76f610c9-b851-4f35-a0af-571986b22318" />

Trayectoria 2

```
tf=31.5
ts=0.01

hxd=t-3*sin(t);
hyd=4-3*cos(t);

hxdp=1-3*cos(t);
hydp=3*sin(t);
```

<img width="1550" height="484" alt="imagen" src="https://github.com/user-attachments/assets/4e60578f-5755-4ce0-b0c6-0c74120a18e8" />

Trayectoria 3

```
tf=31.5
ts=0.01

hxd=3-cos(t)-cos(3*t);
hyd=4*sin(3*t);

hxdp=sin(t)+3*sin(3*t);
hydp=12*cos(3*t);
```


<img width="223" height="267" alt="imagen" src="https://github.com/user-attachments/assets/b02b2d07-33a6-453d-8abe-46320a6581e2" />

Trayectoria 4

```
tf=31.5
ts=0.01

hxd=cos(t) + 1/2*cos(7*t) + 1/3*sin(17*t);
hyd=sin(t) + 1/2*sin(7*t) + 1/3*cos(17*t);

hxdp = gradient(hxd, ts); 
hydp = gradient(hyd, ts);
```

<img width="223" height="267" alt="imagen" src="https://github.com/user-attachments/assets/04c9d4be-085b-4706-b701-61deed4b3d30" />

Trayectoria 5

```
tf=31.5
ts=0.01

hxd=17*cos(t)+7*cos(17+7*t);
hyd=17*sin(t)-7*sin(17+7*t);

hxdp = gradient(hxd, ts); 
hydp = gradient(hyd, ts);

```

<img width="876" height="861" alt="imagen" src="https://github.com/user-attachments/assets/48cd0089-d7ad-4346-8eb4-8b25d877f273" />

Trayectoria 6

```
tf=31.5
ts=0.01

hxd=2*cos(t);
hyd=2*sin(t);

hxdp = gradient(hxd, ts); 
hydp = gradient(hyd, ts);

```

<img width="876" height="861" alt="imagen" src="https://github.com/user-attachments/assets/d1e41364-0842-41ee-9aac-fc969b94b4b0" />

Trayectoria 7

```
tf=31.5
ts=0.01

hxd=5*t-4*sin(t);
hyd=5*t-4*cos(t);

hxdp = gradient(hxd, ts); 
hydp = gradient(hyd, ts);

```

<img width="876" height="861" alt="imagen" src="https://github.com/user-attachments/assets/de7c048a-5bff-4b56-ab4f-c93c70dece40" />


Trayectoria 8

```
tf=31.5
ts=0.01

hxd=4*cos(t)+cos(4*t);
hyd=4*sin(t)-sin(4*t) ;

hxdp = gradient(hxd, ts); 
hydp = gradient(hyd, ts);

```
<img width="876" height="861" alt="imagen" src="https://github.com/user-attachments/assets/6597d0e9-7d42-4db1-8752-b5850a6f0613" />

Trayectoria 9

```
tf=31.5
ts=0.01

L = 8; % Radio o distancia del centro al vértice
puntos = 6; % Número de lados

% Creamos los vértices 
theta_v = linspace(0, 2*pi, puntos + 1);
vertices_x = L * cos(theta_v);
vertices_y = L * sin(theta_v);

hxd = interp1(linspace(0, tf, length(vertices_x)), vertices_x, t, 'linear');
hyd = interp1(linspace(0, tf, length(vertices_y)), vertices_y, t, 'linear');

hxdp = gradient(hxd, ts); 
hydp = gradient(hyd, ts);

```

<img width="851" height="839" alt="imagen" src="https://github.com/user-attachments/assets/66856f5a-43ad-4ea1-bafb-befd914ae9b0" />


Trayectoria 10


```
tf=31.5
ts=0.01

hxd=5*cos(9*t).*cos(t);
hyd=5*cos(9*t).*sin(t);

hxdp = gradient(hxd, ts); 
hydp = gradient(hyd, ts);

```


<img width="876" height="861" alt="imagen" src="https://github.com/user-attachments/assets/f0213c3c-0e8c-4b00-bc52-c29f58b7bc66" />

Trayectoria 11

```
tf=31.5
ts=0.01

a=0.5;

hxd = a * (16 * sin(t).^3);
hyd = a * (13 * cos(t) - 5 * cos(2*t) - 2 * cos(3*t) - cos(4*t));

hxdp = gradient(hxd, ts); 
hydp = gradient(hyd, ts);

```

<img width="864" height="877" alt="imagen" src="https://github.com/user-attachments/assets/eb6a4ded-bd16-4290-b37a-cb8bff5aca13" />














