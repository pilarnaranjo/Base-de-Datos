
<div align="center">

<img src="https://img.shields.io/badge/EJERCICIO-04-DCC6F0?style=for-the-badge&labelColor=8064A2" />

# ✈️ Sistema de Aerolínea

*Diseño de una base de datos para la gestión de vuelos, aviones, pasajeros y reservas.*

</div>

---

**Enunciado:** Una aerolínea opera vuelos (cada uno con número, fecha, origen y destino), cada vuelo lo realiza un avión. Los pasajeros realizan reservas para un vuelo específico, indicando asiento y tarifa pagada en el momento de la reserva.

---

### 📐 Modelo Entidad-Relación

<img width="578" height="317" alt="image" src="https://github.com/user-attachments/assets/b055bd16-c8bc-4943-b85f-f2f93e62d29c" />

---

### 🔗 Modelo Relacional

<img width="583" height="241" alt="image" src="https://github.com/user-attachments/assets/7a9c7e1b-ccd9-4423-9c88-392930ce094b" />

---

### 💻 Código SQL

```SQL
CREATE TABLE Avion (
    Id_avion INT PRIMARY KEY
);

CREATE TABLE Vuelo (
    numero_vuelo INT PRIMARY KEY,
    fecha DATE NOT NULL,
    origen VARCHAR(30) NOT NULL,
    destino VARCHAR(30) NOT NULL,
    Id_avion INT NOT NULL,
    FOREIGN KEY (Id_avion) REFERENCES Avion (Id_avion)
);

CREATE TABLE Pasajero (
    Id_pasajero INT PRIMARY KEY
);

CREATE TABLE Reserva (
    numero_vuelo INT NOT NULL,
    Id_pasajero INT NOT NULL,
    PRIMARY KEY (numero_vuelo, Id_pasajero),
    FOREIGN KEY (numero_vuelo) REFERENCES Vuelo (numero_vuelo),
    FOREIGN KEY (Id_pasajero) REFERENCES Pasajero (Id_pasajero)
);
```
---

<div align="center">

<img src="https://img.shields.io/badge/BASE_DE_DATOS-MODELADO_Y_GESTIÓN-DCC6F0?style=flat-square&labelColor=8064A2" />

*Portafolio Digital de Aprendizaje*  
**Universidad Nacional de Loja · Carrera de Computación**

</div>
