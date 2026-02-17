# BiblioTech 

##  Descripción
BiblioTech es una plataforma diseñada para digitalizar la administración de una biblioteca física o virtual. El sistema permite gestionar un catálogo extenso de libros, organizar autores y categorías, y llevar un control riguroso de los usuarios y sus préstamos activos. La solución busca automatizar el flujo desde que un usuario busca un ejemplar hasta que lo devuelve, asegurando la integridad de la disponibilidad de los libros.

##  Motivación
La gestión manual de inventarios y préstamos suele derivar en pérdida de información o falta de control sobre las fechas de entrega. Este proyecto nace de la necesidad de:
Optimizar el tiempo: Automatizar el registro de entradas y salidas.
Centralización: Tener una base de datos única para evitar duplicidades en el catálogo.
Accesibilidad: Permitir que los bibliotecarios visualicen de forma rápida qué ejemplares están disponibles y quiénes tienen libros en mora.
# 📚 Sistema de Biblioteca Virtual (Examen)

## 1. Título
**BiblioTech: Gestión Integral de Catálogo y Usuarios**

## 2. Descripción
Este proyecto consiste en el diseño de una base de datos relacional para administrar una biblioteca virtual. El sistema permite el registro de autores, la catalogación de libros y el control de préstamos realizados por los usuarios, garantizando la integridad de los datos y la trazabilidad de cada ejemplar.

## 3. Motivación
La principal motivación de este desarrollo es resolver los problemas de pérdida de stock y falta de control en las fechas de devolución que ocurren en sistemas manuales. Con este diseño se busca:
* Centralizar la información de los libros y sus autores.
* Monitorear en tiempo real quién tiene cada libro.
* Facilitar la expansión del catálogo de forma organizada.

## 4. Diagrama Entidad-Relación (E-R)
Este diagrama representa la lógica del negocio y cómo interactúan las entidades principales mediante llaves primarias y foráneas.
erDiagram
    USUARIO ||--o{ PRESTAMO : realiza
    LIBRO ||--o{ PRESTAMO : incluye
    CATEGORIA ||--o{ LIBRO : clasifica

    USUARIO {
        int id_usuario PK
        string nombre
        string email
        string telefono
    }

    LIBRO {
        int id_libro PK
        string titulo
        string autor
        string isbn
        int stock
        int id_categoria FK
    }

    PRESTAMO {
        int id_prestamo PK
        int id_usuario FK
        int id_libro FK
        date fecha_salida
        date fecha_devolucion
        string estado
    }

    CATEGORIA {
        int id_categoria PK
        string nombre
        string descripcion
    }
    classDiagram
    class Usuario {
        +int id_usuario
        +string nombre
        +string email
        -string password
        +registrar()
        +iniciarSesion()
    }

    class Libro {
        +int id_libro
        +string titulo
        +string autor
        +string isbn
        +bool disponibilidad
        +actualizarStock()
    }

    class Prestamo {
        +int id_prestamo
        +date fecha_inicio
        +date fecha_fin
        +string estado
        +generarMulta()
        +finalizarPrestamo()
    }

    class Categoria {
        +int id_categoria
        +string nombre
        +obtenerLibros()
    }

    Usuario "1" --> "*" Prestamo : solicita
    Libro "1" -- "*" Prestamo : es_prestado
    Categoria "1" -- "*" Libro : contiene

|
