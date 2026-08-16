---
layout: default
title: Modelo C4
parent: Diagramas y esquemas
nav_order: 1
---

# Modelo de arquitectura C4

La arquitectura de software de la plataforma **SocioUnido** está documentada bajo el estándar del modelo C4. Este enfoque permite visualizar el ecosistema desde distintas capas, garantizando claridad técnica y de negocio.

## Nivel 1: Contexto del sistema

Muestra la interacción de la plataforma con los distintos actores del ecosistema y los servicios externos integrados.

<p align="center">
  <img src="C4 Nivel 1.png" alt="Diagrama C4 Nivel 1: Contexto" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
  <br>
  <em><strong>Figura 1:</strong> Contexto del sistema. Interacción de la plataforma con socios, dirigencia, personal de control y sistemas externos (pasarela de pagos y API de WhatsApp).</em>
</p>

## Nivel 2: Contenedores

Representa una vista de alto nivel de las aplicaciones web, móviles y bases de datos, detallando la distribución de la API Gateway y los microservicios de backend.

<p align="center">
  <img src="C4 Nivel 2.png" alt="Diagrama C4 Nivel 2: Contenedores" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
  <br>
  <em><strong>Figura 2:</strong> Vista de contenedores, lógica basada en microservicios y conectores perimetrales detrás de la puerta de enlace de API.</em>
</p>

## Nivel 3: Componentes

Desglose detallado de la lógica interna, controladores y componentes específicos de cada microservicio del ecosistema.

### 👤 Microservicio de autenticación

Sistema centralizado para el manejo seguro de identidades, validación de credenciales y generación de vales web JSON (tokens JWT).

<p align="center">
  <img src="C4 Nivel 3-MS Auth.png" alt="C4 Nivel 3: MS Auth" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 📋 Microservicio de gestión societaria
Encargado de las operaciones de creación, lectura, actualización y borrado (CRUD) de usuarios, perfiles y reglas de negocio del padrón de socios.

<p align="center">
  <img src="C4 Nivel 3-MS Gestion.png" alt="C4 Nivel 3: MS Gestión" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 💵 Microservicio de pagos
Estructura responsable de la facturación automatizada, control de cobros recurrentes y comunicación directa con las pasarelas de pago externas.

<p align="center">
  <img src="C4 Nivel 3-MS Payments.png" alt="C4 Nivel 3: MS Payments" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 🤖 Microservicio de procesamiento de lenguaje natural
Detalle del motor de IA integrado vía retrollamadas web (webhooks) con la API de WhatsApp para brindar atención automatizada e interactiva a los socios.

<p align="center">
  <img src="C4 Nivel 3-MS NLP.png" alt="C4 Nivel 3: MS NLP" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 🎫 Microservicio de acceso inteligente
Componente encargado de la validación matemática fuera de línea (offline) mediante contraseñas temporales de un solo uso (TOTP) para el control de molinetes en estadios.

<p align="center">
  <img src="C4 Nivel 3-MS Smart Access.png" alt="C4 Nivel 3: MS Smart Access" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 📊 Microservicio de analíticas e inteligencia artificial
Orquestación de flujos asíncronos y modelos predictivos de machine learning entrenados para la detección temprana de riesgo de morosidad y abandono.

<p align="center">
  <img src="C4 Nivel 3-MS Analytics & AI.png" alt="C4 Nivel 3: MS Analytics & AI" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 🚪 API Gateway
Punto de entrada unificado basado en KrakenD, encargado de interceptar peticiones, validar tokens JWT, aplicar limitación de tasa (rate limiting) y enrutar el tráfico hacia los microservicios correspondientes.

<p align="center">
  <img src="C4 Nivel 3-Gateway.png" alt="C4 Nivel 3: API Gateway" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 🩺 HealthChecker
Servicio dedicado al monitoreo continuo del estado de salud y disponibilidad (uptime) de los microservicios y bases de datos del ecosistema, alertando ante posibles caídas y facilitando la observabilidad del sistema.

<p align="center">
  <img src="C4 Nivel 3- Healthchecker.png" alt="C4 Nivel 3: Healthchecker" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 💻 Web administrativa (panel de gestión)
Aplicación frontend orientada al personal del club, que centraliza la administración de socios, disciplinas, reservas e informes, comunicándose de forma segura a través de la API Gateway.

<p align="center">
  <img src="C4 Nivel 3-Web Administrativa.png" alt="C4 Nivel 3: Web Administrativa" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 📱 App del socio (PWA)
Aplicación web progresiva diseñada para el usuario final, con soporte offline, notificaciones push en tiempo real y almacenamiento local para garantizar el acceso rápido al carnet digital y gestión de reservas.

<p align="center">
  <img src="C4 Nivel 3-App Socio.png" alt="C4 Nivel 3: App Socio" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 💼 App del empleado (PWA)
Aplicación web progresiva orientada al personal operativo y de campo del club. Facilita el seguimiento de operaciones cotidianas, gestión de tareas y comunicación interna, apoyándose en la infraestructura central.

<p align="center">
  <img src="C4 Nivel 3- App Empleados.png" alt="C4 Nivel 3: App Empleados" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

## Nivel 4: Código

En la industria actual, la diagramación estática de este nivel ha sido prácticamente discontinuada (*outphased*). Simon Brown, creador del modelo C4, establece explícitamente que este nivel es **opcional**. 

La alta variabilidad del código moderno, sumado a la velocidad de despliegue impulsada por los modernos sistemas de integración y entrega continua (CI/CD), provoca que cualquier diagrama de código hecho manualmente sufra de "decadencia de documentación" (*documentation decay*) casi de inmediato, volviéndose obsoleto y excesivamente costoso de mantener .

Por esta razón, la práctica estándar y las recomendaciones oficiales indican que, de requerirse este nivel de detalle (como diagramas de clases UML o flujos de secuencia), el mismo debe ser **generado automáticamente** bajo demanda mediante Entornos de Desarrollo Integrado (IDE) o herramientas especializadas que conectan con repositorios directamente desde el código fuente . Hoy en día, la mayoría de los equipos de ingeniería prefieren omitir este esfuerzo manual y apoyarse en la navegación del código y grafos de dependencia generados dinámicamente en el entorno de desarrollo .

**Por todo lo expuesto, hemos optado por no realizar la diagramación manual de este nivel, alineándonos con los lineamientos y las mejores prácticas modernas de la industria del software.**

***

**Fuentes de consulta y fundamentación técnica sobre el Nivel 4:**
* [Visual Paradigm: "What is the C4 Model?"](https://www.visual-paradigm.com/guide/what-is-the-c4-model-a-comprehensive-guide-to-visualizing-software-architecture/) 
* [Draw.io / C4 Model Guide: "Because this level often represents implementation details, ideally it is automatically generated..."](https://drawio-app.com/blog/c4-model-draw-io-for-confluence/) 
* [C4 Model Docs (Simon Brown)](https://c4model.com/)
