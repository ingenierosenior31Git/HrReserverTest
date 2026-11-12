# PROMPT MAESTRO ENTERPRISE V3
# CRM COMERCIAL + GESTIÓN DE FLOTA + APP MÓVIL + ROLES DINÁMICOS + DOCUMENTACIÓN DOCUSAURUS

## VISIÓN GENERAL

Diseñar y desarrollar una plataforma SaaS empresarial para compañías de mensajería, logística, distribución y transporte.

La plataforma deberá combinar:

- CRM Comercial.
- Gestión de Clientes.
- Gestión de Contratos.
- Gestión de Cotizaciones.
- Gestión de Flota.
- Gestión de Conductores.
- Gestión de Mantenimientos.
- Gestión Documental.
- Dashboard Ejecutivo.
- App Móvil para Conductores.
- Multiempresa (Multi Tenant).
- Roles Dinámicos.
- Auditoría Integral.
- IA preparada para futuras integraciones.

Principios:

- Máxima facilidad de uso.
- Mínima digitación manual.
- Configuración sin desarrollo.
- Arquitectura escalable.
- Seguridad empresarial.

---

# STACK TECNOLÓGICO

## Frontend

- Angular (última versión estable).
- Standalone Components.
- Signals.
- Bootstrap 5.
- Angular Material.
- Lazy Loading.
- PWA.
- Dark Mode.
- Internacionalización.
- Clean Architecture Frontend.

## Backend

- ASP.NET Core (.NET LTS vigente).
- Clean Architecture.
- Onion Architecture.
- CQRS.
- MediatR.
- DDD.
- Repository Pattern.
- Unit Of Work.
- REST API.
- OpenAPI.

## App Móvil

- .NET MAUI.
- Android.
- iOS.
- Offline First.
- Sincronización automática.

## Base de Datos

Motor inicial:

- PostgreSQL.

Arquitectura preparada para migrar posteriormente a:

- SQL Server.
- MySQL.
- MariaDB.
- Oracle.
- Azure SQL.

Usar:

- Entity Framework Core.
- Fluent API.
- Migrations.

Ninguna regla de negocio deberá depender del proveedor de base de datos.

---

# AUTENTICACIÓN Y SEGURIDAD

- JWT.
- Refresh Tokens.
- MFA.
- OAuth2.
- OpenID Connect.
- Control granular de permisos.
- Auditoría completa.
- OWASP Top 10.

---

# MULTIEMPRESA

Cada empresa contará con:

- Usuarios propios.
- Vehículos propios.
- Conductores propios.
- Clientes propios.
- Datos aislados.
- Configuración independiente.

---

# ROLES DINÁMICOS

El sistema NO tendrá roles fijos.

El administrador podrá:

- Crear roles personalizados.
- Clonar roles.
- Activar o desactivar roles.
- Asignar permisos.
- Definir accesos por módulo.

Permisos:

- Ver.
- Crear.
- Editar.
- Eliminar.
- Aprobar.
- Rechazar.
- Exportar.
- Administrar.

## Recomendaciones Inteligentes

Cuando el administrador cree un nuevo rol el sistema sugerirá automáticamente permisos y módulos recomendados según el nombre y tipo del cargo.

---

# CRM COMERCIAL

## Prospectos

Estados:

- Prospecto.
- Contactado.
- Negociación.
- Cotización.
- Ganado.
- Perdido.

## Pipeline Comercial

Vista Kanban.

## Agenda Comercial

- Llamadas.
- Visitas.
- Reuniones.
- Seguimientos.

## Cotizaciones

- Tarifas por peso.
- Tarifas por volumen.
- Tarifas por zona.
- Tarifas especiales.

## Contratos

- Contratos.
- Otrosí.
- Pólizas.
- Acuerdos comerciales.

---

# GESTIÓN DE FLOTA

## Vehículos

- Placa.
- Marca.
- Modelo.
- Año.
- Capacidad.
- Estado.

## Conductores

- Documento.
- Licencia.
- Vencimientos.
- Contactos.

## Mantenimiento

- Preventivo.
- Correctivo.
- Predictivo.

## Combustible

- Control de consumo.
- Control de costos.
- Rendimiento por kilómetro.

## Documentación

- SOAT.
- Seguros.
- Tecnomecánica.
- Permisos.

---

# APP MÓVIL PARA CONDUCTORES

## Principios

- Máximo 30 segundos por operación.
- Formularios mínimos.
- Botones grandes.
- Fotografía rápida.
- Dictado por voz.

## Inicio de Jornada

- Kilometraje inicial.
- Foto del vehículo.
- Checklist.

## Registro de Combustible

- Foto factura.
- OCR.
- Validación rápida.

## Novedades

- Accidente.
- Retraso.
- Avería.
- Tráfico.
- Otro.

## Fin de Jornada

- Kilometraje final.
- Evidencia fotográfica.
- Observaciones opcionales.

---

# DASHBOARD EJECUTIVO

Indicadores:

- Ventas.
- Conversión.
- Utilidad.
- Disponibilidad de flota.
- Costos operativos.
- Consumo de combustible.
- Mantenimientos.
- Incidentes.

---

# STORAGE

Seleccionable mediante configuración:

- Azure Blob Storage.
- Amazon S3.
- MinIO.
- Almacenamiento Local.

Implementar patrón Strategy.

---

# AUDITORÍA

Registrar:

- Usuario.
- Fecha.
- Dirección IP.
- Acción ejecutada.
- Registro afectado.

---

# INTELIGENCIA ARTIFICIAL (FASE FUTURA)

- Predicción de mantenimiento.
- Predicción de fuga de clientes.
- Recomendación de acciones comerciales.
- Detección de anomalías de combustible.
- Asistente virtual operativo.

---

# POLÍTICA DE CÓDIGO

## Código Sin Comentarios

No utilizar:

- Comentarios de línea.
- Comentarios de bloque.
- Código comentado.

El código deberá ser autoexplicativo mediante:

- Naming semántico.
- SOLID.
- Clean Code.
- Responsabilidad única.

---

# DOCUMENTACIÓN OBLIGATORIA

## Docusaurus

Toda la documentación deberá construirse usando Docusaurus.

Ninguna funcionalidad se considerará terminada sin documentación actualizada.

## Contenido de la Documentación

- Arquitectura.
- Backend.
- Frontend.
- API.
- Seguridad.
- Base de Datos.
- CRM.
- Flota.
- App Móvil.
- Roles y Permisos.
- Despliegue.
- FAQ.

## Diagramas

Generar diagramas Mermaid para:

- Arquitectura.
- Casos de uso.
- Flujos de negocio.
- Procesos operativos.

---

# DEVOPS

- Docker.
- Kubernetes Ready.
- CI/CD.
- SonarQube.
- Health Checks.
- Logs centralizados.
- Versionamiento Git.

---

# CALIDAD

- Cobertura mínima de pruebas: 85%.
- Unit Testing.
- Integration Testing.
- Validaciones automáticas.
- Revisión estática de código.

---

# ENTREGABLES

- Código fuente.
- Scripts de base de datos.
- Docker.
- Swagger/OpenAPI.
- Documentación Docusaurus.
- Diagramas Mermaid.
- Manual de usuario.
- Manual técnico.
- Manual de despliegue.

---

# RESULTADO ESPERADO

Construir una plataforma empresarial moderna, escalable y altamente configurable que combine CRM Comercial, Gestión de Flota, Aplicación Móvil para Conductores, Roles Dinámicos, Seguridad Empresarial, Multiempresa y Documentación Profesional, preparada para evolucionar hacia un ERP logístico completo para empresas de mensajería y transporte.
