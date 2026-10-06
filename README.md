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
