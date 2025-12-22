## 🚀 Nova Chat - Astronaut AI Assistant
Nova Chat es un chatbot inteligente desarrollado en MIT App Inventor que utiliza la API de Google Gemini. A diferencia de un asistente convencional, Nova Chat tiene la personalidad de un astronauta perdido en el espacio, ofreciendo una experiencia inmersiva, auditiva y visual.

### ✨ Funcionalidades Elevadas
Este proyecto toma la base del chatbot de Gemini e integra las siguientes mejoras:

- Personalidad de Sistema (System Prompt): La IA está configurada para responder siempre como un astronauta en una misión solitaria. Sus respuestas incluyen jerga espacial y un tono de bitácora de misión.
- Historial de Chat Dinámico: Implementación de un flujo de conversación estilo "burbujas" mediante etiquetas HTML, permitiendo ver toda la sesión sin que los mensajes se borren.
- Conversión de Texto a Voz (TTS): El astronauta "habla". Cada respuesta recibida desde el espacio profundo es procesada por el motor de síntesis de voz del dispositivo.
- Diseño "Midnight Tech": Interfaz optimizada con una paleta de colores oscuros, fuentes neón y un diseño de tarjeta moderno para mejorar la legibilidad en entornos oscuros.

📸 Galería del Proyecto
Interfaz de Usuario (UI)
[screen_1](https://github.com/MarianaEContreras/Tareas-Introduccion-a-Ciencia-de-Datos/blob/main/02_tareas/Tarea%203/screen_1.png)

Lógica de Programación
[!Code_1](https://github.com/MarianaEContreras/Tareas-Introduccion-a-Ciencia-de-Datos/blob/main/02_tareas/Tarea%203/code_1.png)
[!Code_2](https://github.com/MarianaEContreras/Tareas-Introduccion-a-Ciencia-de-Datos/blob/main/02_tareas/Tarea%203/code_2.png)

### 🛠️ Requisitos Técnicos
- API Key de Gemini: Obtenida a través de Google AI Studio.

#### Componentes Clave:
- Web: Para la comunicación REST con Gemini.
- TextToSpeech: Para la salida de audio.
- Label (HTMLFormat): Para el renderizado del historial de chat.

### 📥 Instrucciones de Instalación
Para replicar o mejorar Nova Chat en tu cuenta de MIT App Inventor:

1. Descarga el archivo: Obtén el archivo .aia de este repositorio.
2. Importación:
   - Entra a MIT App Inventor.
   - Ve a Projects > Import project (.aia) from my computer.
   - Selecciona el archivo descargado.

3. Configuración de la API:
   -  Ve a la sección de Blocks (Bloques).
   -  Busca la variable o el bloque de texto donde se encuentra la API Key y pega tu propia clave de Google AI Studio.
  
4. Personalización del Astronauta:
   - En el bloque PostText, puedes modificar el texto de la "Instrucción de Sistema" para cambiar la personalidad de Nova Chat.

5. Prueba en vivo:
   - Usa el AI Companion en tu smartphone para escanear el código QR y comenzar la misión.

### 🛰️ Créditos y Referencias
Este proyecto fue inspirado y construido sobre la base del tutorial de VaidrollTeam: CÓMO CREAR UN CHATBOT CON INTELIGENCIA ARTIFICIAL GRATIS.
