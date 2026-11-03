<div align="center">

<img src="https://img.shields.io/badge/UNIDAD-01-DCC6F0?style=for-the-badge&labelColor=8064A2" />

# 🟣 Modelo Relacional

*Ejemplos y ejercicios prácticos de diseño de bases de datos.*

</div>

---

### 📚 01. Sistema de Biblioteca

Una biblioteca registra libros y autores. Un libro puede tener varios autores y un autor varios libros. Los socios toman libros prestados; de cada préstamo interesan la fecha de retiro y la de devolución.

**Modelo Relacional**

<img width="761" height="269" alt="image" src="https://github.com/user-attachments/assets/e598276f-4b36-47b3-8f3f-fde364923297" />


---

### 🍇 02. Pedidos de Restaurante

Los clientes realizan pedidos que contienen varios platos con distinta cantidad. Los platos se agrupan en categorías. Cada pedido lo atiende un único mesero. El precio del plato debe registrarse tal como estaba al momento del pedido, aunque luego cambie.

**Modelo Relacional**

<img width="532" height="286" alt="image" src="https://github.com/user-attachments/assets/e2afb27e-6dc7-4f86-93c8-fa191705de73" />

---

### 🪷 03. Clínica Médica

Los pacientes solicitan citas; cada cita la atiende un médico a un paciente en fecha, hora y consultorio. De algunas citas se genera una receta que incluye medicamentos con dosis y duración. Cada médico pertenece a una especialidad.

**Modelo Relacional**

<img width="595" height="313" alt="image" src="https://github.com/user-attachments/assets/c69cdd2f-910d-4a53-88b6-dde866d8f494" />

---

### ✈️ 04. Sistema de Aerolínea

Una aerolínea opera vuelos (cada uno con número, fecha, origen y destino), cada vuelo lo realiza un avión. Los pasajeros realizan reservas para un vuelo específico, indicando asiento y tarifa pagada en el momento de la reserva.

**Modelo Relacional**

<img width="583" height="241" alt="image" src="https://github.com/user-attachments/assets/fae3e22e-44ed-4bf3-85fb-770a3f8a0f81" />

---

## 🟣 Ejercicios Propuestos

### 🎼 05. Empresa Discográfica

Una empresa discográfica necesita modelar los datos sobre sus diferentes recursos según las siguientes características:

● Manager: de cada mánager se almacena un identificador de manager y su nombre. Un manager representa a una serie de artistas.

● Artista: un artista es representado por un manager. De los artistas se almacena su nombre completo (usando un único atributo) y su NIF.

● Evento de promoción: los artistas participan en eventos de promoción para dar a conocer sus trabajos. En un evento de promoción pueden participar varios artistas. De un evento se almacena un identificador único, la fecha de celebración y el número de asistentes.

**Modelo Relacional**

<img width="576" height="220" alt="image" src="https://github.com/user-attachments/assets/73f977b0-d473-4021-8fa8-6234866984b0" />

---

### 💻 06. Tienda Informática

Se desea crear una aplicación para la gestión de una tienda informática. La tienda dispone de una serie de productos que se venden a los clientes. De cada producto informático se desea guardar el código, descripción, precio y número de existencias. De cada cliente se desea guardar el código, nombre, apellidos, dirección y número telefónico. Un cliente puede comprar varios productos en la tienda y un mismo producto puede ser comprado por varios clientes. Cada vez que se compre un artículo quedará registrada la compra en la base de datos junto con la fecha en la que se compró el artículo. La tienda tiene contactos con varios proveedores que son los que suministran los productos. Un mismo producto puede ser suministrado por varios proveedores. De cada proveedor se desea guardar el código, nombres, apellidos, dirección, provincia y número de teléfono.

**Modelo Relacional**

<img width="800" height="287" alt="image" src="https://github.com/user-attachments/assets/4368b53c-f836-4bae-a089-9260911f74c6" />

---

### 🎧 07. Discos Musicales

● La tienda vende discos de diferentes géneros musicales y cantantes

● Cada género musical tiene un identificador

● Cada disco tiene titulo, genero musical, precio y cantante

● De un cantante se registra el nombre y su país, Todo disco pertenece a un cantante y un cantante puede tener muchos discos. Además un disco tiene un conjunto de canciones(identificador y título)

● Un disco tiene muchas canciones y una canción puede estar en varios discos. Interesa conocer la posición de una canción en un determinado disco

**Modelo Relacional**

<img width="565" height="261" alt="image" src="https://github.com/user-attachments/assets/e4b314e1-77a0-4460-8b82-57a525c65679" />

---

### 🚚 08. Camiones

Se desea informatizar la gestión de una empresa de transporte que reparte paquetes por toda España. Los encargados de llevar los paquetes son los camioneros, de los que se quiere guardar la cédula, nombre, teléfono, dirección, salario y población en que vive. De los paquetes transportados interesa conocer el código del paquete, descripción, destinatario y dirección del destinatario.

Un camionero distribuye muchos paquetes, y un paquete sólo puede ser distribuido por un camionero. De las provincias a las que llegan los paquetes interesa guardar el código de provincia y el nombre. Un paquete sólo puede llegar a una provincia. Sin embargo, a una provincia pueden llegar varios paquetes.

De los camiones que llevan los camioneros, interesa conocer la matrícula, modelo, tipo y potencia. Un camionero puede conducir diferentes camiones en fechas diferentes, y un camión puede ser conducido por varios camioneros.

**Modelo Relacional**

<img width="750" height="246" alt="image" src="https://github.com/user-attachments/assets/8efb5552-b2e9-42a6-b028-b7771c9f1437" />

---

### 🐾 09. Veterinaria

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

**Modelo Relacional**

<img width="796" height="429" alt="image" src="https://github.com/user-attachments/assets/a99bd884-63d3-4753-a9d9-c60f39faf36f" />

---

<div align="center">

<img src="https://img.shields.io/badge/UNIVERSIDAD-NACIONAL_DE_LOJA-DCC6F0?style=flat-square&labelColor=8064A2" />

**💜 Portafolio Digital de Aprendizaje**

Carrera de Computación

*Septiembre 2026 – Febrero 2027*

</div>
