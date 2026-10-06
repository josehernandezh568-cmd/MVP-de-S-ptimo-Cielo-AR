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
