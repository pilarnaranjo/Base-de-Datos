
<div align="center">

<img src="https://img.shields.io/badge/EJERCICIO-07-DCC6F0?style=for-the-badge&labelColor=8064A2" />

# 🎧 Discos Musicales

*Diseño de una base de datos para la gestión de discos, géneros musicales, cantantes y canciones.*

</div>

---

**Enunciado:**

● La tienda vende discos de diferentes géneros musicales y cantantes

● Cada género musical tiene un identificador

● Cada disco tiene titulo, genero musical, precio y cantante

● De un cantante se registra el nombre y su país, Todo disco pertenece a un cantante y un cantante puede tener muchos discos. Además un disco tiene un conjunto de canciones(identificador y título)

● Un disco tiene muchas canciones y una canción puede estar en varios discos. Interesa conocer la posición de una canción en un determinado disco

---

### 📐 Modelo Entidad-Relación

<img width="941" height="314" alt="image" src="https://github.com/user-attachments/assets/97ab9ae6-cd5e-4bb0-9b8f-82a96ff8bc7b" />

---

### 🔗 Modelo Relacional

<img width="565" height="261" alt="image" src="https://github.com/user-attachments/assets/a1781ee6-bb5f-4f5e-8e3b-50148053cec5" />

---

### 💻 Código SQL

```SQL
CREATE TABLE Genero_Musical (
    Identificador INT PRIMARY KEY
);

CREATE TABLE Cantante (
    Id_Cantante INT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    pais VARCHAR(50) NOT NULL
);

CREATE TABLE Disco (
    Id_disco INT PRIMARY KEY,
    titulo VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2) NOT NULL,
    Id_genero INT NOT NULL,
    Id_cantante INT NOT NULL,
    FOREIGN KEY (Id_genero) REFERENCES Genero_Musical (Identificador),
    FOREIGN KEY (Id_cantante) REFERENCES Cantante (Id_Cantante)
);

CREATE TABLE Cancion (
    Identificador INT PRIMARY KEY,
    titulo VARCHAR(100) NOT NULL
);

CREATE TABLE Disco_Cancion (
    Id_disco INT NOT NULL,
    Id_cancion INT NOT NULL,
    posicion INT NOT NULL,
    PRIMARY KEY (Id_disco, Id_cancion),
    FOREIGN KEY (Id_disco) REFERENCES Disco (Id_disco),
    FOREIGN KEY (Id_cancion) REFERENCES Cancion (Identificador)
);
```

---

<div align="center">

<img src="https://img.shields.io/badge/BASE_DE_DATOS-MODELADO_Y_GESTIÓN-DCC6F0?style=flat-square&labelColor=8064A2" />

*Portafolio Digital de Aprendizaje*  
**Universidad Nacional de Loja · Carrera de Computación**

</div>
