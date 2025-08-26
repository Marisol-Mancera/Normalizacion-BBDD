# 📚 Normalización y Modelado de Base de Datos

## 📌 Descripción del ejercicio
A partir de una **tabla de datos sin normalizar** (proporcionada en PDF), se realizó el proceso de **normalización** siguiendo las reglas de las formas normales (1FN, 2FN y 3FN).  

Posteriormente, se construyeron los siguientes entregables:  
1. **Diagrama ER de Chen**  
2. **Diagrama Relacional (patas de gallo)**  
3. **Este precioso README.md**  

El objetivo de esta práctica fue: **mejorar la calidad del modelo de datos**, eliminar redundancias, y garantizar la correcta representación de las entidades y relaciones.

---

## 🛠️ Proceso realizado

### 🔹 Normalización
1. **1FN (Primera Forma Normal):**
   - Se eliminaron los grupos repetitivos.
   - Se definieron atributos atómicos en cada columna.

2. **2FN (Segunda Forma Normal):**
   - Se identificaron claves primarias.
   - Se eliminaron dependencias parciales de la clave.

3. **3FN (Tercera Forma Normal):**
   - Se eliminaron dependencias transitivas.
   - Cada atributo depende únicamente de la clave primaria.

---

## 📐 Diagramas

### 🔹 Diagrama ER (Chen)

```mermaid
erDiagram
    STUDENTS {
        int id_students PK
        string student_name
        string student_lastname
    }
    CLASSROOM {
        int id_classroom PK
        string classroom_description
    }
    COURSES {
        int id_course PK
        string language
    }

    STUDENTS }o--|| CLASSROOM : "assigned_to"
    CLASSROOM ||--o{ COURSES : "offers"
```

---

### 🔹 Diagrama Relacional (Patas de gallo)

```mermaid
erDiagram
    STUDENT {
        int id_student PK
        string name_student
        string lastname_student
        int id_classroom FK
    }

    CLASSROOM {
        int id_classroom PK
        string classroom_description
    }

    COURSE {
        int id_course PK
        string language
        int id_classroom FK
    }

    CLASSROOM ||--o{ STUDENT : "assigned_to"
    CLASSROOM ||--o{ COURSE : "offers"
```

---

## 📊 Esquema final de tablas

- **STUDENT**  
  - id_student (PK)  
  - name_student  
  - lastname_student  
  - id_classroom (FK)  

- **CLASSROOM**  
  - id_classroom (PK)  
  - classroom_description  

- **COURSE**  
  - id_course (PK)  
  - language  
  - id_classroom (FK)  

---

## ✅ Conclusiones
- La normalización permitió **eliminar redundancias** y organizar mejor la información.  
- El modelo facilita la **escalabilidad** para añadir más cursos, estudiantes o aulas.  
- La separación de entidades asegura la **integridad referencial** de los datos.  

---
