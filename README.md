# Escrituración y entregas — Condominio Espacio Las Tablas Curauma

Página web para gestionar el avance de escrituración y entrega de cada cliente de Inmobiliaria Umbrales Quince SpA.

## Qué hace
- Lee los Excel **Control de Negocios** (hojas *Negocios*, *Pagos* y *Avance Escrituración*). Se pueden cargar los 3 archivos (AyB, CyD, EyF) a la vez.
- Muestra un tablero con los 6 pasos del proceso:
  1. Escritura lista para firma (banco si es crédito, inmobiliaria si es contado)
  2. Firma del cliente
  3. Recepción de copia maestra
  4. Validación financiera (saldo del precio y Fondo de Puesta en Marcha UF 4)
  5. Firma de la escritura por la inmobiliaria
  6. Entrega del departamento
- En la ficha de cada cliente se marcan los pasos con fecha y nota, se registra banco, ejecutivo, notaría, próxima acción, fecha compromiso y una bitácora (llamadas, correos, acuerdos).
- Alertas: días sin avance, compromisos vencidos, pasos fuera de orden, saldo o puesta en marcha pendientes.
- **Exportar seguimiento** descarga un Excel ordenado (hojas *Seguimiento*, *Resumen por etapa*, *Bitácora*). Ese mismo archivo es el respaldo: se vuelve a cargar con **Cargar archivos** para recuperar o mover el avance a otro computador.

## Dónde quedan los datos
- Los Excel **no se suben a internet**: se leen y quedan guardados solo en el navegador del computador que se usa.
- El avance también queda en ese navegador. Por eso hay que **exportar el seguimiento al final de cada día** (la página avisa cuántos cambios faltan por respaldar) y guardarlo en Drive.
- Usar siempre el mismo computador y navegador. No usar ventana de incógnito.

## Publicar en GitHub Pages (una vez)
1. En github.com, crear un repositorio nuevo (por ejemplo `escrituracion-umbrales`).
2. *Add file → Upload files*: subir `index.html`, `README.md` y `.gitignore`. **No subir Excel.**
3. *Settings → Pages → Build and deployment*: Source = *Deploy from a branch*, Branch = `main`, carpeta `/ (root)` → *Save*.
4. En 1–2 minutos la página queda en `https://<usuario>.github.io/escrituracion-umbrales/`.

## Ajustes
En `index.html`, bloque `CONFIG`:
- `DIAS_SIN_MOVIMIENTO` (10): días sin actualización para marcar alerta.
- `UF_PUESTA_EN_MARCHA` (4): UF exigidas de puesta en marcha.
- `TOLERANCIA_UF` (0,5): diferencia de saldo que se considera pagado.
