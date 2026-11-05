
<div align="center">

<img src="https://img.shields.io/badge/EJERCICIO-06-DCC6F0?style=for-the-badge&labelColor=8064A2" />

# 💻 Tienda Informática

*Diseño de una base de datos para la gestión de productos, clientes, compras y proveedores.*

</div>

---

**Enunciado:** Se desea crear una aplicación para la gestión de una tienda informática. La tienda dispone de una serie de productos que se venden a los clientes. De cada producto informático se desea guardar el código, descripción, precio y número de existencias. De cada cliente se desea guardar el código, nombre, apellidos, dirección y número telefónico. Un cliente puede comprar varios productos en la tienda y un mismo producto puede ser comprado por varios clientes. Cada vez que se compre un artículo quedará registrada la compra en la base de datos junto con la fecha en la que se compró el artículo. La tienda tiene contactos con varios proveedores que son los que suministran los productos. Un mismo producto puede ser suministrado por varios proveedores. De cada proveedor se desea guardar el código, nombres, apellidos, dirección, provincia y número de teléfono.

---

### 📐 Modelo Entidad-Relación

<img width="941" height="451" alt="image" src="https://github.com/user-attachments/assets/3fb0690b-44c0-4592-83a3-30e472b6bc0c" />

---

### 🔗 Modelo Relacional

<img width="800" height="287" alt="image" src="https://github.com/user-attachments/assets/ab6e7f6f-9fe5-464a-9cb1-f057a06df918" />

---

### 💻 Código SQL

```SQL
CREATE TABLE Producto (
    Codigo_producto INT PRIMARY KEY,
    descripcion VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2) NOT NULL,
    numero_existencia INT NOT NULL
);

CREATE TABLE Cliente (
    Codigo_cliente INT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    apellidos VARCHAR(50) NOT NULL,
    direccion VARCHAR(100),
    telefono VARCHAR(15)
);

CREATE TABLE Proveedor (
    Codigo_proveedor INT PRIMARY KEY,
    nombres VARCHAR(50) NOT NULL,
    apellidos VARCHAR(50) NOT NULL,
    direccion VARCHAR(100),
    provincia VARCHAR(50),
    telefono VARCHAR(15)
);

CREATE TABLE Compra (
    Codigo_producto INT NOT NULL,
    Codigo_cliente INT NOT NULL,
    fecha_compra DATE NOT NULL,
    PRIMARY KEY (Codigo_producto, Codigo_cliente, fecha_compra),
    FOREIGN KEY (Codigo_producto) REFERENCES Producto (Codigo_producto),
    FOREIGN KEY (Codigo_cliente) REFERENCES Cliente (Codigo_cliente)
);

CREATE TABLE Suministrado (
    Codigo_producto INT NOT NULL,
    Codigo_proveedor INT NOT NULL,
    PRIMARY KEY (Codigo_producto, Codigo_proveedor),
    FOREIGN KEY (Codigo_producto) REFERENCES Producto (Codigo_producto),
    FOREIGN KEY (Codigo_proveedor) REFERENCES Proveedor (Codigo_proveedor)
);
```

---

<div align="center">

<img src="https://img.shields.io/badge/BASE_DE_DATOS-MODELADO_Y_GESTIÓN-DCC6F0?style=flat-square&labelColor=8064A2" />

*Portafolio Digital de Aprendizaje*  
**Universidad Nacional de Loja · Carrera de Computación**

</div>
