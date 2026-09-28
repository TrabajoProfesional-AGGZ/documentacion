---
layout: default
title: Validación del producto
nav_order: 7
---

# Validación del producto

En esta sección se documentan las entrevistas, sesiones de testeo inicial y charlas de retroalimentación llevadas a cabo con trabajadores de los clubes y usuarios potenciales de **SocioUnido**.

El objetivo principal de estas instancias es **validar la UX/UI, evaluar la usabilidad de la aplicación y corroborar el valor agregado** de las soluciones propuestas frente a las necesidades reales del día a día en las instituciones deportivas.

## Entrevistas y sesiones de Feedback

A continuación, se presentan los registros audiovisuales y resúmenes de los encuentros realizados para contrastar el desarrollo de la plataforma con el testimonio de sus futuros usuarios.

### Club Atlético Talleres (Remedios de Escalada)

* **Entrevistado:** Martín Fernando Rubino
* **Rol / relación con el club:** Trabajador de la institución
* **Foco del encuentro:** Realizar un primer análisis de las funcionalidades diseñadas para el club, detección de puntos de dolor y relevamiento de primeras impresiones sobre la propuesta de valor de **SocioUnido**.

#### Registro audiovisual de la entrevista

<div style="margin-top: 25px; width: 100%; text-align: center;">
    <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
        <iframe 
            src="https://www.youtube.com/embed/9hek6PtsLIw" 
            style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none;" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
            allowfullscreen>
        </iframe>
    </div>
</div>

## Entrevistas de UX/UI con usuarios finales

Para masificar el feedback sobre el diseño y la usabilidad de la aplicación, realizamos un relevamiento mediante un formulario con distintos usuarios de prueba. A continuación, se presentan los resultados analíticos, que se alimentan de nuestra base de datos estática a medida que ingresan nuevas respuestas.

<script src="https://cdn.jsdelivr.net/npm/papaparse@5.4.1/papaparse.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script src="https://cdn.jsdelivr.net/npm/chartjs-plugin-datalabels@2.0.0"></script>

<div style="background-color: #f8f9fa; padding: 15px; border-radius: 8px; margin-bottom: 20px; border-left: 5px solid #28a745;">
    <h3 style="margin-top: 0; color: #333;">Dashboard Completo de Resultados UX/UI</h3>
    <p id="total-respuestas" style="font-weight: bold; font-size: 1.1em; margin-bottom: 0;">Cargando respuestas...</p>
</div>

<div id="dashboard-container"></div>

<script>
document.addEventListener("DOMContentLoaded", function() {
    Chart.register(ChartDataLabels);
    const csvUrl = 'respuestas.csv';

    function formatearTitulo(texto, maxCaracteresPorLinea) {
        const palabras = texto.split(' ');
        const lineas = [];
        let lineaActual = '';
        
        palabras.forEach(palabra => {
            if ((lineaActual + palabra).length > maxCaracteresPorLinea) {
                lineas.push(lineaActual.trim());
                lineaActual = palabra + ' ';
            } else {
                lineaActual += palabra + ' ';
            }
        });
        if (lineaActual.trim()) lineas.push(lineaActual.trim());
        return lineas;
    }

    Papa.parse(csvUrl, {
        download: true,
        header: true,
        skipEmptyLines: true,
        complete: function(results) {
            const data = results.data.filter(row => row['Marca temporal']); 
            document.getElementById('total-respuestas').innerText = "Total de encuestas de UX completadas: " + data.length;

            const secciones = {
                "1. Demografía de los Testers": [
                    '¿Quién te mandó esta encuesta?', 'Edad', 'Género', '¿Estudiás y/o trabajás?', 'Qué área define mejor a tu campo de estudio/trabajo'
                ],
                "2. Checkpoints Generales": [
                    '¿Pudiste realizar todos los checkpoints de tareas? ', 
                    'Si la respuesta anterior fue no, ¿cuál/es tarea/s no pudiste cumplir? ¿Por qué?'
                ],
                "3. Crear Cuenta": [
                    '¿Pudiste realizar esta tarea?', 'Del 1 al 5, ¿qué tan dificil te pareció?', 'El formulario te pareció', 'La cantidad de datos a ingresar te pareció', 'Comentarios extra'
                ],
                "4. Cambio de Contraseña": [
                    '¿Pudiste encontrar esta tarea?', '¿El sistema te rechazó algun intento de contraseña?', 'Si la respuesta fue sí, ¿entendiste la razón del rechazo?', 'Comentarios extra 2'
                ],
                "5. Reservas": [
                    '¿Pudiste realizar alguna reserva en la aplicación?', '¿El sistema te rechazó alguna reserva?', 'Si la respuesta anterior fue sí, ¿el mensaje del sistema fue claro para entender el problema?', '¿Cuál fue el problema que tuviste? ¿Lo pudiste resolver?', 'El formulario de reserva, te pareció', '¿Pudiste ver tus reservas confirmadas, pendientes, canceladas e históricas?', '¿Pudiste cancelar una reserva? ¿Te pareció fácil?', 'Comentarios extra 3'
                ],
                "6. Inscripción a Actividades": [
                    '¿Pudiste anotarte a alguna actividad?', '¿Intentaste inscribirte a alguna actividad que no sea para tu categoría de socio?', '¿Si la respuesta anterior fue sí, te parece que la aplicación informa claramente la razón por la cuál no se pudo realizar la inscripción?', '¿Pudiste ver tus inscripciones desde la aplicación?', '¿Pudiste darte de baja de una inscripción? ¿Te pareció fácil?', 'Comentarios extra 4'
                ],
                "7. Eventos": [
                    '¿Pudiste encontrar la sección de compra de entradas para eventos?', '¿Pudiste reservar y pagar tu entrada para un evento?', 'Como socio, ¿te parece útil poder reservar entradas para eventos de tu club desde la aplicación?', 'Como socio, ¿te sirve poder pagar las entradas para los eventos desde la aplicación?', '¿Pudiste encontrar tus entradas dentro de la aplicación?', 'Comentarios extra 5'
                ],
                "8. Tienda": [
                    '¿Encontraste la tienda del club?', '¿Pudiste realizar una compra de algún producto?', 'Como socio, ¿te parece útil poder ver y comprar productos del club desde la aplicación?', 'La vista de los productos te pareció', 'Comentarios extra 6'
                ],
                "9. Noticias y Alertas": [
                    '¿Pudiste consultar la sección de noticias del club?', '¿Pudiste encontrar la sección de alertas? ', '¿Qué tan díficil te pareció encontrar las alertas?', '¿Considerás que es necesario tener una sección de alertas y una de noticias por separado?', 'Comentarios'
                ],
                "10. Pagos": [
                    '¿Pudiste realizar el pago de cuotas en la aplicación para regularizar el estado financiero?', '¿Cuál es tu opinión sobre la posibilidad de realizar pagos de las cuotas y regularizar el estado financiero desde la aplicación?', '¿Qué opinas de MercadoPago como sistema de gestión de pagos en la aplicación?', 'Qué te pareció el flujo de pagos dentro de la aplicación'
                ],
                "11. Diseño General de la Aplicación": [
                    'Valoración general de la aplicación', 'Valoración estética de la aplicación', 'Valoración de experiencia de uso (animaciones, errores, etc.)', 'Los colores, logotipos y escudos utilizados para la aplicación fueron los del Inter Miami CF. Esto fue una decisión de diseño para mantener la neutralidad ante posibles fanatismos, evitando usar colores característicos de clubes del fútbol argentino que puedan generar mala predisposición en fanáticos de equipos rivales. ¿Qué te pareció la elección del Inter Miami CF como club para la demo?', '¿Te pareció que las funcionalidades estaban correctamente divididas y asignadas a sus páginas?', 'Desde un punto de vista estético, el diseño de la aplicación te pareció', 'Si tu respuesta anterior fue desagradable o que hay cosas para mejorar, ¿qué cambiarías?', 'La información mostrada en la aplicación te pareció', 'En general, los errores y avisos dentro de la aplicación fueron informados', 'Comentarios extra sobre diseño de la aplicación y experiencia de uso'
                ]
            };

            const container = document.getElementById('dashboard-container');
            let chartIdCounter = 0;

            const colores = ['#4e79a7', '#f28e2c', '#e15759', '#76b7b2', '#59a14f', '#edc949', '#af7aa1', '#ff9da7', '#9c755f', '#bab0ab'];

            Object.keys(secciones).forEach(seccion => {
                const sectionDiv = document.createElement('div');
                sectionDiv.innerHTML = `<h3 style="border-bottom: 2px solid #ddd; padding-bottom: 5px; margin-top: 40px; color: #2c3e50;">${seccion}</h3>`;
                const gridDiv = document.createElement('div');
                gridDiv.style = "display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px;";
                
                const comentariosList = [];

                secciones[seccion].forEach(pregunta => {
                    let freq = {};
                    let esComentario = false;

                    data.forEach(row => {
                        const val = row[pregunta];
                        if (val && val.trim() !== "") {
                            freq[val] = (freq[val] || 0) + 1;
                        }
                    });

                    const uniqueKeys = Object.keys(freq);
                    if (pregunta.toLowerCase().includes('comentario') || pregunta.toLowerCase().includes('por qué') || pregunta.toLowerCase().includes('cambiarías') || pregunta.toLowerCase().includes('problema que tuviste')) {
                        esComentario = true;
                    }

                    if (esComentario) {
                        uniqueKeys.forEach(k => comentariosList.push(`<strong>${pregunta.length > 50 ? 'Respuesta' : pregunta}:</strong> ${k}`));
                    } else if (uniqueKeys.length > 0) {
                        chartIdCounter++;
                        const canvasId = `chart-${chartIdCounter}`;
                        const chartWrapper = document.createElement('div');
                        chartWrapper.style = "padding: 20px; background: #fff; border: 1px solid #e1e4e8; border-radius: 8px; box-shadow: 0 1px 3px rgba(0,0,0,0.05); display: flex; flex-direction: column; align-items: center; justify-content: center;";
                        chartWrapper.innerHTML = `<canvas id="${canvasId}" style="width: 100%; min-height: 280px;"></canvas>`;
                        gridDiv.appendChild(chartWrapper);

                        let titleText = formatearTitulo(pregunta, 45);

                        setTimeout(() => {
                            new Chart(document.getElementById(canvasId), {
                                type: 'doughnut',
                                data: {
                                    labels: Object.keys(freq),
                                    datasets: [{
                                        data: Object.values(freq),
                                        backgroundColor: colores,
                                        borderWidth: 1
                                    }]
                                },
                                options: {
                                    responsive: true,
                                    maintainAspectRatio: false,
                                    layout: {
                                        padding: {
                                            top: 10,
                                            bottom: 10
                                        }
                                    },
                                    plugins: {
                                        title: { 
                                            display: true, 
                                            text: titleText, 
                                            font: { size: 13, weight: 'normal' },
                                            padding: { bottom: 20 }
                                        },
                                        legend: { 
                                            display: true, 
                                            position: 'bottom', 
                                            labels: { 
                                                boxWidth: 12,
                                                font: { size: 11 }
                                            } 
                                        },
                                        datalabels: {
                                            color: '#fff',
                                            font: { weight: 'bold' },
                                            formatter: (value, ctx) => { return value; }
                                        }
                                    }
                                }
                            });
                        }, 100);
                    }
                });

                sectionDiv.appendChild(gridDiv);

                if (comentariosList.length > 0) {
                    const commentsDiv = document.createElement('div');
                    commentsDiv.style = "background: #f8f9fa; padding: 15px; border-radius: 8px; margin-top: 20px; border-left: 4px solid #6c757d;";
                    let ulHTML = `<h4 style="margin-top:0; color: #495057;">Comentarios y observaciones</h4><ul style="font-size: 0.9em; color: #444; margin-bottom: 0; padding-left: 20px;">`;
                    comentariosList.forEach(com => {
                        ulHTML += `<li style="margin-bottom: 10px; line-height: 1.4;">${com}</li>`;
                    });
                    ulHTML += `</ul>`;
                    commentsDiv.innerHTML = ulHTML;
                    sectionDiv.appendChild(commentsDiv);
                }

                container.appendChild(sectionDiv);
            });
        },
        error: function(err) {
            console.error("Error cargando el CSV:", err);
            document.getElementById('total-respuestas').innerText = "Hubo un error cargando los datos.";
        }
    });
});
</script>
