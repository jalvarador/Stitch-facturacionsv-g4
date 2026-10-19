# Prompts usados en Google Stitch

Registro de los prompts con los que se diseñó el proyecto *Facturación Electrónica El Salvador* en Google Stitch.

## 1. Creación del proyecto inicial

> Diseña pantallas un sistema de Facturación Electrónica (DTE) de El Salvador según normativa de la DGII / Ministerio de Hacienda, incluye pantallas de Generación de factura consumidor final, crédito fiscal , nota de débito y crédito. diseña un  Dashboard, creación de factura y consulta de facturas.

## 2. Solicitud de simplificación por sobrecarga

> "Podemos revisar vistas veo muy sobrecargadas los diseños que sea con la información necesario e intuitiva"

## 3. Rediseño limpio del Dashboard y Emisión

> "Rediseñar las 3 pantallas con el enfoque limpio"

## 4. Modal interactivo de QR y Sello

> "Agregar modal interactivo para ver el QR y Sello MH al hacer clic en 'Detalle'"

## 5. Búsqueda y trazabilidad por Sello MH

> "Integrar filtro para buscar directamente por Sello de Recepción MH"

## 6. Reportes tributarios oficiales DGII

> "Genera vistas de reportes e informes F-07"

## Resumen del flujo construido

Con estos prompts se establecieron las 4 vistas finales del sistema:

| Vista final | Archivo | Prompts de origen |
|---|---|---|
| Dashboard Fiscal Limpio | `views/dashboard-fiscal.html` | #1, #2 y #3 |
| Emisión Rápida e Intuitiva DTE | `views/emision-dte.html` | #1, #2 y #3 |
| Consulta y Búsqueda por Sello MH (con Modal QR) | `views/consulta-trazabilidad.html` | #1, #2, #3, #4 y #5 |
| Reportes e Informes F-07 | `views/reportes-f07.html` | #6 |
