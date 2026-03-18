# ⚡ Advanced XExe Builder v 1.0 [MinGW64 Edition]

![Version](https://img.shields.io/badge/Version-1.0_Pro_Edition-green)
![Engine](https://img.shields.io/badge/Engine-MinGW64_%7C_C%2B%2B_Native-blue)
![Platform](https://img.shields.io/badge/Platform-Windows_10/11-lightgrey)

Herramienta profesional diseñada para convertir scripts de automatización (BAT, REG, PS1) en ejecutables nativos de Windows seguros, portables y sin dependencias de .NET Framework.

---

## 📖 Tabla de Contenidos
- [Propósito del Programa](#-propósito-del-programa)
- [Características Principales](#-características-principales)
- [Requisitos del Sistema](#-requisitos-del-sistema)
- [Cómo Funciona (Técnico)](#-cómo-funciona-técnico)
- [Autor y Empresa](#-autor-y-empresa)

---

## 🎯 Propósito del Programa

Esta aplicación sirve como un **compilador de scripts avanzado**. Su objetivo principal es permitir a desarrolladores, administradores de sistemas y entusiastas de la seguridad informática transformar archivos de texto plano (scripts) en ejecutables binarios compilados.

**¿Para qué sirve?**
1.  **Portabilidad:** Convierte scripts en `.exe` independientes que pueden ejecutarse en cualquier Windows sin necesidad de editar el código fuente.
2.  **Seguridad y Privacidad:** Oculta la lógica del script mediante compilación nativa y encriptación, impidiendo que usuarios no autorizados lean o modifiquen el código fácilmente.
3.  **Profesionalismo:** Permite entregar herramientas con iconos personalizados, solicitudes de administrador automáticas y sin ventanas de consola molestas.

---

## ✨ Características Principales

### 1. Compilación Nativa (MinGW64)
A diferencia de otros convertidores que dependen de .NET (C#), esta herramienta utiliza **MinGW64 (G++)** para compilar el código directamente a lenguaje máquina (C++ Nativo).
*   **Ventaja:** Ejecutables más ligeros, arranque rápido y **cero dependencias** externas.

### 2. Soporte Multi-Lenguaje
Interfaz y motor preparados para compilar los tres tipos de scripts más utilizados en la administración de Windows:
*   **Batch (.bat):** Automatización clásica de CMD.
*   **PowerShell (.ps1):** Scripts avanzados de sistema.
*   **Registro (.reg):** Importación silenciosa de claves de registro.

### 3. Panel de Comandos Integrado
Editor inteligente con un panel lateral que filtra y sugiere comandos según el tipo de script seleccionado. Doble clic para insertar, ideal para ahorrar tiempo y evitar errores de sintaxis.

### 4. Seguridad Avanzada
*   **Encriptación XOR:** Cifra el contenido del script dentro del ejecutable. El payload se desencripta solo en memoria al ejecutarse.
*   **Ofuscación Avanzada:** Al activar esta opción, el compilador:
    *   Renombra funciones críticas con nombres aleatorios.
    *   Inserta código basura (*Junk Code*) para confundir analizadores y dificultar la ingeniería inversa.

### 5. Personalización de Ejecución
*   **Modo GUI / Consola:** Elige si tu programa debe mostrar la ventana negra (Consola) o ejecutarse en segundo plano (GUI).
*   **Permisos de Administrador (UAC):** Configura el EXE para que solicite permisos de administrador automáticamente al iniciarse.
*   **Iconos Personalizados:** Incrusta cualquier icono `.ico` en el ejecutable final.

---

## ⚙️ Requisitos del Sistema

*   **Sistema Operativo:** Windows 10 u 11 (64 bits recomendado).
*   **Compilador:** Es necesario tener instalado **MinGW-w64**.
    *   El programa busca automáticamente `g++.exe` en el PATH del sistema o en rutas comunes (`C:\mingw64\bin\`).

---

## 🛠️ Cómo Funciona (Técnico)

El programa actúa como un "Stub Builder" inteligente:

1.  **Captura:** Lee el código fuente del script proporcionado por el usuario.
2.  **Procesamiento:** 
    *   Convierte el script a Base64.
    *   Aplica encriptación XOR y conversión a Hexadecimal si está activado (para evitar errores de sintaxis en C++).
3.  **Generación de Código:** Escribe dinámicamente un archivo `main.cpp` que contiene las funciones de desencriptado y el payload incrustado.
4.  **Compilación:** Invoca al compilador `g++` para transformar el código C++ en un ejecutable final (`exe`), enlazando estáticamente las librerías para evitar dependencias.

---

## 👤 Autor y Empresa

Desarrollado con fines educativos y de seguridad informática.

*   **Creador:** Rhino Team
*   **Desarrollador Principal:** [Pr0fEs0r-X](https://github.com/Pr0fEs0r-X)
*   **Compañía:** Rhino Forensic

---

## ⚠️ Aviso Legal

Esta herramienta es proporcionada "tal cual" con fines educativos y de automatización legítima. El uso de técnicas de ofuscación o encriptación puede ser detectado por antivirus heurísticos como comportamiento sospechoso. El autor no se hace responsable del mal uso que se pueda dar a este software.

```
