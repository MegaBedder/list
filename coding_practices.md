# Buenas Practicas

## Objetivos
* Calidad general: reduce la cantidad de errores y problemas de software .
* Hacer que el código fuente sea comprensible: el código fuente debe ser legible y comprensible para que se apruebe en una auditoría de código .
* Hacer que el software se comporte de una manera predecible a pesar de las entradas inesperadas o las acciones del usuario.

## Comentarios
* Tratar que el código sea autodescriptivo, para no requerir comentarios.
* En el caso de que no sea conveniente puede comentar el código para aclarar lo que está sucediendo y asi facilitar la comprension de lo que hace el código.

El uso no controlado de estructuras y funciones de tamaño constante para datos de tamaño dinámico (el problema de desbordamiento del búfer).
* Las funciones deben usarse con `el tamaño máximo del búfer de entrada` como argumento adicional.
* Las funciones como `scanf` se pueden usar de manera segura, pero requieren que el programador se encargue de la selección de cadenas de formato seguras, desinfectándolas antes de usarlas.

## Confiando en la validez interna de los datos.
## Programación defensiva
```PHP
// Programación excesivamente defensiva
function trafficlight_colorname($trafficlight_color) {
    switch ($trafficlight_color) {
        case TRAFFICLIGHT_RED:    return "red";
        case TRAFFICLIGHT_YELLOW: return "yellow";
        case TRAFFICLIGHT_GREEN:  return "green";
    }

    return "black"; // Para ser manejado como un semáforo apagado.
}
```

## Programación ofensiva
```PHP
// Programación ofensiva
function trafficlight_colorname($trafficlight_color) {
    switch ($trafficlight_color) {
        case TRAFFICLIGHT_RED:    return "red";
        case TRAFFICLIGHT_YELLOW: return "yellow";
        case TRAFFICLIGHT_GREEN:  return "green";
    }

    assert(0); // Afirmar que esta sección es inalcanzable.
}
```

## Confiando en los componentes del software
## Programación defensiva
```PHP
if (is_legacy_compatible($user_config)) {
    // Estrategia: No confíes en que el nuevo código se comporte igual.
    old_code($user_config);
} else {
    // Fallback: No confíe en que el nuevo código maneja los mismos casos
    if (new_code($user_config) != OK) {
        old_code($user_config);
    }
}
```

## Programación ofensiva
Just Do It
```PHP
// Confía en que el nuevo código no tenga nuevos errores.
new_code($user_config);
```
## Canonización de Datos de Entrada
Es probable que los usuarios malintencionados inventen nuevos tipos de representaciones de datos incorrectos.
> Por ejemplo, si un programa intenta rechazar el acceso al archivo `/etc/passwd`, un cracker podría pasar otra variante de este nombre de archivo, como `/etc/./passwd`.

Las bibliotecas de Canonicalización se pueden emplear para evitar errores debidos a la entrada no canónica de datos.

## Otras técnicas
### Datos
* Encripta / autentica todos los datos importantes transmitidos a través de redes.
> No intente implementar su propio esquema de encriptación, sino use uno probado.
* Todos los datos son importantes hasta que se demuestre lo contrario.
* Todos los datos están contaminados hasta que se demuestre lo contrario.
* Todo el código es inseguro hasta que se demuestre lo contrario.
> No puede probar la seguridad de ningún código en la zona de usuario o, más canónicamente, "nunca confíe en el cliente".
* Si se debe verificar que los datos sean correctos, verifique que sean correctos, no que sean incorrectos.
> Prefiera lista blanca antes que una lista negra.

### Diseño por contrato
* El diseño por contrato utiliza condiciones previas, condiciones posteriores e invariantes para garantizar que los datos proporcionados (y el estado del programa en general) se desinfecten.

* Esto permite que el código documente sus suposiciones y las haga de manera segura.

* Esto puede implicar la verificación de la validez de los argumentos de una función o un método antes de ejecutar el cuerpo de la función.

* Después del cuerpo de una función, también es aconsejable realizar una verificación del estado del objeto (en lenguajes de programación orientados a objetos) u otros datos retenidos y el valor de retorno antes de las salidas `break/return/throw/código de error`.
```PHP
// Design By Contract with PHP

// Function
function combine($a, $b) {
    return "Combined: " . $b . $a;
}

// Parameters
$a = 7;
$b = 'Simple DbC with PHP';

// Pre-Condition
assert(
    is_integer($a)
, new AssertionError('no es un entero'));

// Invariant
$result = combine($a, $b);
    
// Post-Condition
assert(
    is_string($result)
, new AssertionError('no es una cadena'));

// Continue execution
print($result . "\n");
```

### Afirmaciones (Assertions)
Son la forma preferida de verificar las cosas que no deberían ser necesarias, como los contratos de diseño entre componentes de software.

* Dentro de las funciones, es posible que desee verificar que no está haciendo referencia a algo que no es válido (es decir, nulo) y que las longitudes de la matriz son válidas antes de hacer referencia a los elementos, especialmente en todas las instancias locales / temporales.
* Una buena heurística es no confiar en las bibliotecas que usted tampoco escribió.
* Así que cada vez que los llames, verifica qué recibes de ellos.
* A menudo ayuda crear una pequeña biblioteca de funciones de "confirmación" (asserting) y "verificación" (checking) para hacer esto junto con un registrador para que pueda rastrear su ruta y reducir la necesidad de extensos ciclos de depuración en primer lugar.
* Con el advenimiento de las bibliotecas de registro (logging libraries) y la programación orientada a aspectos, muchos de los aspectos tediosos de la programación defensiva se mitigan.

### Prefiere excepciones a los códigos de retorno
* Es preferible enviar mensajes de excepción inteligibles (comprensibles) que impongan parte de su contrato de API y
* guíen al programador cliente en lugar de devolver los valores
* para los cuales es probable que el programador cliente no esté preparado y,
* por lo tanto, minimicen sus quejas y aumenten la solidez y seguridad de su software.
```PHP
class CustomException extends Exception {}

try {
    $error = true;

    if ($error)
        // Exception
        throw new CustomException('Always throw this error');

    echo "\nNever executed if there is an Exception";

} catch (CustomException $e) {
    echo 'Caught exception: ', $e->getMessage(), "\n";
}
```

https://en.wikipedia.org/wiki/Best_coding_practices

https://en.wikipedia.org/wiki/Offensive_programming

https://en.wikipedia.org/wiki/Defensive_programming

https://en.wikipedia.org/wiki/Design_by_contract

https://en.wikipedia.org/wiki/Aspect-oriented_programming
