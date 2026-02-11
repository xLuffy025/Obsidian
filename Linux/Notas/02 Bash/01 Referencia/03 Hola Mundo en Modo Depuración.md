```bash 
$ cat hola.sh
#!/bin/bash
echo "Hola Mundo"
$ bash -x hola.sh
+ echo Hola Mundo 
Hola Mundo 
```

 El argumento te permite repasar cada línea del guion. Un buen ejemplo es este:`-x`

```bash
$ cat hello.sh
#!/bin/bash 
echo "Hello World\n" 
adding_string_to_number="s"
v=$(expr 5 + $adding_string_to_number) 

$ ./hello.sh 
Hello World

expr: non-integer argument
```

El error indicado arriba no es suficiente para rastrear el script; Sin embargo, usar la siguiente forma te da una mejor idea de dónde buscar el error en el script.

```bash
$ bash -x hello.sh 
+ echo Hello World\n
Hello World

+ adding_string_to_number=s
+ expr 5 + s
expr: non-integer argument
+ v=
```
 

 