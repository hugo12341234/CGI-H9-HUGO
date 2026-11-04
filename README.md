# Prácticas de Computación Gráfica e Interacción Humano-Computadora

**Hugo Emmanuel Chacon Jaral** · Facultad de Ingeniería, UNAM

Prácticas 0 a 9 de OpenGL moderno (C++ con GLFW, GLEW y GLM). Cada práctica es un proyecto de Visual Studio independiente y todo lo necesario para compilarla viene en este repositorio.

## Cómo compilar una práctica

1. Clonar el repositorio:
   ```
   git clone https://github.com/hugo12341234/CGI-H9-HUGO
   ```
2. Abrir el archivo `.sln` que está dentro de la carpeta de la práctica.
3. En la barra superior elegir **Debug** y **x86** (es la única plataforma disponible; las librerías son de 32 bits).
4. Presionar **F5** (o Ctrl + F5) para compilar y ejecutar.

**Requisitos:** Windows y Visual Studio 2022 o 2026 con la carga de trabajo *Desarrollo para el escritorio con C++*. No hay que instalar ni configurar nada más.

## Prácticas

| Carpeta | Tema | Código principal |
|---|---|---|
| `Practica0_ConfiguracionOpenGL` | Configuración de OpenGL | `Project1/Main.cpp` |
| `Practica1_IntroduccionOpenGL` | Introducción a OpenGL (dibujo 2D) | `configCGIH9/Main_Dibujo2D.cpp` |
| `Practica2_Proy_Puert_Trans` | Proyecciones y transformaciones básicas | `configCGIH9/Main_P3.cpp` |
| `Practica3_ModeladoGeometrico` | Modelado geométrico | `configCGIH9/Main_Modelado.cpp` |
| `Practica4_ModeladoJerarquico` | Modelado jerárquico | `configCGIH9/Modelado_Jerarquico.cpp` |
| `Practica5_CargaModelos_CamSimetrica` | Carga de modelos y cámara | `configCGIH9/Carga de Modelos.cpp` |
| `Practica6_Texturizado` | Texturizado | `configCGIH9/Texturizado.cpp` |
| `Practica7_Iluminacion1` | Materiales e iluminación | `configCGIH9/Iluminacion.cpp` |
| `Practica8_Iluminacion2` | Fuentes de luz | `configCGIH9/fuentesDeLuz.cpp` |
| `Practica9_AnimacionBasica` | Animación básica (máquina de estados) | `configCGIH9/Maquina de estados.cpp` |

El archivo de solución de la Práctica 0 es `Project1.sln`; en las prácticas 1 a 9 es `configCGIH9.sln`.

## Estructura

```
External Libraries/        GLEW, GLFW, GLM, Assimp y SOIL2, compartidas por todas las prácticas
PracticaN_.../             .sln, código, shaders, modelos e imágenes de la práctica
```

Los proyectos encuentran `External Libraries` con una ruta relativa, por lo que el repositorio puede clonarse en cualquier carpeta.

## Problemas comunes

- **Marca que falta `MSVCP140D.dll`, `VCRUNTIME140D.dll` o `ucrtbased.dll`** (prácticas 5 a 9): `assimp` usa las bibliotecas de depuración de Visual C++. Se instalan con la carga de trabajo *Desarrollo para el escritorio con C++* de Visual Studio.
- **Error al vincular `glew32.lib` o `glfw3.lib`:** revisar que la plataforma sea **x86**, no x64.
- **Pantalla negra o no encuentra shaders y modelos:** ejecutar desde Visual Studio con F5. Los shaders y modelos se buscan en la carpeta del proyecto.

## Librerías de terceros

GLEW, GLFW, GLM, Assimp y SOIL2 se incluyen tal como se usaron en el laboratorio, cada una con su propia licencia.
