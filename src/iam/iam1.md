Las organizaciones clasifican y categorizan la información en función de su valor para sus actividades en curso, y si alguna de sus características de seguridad se ve comprometida, determinan cómo ese 
valor puede verse afectado. A medida que las necesidades de seguridad de la información se alinean con las prioridades organizacionales, esto informa decisiones críticas sobre los controles de seguridad, 
que pueden ser de naturaleza administrativa, técnica u operativa. Sin embargo, todos estos controles dependen de decisiones sobre la necesidad de saber: quién, dentro y fuera de la organización, debe poseer
el conocimiento sobre lo que contiene un conjunto de datos en particular y, por extensión, quién requiere la capacidad de crear, modificar, mover, copiar o cambiar de otra manera la ubicación, estado o
características de ese conjunto de datos.

Esto lleva a la siguiente tarea importante que enfrentan los profesionales de seguridad de la organización: crear y gestionar los procesos de gestión de identidades y accesos (IAM) que la organización 
necesita. Dichos sistemas IAM deben acomodar tanto a usuarios humanos como no humanos, como software, hardware, dispositivos de Internet de las Cosas (IoT) y una creciente variedad de robots.

Existe cierta confusión en el mercado sobre qué terminología usar para este tema: gestión de identidades (IdM) o IAM. Algunas fuentes, como Gartner Research, han intentado definir IdM como enfocado en 
el proceso de emisión y gestión de identidades para controlar su acceso a los recursos del sistema, y reservar IAM para el problema más grande de cuestiones de identidad y acceso en sistemas en la nube y 
sistemas federados. IAM se usará a lo largo de este dominio y curso. Los sistemas IAM consisten en procesos que crean y gestionan identidades, asocian privilegios con identidades y luego usan esa 
información para asegurar que ninguna identidad desconocida o no reconocida (humana o no humana) pueda acceder a los recursos del sistema o realizar cualquier operación sobre ellos. Los sistemas IAM 
también deben realizar un seguimiento de todo lo relacionado con el ciclo de vida de una identidad y de sus intentos de acceder a los recursos. Esta "triple A" de autenticación, autorización y contabilidad 
(AAA), y las funciones centrales de gestión de identidades en el corazón de esto, han sido reconocidas durante mucho tiempo como la piedra angular de la seguridad, y se conoce por el acrónimo IAAA. 
Sin esto, ninguno de los controles de seguridad sabría qué actividades permitir y cuáles prevenir.

Control de Acceso Físico y Lógico a Activos (5.1)
Objetivos

    Explicar las necesidades y los procesos para el acceso físico y lógico a los activos.

Resumen

Proveer un control positivo de los intentos de acceso (visualizar, modificar o mover) a los activos de una organización requiere un conjunto consistente y cohesivo de controles administrativos, físicos y lógicos (o técnicos). Por supuesto, todos los sistemas de control de acceso (AC) están impulsados por información: el inventario de activos de información, las políticas de clasificación y categorización, y los resultados de las decisiones tomadas a lo largo del ciclo de vida del sistema de identidad y AC y los sistemas de información que ayuda a proteger.

La selección y uso de esos controles mencionados deben estar guiados por consideraciones de diseño basadas en los modelos de seguridad y modelos de AC empleados. Los controles administrativos, que dirigen las acciones de las personas, están basados en un contexto organizacional más amplio.

Como sus nombres sugieren, los controles físicos restringen o guían los movimientos y acciones de los usuarios; los controles lógicos permiten, restringen, guían o de otra manera influyen en el flujo de información a través del sistema. Algunos de esos flujos de información pueden haber sido desencadenados por acciones físicas de un usuario, como una pulsación de tecla, un clic de ratón o moverse dentro del rango de captura de un detector de movimiento u otro sensor. Otros flujos de información resultaron de las acciones de elementos de software, que presumiblemente fueron activados por un usuario.

Con el rápido crecimiento en el uso de robots semiautónomos y autopropulsados, es importante tener en cuenta que los usuarios en este contexto deben incluir tanto a humanos como no humanos. Veamos más de cerca el control de acceso físico y lógico en acción, como parte de un programa de seguridad de activos de información.

**Control de Acceso: Lo Básico**

Una variedad de definiciones de control de acceso se utilizan en toda la comunidad de seguridad de la información a nivel mundial. Un punto de partida útil se encuentra en la norma ISO/IEC 27000:2016(E), que define el control de acceso como un “medio para asegurar que el acceso a los activos esté autorizado y restringido según los requisitos comerciales y de seguridad”. Para obtener información adicional, consulte ISO/IEC 27000:2016(E) y otros documentos de la serie ISO/IEC 27000. El NIST define el control de acceso de diversas maneras; algunas (como NIST SP 800-79-2) se enfocan más claramente en otorgar o denegar solicitudes para obtener o usar información u otros activos, mientras que otros controles (como NIST SP 800-192) se enfocan más en los medios para hacerlo. La declaración de propósito de la ISO proporciona un punto de partida para que las organizaciones lo usen mientras desarrollan, implementan, gestionan y evalúan el rendimiento de tales sistemas como parte de sus programas de seguridad de la información.

Como nombre, el control de acceso deja algunas palabras clave implícitas en lugar de explícitas. Más explícitamente, el control de acceso podría llamarse control del acceso de sujetos a objetos en un sistema. Esto se ilustra en la Figura 5.1, que proporciona una visión general y una introducción a los temas básicos del control de acceso. Pongámonos en el papel de los defensores de los sistemas y activos de la organización mientras nos adentramos en la terminología.

- **Objetos** son los activos de información o los recursos del sistema que son los bloques de construcción de los sistemas que debemos proteger. Pueden ser archivos, registros o campos dentro de una base de datos. Los recursos de hardware como áreas de memoria, tiempo de CPU, espacio en disco o dispositivos de interfaz de red también son objetos, en términos de AC. Las áreas físicas de un edificio, documentos impresos e incluso los canales Wi-Fi proporcionados por los puntos de acceso inalámbrico de la organización pueden considerarse como objetos que necesitan protección. Los objetos también pueden ser otros sujetos.
- **Sujetos** son cualquier persona, proceso, dispositivo u otra entidad que quiera acceder a cualquiera de los objetos en el sistema.
- **Acceso** se puede pensar en términos de base de datos, como operaciones de crear, leer, actualizar o eliminar (CRUD), o los diversos pasos en el modelo de ciclo de vida de seguridad de datos descrito en el Dominio 2, que agrega compartir, archivar y almacenar como acciones explícitas.

Observe en esta figura que uno de los sujetos (presumiblemente un humano) está utilizando una computadora (que puede o no ser su propio activo) como intermediario para acceder a una base de datos en un servidor perteneciente a la organización. Esto destaca la complejidad de conocer al sujeto solicitante final.

- El usuario ejecuta una aplicación en su dispositivo, a la cual su sistema operativo (SO) anfitrión le asigna un conjunto de identificaciones de proceso (IDs).

- Uno de esos IDs de proceso, para un hilo particular, realiza llamadas al sistema para solicitar una conexión a la base de datos remota en el servidor; esto involucra a otros IDs de proceso que realizan estos servicios en nombre del proceso solicitante.

- El servidor recibe esa solicitud de conexión remota y las solicitudes de acceso a datos subsiguientes.

Para mantener la seguridad de los datos en el servidor, ese sistema de gestión de bases de datos necesita recibir un conjunto de credenciales que esencialmente digan: “El usuario con ID X, que ha sido reconocido y aprobado para acceder en su propio sistema, está solicitando acceso a estos registros y campos de datos, para que pueda realizar estas acciones CRUD. ¿Puedes aprobar?”





**Opciones de Administración de IAM**

La información y la administración de la información son clave para la gestión de los sistemas de control de acceso (AC) de una organización. La información puede asociarse con sistemas de AC tanto lógicos como físicos. Ya sea un sistema de acceso lógico o físico, el control de ese sistema se mantiene en algún lugar como datos discretos o información, o ambos. La gestión de la información relacionada con el acceso físico y lógico se lleva a cabo de tres maneras principales: centralizada, descentralizada e híbrida.

**Centralizada.** La administración centralizada significa que una función es responsable de configurar los ACs para que los usuarios puedan acceder a los datos y realizar actividades relevantes. A medida que cambian las necesidades de procesamiento de información de los usuarios, su acceso solo puede modificarse a través de la administración central, generalmente después de que las solicitudes hayan sido aprobadas mediante un procedimiento establecido y por la autoridad correspondiente. Una ventaja de la administración centralizada es que se mantiene un control estricto sobre la información porque la capacidad de realizar cambios reside en unas pocas personas. La cuenta de cada usuario puede ser monitoreada centralmente, y cerrar el acceso de todos los usuarios puede lograrse fácilmente si ese individuo deja la organización. Los procedimientos y criterios consistentes y uniformes generalmente no son difíciles de hacer cumplir, ya que relativamente pocas personas supervisan el proceso.

Las implementaciones de AC centralizado requieren que todas las acciones de autenticación y autorización sean manejadas por el sistema de AC central. Desde una perspectiva, esto es una ventaja, ya que las actualizaciones de identidades y privilegios están disponibles inmediatamente para su uso en todos los nodos dentro de las redes de la organización. Esto también puede imponer demandas de rendimiento sustanciales en ese sistema de AC.

**Descentralizada.** En contraste con la administración centralizada, la administración descentralizada o distribuida significa que el acceso a la información es controlado por los propietarios o creadores de los archivos, sean quienes sean o estén donde estén esos individuos. Una ventaja de la administración descentralizada es que el control está en manos de las personas más responsables de la información, más familiarizadas con ella y mejor capaces de juzgar quién debería poder hacer qué en relación con ella. Una desventaja, sin embargo, es que puede no haber consistencia entre los creadores/propietarios sobre los procedimientos y criterios para otorgar acceso y capacidades a los usuarios. Otra desventaja es que cuando las solicitudes no se procesan centralmente, puede ser más difícil formar una vista general del acceso de todos los usuarios en el sistema en un momento dado. Diferentes propietarios de datos pueden implementar inadvertidamente combinaciones de acceso que introducen conflictos de intereses o no están en el mejor interés de la organización. También puede ser difícil asegurar que el acceso se termine correctamente cuando un empleado se transfiere dentro o deja una organización.

Los sistemas de AC descentralizados o distribuidos pueden proporcionar mayores niveles de tolerancia a fallos, especialmente para arquitecturas empresariales grandes y dispersas geográficamente. También pueden proporcionar mejores tiempos de respuesta en comparación con los sistemas centralizados, ya que tienden a estar sirviendo a un número mucho menor de sistemas clientes (es decir, cualquier sistema que solicite una acción de autenticación o autorización). También puede tomar bastante tiempo, tal vez hasta 24 a 48 horas, para actualizar las bases de datos de AC en todos los servidores del sistema. Esta latencia puede permitir una ventana de oportunidad para que un atacante intente usar privilegios que la administración ha decidido revocar, pero que no todos los nodos en el sistema de AC han llevado a cabo.

**Híbrida.** En un enfoque híbrido, se ejerce control centralizado para cierta información y se permite control descentralizado para otra información. Una disposición típica es que la administración central sea responsable del acceso más amplio y básico, y los creadores/propietarios de archivos controlen los tipos de acceso o las habilidades de los usuarios para los archivos bajo su control. Por ejemplo, cuando se contrata a un nuevo empleado en un departamento, un administrador central podría proporcionar al empleado permisos de acceso basados en el elemento funcional al que están asignados, la clasificación del trabajo y la tarea específica para la que fueron contratados. El empleado podría tener acceso solo de lectura a una biblioteca de documentos de SharePoint de toda la organización y a archivos de informes de estado del proyecto, pero el mismo empleado podría tener privilegios de lectura y escritura en el informe semanal de actividades de su departamento. Además, si el empleado deja un proyecto, el gerente del proyecto puede cerrar fácilmente el acceso de ese empleado a ese archivo.

**Control de Acceso como un Sistema**

Los sistemas de AC se construyen utilizando las tres categorías de controles de seguridad. Los controles administrativos, que son las políticas, directivas, procedimientos, programas de capacitación y educación, estándares y requisitos de cumplimiento orientados a las personas, impulsan el diseño de flujos de trabajo y procesos para asegurar que se cumplan las necesidades de seguridad. A partir de esta base de diseño, los profesionales de seguridad y sistemas eligen la combinación correcta de controles físicos y lógicos o técnicos. Esto puede verse en muchas de las publicaciones de NIST, ISO y otras sobre sistemas de AC que se refieren tanto a políticas y procedimientos como a dispositivos y sistemas de reglas implementados en software.

Los sistemas de AC físicos guían, previenen o permiten el movimiento de usuarios y dispositivos dentro de un espacio definido, como parte de un enfoque sistemático de la seguridad y la gestión de riesgos. El ejemplo más simple de un sistema de AC físico es una puerta que se puede cerrar con llave, limitando a las personas a un lado de la puerta o al otro. Los controles de acceso lógico funcionan dentro de los flujos de datos e información del propio sistema. El proceso de inicio de sesión del usuario demuestra un control lógico en operación: toma los flujos de datos generados o desencadenados por acciones físicas realizadas por el usuario (por ejemplo, pulsaciones de teclas y movimientos del ratón) y procesa esos datos para determinar si se concede o deniega al usuario el permiso para avanzar lógicamente al siguiente paso impulsado por el software que desea realizar.

Una tarjeta inteligente, un controlador de entrada física, proporciona un ejemplo de una combinación de controles físicos y lógicos. El dispositivo lector de tarjetas en la puerta no opera directamente las cerraduras o los mecanismos de liberación de la puerta; en su lugar, los datos leídos de la tarjeta, y tal vez otros datos ingresados por el usuario, se envían a través de una conexión de red a un servidor de AC. Ese servidor determina si se debe conceder este intento de acceso específico, basado en su base de reglas almacenada y otros parámetros. Luego, responde al controlador de entrada con los comandos para abrir la puerta, o para denegar la entrada y tal vez tomar otra acción. Como parte de su función de contabilidad, el servidor de AC registra el intento y sus decisiones resultantes; el controlador de entrada toma nota en sus propios archivos de registro.

Antes de la selección e implementación del tipo de AC lógico, el propietario de los datos necesita clasificar y categorizar su información. Cada uno de estos procesos complementarios identifica el tipo de protección (en términos de CIANA+PS) que los diseñadores del sistema y los profesionales de seguridad necesitan proporcionar y hasta qué punto, para satisfacer las necesidades generales de gestión de riesgos de información de la organización. Este paso debe ser el primero. Las pequeñas y medianas empresas a menudo procrastinan cuando se trata de un enfoque basado en el riesgo para el control de acceso, pensando que agrega demasiado tiempo de análisis, esfuerzo y costo; esto no tiene por qué ser el caso.





Varias fuentes, como las que se encuentran en la hoja de ruta del Gobierno Federal de los EE. UU. para la Gestión de Identidad, Credenciales y Acceso (FICAM, por sus siglas en inglés), definen a un sistema de control de acceso como:

* Autorizar o denegar el uso para un usuario individual.
* Autorizar o permitir a un usuario individual.
* Se basan en que el usuario tenga una identidad registrada y aprobada por el sistema.
* Utilizan recursos de sistemas de información, como terminales, estaciones de trabajo, redes de comunicaciones, aplicaciones o software del sistema o datos.
* Para el uso con este acceso, conceder instancias de los permisos registrados para esta identidad.


Además, estas fuentes pueden contener orientación sobre la implementación de estas tareas, que son reconocibles como las etapas en el ciclo de vida de la gestión de identidades, que es el enfoque del Dominio 5.5. Algunas de las tecnologías utilizadas para implementar estos controles se discuten en la siguiente sección.

Estas definiciones corren el riesgo de difuminar dos tareas principales: la gestión de identidades y el control de acceso. Como muchos de nosotros sabemos por experiencia personal, aunque somos una persona única, tenemos muchas identidades digitales diferentes, algunas de las cuales pueden ser aceptadas para propósitos de autenticación por algunos sistemas pero no por otros. Esos sistemas luego asumen las tareas separadas pero vitales de autorizar nuestros intentos de acceder a los recursos.

Debido al volumen de usuarios remotos, muchos entornos de sistemas requieren un sistema de AC lógico mucho más complejo y matizado que el necesario para controlar el acceso físico. Como ilustra el ejemplo de entrada con tarjeta inteligente, ambos tipos de sistemas deben colaborar para lograr una seguridad general efectiva, pero es claramente más simple, en principio, restringir el movimiento físico y las acciones de las personas que controlar las muchas formas diferentes de acceso remoto, uso compartido de recursos y entornos de colaboración.

Muchos controles de acceso lógico están integrados en el sistema operativo o pueden diseñarse como características de plataformas de aplicaciones o utilidades importantes, como los sistemas de gestión de bases de datos (DBMS). Pueden implementarse con paquetes de seguridad adicionales instalados en el sistema operativo. Dichos paquetes están disponibles para varios sistemas, como PC y mainframes. Además, los controles de acceso lógico pueden estar presentes en componentes especializados que regulan las comunicaciones entre computadoras y redes.


**Control de Acceso Lógico**

Considerando los datos críticos gestionados por Aeros 3 y sus amplios sistemas que a menudo son accedidos de forma remota, Tamika debe evaluar una amplia gama de controles para asegurar el acceso seguro a la información, sistemas, dispositivos, aplicaciones y otros activos.

**Pregunta de Ensayo**

**Pregunta 1**

(5.1.1-6) ¿Cómo podría Tamika abordar los controles de acceso lógico para asegurar que solo el personal autorizado tenga acceso apropiado a diferentes categorías de activos, equilibrando las necesidades de seguridad y operativas?


