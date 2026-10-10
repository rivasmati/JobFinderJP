# Wireframes: resumen en texto

Resume `Mapa de trabajos en Japón · Wireframes.html` (versión 2, 31 tableros) para que cualquier sesión pueda leer la estructura sin abrir el HTML. El contenido y las reglas del producto están en [PRODUCT.md](PRODUCT.md) y en [Mapa de trabajos en Japón definición del producto.md](Mapa%20de%20trabajos%20en%20Japón%20definición%20del%20producto.md); si hay diferencias, mandan esos.

## Cómo es el archivo

- Un HTML empaquetado (3,2 MB): cada tablero es un `iframe` con su propio paquete comprimido. No se puede leer con un editor de texto. Para verlo hay que abrirlo en un navegador, por ejemplo con `python3 -m http.server`.
- **Son wireframes, no diseño visual:** escala de grises, tipografía del sistema, íconos de relleno, mapa "esquemático". No definen color, tipografía final ni estilo.
- Tamaños: móvil 390 px de ancho (con una marca de "pliegue móvil" a 844 px) y escritorio 1280 px.
- Las etiquetas "Condicional" que se ven junto a algunos campos son anotaciones del wireframe, no texto de interfaz.
- Una versión anterior (22 tableros) quedó guardada en git en el commit `12249e7`.

## Estructura común

- **Encabezado:** nombre del sitio ("Mapa de trabajos en Japón") y botón "Proponer lugar" siempre visible. En escritorio se suma el buscador por nombre o ciudad.
- **Pie:** nombre del sitio, "Directorio en español" y enlaces: Cómo funciona, Reglas de la comunidad, Términos de uso, Privacidad, Guía de visa (YoMeAnimo).
- **Tarjeta de lugar:** nombre, rubro y ciudad; salario por hora (un valor si hay una sola reseña, rango si hay varias) con "basado en N reseñas"; etiquetas de alojamiento, temporada e idioma; estado de vigencia con ícono y texto.
- **Vigencia:** "✓ Activo · última reseña hace X" o "! Se desconoce si sigue activo · última reseña hace 19 meses".
- **Avisos:** un solo bloque por pantalla ("Un lugar no es una vacante: consultá siempre al empleador"); el aviso del salario va aparte, junto al dato.
- **Datos que faltan:** "Sin datos aún" más "Completalo con una reseña".

## Tableros

### Público, móvil

| Tablero | Contenido y estructura |
|---|---|
| P0 · Inicio: buscador | Título "¿Dónde querés trabajar?", campo de ciudad o prefectura (acepta latino y japonés), cinco zonas con cantidad de lugares (Ski Hokkaido 22, Ski Nagano 17, Playa Okinawa 12, Tokio 31, Kioto 14), "Retomar tu última búsqueda", accesos por condición (con alojamiento, invierno, verano), "Ver todos los lugares", invitación a proponer un lugar. |
| P0 · Aviso de cookies | El inicio con una barra fija inferior: "Usamos cookies solo para publicidad no personalizada", enlace a Privacidad y botones "Rechazar" y "Aceptar" del mismo peso. |
| P1 · Resultados: lista | Buscador por nombre o ciudad, filtros en una fila que se desplaza (alojamiento activo, rubro, ¥ por hora, temporada, idioma y nivel), alternancia Lista/Mapa, "38 lugares", orden por reseña más reciente, tarjetas, "Cargar más lugares" y el aviso de postulación. |
| P1 · Mapa: panel mínimo | Mapa con pines agrupados por zona y un pin seleccionado; panel inferior de dos líneas (nombre, rubro, vigencia, salario por hora). El mapa ocupa cerca del 70% de la pantalla. |
| P1 · Mapa: panel medio | El mismo panel más alojamiento, temporada e idioma, con asa y la ayuda "Deslizá hacia arriba para ver más". |
| P1 · Mapa: panel completo | El panel con nombre en latino y japonés, salario con su aviso de referencia, alojamiento, idioma, el aviso "Un lugar no es una vacante" y el botón "Ver ficha completa". |
| P1 · Sin resultados | Filtros activos, "0 lugares", estado vacío con "Quitar filtros" y "¿Conocés un lugar? Proponelo". |
| P2 · Ficha completa | Nombre (latino y japonés), rubro, temporada, ciudad, vigencia, salario por hora con "basado en 6 reseñas", alojamiento (tipo, costo mensual, si se descuenta), condiciones (idiomas, horas por tipo de visa, horas mínimas, horas extra, puestos, requisitos), reseñas (temporada, visa, fecha, puntuaciones, recomendación, comentario, etiqueta "Editada por moderación"), "Ver N reseñas más", ubicación y contacto, fechas, acciones (agregar reseña, denunciar, pedir baja) y bloque de avisos. |
| P2 · Datos incompletos | La ficha de un lugar con una sola reseña: salario de un solo valor y "Sin datos aún" con invitación a completar. |
| P2 · Vigencia vencida | La ficha con el aviso de vigencia arriba del salario y un botón "Agregar reseña" para confirmarla. |
| P3 · Proponer lugar | Formulario único de cinco secciones (1. El lugar, 2. Condiciones, 3. Tu experiencia, 4. Contacto, 5. Confirmación). Obligatorios con asterisco. Comentario de hasta 300 caracteres con contador. |
| P3 · Posible duplicado | Dentro de la sección 1, una tarjeta en línea: "¿Es este lugar?" con el lugar existente y los botones "Sí, reseñar este lugar" y "No, es otro". |
| P3 · Sin coincidencia | La sección 1 con una confirmación: "No encontramos lugares parecidos". |
| P3 · Alojamiento: Sí | El formulario con los campos condicionales de alojamiento (tipo, costo mensual, si se descuenta) y la puntuación de alojamiento. |
| P3 · Rechazo por riesgo alto | Aviso de rechazo en el momento, con el motivo (nombre propio en el comentario), el campo marcado y las demás respuestas conservadas. |
| P3 · Errores de validación | Resumen arriba ("Faltan 2 campos: Nombre · Ambiente general. Y revisá: Salario · Comentario"), "Campo obligatorio" junto a cada campo vacío, "Revisá el valor: parece muy alto o muy bajo" en el salario y "312 / 300 · Máximo 300 caracteres" en el comentario. |
| P4 · Agregar reseña | Formulario corto sobre un lugar existente: visa, temporada, forma de pago, salario, horas semanales (condicional), puntuaciones, comentario, confirmación. Muestra el valor por hora calculado. |
| P4 · Estudiante: límite de 28 horas | El campo de horas semanales con botones − y +, tope de 28 y la ayuda "Máximo 28 h con visa de estudiante". |
| P5 · Envío recibido | "Recibido. Lo revisamos y se aprueba o rechaza en un plazo de hasta 48 horas", sin aviso del resultado. |
| P6 · Denunciar contenido | Pestañas "Denunciar contenido" y "Soy el negocio". Qué denunciar (ficha o reseña), motivo (posible trabajo ilegal, datos personales, insultos, acusación de delito, información falsa, otro) y detalle. |
| P6 · Pedir baja (negocio) | Motivo y contacto del negocio (no se publica). |
| P6 · Confirmación | "Recibimos tu denuncia", revisión manual. |
| P7 · Cómo funciona | Cómo se publica un lugar en cuatro pasos, qué muestra cada ficha, reseñas anónimas, visas y horas, enlaces legales y el aviso de que no se intermedia. |

### Público, escritorio (1280 px)

| Tablero | Estructura |
|---|---|
| P1 · Resultados (escritorio) | Encabezado con buscador. Barra lateral izquierda de filtros (ciudad, rubro con casillas, salario mín/máx, alojamiento Todos/Sí/No, temporada, idioma). A la derecha, alternancia Lista/Mapa y tarjetas en dos columnas. |
| P2 · Ficha (escritorio) | Columna principal con título, recuadros de salario y alojamiento, condiciones en dos columnas y reseñas. Columna derecha fija con ubicación, contacto, fechas y acciones. |

### Administración (solo vos)

| Tablero | Estructura |
|---|---|
| A1 · Cola de moderación | Pestañas Cola (7), Contactos (2), Denuncias (3). Filtros Todos/Lugares nuevos/Reseñas. Lista ordenada por riesgo y antigüedad: nivel de riesgo, tipo, lugar, motivo de la IA, marca de posible duplicado. |
| A2 · Detalle de envío | Riesgo y motivo de la IA, posible duplicado con "Comparar" y "Es el mismo: unir como reseña", verificación en Google Maps, contenido editable, decisión (aprobar, corregir y aprobar, rechazar con motivo). |
| A1 + A2 · Moderación (escritorio) | Dos paneles: cola a la izquierda (el envío abierto resaltado) y detalle a la derecha. |
| A1 + A2 · Posible duplicado: comparar (escritorio) | El mismo diseño con una tabla campo por campo entre el envío nuevo y el lugar publicado (3 de 6 coinciden), con "Es el mismo: unir como reseña" y "Son distintos: seguir revisando". |
| A3 · Contactos pendientes | Contactos personales pendientes de confirmación; acciones "Confirmó: publicar" y "Descartar". Datos parcialmente ocultos. |
| A4 · Denuncias, bajas y ocultos | Tres bloques: denuncias (con prioridad alta para posible trabajo ilegal), pedidos de baja y ocultos con "Restaurar". |

## Decisiones tomadas sobre los problemas de la versión 1

| # | Problema | Decisión |
|---|---|---|
| 0 | Rango "¥1.050 – 1.050" con una sola reseña | Un solo valor ("¥1.050 por hora") cuando mínimo y máximo coinciden. |
| 1 | Falta el aviso de duplicado al proponer | Tarjeta en línea dentro de la sección "El lugar", con dos estados dibujados. "Sí" lleva a P4. |
| 2 | Administración solo en móvil | Escritorio de dos paneles para A1+A2; A3 y A4 siguen solo en móvil. |
| 3 | Sin aviso de cookies | Barra inferior para todos, "Aceptar" y "Rechazar" con el mismo peso; se activa recién cuando entren los anuncios. |
| 4 | Sin errores de validación | Errores junto a cada campo más resumen arriba. En visa de estudiante el campo se limita a 28 h en vez de dar error. |
| 5 | La tarjeta del mapa tapaba la mitad | Panel inferior de tres alturas (mínimo, medio, completo). |

## Pendientes y observaciones

- **Rango de salario "razonable"** para el error de validación: sin definir. No inventar cifras.
- **P1 escritorio:** los campos de salario mínimo y máximo no entran en la barra lateral y el segundo se sale del recuadro. Corregir al pasar a diseño visual.
- **Cookies:** el aviso solo está dibujado sobre el inicio; se asume que se muestra en cualquier pantalla hasta que el usuario elija.
- **Mapa:** es un marcador de posición. La librería de mapas se decide en la etapa de stack.
- **Sin dibujar (decisión consciente):** páginas de reglas de la comunidad, términos y privacidad; A3 y A4 en escritorio.
- **Estilo visual:** no definido en estos wireframes. Paleta decidida en [PRODUCT.md](PRODUCT.md): blanco, negro y grises, con rojo y azul solo como detalles.
