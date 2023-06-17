# reto
Retointecorp
Contiene las definiciones de API rest customer y de los microservicios para crearcliente, obtener kpi de clientes y listado de clientes.
Se adjunta propuesta de diagramas de arquitectura para un escenario utilizando Azure Cloud y AWS.

Estructura de entregables:

1) En archivo CustomerManagement.yaml se encuentra la definición del api rest documento en swagger indicando el dominio de negocio alineado    a BIAN : Customer Management.  
   En el yaml se detalla que se tendrá un api management de azure el cual tiene la siguiente nomenclatura:
   apim-ginr-dev-backend-001.azure-api.net/customer-management-api donde :
   *apim: api management,
   *ginr: grupo intercorp retail,
   *dev: ambiente de despliegue,
   *backend: destino de conexión.En este caso el back es una BD Azure SQL.
   
2) En el archivo MIC-Customers.yaml se encuentra el microservicio que contiene los 3 endpoints: create(crea cliente), kpiclientes,listclientes.
En cada microservicio se ha incluido unos headers a modo de tener un estándar para consumir los microservicios:
consumer-id: Aquí iría el canal o aplicativo consumidor,
country-id: Id del país al que pertenece el servicio.Iría PE por default,
destinationCountry-id: Id del país destino. Ejm: PE.

Los endpoints a consumir serían los siguientes:

Creación de cliente :https://dev-service-back.reto.pe/customer-management/customers/v1.0/create ,
KPI de Clientes:  https://dev-service-back.reto.pe/customer-management/customers/v1.0/kpiclientes ,
Lista de Clientes https://dev-service-back.reto.pe/customer-management/customers/v1.0/listclientes ,


3) En archivo Diagrama Microservicios.drawio se encuentra las dos propuestas de arquitectura utilizando el cloud azure y aws cloud. Se considera una capa de seguridad que cumpla función de WAF y a la vez una propuesta para poder consumir los microservicios desde un canal sería generar un token de acceso, aquí se ha incluido generarlo por los servicios que tienen de directorio activo tanto azure como aws. En el caso de Azure sería Azure Active Directory y en el caso de AWS sería AWS Directory Service.

4) El excel anexo contiene como sería la distribución de tablas en la base de datos SQL Server de Azure y las respuestas que se obtendrían al consumir los endpoints de los microservicios.
 4.1) 
