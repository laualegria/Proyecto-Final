# Proyecto-Final
#Google-Slides:
https://docs.google.com/presentation/d/1fCN5peVRIdFvjufWmUoP8ujwh57QBvNde12Nz6f5nl4/edit?usp=sharing
# Presentación: 
En esta presentación se elaboró un análisis acerca la predicción de ataques cardíacos en las personas, gracias a los datos obtenidos del dataset, a la limpieza de datos que se realizó mediante Python, y a la visualización de gráficos mediante Power BI la cual hace que los datos se vean organizados y le de una fácil lectura a la hora de analizarlos. 
# Objetivo:
El objetivo de este proyecto es elaborar un respectivo análisis sobre pacientes con predicción de ataques cardíacos mediante datos de historia familiar, exámenes médicos, entre otros, las cuales nos ayuda a predecir la probabilidad de que un paciente sufra un ataque cardíaco. 
# Descripción de la problemática:
El análisis y la predicción de ataques cardíacos es una tarea compleja ya que enfrenta múltiples desafíos y muchos factores de riesgo que pueden desencadenar un ataque cardíaco ya que La predicción de un ataque cardíaco no se puede reducir a un solo factor, porque es el resultado de una combinación de factores de riesgo, como la edad, el género, la presión arterial, el colesterol, la diabetes, el tabaquismo, la historia familiar y otros. Estas variables son interdependientes y pueden variar de una persona a otra.
# Datos utilizados:
Las herramientas que se utilizaron para la elaboración del proyecto fueron:
1. Kaggle:Se utilizó esta página para la elección de mi dataset.
2. Google Colab:Se utilizó esta herramienta para la limpieza del dataset.
3. Power BI desktop: Se utilizó esta herramienta para la visualización de los datos.
4. GitHub:Se utilizó esta herramienta para subir los archivos y cumplir con otros requisitos del proyecto. 
 # Resultados e interpretaciones [a través de Power BI]:
<img width="628" alt="image" src="https://github.com/laualegria/Proyecto-Final/assets/112332809/89c2b15e-9aec-4d2a-bff8-b84bb4208f71">
<img width="634" alt="image" src="https://github.com/laualegria/Proyecto-Final/assets/112332809/b22bbb11-c899-4888-81b2-8864c645270a">
<img width="631" alt="image" src="https://github.com/laualegria/Proyecto-Final/assets/112332809/0a532be2-57d7-4d36-a32f-8a5e1d767819">

IMAGEN 1: En la primera página del Power BI utilicé un mapa para visualizar la población de personas con predicción de ataque cardíaco por país y continente. 
IMAGEN 2: En la segunda página del Power BI utilicé una tabla para que se puedan analizar los datos de los pacientes, por ejemplo su edad, datos con algunas enfermedades, si tienen riesgos de ataque cardíaco, entre otros. Se agregó también dos tarjetas la cual una muestra el promedio de la actividad fisica y la otra muestra si hay riesgo de ataque cardíaco.
IMAGEN 3: En la tercera página del Power BI utilicé dos gráficos de anillos en el cual uno compara las horas de sueño por día entre el género masculino y femenino. Como se puede apreciar, el género femenino tiene menos horas de sueño que el género masculino. 
Y en el otro gráfico de anillos compara la suma de los días de actividad física por semana entre el género masculino y femenino. Como se puede apreciar, el género masculino realiza más ejercicio que el género femenino. 
*Utilicé un gráfico de barras agrupadas para comparar la obesidad por género.
*Utilicé un gráfico de columnas apiladas para comparar riesgos previos de corazón por género.
*Utilicé un gráfico circular en el que compara el riesgo de un ataque cardíaco por género.
Por último se agregó una segmentación de datos para que se puedan visualizar las gráficas por la filtración de género.
# Conclusiones:
Basándonos en los datos recopilados, se llegó a la conclusión de que dependiendo del estilo de vida de las personas puede existir un riesgo significativo de que una gran parte de la población pueda experimentar un ataque cardíaco.
Este riesgo se fundamenta en el análisis realizado, el cual fue de gran ayuda para identificar varios aspectos los cuales pueden aumentar la probabilidad de sufrir un ataque cardíaco. 
# Descripción del proyecto:
Para la elaboración de este proyecto, se recopilaron datos de pacientes y se procedió a realizar una limpieza de los mismos. Esta limpieza fue necesaria para especificar ciertos datos y garantizar una mayor claridad en el análisis. Una vez que los datos estuvieron limpios, se empleó la herramienta Power BI para llevar a cabo la visualización de estos, permitiendo así un análisis gráfico más completo de la información recopilada.
# Referencias: 
https://www.kaggle.com/datasets/iamsouravbanerjee/heart-attack-prediction-dataset 
# Queries, scripts de Python:
```Importación de librerias
import  pandas as pd #Importar la biblioteca pandas con el alias pd
import matplotlib.pyplot as plt #Biblioteca para crear gráficos y visualizaciones estáticas, animadas e interactivas en Python
import seaborn as sns #Biblioteca para crear gráficos estadísticos atractivos e informativos en Python
import numpy as np

csv_path ="https://docs.google.com/spreadsheets/d/e/2PACX-1vS2R59rt5oqQ-1wd_KJx5ytCD8BU9VQJjgbHnsALPig4RFRSCTtrMB2bEVtH2Znps7JiPxQNIowqrEk/pub?gid=216290071&single=true&output=csv"
df = pd.read_csv(csv_path, sep=",")#Se utilizó para importar el dataset.

df.rename(columns={'Sedentary Hours Per Day': 'Sedentary-Hours-Per-Day'}, inplace=True) #Se cambió modificos los nombres de la cabecera de la tabla

df.rename(columns={'Patient ID': 'Patient-ID'}, inplace=True)
df.rename(columns={'Blood Pressure': 'Blood-Pressure'}, inplace=True)
df.rename(columns={'Heart Rate': 'Heart-Rate'}, inplace=True)
df.rename(columns={'Family History': 'Family-History'}, inplace=True)
df.rename(columns={'Alcohol Consumption': 'Alcohol-Consumption'}, inplace=True)
df.rename(columns={'Exercise Hours Per Week': 'Exercise-Hours-Per-Week'}, inplace=True)
df.rename(columns={'Previous Heart Problems': 'Previous-Heart-Problems'}, inplace=True)
df.rename(columns={'Medication Use': 'Medication-Use'}, inplace=True)
df.rename(columns={'Stress Level': 'Stress-Level'}, inplace=True)
df.rename(columns={'Physical Activity Days Per Week': 'Physical-Activity-Days-Per-Week'}, inplace=True)
df.rename(columns={'Sleep Hours Per Day': 'Sleep-Hours-Per-Day'}, inplace=True)
df.rename(columns={'Heart Attack Risk': 'Heart-Attack-Risk'}, inplace=True)

df.head()
#Se cambió modificaron los nombres de la cabecera de la tabla

df["Diabetes"] = df["Diabetes"].replace(1," Positivo ").replace(0," Negativo ")
df["Sex"] = df["Sex"].str.replace("Male"," Masculino ").str.replace("Female"," Femenino")
df["Diabetes"] = df["Diabetes"].str.replace("Male"," Masculino ").str.replace("Female"," Femenino")
df["Family-History"] = df["Family-History"].replace(0," Negativo ").replace(1," Positivo ")
df["Smoking"] = df["Smoking"].replace(0," No ").replace(1," Si ")
df["Obesity"] = df["Obesity"].replace(0," No ").replace(1," Si ")
df["Alcohol-Consumption"] = df["Alcohol-Consumption"].replace(0," No ").replace(1," Si ")
df["Previous-Heart-Problems"] = df["Previous-Heart-Problems"].replace(0," Negativo ").replace(1," Positivo ")
df["Medication-Use"] = df["Medication-Use"].replace(0," No ").replace(1," Si ")
df["Heart-Attack-Risk"] = df["Heart-Attack-Risk"].replace(0," No ").replace(1," Si ")
df["Diet"] = df["Diet"].str.replace("Average"," Promedio ").str.replace("Unhealthy"," Enfermizo").str.replace("Healthy"," Sano")
df.head()

#Se modificaron los datos de las columnas por unos datos más precisos.

df=df.drop(["Hemisphere"],axis=1) 
df=df.drop(["Sedentary-Hours-Per-Day"],axis=1)
df=df.drop(["BMI"],axis=1)
df=df.drop(["Exercise-Hours-Per-Week"],axis=1)
df.head()
#Se eliminaron columnas.

print(df)
#visualizar el contenido del DataFrame

# Eliminar filas con valores nulos en el DataFrame original
df.dropna(inplace=True)

# Verificar valores nulos en todo el DataFrame
valores_nulos = df.isnull().sum()

# Mostrar la cantidad de valores nulos por columna
print(valores_nulos)

df.dtypes #Sirve para visualizar el dato correspondiente de las columnas.

print(df['Heart-Attack-Risk']) #Imprimí esta columna para corroborar de que se habia hecho modificacion de los datos de las filas

sns.histplot(df['Heart-Rate'])
plt.xlabel('Heart-Rate')
plt.ylabel('count')
plt.title('Ritmo cardíaco')
plt.show()

#En este histograma se puede visualizar los datos del ritmo cardáico de los pacientes.

# Creando un histograma para la columna 'Heart-Attack-Risk' del DataFrame df
# figsize=(6,6) especifica las dimensiones del gráfico en pulgadas
df['Heart-Attack-Risk'].hist(figsize=(6,6))
plt.title('Riesgo de Ataque Cardíaco') #Titulo de la gráfica

# Mostrando el gráfico en pantalla
plt.show()

#En este histograma se puede visualizar cual es el máximo riesgo de ataque cardíaco y en este caso en ganador es el "NO"

# Creando una figura con dimensiones específicas (10x10 pulgadas)
fig=plt.figure(figsize=(10,10))
# Creando un diagrama de caja (boxplot) para la columna 'Physical-Activity-Days-Per-Week' del DataFrame df
# Esto ayuda a visualizar la distribución de los datos, identificar outliers, y observar la tendencia central y dispersión
sns.boxplot(y=df["Physical-Activity-Days-Per-Week"])

# Mostrando el gráfico en pantalla
plt.show()

#Tendencia central: La mediana se muestra como una línea horizontal en el interior de la caja.
#Outliers(valores atipicos): Los valores atípicos se representan como puntos individuales fuera del del gráfico de caja



!pip install pandas_profiling==3.0.0 # Esta biblioteca proporciona un informe de análisis exploratorio de datos (EDA) con una sola línea de código
!pip install pandas_profiling --upgrade

import ydata_profiling as pandas_profiling

# Generar el informe
ataquecardiacoProfile = pandas_profiling.ProfileReport(df)

# Guardar el informe como un archivo HTML
ataquecardiacoProfile.to_file(output_file="AtaquecardiacoDataProfile.html")

# Si deseas visualizar el informe dentro del notebook puedes usar la siguiente línea:
# ataquecardiacoProfile.to_notebook_iframe()

df.to_csv('dataset_ataque_cardiaco.csv', index=False) #Se utilizó para descargar el dataset limpio.
