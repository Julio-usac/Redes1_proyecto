# Manual de construccion y configuracion
## Topología 2
La topología 2 es la encargada de distribuir y repartir las VLANS hacia las demás topologías, es el Cuarto de telecomunciaciones
### Configuración de la topología de red:
Componentes a utilizar:
- 4 Etherswitch Router
- 1 Cloud
- 4 switch
- 1 router
- 3 maquinas virtuales
- 3 vpc

Conexiones de la topologia:

<p align="center">
  <img src="img/topo2.png" width="600">
</p>

### Configuración del ESW1:

Podemos ver que los portchannels están configurados y la interface que se conecta a la nube en el ESW1 con el comando sh int trunk.

<p align="center">
  <img src="img/trunkesw1.png" width="600">
</p>

Además el ESW1 es el que se configura en modo servidor y por lo tanto el encargado de suministrarle las VLANS creadas en este hacia los demas switchs, miramos esto con el comando sh vtp status

<p align="center">
  <img src="img/vtpesw1.png" width="600">
</p>

Se configuraron las siguientes vlan en el ESW1:

<p align="center">
  <img src="img/vlanesw1.png" width="600">
</p>

### Configuracion otros ESW:

Podemos ver que los portchannels están configurados y las conexiones a los oros ESW con el comando sh int trunk.

<p align="center">
  <img src="img/trunkotro.png" width="600">
</p>


<p align="center">
  <img src="img/trunkotro2.png" width="600">
</p>

Todos los ESW fueron configurados en modo cliente a excepcion del ESW1 que es modo servidor, podemos ver esto con el sh vtp status:

<p align="center">
  <img src="img/vtpotro.png" width="600">
</p>

Al ser clientes, los ESW obtienen las vlan del ESW1 que es modo servidor, podemos ver esto con sh vlan-sw:

<p align="center">
  <img src="img/vlanotro.png" width="600">
</p>


