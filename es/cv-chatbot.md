# CV Chatbot

Este README presenta un resumen de las herramientas e ideas utilizadas para desarrollar **CV Chatbot**. Puede verse funcionando aquí: [CV Chatbot en Heroku](https://yabra-cv-chatbot-5d4c332eae4a.herokuapp.com/).

## Descripción general

CV Chatbot es una aplicación interactiva que permite explorar un currículum de forma conversacional. Integra **modelos de lenguaje** con una interfaz sencilla pero efectiva, facilitando interacciones intuitivas y dinámicas.

## Funcionamiento

El núcleo del chatbot está desarrollado en **Python**, utilizando **LangChain** y **LangGraph** para estructurar las interacciones con **GPT-4o-mini** y gestionar el historial del chat de forma eficiente. Estas bibliotecas simplifican el trabajo con modelos de lenguaje y permiten diseñar prompts de forma flexible.

Un tutorial útil durante el desarrollo fue:  
🔗 [Tutorial de Chatbot con LangChain](https://python.langchain.com/docs/tutorials/chatbot/)

## Elección del modelo

### RAG vs. Contexto largo en el prompt

Se consideraron dos enfoques: **Generación aumentada con recuperación (RAG)** y la inclusión directa del currículum en el prompt. Dado que el CV detallado no supera las **cuatro páginas**, y los modelos actuales manejan contextos extensos con eficacia, se optó por **incluir directamente la información del CV en el prompt del sistema**. Esto garantiza que el chatbot tenga siempre acceso a la información completa sin necesidad de un sistema de recuperación.

### Seguridad

Se buscó que el chatbot mantuviera un tono **profesional y enfocado**. Para evitar respuestas a consultas **irrelevantes** o **inapropiadas**, se probaron diferentes estrategias de prompts que orientan al modelo a mantener un enfoque **profesional y temático**. El prompt final asegura que el chatbot solo hable sobre el currículum y temas relacionados.

## Interfaz

Al no contar con experiencia en desarrollo frontend, se utilizó **Dash (de Plotly)** para crear una interfaz simple pero funcional, completamente en **Python**. Dash facilita la creación de aplicaciones web interactivas con poco esfuerzo.

Este ejemplo fue especialmente útil:  
🔗 [Ejemplo de Chatbot con Dash](https://github.com/plotly/dash-sample-apps/tree/main/apps/dash-chatbot)

## Despliegue

El chatbot está desplegado en **Heroku** utilizando un **Dyno básico**. Heroku permite un proceso de despliegue sencillo y gestiona la escalabilidad para aplicaciones pequeñas.

## Base de datos

Para registrar las interacciones, se configuró una base de datos **PostgreSQL** en **Heroku**. Esto permite analizar cómo se usa el chatbot. Se utiliza la biblioteca **psycopg2** en Python para insertar los datos en las tablas correspondientes.
