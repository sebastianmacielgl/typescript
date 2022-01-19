# Sobre Typescript

## Qué es Typescript

Viene a ser un **superset de habilidades** para Javascript. Si bien Javascript es un lenguaje de tipado dinámico, Typescript está diseñado para escribir código de tipado estático que después se va a transformar en Javascript.

### Qué nos brinda?

Nos proporciona la _seguridad_ de un lenguaje de tipado estático. Esto quiere decir, que no vamos a encontrar errores en tiempo de ejecución, si no en tiempo de compilación. Es decir, mientras escribimos código podemos gozar de la corrección de errores, según configuremos nuestro IDE, lo cual se traduce en **evitar tener errores al momento de ejecutar nuestra aplicación** y enterarnos recién en ese momento que hicimos algo mal.

### Casos prácticos

Un caso muy común, es querer que una variable siempre tenga un tipo de dato, por ejemplo `string`. Es algo que no podemos hacer en vanilla javascript, y es extremadamente útil en casos como el siguiente:

    let edad = '22'

    function sumarDiez(valor) {
        return valor + 10
    }

    sumarDiez(edad)

    // Output: '2210'
    // Resultado esperado: 32

El problema claro es que le estamos pasando un `string` a la función `sumarDiez()`. Typescript nos da herramientas para convertir este tipado dinámico, en estático.
Es decir, avisarle al código realmente qué tipo de datos queremos que se manejen:

    let edad: number = '22'
    // Esto nos va a dar un error, porque el tipo es number y el valor es string

Por otro lado, podemos determinar el tipo que va tomar el parámetro `valor: number` e incluso definir lo que va a retornar la función `:number`:

    function sumarDiez(valor: number): number {
    	return valor + 10
    }

Nos es útil sobre todo cuando hagamos una llamada a alguna API de la cual podemos no estar seguros de qué datos nos van a entregar, con esto nos aseguramos de lo que planeamos con alguna función, queremos tomar un `number` que haga algún proceso que nos returne un `number`. Ni más ni menos.

### Otras características

    const user = {
    	name: 'Carlos',
    	apellido: 'Gonzalez',
    	edad: 30
    }

### Interfaces

Podemos solucionar problemas de tipos incluso de mejor manera declarando de antemano cómo sería el contenido de casi cualquier cosa, de la siguiente manera:

    interface User {
    	name: string;
    	apellido: string;
    	edad: number;
    }

    const user: User = {
    	name: 'Carlos',
    	apellido: 'Gonzalez',
    	edad: 30
    }

El _autocompletado_ del que uno dispone cuando utiliza Typescript es sin duda uno de los mayores atractivos.

Podemos empezar a escribir `user.` y después del punto el IDE nos va a empezar a sugerir el contenido. Y sobre todo, lo que no exista, por ejemplo en este caso una key `dni` inexistente.

Otro punto a favor: **Tu código va a estar autodocumentado**.

### En resumen

Si le pasamos un `number` a una función que espera un `string`:
Con Typescript es el IDE quien nos va a avisar en tiempo de compilación.
Con Vanilla Javascript, el que nos va a avisar va a ser QA o el mismo usuario en producción.
