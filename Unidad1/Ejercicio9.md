
<div align="center">

<img src="https://img.shields.io/badge/EJERCICIO-09-DCC6F0?style=for-the-badge&labelColor=8064A2" />

# 🐾 Veterinaria

*Diseño de una base de datos para la gestión de propietarios, mascotas, personal y consultas veterinarias.*

</div>

---

**Enunciado:**

● Del propietario interesa: cédula, apellidos, nombres, dirección , teléfonos

● De la mascota interesa: identificador, nombre, fecha de nacimiento, tipo

● Un propietario puede llevar una o varias mascotas

● Una mascota la lleva uno y solo un propietario

● Del personal de la clínica veterinaria interesa un código, el cédula, nombre

● Entre el personal de la clínica se distingue a los veterinarios y los auxiliares, pudiendo haber otros tipos

  ○ Del veterinario se guarda además su fecha_alta y especialidad

  ○ De los auxiliares interesa su base de cotización

● Las mascotas pasan consulta con los veterinarios. De manera que:

  ○ un veterinario puede pasar consulta a ninguna o a varias mascotas, y

  ○ una misma mascota de la clínica ha pasado consulta una o más veces en fechas diferentes con varios veterinarios.

  ○ Al pasar consulta se realiza un diagnóstico.

● Cada propietario tiene un familiar de contacto para casos de emergencia.

  ○ De este familiar interesa la cédula, nombre y teléfono.

  ○ Si el propietario se da de alta en la clínica veterinaria, el familiar ya no interesa.

  ○ El familiar es contacto de un solo propietario

---

### 📐 Modelo Entidad-Relación

<img width="940" height="291" alt="image" src="https://github.com/user-attachments/assets/04bdb3c1-8d04-4972-a497-77d3de6ff2bb" />

---

### 🔗 Modelo Relacional

<img width="796" height="429" alt="image" src="https://github.com/user-attachments/assets/7f5ee15d-2656-44af-a2ca-e8434864d942" />

---

### 💻 Código SQL

```SQL
CREATE TABLE Propietario (
    Cedula VARCHAR(10) PRIMARY KEY,
    apellidos VARCHAR(50) NOT NULL,
    nombres VARCHAR(50) NOT NULL,
    direccion VARCHAR(100)
);

CREATE TABLE Propietario_Telefono (
    Cedula VARCHAR(10) NOT NULL,
    telefono VARCHAR(15) NOT NULL,
    PRIMARY KEY (Cedula, telefono),
    FOREIGN KEY (Cedula) REFERENCES Propietario (Cedula)
);

CREATE TABLE Mascota (
    Id_mascota INT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    fecha_nacimiento DATE,
    tipo VARCHAR(30),
    Cedula_propietario VARCHAR(10) NOT NULL,
    FOREIGN KEY (Cedula_propietario) REFERENCES Propietario (Cedula)
);

CREATE TABLE Familiar_Contacto (
    Cedula_propietario VARCHAR(10) NOT NULL,
    Cedula_Familiar VARCHAR(10) NOT NULL,
    nombre VARCHAR(50) NOT NULL,
    telefono VARCHAR(15),
    PRIMARY KEY (Cedula_propietario, Cedula_Familiar),
    FOREIGN KEY (Cedula_propietario) REFERENCES Propietario (Cedula)
);

CREATE TABLE Personal_Clinica (
    Codigo INT PRIMARY KEY,
    Cedula_Personal VARCHAR(10) NOT NULL UNIQUE,
    nombre VARCHAR(50) NOT NULL
);

CREATE TABLE Veterinario (
    Codigo INT PRIMARY KEY,
    especialidad VARCHAR(50),
    fecha_alta DATE,
    FOREIGN KEY (Codigo) REFERENCES Personal_Clinica (Codigo)
);

CREATE TABLE Auxiliar (
    Codigo INT PRIMARY KEY,
    base_cotizacion DECIMAL(10,2),
    FOREIGN KEY (Codigo) REFERENCES Personal_Clinica (Codigo)
);

CREATE TABLE Consulta (
    Id_mascota INT NOT NULL,
    Codigo_veterinario INT NOT NULL,
    fecha DATE NOT NULL,
    diagnostico VARCHAR(200),
    PRIMARY KEY (Id_mascota, Codigo_veterinario, fecha),
    FOREIGN KEY (Id_mascota) REFERENCES Mascota (Id_mascota),
    FOREIGN KEY (Codigo_veterinario) REFERENCES Veterinario (Codigo)
);
```

---

<div align="center">

<img src="https://img.shields.io/badge/BASE_DE_DATOS-MODELADO_Y_GESTIÓN-DCC6F0?style=flat-square&labelColor=8064A2" />

*Portafolio Digital de Aprendizaje*  
**Universidad Nacional de Loja · Carrera de Computación**

</div>
