# Find-values-in-Dataframe

Encontrando valores de una columna especifica, en otro documento utilizando dataframes en pandas.

Para este ejercicio utilizamos la libreria Pandas.

Una funcion de pandas con la que podemos validar si los datos de un Dataframe estan en otro dataframe es **_isin()_**, devuelve el valor True cuando los valores son idénticos, o False en el caso de falta de coincidencia.

En esta linea validamos si los valores en la columna Job Data de df_2 también están presentes en la columna job_name de df_1.

    mask = df_2['col_name'].isin(df_1['col_name'])


Utilizando esta variable mask filtramos el DataFrame df_1. El resultado son las filas de df_1 donde el valor en la columna job_name coincide con un valor en la columna Job Dataprco de df_2. 

    val found = df_1[df_1['col_name'].isin(df_2['col_name'][mask])]