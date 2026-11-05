
<div align="center">

<img src="https://img.shields.io/badge/EJERCICIO-03-DCC6F0?style=for-the-badge&labelColor=8064A2" />

# 🏥 Clínica Médica

*Diseño de una base de datos para la gestión de pacientes, médicos, citas y recetas.*

</div>

---

**Enunciado:** Los pacientes solicitan citas; cada cita la atiende un médico a un paciente en fecha, hora y consultorio. De algunas citas se genera una receta que incluye medicamentos con dosis y duración. Cada médico pertenece a una especialidad.

---

### 📐 Modelo Entidad-Relación

<img width="980" height="415" alt="image" src="https://github.com/user-attachments/assets/acfddc21-9c3c-4b28-9719-4dc14b537358" />

---

### 🔗 Modelo Relacional

<img width="595" height="313" alt="image" src="https://github.com/user-attachments/assets/5db7aff6-8b13-4d92-99d5-91f25befe41e" />

---

### 💻 Código SQL
```sql
CREATE TABLE Paciente (
    Id_paciente INT PRIMARY KEY
);

CREATE TABLE Especialidad (
    Id_especialidad INT PRIMARY KEY
);

CREATE TABLE Medico (
    Id_medico INT PRIMARY KEY,
    Id_especialidad INT NOT NULL,
    FOREIGN KEY (Id_especialidad) REFERENCES Especialidad (Id_especialidad)
);

CREATE TABLE Cita (
    Id_cita INT PRIMARY KEY,
    fecha DATE NOT NULL,
    hora TIME NOT NULL,
    consultorio VARCHAR(20) NOT NULL,
    Id_paciente INT NOT NULL,
    Id_medico INT NOT NULL,
    FOREIGN KEY (Id_paciente) REFERENCES Paciente (Id_paciente),
    FOREIGN KEY (Id_medico) REFERENCES Medico (Id_medico)
);

CREATE TABLE Receta (
    Id_receta INT PRIMARY KEY,
    Id_cita INT NOT NULL,
    FOREIGN KEY (Id_cita) REFERENCES Cita (Id_cita)
);

CREATE TABLE Medicamento (
    Id_medicamento INT PRIMARY KEY
);

CREATE TABLE Receta_Medicamento (
    Id_receta INT NOT NULL,
    Id_medicamento INT NOT NULL,
    PRIMARY KEY (Id_receta, Id_medicamento),
    FOREIGN KEY (Id_receta) REFERENCES Receta (Id_receta),
    FOREIGN KEY (Id_medicamento) REFERENCES Medicamento (Id_medicamento)
);
```


---

<div align="center">

<img src="https://img.shields.io/badge/BASE_DE_DATOS-MODELADO_Y_GESTIÓN-DCC6F0?style=flat-square&labelColor=8064A2" />

*Portafolio Digital de Aprendizaje*  
**Universidad Nacional de Loja · Carrera de Computación**

</div>
