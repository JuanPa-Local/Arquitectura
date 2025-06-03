Link:
https://circuitverse.org/users/296613/projects/pdua-2510-jpsm

Proyecto
Este programa ha sido diseñado para ejecutarse en un procesador académico tipo PDUA (Procesador de Datos de Uso Académico) y realiza la multiplicación de dos números enteros con signo utilizando el Algoritmo de Booth, implementado completamente en instrucciones binarias de 8 bits.

Objetivo
El propósito principal de este código es demostrar el funcionamiento del algoritmo de Booth para multiplicación binaria de dos números de 8 bits, teniendo en cuenta el manejo del signo (positivo o negativo) a través del complemento a dos.

Funcionamiento General
Carga de Datos Iniciales:
Se cargan los operandos en memoria:

Multiplicando: 5 (almacenado en la dirección 0x20)
Multiplicador: 2 (almacenado en la dirección 0x21)

Inicialización:
Se inicializan las variables de resultado, contador, y registros auxiliares.

Ciclo de Booth (8 iteraciones):
El algoritmo analiza los bits menos significativos del multiplicador y del bit Q-1 para decidir si debe sumar, restar o simplemente desplazar a la derecha el contenido del acumulador.

Subrutinas:
ADD_MULT: Suma el multiplicando al acumulador.
SUB_MULT: Resta el multiplicando usando su complemento a dos.
SHIFT_RIGHT: Ejecuta el desplazamiento aritmético para completar una iteración del algoritmo.
SKIP_MSB_SET: Ajusta el bit más significativo del multiplicador según los desplazamientos.

Finalización:
Al finalizar el ciclo, el resultado de la multiplicación se almacena en:
Parte alta (RESULT_H) → Registro A
Parte baja (RESULT_L) → Registro ACC

Formato del Código
El programa está codificado enteramente en instrucciones binarias de 8 bits, en el formato 0bxxxxxxxx, como lo requiere el entorno del simulador PDUA. Las direcciones de memoria para las variables están reservadas entre 0x20 y 0x26.
