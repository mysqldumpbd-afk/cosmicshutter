# Changelog

Formato libre, en español, en orden descendente (lo más nuevo arriba).

## v20 — 2026-08-26

Revisión de producto orientada a dejar la app lista para empacarse como APK offline.

### Cambiado
- Rebranding completo: nombre de la app de "Cosmolancer" a **Cosmic Shutter** (título, encabezado, texto alternativo del logo, marca de agua e imagen exportada, claves de `localStorage`).
- Logo nuevo, recortado a transparencia real y optimizado a WebP (de 1.7 MB a ~110 KB).
- Panel de "Agradecimiento": las menciones al diseñador del juego original pasan de su nombre completo a "Dr. R.K.", y las menciones al nombre del juego de mesa original ("Cosmolancer") se reescribieron como "el juego que lo inspiró" — sin nombrar marca ni diseñador reales, en los tres idiomas.
- Selección de colores en la pantalla de configuración: reemplaza "cada jugador elige su color" (un casillero por jugador) por una selección directa de qué colores están en juego — pensado para que una sola persona cargue los datos por todos. Con 4 jugadores se activan los 4 colores automáticamente.
- Resultado de la ronda agrupado por jugador (colapsado al máximo por defecto), con el total de la ronda visible en el encabezado de cada grupo; las tarjetas de cámara individuales siguen expandibles una por una.
- Botones de "Acciones" reordenados en una cuadrícula por prioridad (calcular arriba, cerrar ronda/pruebas en el medio, reiniciar/cerrar partida separados abajo) en vez de una fila irregular.
- Etiquetas de botones acortadas: "Cerrar ronda y limpiar tablero" → "Cerrar ronda", "Cerrar partida (volver al inicio)" → "Cerrar partida".

### Arreglado
- Tipografías (Oxanium, Inter) auto-hospedadas como `@font-face` embebido en base64 — antes dependían de Google Fonts por red y rompían el modo offline.
- Persistencia de la partida en curso en `localStorage`: sobrevive a que Android mate la app en segundo plano a mitad de ronda.
- Fuga de textos en español dentro del desglose de fila/columna ("sin casillas en este segmento", "anulado", "hiperimpulso") que no pasaban por el sistema de traducción y se veían en español aunque la app estuviera en inglés o portugués.
- Contraste insuficiente (3.75:1) del texto de aviso de pie de página, ahora en 6.97:1.
- Panel de música flotando encima del logo sin separación visual — ahora tiene flecha de anclaje y un fondo oscurecido detrás.
- Botón de "Llenado automático (pruebas)" oculto por defecto, visible de nuevo a pedido para seguir probando.

### Limpieza
- Carpeta `app-build/` (y este repo) con solo lo que la app realmente usa: antes, empacar la carpeta completa del proyecto arrastraba ~100 MB de versiones viejas (v2–v19) y arte/audio sin usar, contra un peso real de ~9 MB.
