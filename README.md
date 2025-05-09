# 🔒 Write-up Ético: Exposición de Archivos Públicos CSV en Servidor Universitario de Prueba

**Autor:** [p1r4t3h00k](https://www.youtube.com/@p1r4t3h00k)  
**Fecha del hallazgo:** 08/05/2025  
**Clasificación:** Vulnerabilidad Crítica – Exposición de Datos  
**Tipo de ataque:** Directory Listing / Archivos accesibles sin autenticación

---

## 🧠 Introducción

Durante una exploración casual enfocada a revisar prácticas comunes en servidores web educativos, se identificó una exposición accidental de archivos sensibles en el subdominio de una institución educativa ficticia: `demo.universidad.edu.mx`.

El hallazgo fue inesperado, pero real. Al acceder a una ruta pública (`/mdl/`), el servidor mostraba un listado completo de archivos `.csv` que contenían datos simulados de tipo académico y personal.

Este write-up tiene fines **educativos y éticos**, sin exponer datos reales ni vulnerar ninguna ley. **Todo ha sido reportado de forma responsable** y se ha anonimizado completamente cualquier referencia a instituciones reales.

---

## 🔍 Descripción Técnica

**Ruta accesible sin autenticación:**

https://demo.universidad.edu.mx/mdl/


**Archivos CSV visibles en el directorio (ejemplo):**

    Moodle_20250508_00.csv

    Moodle_SUSPENDED_20250508.csv

    Cursos_20250508_01.csv

    Pottencia_20250508_01.csv


Los nombres de archivo simulaban contener:

- Matrículas de alumnos  
- Nombres completos  
- Correos institucionales  
- Estatus académico  
- Información de cursos

> ❗ El servidor tenía habilitada la opción `autoindex` del servidor web, lo que permitió listar archivos sin autenticación, token o protección.

---

## ⚠️ Riesgos Detectados

| Riesgo | Descripción |
|--------|-------------|
| 📬 Fuga de datos personales | Datos de contacto de alumnos y docentes |
| 🧑‍💻 Ingeniería social | Posible suplantación de identidad |
| 🚨 Violación legal | Ley Federal de Protección de Datos Personales (México) |
| 📘 Exposición académica | Información sobre cursos, calificaciones o estatus |
| 🧱 Reconocimiento | Información útil para atacantes en fases de recolección de datos |

---

## 🛠️ Recomendaciones de mitigación

1. **Desactivar el listado de directorios (`Options -Indexes`) en el servidor web**
2. **Restringir el acceso a rutas sensibles**
3. **Eliminar archivos con datos sensibles de la raíz pública**
4. **Configurar autenticación y roles de acceso**
5. **Auditar accesos anteriores para detectar descargas o scraping**

---

## 🎓 Laboratorio educativo

Para demostrar esta clase de fallos sin poner en riesgo a nadie, puedes montar un entorno local con Apache y archivos CSV falsos.

**Script educativo disponible:**  
👉 Mira el video o revisa el archivo `lab-csv-exposure.sh` en este repositorio para recrear la vulnerabilidad en un entorno aislado y controlado.

---

## 📢 Divulgación responsable

La exposición fue **reportada de forma responsable** el **09/05/2025**.  
Este write-up no busca exponer a ninguna institución, sino **concientizar sobre la importancia de la ciberseguridad**, especialmente en contextos académicos.

---

## 👨‍💻 Reflexión final

Los hallazgos éticos no siempre son intencionados. A veces basta un pequeño vistazo para descubrir configuraciones inseguras con impactos reales. Lo que te define es lo que haces con ese conocimiento.

🔐 La ciberseguridad comienza con la educación.

---

## 📹 Mira el video completo

🎥 En mi canal [p1r4t3h00k](https://www.youtube.com/@p1r4t3h00k) te enseño paso a paso cómo recrear este escenario de forma **ética**, cómo montar tu laboratorio y cómo **cerrar la brecha de seguridad**.
