verificacion : 
el proceso de evaluacion de un sistema o de uno de sus componentes para determinar si los productos de una fase dada
satisfacen las condiciones impuestas al comienzo de dicha fase 

validacion :
el proceso de evaluacion de un sistema o de uno de sus componenetes durante o al final del proceso de desarrollo para determinar si satisface los requisitos especificados 

asi validar una aplicacion implica comprobar si satisface los requisitos marcados por el usuarios

verificacion: estamos construyendo correctamente el producto ? 
validacion : estamos construyendo el producto correcto 

pruebas permiten verficiar y validar el software cuando ya esta en forma de codigo ejecutable 

Definiciones

Prueba (test) 
Una actividad en la cual un sistema o uno de sus componentes se ejecuta en circunstancias previamente especificadas, los resultados se observan y registran y se realiza una evaluacion de algun aspecto. Para [Myers 1979], probar (o la prueba) es el "proceso de ejecutar un programa con el fin de encontrar errores". El nombre "prueba",ademas de la actividad de probar, se puede usar para "un conjunto de casos y procedimientos de prueba [IEEE 1990]

Algunos autores consideran prueba a otras actividades, como las revisiones, las pruebas formales, etc (papel). En las que no se ejecuta software, designandolas como pruebas estaticas (static testing)

Caso de prueba (test case)
"Un conjunto de entradas, condiciones de ejecucion y resultados esperados desarrolados para un objetivo particular como, por ejemplo, ejercitar un camino concreto de un programa o verificar el cumplimiento de un determinado requisito". Tambien se puede referir a la documentacion donde se describen las entradas, condiciones y salidas de un caso de prueba. 

Defecto (defect, fault, bug)
"Un defecto en el software como, por ejemplo, un proceso, una definicion de datos o un paso de procesamiento incorrectos en un programa".

Fallo (failure)
"la incapacidad de un sistema o de alguno de sus componenetes para realizar las funciones requeridas dentro de los requisitos de rendimiento espeficiados"

Error (error) Tiene varias acepciones:
1. La diferencia entre un valor calculado, observado o medido y el valor verdadero, especificado o teoricamente correcto. 
2. Un deefcto, por ejemplo, una instruccion incorrecta en un programa
3. Un resultado incorrecto.
4. Una accion humana que conduce a un resultado incorrecto (mistake)
en el libro ignoramos #2 y #3, ya que coinciden con las definiciones de defecto y fallo, para evitar errores.

11.2 Filosofia de las pruebs de software
la prueba del software es exhaustiva del software es impracticable: No se pueden probar todas las posibilidades de su funcionamiento incluso en programas pequenos y sencillos.

Myers Se trata de una actividad a posteriori de deteccion y no de prevencion de problemas en el software

el descubrimiento de un defecto significa un exito para la mejora de la claidad al igual que, a pesar de lo incomodo que resulta, la deteccion de un problema de salud de un analisis medico se considera un exito para lograr la curaion del paciente 

Myers 1979 recomendaciones
1. cada caso de prueba debe definir el resultado de salida esperado. Este resultado esperado es el que se compra con el realmente objetnido de la ejecucion en la prueba. Las discrepancia entre ambos (errores) se consideran sintomas de un posible defecto en el software

2.El programador debe evitar probar sus propios programas porque desea (consicnete o inconsciente) demostrar que funcionan sin problemas. Esta actitud inadecuada lleva a realizar pruebas menos rigurosas de lo deseable. Ademas, es normal que las situaciones que ha olvidado considerar al crear el programa (por ejemplo, no pensar en como tratar un fichero de entrada vacio) queden, de nuevo, olvidadas al escribir casos de prueba. Lo ideal seria que probara el software el peor enemigo de quien lo ha construido, ya que asi se asegurarian una busqueda implacable de cualquier error cometido.

3. Se debe inspeccionar a conciencia el resultado de cada prueba para, asi, poder descubrir posibles sintomas de defectos. Lamentablemente es frecuente pasar por alto sintomas bastante claros. Esto invalida todo el esfuerzo realizado en la planificacion, diseño y ejecucion de pruebas. 

4. Al generar casos de prueba, se deben incluir tanto datos de entradas validos y esperados como no validos e inesperados. Es frecuente observar una tendencia a centrarse en lo esperado y lo valido.

5. Las pruebas deben centrarse en dos objetivos (es habitual olvidar el segundo)
    Probar si el software no hace lo que debe. 
    Probar si el software hace lo que no debe, es decir, si provoca efectos secundarios adversos 

6. Se deben evitar los casos desechables, es decir, los no documentados ni diseñados con cuidado (por ejemplo, los que se teclean sobre la marcha), ya que suele ser necesario probar una y otra vez el software hasta que queda libre de defectos. No documentar o guardar los casos significa repetir constantemente el diseño de casos de prueba

7. No deben hacerse planes de prueba suponiendo que, practicamente, no hay defectos en los programas y, por lo tanto, dedicando pocos recursos a las pruebsa. Hay que asumir que siempre hay defectos (estan cuantificadas ya las tasas habituales de defectos de los mejores desarrolladores profesionales y no son cero) y hay que detectarlos. Las estdisticas confirman que, practicamente, el 40% del esfuerzo de desarrollo se consumen en pruebas y depuracion.

8. La experiencia parece indicar que donde hay un defecto hay otros, es decir, la probabilidad de descburir nuevos defectos en una parte del software es proporcional al numero de defectos ya descubiertos (algunos autores matizan esta afirmacion en funcion de la complejidad y la habilidad del desarrollador )

9. Las preubas son una tarea tanto o mas creativa que el desarrollo de software. Siempre se han considerado a las pruebas como una tarea destructiva y rutinaria. No obstante, no existen tecnicas rutinarias (como veremos) para el diseño de pruebas y hay que recurrir al ingenio para alcanzar un buen nivel de deteccion de defectos con los recursos disponibles Myers habla en su libro del "arte de las pruebas" tambien se suele decir que si cree que la construccion del programa ha sido dificil, aun no ha visto nada". 

11.3
Proceso de prueba
figura 11.2 Ciclo completo de las pruebas (IEEE 1008)

El proceso de prueba comienza con la generacion de un [plan de pruebas] en base a la documentacion sobre el proyecto y la documentacion sobre el software a probar. A partir de dicho plan, se entra en detalle [diseñando pruebas] especificas basandose en la documentacion del software a probar. Una vez detalladas las pruebas (especificaciones de casos y de procedimientos) se toma la configuracion del software (revisada, para confirmar que se trata de la version apropiada del programa) que se va a probar para [ejecutar] sobre ella los casos. En algunas situaciones, se puede tratar de reejecuciones de pruebas, por lo que es conveniente tener constancia de los defectos ya detectados aunque aun no corregidos). A partir de los resultados de salida, se pasa a su [evaluacion] mediante comparacion con la salida esperada. A partir de esta, se pueden realizar dos actividades :
    Depuracion (localizacion y correccion de defectos)
    El analisis de la estadistica de errores 
La depuracion puede corregir o no los defectos. Si no consigue localizarlos, puede ser necesario realizar pruebas adicionales para obtener mas informacion. Si se corrige un defect, se debe volver a probar el software para comprobar que el problema esta resuelto. 
Por su parte, el analisis de errores puede servir pra realizar predicciones de la fiabilidad del software y para detectar las causas mas habiituales de error y mejorar los procesos de desarrollo. 

11.4 Tecnicas de diseño de casos de prueba 
existen tres enfoques para el diseño de casos : 
1. EL [enfoque estructural] o de [caja blanca] 11.3 Consiste en centrarse en la estructura interna (implementacion) del programa para elegir los casos de prueba. En este caso , la prueba ideal (exhaustiva) del software consistiria en probar todos los posibles caminos de ejecucion, a traves de las instrucciones del codigo, que puedan trazarse. 
2. El [enfoque funcional] o de [caja negra] 11.3 Consiste en estudiar la especificacion de las funciones, la entrada y la salida para derivar los casos. Aqui, la prueba ideal del software consistiria en probar todas las posibles entradsa y salidas de programa. 
3. El [enfoque aleatorio] consiste en utilizar modelos (en muchas ocasiones estadisticos) para crear a partir de ellos los casos de prueba. La prueba exhaustiva consistiria en probar todas las posibles entradas al programa 

Estos enfoques no son excluyentes entre si, ya que se pueden combinar para conseguir  una deteccion de defectos mas eficaz. Veremos a continuacion una presentacion de cada uno de ellos -