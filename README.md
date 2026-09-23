# Influencer Discovery & Matching — M1

Proyecto integrador desarrollado para la carrera de AI Automation Avanzado.

## Descripción

Este workflow implementa la primera versión de un agente de IA especializado en descubrimiento y matching de influencers a partir de una base de datos existente.

El agente recibe solicitudes en lenguaje natural, interpreta los criterios de búsqueda y decide autónomamente cuándo utilizar las herramientas disponibles para obtener y validar la información antes de generar una respuesta.

## Arquitectura

Chat Trigger → AI Agent → Gmail

El AI Agent cuenta con:

- OpenAI Chat Model como modelo de lenguaje.
- Google Sheets como Tool para consultar la base de influencers.
- Code Tool para validar el límite máximo de recomendaciones.
- Gmail como nodo final de observabilidad y supervisión humana.

## Guardrails

- Máximo de 7 iteraciones del AI Agent.
- Máximo de 10 influencers recomendados por solicitud.
- Prohibición de inventar perfiles o información no respaldada por la base de datos.
- Respeto estricto de los criterios explícitos del usuario.
- Uso de la menor cantidad posible de llamadas a herramientas.
- Detención ante información insuficiente en lugar de completar resultados mediante suposiciones.

## Funcionamiento

El agente utiliza un enfoque basado en Tools Agent y decide de forma autónoma cuándo consultar Google Sheets.

La herramienta permite realizar búsquedas dinámicas utilizando criterios como país y categoría. Los resultados obtenidos son evaluados por el agente y posteriormente enviados mediante Gmail como reporte automático de observabilidad.

## Checkpoint 1

Este repositorio contiene el archivo exportado de n8n correspondiente al primer checkpoint:

`checkpoint1_ricardo_andreu.json`

El workflow constituye la base del proyecto integrador y será ampliado en los siguientes módulos.
