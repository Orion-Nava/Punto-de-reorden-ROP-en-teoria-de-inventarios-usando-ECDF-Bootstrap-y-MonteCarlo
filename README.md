# Punto-de-reorden-ROP-en-teoria-de-inventarios-usando-simulacion-Monte-Carlo

Los modelos clásicos del punto de reorden (ROP) en teoría de inventarios asumen distribuciones normales para la demanda y tiempos de entrega. En este proyecto se usa simulación Monte Carlo para establecer puntos de reorden en escenarios donde no se cumplen tales supuestos.


El **punto de reorden (ROP)** es el nivel de inventario en el que debe emitirse un nuevo pedido para reabastecer antes de que el stock se agote, considerando el tiempo que tarda en llegar el pedido.

**Modelo determinístico**
Si no consideramos incertidumbre en el modelo:

$$ROP = L \times d$$

donde:
ROP = Punto de reorden
L = Tiempo de entrega de pedidos (*lead time*)
D = Demanda por unidad de tiempo

**Modelo probabilístico**
Si consideramos incertidumbre en el modelo:

$$ROP = \hat{D}_L + SS$$

$$ROP = \hat{L} \times \hat{D} + z\sqrt{\hat{L} \sigma_{D}^2 + \hat{D}^2 \sigma_{L}^2}$$







