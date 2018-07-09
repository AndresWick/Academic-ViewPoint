# Microservicios y Serverless
## Microservicios
<div class =text-justify>
Es un enfoque de estilo arquitectónico que nos permite pensar el desarrollo de software a partir de una serie de pequeños servicios. Donde cada servicio se encarga de implementar una funcionalidad completa del negocio. En vez de tener un único ejecutable, cada componente es un ejecutable por sí mismo, y los servicios se comunican entre sí a través de llamadas. Es decir que cada microservicio se puede desplegar de forma independiente, un cambio en el módulo de inventario, no afectará a los demás, solo tendremos que subir ese módulo. Podemos formar equipos multifuncionales que se encarguen de varios microservicios, escalando el proceso de desarrollo de forma más sencilla, en lugar de replicar toda la aplicación y gestionarlo con balanceadores, replicaremos los microservicios que tengan más carga.  


La arquitectura introduce complejidad adicional y nuevos problemas a resolver, como latencia en la red, formato de los mensajes, balanceo de carga y tolerancia a fallas (Este patrón de implementación permite el balanceo entre distintas instancias de forma transparente a la hora de consumir un servicio). 

El siguiente diagrama muestra la arquitectura de microservicios en capas:

![GitHub](/microserviciosCapas.jpg)

Además de los propios servicios, hay otros componentes que aparecen en una arquitectura típica de microservicios:

Administración: El componente de administración es responsable de la colocación de servicios en los nodos, la identificación de errores, el reequilibrio de servicios entre nodos, etc.
Detección de servicios: Mantiene una lista de servicios y los nodos en que se encuentran. Permite la búsqueda de servicios para localizar el punto de conexión de un servicio.

Puerta de enlace de API: La puerta de enlace de API es el punto de entrada para los clientes. Los clientes no llaman directamente a los servicios. En su lugar, llaman a la puerta de enlace de API, que reenvía la llamada a los servicios apropiados en el back-end. La puerta de enlace de API podría agregar las respuestas de varios servicios y devolver la respuesta agregada.

La puerta de enlace debe controlar y enrutar las solicitudes de cliente sin ningún conocimiento de las reglas de negocios o la lógica de dominio. En caso contrario, la puerta de enlace se convierte en una dependencia y puede provocar el acoplamiento entre servicios.

### Modelo de Despliegue: 

Nos referimos aquí al modo en que vamos a organizar y gestionar los despliegues de los microservicios, así como a las tecnologías que podemos usar para tal fin.

Existen convencionalmente dos tendencias en este sentido a la hora de encapsular microservicios:

•	Máquinas virtuales (simula un sistema de computación y puede ejecutar programas como si fuese una computadora real).
•	Contenedores (paquetes de elementos que permiten ejecutar una aplicación determinada en cualquier sistema operativo.)


Cuando tratamos con problemas complejos es necesario tratar con el problema de manejar procesos de negocio que involucran a varios servicios. Hay dos formas de abordar este tipo de problemas: Orquestación y coreografía.

• Con orquestación lo que hacemos es tener un software que guíe y dirija el proceso, de forma similar a como lo hace un director de orquesta.

• Con coreografía lo que hacemos es dejar que cada parte del sistema realice su trabajo y se les deja trabajar en los detalles, como hacen los bailarines en un ballet. Es más adaptado a la arquitectura de microservicios que cada servicio sepa cómo actuar en cada momento, e interactúe con otros, en lugar de tener a alguien que los coordine. Por eso para integrar se suele preferir tener coreografía.
</div>

## Serverless:

Serverless es un tipo de arquitectura donde los servidores (físicos o en la nube) dejan de existir para el desarrollador y en cambio el código corre en “ambientes de ejecución” que administran proveedores como Amazon, Google, IBM, etc. Cuando la funcion es invocada, ya sea por un request HTTP u otro evento, el ambiente de ejecución es iniciado, el código se ejecuta e inmediatamente el ambiente desaparece. Si la función es invocada mil veces, el proveedor se encarga de escalar y generar el número de ambientes necesarios para responder a las mil invocaciones.

![GitHub](/serverless.png)

Sin servidor también puede significar aplicaciones donde la lógica del lado del servidor todavía está escrita por el desarrollador de aplicaciones, pero a diferencia de las arquitecturas tradicionales, se ejecuta en contenedores de cómputo sin estado que son activados por eventos, efímeros (puede durar solo una invocación) y totalmente administrados por un tercero. Una forma de pensar en esto es "Funciones como servicio" o "FaaS". AWS Lambda es uno de los ejemplos más famosos. 

Este servicio de Amazon nos permite crear unos endpoints para crear una API y basado en estos endpoints configurar qué código del que tenemos en AWS Lambda ejecutará cada uno de ellos. De esta forma no tenemos que tener ningún servidor donde resida nuestro código, sólo lo subimos y configuramos la API para que ejecute ese código. Gracias a las políticas de autoescalado que podemos configurar en Amazon podemos hacer servicios que siempre respondan independientemente de la carga que tengan. A día de hoy, los lenguajes que soporta AWS Lambda son Java, NodeJS y Python, pero seguro que irán llegando otros.

![GitHub](/Lambda.png)

AWS Lambda escala automáticamente la aplicación ejecutando código en respuesta a cada disparador. El código se ejecuta en paralelo y procesa cada disparador por separado. Así logra escalar precisamente con el tamaño de la carga de trabajo.

Es posible usar AWS Lambda para ejecutar código en respuesta a disparadores, como cambios en los datos, cambios en el estado del sistema o acciones de los usuarios. Lambda se puede activar directamente mediante servicios de AWS como S3, DynamoDB, Kinesis, SNS y CloudWatch, o se puede organizar en flujos de trabajo mediante AWS Step Functions. (AWS Step Functions facilita la coordinación de componentes de aplicaciones y microservicios distribuidos con flujos de trabajo visuales. ) Esto permite crear una variedad de sistemas de procesamiento de datos sin servidor en tiempo real.

---
# Introductory-ViewPoint
Punto de vista introductorio del sistema de gestión académico.
---

# Diagrama Introductorio
---

 ![GitHub](/Introduction%20ViewPoint.jpg)
 ---
 # Diagrama de organización
 
  ![GitHub](/Model%20from%20the%20organization.jpg)
 
 ---
 # Diagrama de cooperación
 ![GitHub](/co-operation.bmp)
 
 ---
  # Diagrama de Función del Negocio
 ![GitHub](/Business%20Functions.png)
 
 ---
  # Diagramas de Procesos 
  ---
  ## Asignación de notas
 ![GitHub](/Asignacion%20notas.JPG)
 
 ---
  ## Contratación docentes
 ![GitHub](/Contratacion%20docentes.JPG)
 
 ---
  ## Evaluación docente
 ![GitHub](/Evaluacion%20docente.JPG)
 
 ---
  ## Generación de horarios
 ![GitHub](/Generacion%20horarios.JPG)
 
 ---
  ## Inscripción de estudiantes
 ![GitHub](/Inscripcion%20estudiantes.JPG)
 
 ---
  ## Admisiones
 ![GitHub](/Gestion%20Admision.JPG)
 
 ---
  ## Inscripcion de materias
 ![GitHub](/Inscripcion%20materias.JPG)
 
 ---
  ## Pago docentes
 ![GitHub](/Pago%20docentes.JPG)
 
 ---
  ## Vacacionales
 ![GitHub](/Vacacionales.JPG)
 
 ---
  ## Proyecto de grado
 ![GitHub](/Proyecto%20de%20grado.JPG)
 
 ---
  ## Monitorias
 ![GitHub](/Monitorias.JPG)
 
 ---
  # Diagrama de Cooperación de Aplicación 
  ![GitHub](/VistaCooperacionDeAplicaciones.png)
 ---
  # Diagramas de Uso
  ---
  ## Asignación de notas
 ![GitHub](/SerNotas.JPG)
 
 ---
  ## Contratación docentes
 ![GitHub](/SerContratacion.JPG)
 
 ---
  ## Evaluación docente
 ![GitHub](/SerEvaluacion.JPG)
 
 ---
  ## Generación de horarios
 ![GitHub](/SerHorarios.JPG)
 
 ---
  ## Inscripción de estudiantes
 ![GitHub](/SerInscripciones.JPG)
 
 ---
  ## Admisiones
 ![GitHub](/SerAdmisiones.JPG)
 
 ---
  ## Inscripcion de materias
 ![GitHub](/SerMaterias.JPG)
 
 ---
  ## Pago docentes
 ![GitHub](/SerPagoDoc.JPG)
 
 ---
  ## Vacacionales
 ![GitHub](/SerVacacionales.JPG)
 
 ---
  ## Proyecto de grado
 ![GitHub](/SerProyecto.JPG)
 
 ---
  ## Monitorias
 ![GitHub](/SerMonitorias.JPG)
 
---
  # Diagrama de uso de infraestructura
 ![GitHub](/Infraestructura.JPG)
 
 
 
  Autores:
*  [GitHub](https://github.com/preguntaud)
    @preguntaud
    - Oscar Eduardo Calderón R.
    / Cod. 20142020110
*  [GitHub](https://github.com/AndresWick)
    @AndresWick
    - Carlos Andrés Aguirre Cañas
    / Cod. 20141020215
*  [GitHub](https://github.com/j0el360)
    @j0el360
    - Joel Guerra Morales
    / Cod. 20141020054
*  [GitHub](https://github.com/CristianC4)
    @CristianC4
    - Cristian Camilo Cuervo
    / Cod. 20142020010

