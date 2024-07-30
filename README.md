
# HERESI SISTEMA IS3

# Plataforma de Telepsiquiatría

## Índice
- [Nombre del Equipo de Trabajo](#nombre-del-equipo-de-trabajo)
- [Cliente](#cliente)
- [Propósito del Proyecto](#propósito-del-proyecto)
  - [Objetivos](#objetivos)
- [Visión General de Arquitectura](#visión-general-de-arquitectura)
  - [Estructura del Proyecto](#estructura-del-proyecto)
    - [Estructura de Carpetas y Archivos](#estructura-de-carpetas-y-archivos)
    - [Descripción de Carpetas y Archivos](#descripción-de-carpetas-y-archivos)
- [Servicios de Soporte a Tareas Automáticas en Procesos de Negocio](#servicios-de-soporte-a-tareas-automáticas-en-procesos-de-negocio)
  - [Módulos](#módulos)
  - [Operaciones Disponibles](#operaciones-disponibles)
  - [Modelos](#modelos)
    - [Entidades y Agregados](#entidades-y-agregados)
- [Pruebas de Software](#pruebas-de-software)
  - [Pruebas de APIs](#pruebas-de-apis)
  - [Pruebas de Seguridad](#pruebas-de-seguridad)
  - [Pruebas de Performance](#pruebas-de-performance)
- [Gestión de Cambios](#gestión-de-cambios)
- [Contribución](#contribución)
- [Licencia](#licencia)

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

### Objetivos

1. **Mejorar la precisión de diagnósticos y la efectividad de tratamientos:** Implementar herramientas en la plataforma que faciliten la evaluación remota de pacientes, permitiendo una mejor comprensión de sus necesidades y una planificación de tratamientos más precisa.
2. **Facilitar seguimientos efectivos y personalizados:** Desarrollar funcionalidades que posibiliten el seguimiento continuo de pacientes a distancia, asegurando un monitoreo efectivo de su progreso y ajustando los tratamientos según sea necesario para mejorar los resultados clínicos.
3. **Promover la empatía y la humanización en la atención remota:** Integrar elementos en la plataforma que fomenten la conexión emocional entre pacientes y profesionales de la salud mental durante las consultas virtuales, asegurando un trato respetuoso, cálido y empático, a pesar de la distancia física.
4. **Combatir el estigma y la discriminación:** Incorporar recursos educativos y de sensibilización en la plataforma para promover la comprensión y aceptación de los trastornos mentales, fomentando un ambiente inclusivo y libre de prejuicios tanto para pacientes como para profesionales de la salud.

## Visión General de Arquitectura

### Estructura del Proyecto

El proyecto está organizado en varias carpetas y archivos clave para facilitar el desarrollo, la implementación y el mantenimiento. A continuación se describe la estructura del proyecto contenida:

#### Estructura de Carpetas y Archivos

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

## Servicios de Soporte a Tareas Automáticas en Procesos de Negocio

Esta sección describe los servicios de soporte a tareas automáticas en procesos de negocio utilizando **OpenAPI** y la herramienta **Swagger**.

### Módulos

#### Clinic Management
**Propósito:** Gestionar clínicas y registros de pacientes.

### Operaciones Disponibles

| Método | URL              | Parámetros       |
| ------ | ---------------- | ---------------- |
| GET    | /api/patients    | id, name         |
| POST   | /api/patients    | name, age, gender|
| GET    | /api/clinics     | id, location     |
| POST   | /api/clinics     | name, address    |

### Modelos

#### Entidades y Agregados

##### Paciente
- **Descripción:** Entidad que representa a un paciente.
- **Atributos:**
  - **id:** Identificador único del paciente.
  - **name:** Nombre del paciente.
  - **age:** Edad del paciente.
  - **gender:** Género del paciente.

##### Clínica
- **Descripción:** Entidad que representa a una clínica.
- **Atributos:**
  - **id:** Identificador único de la clínica.
  - **name:** Nombre de la clínica.
  - **address:** Dirección de la clínica.

## Pruebas de Software

### Pruebas de APIs

**Casos de Prueba y Resultados:**

- Verificar que las operaciones CRUD (crear, leer, actualizar, eliminar) funcionan correctamente para usuarios, citas y registros clínicos.
- Verificar la interacción entre módulos, como agendado de citas e historial clínico.
- Evaluar la facilidad de uso de la interfaz de usuario y asegurar que es accesible para diferentes perfiles de usuarios.

### Pruebas de Seguridad

**Casos de Prueba y Resultados:**

Reporte Inicial:
![Reporte Inicial](https://github.com/user-attachments/assets/e6832625-a7ca-4c8a-ae0f-090c20e52a6f/b3f48072-9ab3-463d-a3b5-301097f194ef)

Reporte Post Fix:
![Reporte Post Fix](https://github.com/user-attachments/assets/b144f655-32d3-477e-afa6-a99d47a03d3e/7a630c38-ef93-46f6-9051-ac557362c2a3)

### Pruebas de Performance

**Casos de Prueba y Resultados:**

- Medir el tiempo de respuesta de las operaciones bajo carga normal y máxima.
- Simular el uso del sistema por múltiples usuarios simultáneos para asegurar que soporta el número esperado de usuarios.

## Gestión de Cambios

**Registro y Seguimiento:** Registro de defectos y mejoras, seguimiento de cambios realizados en el sistema.

