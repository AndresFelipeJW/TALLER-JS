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
// Ingresar dos números
let numero1 = prompt("Por favor, introduce el primer número:");
let numero2 = prompt("Por favor, introduce el segundo número:");

// Revisamos si los valores ingresados son números
if (!isNaN(numero1) && !isNaN(numero2)) {
    let suma = Number(numero1) + Number(numero2);
    
    alert("La suma de los dos números es: " + suma);
} else {
    alert("Al menos uno de los valores ingresados no es un número.");
}
```

## Ejercicio No.6°

- Pedir dos números por pantalla y una operación (+, -, *, /) y mostrar en un alert el resultado de la operación.  Si la operación no es ninguna de las anteriores, se debe mostrar el mensaje "Operación incorrecta".  Se debe validar que los valores introducidos sean números.

```Javascript
// Ingresar dos números y la operación
let numero1 = prompt("Por favor, introduce el primer número:");
let numero2 = prompt("Por favor, introduce el segundo número:");
let operacion = prompt("Por favor, introduce la operación (+, -, *, /):");

// Verificamos si los valores ingresados son números
if (!isNaN(numero1) && !isNaN(numero2)) {
    let num1 = Number(numero1);
    let num2 = Number(numero2);
    
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

    if (resultado !== undefined && !isNaN(resultado)) {
        alert("El resultado de la operación es: " + resultado);
    } else {
        alert("El resultado de la operación no es un número válido.");
    }
} else {
    // Si al menos uno de los valores ingresados no es numérico, mostramos un mensaje de error
    alert("Al menos uno de los valores ingresados no es un número.");
}
```

## Ejercicio No.7°

- Leer tres notas de los estudiantes y calcular la media.  Tiene que indicar si está reprobado (nota < 3) o aprobado, junto con la nota media.  Si alguna nota no es un número, no dejar de pedirlas hasta que sea correcta.

```Javascript
let nota1;
do {
    nota1 = prompt("Por favor, introduce la nota 1:");
    if (isNaN(parseFloat(nota1))) {
        alert("Por favor, introduce un valor numérico para la nota 1.");
    }
} while (isNaN(parseFloat(nota1)));
nota1 = parseFloat(nota1);

let nota2;
do {
    nota2 = prompt("Por favor, introduce la nota 2:");
    if (isNaN(parseFloat(nota2))) {
        alert("Por favor, introduce un valor numérico para la nota 2.");
    }
} while (isNaN(parseFloat(nota2)));
nota2 = parseFloat(nota2);

let nota3;
do {
    nota3 = prompt("Por favor, introduce la nota 3:");
    if (isNaN(parseFloat(nota3))) {
        alert("Por favor, introduce un valor numérico para la nota 3.");
    }
} while (isNaN(parseFloat(nota3)));
nota3 = parseFloat(nota3);

let media = (nota1 + nota2 + nota3) / 3;

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
// Ingresar dos números
let numero1;
let numero2;
do {
    numero1 = prompt("Por favor, introduce el primer número:");
    numero2 = prompt("Por favor, introduce el segundo número:");
    if (isNaN(numero1) || isNaN(numero2)) {
        alert("Por favor, introduce valores numéricos para ambos números.");
    }
} while (isNaN(numero1) || isNaN(numero2));

numero1 = Number(numero1);
numero2 = Number(numero2);

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
let lado = 5;

for (let i = 1; i <= lado; i++) {
    let linea = "";
    for (let j = 1; j <= lado; j++) {
        if (i === 1 || i === lado || j === 1 || j === lado) {
            linea += "*";
        } else {
            linea += " ";
        }
    }
    console.log(linea);   
}
```

## Ejercicio No.10°

- Cree esta figura por pantalla con JS

```Javascript
let filas = 5;
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
```