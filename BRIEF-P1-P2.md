# Brief de diseño: resultados (P1) y ficha de lugar (P2)

Estado: aprobado por el usuario el 2026-10-31. Dirección elegida: **Línea de estaciones** (señalética del metro de Tokio y de JR). Es un brief de diseño, no una especificación técnica; no define stack ni escribe código. Contexto del producto en [PRODUCT.md](PRODUCT.md); estructura de pantallas en [WIREFRAMES.md](WIREFRAMES.md).

Referencia visual: [referencias/estaciones-boceto-p1.html](referencias/estaciones-boceto-p1.html), boceto de la primera pantalla de resultados en móvil con datos de ejemplo. Es una referencia de ambiente, no un diseño final: la composición definitiva se decide al construir.

## 1. Trabajo y público

Una persona con visa Working Holiday o de estudiante, o que investiga antes de aplicar, que decide a dónde postularse. Llega con 3 o 4 lugares en mente, desde el celular, y los compara. Modo: **operar** (completar una tarea).

## 2. Resultado y prueba

- Acción principal: decidir "me sirve / no me sirve" sin entrar a cada lugar.
- Éxito: en pocos segundos ve el **salario por hora** y el **alojamiento** de cada lugar y su vigencia.
- Prioridad de la ficha (P2): **salario y alojamiento primero**, luego vigencia y confianza ("basado en N reseñas"), luego condiciones y reseñas.
- Prioridad de los resultados (P1): **lista primero**; el mapa es apoyo para ubicarse.

## 3. Dirección elegida

**Idea:** cada lugar es una parada de metro. Un círculo con código de zona y número (por ejemplo H-17, N-09) sobre una línea vertical gruesa. Es la señalética que el público va a leer a diario en Japón.

- **Qué presta el mundo del metro (solo cuatro cosas):** tipografía, paleta, densidad y un gesto propio (el círculo de estación). No presta el diseño de la página, la navegación ni los controles: esos son los habituales de la web.
- **Primera pantalla de P1 en móvil:** barra negra con el nombre del sitio y "Proponer lugar"; buscador y filtros en una fila; contador "38 lugares"; la línea con una parada por lugar. Cada parada: círculo con código, nombre, rubro y ciudad, **salario por hora grande a la derecha**, etiquetas (alojamiento, temporada, idioma) y la vigencia con ícono y texto.
- **P2:** abre como el cartel de una estación: círculo con el código y el nombre en español y japonés. Debajo, dos bloques grandes: salario y alojamiento. Después condiciones, reseñas, ubicación y contacto, fechas y acciones, y el bloque único de avisos.
- **Mapa:** los pines son los mismos círculos con su código; los grupos muestran la cantidad. El pin seleccionado es rojo.
- **Escritorio:** filtros en una barra lateral izquierda y tarjetas en dos columnas (como en los wireframes). La ficha lleva una columna lateral fija con ubicación, contacto y acciones.
- **Color (paleta fijada por el usuario):** blanco, negro y escala de grises como base. **Rojo** = lo seleccionado. **Azul** = lo interactivo (filtros activos, enlaces, botón principal). **Círculo gris punteado** = vigencia vencida, siempre acompañado del texto "! Se desconoce si sigue activo". Nunca usar los rayos de la bandera del sol naciente; el círculo rojo plano de la bandera actual sí es válido.
- **Tipografía:** sans con versión japonesa (BIZ UDPGothic y Zen Kaku Gothic New como punto de partida). Evitar las tipografías de uso automático (Inter, DM Sans, Space Grotesk, entre otras).
- **Cifras:** numerales tabulares, para que los ¥ de todas las tarjetas se alineen y se comparen de un vistazo.

## 4. Alcance y límites

- Alcance: dirección visual y brief de P1 (lista y mapa) y P2 (ficha). P3 a P7 y administración heredan el sistema cuando se construyan.
- Fidelidad: brief y dirección; sin código ni prototipo todavía.
- No se toca: contenido, reglas de salario y horas, flujos ni pantallas definidos en [PRODUCT.md](PRODUCT.md) y [WIREFRAMES.md](WIREFRAMES.md).
- Anti-objetivos: ningún diseño tipo plantilla (tarjetas redondeadas con sombra suave, degradados, íconos genéricos); ninguna ruta geográfica sugerida por la línea.

## 5. Estados y rangos

- Una sola reseña: salario como valor único ("¥1.050"), no como rango.
- Datos incompletos: "Sin datos aún" con la invitación a completar con una reseña.
- Vigencia vencida: círculo punteado gris más texto; el aviso va arriba del salario en la ficha.
- Sin resultados: estado vacío con "Quitar filtros" y "¿Conocés un lugar? Proponelo".
- Rangos reales: lista de decenas de lugares (38 en los ejemplos); entre 1 y unas decenas de reseñas por lugar; salarios de ejemplo entre ¥1.000 y ¥1.400 por hora. Todo dato de ejemplo debe verse como ejemplo.

## 6. Interacción y composición

- La línea vertical es solo ritmo visual: **no implica orden geográfico ni recorrido**. Los resultados se ordenan por reseña más reciente.
- Lista y mapa se alternan al mismo nivel sin perder los filtros.
- El mapa en móvil usa un panel inferior de tres alturas (mínimo, medio, completo), como en los wireframes v2.
- Un solo bloque de avisos por pantalla; el aviso del salario va junto al dato.
- Estados de vigencia y de error: ícono + texto además del color.

## 7. Restricciones y decisiones abiertas

- Accesibilidad: contraste suficiente con una paleta casi monocromática; estándar formal sin fijar (recomendado: WCAG AA).
- El texto de los sellos y códigos debe ser legible en móvil (en el boceto era muy chico).
- **Decisión abierta:** cómo asignar el código de zona a lugares fuera de las cinco zonas fuertes (Hokkaido, Nagano, Okinawa, Tokio, Kioto). Propuesta: usar las regiones de Japón (Hokkaido, Tohoku, Kanto, Chubu, Kansai, Chugoku y Shikoku, Kyushu, Okinawa).
- **Decisión abierta:** esquema de numeración de cada parada (por zona o global) y su uso como dirección estable del lugar.
- El tipo de letra definitivo y los tokens se fijan al construir; el archivo DESIGN.md se escribe al terminar la construcción, no antes.
