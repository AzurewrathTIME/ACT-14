# 🎓 Sistema de Gestión Académica

Aplicación de consola desarrollada en **C++** para administrar información básica de alumnos, maestros, administradores, materias y calificaciones.

El proyecto está diseñado para practicar conceptos fundamentales de **Programación Orientada a Objetos (POO)**, como herencia, encapsulamiento, polimorfismo, sobrecarga de operadores, constructores y manejo de arreglos de objetos.

## 📌 Descripción

El sistema permite gestionar diferentes tipos de personas dentro de una institución educativa:

- 👨‍🎓 **Alumnos**
- 👨‍🏫 **Maestros**
- 👨‍💼 **Administradores**
- 📚 **Materias**
- 📝 **Calificaciones**

Toda la interacción se realiza mediante un **menú de consola**, donde el usuario puede registrar, consultar, modificar, eliminar y comparar información.

## ✨ Características

### 👨‍🎓 Gestión de alumnos

El sistema permite:

- Registrar alumnos.
- Mostrar un alumno específico.
- Mostrar todos los alumnos.
- Buscar alumnos por nombre.
- Modificar información de un alumno.
- Eliminar alumnos.
- Calcular el promedio de edades de los alumnos.

Cada alumno cuenta con:

| Dato | Descripción |
|---|---|
| Nombre | Nombre del alumno |
| Edad | Edad del alumno |
| Matrícula | Identificador del alumno |
| Materias | Materias inscritas |
| Calificaciones | Notas obtenidas |

### 📚 Gestión de materias

Cada alumno puede tener hasta **10 materias**.

Para cada materia se almacena:

- Nombre de la materia.
- Clave de la materia.

### 📝 Gestión de calificaciones

El sistema permite registrar calificaciones asociadas a las materias de cada alumno.

Las calificaciones deben estar dentro del rango:

0 - 10


Antes de registrar una calificación, el programa verifica que la materia correspondiente exista.

### 📖 Historial académico

Es posible consultar el historial académico de un alumno.

El sistema muestra:

Materia Clave Nota


### 👨‍🏫 Maestros

Los maestros heredan las características básicas de `Persona`.

Además, cuentan con:

- Nombre
- Edad
- Especialidad

### 👨‍💼 Administradores

Los administradores heredan de `Persona`.

Además, cuentan con:

- Nombre
- Edad
- Departamento

## 🧠 Conceptos de Programación Orientada a Objetos

### 🔒 Encapsulamiento

Los atributos de las clases se encuentran definidos como `private` o `protected` y se accede a ellos mediante métodos `set` y `get`.

Ejemplo:

class Materia { private: string nombre; string clave;

public: void setNombre(string n) { nombre = n; }

string getNombre() { return nombre; } };


### 🧬 Herencia

`Alumno`, `Maestro` y `Administrador` heredan de la clase base `Persona`.

Persona │ ┌────────────┼────────────┐ │ │ │ Alumno Maestro Administrador


### 🔄 Polimorfismo

La clase `Persona` utiliza métodos virtuales:

virtual void mostrarInformacion(); virtual bool operator==(const Persona& otra) const; virtual ~Persona();


Esto permite que las clases derivadas proporcionen su propia implementación.

### ⚖️ Sobrecarga del operador `==`

El programa permite comparar objetos utilizando:

==


Cada clase utiliza un criterio diferente.

### 🖨️ Sobrecarga del operador `<<`

También se sobrecarga el operador `<<` para poder imprimir directamente los objetos.

Ejemplo:

cout << alumnos[i];


## 🏗️ Estructura de clases

El proyecto está compuesto por las siguientes clases:

### `Materia`

Representa una materia académica.

**Atributos:**

string nombre; string clave;


**Funciones principales:**

- `setNombre()`
- `getNombre()`
- `setClave()`
- `getClave()`
- `mostrar()`

### `Calificacion`

Representa una calificación asociada a una materia.

**Atributos:**

string claveMateria; float nota;


**Funciones principales:**

- `setClaveMateria()`
- `getClaveMateria()`
- `setNota()`
- `getNota()`
- `mostrar()`

### `Persona`

Clase base para representar a una persona.

**Atributos:**

string nombre; int edad;


**Funciones principales:**

- `setNombre()`
- `getNombre()`
- `setEdad()`
- `getEdad()`
- `mostrarInformacion()`
- `operator==`
- `operator<<`

### `Alumno`

Hereda de `Persona`.

**Atributos adicionales:**

string matricula; Materia materias[10]; Calificacion calificaciones[10]; int numMaterias; int numCalificaciones;


Permite administrar las materias y calificaciones de cada alumno.

### `Maestro`

Hereda de `Persona`.

**Atributo adicional:**

string especialidad;


### `Administrador`

Hereda de `Persona`.

**Atributo adicional:**

string departamento;


## 🗂️ Funciones principales

Función	Descripción
registrarAlumno()	Registra un nuevo alumno
mostrarAlumno()	Muestra un alumno específico
mostrarTodos()	Muestra todos los alumnos
buscarAlumno()	Busca un alumno por nombre
eliminarAlumno()	Elimina un alumno
modificarAlumno()	Modifica los datos de un alumno
agregarMateria()	Agrega una materia a un alumno
registrarCalificacion()	Registra una calificación
mostrarHistorial()	Muestra el historial académico
registrarMaestro()	Registra un maestro
registrarAdministrador()	Registra un administrador
mostrarPersonas()	Muestra maestros y administradores
compararPersonas()	Compara dos personas
calcularPromedio()	Calcula el promedio de edades
🎮 Menú del programa

Al ejecutar el programa se muestra el siguiente menú:

===== MENU =====
1. Registrar Alumno.
2. Mostrar un Alumno.
3. Mostrar Todos los Alumnos.
4. Calcular Promedio.
5. Buscar Alumno por nombre.
6. Eliminar Alumno.
7. Modificar Alumno.
8. Agregar Materia.
9. Registrar Calificacion.
10. Mostrar Historial Academico.
11. Registrar Maestro.
12. Registrar Administrador.
13. Mostrar Maestros y Administradores.
14. Comparar Personas.
15. Salir.

💾 Límites del sistema
Elemento	Capacidad
Alumnos	10
Materias por alumno	10
Calificaciones por alumno	10
Maestros y administradores	100

Estos límites están definidos principalmente mediante:

const int MAX = 10;

y:

Persona* personas[100];

⚙️ Requisitos

Para compilar y ejecutar el proyecto necesitas:

    💻 Un compilador compatible con C++
    🛠️ GCC, MinGW, Clang o Visual Studio
    🖥️ Terminal o consola

No utiliza librerías externas.

La biblioteca principal utilizada es:

#include <iostream>
#include <string>

🚀 Compilación

Guarda el código como:

main.cpp

Después ejecuta:

g++ main.cpp -o sistema

Windows

sistema.exe

Linux / macOS

./sistema

📚 Objetivo académico

El objetivo principal del proyecto es poner en práctica los fundamentos de Programación Orientada a Objetos en C++, especialmente:

    Encapsulamiento
    Herencia
    Polimorfismo
    Constructores
    Destructores
    Sobrecarga de operadores
    Clases y objetos
    Arreglos de objetos
    Punteros
    Memoria dinámica
    Métodos set y get

📄 Licencia

Este proyecto fue desarrollado con fines educativos y académicos.

Puedes modificarlo, estudiarlo y utilizarlo como base para continuar aprendiendo C++ y Programación Orientada a Objetos.

<div align="center">
🎓 Sistema de Gestión Académica

Desarrollado en C++ | Programación Orientada a Objetos

⭐ Si este proyecto te ayudó, ¡no olvides darle una estrella!

</div>


### 🔴 Y MUY IMPORTANTE

En tu captura veo esto:

README14.md


Eso **no es el problema principal**, pero si quieres que GitHub lo detecte automáticamente, renómbralo:

README.md


Y en VS Code abre el preview con:

**`Ctrl + Shift + V`**

o:

**`Ctrl + K` → `V`**

---
