# 🎮 SoLong

[![42School](https://img.shields.io/badge/42-School-000000?style=flat&logo=42&logoColor=white)](https://42.fr)
[![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=white)](https://en.wikipedia.org/wiki/C_(programming_language))
[![MLX42](https://img.shields.io/badge/MLX42-Graphics-blue?style=flat)](https://github.com/codam-coding-college/MLX42)
[![Made with ❤️](https://img.shields.io/badge/Made%20with-❤️-red.svg)](https://github.com/rdelicado)

> Un juego 2D desarrollado en C utilizando la librería MLX42, donde el jugador debe recolectar todos los objetos y alcanzar la salida en un laberinto.

## 📋 Tabla de Contenidos

- [Descripción](#-descripción)
- [Características](#-características)
- [Instalación](#-instalación)
- [Uso](#-uso)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Formatos de Mapa](#-formatos-de-mapa)
- [Controles](#-controles)
- [Compilación](#-compilación)

## 🎯 Descripción

**SoLong** es un juego 2D estilo arcade desarrollado como parte del curriculum de 42School. El jugador controla un personaje que debe navegar por un laberinto, recolectar todos los objetos coleccionables y alcanzar la salida para completar el nivel.

### Objetivos del Juego:
- 🔍 Navegar por el laberinto utilizando las teclas WASD
- 💎 Recolectar todos los objetos coleccionables (C)
- 🚪 Alcanzar la salida (E) después de recoger todos los objetos
- 📊 Minimizar el número de movimientos

## ✨ Características

### Funcionalidades Principales
- **Renderizado 2D**: Gráficos fluidos utilizando MLX42
- **Sistema de Colisiones**: Detección de paredes y obstáculos
- **Validación de Mapas**: Verificación automática de mapas válidos
- **Contador de Movimientos**: Seguimiento de pasos realizados
- **Flood Fill Algorithm**: Verificación de rutas válidas
- **Gestión de Memoria**: Sin memory leaks

### Validaciones de Mapa
- ✅ Formato rectangular
- ✅ Rodeado completamente por muros (1)
- ✅ Un solo jugador (P) y una salida (E)
- ✅ Al menos un objeto coleccionable (C)
- ✅ Ruta válida a todos los objetos y la salida

## 🚀 Instalación

### Prerrequisitos
```bash
# Linux/WSL
sudo apt-get update
sudo apt-get install build-essential libglfw3-dev

# macOS
brew install glfw
```

### Clonación e Instalación
```bash
# Clonar el repositorio
git clone https://github.com/rdelicado/Solong.git
cd Solong

# Compilar el proyecto
make

# Compilar versión bonus (características adicionales)
make bonus
```

## 🎮 Uso

### Ejecución Básica
```bash
# Ejecutar con un mapa específico
./so_long maps/map_test.ber

# Ejecutar versión bonus
./so_long_bonus maps/map_test_bonus.ber
```

### Ejemplos de Mapas Incluidos
```bash
# Mapa simple para principiantes
./so_long maps/map_mini.ber

# Mapa de dificultad media
./so_long maps/map_mediano.ber

# Mapa laberíntico
./so_long maps/map_lab.ber
```

## 📁 Estructura del Proyecto

```
SoLong/
├── src/                          # Código fuente principal
│   ├── so_long.c                 # Función main y validaciones
│   ├── utils_read_map.c          # Lectura y parseo de mapas
│   ├── utils_check_map.c         # Validación de mapas
│   ├── utils_flood_fill.c        # Algoritmo flood fill
│   ├── utils_main_game.c         # Loop principal del juego
│   ├── utils_img.c               # Gestión de imágenes
│   ├── utils_accion_player.c     # Movimientos del jugador
│   └── utils_struct.c            # Inicialización de estructuras
├── srcb/                         # Código fuente bonus
├── include/
│   ├── so_long.h                 # Headers principales
│   └── so_long_bonus.h           # Headers bonus
├── maps/                         # Mapas de ejemplo
│   ├── map_test.ber              # Mapa básico
│   ├── map_lab.ber               # Mapa laberinto
│   └── map_mediano.ber           # Mapa intermedio
├── img/                          # Sprites y texturas
├── MLX42/                        # Librería gráfica
├── libft/                        # Librería de utilidades C
└── Makefile                      # Sistema de compilación
```

## 🗺️ Formatos de Mapa

### Elementos del Mapa
- `1` - Muro (Wall)
- `0` - Espacio vacío (Floor)
- `P` - Posición inicial del jugador (Player)
- `C` - Objeto coleccionable (Collectible)
- `E` - Salida (Exit)

### Ejemplo de Mapa (.ber)
```
111111111
1000000C1
10C000001
1000P0001
100000001
1C000E001
111111111
```

### Reglas de Validación
1. **Extensión**: Debe terminar en `.ber`
2. **Forma**: Rectangular (todas las filas igual longitud)
3. **Bordes**: Completamente rodeado por muros (1)
4. **Elementos únicos**: Un solo P y un solo E
5. **Coleccionables**: Al menos un C
6. **Accesibilidad**: Todos los elementos alcanzables desde P

## 🎮 Controles

| Tecla | Acción |
|-------|--------|
| `W` / `↑` | Mover arriba |
| `S` / `↓` | Mover abajo |
| `A` / `←` | Mover izquierda |
| `D` / `→` | Mover derecha |
| `ESC` | Salir del juego |

## 🔧 Compilación

### Opciones de Make
```bash
# Compilación estándar
make

# Compilación con bonus
make bonus

# Limpiar objetos
make clean

# Limpiar todo
make fclean

# Recompilar
make re

# Compilar y limpiar objetos
make solong
```

### Flags de Compilación
- `-Wall -Wextra -Werror`: Warnings estrictos
- `-g`: Información de debug
- Linkeo con `libmlx42.a`, `libft.a` y `libglfw`

---

**Desarrollado con 💙 por [rdelicado](https://github.com/rdelicado)**

*Proyecto académico - 42School*