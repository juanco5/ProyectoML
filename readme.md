# Proyecto de Machine Learning: Análisis del `salary_in_usd` de Profesionales en Data Science

## Introducción

En este proyecto, realizamos un análisis y modelado de los salarios (`salary_in_usd`) de profesionales en el campo de Data Science. Nuestro objetivo es identificar los factores que influyen en los salarios y construir modelos predictivos que puedan estimar el salario basado en diversas características. El objetivo es predecir con maximo un error del 10%.

## Descripción de los Datos

El conjunto de datos incluye información sobre profesionales de Data Science. Las columnas principales del dataset son:

- `work_year`: Año del dato recogido. 2022,2023,2024
- `experience_level`: Nivel de experiencia del profesional. (en=entry, mi=middle, se=senior, ex=Executive-level / Director)
- `employment_type	`: FL=freelance, pt=part time, ct=contrato por proyecto, ft=fulltime
- `job_title`: Nombre del puesto
- `salary_in_usd`: Salario
- `employee_residence`: Donde vive el empleado
- `remote_ratio`: Si trabajo online = 1. Presencial 0
- `company_location	`: Donde esta ubicada la empresa
- `company_size`: Tamaño empresa. S= small, M=middle, L=large


## Análisis Exploratorio de Datos

Realizamos un análisis exploratorio de datos (EDA) para entender mejor la distribución y relación entre las diferentes variables. 
- Vemos que columnas no son necesarias y pueden ser eliminadas.
- Vemos como pasar las columnas que estan en str a int para utilizarlas en nuestro modelo

## Modelos ML

Utilizamos varios modelos de Machine Learning para predecir el salary_in_usd. Los modelos evaluados incluyen:

- Regresión Lineal
- Random Forest
- XGBoost
- Polinomica

## Soluciones

Al ver que la prediccion del modelo tenia un error mucho más alto del que buscabamos al inicio del proyecto, vamos probando los modelos haciendo diferentes cambios en la limpieza de datos.

- ML_Definitivo_Ultimaversion: Modelo elegido. Es el que mejor predice
- ML_Definitivo2: Nos quedamamos solo con las columnas que mas correlacion tenian con el target: company_location y experience_level. Tambien con job_title ya que es necesario para luego predecir el target
- ML_Definitivo3: La columna job_title la agrupamos por la media de los salarios en vez de hacer dummies, para asi no tener tantas columnas.
- ML_Definitivo4: Hacemos el modelo solo para US que es de donde mas data tenemos, en vez de hacer un undersample. Aunque este modelo explica ligeramente mejor procentualmente no lo hace en valor absoluto y ademas solo vale para US por lo que lo descartamos
- ML_Definitivo5: eliminamos los outliers de las columnas que mejor predicen : company_location y experience_level



## Conclusiones

En este proyecto, hemos explorado y modelado los salarios de profesionales en Data Science. Identificamos los factores clave que influyen en los salarios y construimos modelos predictivos. El modelo predice con un error superior al que buscabamos e incluso despues de probar varias limpiezas no hemos podido disminuirlo. Posiblemente se debe a que los salarios dentro de este mismo sector para profesionales con unas caracteristicas similares pueden ser muy variados. 

## Pasos a seguir

Habria que ver si con otras features si se podria mejorar el modelo. 
Mirar si hay mas data al respecto.
