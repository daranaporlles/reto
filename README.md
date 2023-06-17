# reto
Retointecorp
Contiene las definiciones de API rest customer y de los microservicios para crearcliente, obtener kpi de clientes y listado de clientes.
Se adjunta propuesta de diagramas de arquitectura para un escenario utilizando Azure Cloud y AWS.

Estructura de entregables:

1) En archivo CustomerManagement.yaml se encuentra la definición del api rest documento en swagger indicando el dominio de negocio alineado    a BIAN : Customer Management.  
   En el yaml se detalla que se tendrá un api management de azure el cual tiene la siguiente nomenclatura:
   apim-ginr-dev-backend-001.azure-api.net/customer-management-api donde :
   *apim: api management
   *ginr: grupo intercorp retail
   *dev: ambiente de despliegue
   *backend: destino de conexión, en este caso el back es una BD Azure SQL.
   
2) En el archivo MIC-Customers.yaml se encuentra el microservicio que contiene los 3 endpoints: create(crea cliente), kpiclientes,listclientes.
En cada microservicio se ha incluido unos headers a modo de tener un estándar para consumir los microservicios:
consumer-id: Aquí iría el canal o aplicativo consumidor,
country-id: Id del país al que pertenece el servicio.Iría PE por default.
destinationCountry-id: Id del país destino. Ejm: PE.
