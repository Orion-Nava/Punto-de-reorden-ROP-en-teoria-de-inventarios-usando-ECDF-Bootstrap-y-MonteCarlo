# Punto-de-reorden-ROP-en-teoria-de-inventarios-usando-simulacion-Monte-Carlo

____________________________________

Los modelos clásicos del punto de reorden (ROP) en teoría de inventarios asumen distribuciones normales para la demanda y tiempos de entrega. En este proyecto se usa simulación Monte Carlo para establecer puntos de reorden en escenarios donde no se cumplen tales supuestos.

__________________________________

El **punto de reorden (ROP)** es el nivel de inventario en el que debe emitirse un nuevo pedido para reabastecer antes de que el stock se agote, considerando el tiempo que tarda en llegar el pedido.

___________________________________


**Modelo determinístico**

Si no consideramos incertidumbre en el modelo:

$$ROP = \bar{L} \times \bar{D}$$

donde:

ROP = Punto de reorden

- $\bar{L}$ = Tiempo de entrega promedio de pedidos (*lead time*)

- $\bar{D}$ = Demanda promedio por unidad de tiempo

_________________________________________________


**Modelo probabilístico**

Si consideramos incertidumbre en el modelo:

$$ROP = \hat{D}_L + SS$$

$$ROP = \bar{L} \times \bar{D} + z\sqrt{\bar{L} \sigma_{D}^2 + \bar{D}^2 \sigma_{L}^2}$$

- SS = Inventario de seguridad (*stock security*)

- $\bar{L}$ = Tiempo de entrega promedio de pedidos (*lead time*)

- $\bar{D}$ = Demanda promedio por unidad de tiempo

- $\sigma_{D}^{2}$ = Varianza de la demanda

- $\sigma_{L}^2$ = Varianza de los tiempos de entrega

- $z$ = Cuantil normal estándar del nivel del servicio deseado

Los supuestos son que la demanda y el tiempo de entrega son idependientes y que tienen distribución aproximadamente normal

_____________________________________________________


El uso del modelo determinístico es más con fines pedagógicos; el nivel de servicio (*SL: Service Level*) que proporciona es de 50 %, ya que se basa en promedios como tal.






