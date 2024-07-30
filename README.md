# HERESI SISTEMA IS3# SMMHeresi
Para estructurar el README del repositorio de GitHub del proyecto de manera adecuada, siguiendo las indicaciones proporcionadas en la imagen y la información general del proyecto, puedes organizar el contenido de la siguiente manera:

---

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

**Arquitectura:** DDD (Domain-Driven Design) y Arquitectura Limpia.

## Servicios de Soporte a Tareas Automáticas en Procesos de Negocio

**Formato Estándar:** OpenAPI y Herramienta Swagger

### Módulos

#### Nombre + Propósito

- **Programación de Citas:**
  - **Operaciones Disponibles:**
    - **Método:** POST
    - **URL:** `/api/citas`
    - **Parámetros:** `{ "pacienteId": "123", "fecha": "2024-08-01", "hora": "10:00" }`
  - **Modelos:**
    - **Entidades:** Cita, Paciente
    - **Agregados o Módulos Clave:** Gestión de Citas

#### Consulta Virtual

- **Operaciones Disponibles:**
  - **Método:** POST
  - **URL:** `/api/consultas`
  - **Parámetros:** `{ "pacienteId": "123", "profesionalId": "456", "fecha": "2024-08-01", "hora": "10:00", "tipo": "virtual" }`
- **Modelos:**
  - **Entidades:** Consulta, Paciente, Profesional
  - **Agregados o Módulos Clave:** Gestión de Consultas Virtuales

### Pruebas de Software

