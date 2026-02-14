# BiblioTech 

##  Descripción
Un sistema integral diseñado para digitalizar el control de inventario y préstamos de libros en bibliotecas medianas y pequeñas.

##  Motivación
Este proyecto nace de la necesidad de reducir la pérdida de ejemplares físicos y agilizar el proceso de registro de usuarios, sustituyendo las bitácoras manuales por una base de datos eficiente.

##  Tech Stack
* **Base de Datos:** MySQL / PostgreSQL
* **Diseño:** Modelo Entidad-Relación (E-R)
* **Documentación:** Markdown

##  Modelo Entidad-Relación
Aquí se detalla la lógica de los datos:
* **Entidades:** Usuario, Libro, Préstamo.
* **Relaciones:** Un Usuario realiza N Préstamos; un Préstamo incluye N Libros.
