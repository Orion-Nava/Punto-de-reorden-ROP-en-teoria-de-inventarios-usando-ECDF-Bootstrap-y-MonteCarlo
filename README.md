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

Los supuestos son que la demanda y el tiempo de entrega son independientes y que tienen distribución aproximadamente normal

_____________________________________________________


El modelo determinístico se usa más con fines pedagógicos; el nivel de servicio (*SL: Service Level*) que proporciona es de 50 %, ya que se basa en promedios como tal. Por otro lado, en la práctica la demanda y los tiempos no siempre tienen distribución normal. En cadenas de suministro, por ejemplo, lo usual es que la demanda tenga distribución normal o Poisson, mientras que el tiempo de entrega suele tener distribución log normal, gamma o Weibull. En tales casos, no es conveniente aplicar la fórmula probabilística clásica para el cálculo del ROP; en su lugar, conviene implementar métodos no paramétricos:


- Usar la función de distribución empírica (cuando hay suficientes datos).

- Usar Bootstrap y simulación Monte Carlo (cuando los datos son pocos).

__________________________________________________________

**Usando la función de distribución empírica de la demanda durante el tiempo de entrega**

1. Multiplicar tiempos de entrega por datos de demanda y obtener vector de demanda durante los tiempos de entrega.

$$D_{L, i} = L_{i} \times D_{i}, \qquad i = 1, 2, n$$

2. Construir la *función de distribución empírica*, que se define como:

$$\hat{F}_{n}(x) = \frac{1}{n} \sum_{i=1}^{n}1\{D_{L, i}\geq x\}$$

3. Tomar como ROP el cuantil empírico correspondiente al nivel de servicio deseado.


____________________________________________________________

**Usando Bootstrap y Simulación Monte Carlo**

1. 




