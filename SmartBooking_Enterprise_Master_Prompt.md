# SmartBooking Enterprise

## Plataforma Empresarial de Reservas de Salas

### Visión General

Actúa como un Arquitecto de Software Empresarial Senior, UX/UI Lead, Product Owner, Solution Architect y Tech Lead especializado en plataformas de gestión de espacios corporativos.

Diseña e implementa una solución SaaS denominada **SmartBooking Enterprise**, orientada a la reserva inteligente de salas corporativas con actualización en tiempo real, autogestión, terminales digitales para salas y generación de calendarios imprimibles.

---

# Objetivos

- Reservar salas en menos de 30 segundos.
- Menos de 3 clics para completar una reserva.
- Actualización en tiempo real.
- Experiencia moderna y visual.
- Arquitectura escalable y mantenible.
- Compatibilidad futura con PostgreSQL y SQL Server.

---

# Arquitectura

## Principios

- Clean Architecture
- Domain Driven Design (DDD)
- SOLID
- CQRS
- Event Driven Architecture
- Security By Design
- Observabilidad
- Twelve-Factor App

---

# Stack Tecnológico

## Frontend

- Angular 22
- TypeScript
- Standalone Components
- Angular Signals
- RxJS
- Bootstrap 5
- Bootstrap Icons
- SCSS
- FullCalendar Enterprise
- SignalR Client
- Signal Store

## Backend

- .NET 10
- ASP.NET Core
- Entity Framework Core
- MediatR
- FluentValidation
- AutoMapper
- Serilog
- SignalR

## Base de Datos

Base principal:

- PostgreSQL

Requisito obligatorio:

La solución debe ser Database Agnostic.

Debe permitir reemplazar PostgreSQL por SQL Server únicamente mediante configuración.

Implementar:

- Repository Pattern
- Unit Of Work
- Dependency Injection
- Entity Framework Core
- Migraciones desacopladas

Sin modificar:

- Dominio
- Casos de uso
- Aplicación
- APIs
- Servicios

---

# Modelo Funcional

## Recurso Reservable

La plataforma estará enfocada en la reserva de salas.

Todos los espacios serán gestionados bajo la entidad:

```text
Sala
```

Incluye:

- Sala de reuniones
- Auditorio
- Laboratorio
- Sala de capacitación
- Oficina compartida
- Sala especial
- Espacio colaborativo

---

# Modalidad de Autogestión

Las salas funcionarán bajo modalidad:

```text
AutoGestionada
```

Cuando una sala esté disponible:

- El primer usuario obtiene la reserva.
- La reserva se confirma automáticamente.
- No requiere aprobaciones.
- Actualización inmediata para todos los usuarios.

Validaciones:

- No permitir doble reserva.
- No permitir solapamientos.
- No permitir reservas sobre mantenimientos.
- No permitir reservas sobre bloqueos.

---

# Estados

```text
Disponible
Reservada
En Curso
Finalizada
Cancelada
Bloqueada
Mantenimiento
```

---

# Experiencia Visual

La plataforma debe tener un diseño:

- Moderno
- Impactante
- Profesional
- Minimalista
- Responsive
- Mobile First
- Accesible (WCAG AA)

Inspirado en:

- Microsoft Outlook
- Microsoft Bookings
- Microsoft Teams
- Notion
- Linear

---

# Portal de Gestión

Dirigido a:

- Administradores
- Supervisores
- Colaboradores

Funciones:

- Crear reservas
- Editar reservas
- Cancelar reservas
- Consultar disponibilidad
- Consultar ocupación
- Parametrizar salas
- Generar reportes

---

# Pantalla Principal

La pantalla principal será un calendario empresarial.

Distribución:

- Barra superior
- Buscador global
- Filtros rápidos
- Perfil usuario
- Panel lateral de salas
- Calendario central
- Panel de indicadores

Modos:

- Día
- Semana
- Mes
- Timeline
- Agenda

---

# Datos Visibles En Reserva

Cada reserva debe mostrar:

- Nombre de la sala
- Grupo o área
- Descripción corta
- Hora inicio
- Hora fin
- Estado

---

# Colores

- Verde: Aprobada/Reservada
- Azul: En Curso
- Gris: Finalizada
- Rojo: Cancelada
- Naranja: Bloqueada

---

# Tiempo Real

Implementar SignalR.

Eventos:

- Reserva creada
- Reserva modificada
- Reserva cancelada
- Check-In
- Check-Out
- Cambio de estado

Objetivo:

- Actualización menor a 500 ms
- Sin recargar pantalla

---

# Reserva Simplificada

Al seleccionar un bloque horario:

Abrir modal rápido.

Campos:

- Sala
- Grupo
- Descripción
- Fecha
- Hora inicio
- Hora fin
- Observación (opcional)

---

# Motor Inteligente

Funciones:

- Detección de conflictos
- Detección de solapamiento
- Sugerencia de horarios alternativos
- Sugerencia de salas alternativas

Indicador:

- Disponible
- Ocupado

---

# Portal Terminal de Sala

## Objetivo

Permitir que una pantalla física ubicada fuera de la sala consulte y gestione las reservas.

---

# Tecnología Recomendada

```text
Angular 22
+
PWA
+
Capacitor
```

Despliegue:

- Android Tablet
- Smart Display
- Kiosco Digital
- Pantalla táctil
- Aplicación Web

---

# Vista Terminal

Información visible:

- Nombre de la sala
- Estado actual
- Práctica agenda del día
- Próxima reserva
- Tiempo restante

Ejemplo:

```text
SALA A-5

DISPONIBLE

Próxima Reserva
10:00 - 11:00
Comité Comercial
```

---

# Funciones de Terminal

## Reservar Ahora

Opciones:

- 15 minutos
- 30 minutos
- 1 hora
- 2 horas

## Extender Reserva

- +15 minutos
- +30 minutos
- +60 minutos

## Liberar Sala

Permite finalizar antes de tiempo.

## Check-In

Confirmar presencia.

Si nadie hace check-in dentro del tiempo configurado:

- Cancelar reserva.
- Liberar sala.

---

# Código QR

Cada sala debe generar automáticamente un QR.

Permite:

- Ver agenda
- Reservar
- Check-In
- Extender reserva

---

# Calendarios Imprimibles

## Objetivo

Permitir operación sin terminal digital.

## Formatos

- Diario
- Semanal
- Mensual

## Exportación

- PDF
- Impresión directa

---

# Diseño de Impresión

Generar bloques horarios con espacios vacíos para escribir manualmente.

Ejemplo:

```text
SALA A-5

08:00 - 09:00
____________________

09:00 - 10:00
____________________

10:00 - 11:00
____________________
```

Debe soportar modo híbrido mostrando:

- Reservas existentes
- Espacios libres para anotaciones manuales

---

# Roles

## Administrador

- Gestionar salas
- Gestionar usuarios
- Gestionar sedes
- Gestionar reglas
- Ver reportes

## Supervisor

- Consultar ocupación
- Gestionar reservas de su área

## Colaborador

- Crear reservas
- Modificar reservas
- Cancelar reservas

---

# Reportes

- Ocupación por sala
- Horas reservadas
- Utilización por sede
- Salas más usadas
- Tendencias de ocupación
- Cancelaciones

Exportar:

- Excel
- PDF

---

# Dashboard Ejecutivo

Indicadores:

- Salas disponibles
- Salas ocupadas
- Salas bloqueadas
- Porcentaje de ocupación
- Reservas del día
- Reservas por sede
- Horas utilizadas

---

# Seguridad

- JWT
- Refresh Tokens
- RBAC
- MFA opcional
- OWASP Top 10

---

# Rendimiento

- Carga inicial menor a 2 segundos.
- Actualización menor a 500 ms.
- Soporte para mínimo 1.000 usuarios concurrentes.

---

# Resultado Esperado

Construir una plataforma empresarial moderna de reservas de salas basada en autogestión, calendario centralizado, actualización en tiempo real, terminales digitales, códigos QR inteligentes y calendarios imprimibles, preparada para funcionar como producto SaaS empresarial escalable.
