# Actividad-6.1-Seguimiento-de-Trayectorias-

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












