# IA_minibots_T7_IA_generativa

Para los tres primeros puntos, y teniendo en cuenta que estoy usando una distribución de ubuntu 20.04, he decidido usar docker para crear un entorno virtual para el desarrollo de los mismos. De esta manera, los entornos virtuales pueden usar correctamente las versiones de librerias necesariasa sin ningun problema, sin embargo, en un entorno diferente puede ser ejecutado sin la ayuda de docker, siempre y cuando se cumplan con las dependencias necesarias, las cuales se encuentran en el archivo requirements.txt.

En resumen, se pueden usar dos vias para el uso de codigo:
 - **Docker:** Crear la imagen y disponer el servicio a traves del puerto 8888. con el comando 
  
   ```bash
   docker compose up -d
   ```

 - **Entorno virtual:** Crear un entorno virtual e instalar las dependencias necesarias con los siguientes comandos: 

   Para linux:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   ```
   Para windows:
   ```bash
   python -m venv .venv
   .venv\Scripts\activate
   pip install -r requirements.txt
   ```


### Desarrollar un agente de IA, con cualquier chatbot de IA, para el manejo de las tareas del curso.

Para el desarrollo de este punto, se ha decidido usar la libreria langchain, la cual permite crear agentes de IA, con cualquier chatbot de IA, para el manejo de las tareas del curso.

Para esto se descarga un modelo de lenguaje destilado, en este caso **TheBloke/Mistral-7B-Instruct-v0.2-GGUF**, el cual es un modelo de lenguaje de tamaño intermedio, el cual se ejecuta localmente y posee una confiabilidad mayor a la de los modelos de lenguaje de tamaño reducido.

Luego de descargar el modelo, se configuran los parametros de ejecucion, y con la ayuda de gradio se crea una interfaz grafica para la interaccion con el agente.


### Mejorar el sistema RAG para crear un chat que permita acceder a la información actualizada de la Universidad Nacional, u otra empresa o entidad.

El sistema desarrollado implementa un enfoque de Retrieval-Augmented Generation (RAG), en el cual primero se recupera información relevante desde una base de documentos mediante el uso de embeddings y técnicas de similitud semántica, y posteriormente un modelo de lenguaje genera respuestas basadas en dicho contexto. 

Para ello, se emplea un proceso de segmentación de texto (chunking) y un modelo de embeddings local que permite indexar eficientemente la información sin depender de servicios externos. El chatbot interactivo permite consultar contenidos almacenados en una carpeta de datos, la cual puede actualizarse fácilmente agregando nuevos documentos, garantizando así que el sistema pueda trabajar con información reciente. Este enfoque puede aplicarse a contextos reales, como la consulta de información institucional de la Universidad Nacional de Colombia, facilitando el acceso a datos relevantes para los usuarios.

Se puede observar mejor todo en el siguiente archivo

[02_rag_chatbot.ipynb](gemini/02_rag_chatbot.ipynb)

Como mejora futura, el sistema podría integrarse con fuentes externas como páginas web oficiales para obtener información en tiempo real y ampliar aún más su capacidad de respuesta.

### Desarrollar un Agentic AI para el manejo personal de sus actividades.

### Hacer un estudio sobre las posibilidades de la IA Física en nuestro país. 

La Inteligencia Artificial Física hace referencia a la aplicación de la inteligencia artificial en sistemas que interactúan con el mundo real, como robots, drones, vehículos autónomos y sistemas de automatización. En el contexto colombiano, esta área presenta un desarrollo progresivo, principalmente impulsado por universidades, centros de investigación y algunas empresas tecnológicas. Instituciones como la Universidad Nacional de Colombia han liderado proyectos en robótica, automatización y sistemas inteligentes, contribuyendo al avance académico y tecnológico del país.

Actualmente, la IA física en Colombia se aplica en sectores como la industria, donde se utilizan sistemas automatizados para optimizar procesos productivos, así como en la agricultura, mediante el uso de drones y sensores inteligentes para mejorar la eficiencia en cultivos. También se han desarrollado aplicaciones en seguridad y vigilancia, donde los sistemas autónomos permiten monitorear espacios de manera más eficiente. Sin embargo, su implementación aún enfrenta desafíos importantes, como el alto costo de las tecnologías, la limitada infraestructura y la necesidad de mayor inversión en investigación y desarrollo.

A pesar de estas dificultades, el futuro de la IA física en Colombia es prometedor. Se espera que, con el crecimiento de la transformación digital y el fortalecimiento de la educación en áreas como la ingeniería y la inteligencia artificial, aumente la adopción de estas tecnologías en distintos sectores. Esto permitiría mejorar la productividad, reducir errores humanos y fomentar la innovación en el país. En conclusión, aunque la IA física aún se encuentra en una etapa de desarrollo en Colombia, su potencial es significativo y representa una oportunidad clave para el avance tecnológico y económico.

Es fundamental que el país continúe fortaleciendo la inversión en ciencia y tecnología para aprovechar al máximo los beneficios de la inteligencia artificial física.
