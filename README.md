# TALLER-JS

## Ejercicio No.1°

- Mostrar por consola la tabla de multiplicar del 5 utilizando la sentencia for de la siguiente manera:

5 x 0 = 0

5 x 1 = 5

5 x 2 = 10

...

```Javascript
// Bucle for para generar la tabla de multiplicar del 5
for (let i = 0; i <= 10; i++) 
{
    let resultado = 5 * i;
    console.log("5 x " + i + " = " + resultado);
}
```

## Ejercicio No.2°

- Modificar el programa anterior y mostrar las 10 tablas de multiplicar.

```Javascript
for (let i = 1; i <= 10; i++) {
    console.log("Tabla del " + i + ":");
    for (let j = 0; j <= 10; j++) {
        let resultado = i * j;
        console.log(i + " x " + j + " = " + resultado);
    }
    console.log("------------------");
}
```

## Ejercicio No.3°

- Pedir por pantalla a través de prompt un texto y mostrar en un alert si el texto introducido es un valor numérico o es una cadena.

```Javascript
// Ingresar un texto
let texto = prompt("Por favor, introduce un texto:");

// Verificamos si el texto es un valor numérico o una cadena
if (!isNaN(texto)) {
    alert("El texto introducido es un valor numérico.");
} else {
    alert("El texto introducido es una cadena.");
}
```

## Ejercicio No.4°

- Pedir dos textos por pantalla a través de prompt y mostrar en un alert las dos cadena concatenadas.

```Javascript
// Ingresear dos textos
let texto1 = prompt("Por favor, introduce el primer texto:");
let texto2 = prompt("Por favor, introduce el segundo texto:");

// Concatenamos las dos cadenas
let resultado = texto1 + " " + texto2;

// Mostramos el resultado en un alert
alert("Las dos cadenas concatenadas son: " + resultado);
```

## Ejercicio No.5°

- Pedir dos números por pantalla con prompt y mostrar la suma de ambos.  Se debe validar que los números introducidos sean números.

```Javascript
// Función para validar si un valor es numérico
function esNumero(valor) {
    return !isNaN(parseFloat(valor)) && isFinite(valor);
}

// Ingresar dos números
let numero1 = prompt("Por favor, introduce el primer número:");
let numero2 = prompt("Por favor, introduce el segundo número:");

// Revisamos si los valores ingresados son números
if (esNumero(numero1) && esNumero(numero2)) 
{
    let suma = parseFloat(numero1) + parseFloat(numero2);
    
    alert("La suma de los dos números es: " + suma);
} else {
    alert("Al menos uno de los valores ingresados no es un número.");
}
```

## Ejercicio No.6°

- Pedir dos números por pantalla y una operación (+, -, *, /) y mostrar en un alert el resultado de la operación.  Si la operación no es ninguna de las anteriores, se debe mostrar el mensaje "Operación incorrecta".  Se debe validar que los valores introducidos sean números.

```Javascript
function esNumero(valor) {
    return !isNaN(parseFloat(valor)) && isFinite(valor);
}

// Ingresar dos números y la operación
let numero1 = prompt("Por favor, introduce el primer número:");
let numero2 = prompt("Por favor, introduce el segundo número:");
let operacion = prompt("Por favor, introduce la operación (+, -, *, /):");

// Verificamos si los valores ingresados son números
if (esNumero(numero1) && esNumero(numero2)) {
    let num1 = parseFloat(numero1);
    let num2 = parseFloat(numero2);
    
    // Realizamos la operación según la opción ingresada
    let resultado;
    switch (operacion) {
        case "+":
            resultado = num1 + num2;
            break;
        case "-":
            resultado = num1 - num2;
            break;
        case "*":
            resultado = num1 * num2;
            break;
        case "/":
            resultado = num1 / num2;
            break;
        default:
            alert("Operación incorrecta");
            break;
    }

    if (resultado !== undefined) {
        alert("El resultado de la operación es: " + resultado);
    }
} else {
    // Si al menos uno de los valores ingresados no es numérico, mostramos un mensaje de error
    alert("Al menos uno de los valores ingresados no es un número.");
}
```

## Ejercicio No.7°

- Leer tres notas de los estudiantes y calcular la media.  Tiene que indicar si está reprobado (nota < 3) o aprobado, junto con la nota media.  Si alguna nota no es un número, no dejar de pedirlas hasta que sea correcta.

```Javascript
function esNumero(valor) {
    return !isNaN(parseFloat(valor)) && isFinite(valor);
}

function pedirNota(numeroNota) {
    let nota;
    do {
        nota = prompt("Por favor, introduce la nota " + numeroNota + ":");
        if (!esNumero(nota)) {
            alert("Por favor, introduce un valor numérico para la nota " + numeroNota + ".");
        }
    } while (!esNumero(nota));
    return parseFloat(nota);
}

// Ingresar las tres notas
let nota1 = pedirNota(1);
let nota2 = pedirNota(2);
let nota3 = pedirNota(3);


let media = (nota1 + nota2 + nota3) / 3;

// Determinamos si el estudiante está aprobado o reprobado
let estado;
if (media >= 3) {
    estado = "aprobado";
} else {
    estado = "reprobado";
}


alert("La nota media del estudiante es: " + media.toFixed(2) + ". Está " + estado + ".");
```

## Ejercicio No.8°

- Introducir dos números e indicar cuál es el mayor o si son iguales.

```Javascript
function esNumero(valor) {
    return !isNaN(parseFloat(valor)) && isFinite(valor);
}

// Ingresar dos números
let numero1;
let numero2;
do {
    numero1 = prompt("Por favor, introduce el primer número:");
    numero2 = prompt("Por favor, introduce el segundo número:");
    if (!esNumero(numero1) || !esNumero(numero2)) {
        alert("Por favor, introduce valores numéricos para ambos números.");
    }
} while (!esNumero(numero1) || !esNumero(numero2));


numero1 = parseFloat(numero1);
numero2 = parseFloat(numero2);

// Comparamos los números e indicamos cuál es mayor o si son iguales
if (numero1 > numero2) {
    alert("El primer número (" + numero1 + ") es mayor que el segundo número (" + numero2 + ").");
} else if (numero2 > numero1) {
    alert("El segundo número (" + numero2 + ") es mayor que el primer número (" + numero1 + ").");
} else {
    alert("Ambos números son iguales (" + numero1 + ").");
}
```

## Ejercicio No.9°

-  Pintar un cuadrado de asteriscos de 5 por cada lado

```Javascript

```

## Ejercicio No.10°

- Cree esta figura por pantalla con JS

```Javascript
// pintamos la figura con asteriscos
function pintarFigura(filas) {
    let longitudMaxima = filas * 2 - 1;
    let mitad = Math.ceil(filas / 2);

    for (let i = 1; i <= filas; i++) {
        let asteriscos = i * 2 - 1;
        let espacios = (longitudMaxima - asteriscos) / 2;

        let fila = " ".repeat(espacios) + "*".repeat(asteriscos);
        console.log(fila);
    }

    for (let i = mitad - 1; i >= 1; i--) {
        let asteriscos = i * 2 - 1;
        let espacios = (longitudMaxima - asteriscos) / 2;

        let fila = " ".repeat(espacios) + "*".repeat(asteriscos);
        console.log(fila);
    }
}
pintarFigura(5);
```