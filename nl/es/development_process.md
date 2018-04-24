---

copyright:
  years: 2018
lastupdated: "2018-03-16"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Fases recomendadas para el desarrollo en la nube
{: #development_process}

Los desarrolladores de apps en la nube recorren cuatro fases fundamentales en el proceso de desarrollo: inicio, codificación, entrega y gestión. El flujo es interactivo y rápido. El objetivo es crear rápidamente una app mínima viable, y luego utilizar la información proveniente de la app de producción para iterar de forma continua el código o el ciclo de entrega hasta que su app se adecúe a los usuarios.
{: shortdesc}

![Flujo de desarrollo](images/dev_flow_overview.png "Flujo de desarrollo") Figura 1. Fases del proceso de desarrollo.

En algunos casos, se llama a la fase de "Ejecutar" como una fase distinta, pero aquí la combinamos con las fases de Entregar y Gestionar.

Ahora vamos a ver con algo más de detalle la mejor manera de utilizar {{site.data.keyword.cloud_notm}} en el flujo de desarrollo.

##Iniciación
{: #get_started}

Empiece a crear su app a partir de los paneles de control de desarrollador de {{site.data.keyword.cloud_notm}}, donde se puede seleccionar un kit de iniciación relacionado con su caso de uso. Elija también un lenguaje de programación. {{site.data.keyword.cloud_notm}} utiliza las indicaciones del kit de iniciación para suministrar automáticamente los recursos que necesita y para crear un proyecto de app independiente del tiempo de ejecución específico del lenguaje y que es la base de su app de producción. Para completar la fase de iniciación, pulse **Desplegar en la nube** desde el panel de control de desarrollador. Una pulsación crea una cadena de herramientas de DevOps completa con un repositorio de código que se cumplimenta con el código fuente de su app y un conducto de despliegue.

![Iniciación](images/dev_get_started.png "Iniciación") Figura 2. Flujo de iniciación

Cuando utilice el botón **Desplegar en la nube** para configurar su cadena de herramientas de DevOps, seleccione su plataforma de tiempo de ejecución, por ejemplo, Kubernetes o Cloud Foundry. La app de inicio creada para {{site.data.keyword.cloud_notm}} es independiente del entorno de tiempo de ejecución y no necesita ser modificada.
{: tip}

##Desarrollo local
{: #develop_locally}

Después de crear su cadena de herramientas y proyecto de app de inicio, iniciará su desarrollo de forma local. Clone el código desde el repositorio en una estación de trabajo local e impórtela en su IDE. Utilice {{site.data.keyword.dev_cli_notm}} para crear, ejecutar y probar su app en la nube en su máquina local. {{site.data.keyword.dev_cli_notm}} crea y gestiona un contenedor local en su nombre. Cuando esté listo para ver su app en ejecución en la nube, envíe por push su código al repositorio en la nube y fusione sus cambios.

![Desarrollo local](images/dev_code_locally.png "Desarrollo local") Figura 3. Flujo de desarrollo local

Las funciones básicas para {{site.data.keyword.dev_cli_notm}} son `bx dev build` y `bx dev run`, sin embargo, la interfaz de línea de mandatos (CLI) ofrece mucho más. Consulte [{{site.data.keyword.dev_cli_notm}}](../cli/idt/index.html) para obtener más detalles.
{: tip}

##Gestión y entrega en {{site.data.keyword.cloud_notm}}
{: #deliver_and_manage}

La fusión de los cambios en su repositorio en la nube inicia un ciclo de compilación y despliegue en la cadena de herramientas de DevOps que ha creado con anterioridad. Su app se estará ejecutoriado en la nube al cabo de unos minutos.

Para comprobar el estado de su conducto de DevOps, utilice el panel de control Conducto de entrega. Para comprobar el estado general de su app, consulte el panel de control de {{site.data.keyword.cloud_notm}} de su cuenta.
{: tip}

La cadena de herramientas que se crea al inicio tiene los componentes básicos necesarios para una entrega continua que se basa en la colaboración con su equipo. Sin embargo, {{site.data.keyword.cloud_notm}} ofrece un amplio conjunto de servicios de DevOps que puede añadir a su cadena de herramientas para mejorar la entrega, la supervisión, la creación de registros y alertas.

![Entrega y gestión](images/dev_deliver_and_manage.png "Entrega y gestión") Figura 4. Flujo de entrega y gestión.

Obtenga más información sobre la [entrega continua en {{site.data.keyword.cloud_notm}}](../services/ContinuousDelivery/index.html#cd_getting_started).

## Recopilación

![Detalles del proceso](images/dev_process_detail.png "Detalles del proceso") Figura 5. Proceso de desarrollo de principio a fin.