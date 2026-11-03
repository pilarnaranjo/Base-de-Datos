
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

Scripts correspondientes a la creación y definición de las estructuras de la base de datos.

[📂 Consultar scripts SQL](./codigo_sql/)

---

<div align="center">

<img src="https://img.shields.io/badge/BASE_DE_DATOS-MODELADO_Y_GESTIÓN-DCC6F0?style=flat-square&labelColor=8064A2" />

*Portafolio Digital de Aprendizaje*  
**Universidad Nacional de Loja · Carrera de Computación**

</div>
