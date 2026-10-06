# Séptimo Cielo — V7

Carta unificada: categoría → producto → ficha → 3D/AR cuando el activo está disponible. Los modelos se cargan bajo demanda.

Los cuatro activos actuales son demostrativos. El resto de fichas queda preparado para incorporar digitalizaciones futuras sin rediseñar la interfaz.


## V8
Se incorpora Ceviche Peruano como quinta experiencia 3D/AR demostrativa. Modelo referencial a escala métrica para pruebas web y AR.


## V8.1
Ceviche Peruano corregido con materiales PBR visibles: pescado, aguacate, leche de tigre, chips, cebolla, cilantro y cerámica. Visor calibrado con entorno neutral, sombras y exposición.

## V8.2 — Estándar de orientación AR
- Todos los platos deben modelarse sobre el plano XY, con Z como altura.
- La base inferior del plato se normaliza a Z=0 para apoyar sobre la superficie.
- AR usa colocación horizontal (`ar-placement="floor"`) y escala fija.
- El Ceviche Peruano fue normalizado con este estándar.

## V8.3 — Corrección de orientación nativa
La rotación del Ceviche se hornea dentro del GLB para corregir la diferencia de ejes entre el visor web y los visores AR nativos. Se mantiene colocación sobre superficie horizontal y escala fija.

## V8.4 — Corrección definitiva de cara superior
V8.3 dejó el plato en el plano horizontal correcto XZ, pero con la normal hacia -Y, por eso se veía de cabeza.
V8.4 gira el modelo 180° sobre X para que la comida mire hacia +Y, que es el eje vertical de glTF/model-viewer.
La base física queda anclada en Y=0 para colocación sobre mesa.

## V8.5 — Cache bust del modelo 3D
La geometría corregida de V8.4 se publica con un nombre de archivo nuevo
(`ceviche-peruano-v85.glb`) y el HTML añade `?v=85`.
Esto evita que Chrome/model-viewer/AR reutilicen el GLB invertido guardado en caché.

## V8.6 — Tomahawk horizontal
Tomahawk normalizado al mismo estándar que validó el Ceviche:
- glTF/model-viewer Y-up
- mesa = plano XZ
- base física = Y=0
- escala fija en AR
- archivo versionado `tomahawk-v86.glb?v=86` para evitar caché del modelo anterior.

## V9.0 — Estándar universal para todos los platos 3D/AR
Se aplica a todos los productos 3D actuales y a los futuros:
- glTF/model-viewer Y-up.
- Mesa = plano XZ.
- Base física = Y=0.
- AR horizontal y escala física fija.
- Archivo GLB versionado para evitar caché.
- Todos los visores usan el mismo encuadre/cámara.
- En móvil el visor queda limitado al ancho de pantalla y a una altura responsive máxima.
- El tamaño visual del visor se estandariza sin falsear el tamaño físico real de cada plato en AR.


## V9.2
Layout V9 restaurado. Solo Tomahawk usa cámara 155% para quedar dentro de la cuadrícula como el Ceviche. Sin cambios de tamaño o fondo del modal.

## V9.3 — corrección móvil definitiva
- La ficha de producto queda en una sola columna y exactamente dentro del viewport.
- Se elimina el desplazamiento horizontal de toda la página/ficha.
- Se conservan el ancho, fondo y estructura visual del Ceviche usado como referencia.
- Tomahawk usa un encuadre propio más alejado (175%) para entrar completo dentro de la misma cuadrícula.
- No se modifica la orientación ni el funcionamiento AR.


## V10 — Chicharrones 3D Gen 2
Añade Chicharrones a 3D/AR con panceta por capas, papa criolla, guacamole, pico de gallo y ají. Mantiene el estándar móvil V9.3 sin scroll horizontal y AR Y-up/floor/fixed. Modelo referencial de demostración; sustituible por digitalización del plato real.

## V11.1 — Spring Roll corregido
La V11 anterior insertó por error un objeto JavaScript antes del DOCTYPE, por eso el navegador mostraba código como texto.
Esta versión parte nuevamente de la V10 aprobada e integra Spring Roll correctamente dentro de `arAssets`.
La estructura, responsive móvil, Chicharrones y demás platos permanecen sin cambios.

## V12 — Focaccia Capresse Gen 2
Se incorpora Focaccia Capresse ($19.000) al sistema 3D + AR.
Visualización referencial basada en la carta: focaccia crocante, mozzarella, tomates frescos, pesto, espejo de napolitana y reducción de balsámico.
Se mantiene intacta la arquitectura móvil aprobada: una sola columna, sin desplazamiento horizontal, AR horizontal y cámara individual.

## V13 — Ensalada Séptimo Cielo Gen 2
Se incorpora Ensalada Séptimo Cielo ($19.000) al sistema 3D + AR: mix de lechugas asiáticas, tomates cherry, bocconcini, pesto y reducción de balsámico. Visualización referencial.
La arquitectura móvil aprobada permanece intacta.

## V14 — Nachos de la Casa
Décimo plato 3D + AR. Visualización referencial basada en la carta oficial. Se conserva íntegra la arquitectura móvil aprobada.

## V15 — Experiencia Comercial
Se conserva el catálogo aprobado de 10 modelos 3D/AR y se añade una capa de experiencia comercial:
- explicación inmediata del flujo Elige → 3D → AR;
- señalización “3D + AR disponible”;
- instrucción contextual dentro del detalle del plato;
- arquitectura, cámaras, orientación, escala AR y responsive previamente aprobados sin cambios.
