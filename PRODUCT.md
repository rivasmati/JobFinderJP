# Product

<!-- impeccable:product-schema 1 -->

Fuente de verdad detallada: [Mapa de trabajos en Japón definición del producto.md](Mapa%20de%20trabajos%20en%20Japón%20definición%20del%20producto.md). Este archivo resume lo durable; ante una diferencia, manda aquel documento.

## Platform

web

## Stack

delegated: el usuario delegó la elección en Claude (2026-10-10). Todavía no está elegido; se define en una sesión dedicada de stack. Restricciones confirmadas que esa elección debe respetar:

- Costo mínimo: los ingresos por publicidad solo cubren dominio, hosting y moderación con IA.
- Web responsive con prioridad móvil; sin app nativa.
- Sin cuentas de usuario ni login público; un único administrador.
- Mapa con pines agrupados por zona.
- Clasificación de cada envío con IA antes de la aprobación manual.
- Analíticas agregadas sin cookies; publicidad no personalizada.

Decisiones del usuario (2026-10-31):

- Publicación en un subdominio, sobre un hosting que el usuario ya tiene. Costo adicional: cero. Tipo de hosting confirmado: compartido con cPanel, PHP y MySQL (sin Node.js). Falta confirmar versión de PHP, acceso SSH y si permite Composer.
- Sin gasto en IA de pago. La IA de moderación deja de ser obligatoria; ver la decisión de moderación en la sesión de stack.
- El administrador trabaja desde una computadora, no desde el celular.

## Users

Hispanohablantes (Argentina, Chile, Uruguay, España) con visa Working Holiday o de estudiante en Japón, o que investigan antes de aplicar. Buscan trabajo no formal y hoy dependen de grupos de WhatsApp y Facebook y de recomendaciones personales. Usan el sitio sobre todo desde el celular para decidir a dónde postularse y qué esperar ahí.

Audiencia confirmada: 1.200 visas Working Holiday por año; estudiantes y personas que investigan, sin dato.

Segundo rol: el administrador (una sola persona), que verifica lugares y modera todos los envíos.

## Product Purpose

Directorio web con un mapa de Japón donde la comunidad propone lugares de trabajo que contratan extranjeros con esas visas. Cada lugar tiene una ficha de condiciones reales (salario por hora, alojamiento, idiomas, horas) y reseñas anónimas. Todo se verifica y aprueba antes de publicarse.

Existe para reducir la incertidumbre al buscar trabajo en Japón. Es un proyecto de comunidad y portfolio; los ingresos son secundarios.

Métricas a observar, sin metas definidas: lugares creados, reseñas por lugar, porcentaje de lugares con aviso de vigencia, denuncias por mes, visitas mensuales.

## Positioning

Registro persistente y buscable de lugares (no avisos que vencen), escrito por trabajadores hispanohablantes que estuvieron ahí, con salario y alojamiento estructurados y comparables. Ninguna plataforma analizada combina reseñas de trabajadores Working Holiday, condiciones estructuradas y español.

Complementa a los grupos, no los reemplaza: responde "¿a dónde me conviene postularme y qué me espera ahí?", no "¿quién contrata hoy?". Un lugar no es una vacante.

Es una vidriera curada, no una red social.

## Operating Context

- Lectura libre sin registro. Contribución por un único formulario, sin cuenta ni email.
- 8 pantallas públicas (P0 inicio/buscador, P1 resultados lista y mapa, P2 ficha, P3 proponer lugar, P4 agregar reseña, P5 envío recibido, P6 denunciar o pedir baja, P7 informativas) y 4 de administración (A1–A4).
- Lista por defecto, ordenada por reseña más reciente, con mapa al mismo nivel.
- Navegación global: buscador, botón "Proponer lugar" siempre visible, pie con páginas informativas.
- Nombres de lugares y ciudades en alfabeto latino y japonés; la búsqueda acepta ambos.
- Contacto: enlace a Google Maps o canales oficiales del negocio. Se guarda solo el enlace, no se copian datos de Google.
- El envío no se notifica: una ventana confirma la recepción y el plazo de hasta 48 horas.

## Capabilities and Constraints

- **Rubros (lista cerrada):** hotelería, ski resort, resort de playa, gastronomía, granja, tours y guías, comercio, enseñanza de idiomas, limpieza.
- **Filtros:** ciudad o prefectura, rubro, salario por hora mínimo y máximo, alojamiento, temporada o permanente, idioma y nivel, nombre.
- **Salario:** el único valor público es por hora, bruto, en yenes, como rango y siempre con "basado en N reseñas" y aviso de referencia. El monto mensual solo se usa para calcular (mensual ÷ (horas semanales × 4,33)).
- **Horas por visa:** 40 por defecto para Working Holiday; máximo 28 para estudiantes.
- **Reseñas:** anónimas, una por temporada, fechadas, no editables, sin nombres de personas. Puntuaciones de 1 a 5 más "¿lo recomendarías?". Las corregidas llevan la etiqueta "Editada por moderación".
- **Vigencia:** tras 18 meses sin reseñas, aviso "se desconoce si sigue activo". Se comunica con texto e ícono, nunca solo con color.
- **Datos faltantes:** se muestran como "Sin datos aún", con invitación a completar.
- **Avisos:** un solo bloque de avisos por pantalla.
- **Moderación previa total:** nada se publica automáticamente. Riesgo alto se rechaza en el momento con motivo.
- **Privacidad por diseño legal:** sin geolocalización, sin email en formularios, sin cookies de analítica. Contactos personales solo con confirmación de la persona.
- **Fuera del MVP:** cuentas, fotos, logos, mensajes entre usuarios, monto mensual visible, aviso de "busca personal", otros idiomas, importaciones.
- **Sin decidir:** nombre del producto; ejemplos de CV por rubro; límite de horas para españoles; modelo pago futuro.

## Brand Commitments

- **Nombre:** sin definir. "jobFinderJP" es solo el nombre de la carpeta. No inventar uno.
- **Idioma y voz:** solo español, neutro con voseo ("¿Conocés un lugar? Proponelo"). Directo y honesto sobre los límites del dato.
- **Paleta (decisión del usuario, vinculante):** blanco, negro y escala de grises; rojo y azul solo para detalles, en referencia a la bandera de Japón y al azul de la camiseta de la selección japonesa de fútbol.
- **Intención declarada:** intuitivo pero original; no debe parecer un diseño genérico de IA.
- Sin logo ni otros recursos de marca todavía.

## Evidence on Hand

- Documento de definición del producto (enlazado arriba), con análisis de competencia, referentes en Australia y riesgos legales con fuentes.
- No hay lugares ni reseñas cargados todavía (el plan es empezar con 4 o 5 lugares propios y una carga con grupos de Working Holiday). No fabricar lugares, reseñas, testimonios ni cifras de uso como si fueran reales; los datos de ejemplo deben verse como ejemplo.
- Sin fotos: el MVP no usa fotos ni logos de los lugares.

## Product Principles

1. **Un lugar no es una vacante.** El sitio ayuda a decidir a dónde postularse; nunca promete que contratan hoy.
2. **La confianza sale del proceso, no de la identidad.** Se verifica el lugar y se aprueba cada envío; no se identifica a quien escribe.
3. **La fecha es parte del dato.** Toda condición se muestra con cuán reciente es y en cuántas reseñas se basa.
4. **Contribuir tiene que costar poco.** Un solo formulario, mayormente de selección, sin registro.
5. **Recolectar lo mínimo.** Cada dato que no se pide reduce el riesgo legal y la carga de moderación.

## Accessibility & Inclusion

- Los estados (vigencia, riesgo, errores) se comunican con texto e ícono además del color.
- Prioridad móvil: lo esencial de cada pantalla se ve sin hacer scroll en el celular.
- Soporte de texto japonés junto al latino en nombres y búsqueda.
- Estándar formal (por ejemplo WCAG AA): no establecido todavía.
