---
layout: default
title: Modelo C4 simplificado
parent: Diagramas y esquemas
nav_order: 2
---

# Modelo de Arquitectura C4 (Simplificado)

La arquitectura de software de la plataforma **SocioUnido** está documentada bajo el estándar del modelo C4. Este enfoque permite visualizar el ecosistema desde distintas capas, garantizando claridad técnica y de negocio.

**Nota:** Esta sección presenta el modelo de arquitectura C4 enfocado en abstracciones visuales simplificadas. Su objetivo es agilizar las revisiones técnicas de alto nivel y facilitar la inducción rápida de nuevos integrantes al flujo de los servicios.

## Nivel 1: Contexto del Sistema

Muestra la interacción de la plataforma con los distintos actores del ecosistema y los servicios externos integrados.

<p align="center">
  <img src="C4 Nivel 1.png" alt="Diagrama C4 Nivel 1: Contexto" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
  <br>
  <em><strong>Figura 1:</strong> Contexto del sistema. Interacción de la plataforma con Socios, Dirigencia, Personal de Control y sistemas externos (Pasarela de Pagos y API de WhatsApp).</em>
</p>

## Nivel 2: Contenedores

Representa una vista de alto nivel de las aplicaciones web, móviles y bases de datos, detallando la distribución de la API Gateway y los microservicios de backend.

<p align="center">
  <img src="C4 Nivel 2.png" alt="Diagrama C4 Nivel 2: Contenedores" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
  <br>
  <em><strong>Figura 2:</strong> Vista de contenedores, lógica basada en microservicios y conectores perimetrales detrás de la puerta de enlace de API.</em>
</p>

## Nivel 3: Componentes de Microservicios

Desglose detallado de la lógica interna, controladores y componentes específicos de cada microservicio del ecosistema.

### 👤 Microservicio de Autenticación (MS Auth)
Sistema centralizado para el manejo seguro de identidades, validación de credenciales y generación de vales web JSON (Tokens JWT).

<p align="center">
  <img src="C4 Nivel 3-MS Auth.png" alt="C4 Nivel 3: MS Auth" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 📋 Microservicio de Gestión Societaria (MS Core)
Encargado de las operaciones de creación, lectura, actualización y borrado (CRUD) de usuarios, perfiles y reglas de negocio del padrón de socios.

<p align="center">
  <img src="C4 Nivel 3-MS Gestion.png" alt="C4 Nivel 3: MS Gestión" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 💵 Microservicio de Pagos (MS Payments)
Estructura responsable de la facturación automatizada, control de cobros recurrentes y comunicación directa con las pasarelas de pago externas.

<p align="center">
  <img src="C4 Nivel 3-MS Payments.png" alt="C4 Nivel 3: MS Payments" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 🤖 Microservicio de Procesamiento de Lenguaje Natural (MS NLP)
Detalle del motor de IA integrado vía retrollamadas web (Webhooks) con la API de WhatsApp para brindar atención automatizada e interactiva a los socios.

<p align="center">
  <img src="C4 Nivel 3-MS NLP.png" alt="C4 Nivel 3: MS NLP" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 🎫 Microservicio de Acceso Inteligente (MS Smart Access)
Componente encargado de la validación matemática fuera de línea (offline) mediante contraseñas temporales de un solo uso (TOTP) para el control de molinetes en estadios.

<p align="center">
  <img src="C4 Nivel 3-MS Smart Access.png" alt="C4 Nivel 3: MS Smart Access" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 📊 Microservicio de Analítica e Inteligencia Artificial (MS Analytics & AI)
Orquestación de flujos asíncronos y modelos predictivos de Machine Learning entrenados para la detección temprana de riesgo de morosidad y abandono.

<p align="center">
  <img src="C4 Nivel 3-MS Analytics & AI.png" alt="C4 Nivel 3: MS Analytics & AI" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 🚪 API Gateway
Punto de entrada unificado basado en KrakenD, encargado de interceptar peticiones, validar tokens JWT, aplicar limitación de tasa (Rate Limiting) y enrutar el tráfico hacia los microservicios correspondientes.

<p align="center">
  <img src="C4 Nivel 3-Gateway.png" alt="C4 Nivel 3: API Gateway" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 💻 Web administrativa (Panel de gestión)
Aplicación frontend orientada al personal del club, que centraliza la administración de socios, disciplinas, reservas e informes, comunicándose de forma segura a través de la API Gateway.

<p align="center">
  <img src="C4 Nivel 3-Web Administrativa.png" alt="C4 Nivel 3: Web Administrativa" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>

### 📱 App del Socio (PWA)
Aplicación Web Progresiva diseñada para el usuario final, con soporte offline, notificaciones push en tiempo real y almacenamiento local para garantizar el acceso rápido al carnet digital y gestión de reservas.

<p align="center">
  <img src="C4 Nivel 3-App Socio.png" alt="C4 Nivel 3: App Socio" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
</p>
