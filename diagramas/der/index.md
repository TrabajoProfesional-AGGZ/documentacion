---
layout: default
title: Diagramas Entidad-Relación
parent: Diagramas y esquemas
nav_order: 3
---

# Diagramas Entidad-Relación (DER)

La persistencia del ecosistema de **SocioUnido** sigue un enfoque descentralizado mediante bases de datos aisladas por microservicio, asegurando la escalabilidad operativa, la consistencia de datos y el principio de responsabilidad única.

A continuación, se detallan las estructuras del modelo relacional para los repositorios de datos principales:

## 📋 Base de Datos de Gestión Societaria (MS Core)

Este esquema relacional centraliza el padrón maestro del club deportivo. Administra la información de contacto de los socios, la asignación de categorías, el control de roles administrativos internos de la dirigencia y las reglas de negocio esenciales de la institución.

<p align="center">
  <img src="MS Core - Database.png" alt="DER del Microservicio Core" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
  <br>
  <em><strong>Esquema 1:</strong> Modelo lógico de datos encargado del control de identidad, categorías societarias y perfiles del padrón.</em>
</p>

## 💵 Base de Datos de Finanzas y Facturación (MS Payments)

Esquema especializado en registrar transacciones monetarias. Controla los estados de las facturaciones mensuales, la generación de comprobantes, el historial de pagos efectuados y las firmas de integración con las pasarelas de pago digitales externas.

<p align="center">
  <img src="MS Payments - Database.png" alt="DER del Microservicio de Pagos" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
  <br>
  <em><strong>Esquema 2:</strong> Modelo de persistencia para el control transaccional, vencimientos de cuotas y conciliación financiera.</em>
</p>

## 📊 Base de Datos de Analítica Predictiva (MS Analytics & AI)

Modelo optimizado para la recopilación histórica de métricas de comportamiento e interacciones. Estructura los conjuntos de datos limpios necesarios para nutrir las tareas asíncronas y los algoritmos predictivos que alertan sobre posibles tendencias de morosidad.

<p align="center">
  <img src="MS Analytics & AI - Database.png" alt="DER del Microservicio de Analítica e IA" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
  <br>
  <em><strong>Esquema 3:</strong> Almacenamiento estructurado para logs analíticos, métricas predictivas e históricos de entrenamiento de modelos.</em>
</p>
