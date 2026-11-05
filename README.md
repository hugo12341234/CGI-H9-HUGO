# Prácticas de Computación Gráfica e Interacción Humano-Computadora

**Hugo Emmanuel Chacon Jaral** · Facultad de Ingeniería, UNAM

Prácticas 0 a 9 de OpenGL moderno (C++ con GLFW, GLEW, GLM, Assimp y SOIL2). **Cada práctica es una rama** y todas usan la misma estructura: una sola solución de Visual Studio en la raíz del repositorio. Al cambiar de rama, la solución pasa a ser la de esa práctica. Todo lo necesario para compilar viene en el repositorio.

## Cómo compilar una práctica

1. Clonar el repositorio:
   ```
   git clone https://github.com/hugo12341234/CGI-H9-HUGO
   ```
2. Elegir la práctica cambiando de rama (con Visual Studio cerrado o aceptando recargar la solución):
   ```
   git switch Practica5_CargaModelos_CamSimetrica
   ```
   Sin cambiar de rama se obtiene la Práctica 9 (rama `master`).
3. Abrir la solución de la raíz: `configCGIH9.sln` (en la Práctica 0 es `Project1.sln`).
4. En la barra superior elegir **Debug** y **x86** (las librerías son de 32 bits).
5. Presionar **F5** (o Ctrl + F5) para compilar y ejecutar.

Para pasar a otra práctica basta repetir el paso 2 y volver a compilar.

**Requisitos:** Windows y Visual Studio con la carga de trabajo *Desarrollo para el escritorio con C++*. No hay que instalar ni configurar nada más.

## Ramas

| Rama | Tema | Código principal |
|---|---|---|
| `Practica0_ConfiguracionOpenGL` | configuración de OpenGL | `Project1/Main.cpp` |
| `Practica1_IntroduccionOpenGL` | introducción a OpenGL (dibujo 2D) | `configCGIH9/Main_Dibujo2D.cpp` |
| `Practica2_Proy_Puert_Trans` | proyecciones, puertos de vista y transformaciones | `configCGIH9/Main_P3.cpp` |
| `Practica3_ModeladoGeometrico` | modelado geométrico | `configCGIH9/Main_Modelado.cpp` |
| `Practica4_ModeladoJerarquico` | modelado jerárquico | `configCGIH9/Modelado_Jerarquico.cpp` |
| `Practica5_CargaModelos_CamSimetrica` | carga de modelos y cámara sintética | `configCGIH9/Carga de Modelos.cpp` |
| `Practica6_Texturizado` | texturizado | `configCGIH9/Texturizado.cpp` |
| `Practica7_Iluminacion1` | iluminación 1 | `configCGIH9/Iluminacion.cpp` |
| `Practica8_Iluminacion2` | iluminación 2 (fuentes de luz) | `configCGIH9/fuentesDeLuz.cpp` |
| `Practica9_AnimacionBasica` | animación básica (máquina de estados) | `configCGIH9/Maquina de estados.cpp` |

La rama `todas-las-practicas` conserva la versión anterior del repositorio, con una carpeta por práctica.

## Estructura de cada rama

```
External Libraries/    GLEW, GLFW, GLM, Assimp y SOIL2
configCGIH9.sln        solución de la práctica (Project1.sln en la Práctica 0)
configCGIH9/           proyecto: código, shaders, modelos, imágenes y DLL
```

Los proyectos encuentran `External Libraries` con `$(SolutionDir)`, como en la configuración de clase.

## Problemas comunes

- **Marca que falta `MSVCP140D.dll`, `VCRUNTIME140D.dll` o `ucrtbased.dll`** (prácticas 5 a 9): `assimp` usa las bibliotecas de depuración de Visual C++. Se instalan con la carga de trabajo *Desarrollo para el escritorio con C++* de Visual Studio.
- **Error al vincular `glew32.lib` o `glfw3.lib`:** revisar que la plataforma sea **x86**, no x64.
- **Pantalla negra o no encuentra shaders y modelos:** ejecutar desde Visual Studio con F5. Los shaders y modelos se buscan en la carpeta del proyecto.

## Librerías de terceros

GLEW, GLFW, GLM, Assimp y SOIL2 se incluyen tal como se usaron en el laboratorio, cada una con su propia licencia.
