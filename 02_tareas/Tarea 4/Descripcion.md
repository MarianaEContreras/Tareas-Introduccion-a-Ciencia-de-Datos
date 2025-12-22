## 👁️ AI Image Classifier 
Este proyecto demuestra cómo integrar modelos de Google Teachable Machine en MIT App Inventor para crear una aplicación de clasificación de imágenes en tiempo real. A diferencia de una implementación básica, esta versión incluye optimizaciones de UI/UX, gestión de recursos y lógica de filtrado de datos.

### ✨ Funcionalidades Avanzadas
El proyecto incluye las siguientes mejoras de rendimiento y usabilidad:
- Visor de Confianza Dinámico: Una barra de progreso visual que cambia de tamaño y color (Verde/Naranja/Rojo) en tiempo real según la certeza del modelo de IA.
- Sistema de Umbral (Threshold): Lógica de filtrado que solo muestra resultados si la confianza es superior al 70%, evitando "falsos positivos" por ruido visual.
- Gestión de Energía (Battery Saver): Incluye un interruptor (Toggle) para pausar o activar el reloj de escaneo, evitando el sobrecalentamiento del dispositivo y el drenado de batería.
- Escaneo Automatizado: Uso de un componente Clock para realizar clasificaciones periódicas (cada 2 segundos) sin necesidad de intervención manual del usuario.

### 📸 Galería del Proyecto
Interfaz de Usuario (UI)
[](https://github.com/MarianaEContreras/Tareas-Introduccion-a-Ciencia-de-Datos/blob/main/02_tareas/Tarea%204/img/screen_1.png)

Lógica de Programación (Bloques)
[](https://github.com/MarianaEContreras/Tareas-Introduccion-a-Ciencia-de-Datos/blob/main/02_tareas/Tarea%204/img/code_1.png)
[](https://github.com/MarianaEContreras/Tareas-Introduccion-a-Ciencia-de-Datos/blob/main/02_tareas/Tarea%204/img/code_2.png)

### 🛠️ Requisitos Técnicos
1. Modelo de IA: Exportado como TensorFlow.js desde Teachable Machine.
  - Extensión: TMIC.aix (Teachable Machine Image Classifier).
2. Sensores: Componente Clock para el ciclo de escaneo.
3. Conectividad: Requiere acceso a internet constante para validar el modelo alojado en la nube.

###📥 Instrucciones de Instalación
Para importar y configurar este proyecto en tu entorno de MIT App Inventor, sigue estos pasos:

1. Preparación del Modelo
  - Entrena tu modelo de imagen en Teachable Machine.
  - Exporta el modelo seleccionando TensorFlow.js y haz clic en Upload my model.
  - Copia la URL del modelo generada.

2. Configuración en App Inventor
  - Extensión: Descarga el archivo .aix de la extensión TMIC e impórtalo en tu proyecto (Extensions -> Import Extension).
  - Importar Proyecto: Sube el archivo .aia de este repositorio a tu cuenta de App Inventor.
  - Vincular Modelo:
      - Selecciona el componente TMIC1 en el diseñador.
      - Pega la URL de tu modelo en la propiedad UrlModel.

3. Despliegue
Utiliza AI Companion en un dispositivo Android físico.

Nota: Los emuladores de PC no son compatibles ya que no pueden acceder a la cámara de la misma forma que requiere la extensión TMIC.

### 🛰️ Créditos y Referencias
La arquitectura de comunicación de este proyecto utiliza la extensión TMIC desarrollada por la comunidad de MIT App Inventor para el soporte de TensorFlow.js.
