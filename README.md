# CGI-H9-HUGO: OpenGL lab practices

Lab practices for **Computer Graphics and Human-Computer Interaction** (Facultad de Ingeniería, UNAM), written in C++ with modern OpenGL 3.3 core profile.

Every practice lives in its own folder and is a **self-contained Visual Studio project**: source code, shaders, 3D models and textures are all included, so each one builds and runs on its own after a `git clone`. No library binaries are committed; GLFW, GLEW, GLM and Assimp are restored automatically with [vcpkg](https://vcpkg.io).

## Practices

| # | Topic | Folder | Entry point |
|---|-------|--------|-------------|
| 0 | OpenGL setup: window and hard-coded shaders | `Practica00_ConfiguracionOpenGL` | `Main.cpp` |
| 1 | Introduction to OpenGL: 2D drawing, vertices and indices | `Practica01_IntroduccionOpenGL` | `Main_Dibujo2D.cpp` |
| 2 | Projections, viewports and geometric transformations | `Practica02_ProyeccionesTransformaciones` | `Main_P3.cpp` |
| 3 | Geometric modeling | `Practica03_ModeladoGeometrico` | `Main_Modelado.cpp` |
| 4 | Hierarchical modeling | `Practica04_ModeladoJerarquico` | `Modelado_Jerarquico.cpp` |
| 5 | Model loading (Assimp) and synthetic camera | `Practica05_CargaModelos_CamaraSintetica` | `Carga de Modelos.cpp` |
| 6 | Texturing | `Practica06_Texturizado` | `Texturizado.cpp` |
| 7 | Lighting 1 | `Practica07_Iluminacion1` | `Iluminacion.cpp` |
| 8 | Lighting 2: light sources | `Practica08_Iluminacion2` | `fuentesDeLuz.cpp` |
| 9 | Basic animation: state machine with a dog model | `Practica09_AnimacionBasica` | `Maquina de estados.cpp` |

Each folder contains its `.sln`/`.vcxproj`, the entry point above, `Shader/` (GLSL), and, when needed, `Models/`, `images/` and `SOIL2/` (image loading helper compiled with the project).

## Requirements

- Windows 10/11 with a GPU and driver that support **OpenGL 3.3**
- **Visual Studio 2022 or newer** with the *Desktop development with C++* workload (it includes vcpkg and Git)
- Internet connection for the first build

## Run a practice

1. One-time setup: open **Developer PowerShell for VS** and run
   ```powershell
   vcpkg integrate install
   ```
2. Clone the repository:
   ```powershell
   git clone https://github.com/hugo12341234/CGI-H9-HUGO.git
   ```
3. Open the `.sln` inside the practice folder you want, for example `Practica07_Iluminacion1/Practica07.sln`.
4. Choose `Debug` and `x64` (x86 also works) and press **F5**.

The first build downloads and compiles GLFW, GLEW, GLM and Assimp into `vcpkg_installed/` at the repository root. That takes several minutes (Assimp is the slow one), happens only once, and is shared by all practices. DLLs are copied next to the executable automatically.

## Troubleshooting

- **`Cannot open include file: 'GL/glew.h'`**: vcpkg integration is missing. Run `vcpkg integrate install`, then reload the solution.
- **Black window or shader/model not found**: start the program from Visual Studio (F5) or with the practice folder as the working directory, because shaders, models and images are loaded with relative paths (`Shader/...`, `Models/...`, `images/...`).
- **Window does not open**: update the graphics driver; the practices request an OpenGL 3.3 core context.

## Notes

- Projects define `GLM_FORCE_CTOR_INIT` so GLM vectors and matrices are zero/identity-initialized, as in the older GLM version used by the course.
- Base code (`Shader.h`, `Camera.h`, `Mesh.h`, `Model.h`, SOIL2 and `stb_image`) comes from the course material; the practice solutions are in each entry-point file.
- Practices 0 to 9 are included; the keyframe animation practice is not part of the repository yet.
