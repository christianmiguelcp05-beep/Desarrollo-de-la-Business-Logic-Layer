# Desarrollo-de-la-Business-Logic-Layer
Understanding
Desarrollar la capa de lógica de negocio completa en SchoolApp.BL para todas las entidades del esquema dbo, siguiendo el patrón de inyección de dependencias. Incluye crear servicios faltantes, repositorios faltantes, registrar dependencias y validar compilación.

Assumptions
SchoolApp.DAL contiene 6 entidades en Models/dbo: Classroom, Course, Enrollment, Student, StudentGrade, Teacher
Algunos repositorios existen (Classroom, Course, Student, Teacher) pero faltan Enrollment y StudentGrade
SchoolApp.BL/Services está vacía y necesita todos los servicios
SchoolApp.BL y Web existen pero están vacíos de código de negocio
No hay servicios existentes que modificar (BL está vacío)
.NET 10 es el target
Approach
Primero haremos un análisis completo (paso 1) para confirmar estado actual de DAL y BL/Services. Luego crearemos los repositorios faltantes siguiendo el patrón base de IRepository y Repository. Después crearemos los 6 servicios (interfaces + implementaciones) en BL/Services. Verificaremos referencias y registraremos todas las dependencias en DependencyInjection.cs de BL. Finalmente compilaremos y validaremos sin errores.

Key Files
SchoolApp.DAL/Models/dbo/* - Entidades (Classroom, Course, Enrollment, Student, StudentGrade, Teacher)
SchoolApp.DAL/Repositories/IRepository.cs - Interfaz base genérica
SchoolApp.DAL/Repositories/Repository.cs - Implementación base genérica
SchoolApp.DAL/DependencyInjection.cs - Registro actual de DAL
SchoolApp.BL/Services/ - Carpeta donde irán todos los servicios (crear)
SchoolApp.BL/DependencyInjection.cs - Registro de servicios BL (crear)
SchoolApp.BL/SchoolApp.BL.csproj - Verificar referencias
SchoolApp.Web/Program.cs - Verificar llamada a setup
Risks & Open Questions
SchoolApp.BL.Tests existe pero no se usará en este trabajo
Validaciones básicas pueden variar, usaremos null checks y rangos simples
Asumimos que todos los repositorios usan el patrón genérico IRepository

Última actualización: 2026-11-03 03:29:07

 Pasos del plan
 Analizar SchoolApp.DAL/Models para confirmar entidades
 Analizar SchoolApp.DAL/Repositories para listar repositorios existentes y faltantes
Crear repositorios faltantes (EnrollmentRepository, IEnrollmentRepository, StudentGradeRepository, IStudentGradeRepository)
Crear carpeta SchoolApp.BL/Services y todos los servicios (6 interfaces + 6 implementaciones)
Verificar referencias entre proyectos y agregar si faltan
 Crear y registrar DependencyInjection.cs en SchoolApp.BL
Verificar que ApplicationSetup.cs en SchoolApp.Web llama al registro
Compilar solución y corregir errores
Generar resumen de cambios
