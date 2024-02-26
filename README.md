# Find-values-in-Dataframe

Encontrando valores de una columna especifica, en otro documento utilizando dataframes en pandas.

Para este ejercicio utilizamos la libreria Pandas.

Una funcion de pandas con la que podemos validar si los datos de un Dataframe estan en otro dataframe es **_isin()_**, devuelve el valor True cuando los valores son idénticos, o False en el caso de falta de coincidencia.

En esta linea validamos si los valores en la columna Job Data de df_2 también están presentes en la columna job_name de df_1.

    mask = df_2['col_name'].isin(df_1['col_name'])


Utilizando la variable mask filtramos el DataFrame df_1. 

El resultado son las filas donde el valor en la columna del df_1 coincide con un valor en la columna del df_2, es decir todos los valores que fueron identificados como True por la función.

    val found = df_1[df_1['col_name'].isin(df_2['col_name'][mask])]

Para visualizar los resultados podemos simplemente guardar los resultados en un nuevo dataframe, ocultando el indice de los resultados.

    val found.to_csv('val_found.csv', index=False)


Listo ya podemos entregar los datos.

(:


## Pero... ¿Si ahora necesito los que no estan? 😮

Utilizamos el operador bitwise **~** para invertir la máscara booleana (mask). Como resultado tenemos una nueva máscara que indica las filas donde el valor en la columna del df_2 no está presente en la columna del df_1.

    not_in = ~mask

El operador bitwise NOT, invierte el valor booleano de cada elemento en la _var_ mask.

Asi que para terminar Optimizamos 🐱‍💻 el codigo de la linea donde filtramos los resultados de nuestra mask, para hacerlo mas simple. 

    not_found = df_2[not_in]

Guarda el dataframe filtrado como un nuevo archivo CSV

    not_found.to_csv('not_found.csv', index=False)





