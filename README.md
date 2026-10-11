# Factores de rendimiento estudiantil

Análisis exploratorio y limpieza de datos del conjunto **Student Performance Factors** (Kaggle), para el proyecto final de Programación 2.

## Integrantes
-Nciholas Ocampo Ruiz 
-Rafael Lamar Martinez Romero
## Fuente de datos

- **Dataset:** Student Performance Factors
- **Enlace:** https://www.kaggle.com/datasets/fares279/student-performance-factors
- **Archivo:** `data/StudentPerformanceFactors.csv`
- **Tamaño:** 6,607 registros y 20 variables (cumple el requisito de más de 1,000 filas)

## Estructura de los datos

Cada fila representa a **un estudiante**. Las columnas mezclan:

- **Contexto familiar y socioeconómico:** involucramiento parental, ingreso familiar, educación de los padres, distancia al colegio.
- **Condiciones escolares:** tipo de colegio, calidad docente, acceso a recursos, internet, tutorías.
- **Hábitos y entorno:** horas de estudio, asistencia, sueño, actividad física, motivación, actividades extracurriculares, influencia de pares, discapacidad de aprendizaje.
- **Resultados académicos:** puntaje previo y puntaje del examen final (`Exam_Score`, variable de interés).

Hay **más de dos variables categóricas** (nivel de involucramiento, recursos, motivación, tipo de colegio, etc.), **más de dos numéricas continuas** (horas de estudio, asistencia, puntaje del examen) y **más de dos numéricas discretas** (horas de sueño, sesiones de tutoría, actividad física, puntajes previos).

Algunas columnas tienen valores faltantes (sobre todo `Teacher_Quality`, `Parental_Education_Level` y `Distance_from_Home`) y hay inconsistencias puntuales (asistencia negativa, puntaje de examen fuera de 0–100).

## Diccionario de la base de datos

**Hours_Studied**: Representa el número total de horas que el estudiante dedica al estudio. Tipo de datos: Numérico decimal (float64).

**Attendance**: Indica el porcentaje de asistencia del estudiante a las clases escolares. Tipo de datos: Numérico decimal (float64).

**Parental_Involvement**: Describe el nivel de participación, acompañamiento e implicación de los padres en la educación del estudiante (por ejemplo, Bajo, Medio, Alto). Tipo de datos: Categórico / Texto (object).

**Access_to_Resources**: Mide el nivel de disponibilidad y acceso a recursos educativos necesarios (como tecnología, libros y material de apoyo). Tipo de datos: Categórico / Texto (object).

**Extracurricular_Activities**: Señala si el estudiante participa o no en actividades extracurriculares (Sí / No). Tipo de datos: Categórico / Texto (object).

**Sleep_Hours**: Cantidad promedio de horas de sueño que duerme el estudiante al día. Tipo de datos: Numérico entero (int64).

**Previous_Scores**: Calificaciones o puntajes obtenidos por el estudiante en evaluaciones académicas anteriores. Tipo de datos: Numérico entero (int64).

**Motivation_Level**: Refleja el nivel de motivación personal del estudiante hacia su rendimiento académico y aprendizaje (Bajo, Medio, Alto). Tipo de datos: Categórico / Texto (object).

**Internet_Access**: Indica si el estudiante cuenta con acceso a internet en su hogar (Sí / No). Tipo de datos: Categórico / Texto (object).

**Tutoring_Sessions**: Número de sesiones de tutoría o clases particulares adicionales que recibe el estudiante. Tipo de datos: Numérico decimal (float64).

**Family_Income**: Representa el nivel socioeconómico o de ingresos del núcleo familiar (Bajo, Medio, Alto). Tipo de datos: Categórico / Texto (object).

**Teacher_Quality**: Calificación o percepción sobre la calidad de la enseñanza impartida por los profesores (Bajo, Medio, Alto). Tipo de datos: Categórico / Texto (object).

**School_Type**: Especifica la categoría de la institución educativa a la que asiste el estudiante (Pública / Privada). Tipo de datos: Categórico / Texto (object).

**Peer_Influence**: Describe el tipo de influencia o presión social ejercida por el grupo de compañeros o amigos (Positiva, Negativa, Neutral). Tipo de datos: Categórico / Texto (object).

**Physical_Activity**: Mide la frecuencia o nivel de actividad física y ejercicio que realiza el estudiante de forma regular. Tipo de datos: Numérico decimal (float64).

**Learning_Disabilities**: Indica si el estudiante tiene diagnosticada alguna dificultad o trastorno de aprendizaje (Sí / No). Tipo de datos: Categórico / Texto (object).

**Parental_Education_Level**: Máximo nivel educativo alcanzado por los padres o tutores del estudiante (Secundaria, Universidad, Postgrado). Tipo de datos: Categórico / Texto (object).

**Distance_from_Home**: Distancia estimada que existe entre el hogar del estudiante y la escuela (Cerca, Moderada, Lejos). Tipo de datos: Categórico / Texto (object).

**Gender**: Género biológico o autopercibido del estudiante (Masculino / Femenino). Tipo de datos: Categórico / Texto (object).

**Exam_Score**: Calificación o puntaje final obtenido por el estudiante en el examen evaluado. Tipo de datos: Numérico decimal (float64).

## Conclusiones finales del notebook

1.
2.
3.
4.
5.
