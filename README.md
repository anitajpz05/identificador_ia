Ana María Jiménez Pérez 
Sistema de Clasificación Inteligente de Correos Electrónicos 
Introducción
En la actualidad, el uso del correo electrónico constituye una herramienta esencial de comunicación tanto personal como profesional. Sin embargo, el incremento masivo de mensajes no deseados (spam) representa un problema significativo que afecta la productividad, la seguridad informática y la eficiencia en la gestión de información. Estos correos pueden contener publicidad invasiva, enlaces maliciosos o intentos de fraude, lo que obliga a implementar sistemas automatizados capaces de clasificarlos correctamente.
Ante esta problemática, surge la necesidad de desarrollar soluciones basadas en técnicas de Inteligencia Artificial que permitan distinguir de forma automática entre correos legítimos y correos no deseados. Además, dentro de los correos legítimos resulta útil establecer niveles de prioridad para optimizar la atención del usuario. En este contexto, se diseñó e implementó un sistema de clasificación automática en consola utilizando aprendizaje automático supervisado.
Desarrollo
El sistema desarrollado consiste en un modelo de clasificación de correos electrónicos implementado en Python, basado en el algoritmo probabilístico Naive Bayes Gaussiano, el cual es ampliamente utilizado en tareas de clasificación por su eficiencia y simplicidad computacional.
1. Generación del conjunto de datos
Para entrenar el modelo se generó un dataset simulado de 5000 correos electrónicos. Cada correo se representa mediante características numéricas que simulan atributos reales observables en mensajes:
•	Frecuencia de palabras clave sospechosas.
•	Cantidad de signos de exclamación.
•	Longitud del mensaje.
•	Presencia de enlaces.
•	Tipo de dominio del remitente.
Se estableció una lógica probabilística para etiquetar automáticamente cada correo como:
•	Spam
•	Ham (no spam)
Adicionalmente, si el correo es legítimo, se le asigna un nivel de importancia:
•	Poco importante
•	Importante
•	Muy importante
2. División del dataset
Los datos generados se dividen automáticamente en:
•	70% para entrenamiento
•	30% para prueba
Esta división permite evaluar el rendimiento real del modelo con datos no vistos previamente.
3. Entrenamiento del clasificador de spam
Se entrena un modelo Naive Bayes con los datos de entrenamiento para aprender los patrones estadísticos que distinguen correos spam de los legítimos. Posteriormente se evalúa su precisión usando el conjunto de prueba, mostrando métricas de rendimiento como precisión, recall y f1-score.
4. Entrenamiento del clasificador de importancia
Se entrena un segundo modelo independiente, pero solo con correos legítimos. Este modelo aprende a clasificar el nivel de importancia de los mensajes no spam según sus características.
5. Interacción en consola
El sistema permite al usuario introducir manualmente las características de un correo desde la terminal. El programa procesa esos datos y devuelve:
•	Si el correo es spam o no.
•	En caso de no ser spam, su nivel de importancia.
Esta interacción demuestra el funcionamiento práctico del sistema en tiempo real y valida el aprendizaje obtenido durante el entrenamiento.
Solución Propuesta
La solución planteada consiste en la aplicación de aprendizaje automático supervisado para automatizar la clasificación de correos electrónicos. El uso del algoritmo Naive Bayes permite:
•	Procesar grandes volúmenes de datos rápidamente.
•	Tomar decisiones probabilísticas confiables.
•	Reducir la intervención humana en la gestión de correos.
El sistema desarrollado cumple con los objetivos planteados al:
•	Detectar spam de manera automática.
•	Clasificar la prioridad de mensajes legítimos.
•	Funcionar completamente en entorno de consola sin interfaces externas.

Conclusiones
El desarrollo de este sistema demuestra que los algoritmos de aprendizaje automático pueden aplicarse eficazmente a problemas reales de filtrado y organización de información. El modelo implementado logró clasificar correos electrónicos de forma automática basándose en características cuantificables, mostrando resultados precisos incluso con datos simulados.
Además, se evidenció que la utilización de múltiples clasificadores permite resolver problemas jerárquicos, como distinguir primero entre spam y no spam, y luego determinar la importancia de los mensajes legítimos. Esto representa una estrategia eficiente para sistemas de decisión escalonados.
Finalmente, el proyecto confirma que herramientas estadísticas sencillas como Naive Bayes pueden ofrecer soluciones robustas, rápidas y funcionales en contextos reales, constituyendo una alternativa viable para el desarrollo de sistemas inteligentes de filtrado de información.

