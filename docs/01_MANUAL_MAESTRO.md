# Manual Maestro HDP Platform

## 1. Visión

HDP Platform es una plataforma ágil para la creación, despliegue y mantenimiento de aplicaciones modernas. Nuestra misión es acelerar la entrega de software confiable mediante automatización y componentes reutilizables. La visión es ser la base técnica ligera y robusta sobre la que construir productos rápidamente, manteniendo calidad y observabilidad desde el primer commit. El objetivo principal es reducir el tiempo desde la idea hasta la producción mediante plantillas, automatizaciones y prácticas reproducibles. Entendemos la plataforma como una Software Factory: un conjunto de herramientas, plantillas y procesos que convierten requisitos en entregables de forma predecible y repetible.

## 2. Filosofía

Las decisiones clave las toman las personas con contexto del producto. La IA (y herramientas automáticas) acelera la implementación y reduce trabajo repetitivo escribiendo código, pruebas y sugerencias. La automatización conecta las piezas del flujo de trabajo (CI/CD, pruebas, despliegue). El software es reutilizable: preferimos componentes y librerías internas sobre copia/pega. La arquitectura es modular: cada módulo tiene responsabilidad clara y API estable. Todo cambio debe favorecer velocidad sin sacrificar trazabilidad ni calidad técnica.

## 3. Equipo Oficial

CEO  
El CEO define la dirección estratégica y prioriza objetivos del negocio; mantiene alineamiento entre producto y recursos técnicos.

CTO (ChatGPT)  
El CTO provee la visión técnica, valida decisiones arquitectónicas y actúa como asesor en soluciones, trade-offs y adopción de tecnologías.

GitHub Copilot  
Copilot asiste a desarrolladores generando código, pruebas y sugerencias dentro del flujo de desarrollo, incrementando productividad y uniformidad.

GitHub  
Plataforma central de control de versiones, revisiones y gestión de ramas; orquesta acciones, PRs y revisiones de código.

Android Studio  
IDE principal para desarrollo móvil Android y para aprovechar emuladores, herramientas de depuración y perfiles de rendimiento.

PowerShell  
Herramienta de scripting y automatización para entornos Windows y pipelines híbridos; útil en tareas locales y CI donde se requiera scripting reproducible.

## 4. Metodología Oficial

Flujo oficial: idea → arquitectura → blueprint técnico (BI) → GitHub Copilot → repositorio → compilación → pruebas → producción.

- Idea: captura mínima y clara del valor entregable.
- Arquitectura: diseño técnico ligero que define límites, integraciones y riesgos.
- Technical Blueprint (BI): documento breve que especifica alcance, criterios de aceptación, APIs y estructura del repositorio.
- GitHub Copilot: genera scaffolding y propuestas de implementación a partir del BI.
- Repository: código fuente organizado según la estructura estándar de la plataforma.
- Compilación: builds automatizados reproducibles en CI.
- Testing: pruebas unitarias, integración y end-to-end automatizadas.
- Production: despliegue automatizado con rollback y observabilidad.

Cada paso está orientado a iteraciones rápidas y feedback temprano; las tareas manuales se automatizan cuando aportan repetibilidad o ahorro de tiempo.

## 5. Principios

- Código reutilizable: preferir librerías y paquetes internos.
- No duplicar código: una funcionalidad, un lugar.
- Configuración sobre hardcoding: parámetros en archivos o variables de entorno.
- Modularidad: módulos con responsabilidad única y contrato público (API).
- Automatización de tareas repetitivas: CI, despliegue, generación y pruebas.

## 6. Official Technologies

Nx  
Monorepo toolkit para organizar aplicaciones y paquetes con tareas coordenadas, caching y generación de código. Facilita el desarrollo de monorepos escalables.

NestJS  
Framework backend en Node.js con arquitectura modular y inyección de dependencias; claro para APIs REST/GraphQL y fácil de testear.

Flutter  
SDK UI para multiplataforma (iOS/Android/web) que permite compartir lógica y acelerar prototipos y productos móviles con rendimiento nativo.

Next.js  
Framework React para aplicaciones web con rendering híbrido (SSR/SSG) y rutas óptimas; ideal para frontends rápidos y SEO cuando aplica.

Prisma  
ORM moderno para TypeScript que facilita modelado, migraciones y consultas tipadas de bases de datos SQL.

PostgreSQL  
Base de datos relacional robusta y extensible; se utiliza como fuente principal de persistencia para datos transaccionales.

Redis  
Almacenamiento en memoria para caching, colas simples y sesiones; mejora latencia y escalabilidad de componentes críticos.

Supabase  
Backend-as-a-Service sobre PostgreSQL que ofrece autenticación, base de datos y storage con APIs listas para integrar.

Docker  
Contenerización para entornos reproducibles de desarrollo, testing y producción; estandariza imágenes y despliegues.

GitHub Actions  
Plataforma CI/CD integrada para automatizar compilaciones, tests y despliegues mediante workflows versionados.

## 7. Repository Structure

- apps/  
  Aplicaciones finales (frontend, backend, mobile). Cada app es autónoma dentro del monorepo.

- packages/  
  Paquetes reutilizables (UI components, utils, domain libraries) que consumen apps y servicios.

- services/  
  Microservicios o APIs independientes que pueden desplegarse por separado.

- templates/  
  Plantillas y blueprints para generar nuevas apps o paquetes con estándares del proyecto.

- docs/  
  Documentación oficial, manuales y blueprints (aquí va 01_MANUAL_MAESTRO.md).

- scripts/  
  Scripts reutilizables para dev, migraciones y tareas operativas.

- tools/  
  Herramientas internas y utilidades CLI para mantenimiento y generación.

- ai/  
  Blueprints y prompts oficiales para IA (Copilot / ChatGPT) y artefactos generados automáticamente.

Cada carpeta contiene README corto con convenciones, comandos y ejemplos mínimos.

## 8. BI Methodology

¿Qué es un BI?  
BI (Blueprint Técnico) es un documento técnico conciso que transforma una idea en instrucciones precisas para implementación y automatización. Es la especificación mínima viable que garantiza que cualquier desarrollador o IA pueda producir código alineado con la visión y criterios de aceptación.

Secciones típicas de un BI:
- Objetivo: qué se va a entregar y por qué.
- Alcance: límites, lo que queda IN y OUT.
- Backend: servicios, endpoints, flujos y dependencias.
- Frontend: pantallas, rutas, estados críticos y componentes clave.
- Base de datos: modelos, migraciones y restricciones.
- API: contratos, formatos y ejemplos de request/response.
- Automatización: jobs, triggers, CI/CD y despliegues.
- Testing: tipos de pruebas requeridas y criterios mínimos.
- Criterios de aceptación: lista clara de condiciones verificables para aprobar la entrega.

Un BI debe ser conciso (1–3 páginas), con ejemplos y endpoints mínimos. Sirve como entrada para generar scaffolding y tareas automatizadas.

## 9. Definition of Done

Un módulo se considera completado cuando:
- Código implementado y committeado en la rama correspondiente.
- Tests unitarios y de integración relevantes pasan en CI.
- Linter y formateo pasan.
- Documentación mínima (README, configuración) incluida.
- Migraciones y cambios de DB acompañados por scripts reproducibles.
- Pipeline de despliegue o manifest actualizado y probado en entorno de staging.
- Criterios de aceptación del BI cumplen en pruebas automatizadas o manuales.
- Pull Request con descripción clara, checklist y evidencia de pruebas aprobado y mergeado.

## 10. Roadmap

- Infraestructura: definir pipeline, observabilidad, recursos de CI y deployment patterns.
- Core: construir las piezas centrales (autenticación, modelos compartidos, utilities).
- Módulos Reusables: componentes UI, librerías de lógica y servicios compartidos.
- Marketplace: catálogo interno de módulos y plantillas consumibles por equipos.
- Generador de Aplicaciones: herramienta que crea scaffolding estándar a partir de un BI.

Anclar entregables a hitos cortos y medibles, priorizando lo que reduce tiempo de entrega o aumenta reutilización.

---

Apéndice: Comandos Git sugeridos (ejecución tras autorización)

- Crear rama:
  git checkout -b docs/manual-maestro

- Añadir archivo:
  mkdir -p docs
  # crear docs/01_MANUAL_MAESTRO.md con este contenido
  git add docs/01_MANUAL_MAESTRO.md

- Commit:
  git commit -m "docs: add Master Manual v1"

- Push y abrir PR:
  git push -u origin docs/manual-maestro
  (Abrir PR hacia main con título "docs: add Master Manual v1" y descripción resumida del cambio.)
