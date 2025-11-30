# 🚢 Hundir la Flota (Battleship)

Un juego clásico de batalla naval desarrollado en Java con interfaz gráfica Swing.  Juego para dos jugadores en el mismo dispositivo, con disparos especiales y sistema de estadísticas.

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Swing](https://img.shields.io/badge/Swing-GUI-blue?style=for-the-badge)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)

---

## 📋 Tabla de Contenidos

- [Descripción](#-descripción)
- [Características](#-características)
- [Requisitos](#-requisitos)
- [Instalación](#-instalación)
- [Cómo Jugar](#-cómo-jugar)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Funcionalidades Detalladas](#-funcionalidades-detalladas)
- [Capturas de Pantalla](#-capturas-de-pantalla)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)
- [Autores](#-autores)

---

## 📖 Descripción

**Hundir la Flota** es una implementación digital del clásico juego de mesa de batalla naval. Dos jugadores compiten por hundir la flota enemiga disparando a un tablero de 10x10 casillas. El primer jugador en hundir todos los barcos del oponente gana la partida.

Esta versión incluye características adicionales como **disparos especiales** (Super Disparo y Mega Disparo), un **sistema de estadísticas** persistente con base de datos SQLite, y una interfaz gráfica intuitiva. 

---

## ✨ Características

### 🎮 Jugabilidad
- **Modo 2 jugadores** en el mismo dispositivo
- **Tablero 10x10** casillas por jugador
- **Configuración personalizable** de barcos y disparos especiales
- **Pantallas de transición** para evitar que un jugador vea el tablero del otro

### 🚀 Disparos Especiales
- **Super Disparo**: Dispara en forma de cruz (5 casillas)
- **Mega Disparo**: Dispara en un área de 3x3 (9 casillas)
- Cantidad configurable antes de iniciar la partida

### 🛳️ Barcos Disponibles
| Barco | Tamaño | Cantidad Máxima |
|-------|--------|-----------------|
| Portaaviones | 5 casillas | 1 |
| Acorazado | 4 casillas | 2 |
| Crucero | 3 casillas | 3 |
| Destructor | 2 casillas | 4 |

### 📊 Sistema de Estadísticas
- Historial de partidas guardado en base de datos SQLite
- Registro de victorias y derrotas
- Contador de turnos por partida
- Visualización de estadísticas históricas

### 🎨 Interfaz Gráfica
- Menú principal intuitivo
- Tableros visuales con códigos de color
- Indicadores de aciertos, fallos y barcos hundidos
- Vista del tablero propio durante la partida

---

## 💻 Requisitos

- **Java JDK 8** o superior
- **SQLite JDBC Driver** (incluido en el proyecto)
- Sistema operativo: Windows, macOS o Linux

---

## 🔧 Instalación

### Opción 1: Clonar el repositorio

```bash
git clone https://github.com/Puerco55/Proyecto-Battleship-git.git
cd Proyecto-Battleship-git
```

### Opción 2: Descargar ZIP

1. Descarga el proyecto desde GitHub
2. Extrae el archivo ZIP
3. Abre el proyecto en tu IDE favorito (Eclipse, IntelliJ IDEA, NetBeans)

### Compilar y Ejecutar

```bash
# Compilar
javac -d bin src/battleship/*. java

# Ejecutar
java -cp bin battleship.MainMenu
```

O simplemente ejecuta la clase `MainMenu. java` desde tu IDE.

---

## 🎯 Cómo Jugar

### 1. Inicio del Juego
1. Ejecuta el juego desde el menú principal
2. Haz clic en **"Jugar"**

### 2.  Configuración de la Partida
1. Selecciona la cantidad de cada tipo de barco
2. Configura los disparos especiales disponibles
3.  Haz clic en **"Comenzar Partida"**

### 3.  Colocación de Barcos (Cada Jugador)
1. Selecciona un tipo de barco
2. Elige la orientación (Horizontal/Vertical)
3. Haz clic en el tablero para colocar el barco
4. Repite hasta colocar todos los barcos
5. Haz clic en **"GUARDAR Y CONTINUAR"**

### 4.  Batalla
1. **Tablero grande (izquierda)**: Tablero del oponente - ¡Dispara aquí!
2.  **Tablero pequeño (derecha)**: Tu tablero - Muestra tus barcos y los impactos recibidos

#### Códigos de Color
| Color | Significado |
|-------|-------------|
| 🔵 Azul | Agua (sin disparar) |
| ⚪ Blanco | Agua (disparo fallado) |
| 🔴 Rojo | Barco impactado |
| ⚫ Gris | Tu barco (sin impactar) |

#### Disparos Especiales
- **Super Disparo**: Haz clic en el botón, luego selecciona el centro.  Dispara en cruz (+)
- **Mega Disparo**: Haz clic en el botón, luego selecciona el centro. Dispara en área 3x3

### 5. Cambio de Turno
1. Después de disparar, haz clic en **"Pasar Turno"**
2.  Pasa el dispositivo al otro jugador
3.  El otro jugador pulsa OK para ver su tablero

### 6. Victoria
- Gana el primer jugador que hunda todos los barcos del oponente
- Las estadísticas se guardan automáticamente

---

## 📁 Estructura del Proyecto

```
Proyecto-Battleship-git/
├── src/
│   └── battleship/
│       ├── MainMenu.java           # Menú principal del juego
│       ├── AjustesPartida.java     # Configuración de la partida
│       ├── ColocarBarcos.java      # Pantalla de colocación de barcos
│       ├── PantallaInicioJuego.java # Pantalla de transición antes de jugar
│       ├── VentanaJuego.java       # Ventana principal del juego
│       ├── MenuOpciones.java       # Menú de opciones
│       ├── MenuEstadisticas.java   # Visualización de estadísticas
│       ├── EstadisticasDAO.java    # Acceso a datos de estadísticas
│       └── GestorBaseDatos.java    # Gestión de la base de datos SQLite
├── battleship_db.sqlite            # Base de datos (se crea automáticamente)
└── README.md                       # Este archivo
```

---

## 🔍 Funcionalidades Detalladas

### MainMenu.java
- Punto de entrada de la aplicación
- Navegación a las diferentes secciones del juego
- Inicialización de la base de datos

### AjustesPartida.java
- Configuración del número de barcos de cada tipo
- Configuración de disparos especiales
- Validación de configuración (máximo 50 casillas ocupadas)

### ColocarBarcos. java
- Tablero interactivo 10x10 para colocar barcos
- Selección de orientación (horizontal/vertical)
- Validación de posiciones (no solapamiento, dentro del tablero)
- Botón para reiniciar el tablero

### VentanaJuego.java
- **Tablero de ataque**: Para disparar al oponente
- **Tablero propio**: Visualización de tus barcos e impactos recibidos
- **Panel de estadísticas**: Aciertos, fallos, barcos hundidos
- **Disparos especiales**: Super Disparo (cruz) y Mega Disparo (3x3)
- **Sistema de turnos**: Alternancia entre jugadores con pantalla de transición
- **Detección de victoria**: Cuando todos los barcos del oponente son hundidos
- **Guardado automático**: Estadísticas guardadas al finalizar

### GestorBaseDatos.java
- Conexión a base de datos SQLite
- Creación automática de tablas
- Gestión de conexiones

### EstadisticasDAO.java
- Guardado de resultados de partidas
- Consulta de estadísticas históricas
- Conteo de victorias y derrotas

---

## 🖼️ Capturas de Pantalla

### Menú Principal
```
┌─────────────────────────────┐
│      Hundir la Flota        │
│                             │
│        [ Jugar ]            │
│       [ Opciones ]          │
│     [ Estadísticas ]        │
│        [ Salir ]            │
└─────────────────────────────┘
```

### Pantalla de Juego
```
┌──────────────────────────────────────────────────┐
│ Aciertos: 3    Fallos: 5    Barcos hundidos: 1   │
├────────────────────────┬─────────────────────────┤
│                        │ Tu tablero:             │
│   TABLERO DEL          │ ┌─────────────┐         │
│   OPONENTE             │ │ ▓▓▓ ░░░ ▓▓  │         │
│                        │ │ ░░░ ▓▓▓ ░░  │         │
│   (Dispara aquí)       │ └─────────────┘         │
│                        │                         │
│   ┌─────────────┐      │ DISPAROS:               │
│   │ X ░ ░ • ░   │      │ [Super Disparo (2)]     │
│   │ ░ ░ X X ░   │      │ [Mega Disparo (1)]      │
│   │ • ░ ░ ░ ░   │      │                         │
│   └─────────────┘      │ [   Pasar Turno   ]     │
└────────────────────────┴─────────────────────────┘
```

---

## 🛠️ Tecnologías Utilizadas

| Tecnología | Uso |
|------------|-----|
| **Java SE** | Lenguaje de programación principal |
| **Swing** | Interfaz gráfica de usuario (GUI) |
| **AWT** | Componentes gráficos adicionales |
| **SQLite** | Base de datos para estadísticas |
| **JDBC** | Conexión con la base de datos |

---

## 🎮 Controles

| Acción | Control |
|--------|---------|
| Colocar barco | Clic izquierdo en el tablero |
| Disparar | Clic izquierdo en casilla del oponente |
| Activar Super Disparo | Clic en botón + Clic en tablero |
| Activar Mega Disparo | Clic en botón + Clic en tablero |
| Pasar turno | Clic en "Pasar Turno" |

---

## 🐛 Solución de Problemas

### El juego no inicia
- Verifica que tienes Java 8 o superior instalado
- Ejecuta `java -version` en la terminal para confirmar

### Error de base de datos
- El archivo `battleship_db.sqlite` se crea automáticamente
- Asegúrate de tener permisos de escritura en el directorio

### Los barcos no se colocan
- Verifica que has seleccionado un barco
- Verifica que has seleccionado una orientación
- Asegúrate de que el barco cabe en la posición seleccionada

---

## 🚀 Mejoras Futuras

- [ ] Modo un jugador contra IA
- [ ] Diferentes niveles de dificultad
- [ ] Efectos de sonido
- [ ] Animaciones de explosiones
- [ ] Modo en red (multijugador online)
- [ ] Personalización de temas visuales
- [ ] Tabla de puntuaciones global

---

## 👥 Autores

Desarrollado como proyecto académico. 

**Repositorio**: [https://github.com/Puerco55/Proyecto-Battleship-git](https://github. com/Puerco55/Proyecto-Battleship-git)

---

## 📄 Licencia

Este proyecto es de uso académico y educativo. 

---

## 🙏 Agradecimientos

- Inspirado en el clásico juego de mesa "Battleship" de Milton Bradley
- Gracias a todos los que han contribuido al proyecto

---

<p align="center">
  <b>¡Buena suerte y que gane el mejor capitán!  🏆</b>
</p>
