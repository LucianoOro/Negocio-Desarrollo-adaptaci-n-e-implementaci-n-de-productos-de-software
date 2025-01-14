# Negocio: Desarrollo, adaptación e implementación de productos de software
Este proyecto documenta el diseño completo de un sistema utilizando UML, abordando cada etapa del modelado para resolver problemas concretos de información en un contexto de negocio específico.

Instrucción de uso: Seleccione ***negocio.rar,*** posteriormente download raw file, se descargará un archivo rar comprimido con un archivo con extension .eap, el cual se debe abrir con el programa Enterprise Architect, y además posee una carpeta con los artefactos en formato pdf para facilitar sus visualización.

Este repositorio contiene el diseño completo de un sistema utilizando teoría de UML, desarrollado como parte de una ejercitación académica para modelar soluciones a problemas de información en contextos concretos de negocio. Incluye:

 - Modelo de Requisitos: Identificación de actores y casos de uso que permiten modelar una solución integral al problema planteado, junto con diagramas de casos de uso.
 - Especificaciones Detalladas: Documentación exhaustiva de los casos de uso mediante descripciones de flujo de sucesos, diagramas de transición de estados, y diseños de interfaces de usuario que contemplan los parámetros de entrada.
 - Diagrama de Clases: Desarrollo de un modelo de dominio que permite sostener la funcionalidad de los casos de uso, integrando conceptos de clases, atributos, relaciones, navegabilidad y multiplicidad.
 - Decisiones de Diseño: Registro de las decisiones tomadas para implementar la solución diseñada, con análisis comparativo de alternativas en términos de ventajas, restricciones y desventajas.
 - Integración de Artefactos: Aplicación de herramientas como el modelo del dominio y el diseño de la interfaz de usuario para lograr una especificación detallada y consistente.

Este proyecto refleja un enfoque sistemático y detallado, orientado a comprender y resolver problemas a través de la especificación de requerimientos y la construcción de modelos UML.

A continuación, se presenta el texto que corresponde a la definición inicial de requisitos para el sistema en cuestión.

> “Una empresa desarrolla y comercializa varios productos de software
> propios. Cuando confirma un nuevo contrato se da el alta del proyecto
> nuevo indicando el cliente, el producto contratado, la fecha
> consensuada para la inicialización y para la finalización del
> proyecto. El proyecto se arma para adaptar e implementar el producto
> en el cliente. El líder del proyecto crea solicitudes de trabajo para
> especificar lo que se requiere realizar para avanzar en cada proyecto.
> Cada solicitud especifica la fecha planificada de entrega, detalle de
> la especificación de los requisitos (es un texto) con estado
> “Solicitado” de la solicitud. El estado actual y el integrante
> responsable de la solicitud son modificados únicamente por el líder
> del equipo o por el propio responsable de la solicitud, de acuerdo a
> las tareas que registra cada integrante responsable sobre la
> solicitud. Cada tarea registrada debe contener: un tipo de tarea,
> fecha y hora de inicio, fecha y hora de finalización de la tarea,
> detalle de la tarea (es un texto). El estado actual de la referencia
> define qué tipos de tareas se podrán registrar. No todos los tipos de
> tareas estarán habilitados en todos los estados posibles. Por ejemplo
> suponiendo un estado “En relevamiento” no se podría registrar una
> tarea de tipo “pruebas” o existiendo el estado “En Testing manual” no
> se podría registrar una tarea de tipo “desarrollo”. Y habrá tipos de
> tareas como “tareas administrativas”, “redacción de documentación”,
> “envío de comunicación” que podrán registrarse en diferentes estados.
> 
> Luego de avanzar más en el relevamiento se clarificaron algunos
> requisitos:   a. El líder de proyecto se auto-asigna de entre el/los
> proyectos disponibles aquellos que corresponda de acuerdo a lo
> acordado en sus reuniones con la Gerencia, lo que debe registrar en el
> sistema.
>      b. En ese momento el sistema asignará un equipo de trabajo al proyecto. Existen varios equipos de trabajo disponibles. Cada uno de
> ellos se especializa en uno o más productos de la empresa. Los
> integrantes del equipo de   trabajo se mantienen en el tiempo en
> general. Pero se debe considerar las variaciones temporales, por
> licencias, rotación o bajas. Cada integrante puede ejecutar uno o más
> roles dentro del equipo. Un integrante eventualmente   puede
> pertenecer a más de un equipo de trabajo del mismo producto. Para
> asignar el equipo al proyecto se evalúa la cantidad de proyectos en
> simultáneo que ha sido determinado que un equipo puede manejar de
> acuerdo a su   experiencia y composición. Cumpliendo esa restricción
> se prioriza la asignación del equipo que ya haya trabajado en otros
> proyectos del mismo cliente.
>      c. El líder del equipo toma las solicitudes creadas, las asigna a un integrante y planifica su fecha de entrega. De considerarlo
> conveniente fracciona la solicitud inicial creada por el líder de
> proyecto en varias solicitudes más   atómicas vinculadas a la
> principal definiendo su alcance y especificación. El registro de
> tareas, seguimiento y cambios de estado se hace siempre sobre las
> solicitudes hijas, en estos casos. El líder de equipo en cualquier  
> momento mientras la solicitud no se haya cerrado puede cambiar de
> responsable a la solicitud por lo que, para control de las tareas y
> responsabilidades, se debe registrar datos precisos de dichos cambios.
> Para registrar tareas en   una solicitud no hace falta ser el
> responsable de la misma, dado que existe cooperación dentro del equipo
> y todos deben registrar el tiempo trabajado en cada solicitud. Pero
> sólo el responsable y el líder de equipo pueden cambiar   los estados
> de la solicitud.
>      d. El líder de equipo también, durante la ejecución del proyecto puede crear nuevas solicitudes o suspender solicitudes. Estas
> necesidades se justifican en razones técnicas y consensos alcanzados
> en las reuniones que se   realizan semanalmente entre los product
> owner (líderes de proyecto y líderes de equipos de un producto)
>      e. El líder de proyecto dará por finalizado un proyecto cuando las solicitudes terminadas hayan cubierto la totalidad de los
> requisitos y de los trabajos necesarios para poner en funcionamiento
> la o las partes del producto que se pactó   implementar en el contrato
> que sustenta al proyecto en cuestión.   Alcance Actividad 4 según
> guía: Caso de Uso Asignar Líder de Proyecto y Equipo de Trabajo a
> Proyecto.
> 
>   Requisitos adicionales   a. Cada solicitud de trabajo tendrá
> asignada un tipo de solicitud. Esto se incluye para dar mejor
> tratamiento a los circuitos de estado que ordenadamente deberá
> transitar una solicitud de acuerdo a su tipo desde su creación hasta  
> su cierre. No es igual el circuito de una solicitud de desarrollo a
> una de capacitación o de migración, etc. El esquema debe permitir
> modelar, al especialista responsable, las diferentes alternativas o
> transiciones que sean   válidas. Habrá estados comunes para todos los
> tipos de solicitud y otros estados más típicos para algunos casos. Con
> lo cual si bien debe existir un clasificador de todos los estados
> válidos, deberá permitirse la definición y   mantenimiento de todas
> las ramas del árbol con las transiciones de estados permitidas, de
> modo tal que cuando el responsable de la solicitud o el líder de
> equipo intenten modificar el estado de una solicitud sólo se les
> permita:   revertir el estado para volver al estado anterior de la
> solicitud o avanzar un estado según corresponda a lo parametrizado
> para el tipo de solicitud y estado actual de la misma.
>      b. El analista de sistemas líder prevé la necesidad de que se habilite una opción dentro del caso de uso que permite cambiar los
> estados de una solicitud para que se pueda revertir el último estado
> registrado porque es un error   común en la operación del sistema.  
> Alcance Actividad 4 según guía: lo que corresponda según el impacto de
> los requisitos en los modelos desarrollados
