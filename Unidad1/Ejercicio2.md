
<div align="center">

<img src="https://img.shields.io/badge/EJERCICIO-02-DCC6F0?style=for-the-badge&labelColor=8064A2" />

# 🍽️ Pedidos de Restaurante

*Diseño de una base de datos para la gestión de clientes, pedidos, platos y meseros.*

</div>

---

**Enunciado:** Los clientes realizan pedidos que contienen varios platos con distinta cantidad. Los platos se agrupan en categorías. Cada pedido lo atiende un único mesero. El precio del plato debe registrarse tal como estaba al momento del pedido, aunque luego cambie.

---

### 📐 Modelo Entidad-Relación

<img width="941" height="261" alt="image" src="https://github.com/user-attachments/assets/0b6ba5a0-560d-4dd8-b682-b5377fb33c73" />

---

### 🔗 Modelo Relacional

<img width="532" height="286" alt="image" src="https://github.com/user-attachments/assets/316002b9-dffa-4320-ad99-29b3026d1738" />

---

### 💻 Código SQL
```SQL
CREATE TABLE Cliente (
    Id_Cliente INT PRIMARY KEY
);

CREATE TABLE Mesero (
    Id_Mesero INT PRIMARY KEY
);

CREATE TABLE Categoria (
    Id_Categoria INT PRIMARY KEY
);

CREATE TABLE Platos (
    Id_Plato INT PRIMARY KEY,
    Id_Categoria INT NOT NULL,
    FOREIGN KEY (Id_Categoria) REFERENCES Categoria (Id_Categoria)
);

CREATE TABLE Pedido (
    Id_Pedido INT PRIMARY KEY,
    Id_Cliente INT NOT NULL,
    Id_Mesero INT NOT NULL,
    FOREIGN KEY (Id_Cliente) REFERENCES Cliente (Id_Cliente),
    FOREIGN KEY (Id_Mesero) REFERENCES Mesero (Id_Mesero)
);

CREATE TABLE Detalle_Pedido (
    Id_Pedido INT NOT NULL,
    Id_Plato INT NOT NULL,
    Cantidad INT NOT NULL,
    Precio_Plato DECIMAL(10,2) NOT NULL,
    PRIMARY KEY (Id_Pedido, Id_Plato),
    FOREIGN KEY (Id_Pedido) REFERENCES Pedido (Id_Pedido),
    FOREIGN KEY (Id_Plato) REFERENCES Platos (Id_Plato)
);

---

<div align="center">

<img src="https://img.shields.io/badge/BASE_DE_DATOS-MODELADO_Y_GESTIÓN-DCC6F0?style=flat-square&labelColor=8064A2" />

*Portafolio Digital de Aprendizaje*  
**Universidad Nacional de Loja · Carrera de Computación**

</div>
