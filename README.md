# PI02-DataPT08-JaredLuna (Data Analyst)

## Problemática
![image](https://github.com/soyHenry/PI_DA/assets/37918365/e7d2031f-753f-49f9-8ab4-ac2558338076)

Se nos plantea la problemática de que la coordinación de vialidad de Argentina quiere que le presentemos tres KPI’s diferentes. Ellos nos proporcionan una base de datos para su análisis, transformación y posteriormente presentación mediante PowerBI o alguna herramienta de BI para la presentación de los KPI’s propuestos.

Estos KPI’s son los siguientes:

- “Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.”
-	“Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.”
-	Proponer nosotros un KPI.

Así que primeramente nos vamos a centrar en utilizar la misma metodología de trabajo que se ha estado usando. Se realizará primeramente una EDA, luego la ETL y posteriormente se realizará el dashboard de PowerBI.

## EDA (Exploratory Data Analysis) 
Para este punto nos centramos en la lectura de nuestros datos, se nos proporcionaron dos archivos .csv que te tuvieron que leer con pandas y una codificación 'ISO-8859-1' por las palabras en español. Una vez leídos nuestros datos pudimos observar su contenido, dándonos una idea de la información que nos estaban proporcionando. Obtuvimos la información de los dataframes que para ver si tenían datos faltantes o nulos para su posterior tratamiento en la ETL.

Se realizaron unas cuantas gráficas para poder obtener un panorama más amplio de nuestra información, ir encontrando outliers e insights para poder definir mejor la propuesta de nuestro KPI. Los resultados de dichas gráficas se pueden observar en el notebook EDA.ipynb, ahí viene más detallada la información.
Una vez analizadas las gráficas, buscado valores faltantes y duplicados se procedió a la parte de la ETL. Cabe mencionar que la base de datos venía bastante prolija, por lo que las correcciones fueron mínimas en la ETL.

## ETL (Extract Transform Load)
Primeramente, se declaran las librerías con las que vamos a transformar nuestros datos, la cual en este caso solamente va a ser con Pandas. Leemos nuestros datos en un dataframe para empezar a trabajar con ellos y primeramente nos centramos en los datos faltantes. Como no deseábamos perder información se optó por todos aquellos datos vacíos rellenarlos con “SD” (sin dato) para conservar los demás datos de las demás columnas. Haciendo otro análisis de las demás columnas nos damos cuenta de que toda la información es pertinente para su uso tal y como esta, así que terminamos con esta parte para la base de hechos.

Para la base de datos de víctimas realizamos el mismo tratamiento, pero en este apartado tuvimos que agregar el separar unas fechas esto para tener un mejor control en los meses y años para la clasificación de datos.

Una vez realizado este tratamiento a nuestros datos se procedió a exportar nuestros datos a un formato parquet para tener un archivo más ligero y su posterior lectura en Power BI.

