
<div align="center">

<img src="https://img.shields.io/badge/EJERCICIO-01-DCC6F0?style=for-the-badge&labelColor=8064A2" />

# 📚 Sistema de Biblioteca

*Diseño de una base de datos para la gestión de libros, autores, socios y préstamos.*

</div>

---

**Enunciado:** Una biblioteca registra libros y autores. Un libro puede tener varios autores y un autor varios libros. Los socios toman libros prestados; de cada préstamo interesan la fecha de retiro y la de devolución.

---

### 📐 Modelo Entidad-Relación

<img width="592" height="242" alt="image" src="https://github.com/user-attachments/assets/c058a0d9-6266-4d13-964b-5d2ba60c0a6b" />


---

### 🔗 Modelo Relacional

<img width="761" alt="Modelo Relacional" src="https://github.com/user-attachments/assets/e598276f-4b36-47b3-8f3f-fde364923297" />

---

### 💻 Código SQL
```SQL
CREATE TABLE Libro (
    Id_Libro INT PRIMARY KEY
);

CREATE TABLE Autor (
    Id_Autor INT PRIMARY KEY
);

CREATE TABLE Libro_Autor (
    Id_Libro INT NOT NULL,
    Id_Autor INT NOT NULL,
    PRIMARY KEY (Id_Libro, Id_Autor),
    FOREIGN KEY (Id_Libro) REFERENCES Libro (Id_Libro),
    FOREIGN KEY (Id_Autor) REFERENCES Autor (Id_Autor)
);

CREATE TABLE Socio (
    Id_Socio INT PRIMARY KEY
);

CREATE TABLE Prestamo (
    Id_Socio INT NOT NULL,
    Id_Libro INT NOT NULL,
    Fecha_Retiro DATE NOT NULL,
    Fecha_Devolucion DATE,
    Primary Key (id_libro, id_socio),
    FOREIGN KEY (Id_Socio) REFERENCES Socio (Id_Socio),
    FOREIGN KEY (Id_Libro) REFERENCES Libro (Id_Libro)
);
```
---

<div align="center">

<img src="https://img.shields.io/badge/BASE_DE_DATOS-MODELADO_Y_GESTIÓN-DCC6F0?style=flat-square&labelColor=8064A2" />

*Portafolio Digital de Aprendizaje*  
**Universidad Nacional de Loja · Carrera de Computación**

</div>

