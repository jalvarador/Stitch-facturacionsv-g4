# DESIGN.md — DTE Factura-SV

Sistema de diseño **«DTE El Salvador Fiscal Suite»**, extraído del proyecto de Google Stitch *Facturación Electrónica El Salvador*.

- **Fuente de verdad:** los tokens del `tailwind.config` en línea de cada vista (`views/*.html`) e `index.html`. Son idénticos en los cinco archivos.
- **Estilo:** «modernismo institucional de alta precisión». Superficies blancas sobre un lienzo azul muy claro, bordes finos, sombras mínimas y estados fiscales inequívocos (Recibido con Sello, Transmitido, Contingencia, Anulado).

---

## 1. Paleta de colores

### 1.1 Tokens principales

| Rol | Token Tailwind | Hex | Uso en las vistas |
|---|---|---|---|
| Primario | `primary` | `#000f1d` | Texto de marca y títulos de máximo énfasis |
| Contenedor primario | `primary-container` | `#0f2537` | Ítem activo del menú, botones oscuros, tarjeta «Total a pagar», cabecera de la portada |
| Sobre contenedor primario | `on-primary-container` | `#788da3` | Texto secundario sobre fondos navy |
| Sobre primario | `on-primary` | `#ffffff` | Texto sobre fondos navy |
| Secundario (acción) | `secondary` | `#0051d5` | Botones de acción («Firmar y Emitir», «Nueva Factura»), enlaces, montos de IVA |
| Contenedor secundario | `secondary-container` | `#316bf3` | Hover de botones azules |
| Terciario (validación) | `on-tertiary-container` | `#1a9e70` | Indicador «EN LÍNEA», textos de «Con Sello MH» |
| Contenedor terciario | `tertiary-container` | `#002a1b` | Insignia «Ambiente de Producción», banner «Consistencia Tributaria» |
| Terciario fijo | `tertiary-fixed` | `#85f8c4` | Fondo de la insignia «Aprobado con Sello», punto de estado |
| Terciario fijo atenuado | `tertiary-fixed-dim` | `#68dba9` | Acentos verdes sobre navy |
| Error | `error` | `#ba1a1a` | Montos negativos, DTE anulados o invalidados |
| Contenedor de error | `error-container` | `#ffdad6` | Fondo de la insignia «Anulado» y de la fila invalidada |
| Sobre contenedor de error | `on-error-container` | `#93000a` | Texto sobre `error-container` |

### 1.2 Superficies y neutros

| Token | Hex | Uso |
|---|---|---|
| `background` / `surface` / `surface-bright` | `#f8f9ff` | Lienzo base de la página |
| `surface-container-lowest` | `#ffffff` | Tarjetas, menú lateral, encabezado y tablas |
| `surface-container-low` | `#eff4ff` | Campos de búsqueda, cajas internas, selector de punto de venta |
| `surface-container` | `#e5eeff` | Cabeceras de tabla |
| `surface-container-high` | `#dce9ff` | Bordes finos (*hairlines*) y hover del menú |
| `surface-container-highest` / `surface-variant` | `#d3e4fe` | Barras de progreso vacías |
| `surface-dim` | `#cbdbf5` | Fondo atenuado |
| `on-surface` / `on-background` | `#0b1c30` | Texto principal y cifras |
| `on-surface-variant` | `#43474c` | Etiquetas y texto secundario |
| `outline` | `#74777d` | Etiquetas en mayúsculas e iconos atenuados |
| `outline-variant` | `#c3c7cd` | Bordes de controles |
| `inverse-surface` | `#213145` | Superficie invertida |
| `inverse-on-surface` | `#eaf1ff` | Texto sobre la superficie invertida |

### 1.3 Tonos fijos y otros (referencia completa)

| Token | Hex | Token | Hex |
|---|---|---|---|
| `primary-fixed` | `#cfe5fd` | `secondary-fixed` | `#dbe1ff` |
| `primary-fixed-dim` | `#b3c9e0` | `secondary-fixed-dim` | `#b4c5ff` |
| `on-primary-fixed` | `#061d2f` | `on-secondary-fixed` | `#00174b` |
| `on-primary-fixed-variant` | `#34495c` | `on-secondary-fixed-variant` | `#003ea8` |
| `inverse-primary` | `#b3c9e0` | `on-secondary-container` | `#fefcff` |
| `surface-tint` | `#4c6075` | `tertiary` | `#001209` |
| `on-tertiary-fixed` | `#002114` | `on-tertiary-fixed-variant` | `#005137` |
| `on-tertiary` / `on-secondary` / `on-error` | `#ffffff` | | |

### 1.4 Colores semánticos de estado DTE

Provienen de la guía narrativa de Stitch. Úsalos para nuevas insignias de estado.

| Estado | Fondo | Borde | Texto |
|---|---|---|---|
| Recibido con Sello | `#ecfdf5` | `#a7f3d0` | `#065f46` |
| Transmitido (en espera MH) | `#eff6ff` | `#bfdbfe` | `#1e40af` |
| Contingencia | `#fffbeb` | `#fde68a` | `#92400e` |
| Rechazado / Anulado | `#fef2f2` | `#fecaca` | `#991b1b` |

---

## 2. Tipografía

| Familia | Fuente | Uso |
|---|---|---|
| Interfaz y cifras | **Inter** (400, 500, 600, 700), de Google Fonts | Navegación, títulos, formularios y montos |
| Códigos legales | **JetBrains Mono** (400, 500, 600, 700), de Google Fonts | Número de control (`DTE-03-M001P001-…`), UUID, Sello de Recepción MH, NIT, NRC y DUI |
| Iconos | **Material Symbols Outlined**, de Google Fonts | Todos los iconos (`dashboard`, `post_add`, `find_in_page`, `assessment`…) |

### Escala tipográfica

| Token | Familia | Tamaño / interlínea | Peso | Tracking | Uso |
|---|---|---|---|---|---|
| `headline-xl` | Inter | 32px / 40px | 700 | -0.02em | Título de la portada |
| `headline-lg` | Inter | 24px / 32px | 600 | -0.015em | Título de página (h1) |
| `headline-md` | Inter | 20px / 28px | 600 | -0.01em | Títulos de sección |
| `headline-sm` | Inter | 16px / 24px | 600 | -0.005em | Títulos de tarjeta y marca |
| `body-lg` | Inter | 16px / 24px | 400 | — | Texto destacado |
| `body-md` | Inter | 14px / 20px | 400 | — | Texto base (`body`) |
| `body-sm` | Inter | 12px / 16px | 400 | — | Texto auxiliar |
| `fiscal-numeric-lg` | Inter | 24px / 32px | 700 | -0.02em | Cifras de los KPI |
| `fiscal-numeric-md` | Inter | 14px / 20px | 600 | -0.01em | Montos en tablas |
| `label-md` | Inter | 12px / 16px | 600 | 0.04em | Botones y chips |
| `label-sm` | Inter | 11px / 14px | 600 | 0.05em | Etiquetas en MAYÚSCULAS |
| `legal-code-sm` | JetBrains Mono | 12px / 16px | 500 | 0.02em | Códigos DTE y UUID |
| `legal-code-xs` | JetBrains Mono | 11px / 14px | 400 | 0.03em | Metadatos (fecha y hora, sello) |

**Regla:** los montos se alinean a la derecha y las etiquetas de sección van en mayúsculas con `tracking-wider`.

---

## 3. Espaciado, radios y elevación

| Espaciado | Valor | | Radio (`tailwind.config`) | Valor |
|---|---|---|---|---|
| `space-xs` | 0.25rem | | `rounded` (DEFAULT) | 0.125rem |
| `space-sm` | 0.5rem | | `rounded-lg` | 0.25rem |
| `space-md` | 0.75rem | | `rounded-xl` | 0.5rem |
| `space-lg` | 1.25rem | | `rounded-full` | 0.75rem ⚠️ |
| `space-xl` | 2rem | | | |
| `gutter` / `margin` | 1rem | | | |
| `gutter-desktop` | 1.5rem | | | |
| `margin-desktop` | 2rem | | | |

⚠️ En esta configuración `rounded-full` vale **0.75rem**, no 9999px. Para círculos perfectos usa `rounded-[9999px]`.

**Elevación:** las tarjetas usan `shadow-sm` con un borde de 1px `surface-container-high`. El menú lateral y el encabezado usan `shadow-[0_1px_8px_rgba(0,0,0,0.04)]`. Los modales se muestran sobre un fondo navy semitransparente.

---

## 4. Componentes repetidos

| Componente | Dónde aparece | Anatomía y clases clave |
|---|---|---|
| **Menú lateral** | Las 4 vistas | `aside` fijo de `w-72` en `surface-container-lowest`, con logo, selector «Punto de Venta», enlace «← Volver al inicio», grupos «Operación Fiscal» y «Cumplimiento y Firma», y la caja «Estado MH SV · EN LÍNEA» al pie. El ítem activo lleva `bg-primary-container text-on-primary`. |
| **Encabezado superior** | Las 4 vistas | Barra `fixed h-16` con `backdrop-blur`. Contiene la insignia «Ambiente de Producción – MH SV» (`tertiary-container`), el certificado digital vigente, el establecimiento activo y el usuario con su avatar. |
| **Cabecera de página** | Las 4 vistas | Ruta en `label-sm` mayúsculas, h1 en `headline-lg` y acciones a la derecha. |
| **Tarjeta KPI** | Dashboard, Consulta, Reportes | `rounded-xl` con borde `surface-container-high`. Lleva etiqueta en mayúsculas, icono en una caja `surface-container-low`, cifra en `fiscal-numeric-lg` y una nota en `legal-code-xs`. |
| **Tabla de documentos** | Dashboard, Consulta, Emisión | Cabecera `surface-container` en mayúsculas, códigos en JetBrains Mono, montos a la derecha y filas separadas por *hairlines*. La fila anulada lleva fondo `error-container` y texto tachado. |
| **Insignia de tipo DTE** | Dashboard, Consulta | `01 Factura`, `03 CCF`, `05 Nota de Crédito`, `06 Nota de Débito`, con fondos suaves azul, navy o rojo. |
| **Insignia de estado MH** | Dashboard, Consulta | «Aprobado con Sello» o «Recibido MH» en verde, «Transmitido» en azul, «Anulado» en rojo. |
| **Chips de filtro** | Consulta | Píldoras `label-md`. La activa lleva `bg-primary-container text-on-primary`. |
| **Botones** | Todas | **Primario de acción:** `bg-secondary text-on-secondary`. **Primario oscuro:** `bg-primary-container`. **Secundario:** blanco con borde `surface-container-high`. **Destructivo:** fondo `error-container` con texto `error`. |
| **Resumen fiscal / Total a pagar** | Emisión, Reportes | Bloque de subtotal, IVA 13 % y retención 1 %, con el total en una tarjeta navy y `fiscal-numeric-lg`. |
| **Código copiable** | Emisión, Consulta | Valor en JetBrains Mono con el icono `content_copy` (número de control, UUID, sello). |
| **Pestañas** | Emisión (tipo de DTE), Reportes (anexos F-07) | La pestaña activa se resalta con un fondo navy o un borde inferior `secondary`. |

---

## 5. Reglas de uso

1. Usa siempre los **tokens**, por ejemplo `bg-secondary` o `text-on-surface-variant`, y no hex sueltos.
2. Escribe **JetBrains Mono** solo para identificadores fiscales y legales, y **Inter** para todo lo demás.
3. El **verde** se reserva para la validación de Hacienda (sello recibido o en línea) y el **rojo** para anulado, rechazado o montos negativos.
4. Para la densidad, prefiere bordes finos de 1px a sombras marcadas.
5. Cada vista mantiene el menú lateral con el enlace **«← Volver al inicio»** hacia `../index.html`.
