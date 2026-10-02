# Ecosistema IA Comercial - BOTTIDEV

Proyecto final del curso **AI Automation**.

El sistema automatiza la generación, revisión y envío de propuestas comerciales para BOTTIDEV utilizando inteligencia artificial, persistencia de datos y un proceso Human-in-the-loop antes de contactar al cliente.

## Tecnologías

- n8n — orquestación del workflow
- Airtable — base de datos, memoria del sistema y dashboard
- OpenAI GPT-5.6 Luna — generación de propuestas comerciales
- Gmail — aprobación humana y envío al cliente

## Flujo del sistema

Airtable Leads  
→ Validación de datos  
→ Generación de propuesta con IA  
→ Registro de propuesta en Airtable  
→ Estado "En revisión"  
→ Human-in-the-loop por Gmail  
→ Aprobación o rechazo humano  
→ Envío de propuesta al cliente  
→ Actualización final en Airtable  
→ Registro de trazabilidad

El sistema también incluye rutas específicas para:

- Datos incompletos
- Errores del agente de IA
- Rechazo humano de propuestas

## Seguridad y resiliencia

- Validación previa de Email y Necesidad
- Filtro anti-loop mediante `Estado = Pendiente IA`
- Retry On Fail en el nodo de IA
- Registro de errores con Execution ID
- Human-in-the-loop antes del envío al cliente
- Thread ID de Gmail para trazabilidad
- Minimización de datos enviados al modelo
- Workflow público sanitizado sin claves API

## Dashboard

Dashboard público de Airtable:

https://airtable.com/app2m4kFYu3sIxysj/shr4CxNc85xkAypDq/tblNzMc1pYDfW1IBD/viw9dwJ43FJ4lrsnj

### KPIs obtenidos

- Tasa de aprobación: **66,7%**
- Volumen de salida: **2**
- Tasa de error: **40%**

## Base de datos

Vista pública en modo lectura:

https://airtable.com/app2m4kFYu3sIxysj/shr4CxNc85xkAypDq/tblNzMc1pYDfW1IBD/viwLUWvQREjd2OdiQ

La base se encuentra estructurada en tres tablas principales:

- Leads
- Propuestas
- Errores

## Workflow n8n

El workflow completo exportado en formato JSON está incluido en el repositorio:

[Ecosistema IA Comercial - BOTTIDEV.json](./Ecosistema%20IA%20Comercial%20-%20BOTTIDEV.json)

## Documentación final

La documentación completa del proyecto incluye la descripción del sistema, estructura de datos, seguridad, resiliencia, pruebas, optimización de costos, prompt utilizado y resultados.

[Ver documentación final](./Entrega-Final-Automation.pdf)

## Mapa de arquitectura

El mapa representa visualmente los triggers, routers, nodos de IA, APIs utilizadas, rutas de error y destinos de datos.

[Ver mapa de arquitectura](./Mapa-arquitectura.pdf)

## Evidencias

Las capturas correspondientes a las ejecuciones, Human-in-the-loop, manejo de errores, dashboard y resultados se encuentran en:

[Ver carpeta de evidencias](./evidencias)

## Pruebas realizadas

Se realizaron cinco pruebas controladas:

- Test Landing → Enviado
- Test Ecommerce → Rechazado
- Test Sin Email → Error
- Test Sin Necesidad → Error
- Test Automatización → Enviado

Los tests contemplan tanto el camino exitoso como escenarios de rechazo y error.

## Video demostrativo

Demostración del funcionamiento completo del ecosistema:

https://youtu.be/fmPPeq-_r-I?si=v8wZMzocStnOediW

El video muestra:

- Estructura de Airtable
- Workflow completo en n8n
- Generación con IA
- Human-in-the-loop
- Aprobación y rechazo
- Envío por Gmail
- Manejo de errores
- Dashboard y métricas

## Repositorio

https://github.com/GabrielBottillo123/bottidev-ecosistema-ia-comercial

## Autor

**Gabriel Alejandro Bottillo**  
BOTTIDEV
