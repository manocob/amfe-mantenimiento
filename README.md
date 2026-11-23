# AMFE de mantenimiento · App para el aula

Aplicación web para hacer **AMFE (Análisis Modal de Fallos y Efectos)** de mantenimiento con alumnos de Formación Profesional. Funciona en cualquier navegador, **sin registro y sin servidor**: todo se guarda en el propio navegador.

**Usar la app:** https://manocob.github.io/amfe-mantenimiento/

## Qué permite hacer

Los alumnos siguen los 8 pasos del AMFE:

1. **Mapa del proceso** al estilo de un mapa de flujo de valor (VSM). Tiene bloques de proveedor, proceso, control, almacén, transporte y cliente. Los bloques se arrastran y se unen con flechas, y se puede marcar el equipo analizado y los pasos críticos.
2. **Equipo de trabajo**, con coordinador y papeles.
3. **Pasos críticos**, justificados por salud y seguridad, calidad y disponibilidad.
4. a 7. **Análisis AMFE.** Para cada fallo se anotan el modo de fallo, el efecto y la gravedad (G), la causa y la ocurrencia (O), y el control actual y la detección (D). La app calcula el **NPR = G × O × D**, lo colorea según el umbral y avisa de los fallos de seguridad.
8. **Acciones correctoras**, con tipo, responsable, fecha y el nuevo G, O y D. La app recalcula el **NPR(2)** y muestra el porcentaje de reducción.

Al final hay un **resumen** con el gráfico del NPR antes y después de las acciones, la **matriz de riesgo G × O**, la **revisión rápida** de incoherencias y la **comprobación automática de mínimos** de cada paso. Desde ahí se puede imprimir o guardar el informe en PDF, exportar la tabla a Excel (CSV) y descargar el archivo de entrega.

### Más utilidades

- **Funciona en ordenador, tableta y móvil** (Windows, Mac, Android e iPhone) desde el navegador, sin instalar nada. En el móvil el mapa se desliza de lado y los bloques se arrastran con el dedo; doble toque para abrir el mapa de detalle. Navegadores recomendados: Chrome, Edge, Firefox o Safari actualizados (iOS 16.4 o posterior).
- **Dos ejemplos resueltos** para enseñar: una bomba de refrigeración (un nivel) y una **línea de estampación transfer de 4 operaciones** con tres niveles de mapa (flujo de valor de la planta › estampación › prensa transfer), 14 fallos y sus acciones.
- **Guardar y seguir desde otro ordenador.** El botón **Guardar** (o Ctrl/Cmd + S) descarga un **informe .html** que se lee e imprime como un documento y lleva dentro todos los datos. En otro ordenador basta con abrir la app y pulsar **«Abrir informe guardado»**. El informe incluye además un **código de continuación**, así que incluso desde el PDF impreso se puede recuperar el trabajo con «Pegar código».
- **Mapas de detalle por niveles.** Cualquier bloque del mapa se puede abrir en un mapa de detalle con sus mini procesos (doble clic o «Crear mapa de detalle»), y estos a su vez en otro. Cada mini proceso puede tener sus propios fallos. Ejemplo: la prensa transfer de una línea de estampación descompuesta en devanadora, aplanadora, lubricadora, rodillo alimentador, transfer, módulos del troquel, salida al conveyor y operario que coloca las piezas en la jaula. El caso G trae esta plantilla lista para cargar.
- **Revisión rápida.** Avisos automáticos de incoherencias: detección baja sin ningún control, fallos de seguridad bajo el umbral, acciones que no reducen el NPR, gravedad que cambia tras una acción, efecto igual al modo de fallo…
- **Filtro de fallos por paso** del mapa, útil cuando hay muchos mini procesos.
- **Importar fallos del caso** como punto de partida.
- **Deshacer y rehacer** (Ctrl/Cmd + Z y Ctrl/Cmd + Y), **duplicar bloques** y **ayuda con glosario** del AMFE.
- En el modo profesor, **compartir con la clase**: genera el enlace con el caso y el umbral ya elegidos y su **código QR** para proyectarlo. Incluye además un resumen de la nota media y de las entregas evaluadas.

## Cómo se usa en clase

**Alumnos**

1. Abren la app y rellenan el grupo, los alumnos y el caso. Hay casos preparados (cinta transportadora, compresor, centro de mecanizado CNC, robot de paletizado y línea de estampación con prensa transfer), dos casos abiertos (inyectora y central hidráulica) y la opción de un caso propio.
2. Recorren los pasos. El trabajo se guarda solo en el navegador.
3. En **Resumen y entrega** descargan el **informe de entrega** (`.html`) y lo suben a la tarea de Classroom, o del aula virtual que uséis. Si el profesor lo prefiere, también pueden copiar un **código de entrega** y pegarlo en la tarea.
4. Al terminar cada sesión pulsan **Guardar**. Para seguir en otro ordenador: en Inicio, «Abrir informe guardado» y eligen el `.html`.

**Profesor**

1. Pulsa **Modo profesor**, o abre la app con `#profesor` al final del enlace.
2. Arrastra a la ventana todos los informes `.html` (o archivos `.amfe.json`) de la tarea, o pega los códigos.
3. Revisa cada entrega: el mapa, las tablas, el gráfico y los mínimos.
4. Evalúa con la **rúbrica de 8 criterios**. Los pesos se pueden configurar. La nota sugerida sale de la comprobación de mínimos y puedes ajustar cada criterio, añadir comentarios y fijar la nota final.
5. Exporta las notas en **CSV** (se abre en Excel) o imprime el informe de cada grupo con su evaluación.
6. Haz una **copia de seguridad** de tus evaluaciones si vas a cambiar de ordenador.

**Enlaces con el caso ya elegido:** `?caso=A`, `?caso=B`… y también `?umbral=120` o `?curso=1ºCE`. Por ejemplo: `https://manocob.github.io/amfe-mantenimiento/?caso=C&umbral=100`

## Privacidad

No hay servidor, cuentas ni cookies. Los datos de los alumnos solo salen de su navegador cuando ellos descargan el archivo o copian el código. Las evaluaciones del profesor se guardan solo en el navegador del profesor.

## Personalizar

Toda la app está en un único archivo, `index.html`. Algunos cambios habituales:

- **Casos:** el objeto `CASOS`, con título, descripción y fallos de referencia.
- **Escalas de G, O y D:** el objeto `SCALES`.
- **Rúbrica y pesos por defecto:** el objeto `RUBRIC`.
- **Papeles del equipo:** el objeto `ROLES`.

Para publicar tu propia copia: haz un *fork* de este repositorio y activa **GitHub Pages** en *Settings → Pages → Deploy from a branch → main / root*.

El código QR se genera con la librería QRCode for JavaScript de Kazuhiko Arase (licencia MIT), incluida en el propio archivo.

## Créditos y licencia

Creada por **Manuel Cobos Velázquez** para el módulo *Estrategias del Mantenimiento Industrial* (Curso de Especialización en Digitalización del Mantenimiento Industrial). Se ha desarrollado con la ayuda de Claude (Anthropic).

Las escalas de valoración y los pasos del AMFE siguen los materiales de la unidad didáctica de Metodología AMFE del módulo.

Licencia [MIT](LICENSE): puedes usarla, copiarla y adaptarla libremente citando la autoría.
