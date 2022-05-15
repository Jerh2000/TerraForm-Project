# Infraestructura Como Codigo: TerraForm

## ¿Qué es la Infraestructura como codigo?

La infraestructura como código se refiere al aprovisionamiento y la gestión de la infraestructura, incluido el hardware, los recursos virtuales, las plataformas, los sistemas de contenedores, los servicios y las topologías, mediante definiciones declarativas o de guion (código) en lugar de mediante la configuración manual o el uso de herramientas de configuración tradicionales. La IaC separa las configuraciones, las políticas, los perfiles, los guiones y las plantillas del hardware o el software en el que se implementan para que puedan almacenarse, compartirse, revisarse y aplicarse como puede hacerse con el código.

Este enfoque, que ha crecido con la popularidad de las infraestructuras de la nube, surge a partir de la mentalidad de DevOps y aplica a la orquestación de la infraestructura el mismo tipo de control de versiones y de repetibilidad que los desarrolladores utilizan para el código fuente de las aplicaciones. Un enfoque IaC apoya la integración, entrega e implementación continuos, creando el mismo entorno de infraestructura cada vez que se aplica.

![Infraestructura como Codigo](/images/IaC.jpg)
_Figura 1: La IaC separa los recursos de configuración del hardware o el software para que puedan almacenarse, compartirse y gestionarse como el código_

## ¿Qúe es TerraForm?

Terraform es una herramienta de aprovisionamiento de servidores. Cuando se trata de Terraform, no se está ligado a una imagen de servidor, sino a una infraestructura completa que puede contener servidores de aplicaciones, bases de datos, servidores CDN, balanceadores de carga, cortafuegos y otros. Mientras que las herramientas de administración de configuración aseguran que cada servidor individual esté en el estado deseado, una herramienta de aprovisionamiento de servidores como Terraform asegura que la infraestructura en su conjunto esté en el estado deseado.

Terraform es una herramienta gratuita y de código abierto creada por HashiCorp y escrita en el lenguaje de programación Go. Puede ser usado para aprovisionar infraestructuras enteras que se extienden a través de múltiples proveedores de nubes públicos y privados como AWS, Google Cloud, Microsoft Azure, OpenStack y otros. Gestiona los recursos externos (dispositivos de red, software como servicio, plataforma como servicio, etc.) con «proveedores».

Básicamente, Terraform permite a los programadores construir, cambiar y versionar la infraestructura de forma segura y eficiente. Terraform puede ayudar con la multinube teniendo un flujo de trabajo para todas las nubes. Terraform trata la infraestructura como código (IaC), es el ejemplo de la próxima generación de sistemas de orquestación de configuración que trae una nueva capa de características y funcionalidades a la mesa.

Terraform es una aplicación con estado. Lo que significa que mantiene un registro de todo lo que construye en sus entornos de nubes, de modo que si necesitas cambiar algo o eliminar algo más tarde, Terraform sabrá lo que construyó, y puede volver y hacer esos cambios por ti.

## Conceptos de TerraForm
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

