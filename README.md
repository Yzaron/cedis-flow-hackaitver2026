# CEDIS Flow — De la Orden de Compra al Embarque

**HackaITVER 2026 · Instituto Tecnológico de Veracruz · Categoría: Sistemas e Industrial**

## Integrantes del Equipo
- Alegre Carrillo Heber
- Alvarez Gonzaga Cristobal
- Barrera Sanchez Edir
- Coba Dias Hugo Alexander
- Flores Roman Oswaldo Abimael

## Descripción del Proyecto
**CEDIS Flow** es una solución web integral y **100 % operativa sin conexión a internet** diseñada para digitalizar, sincronizar y controlar de punta a punta la operación logística de un Centro de Distribución (CEDIS) de **4,000 m²** ($100 \times 40\text{ m}$, racks metálicos de $6\text{ m}$) que recibe alrededor de **35 camiones diarios** en **4 andenes de recibo** y abastece a **32 sucursales** mediante **3 andenes de embarque**.

El sistema elimina el desfase entre el flujo físico de mercancía y la información operativa aplicando las **8 reglas de operación del reto** en cinco módulos integrados:

1. **Agendamiento y Control de Caseta (Reglas 1 y 2):** Programación de citas por hora completa (8:00 a 18:00) sin traslapes por andén, validación de folio de factura único y filtro de acceso en caseta para rechazar unidades sin cita o fuera de horario.
2. **Factura por Bulto y Etiquetas QR (Reglas 3 y 4):** Desglose granular por bulto sin mezcla de productos (respetando el límite de $1,000\text{ kg}$ y $1.91\text{ m}^3$ por tarima) y generación nativa de etiquetas con código QR vectorial (**SVG ISO/IEC 18004**) descargables e imprimibles por Orden de Compra.
3. **Recepción y Validación en Andén (Regla 5):** Escaneo de bultos mediante lector portátil o cámara del dispositivo, con bloqueo y reporte en tiempo real ante mercancía no solicitada, excedentes duplicados o discrepancias contra factura.
4. **Almacenamiento en Racks y Embarque Consolidado (Reglas 6, 7 y 8):** Mapa visual de los **32 racks** ($4\text{ niveles} \times 8\text{ tarimas} = 32\text{ tarimas/rack}$), casilla obligatoria de verificación física (base $1.12 \times 1.15\text{ m}$, altura $\le 1.85\text{ m}$ y film de seguridad), candado que impide la salida de camiones tipo tortón ($12\text{ tarimas} / 12\text{ t} / 22.87\text{ m}^3$) por debajo del **90 % de capacidad**, y emisión automática de la **Relación de Embarque** en PDF con código QR para su recepción en sucursal.
5. **Costo y Viabilidad Económica (CAPEX / OPEX / ROI):** Modelo financiero paramétrico editable con persistencia local que dimensiona infraestructura de red industrial (APs Wi-Fi 6 IP67, switches PoE+), terminales Android rudos 2D, impresoras láser y consumibles mensuales, evaluando escenarios Conservador, Base y Optimista.

## Arquitectura Técnica
- **Stack:** HTML5, CSS3 y JavaScript puro (ES6+) autocontenido en un solo archivo, sin dependencias de servidores ni CDNs externos.
- **Generador QR Offline:** Motor vectorial SVG bajo el estándar **ISO/IEC 18004** (modo Byte UTF-8, versiones 1 a 15, corrección de errores Reed-Solomon nivel L).
- **Persistencia Local:** Almacenamiento automático del estado operativo y financiero mediante `localStorage`.

## Instrucciones de Ejecución
1. Descarga o clona este repositorio (o abre directamente la versión publicada en GitHub Pages).
2. Abre el archivo `index.html` (o `cedis-flow-v5.html`) en cualquier navegador moderno (Chrome, Edge o Firefox), incluso **sin conexión a internet**.
3. Haz clic en el botón **Cargar escenario demo** en la esquina superior derecha para precargar proveedores, citas, bultos con QR e inventario en racks.
4. Recorre las 5 pestañas para probar la simulación de rechazo en caseta, impresión de etiquetas QR, escaneo con detección de intrusos/excedentes, consolidación al $99.7\text{ \%}$ de la Sucursal 1 con exportación a PDF y simulación de retorno de inversión.

## Declaración de Originalidad y Uso de IA
Proyecto desarrollado íntegramente durante la jornada del **HackaITVER 2026** conforme a los artículos 16, 17 y 23 incisos f), g) y h) del Reglamento. Se utilizaron herramientas de inteligencia artificial generativa (**Claude** y **Gemini**) como apoyo para la estructuración de código web autocontenido, implementación del codificador QR ISO/IEC 18004 y depuración técnica, bajo auditoría y validación humana completa de los cinco integrantes del equipo.# cedis-flow-hackaitver2026
