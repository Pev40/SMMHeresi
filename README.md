
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

## Nombre del Equipo de Trabajo

**Equipo:** Poisson

**Integrantes:**
- **Vizcarra Vargas Piero Emiliano:** Scrum Master/DevOps - CEO
- **Lopez Condori Andrea del Rosario:** Desarrollador Front-End/Analista de Calidad
- **Mayorga Villena Jharold Alonso:** Desarrollador Back-End
- **Quispe Rojas Javier:** Desarrollador Front-End/Desarrollador Back-End
- **Zamalloa Molina Sebastian Agenor:** Desarrollador Back-End

## Cliente

- **Nombre:** Centro de Salud Mental Moisés Heresi Farwagi
- **Ubicación:** Av. Pumacahua s/n, Cerro Colorado
- **Organización:** Sociedad de Beneficencia Pública de Arequipa
- **RUC:** 20120958136
- **Web:** [sbarequipa.org.pe](https://sbarequipa.org.pe/)

## Propósito del Proyecto

Desarrollar una plataforma de telepsiquiatría con un sistema de agendado de citas accesible, que permita a los pacientes recibir atención psiquiátrica de manera remota y cómoda, mejorando así el acceso a la atención médica y optimizando la gestión de citas para el hospital psiquiátrico.

### Objetivos

1. **Mejorar la precisión de diagnósticos y la efectividad de tratamientos:** Implementar herramientas en la plataforma que faciliten la evaluación remota de pacientes, permitiendo una mejor comprensión de sus necesidades y una planificación de tratamientos más precisa.
2. **Facilitar seguimientos efectivos y personalizados:** Desarrollar funcionalidades que posibiliten el seguimiento continuo de pacientes a distancia, asegurando un monitoreo efectivo de su progreso y ajustando los tratamientos según sea necesario para mejorar los resultados clínicos.
3. **Promover la empatía y la humanización en la atención remota:** Integrar elementos en la plataforma que fomenten la conexión emocional entre pacientes y profesionales de la salud mental durante las consultas virtuales, asegurando un trato respetuoso, cálido y empático, a pesar de la distancia física.
4. **Combatir el estigma y la discriminación:** Incorporar recursos educativos y de sensibilización en la plataforma para promover la comprensión y aceptación de los trastornos mentales, fomentando un ambiente inclusivo y libre de prejuicios tanto para pacientes como para profesionales de la salud.

## Visión General
### Arquitectura a del Proyecto
![image](https://github.com/user-attachments/assets/18d12313-0ce4-4f66-b6f6-50eccd3d6127)
### Infraestructua del Proyecto
![image](https://github.com/user-attachments/assets/7f94ec32-b3e8-48e3-827b-c7afdf7ecfd8)

### DDD

![ddd](https://github.com/user-attachments/assets/bc1a4af7-23d6-41f9-930c-d111a3bacf71) 

La plataforma de telepsiquiatría está organizada en varias capas siguiendo el patrón de diseño Domain-Driven Design (DDD). 

#### Servicios de Dominio

Esta capa encapsula la lógica de negocio y contiene servicios como `AuthService`, `PatientService`, `DoctorService` y `AppointmentService`, que manejan operaciones esenciales como la autenticación, la gestión de pacientes y doctores, y la programación de citas.

#### Aplicación

La capa de Aplicación incluye controladores como `AccountController`, `PatientsController`, `DoctorsController` y `AppointmentsController`, que manejan las solicitudes HTTP y delegan las operaciones a los servicios de dominio.

#### Repositorios

Esta capa se encarga de la persistencia y recuperación de datos, definiendo métodos para buscar, guardar, actualizar y eliminar entidades. Los repositorios incluyen `PatientRepository`, `DoctorRepository` y `AppointmentRepository`.

#### Dominio

La capa de Dominio contiene las clases principales del modelo, incluyendo agregados como `Patient`, `Doctor` y `Appointment`, y entidades como `User`, que representan los conceptos clave del negocio.

#### Relaciones

Las relaciones entre las capas están claramente delineadas, facilitando la comprensión, el mantenimiento y la expansión del sistema. Los controladores dependen de los servicios de dominio, y estos, a su vez, dependen de los repositorios para interactuar con la base de datos.



### Estructura de Carpetas y Archivos

```
├───.sonarqube
│   ├───bin
│   │   └───targets
│   ├───conf
├───ClinicManagement
│   ├───.config
│   ├───App_Start
│   ├───bin
│   ├───Content
│   │   ├───bootstrap
│   │   │   └───mixins
│   │   ├───css
│   │   │   └───iCheck
│   │   ├───DataTables
│   │   │   ├───css
│   │   │   ├───images
│   │   │   └───swf
│   │   ├───fonts
│   │   ├───iCheck
│   │   ├───images
│   │   └───themes
│   │       └───base
│   │           └───images
│   ├───Controllers
│   │   └───Api
│   ├───Core
│   │   ├───Dto
│   │   ├───Helpers
│   │   ├───Models
│   │   ├───Repositories
│   │   └───ViewModel
│   ├───Migrations
│   ├───obj
│   │   └───Debug
│   │       └───TempPE
│   ├───Persistence
│   │   ├───EntityConfigurations
│   │   └───Repositories
│   ├───Properties
│   ├───Scripts
│   │   ├───DataTables
│   │   ├───flot
│   │   ├───locales
│   │   └───vendors
│   └───Views
│       ├───Account
│       ├───Appointments
│       ├───Attendances
│       ├───Doctors
│       ├───Home
│       ├───Manage
│       ├───Patients
│       ├───Reports
│       └───Shared
└───packages
```

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

- Documentación de  Swagger:
  ![image](https://github.com/user-attachments/assets/67c125b5-7554-40a8-ae66-bd88fbd2031f)
- Dcumentación en Postman : 
![image](https://github.com/user-attachments/assets/7132c2f5-7c47-4a2e-b9e4-f430604a31f7)
https://documenter.getpostman.com/view/16226524/2sA3kd9H84#fb41158a-2f37-4130-b2f0-e06bf999d757

Test de Api:
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response status code is 200", function () {
    pm.response.to.have.status(200);
});


pm.test("Response time is less than 200ms", function () {
  pm.expect(pm.response.responseTime).to.be.below(200);
});


pm.test("Response time is less than 200ms", function () {
  pm.expect(pm.response.responseTime).to.be.below(200);
});

pm.test("Validate the response schema for the presence of required fields", function () {
  const responseData = pm.response.json();

  pm.expect(responseData).to.be.an('array').that.is.not.empty;

  responseData.forEach(function (patient) {
    pm.expect(patient).to.have.property('id');
    pm.expect(patient).to.have.property('token');
    pm.expect(patient).to.have.property('name');
    pm.expect(patient).to.have.property('birthDate');
    pm.expect(patient).to.have.property('phone');
    pm.expect(patient).to.have.property('address');
    pm.expect(patient).to.have.property('cityId');
    pm.expect(patient).to.have.property('cities');
    pm.expect(patient).to.have.property('doctorId');
    pm.expect(patient).to.have.property('doctor');
    pm.expect(patient).to.have.property('dateTime');
    pm.expect(patient).to.have.property('height');
    pm.expect(patient).to.have.property('weight');
  });
});


pm.test("Presence of Content-Type header in the response", function () {
    pm.expect(pm.response.headers.get("Content-Type")).to.exist;
});


pm.test("Response status code is 200", function () {
    pm.response.to.have.status(200);
});


pm.test("Response schema includes required fields", function () {
  const responseData = pm.response.json();
  
  pm.expect(responseData).to.be.an('array');
  responseData.forEach(function(patient){
    pm.expect(patient).to.have.property('id');
    pm.expect(patient).to.have.property('name');
    pm.expect(patient).to.have.property('birthDate');
    pm.expect(patient).to.have.property('phone');
    pm.expect(patient).to.have.property('address');
    pm.expect(patient).to.have.property('cityId');
    pm.expect(patient).to.have.property('cities');
    pm.expect(patient).to.have.property('doctorId');
    pm.expect(patient).to.have.property('dateTime');
    pm.expect(patient).to.have.property('height');
    pm.expect(patient).to.have.property('weight');
  });
});


pm.test("Response time is less than 200ms", function () {
  pm.expect(pm.response.responseTime).to.be.below(200);
});
```
![image](https://github.com/user-attachments/assets/02405fd3-1327-423b-8585-66e7d7f5d977)

### Pruebas de Seguridad

**Casos de Prueba y Resultados:**

Reporte Inicial:
![b3f48072-9ab3-463d-a3b5-301097f194ef](https://github.com/user-attachments/assets/e6832625-a7ca-4c8a-ae0f-090c20e52a6f)
Reporte Post Fix
![7a630c38-ef93-46f6-9051-ac557362c2a3](https://github.com/user-attachments/assets/b144f655-32d3-477e-afa6-a99d47a03d3e)

### Pruebas de Performance
![image](https://github.com/user-attachments/assets/370e50f4-80d6-4869-8dc0-a7dd4b2fc35b)
El analisis de SonarQube nos muestra la deudad tecnica es de 2k H, dando un resultado de mantemibilidad de A. La duplicidad es de 14.7%, principalmente dado por archivos css. El rendimiento si tiene varios problemas dando 243 issues posibles. En cuento a seguridad del codigo nos da un grado A, teniendo 0 issues, dando un nota general de Aceptable.
Informe ZAP:
https://github.com/Pev40/SMMHeresi/blob/main/2024-07-31-ZAP-Report-localhost.html
## Gestión de Cambios

![image](https://github.com/user-attachments/assets/4e6928ef-e9ce-4159-b924-521412e46a95)


### Principios SOLID


#### Single Responsibility Principle (SRP)
El principio de responsabilidad única establece que cada clase debe tener una única responsabilidad o motivo para cambiar. En nuestro proyecto, esto se ve reflejado en el controlador `PatientsController`, que maneja exclusivamente las operaciones relacionadas con los pacientes.

```csharp
public class PatientsController : Controller
{
    private readonly IUnitOfWork _unitOfWork;

    public PatientsController(IUnitOfWork unitOfWork)
    {
        _unitOfWork = unitOfWork;
    }

    public ActionResult Index()
    {
        return View();
    }

    // Otros métodos relacionados con pacientes...
}
```

#### Open/Closed Principle (OCP)
El principio de abierto/cerrado sugiere que las entidades de software deben estar abiertas para la extensión pero cerradas para la modificación. Esto se puede observar en la interfaz `IAppointmentRepository`, que permite agregar nuevas funcionalidades sin modificar las existentes.

```csharp
public interface IAppointmentRepository
{
    IEnumerable<Appointment> GetAppointments();
    IEnumerable<Appointment> GetAppointmentWithPatient(int id);
    // Otros métodos relacionados con citas...
}
```

#### Liskov Substitution Principle (LSP)
El principio de sustitución de Liskov establece que los objetos de una clase derivada deben poder reemplazar a los objetos de la clase base sin alterar el funcionamiento del programa. En nuestro proyecto, `PatientsController` depende de la abstracción `IUnitOfWork`, lo que permite reemplazar la implementación concreta sin cambiar el comportamiento del controlador.

```csharp
public PatientsController(IUnitOfWork unitOfWork)
{
    _unitOfWork = unitOfWork;
}
```

#### Interface Segregation Principle (ISP)
El principio de segregación de interfaces sugiere que los clientes no deben estar forzados a depender de interfaces que no usan. Esto se ve reflejado en nuestro proyecto a través de interfaces bien definidas para cada repositorio, como `IPatientRepository`, `ICityRepository`, etc.

```csharp
public interface IUnitOfWork
{
    IPatientRepository Patients { get; }
    IAppointmentRepository Appointments { get; }
    // Otros repositorios...
}
```

#### Dependency Inversion Principle (DIP)
El principio de inversión de dependencias establece que los módulos de alto nivel no deben depender de módulos de bajo nivel, sino que ambos deben depender de abstracciones. En nuestro proyecto, `PatientsController` depende de la abstracción `IUnitOfWork` en lugar de una implementación concreta, facilitando la inyección de dependencias.

```csharp
private readonly IUnitOfWork _unitOfWork;

public PatientsController(IUnitOfWork unitOfWork)
{
    _unitOfWork = unitOfWork;
}
```
