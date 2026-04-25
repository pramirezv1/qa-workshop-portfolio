# Sesión 1
## Charter
Explorar las funcionalidades de compra y carrito de productos, con el objetivo de identificar fallos en la adición, modificación y eliminación de productos, así como validar el cálculo correcto de precios en el flujo de checkout.

## ÁREAS
- Módulo de catálogo de productos
- Carrito de compras
- Checkout / proceso de pago
- Control de stock de productos

## INICIO
16/04/2026 – 19:00

## TESTER
Pablo Ramirez

## DESGLOSE DE TAREAS
- 15 min → Exploración del catálogo y selección de productos
- 20 min → Agregar productos al carrito en diferentes cantidades
- 15 min → Modificación/eliminación de productos del carrito
- 20 min → Validación de stocks de productos
- 10 min → Revisión del flujo de compra completo
- 10 min → Documentación de hallazgos

## ARCHIVOS DE DATOS
- Usuarios de prueba (usuario logueado estándar)
- Productos de todas las categorías 
- Productos con stock disponible y sin stock (estado False)
- Imágenes asociadas a productos (catálogo mixto)

## NOTAS DE PRUEBA
- En el catologo de pajaros al seleccionar un producto no muestra si hay stock del producto, a diferencia del catalogo de perros
- Permite ingresar una cantidad exagerada de productos (no se deberia de permitir, ya que antes, deberia haber una validacion previa entre la cantidad de stock con la cantidad solicitada por el usuario )
- Al querer visualizar la imagen de un producto muestra la imagen de un producto distinto
- Permite realizar la compra completa de un producto que el estado de su stock esta en "False"

## LISTA DE RIESGOS 
- Venta de productos sin stock disponible (riesgo crítico de negocio)
- Inconsistencia entre stock real y stock mostrado al usuario
- Posibles errores en asignación de imágenes de productos (impacto en UX y confianza del usuario)
- Falta de validación en frontend y/o backend sobre cantidades máximas permitidas
- Riesgo de sobreventa y errores en inventario

## DEFECTOS (BUGS) 
- BUG-01: No se muestra el stock disponible en el catálogo de pájaros (inconsistencia con catálogo de perros)
- BUG-02: Permite agregar al carrito cantidades mayores al stock disponible
- BUG-03: Imagen de producto incorrecta al visualizar detalles de algunos productos
- BUG-04: Permite finalizar compra de productos con stock en estado “False”

## INCIDENTES (ISSUES) 
- ¿Por qué el catálogo de pájaros no muestra stock mientras el de perros sí?
- No está claro si la validación de stock se realiza en frontend, backend o ambos
- ¿El estado “False” del stock significa sin stock absoluto o solo no disponible temporalmente?
- Posible falta de definición de reglas de negocio para control de inventario