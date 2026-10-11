# Factores de rendimiento estudiantil

Análisis exploratorio y limpieza de datos del conjunto **Student Performance Factors** (Kaggle), para el proyecto final de Programación 2.

## Integrantes

- _(Cada integrante agrega su nombre con un commit individual.)_

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

| Variable | Tipo | Qué significa |
|----------|------|----------------|
| `Hours_Studied` | Numérica continua | Horas de estudio semanales reportadas por el estudiante. Rango observado: 0 a 44. |
| `Attendance` | Numérica continua | Porcentaje de asistencia a clases (0–100). Hay al menos un valor inválido (negativo) que debe tratarse. |
| `Parental_Involvement` | Categórica ordinal | Nivel de involucramiento de los padres en la educación: `Low`, `Medium`, `High`. |
| `Access_to_Resources` | Categórica ordinal | Acceso a recursos educativos (libros, materiales, apoyo): `Low`, `Medium`, `High`. |
| `Extracurricular_Activities` | Categórica binaria | Si el estudiante participa en actividades extracurriculares: `Yes` / `No`. |
| `Sleep_Hours` | Numérica discreta | Horas de sueño diarias (enteros de 4 a 10). |
| `Previous_Scores` | Numérica discreta | Puntaje en evaluaciones previas (50 a 100). Sirve como historial académico. |
| `Motivation_Level` | Categórica ordinal | Nivel de motivación del estudiante: `Low`, `Medium`, `High`. |
| `Internet_Access` | Categórica binaria | Si tiene acceso a internet: `Yes` / `No`. |
| `Tutoring_Sessions` | Numérica discreta | Número de sesiones de tutoría (0 a 8). |
| `Family_Income` | Categórica ordinal | Nivel de ingreso familiar: `Low`, `Medium`, `High`. |
| `Teacher_Quality` | Categórica ordinal | Calidad percibida del docente: `Low`, `Medium`, `High`. Es una de las columnas con más faltantes. |
| `School_Type` | Categórica nominal | Tipo de institución: `Public` o `Private`. |
| `Peer_Influence` | Categórica ordinal | Influencia de los compañeros: `Negative`, `Neutral`, `Positive`. |
| `Physical_Activity` | Numérica discreta | Nivel o frecuencia de actividad física (escala entera de 0 a 6). |
| `Learning_Disabilities` | Categórica binaria | Si el estudiante presenta discapacidad de aprendizaje: `Yes` / `No`. |
| `Parental_Education_Level` | Categórica ordinal | Máximo nivel educativo de los padres: `High School`, `College`, `Postgraduate`. |
| `Distance_from_Home` | Categórica ordinal | Distancia casa–colegio: `Near`, `Moderate`, `Far`. |
| `Gender` | Categórica nominal | Género reportado: `Male` / `Female`. |
| `Exam_Score` | Numérica continua | Puntaje del examen final (variable objetivo). Debería estar en 0–100; aparecen valores fuera de rango (`-65` y `101`). |

### Clasificación rápida para el enunciado

- **Categóricas (>2):** `Parental_Involvement`, `Access_to_Resources`, `Motivation_Level`, `Family_Income`, `Teacher_Quality`, `School_Type`, `Peer_Influence`, `Parental_Education_Level`, `Distance_from_Home`, `Gender`, `Internet_Access`, `Extracurricular_Activities`, `Learning_Disabilities`.
- **Numéricas continuas (>2):** `Hours_Studied`, `Attendance`, `Exam_Score`.
- **Numéricas discretas (>2):** `Sleep_Hours`, `Previous_Scores`, `Tutoring_Sessions`, `Physical_Activity`.

## Conclusiones a primera vista (a partir del diccionario)

1. El rendimiento no se explica solo con el examen: el diccionario muestra un **perfil amplio** (hábitos, familia, escuela y pares). El análisis debe cruzar `Exam_Score` con variables de esfuerzo (`Hours_Studied`, `Attendance`, `Tutoring_Sessions`) y de contexto (`Family_Income`, `Teacher_Quality`, `Parental_Involvement`).

2. Varias variables usan la misma escala **Low / Medium / High**. Eso facilita comparar grupos, pero hay que tratarlas como **ordinales**, no como texto suelto, al agrupar y graficar.

3. Hay **faltantes concentrados** en `Teacher_Quality` (79), `Parental_Education_Level` (90) y `Distance_from_Home` (68). No conviene borrar todas esas filas de entrada: primero hay que decidir imputación o eliminación justificada, como pide el enunciado.

4. El diccionario y los rangos ya delatan **inconsistencias**: `Attendance` llega a −91 y `Exam_Score` a −65 y 101. Antes de conclusiones “definitivas” hay que limpiar outliers e inválidos.

5. La mayoría de estudiantes tiene internet (`Yes` ≈ 6,107) y asiste a colegio público (`Public` ≈ 4,597). Cualquier diferencia de puntaje por `Internet_Access` o `School_Type` hay que leerla con cuidado, porque los grupos **No** / `Private` son más pequeños.

## Conclusiones finales del notebook

_(Al cerrar el análisis, cada integrante agrega aquí una de las cinco conclusiones del notebook, con su propio `git add`, `commit` y `push`.)_

1.
2.
3.
4.
5.

## Estructura del repositorio

```text
Proyecto-Final-Progra-2/
├── data/
│   └── StudentPerformanceFactors.csv
├── notebooks/
├── requirements.txt
└── README.md
```
