# Rutas de Tibia — Crónicas del continente

Juego RPG de navegador inspirado en Tibia. Proyecto fan independiente y no oficial.

## Activación

Clave de demostración: `RUTAS-2026-ORBE-7K9P`.

La activación se guarda en `localStorage` del navegador. **No es un sistema de licencias seguro**: al ser una aplicación estática, la clave se puede localizar en el código fuente. Para licencias privadas, usuarios y validación real se necesita un backend.

## Ejecutar en local

1. Descarga o clona este repositorio.
2. Abre `index.html` en un navegador moderno.
3. Para una experiencia más fiable, utiliza un servidor local (por ejemplo, Live Server de Visual Studio Code).

No requiere Node.js, compilación ni dependencias externas para la lógica principal.

## Publicar en GitHub Pages

1. Sube `index.html`, `README.md` y `.gitignore` a la raíz del repositorio.
2. En GitHub abre **Settings → Pages**.
3. En **Build and deployment**, selecciona **Deploy from a branch**.
4. Selecciona la rama `main` y la carpeta `/ (root)` y guarda.

## Cambios de esta versión

- Interfaz de escritorio optimizada para 1920×1080; el mapa ocupa el área principal y el panel lateral contiene personaje, equipo, mochila y hechizos.
- Cacería automática al crear o recuperar un personaje; los encuentros ejecutan ataques y rotaciones sin pulsar botones de combate.
- Cuatro vocaciones de Tibia: Knight, Paladin, Sorcerer y Druid. El identificador interno `rogue` se conserva para no romper perfiles previos, pero se presenta como Paladin.
- Rotaciones automáticas que priorizan el hechizo de daño disponible más potente y curación cuando la salud cae; Exori Gran se desbloquea para Knight a nivel 90.
- Cooldowns de hechizos gestionados en tiempo real (segundos), con bloqueo compartido por grupo de ataque y curación.
- Loot con tiradas independientes por objeto; un monstruo puede soltar varios objetos en una misma muerte. Los objetos apilables se acumulan hasta 100 por pila.
- Validación adicional al dividir pilas para evitar referencias inválidas y cantidades incorrectas.
- Experiencia por nivel mediante la fórmula real de Tibia: `50/3 × (L³ − 6L² + 17L − 12)`. Por ejemplo, nivel 2 = 100 XP, nivel 8 = 4.200 XP y nivel 90 = 11.365.300 XP.
- Experiencia de criaturas revisada con tablas de referencia; Rat = 5 XP, Troll = 20, Amazon = 60, Vampire = 305, Warlock = 4.000 y Demon = 6.000.
- Rutas ordenadas por zonas: Rookgaard, Thais, Carlin, Edron y Demona; se amplían las criaturas de Carlin y Edron.
- Animación de impacto y desplazamiento en combate, además de un cambio visual de ambiente cuando aparece un enemigo.

## Guardado

- El progreso se guarda automáticamente en `localStorage`.
- Los perfiles pueden guardarse, exportarse e importarse como JSON desde el panel de sesiones.
- GitHub Pages no sincroniza partidas entre dispositivos. Para cuentas y sincronización en la nube se necesita un backend, por ejemplo Supabase o Firebase.

## Datos, versiones y atribución

Las fórmulas de experiencia y los valores de criaturas se contrastaron con la tabla oficial de experiencia y bases comunitarias de criaturas. La lista de hechizos toma referencias de Tibia actual para los niveles solicitados; las recargas del simulador usan grupos simplificados de ataque y curación a 2 segundos; no reproducen todos los exhausts ni modificadores del cliente oficial.

- [Tabla oficial de experiencia de Tibia](https://www.tibia.com/library/?subtopic=experiencetable)
- [TibiaWiki — fórmula de experiencia](https://tibia.fandom.com/wiki/Experience_Formula)
- [TibiaWiki — lista de criaturas](https://tibia.fandom.com/wiki/List_of_Creatures)
- [TibiaWiki — hechizos](https://tibia.fandom.com/wiki/Spells)

Tibia, sus nombres, gráficos, sprites, criaturas y objetos oficiales pertenecen a sus respectivos titulares. Este proyecto no está afiliado, patrocinado ni respaldado por CipSoft GmbH. Los sprites externos pueden cambiar o dejar de estar disponibles; utiliza recursos locales solo si tienes permiso para alojarlos. El mapa de esta versión es un esquema propio, no una copia del mapa oficial.

## Alcance técnico

Es un juego de navegador local, no un cliente Tibia ni un servidor multijugador. Los parámetros de daño, curación, equipo y balance de encuentros siguen siendo una simulación simplificada, aunque la curva de experiencia y los valores de XP indicados se basan en referencias reales.
