---
layout: default
title: HealthChecker
parent: Diagramas y esquemas
nav_order: 3
---

# HealthChecker

Este apartado detalla el componente automatizado encargado de monitorear constantemente el estado de salud, la disponibilidad y la latencia de las distintas APIs y microservicios de la plataforma.

## Diagrama de Monitorización Dinámica

Vista de alto nivel del ecosistema de microservicios supervisado por el HealthChecker. Ilustra cómo el componente central se comunica con cada módulo del club para relevar su estado en tiempo real (OK, Degradado, Error).

<p align="center">
  <img src="Grafico Healthchecker.png" alt="Diagrama de Monitorización Dinámica: Healthchecker" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
  <br>
  <em><strong>Figura 1:</strong> Interacción de monitoreo entre el HealthChecker y los microservicios core (NLP, Club, Pagos, Acceso Inteligente, Autenticación y Análisis IA).</em>
</p>

## Modelo C4 Nivel 3: Componentes

Desglose técnico de la lógica interna del servicio de monitoreo.

<p align="center">
  <img src="C4 Nivel 3-Healthchecker.png" alt="C4 Nivel 3: Healthchecker Simplificado" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
  <br>
  <em><strong>Figura 2:</strong> Arquitectura de componentes del Healthchecker. Flujo desde el Task Scheduler y Monitor Engine hasta el HTTP Probe que evalúa los microservicios del sistema.</em>
</p>

## Modelo C4 Nivel 3: Componentes (Simplificado)

Desglose técnico de la lógica interna del servicio de monitoreo.

**Nota:** Esta vista simplificada y optimizada.

<p align="center">
  <img src="C4 Nivel 3-Healthchecker.jpg" alt="C4 Nivel 3: Healthchecker Simplificado" width="100%" style="border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1); margin: 15px 0;">
  <br>
  <em><strong>Figura 2:</strong> Arquitectura de componentes del Healthchecker. Flujo desde el Task Scheduler y Monitor Engine hasta el HTTP Probe que evalúa los microservicios del sistema.</em>
</p>
