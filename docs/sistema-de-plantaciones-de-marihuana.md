# Sistema de plantaciones de marihuana

## Introducción

El cultivo de marihuana es la forma más accesible de producir droga en San Andreas Roleplay: no exige facción, ni licencia, ni habilidad mínima. Cualquier personaje que consiga semillas, abono, fertilizante y agua puede montar su propio cultivo y, con paciencia, cosechar cogollos listos para consumir o vender.

Puedes plantar prácticamente en cualquier sitio: dentro de una casa, en un negocio, en un almacén, en un bosque o al aire libre. La maceta queda fija en el lugar y la orientación donde la colocaste, y permanece ahí aunque cierres sesión o el servidor se reinicie.

Ten cuidado con dónde plantas: **la planta no tiene dueño protegido**. Cualquier personaje que pueda llegar hasta ella podrá robarte los cogollos o destruirla. Un interior cerrado con llave es mucho más seguro que un descampado.

El servidor permite un máximo de **512 plantas activas** en todo el mapa al mismo tiempo. Si el cupo está lleno, no podrás crear nuevas hasta que se liberen espacios.

### Comandos

- /plantacion crear — coloca una maceta nueva con semillas. Alias: `/plantación`.
- /plantacion cuidar — riega la planta más cercana.
- /plantacion mejorar — aplica fertilizante a la planta más cercana.
- /plantacion examinar — muestra el estado de la planta más cercana.
- /plantacion cosechar — recoge los cogollos cuando la planta está madura.
- /plantacion eliminar — destruye la planta más cercana.

Todos los comandos, salvo `crear`, actúan sobre la planta más cercana dentro de **2 metros** y en el mismo interior donde estás.

## Qué necesitas y cuánto cuesta

El cultivo se apoya en cuatro consumibles. Los tres primeros se venden en los negocios de tipo **growshop**; el agua se consigue en cualquier tienda 24/7, máquina expendedora o negocio que la tenga en catálogo.

| Objeto | Dónde se consigue | Unidades por envase | Costo base |
|--------|-------------------|---------------------|------------|
| Semillas de Marihuana | Growshop | hasta 1000 | **$51** |
| Saco de Abono | Growshop | hasta 20 | **$144** |
| Fertilizante para Cannabis | Growshop | hasta 5 | **$216** |
| Botella de Agua | Tiendas, expendedoras, bares | hasta 10 | **$6** |

El costo base es lo que el negocio paga por reponer stock. Cada growshop fija su propio precio de venta al público, que nunca puede ser **inferior al costo base** ni superior a **10 veces** ese costo. Si compras en un puesto con atención en ventanilla (drive-thru), el precio sube un **20%** adicional.

El saco de abono es pesado (**20 kg**) y ocupa **2 ranuras** del inventario: hay que cargarlo con las dos manos, así que planifica el traslado hasta el lugar donde vayas a cultivar.

## Plantar

Para crear una planta debes cumplir **tres condiciones a la vez**:

- Llevar un paquete de **Semillas de Marihuana** en la mano derecha, con al menos 1 unidad.
- Tener un **Saco de Abono** apoyado en el piso, a **5 metros o menos** de ti.
- No haber otra planta a menos de **1,5 metros**.

Al ejecutar `/plantacion crear` colocas la maceta en tu posición y mirando hacia donde estás orientado. La planta nace con **5/10 de salud**, **0/5 de agua**, **0/5 de fertilizante** y madurez **Semilla**.

Cada plantación consume una cantidad aleatoria de insumos:

- **1 a 5 semillas** del paquete.
- **1 a 5 unidades** del saco de abono.

Si a cualquiera de los dos se le acaban las unidades, el envase desaparece de tu inventario.

## Regar y fertilizar

Una planta solo crece si está bien cuidada. Hay dos acciones de mantenimiento y ambas se aplican a la planta más cercana.

| Acción | Comando | Qué necesitas en la mano derecha | Tope | Efecto |
|--------|---------|----------------------------------|------|--------|
| Riego | `/plantacion cuidar` | Botella de Agua | 5/5 de agua | **+1 salud** y **+1 agua** |
| Fertilización | `/plantacion mejorar` | Fertilizante para Cannabis | 5/5 de fertilizante | **+1 salud** y **+1 fertilizante** |

Cada aplicación gasta entre **1 y 3 unidades** del envase, aunque solo sume +1 al medidor de la planta: conviene llevar repuestos. La salud nunca pasa de **10/10** y el agua y el fertilizante nunca pasan de **5/5**; si el medidor ya está al máximo, el comando te avisa y no gasta nada.

**Tip para ahorrar fertilizante:** cuando tengas un fertilizante en la mano, usa `/extraerunidad 1`. Normalmente el fertilizante viene en dos unidades, y al extraer una tendrás dos fertilizantes separados de una unidad cada uno. Así puedes fertilizar dos veces una planta usando un solo fertilizante comprado, lo que resulta más económico y práctico.

Estas tareas también entrenan tu **habilidad de drogas**:

- Fertilizar: **50% de probabilidad** de sumar +1 punto.
- Regar: **25% de probabilidad** de sumar +1 punto.

## Crecimiento

Cada planta atraviesa **seis etapas de madurez**. El aspecto de la maceta cambia visiblemente en cada una:

| Etapa | Nombre | ¿Se puede cosechar? |
|-------|--------|---------------------|
| 0 | Semilla | No |
| 1 | Brote | No |
| 2 | Plántula | No |
| 3 | Crecida | No |
| 4 | Floración | Sí |
| 5 | Cosecha | Sí (rendimiento máximo) |

El ciclo de crecimiento se evalúa **una vez por cada reinicio del servidor**, cuando las plantas vuelven a cargarse. En ese momento, cada planta sube una etapa **solo si cumple los tres umbrales**:

- Salud de **5/10** o más.
- Agua de **3/5** o más.
- Fertilizante de **1/5** o más.

Cumpla o no los requisitos, **siempre se descuentan recursos** en cada ciclo:

| Medidor | Consumo por ciclo |
|---------|-------------------|
| Salud | **1 a 2 puntos** |
| Agua | **1 a 3 puntos** |
| Fertilizante | **1 a 3 puntos** |

Como el consumo es constante, una planta abandonada pierde salud hasta llegar a cero y **se elimina automáticamente** en el siguiente arranque del servidor. En el peor de los casos una planta puede vaciar el agua y el fertilizante en solo dos ciclos, así que lo razonable es pasar a revisarla y recargarla todos los días.

En la práctica, llevar una planta desde semilla hasta la etapa Cosecha requiere **cinco ciclos exitosos** consecutivos, lo que equivale a varios días de cuidado sostenido.

## Examinar

`/plantacion examinar` te muestra el estado de la planta más cercana, pero **cuánto ves depende de tu habilidad de drogas**:

| Habilidad de drogas | Información visible |
|---------------------|---------------------|
| Cualquiera | Identificador de la planta y etapa de madurez |
| **5 o más** | Nivel de agua y de fertilizante |
| **10 o más** | Nivel de salud |

Un cultivador novato ve poco más que el aspecto de la planta: subir habilidad es lo que te permite afinar el riego y la fertilización antes de cosechar.

## Cosechar

Cuando la planta llega a **Floración** o **Cosecha**, ya puedes recogerla con `/plantacion cosechar`. Necesitas tener la **mano derecha vacía**, porque los cogollos aparecen directamente ahí.

| Etapa al cosechar | Gramos obtenidos |
|-------------------|------------------|
| Floración | **20 a 49 gramos** |
| Cosecha | **30 a 49 gramos** |

La **fuerza** (pureza) de la marihuana obtenida, de 0 a 100, depende del estado en que quedó la planta al momento de cortarla:

| Condición al cosechar | Aporte a la fuerza |
|-----------------------|--------------------|
| Agua en **3/5** o más | **+20** |
| Fertilizante en **3/5** o más | **+50** |
| Salud en **5/10** o más | **+30** |

Es decir: una planta que llegue a la cosecha bien regada, bien fertilizada y sana entrega los **100 puntos de fuerza**, mientras que una descuidada puede dar gramos prácticamente inservibles. El fertilizante es, con diferencia, el factor que más pesa en la calidad final. Conviene regar y fertilizar **justo antes** de cortar, porque el ciclo de crecimiento previo ya habrá restado puntos a los medidores.

Cada cosecha tiene un **50% de probabilidad** de sumar +1 a tu habilidad de drogas.

Tras cortarla, la planta **no desaparece**: vuelve a la etapa **Semilla** conservando el agua, el fertilizante y la salud que le quedaban, y empieza de nuevo el ciclo. Una maceta bien mantenida produce indefinidamente.

## Eliminar

`/plantacion eliminar` destruye la planta más cercana y deja una **bolsa de basura** en su lugar. No requiere ningún objeto, cualquiera que llegue hasta la planta puede hacerlo y **la acción es irreversible**: pierdes la planta y todo lo invertido en ella.

## Qué hacer con la cosecha

Los cogollos que obtienes son marihuana normal del gamemode: puedes fumarla, venderla a otros personajes, distribuirla en las zonas de venta callejera o guardarla. Todo eso se explica en el [sistema de drogas](sistema-de-drogas.md).

Un detalle importante para el cultivador: la marihuana **pierde fuerza con el paso de los días** esté donde esté, salvo que la guardes en el **refrigerador de una propiedad** (o dentro de un paquete que esté en ese refrigerador), donde tiene un **70% de probabilidad diaria** de conservar la pureza intacta. Si cosechas grandes cantidades para vender de a poco, el refrigerador es la diferencia entre vender producto premium y vender restos.

## Consejos

- **Planta en interiores con llave.** Es la única protección real contra robos y destrucciones.
- **Separa las macetas.** El mínimo es 1,5 metros entre plantas; dejar algo más de espacio facilita apuntar al comando correcto cuando riegas varias seguidas.
- **Lleva envases de sobra.** Cada riego o fertilización puede gastar hasta 3 unidades, y el bote de fertilizante trae solo 5.
- **Espera a la etapa Cosecha.** Cortar en Floración te da menos gramos en promedio; la diferencia se nota al vender lotes grandes.
- **Riega y fertiliza antes de cortar.** La fuerza se calcula con los valores del momento exacto de la cosecha.
- **Sube tu habilidad de drogas cuidando plantas.** Con 5 puntos ya ves el agua y el fertilizante, y con 10 ves también la salud, lo que te permite dejar de adivinar.
