# Sobrecarga-funciones
Las sobrecargas de funciones en TypeScript te permiten definir múltiples firmas para una misma función. Esto significa que puedes tener una función con diferentes parámetros y tipos de retorno, y el compilador de TypeScript seleccionará automáticamente la firma adecuada según cómo se invoque la función. Aquí tienes información completa y ejemplos sobre las sobrecargas de funciones en TypeScript:

1. Definición de sobrecargas:
   Para definir una sobrecarga de función en TypeScript, debes declarar múltiples firmas para la función utilizando la palabra clave `declare`. Cada firma especifica los parámetros y el tipo de retorno correspondiente.

   ```typescript
   function myFunction(param1: type1): returnType;
   function myFunction(param1: type2, param2: type3): returnType;
   function myFunction(param1: type4, param2?: type5): returnType;
   // ... Otras sobrecargas ...
   ```

   Ejemplo:
   ```typescript
   function add(a: number, b: number): number;
   function add(a: string, b: string): string;
   function add(a: any, b: any): any {
     return a + b;
   }

   console.log(add(1, 2));            // Output: 3
   console.log(add("Hello", "World")); // Output: HelloWorld
   ```

   En este ejemplo, se definen tres sobrecargas para la función `add`. La primera sobrecarga toma dos parámetros de tipo `number` y devuelve un valor de tipo `number`. La segunda sobrecarga toma dos parámetros de tipo `string` y devuelve un valor de tipo `string`. La tercera sobrecarga toma un parámetro de cualquier tipo y un parámetro opcional de tipo `any`, y devuelve un valor de tipo `any`. La implementación real de la función se proporciona después de las sobrecargas.

2. Selección automática de la sobrecarga adecuada:
   El compilador de TypeScript seleccionará automáticamente la firma adecuada de la función según los argumentos proporcionados en la llamada.

   Ejemplo:
   ```typescript
   function multiply(a: number, b: number): number;
   function multiply(a: number, b: string): string;
   function multiply(a: any, b: any): any {
     return a * b;
   }

   console.log(multiply(2, 3));            // Output: 6
   console.log(multiply(2, "Hello"));      // Output: HelloHello
   ```

   En este ejemplo, la primera sobrecarga de `multiply` toma dos parámetros de tipo `number` y devuelve un valor de tipo `number`. La segunda sobrecarga toma un parámetro de tipo `number` y un parámetro de tipo `string`, y devuelve un valor de tipo `string`. Al llamar a la función con argumentos de tipo `number` y `number`, se selecciona automáticamente la primera sobrecarga. Al llamar a la función con argumentos de tipo `number` y `string`, se selecciona automáticamente la segunda sobrecarga.

Las sobrecargas de funciones en TypeScript te permiten crear funciones más flexibles que pueden adaptarse a diferentes tipos de argumentos y proporcionar diferentes resultados. Esto mejora la usabilidad y la claridad del código al permitir invocar la función con diferentes combinaciones de argumentos sin necesidad de escribir funciones separadas con nombres distintos.
