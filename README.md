# Torneos de Ajedrez Escolar ♞

App web de un solo archivo (`index.html`) para organizar torneos de ajedrez en un centro educativo: desde una sesión de clase hasta un torneo de recreos de varias semanas o una competición con ELO.

Funciona sin instalar nada y sin internet: las librerías para el PDF van dentro del archivo. Los datos se guardan en el navegador y se pueden exportar e importar como `.json`.

## Qué hace

**Tres niveles con ajustes por defecto**

| Nivel | Pensado para | Por defecto |
|---|---|---|
| ♟ Clase | Una sesión de 50 min | Suizo de 4 rondas, desempates Buchholz y victorias |
| ♞ Recreo | Varias jornadas | Suizo de 6 rondas, se pasa lista cada día, evita enfrentar a compañeros del mismo grupo |
| ♛ Competición | Torneo intercentros o fin de curso | Suizo de 7 rondas, ELO, colores estrictos, Buchholz -2 + Progresivo + Sonneborn-Berger (como el manual de Swiss Perfect) |

**Sistemas:** suizo, liga todos contra todos (tablas de Berger, con opción de ida y vuelta) y eliminatoria (con cuadro y desempate por partida rápida).

**Modalidades:** individual o por equipos (de 2 a 8 tableros, con reservas, puntos de encuentro o de tablero y clasificación por tableros).

**Durante el torneo:** resultados con un clic, incomparecencias (+/-, -/+, -/-), descansos con número impar, ausencias por ronda, retiradas, deshacer la última ronda, añadir rondas y vista a pantalla completa para el proyector.

**Desempates configurables y ordenables:** Buchholz, Buchholz -1, Buchholz -2, Sonneborn-Berger, Progresivo, Victorias, Enfrentamiento directo, Partidas con negras y, en equipos, puntos de tablero o de encuentro.

**Mis grupos:** guarda tus clases una sola vez (se pueden pegar desde Séneca o Excel) y cárgalas en cualquier torneo con un clic.

**Jugar en la app:** cada mesa tiene un botón ♟ que abre un tablero con las reglas completas (enroque, captura al paso, coronación, jaque mate, ahogado, tablas), reloj opcional con incremento y opción de deshacer para iniciación. En el **modo alumnado**, cada alumno pulsa su nombre, confirma mesa y color, y juega; el resultado se apunta solo. Funciona en el dispositivo donde está abierto el torneo (un ordenador o una tableta por mesa compartida).

**Colores:** la app alterna blancas y negras, equilibra el total y nadie juega tres veces seguidas con el mismo color salvo que sea imposible sin repetir rival.

**PDF:** clasificación, cuadro de rondas o tabla cruzada, cuadro de la eliminatoria, resultados de todas las rondas, mejores por tablero, lista de participantes, hoja de emparejamientos para colgar y diplomas del podio.

## Publicarla en GitHub Pages

1. Entra en `github.com/new`. En **Owner** elige tu cuenta y en **Repository name** escribe un nombre corto sin espacios (por ejemplo `torneos-ajedrez`). Marca **Public** y activa **Add README**. Pulsa **Create repository**.
2. Dentro del repositorio pulsa **Add file → Upload files**. Arrastra `index.html` (y este `README.md` si quieres sustituir el que se creó). Pulsa **Commit changes**.
   - El archivo pesa unos 480 KB porque lleva dentro el generador de PDF. Subirlo es más cómodo que copiar y pegar el código.
3. Ve a **Settings → Pages**. En **Branch** elige `main` y la carpeta `/ (root)`. Pulsa **Save**.
4. Al cabo de un minuto, en esa misma página aparece la dirección en un recuadro verde: `https://TU-USUARIO.github.io/torneos-ajedrez/`.

## Notas técnicas

- Emparejamiento suizo de tipo holandés simplificado: grupos de puntuación, mitad superior contra mitad inferior, sin repetir rival, con el descanso para el último que aún no ha descansado y colores equilibrados. Las restricciones se relajan por orden (colores → grupo → repetir rival) solo cuando no hay otra opción. No es un programa homologado por la FIDE: para torneos con ELO oficial, usa el programa que pida la federación.
- El Buchholz no cuenta las partidas no jugadas (descansos e incomparecencias).
- Librerías incluidas: [chess.js](https://github.com/jhlywa/chess.js) 0.10.3 (BSD-2-Clause), [jsPDF](https://github.com/parallax/jsPDF) 2.5.1 y [jsPDF-AutoTable](https://github.com/simonbengtsson/jsPDF-AutoTable) 3.8.2, ambas con licencia MIT.
