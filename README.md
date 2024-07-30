# HERESI SISTEMA IS3

# Plataforma de Telepsiquiatría

## Nombre del Equipo de Trabajo

**Equipo:** Poisson

**Integrantes:**
- **Lopez Condori Andrea del Rosario:** Desarrollador Front-End/Analista de Calidad
- **Mayorga Villena Jharold Alonso:** Desarrollador Back-End
- **Quispe Rojas Javier:** Desarrollador Front-End/Desarrollador Back-End
- **Vizcarra Vargas Piero Emiliano:** Scrum Master/DevOps
- **Zamalloa Molina Sebastian Agenor:** Desarrollador Back-End

## Cliente

**Cliente:** Organización Ficticia

## Propósito del Proyecto

Desarrollar una plataforma de telepsiquiatría con un sistema de agendado de citas accesible, que permita a los pacientes recibir atención psiquiátrica de manera remota y cómoda, mejorando así el acceso a la atención médica y optimizando la gestión de citas para el hospital psiquiátrico.

## Visión General de Arquitectura

### Estructura del Proyecto

El proyecto está organizado en varias carpetas y archivos clave para facilitar el desarrollo, la implementación y el mantenimiento. A continuación se describe la estructura del proyecto contenida en el archivo `ClinicManagement.7z`:

#### Estructura de Carpetas y Archivos

```
ClinicManagement/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── clinicmanagement/
│   │   │           ├── controller/
│   │   │           │   └── AppointmentController.java
│   │   │           ├── model/
│   │   │           │   └── Appointment.java
│   │   │           ├── repository/
│   │   │           │   └── AppointmentRepository.java
│   │   │           └── service/
│   │   │               └── AppointmentService.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       └── java/
│           └── com/
│               └── clinicmanagement/
│                   └── AppointmentControllerTest.java
├── .gitignore
├── README.md
└── pom.xml
```

#### Descripción de Carpetas y Archivos

- **src/main/java/com/clinicmanagement/controller/AppointmentController.java**: Contiene las clases controladoras que manejan las solicitudes HTTP relacionadas con las citas.
- **src/main/java/com/clinicmanagement/model/Appointment.java**: Define las entidades y modelos de datos utilizados en el sistema, en este caso, las citas.
- **src/main/java/com/clinicmanagement/repository/AppointmentRepository.java**: Interfaces que extienden los repositorios de Spring Data JPA para interactuar con la base de datos.
- **src/main/java/com/clinicmanagement/service/AppointmentService.java**: Implementa la lógica de negocio y las operaciones de servicio para las citas.
- **src/main/resources/application.properties**: Archivo de configuración de la aplicación.
- **src/test/java/com/clinicmanagement/AppointmentControllerTest.java**: Contiene las pruebas unitarias para las clases controladoras.
- **.gitignore**: Lista de archivos y directorios que Git debe ignorar.
- **README.md**: Archivo de documentación del proyecto.
- **pom.xml**: Archivo de configuración del proyecto Maven, incluyendo dependencias y plugins necesarios para la compilación y ejecución del proyecto.

### Servicios de Soporte a Tareas Automáticas en Procesos de Negocio

### Pruebas de Software
**Pruebas de Seguridad**
Reporte Inicial:
![b3f48072-9ab3-463d-a3b5-301097f194ef](https://github.com/user-attachments/assets/e6832625-a7ca-4c8a-ae0f-090c20e52a6f)
Reporte Post Fix
![7a630c38-ef93-46f6-9051-ac557362c2a3](https://github.com/user-attachments/assets/b144f655-32d3-477e-afa6-a99d47a03d3e)


