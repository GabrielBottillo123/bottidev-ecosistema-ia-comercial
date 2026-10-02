# Ecosistema IA Comercial - BOTTIDEV

Proyecto final del curso AI Automation.

El sistema automatiza la generación, revisión y envío de propuestas comerciales para BOTTIDEV utilizando inteligencia artificial y Human-in-the-loop.

## Tecnologías

- n8n — orquestación del workflow
- Airtable — base de datos y dashboard
- OpenAI GPT-5.6 Luna — generación de propuestas
- Gmail — aprobación humana y envío al cliente

## Flujo

Airtable Leads  
→ Validación de datos  
→ Generación de propuesta con IA  
→ Registro en Airtable  
→ Human-in-the-loop por Gmail  
→ Aprobación o rechazo  
→ Envío al cliente  
→ Actualización final y trazabilidad

El sistema también incluye rutas específicas para datos incompletos y errores del agente IA.

## Seguridad y resiliencia

- Validación previa de Email y Necesidad
- Filtro anti-loop mediante Estado = Pendiente IA
- Retry On Fail
- Registro de errores con Execution ID
- Human-in-the-loop antes del envío
- Thread ID de Gmail para trazabilidad
- Workflow público sanitizado sin credenciales privadas

## Dashboard

Dashboard público de Airtable:

https://airtable.com/app2m4kFYu3sIxysj/shr4CxNc85xkAypDq/tblNzMc1pYDfW1IBD/viw9dwJ43FJ4lrsnj

KPIs obtenidos en las pruebas:

- Tasa de aprobación: 66,7%
- Volumen de salida: 2
- Tasa de error: 40%

## Base de datos

Vista pública en modo lectura:

https://airtable.com/app2m4kFYu3sIxysj/shr4CxNc85xkAypDq/tblNzMc1pYDfW1IBD/viwLUWvQREjd2OdiQ

## Archivos

- `Ecosistema IA Comercial - BOTTIDEV - SANITIZADO.json`: workflow exportado de n8n.
- `Arquitectura-Ecosistema-IA-BOTTIDEV.pdf`: mapa de arquitectura del ecosistema.

## Pruebas

Se realizaron cinco pruebas controladas:

- Test Landing → Enviado
- Test Ecommerce → Rechazado
- Test Sin Email → Error
- Test Sin Necesidad → Error
- Test Automatización → Enviado

## Autor

Gabriel Alejandro Bottillo  
BOTTIDEV
