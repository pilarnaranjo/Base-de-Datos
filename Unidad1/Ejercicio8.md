
<div align="center">

<img src="https://img.shields.io/badge/EJERCICIO-08-DCC6F0?style=for-the-badge&labelColor=8064A2" />

# 🚚 Camiones

*Diseño de una base de datos para la gestión de camioneros, paquetes, provincias y camiones.*

</div>

---

**Enunciado:** Se desea informatizar la gestión de una empresa de transporte que reparte paquetes por toda España. Los encargados de llevar los paquetes son los camioneros, de los que se quiere guardar la cédula, nombre, teléfono, dirección, salario y población en que vive. De los paquetes transportados interesa conocer el código del paquete, descripción, destinatario y dirección del destinatario.

Un camionero distribuye muchos paquetes, y un paquete sólo puede ser distribuido por un camionero. De las provincias a las que llegan los paquetes interesa guardar el código de provincia y el nombre. Un paquete sólo puede llegar a una provincia. Sin embargo, a una provincia pueden llegar varios paquetes.

De los camiones que llevan los camioneros, interesa conocer la matrícula, modelo, tipo y potencia. Un camionero puede conducir diferentes camiones en fechas diferentes, y un camión puede ser conducido por varios camioneros.

---

### 📐 Modelo Entidad-Relación

<img width="1041" height="378" alt="image" src="https://github.com/user-attachments/assets/679a2f3d-a976-4771-a85a-e5464e3db368" />

---

### 🔗 Modelo Relacional

<img width="750" height="246" alt="image" src="https://github.com/user-attachments/assets/5a2cc5c0-b179-4c09-945f-9467856ee182" />

---

### 💻 Código SQL

```SQL

CREATE TABLE Camionero (
    Cedula VARCHAR(10) PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    telefono VARCHAR(15),
    direccion VARCHAR(100),
    salario DECIMAL(10,2),
    poblacion VARCHAR(50)
);

CREATE TABLE Camion (
    Matricula VARCHAR(10) PRIMARY KEY,
    modelo VARCHAR(50),
    tipo VARCHAR(50),
    potencia INT
);

CREATE TABLE Provincia (
    Id_provincia INT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL
);

CREATE TABLE Paquete (
    Codigo INT PRIMARY KEY,
    descripcion VARCHAR(100),
    destinatario VARCHAR(100) NOT NULL,
    direccion VARCHAR(100) NOT NULL,
    cedula_camionero VARCHAR(10) NOT NULL,
    id_provincia INT NOT NULL,
    FOREIGN KEY (cedula_camionero) REFERENCES Camionero (Cedula),
    FOREIGN KEY (id_provincia) REFERENCES Provincia (Id_provincia)
);

CREATE TABLE Camionero_Camion (
    Cedula_Camionero VARCHAR(10) NOT NULL,
    Matricula VARCHAR(10) NOT NULL,
    fecha DATE NOT NULL,
    PRIMARY KEY (Cedula_Camionero, Matricula, fecha),
    FOREIGN KEY (Cedula_Camionero) REFERENCES Camionero (Cedula),
    FOREIGN KEY (Matricula) REFERENCES Camion (Matricula)
);
```
---

<div align="center">

<img src="https://img.shields.io/badge/BASE_DE_DATOS-MODELADO_Y_GESTIÓN-DCC6F0?style=flat-square&labelColor=8064A2" />

*Portafolio Digital de Aprendizaje*  
**Universidad Nacional de Loja · Carrera de Computación**

</div>
