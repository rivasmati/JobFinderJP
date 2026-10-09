# Mapa de trabajos en Japón: definición del producto

Sep 30, 2026 · @Matias

## Resumen de la idea y objetivo

Directorio web en español, sin cuentas de usuario, con un mapa de Japón donde la comunidad propone lugares de trabajo que contratan extranjeros con visa Working Holiday o de estudiante. Cada lugar tiene una ficha de condiciones reales y reseñas anónimas, y todo se verifica y aprueba antes de publicarse: funciona como una vidriera curada, no como una red social.

**Objetivo:** reducir la incertidumbre de un hispanohablante al buscar trabajo en Japón, mostrando dónde contratan y en qué condiciones, validado por personas que trabajaron ahí.

**Problema que resuelve:** hoy la información está dispersa en grupos de Facebook y recomendaciones personales, sin datos comparables de salario, alojamiento ni vigencia.

**Naturaleza del proyecto:** comunidad y portfolio. Los ingresos son secundarios y solo deben cubrir costos.

## Público y alcance del MVP

El MVP es únicamente el mapa de trabajos con fichas y reseñas; todo lo demás queda afuera o en duda.

**Público:** hispanohablantes (latinoamericanos y españoles) con visa Working Holiday o de estudiante. Solo trabajos no formales. La plataforma funciona solo en español.

| Dentro del MVP | Fuera del MVP | En duda |
| --- | --- | --- |
| Mapa con pines por lugar de trabajo | Cuentas de usuario y login | Ejemplos de CV genéricos, uno por rubro |
| Ficha de lugar con campos estructurados | Banco de CVs subidos por usuarios | Modelo pago futuro (según analíticas) |
| Lectura libre, sin registro | Guía de visa propia (se linkea la guía maestra de YoMeAnimo) |  |
| Reseñas anónimas por formulario, una por temporada | Plataforma de alquileres (futuro) |  |
| Verificación del lugar antes de publicarlo | Importación desde Craigslist |  |
| Moderación previa con IA y aprobación manual | Idiomas distintos al español |  |
| Filtros de búsqueda | Monto mensual visible |  |
| Analíticas agregadas sin cookies | Aviso de "busca personal" |  |
| Publicidad no personalizada | Fotos, logos y mensajes entre usuarios |  |

**Rubros (lista cerrada):** hotelería, ski resort, resort de playa, gastronomía, granja, tours y guías, comercio, enseñanza de idiomas, limpieza.

**Filtros:** ciudad, rubro, salario por hora (mínimo y máximo), alojamiento sí o no, temporada o permanente, idiomas y nivel, nombre del lugar.

## Información de cada ficha de lugar

Cada lugar tiene una ficha pública que resume los datos de todas sus reseñas; un lugar no puede existir sin al menos una reseña.

| Campo | Formato | Fuente |
| --- | --- | --- |
| Nombre | Alfabeto latino, japonés opcional como referencia | Usuario |
| Ubicación | Pin en el lugar de trabajo, siempre | Usuario |
| Rubro | Lista cerrada | Usuario |
| Puestos habituales | Texto corto | Usuario |
| Temporada o permanente | Opción cerrada | Usuario |
| Salario | Rango por hora, bruto, en yenes | Calculado desde las reseñas |
| Horas semanales promedio | Número, 40 por defecto | Usuario |
| Horas mínimas garantizadas y horas extra (no entran en el cálculo de salario) | Mínimas: sí o no. Extra: se suelen hacer, se permiten o no se permiten | Usuario |
| Idiomas requeridos | Idioma y nivel | Usuario |
| Alojamiento | Sí o no, tipo y costo mensual | Usuario |
| Requisitos | Texto corto moderado | Usuario |
| Reseñas | Puntuaciones estructuradas más comentario corto | Usuario |
| Contacto | Público de Google Maps o cargado por el usuario | Usuario, con aprobación si es personal |
| Fechas | Publicación, última actualización, última reseña | Sistema |
| Estado de vigencia | Aviso tras 18 meses sin reseñas | Sistema |

## Reglas de salario y horas

El único valor visible es el salario por hora, bruto, en yenes; el monto mensual solo sirve para calcularlo.

1. El usuario puede ingresar el salario por hora o el monto mensual bruto (antes de descontar alojamiento y sin incluir horas extra).
2. Si ingresa mensual, el sistema calcula la hora con la fórmula de abajo y descarta el monto mensual de la vista pública.
3. Las horas semanales son 40 por defecto; el usuario puede modificarlas y el cálculo se actualiza.
4. La ficha muestra un rango (mínimo y máximo) de todas las reseñas del lugar.
5. Siempre se muestra un aviso: el valor es una referencia, puede variar, puede estar desactualizado y no es un dato exacto.

```latex
\text{salario por hora} = \frac{\text{monto mensual bruto}}{\text{horas semanales} \times 4{,}33}
```

Ejemplo: 200.000 yenes mensuales con 40 horas semanales equivalen a 200.000 ÷ 173,2 ≈ 1.155 yenes por hora.

**Alojamiento:** por defecto se asume descontado del sueldo cuando lo provee el empleador; el usuario puede aclarar lo contrario.

## Reseñas, contacto y vigencia

Las reseñas son anónimas y llegan por un formulario sin cuenta ni email; la confianza no sale de identificar a quien escribe, sino de verificar el lugar y aprobar cada envío.

**Reseñas**

- Solo sobre el lugar y roles genéricos (jefe, compañeros). Nunca nombres ni descripciones de personas.
- Una reseña por temporada trabajada, fechada y no editable. Otra temporada se carga como reseña nueva.
- Pregunta obligatoria de tipo de visa (Working Holiday o Estudiante), que ajusta el default de horas.
- Se confía en la palabra de quien reseña; los envíos repetidos o abusivos se bloquean.

**Contacto**

- Visible para todos: el enlace al lugar en Google Maps o los canales oficiales que publica el propio negocio.
- Contacto personal: queda pendiente, llega a tu bandeja de email y solo se publica si la persona confirma que quiere aparecer. La reseña se publica igual sin él.

**Vigencia y bajas**

- Antes de publicar un lugar nuevo, verificás que existe (por ejemplo, que figura en Google Maps con esa dirección).
- Cada reseña muestra su fecha y temporada.
- Tras 18 meses sin reseñas, el lugar muestra el aviso "se desconoce si sigue activo" hasta que una reseña nueva lo confirme.
- Si un negocio pide salir, se le pregunta el motivo y el lugar se oculta al público junto con sus reseñas. Queda visible solo para vos.
- Si coincide dirección o un nombre parecido, el formulario pregunta si es el mismo lugar.

## Moderación y protección legal

La protección no viene de los avisos solos, sino de poder demostrar un proceso: reglas claras, moderación previa, denuncias y respuesta rápida a pedidos de baja.

**Moderación previa total:** cada envío (lugar, reseña, contacto) pasa primero por un clasificador con IA y después por tu aprobación. Nada se publica automáticamente.

| Nivel de riesgo | Ejemplos | Acción |
| --- | --- | --- |
| Bajo | Opiniones sobre el lugar sin datos sensibles | Aprobación rápida |
| Medio | Acusaciones ambiguas, tono agresivo | Revisión detallada antes de aprobar |
| Alto | Insultos, nombres de personas, acusaciones de delitos, discriminación, datos personales | Rechazo automático con explicación |

**Prevención de trabajo ilegal**

- Rubros cerrados que excluyen actividades prohibidas para estas visas.
- Declaración obligatoria al crear un lugar: el trabajo es legal para visa Working Holiday o de estudiante.
- Aviso fijo sobre el límite de horas y el permiso de trabajo de la visa de estudiante.
- Denuncia específica "posible trabajo ilegal" con prioridad alta.

**Documentos legales**

- Términos de uso con reglas de contenido y bloqueo de envíos repetidos o abusivos.
- Aviso general: la plataforma no intermedia en la contratación ni garantiza la legalidad ni las condiciones de los empleadores.
- Política de privacidad: sin cuentas; qué datos técnicos mínimos se registran de cada envío y por cuánto tiempo; conservación interna del contenido oculto; entrega de datos solo por orden judicial; uso de analíticas sin cookies.

## Audiencia y monetización

La audiencia confirmada es de 1.200 visas Working Holiday por año, más estudiantes sin dato, suficiente para comunidad y portfolio, pero chica para que la publicidad genere más que la cobertura de costos básicos.

| Segmento | Visas por año | Estado |
| --- | --- | --- |
| Working Holiday Chile | 200 | Confirmado ([YoMeAnimo](https://www.yomeanimo.com/cl/japon-reabre-working-holiday-chilenos-que-cambia)) |
| Working Holiday Argentina | 400 | Confirmado (YoMeAnimo) |
| Working Holiday Uruguay | 100 | Confirmado (YoMeAnimo) |
| Working Holiday España | 500 | Confirmado (YoMeAnimo) |
| Estudiantes hispanohablantes que trabajan | Sin dato | Sin fuente |
| Personas que investigan antes de aplicar | Sin dato | Probablemente mayor que los visados |

Según las listas de convenios consultadas ([japan-guide](https://www.japan-guide.com/e/e2350.html)), Argentina, Chile y Uruguay son los únicos países latinoamericanos con Working Holiday en Japón.

**Monetización inicial:** Google Ads con anuncios no personalizados, para no rastrear la navegación de los usuarios. Ningún referente en Australia vive de publicidad, así que se asume solo como cobertura de costos.

```latex
\text{ingreso mensual} = \frac{\text{visitas} \times \text{páginas por visita} \times \text{pago por mil páginas}}{1000}
```

**Condición de viabilidad:** la arquitectura tiene que ser de costo mínimo para que los ingresos cubran dominio, hosting y moderación con IA. Se definirá en la etapa de stack.

**Evolución (decidido):** medir el uso con analíticas agregadas sin cookies y, si el tráfico lo justifica, pasar a un modelo pago. Reglas para esa transición:

1. Las fichas y reseñas escritas por la comunidad se mantienen gratis. Cobrar por contenido que otros aportaron gratis rompe la confianza que sostiene las contribuciones.
2. Lo pago son extras: alertas, guías, ejemplos de CV, acceso sin publicidad o publicaciones de empleadores.
3. Cobrar exige cuentas y pagos, lo que vuelve a recolectar datos personales; la revisión legal se repite en ese momento.
4. Antes de decidir, definir qué métricas lo justifican: visitas mensuales, usuarios que vuelven y reseñas por mes.

## Cosas a tener en cuenta

Los mayores riesgos del proyecto no son técnicos: son el arranque sin contenido, la carga de moderación sobre una sola persona y la exposición legal por contenido de terceros.

| Riesgo | Severidad | Mitigación |
| --- | --- | --- |
| Arranque en frío: 4 o 5 lugares propios no alcanzan para atraer usuarios | Grave | Carga concentrada con los grupos de Working Holiday antes de anunciar |
| Toda la moderación y verificación depende de vos | Grave | Clasificación con IA, reseñas mayormente estructuradas, límite de caracteres |
| Reseñas falsas de empleadores (positivas propias o negativas a competidores) | Moderado | Verificación del lugar, moderación previa, bloqueo de envíos repetidos |
| Datos desactualizados por la estacionalidad (queja principal en los referentes) | Moderado | Fecha y temporada visibles, aviso a los 18 meses |
| Incentivo: nadie está obligado a reseñar | Moderado | Formulario corto sin registro, mayormente de selección |
| Un desarrollador hispanohablante (WorkyDay) ya hace la misma idea para Australia | Moderado | Lanzar antes de que se expanda a Japón |
| Contactos personales sin consentimiento | Moderado | Nunca publicar sin confirmación de la persona |
| Aprobación de Google Ads requiere contenido suficiente | Leve | Solicitarla recién con fichas reales publicadas |
| Nombres duplicados en distintos alfabetos | Leve | Pregunta de coincidencia al crear |

**Métricas a observar desde el lanzamiento** (sin metas definidas todavía): lugares creados, reseñas por lugar, porcentaje de lugares con aviso de vigencia, denuncias por mes, visitas mensuales.

## Análisis de competencia

Ninguna plataforma analizada combina reseñas de trabajadores con visa Working Holiday, condiciones reales estructuradas y contenido en español; ese es el espacio libre. El competidor real no es otro sitio, sino el hábito de usar grupos de WhatsApp y Facebook.

| Competidor | Tipo | Idioma | Quién publica | Qué ofrece | Qué no cubre |
| --- | --- | --- | --- | --- | --- |
| Grupos de WhatsApp y Facebook | Directo | Español | Trabajadores y empleadores | Búsquedas activas con horas, salario y lugar | Alojamiento casi nunca, reseñas, búsqueda, historial persistente |
| [Epic Japan Jobs](https://www.epicjapanjobs.com/jobs/find/ski) | Directo | Inglés | Empleadores (gratis) | Trabajos para Working Holiday, filtros de alojamiento y comida, carga de CV | Reseñas de trabajadores, español |
| [YOLO Japan](https://www.yolo-japan.com/en/recruit/job/search) | Directo | Varios, sin español en su lista | Empleadores | Más de 300.000 usuarios, filtros por nivel de japonés, además vivienda y SIM | Reseñas, foco en Working Holiday |
| [Jobs in Japan](https://jobsinjapan.com/job-type/seasonal/) | Directo | Inglés | Empleadores | Categoría temporada, salario por hora, niveles de idioma, generador de CV japonés | Reseñas, español |
| [GaijinPot Jobs](https://jobs.gaijinpot.com/employer) | Indirecto | Inglés | Empleadores (pago) | Más de 8.000 empresas, sesgo a enseñanza y empleo formal | Trabajo de temporada no calificado, reseñas |
| [OpenWork](https://www.tokyodev.com/articles/is-there-a-japanese-equivalent-of-glassdoor) | Indirecto | Japonés | Empleados | Base de reseñas de empresas más grande de Japón | Negocios chicos, extranjeros, trabajo temporal |
| [JENZA](https://bunac.org/working-holidays/work-japan) y agencias similares | Indirecto | Inglés | Agencia | Paquete pago con visa, alojamiento inicial y trabajo asignado | Gratuidad, libertad de elección |
| [YoMeAnimo](https://www.yomeanimo.com/todo-lo-que-debes-saber-sobre-buscar-trabajo-en-japon) | Indirecto y posible aliado | Español | Editorial | Guía de visa, consejos para buscar trabajo, experiencias | Base de lugares, reseñas, mapa |
| Craigslist Japón | Directo | Inglés | Cualquiera | Avisos clasificados | Sin analizar en detalle |

**Diferencial propuesto:** registro persistente y buscable de lugares (no avisos que vencen), escrito por trabajadores hispanohablantes, con alojamiento y salario estructurados y reseñas del ambiente.

**Posicionamiento (decidido):** la plataforma complementa a los grupos, no los reemplaza. Responde "¿a dónde me conviene postularme y qué me espera ahí?", no "¿quién contrata hoy?". El aviso de "busca personal" confirmado por el empleador queda fuera del MVP; si se suma, lo activás vos a mano, con fecha visible y vencimiento a los 30 días.

**YoMeAnimo (decidido):** alianza de distribución postergada hasta cumplir el criterio: al menos un lugar con reseña en cada zona fuerte (ski en Hokkaido y Nagano, playa en Okinawa, Tokio y Kioto) y reseñas de la última temporada.

**Riesgos competitivos**

1. **Grave: lugar no es vacante.** Los grupos muestran búsquedas activas hoy; la plataforma muestra lugares que contrataron alguna vez. Si el usuario busca "quién contrata ahora", los grupos ganan. El valor está en decidir a dónde postularse y qué esperar, no en reemplazar los avisos.
2. **Moderado: filtros de alojamiento ya existen.** Epic Japan Jobs y YOLO Japan ya filtran por alojamiento; el diferencial no puede depender solo de ese campo, sino de que el dato venga de quien vivió ahí.
3. **Moderado: YoMeAnimo podría hacerlo.** Tiene audiencia en español y contenido de experiencias. Es a la vez la amenaza más probable y el mejor canal de distribución.
4. **Leve: el hispanohablante que maneja inglés** puede resolver con los sitios en inglés; el español es ventaja de comodidad, no de exclusividad.

**Referencia legal útil:** Epic Japan Jobs [aclara públicamente](https://www.epicjapanjobs.com/jobs/find/ski) que funciona como servicio de avisos, sin intermediación ni colocación. Es el tipo de posicionamiento a validar con un profesional para esta plataforma.

**Dato para la verificación pendiente:** una fuente secundaria ([Indeed España](https://es.indeed.com/orientacion-laboral/buscar-trabajo/como-trabajar-en-japon)) indica un límite de 28 horas semanales para estudiantes con permiso de trabajo. Falta confirmarlo en la fuente oficial japonesa.

## Referentes en Australia

Los productos equivalentes para mochileros en Australia son directorios curados por su equipo, verifican al negocio y no al usuario, y ninguno vive de publicidad.

| Producto | Qué hace | Cuentas | Modelo |
| --- | --- | --- | --- |
| [WikiFarms](https://play.google.com/store/apps/details?id=com.adrien.wikifarms&hl=en) | Mapa de granjas, contactos y reseñas; datos cargados y verificados por su equipo; operado desde Francia | No declara recolectar datos | App paga, sin publicidad |
| [The 88th Day](https://the88thday.com/) | Directorio en mapa, contador de días y recibos de sueldo; aclara que un listado no implica que contraten | Obligatoria | Freemium: 3 empleadores gratis por rubro y estado |
| [Farmwork4u](https://farmwork4u.com/) | Empleadores verificados en el registro de empresas y contactados antes de publicarse | Sí | Pago único de 12 dólares australianos |
| [88Finder](https://find88days.com/) | Verifica granjas en el registro de empresas y retira las que acumulan malas reseñas | Sí | Gratis con opciones pagas |
| [WorkyDay](https://apps.apple.com/bo/app/workyday/id6759898869) | Mapa de lugares donde suelen contratar mochileros, descrito en español | No declara recolectar datos | Gratis |

**Aprendizajes aplicados:** vidriera curada sin cuentas, verificación del lugar antes de publicar, posicionamiento de "lugar no es vacante", fecha visible como defensa contra la desactualización, y publicidad solo como cobertura de costos.

## Verificaciones

La audiencia total es de 1.200 visas Working Holiday hispanohablantes por año, y el límite de 28 horas semanales para estudiantes queda confirmado en fuente oficial.

| Dato | Resultado | Fuente |
| --- | --- | --- |
| Cupo Argentina | 400 por año (200 por semestre); los de 2026 están agotados | [YoMeAnimo](https://www.yomeanimo.com/working-holiday-japon-argentinos) |
| Cupo Chile | 200 por año | [YoMeAnimo](https://www.yomeanimo.com/working-holiday-japon-como-conseguir-la-visa-para-chilenos) |
| Cupo Uruguay | 100 por año | [YoMeAnimo](https://www.yomeanimo.com/working-holiday-japon-uruguayos) |
| Cupo España | 500 por año | [YoMeAnimo](https://www.yomeanimo.com/calendario-visas-working-holiday-para-espanoles) |
| **Total** | **1.200 visas por año** | Suma de las anteriores |
| Límite de horas de estudiantes | En principio 28 horas por semana, y prohibido trabajar donde funcionen negocios de entretenimiento adulto (風俗営業) | [Agencia de Inmigración de Japón](https://www.moj.go.jp/isa/applications/procedures/shikakugai_00001.html) |

**Inconsistencia a resolver (España):** una guía de YoMeAnimo para españoles menciona un límite de media jornada (4 horas diarias, 960 horas anuales) en el plan de viaje, mientras que su calendario actualizado indica que pueden trabajar los 12 meses sin limitaciones. Si el límite existe, el default de 40 horas sería incorrecto para españoles. Hay que confirmarlo con la Embajada de Japón en España.

## Riesgos legales

Sin cuentas ni datos de usuarios, el disparador principal de la ley laboral japonesa (recolectar datos de personas que buscan trabajo) probablemente desaparece, y el riesgo pasa a concentrarse en el contenido publicado. Operar desde Nueva Zelanda reduce la exposición práctica, pero no elimina los reclamos de negocios en Japón y suma la ley de privacidad neozelandesa. Nada de esta sección es asesoramiento legal.

| Frente | Riesgo | Severidad | Mitigación | Estado |
| --- | --- | --- | --- | --- |
| Ley de Seguridad del Empleo (職業安定法): servicio de información de empleo | Desde 2022 incluye sitios que [recolectan y publican información de empleo por su cuenta](https://ailaw.co.jp/blog/tokutei-boshu-jyoho-teikyo-guide-2026/); obliga a [información exacta y actualizada, corrección o baja sin demora y atención de reclamos](https://www.mhlw.go.jp/content/11600000/000983825.pdf) | Moderado | Vigencia, denuncias y bajas ya diseñadas | Cubierto por diseño |
| Notificación previa (特定募集情報等提供事業) | Obligatoria para quien recolecta datos de postulantes, que [incluyen emails, historial de navegación y ubicación](https://www.hakengyou.com/post-3245/) | Moderado | Sin cuentas, sin email en formularios, analíticas sin cookies y publicidad no personalizada | Probablemente evitado; confirmar |
| Frontera con la colocación laboral (職業紹介) | Elegir a quién mostrar qué, o cobrar por contrataciones, [puede encuadrar como colocación](https://nishi-jimu.com/shokai/shokai_400.html) | Moderado | Misma información para todos, nunca cobrar por contratación ni intermediar | Cubierto por diseño |
| Difamación de negocios | En Japón decir algo cierto no alcanza como defensa | Grave | Reseñas estructuradas, moderación previa total, sin nombres de personas, baja rápida | Cubierto por diseño |
| Pedidos de datos del autor de una reseña | Un afectado puede [pedir judicialmente los datos de quien publicó](https://www.kitahama.or.jp/topics/latest-00002/) | Leve | Registrar solo datos técnicos mínimos y por poco tiempo | A definir |
| Facilitación de trabajo ilegal | Contratar estudiantes fuera de su permiso es delito [para el empleador](https://www.jinzaiplus.jp/posts/66) | Moderado | Rubros cerrados, declaración obligatoria, límite de 28 horas, denuncia prioritaria | Cubierto por diseño |
| Datos personales (Japón, Unión Europea, Nueva Zelanda) | Al no haber cuentas, el alcance se reduce a datos técnicos y contactos pendientes | Leve | Política de privacidad clara; confirmar las obligaciones de la ley neozelandesa | A confirmar |
| Contactos personales | Publicar datos de un individuo sin consentimiento | Moderado | Solo con confirmación de la persona | Resuelto |
| Datos de Google Maps | Los términos de Google limitan guardar y republicar sus datos | Moderado | Guardar solo el enlace al lugar; no copiar teléfonos ni fotos | A verificar |
| Publicidad de Google | Exige aviso de consentimiento de cookies para visitantes europeos | Leve | Aviso desde el lanzamiento; anuncios no personalizados | A verificar |
| Tu situación migratoria en Nueva Zelanda | Generar ingresos propios debe ser compatible con tu visa | Grave hasta confirmar | Confirmar que tu visa permite actividad independiente | Pregunta abierta |

**Recomendación práctica:** aunque el diseño sin cuentas probablemente evita la notificación, una consulta gratuita a la Oficina de Trabajo de Okinawa (労働局) antes de irte lo confirmaría con certeza. Llevá este documento como descripción del servicio.

## Mapa del sitio

El producto tiene 8 pantallas públicas y 4 de administración, pensadas para web responsive con prioridad móvil, sin app nativa.

| # | Pantalla | Acceso | Propósito |
| --- | --- | --- | --- |
| P0 | Inicio: buscador | Público | Elegir zona o condición antes de ver resultados, sin bloquear la exploración |
| P1 | Resultados: lista y mapa | Público | Ver, filtrar y comparar lugares |
| P2 | Ficha de lugar | Público | Ver condiciones, reseñas y contacto |
| P3 | Proponer lugar | Público | Cargar un lugar nuevo con su primera reseña |
| P4 | Agregar reseña | Público | Reseñar un lugar existente |
| P5 | Envío recibido | Público | Ventana emergente que confirma el envío y explica el plazo de revisión |
| P6 | Denunciar o pedir baja | Público | Reportar contenido o pedir que un negocio salga |
| P7 | Páginas informativas | Público | Cómo funciona, reglas de la comunidad, términos, privacidad, enlace a la guía de visa de YoMeAnimo |
| A1 | Cola de moderación | Solo vos | Revisar envíos ordenados por riesgo |
| A2 | Detalle de envío | Solo vos | Verificar el lugar y aprobar, corregir o rechazar |
| A3 | Contactos pendientes | Solo vos | Registrar la confirmación de cada persona |
| A4 | Denuncias, bajas y ocultos | Solo vos | Resolver reportes y restaurar lugares ocultos |

**Navegación global:** buscador, botón "Proponer lugar" siempre visible y pie con páginas informativas.

## Contenido por pantalla

Prioridad 1 se ve sin hacer scroll en móvil; prioridad 2 inmediatamente debajo; prioridad 3 al final o desplegable.

**P0 · Inicio: buscador**

| Prioridad | Contenido |
| --- | --- |
| 1 | Buscador grande de ciudad o prefectura (acepta alfabeto latino y japonés) |
| 1 | Accesos rápidos a zonas fuertes: ski en Hokkaido, Nagano, Okinawa, Tokio, Kioto |
| 2 | Accesos rápidos por condición: con alojamiento, temporada de invierno, temporada de verano |
| 2 | "Ver todos los lugares" |
| 2 | Última búsqueda recordada en el navegador del usuario |
| 3 | Botón "Proponer lugar" y enlace a "Cómo funciona" |

Sin geolocalización en el MVP: la ubicación del usuario es uno de los datos que activan la ley laboral japonesa.

**P1 · Resultados: lista y mapa**

| Prioridad | Contenido |
| --- | --- |
| 1 | Buscador por nombre o ciudad (acepta alfabeto latino y japonés) |
| 1 | Filtros: ciudad o prefectura, rubro, salario por hora mínimo y máximo, alojamiento, temporada o permanente, idioma y nivel |
| 1 | Vista de lista por defecto, ordenada por reseña más reciente, con alternancia a mapa al mismo nivel (el mapa agrupa los pines por zona) |
| 2 | Tarjeta de lugar (en la lista o al tocar un pin): nombre, rubro, ciudad, rango salarial por hora, alojamiento sí o no, temporada, idioma principal, estado de vigencia, cantidad de reseñas |
| 3 | Aviso breve: "Un lugar no es una vacante; consultá siempre al empleador" |

**P2 · Ficha de lugar**

| Prioridad | Contenido |
| --- | --- |
| 1 | Nombre (latino y japonés opcional), rubro, ciudad, temporada o permanente |
| 1 | Estado de vigencia con fecha de la última reseña |
| 1 | Rango de salario por hora en yenes, con "basado en N reseñas" y aviso de referencia |
| 1 | Alojamiento: sí o no, tipo, costo mensual, si se descuenta del sueldo |
| 2 | Idiomas y nivel, horas semanales promedio, horas mínimas garantizadas, horas extra |
| 2 | Puestos habituales y requisitos |
| 2 | Reseñas: temporada, tipo de visa, puntuaciones, comentario corto, fecha |
| 2 | Contacto: enlace a Google Maps y canales oficiales del negocio |
| 3 | Acciones: agregar reseña, denunciar, pedir baja como negocio |
| 3 | Bloque único de avisos: información de referencia, puede estar desactualizada, no es una vacante |

**P3 y P4 · Formularios de envío**

| Sección | Campos (\* obligatorio) | Condicionales | Pantalla |
| --- | --- | --- | --- |
| El lugar | Nombre\*, ubicación\* (enlace de Google Maps o buscador de dirección), rubro\*; aviso si parece duplicado |  | Solo P3 |
| Condiciones | Temporada o permanente, puestos, idiomas y nivel, requisitos, horas mínimas garantizadas, horas extra, ¿ofrece alojamiento? | Si es de temporada: qué temporada. Si ofrece alojamiento: tipo, costo mensual, si se descuenta del sueldo | Solo P3 |
| Tu experiencia | Tipo de visa\*, temporada trabajada\*, forma de pago\*, salario\*, ambiente general\*, trato de los jefes, compañeros, cumplimiento de lo pactado, ¿lo recomendarías?, comentario corto | Si el pago es mensual: horas semanales. Si la visa es de estudiante: horas limitadas a 28. Si hubo alojamiento: puntuación de alojamiento | P3 y P4 |
| Contacto | Contacto público del negocio, ¿querés sumar un contacto personal? | Si responde que sí: datos del contacto personal, que quedan pendientes | Solo P3 |
| Confirmación | Declaración de legalidad\* y aceptación de reglas\*, incluida la posible corrección por moderación |  | P3 y P4 |

Todos los campos están visibles en un único formulario; solo aparecen o desaparecen los condicionales según las respuestas. Una leyenda al inicio aclara que el asterisco marca los obligatorios.

**Puntuaciones de la reseña (decidido):** ambiente general (obligatoria), trato de los jefes, compañeros, cumplimiento de lo pactado (horas y pago) y alojamiento si corresponde, en escala de 1 a 5, más "¿lo recomendarías?" sí o no.

**A1 y A2 · Moderación:** envío, nivel de riesgo asignado por la IA con su motivo, alerta de posible duplicado, enlace para verificar el lugar en Google Maps, y acciones de aprobar o rechazar con motivo.

## Flujos clave

Seis recorridos cubren todo el MVP; cada uno indica sus bifurcaciones y estados especiales.

**F1 · Buscar un lugar**

1. El usuario entra a P0 y elige una zona, un acceso rápido o "Ver todos".
   1. Si ya buscó antes, P0 le ofrece retomar su última búsqueda.
2. Pasa a P1: lista de resultados con esos filtros, ordenada por reseña más reciente.
3. Ajusta filtros o cambia a mapa en cualquier momento sin perder los filtros.
   1. Sin resultados: estado vacío con "quitar filtros" y "¿Conocés un lugar? Proponelo".
4. Toca una tarjeta (o un pin en el mapa).
5. Abre la ficha (P2).

**F2 · Leer una ficha**

1. Ve primero vigencia, salario, alojamiento y temporada.
2. Baja a condiciones, reseñas y contacto.
3. Sale al contacto (Google Maps o canal oficial) o a una acción: agregar reseña o denunciar.
   1. Si el lugar tiene el aviso de vigencia, el bloque superior lo destaca antes que el salario.

**F3 · Proponer un lugar nuevo**

1. Toca "Proponer lugar" desde cualquier pantalla.
2. Pega el enlace de Google Maps o busca la dirección; completa nombre y rubro.
   1. Si coincide con un lugar existente: "¿Es este lugar?". Sí lleva a F4 con ese lugar; no continúa.
3. Completa su experiencia: visa, temporada, salario y puntuación de ambiente.
4. Completa los campos opcionales que quiera; los condicionales aparecen según sus respuestas.
5. Acepta la declaración y envía.
6. La IA clasifica al instante.
   1. Riesgo alto: se rechaza en el momento con el motivo y la opción de corregir.
   2. Riesgo bajo o medio: ventana emergente "Recibido. Lo revisamos y se aprueba o rechaza en un plazo de hasta 48 horas".

**F4 · Reseñar un lugar existente**

1. Desde la ficha, toca "Agregar reseña".
2. Completa visa, temporada, salario y puntuación de ambiente; y los opcionales que quiera.
3. Acepta la declaración y envía.
4. Misma clasificación que F3 y la misma ventana emergente de revisión.

**F5 · Denunciar o pedir baja**

1. Desde la ficha, elige "Denunciar contenido" o "Soy el negocio y quiero salir".
2. Elige el motivo; si es el negocio, deja un medio de contacto del negocio.
3. Pantalla de confirmación; el caso entra a A4.

**F6 · Moderar (solo vos)**

1. Entrás a A1: envíos ordenados por riesgo y antigüedad.
2. Abrís uno (A2): revisás el motivo de la IA, verificás el lugar en Google Maps y controlás duplicados.
3. Aprobás, rechazás con motivo, o corregís y aprobás.
   1. Si corregís (por ejemplo, borrar un nombre propio), la reseña publicada muestra la etiqueta "Editada por moderación".
4. Si incluye contacto personal, pasa a A3 hasta que la persona confirme.
5. En A4 resolvés denuncias y bajas: ocultar, mantener o restaurar.

## Diagnóstico de usabilidad

Las tres fallas graves de la contribución están resueltas; los flujos quedan aprobados para pasar a wireframes.

| # | Problema | Severidad | Solución | Estado |
| --- | --- | --- | --- | --- |
| 1 | Contribuir en 5 pasos sin registro provoca abandono en móvil | Grave | Un solo formulario con todos los campos visibles, obligatorios con asterisco y condicionales según las respuestas | Resuelto |
| 2 | Quien envía no sabe si su aporte se publicó | Grave | Ventana emergente con el plazo de revisión; se acepta que el resultado no se notifica | Resuelto: hasta 48 horas |
| 3 | Pines amontonados vuelven el mapa inutilizable en móvil | Grave | Lista por defecto y mapa al mismo nivel, con pines agrupados | Resuelto |
| 4 | Campos opcionales generan fichas con datos incompletos | Moderado | Mostrar "Sin datos aún" con invitación a completar desde una reseña | Nuevo |
| 5 | Con una sola reseña, el rango salarial parece un dato firme | Moderado | Mostrar siempre "basado en N reseñas" | Diseño |
| 6 | Las horas promedio mezclan estudiantes y Working Holiday | Moderado | Mostrar horas por tipo de visa | Diseño |
| 7 | Demasiados avisos generan ceguera | Moderado | Un solo bloque de avisos por pantalla y ayudas junto al dato | Diseño |
| 8 | La corrección por moderación no se puede avisar al autor porque no hay cuentas | Moderado | Consentimiento en el formulario y etiqueta pública "Editada por moderación" | Nuevo |
| 9 | Nombres del mismo lugar en distintos alfabetos | Leve | Búsqueda y detección de duplicados en ambos alfabetos | Diseño |
| 10 | Vigencia comunicada solo con color | Leve | Texto e ícono además del color | Diseño |

## Decisiones pendientes y próximos pasos

Las decisiones de producto están cerradas; quedan consultas legales y una verificación antes de invertir en desarrollo.

**Horas por tipo de visa (decidido):** la reseña pregunta de forma obligatoria con qué visa trabajó la persona: Working Holiday o Estudiante (turista no es opción, porque no permite trabajar). El default de horas es 40 para Working Holiday y el límite oficial para estudiantes, que además no pueden ingresar un valor mayor. El usuario puede ajustar sus horas reales y la cuenta se recalcula.

- [ ] Agregar la pregunta obligatoria de tipo de visa a la reseña
- [ ] Confirmar con la Embajada de Japón en España si hay límite de horas para españoles
- [ ] Consultar al 労働局 si el servicio requiere la notificación previa
- [ ] Decidir si se mantienen los ejemplos de CV por rubro
- [ ] Consultar a un profesional sobre términos de uso y privacidad
- [ ] Confirmar que tu visa en Nueva Zelanda permite ingresos propios por publicidad
