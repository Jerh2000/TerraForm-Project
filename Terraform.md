# INFRAESTRUCTURA COMO CÓDIGO: TERRAFORM

## PRESENTADO POR:
### JAIRO ELIÉCER ROJAS HERRERA
### EMILY VANESSA VANEGAS VILLAFAÑE
### CANDELARIA FLÓREZ PALENCIA
### JOHAN ENRIQUE SUÁREZ MARTINEZ


## DIRIGIDO AL DOCENTE: RONALD ENRIQUE CUELLO MEZA


## ASIGNATURA: SISTEMAS DISTRIBUIDOS


## FUNDACIÓN UNIVERSITARIA TECNOLÓGICO COMFENALCO
## FACULTAD DE INGENIERÍA
## INGENIERIA DE SISTEMAS
## SEMESTRE 9
## SECCIÓN 9


## CARTAGENA DE INDIAS, BOLÍVAR, 16 DE MAYO 2022

##
##
# Infraestructura Como Código: Terraform

## ¿Qué es la Infraestructura como código?

La infraestructura como código se refiere al aprovisionamiento y la gestión de la infraestructura, incluido el hardware, los recursos virtuales, las plataformas, los sistemas de contenedores, los servicios y las topologías, mediante definiciones declarativas o de guión (código) en lugar de, mediante la configuración manual o el uso de herramientas de configuración tradicionales. La IaC separa las configuraciones, las políticas, los perfiles, los guiones y las plantillas del hardware o el software en el que se implementan para que puedan almacenarse, compartirse, revisarse y aplicarse como puede hacerse con el código.

Este enfoque, que ha crecido con la popularidad de las infraestructuras de la nube, surge a partir de la mentalidad de DevOps y aplica a la orquestación de la infraestructura el mismo tipo de control de versiones y de repetibilidad que los desarrolladores utilizan para el código fuente de las aplicaciones. Un enfoque IaC apoya la integración, entrega e implementación continuos, creando el mismo entorno de infraestructura cada vez que se aplica.

![Infraestructura como Codigo](/images/IaC.jpg)
_Figura 1: La IaC separa los recursos de configuración del hardware o el software para que puedan almacenarse, compartirse y gestionarse como el código_

## ¿Qué es Terraform?

Terraform es una herramienta de aprovisionamiento de servidores. Cuando se trata de Terraform, no se está ligado a una imagen de servidor, sino a una infraestructura completa que puede contener servidores de aplicaciones, bases de datos, servidores CDN, balanceadores de carga, cortafuegos y otros. Mientras que las herramientas de administración de configuración aseguran que cada servidor individual esté en el estado deseado, una herramienta de aprovisionamiento de servidores como Terraform asegura que la infraestructura en su conjunto esté en el estado deseado.

Terraform es una herramienta gratuita y de código abierto creada por HashiCorp y escrita en el lenguaje de programación Go. Puede ser usado para aprovisionar infraestructuras enteras que se extienden a través de múltiples proveedores de nubes públicos y privados como AWS, Google Cloud, Microsoft Azure, OpenStack y otros. Gestiona los recursos externos (dispositivos de red, software como servicio, plataforma como servicio, etc.) con «proveedores».

Básicamente, Terraform permite a los programadores construir, cambiar y versionar la infraestructura de forma segura y eficiente. Terraform puede ayudar con la multinube teniendo un flujo de trabajo para todas las nubes. Terraform trata la infraestructura como código (IaC), es el ejemplo de la próxima generación de sistemas de orquestación de configuración que trae una nueva capa de características y funcionalidades a la mesa.

Terraform es una aplicación con estado. Lo que significa que mantiene un registro de todo lo que construye en sus entornos de nubes, de modo que si necesitas cambiar algo o eliminar algo más tarde, Terraform sabrá lo que construyó, y puede volver y hacer esos cambios por ti.

## Conceptos de Terraform
A continuación se muestran los conceptos / terminologías centrales que se utilizan en Terraform:

- **Variables:** También se utiliza como variables de entrada, es un par clave-valor utilizado por los módulos Terraform para permitir la personalización.
  
- **Provider:** Es un complemento para interactuar con las API de servicio y acceder a sus recursos relacionados.
  
- **Módulo:** Es una carpeta con plantillas Terraform donde se definen todas las configuraciones.
  
- **Estado:** Consiste en información en caché sobre la infraestructura administrada por Terraform y las configuraciones relacionadas.
  
- **Recursos:** Se refiere a un bloque de uno o más objetos de infraestructura (instancias de cómputo, redes virtuales, etc.), que se utilizan para configurar y administrar la infraestructura.
  
- **Fuente de datos:** Los proveedores lo implementan para devolver información sobre objetos externos a terraform.
  
- **Valores de salida:** Estos son valores de retorno de un módulo terraform que pueden ser utilizados por otras configuraciones.
  
- **Planificar:** Es una de las etapas en las que determina qué se debe crear, actualizar o destruir para pasar del estado real / actual de la infraestructura al estado deseado.
  
- **Aplicar:** Es una de las etapas donde se aplican los cambios de estado real / actual de la infraestructura para pasar al estado deseado.


## Ciclo de vida de Terraform
El ciclo de vida de Terraform consiste en: `init`, `plan`, `apply` y `destroy`.

![Ciclo de vida](/images/lifecycle.png)

- **Terraform Init** inicializa el directorio de trabajo que consta de todos los archivos de configuración.

- **Terraform Plan** se utiliza para crear un plan de ejecución para alcanzar el estado deseado de la infraestructura. Los cambios en los archivos de configuración se realizan para lograr el estado deseado.


- **Terraform Apply** luego realiza los cambios en la infraestructura tal como se define en el plan, y la infraestructura llega al estado deseado.
 
- **Terraform Destroy** se utiliza para eliminar todos los recursos de infraestructura antiguos, que están marcados como contaminados después de la fase de aplicación.

## ¿Por qué Terraform?

Existen algunas razones clave por las que los desarrolladores eligen utilizar Terraform sobre otras herramientas de infraestructura como código:

- **Código abierto:** Terraform está respaldado por grandes comunidades de colaboradores que crean complementos (plugins) para la plataforma. Independientemente del proveedor de nube que utilice, es muy sencillo encontrar complementos, extensiones y soporte profesional. Esto significa que Terraform también evoluciona rápidamente, con nuevos beneficios y mejoras añadidas constantemente.
  
- **Independiente de la plataforma:** Es decir, puede utilizarlo con cualquier proveedor de servicios de la nube. La mayoría de otras herramientas de IaC están diseñadas para funcionar con un solo proveedor de nube.
  
- **Infraestructura inmutable:** La mayoría de las herramientas de infraestructura como código crean una infraestructura mutable, lo que significa que esta puede cambiar para adaptarse a cambios, como una actualización de middleware o un nuevo servidor de almacenamiento. El peligro con la infraestructura mutable es el desvío de la configuración, a medida que los cambios se acumulan, el suministro real de diferentes servidores u otros elementos 'se desvían' más allá de la configuración original, haciendo que los errores o problemas de rendimiento sean difíciles de diagnosticar y corregir. Terraform suministra una infraestructura inmutable, lo que significa que con cada cambio en el entorno, la configuración actual se sustituye por una nueva que aplica el cambio y se vuelve a suministrar la infraestructura. Y lo que es aún mejor, las configuraciones anteriores se pueden conservar como versiones para habilitar las restauraciones a un estado previo, si es necesario o si así se desea.


## ¿Cómo funciona Terraform?
Terraform tiene dos componentes principales que conforman su arquitectura:
- Nucleo de Terraform
- Proveedores

![Arquitectura](/images/arquitectura.png)

### Núcleo de Terraform
Terraform core utiliza dos fuentes de entrada para hacer su trabajo.

La primera es la fuente de entrada es una *configuración de Terraform* que usted, como usuario, configura. Aquí, usted define lo que debe crearse o aprovisionarse. Y la segunda fuente de entrada es un *estado* en el que terraform mantiene el estado actualizado de cómo se ve la configuración actual de la infraestructura.

Entonces, lo que hace Terraform core es tomar la información y determinar el plan de lo que se debe hacer. Compara el estado, cuál es el estado actual y cuál es la configuración que desea en el resultado final. Averigua qué se debe hacer para llegar al estado deseado en el archivo de configuración. Calcula lo que se debe crear, lo que se debe actualizar, lo que se debe eliminar para crear y aprovisionar la infraestructura.

### Proveedores
El segundo componente de la arquitectura son los proveedores de tecnologías específicas. Esto podría ser proveedores de nube como AWS, Azure, GCP u otra infraestructura como plataforma de servicio. También es un proveedor de componentes de más alto nivel como Kubernetes u otras herramientas de plataforma como servicio, incluso algún software como herramienta de autoservicio.

Terraform tiene más de cien proveedores para diferentes tecnologías, y cada proveedor luego brinda acceso de usuario de terraform a sus recursos. Entonces, a través del proveedor de AWS, por ejemplo, tiene acceso a cientos de recursos de AWS como instancias EC2, los usuarios de AWS, etc. Con el proveedor de Kubernetes, tiene acceso a productos básicos, recursos como servicios e implementaciones y espacios de nombres, etc.


## Beneficios de Terraform
Los principales beneficios que nos proporciona Terraform son:

- Admite crear infraestructuras en gran cantidad de proveedores.
  
- Nos permite administrar tanto infraestructuras grandes como una sola aplicación.

- Proporciona una sintaxis fácil y única que permite administrar casi cualquier recurso independientemente de la plataforma y servicio.

- Los ficheros de Terraform pueden ser compartidos y reutilizables para generar nuevos entornos y ser fácilmente exportables a otros clientes.

- Los modelos de datos pueden ser versionados, y de esta forma muy sencilla observar el progreso de nuestro servicio.

- También nos permite controlar los cambios en la infraestructura de manera simple y ágil.


## Casos de uso de Terraform

- Es una práctica común tener tanto un entorno de producción como de puesta en escena o de control de calidad. A medida que el entorno de producción crece y se hace más complejo, se hace cada vez más oneroso mantener un entorno de puesta en escena actualizado. Usando Terraform, el entorno de producción puede ser codificado y luego compartido con la puesta en escena.  Estas configuraciones pueden ser usadas para crear rápidamente nuevos entornos para probar y luego ser fácilmente eliminados. Terraform puede ayudar a domar la dificultad de mantener entornos paralelos, y hace que sea práctico crearlos y destruirlos de forma elástica.

- A un cierto tamaño de organización, se convierte en un gran desafío para un equipo de operaciones centralizado gestionar una infraestructura grande y creciente. En cambio, resulta más atractivo hacer una infraestructura de «autoservicio», permitiendo a los equipos de producto gestionar su propia infraestructura utilizando las herramientas proporcionadas por el equipo central de operaciones. Utilizando Terraform, el conocimiento de cómo construir y escalar un servicio puede ser codificado en una configuración. Las configuraciones de Terraform pueden ser compartidas dentro de una organización permitiendo a los equipos de clientes utilizar la configuración como una caja negra y utilizar Terraform como una herramienta para gestionar sus servicios.


## Terraform VS Otros
### Terraform frente a Kubernetes
Es común que exista confusión entre Terraform y Kubernetes, y lo que realmente hace cada uno de ellos. La verdad es que no son alternativas y realmente trabajan juntos de manera efectiva.

Kubernetes es un sistema de orquestación de contenedores de código abierto que permite a los desarrolladores planificar implementaciones en nodos de un clúster de computación y gestionar activamente cargas de trabajo contenerizadas, y garantizar que su estado coincida con las intenciones de los usuarios.

Terraform, por otro lado, es una herramienta de Infraestructura como código con un alcance mucho más amplio, que permite a los desarrolladores automatizar una infraestructura completa que abarca múltiples nubes públicas y privadas.

Terraform puede automatizar y gestionar la Infraestructura como servicio (IaaS), la o incluso funcionalidades a nivel de Software como servicio (SaaS) y crear todos estos recursos en todos los proveedores en paralelo. Se puede utilizar Terraform para automatizar el suministro de Kubernetes, en particular, clústeres de Kubernetes gestionado en plataformas de la nube, y para automatizar la implementación de aplicaciones en un clúster.

### Terraform frente a Ansible

Terraform y Ansible son herramientas de Infraestructura como código, pero hay un par de diferencias significativas entre las dos:

Mientras que Terraform es puramente una herramienta declarativa, Ansible combina la configuración declarativa y procedimental. En la configuración procedimental, el usuario especifica los pasos o la forma precisa en la que quiere suministrar la infraestructura al estado deseado. La configuración procedimental significa más trabajo, pero brinda más control. Además, Terraform es de código abierto; Ansible es una herramienta desarrollada y vendida por Red Hat.

#### Orquestación frente a gestión de configuración
Ansible es un herramienta de gestión de la configuracióny Terraform es una herramienta de orquestación. Ésta es la diferencia más fundamental entre Terraform y Ansible. Aunque algunas de las características son comunes entre estas herramientas, siguen siendo diferentes entre sí.

Ansible se usa para agregar, actualizar, eliminar y administrar la configuración de la infraestructura de TI, mientras que Terraform se usa para declarar componentes de infraestructura y organizarlos en múltiples proveedores de nube.

#### Procesal vs declarativo
Terraform utiliza un lenguaje de configuración declarativo para declarar los recursos de la infraestructura de TI. Ansible utiliza lenguajes de procedimiento y declarativos para la gestión de la configuración. La forma de procedimiento se utiliza en Ansible para ejecutar comandos ad-hoc y alcanzar la configuración de infraestructura deseada. Los módulos ansible utilizan un enfoque declarativo.

#### Infraestructura mutable versus inmutable
Puede crear infraestructura mutable usando Ansible e infraestructura inmutable usando Terraform. Ansible gestiona y configura el software de la infraestructura en el mismo servidor. Cuando empuja más actualizaciones de configuración, el entorno de producción se vuelve complejo y da lugar a muchos errores que son difíciles de identificar y corregir.

Terraform utiliza principalmente una nueva Imagen docker para cualquier implementación en el servidor. Terraform crea una nueva imagen de la ventana acoplable para actualizar cualquier software en la infraestructura, implementa esa imagen en todos los servidores y elimina la imagen de la ventana acoplable de configuración anterior. Entonces, incluso después de múltiples actualizaciones de configuración, el entorno permanece estable.

#### Maestro contra sin maestro
Ansible tiene una arquitectura de máquina maestra responsable de almacenar el estado completo de la infraestructura e impulsar las nuevas actualizaciones de configuración en los servidores remotos. Es por eso que se denomina modelo de implementación basado en push en ansible.

En Terraform, no hay un sistema maestro separado. Sin embargo, cuando trabaja con proveedores en la nube como AWS a través de las API, el servidor de API es la máquina maestra en ese caso.



## Referencias
- _[1] Gutiérrez. A(2017). ¿Por qué usar Terraform?.Open Webinars Recuperado de: https://openwebinars.net/blog/por-que-usar-terraform/_
  
- _[2] Avi(2022). Una introducción a Terraform para principiantes – Tutorial de Terraform. Geekflare. Recuperado de: https://geekflare.com/es/terraform-for-beginners/_
  
- _[3] Deloitte(2021). ¿Qué es Terraform?. Deloitte. Recuperado de: https://www2.deloitte.com/es/es/blog/todo-tecnologia/2021/que-es-terraform.html_

- _[4] IBM Cloud Education(2020). TerraForm.IBM. Recuperado de: https://www.ibm.com/co-es/cloud/learn/terraform_
  
- _[5] Rodríguez. A(2022).Terraform como herramienta para la automatización de infraestructuras. Decide. Recuperado de:https://decidesoluciones.es/terraform-automatizacion-de-infraestructuras/_

- _[6] Novoseltseva. E(2020).Beneficios Y Casos De Uso De Terraform. Apiumhub. Recuperado de: https://apiumhub.com/es/tech-blog-barcelona/beneficios-y-casos-de-uso-de-terraform/_

- _[7] Valero. E(2017). Terraform, la navaja suiza para dominar todos los IaaS. Paradigma. Recuperado de: https://www.paradigmadigital.com/dev/terraform-la-navaja-suiza-dominar-todos-los-iaas/_

- _[8] Alvarado. G(2019). Tutorial: Infraestructura como código con Terraform. Galvarado. Recuperado de: https://galvarado.com.mx/post/tutorial-infraestructura-como-c%C3%B3digo-con-terraform/_

- _[9] Deloitte(2021). Los beneficios de utilizar Terraform. Deloitte. Recuperado de: https://www2.deloitte.com/es/es/blog/todo-tecnologia/2021/los-beneficios-de-utilizar-terraform.html_

- _[10] Avi(2022). Comprensión de las herramientas de DevOps: Ansible y Terraform. Geekflare. Recuperado de: https://geekflare.com/es/devops-tools-ansible-and-terraform/_

- _[11] F5 Glosary(2021). ¿Qué es la infraestructura como código?. F5 Glosary. Recuperado de: https://geekflare.com/es/devops-tools-ansible-and-terraform/_

