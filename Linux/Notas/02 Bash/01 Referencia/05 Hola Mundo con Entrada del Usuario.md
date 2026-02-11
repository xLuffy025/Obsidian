Lo siguiente pedirá al usuario que introduzca la entrada y luego almacenará esa entrada como una cadena (texto) en una variable. La variable se utiliza entonces para dar un mensaje al usuario.

```bash
#!/usr/bin/env bash
echo "¿Quien eres?"
read name 
echo "Hola, $name."
```

El comando `read` aquí lee una línea de datos de la entrada estándar en la variable `name`. Esto se referencia usando `$name` y se imprime en estándar usando `echo`.

Ejemplo de salida:
```bash 
$./hola.sh
¿Quién eres?
Jose
Hola, Jose.
```

Aquí el usuario introdujo el nombre "Jose", y este código se usó para decir `Hola, Jose.`

Y si quieres añadir algo al valor de la variable al imprimirlo, usa corchetes alrededor del nombre de la variable como se muestra en el siguiente ejemplo:

```bash
#!/usr/bin/env bash
echo "What are you doing?"
read action
echo "You are ${action}ing."
```

Ejemplo de salida:
```bash
$ ./hello_world.sh
What are you doing?
Sleep
You are Sleeping.
```

Aquí, cuando el usuario introduce una acción, se añade "ing" a esa acción durante la impresión.