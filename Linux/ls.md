NOMBRE
ls - Lista el contenido del directorio

SINOPSIS
ls [OPCIÓN]... [ARCHIVO]...

DESCRIPCIÓN
Lista información sobre los ARCHIVOS (el directorio actual por defecto).
Ordena las entradas alfabéticamente si no se especifican -cftuvSUX ni --sort.

Los argumentos obligatorios para las opciones largas también lo son para las opciones cortas.

-a, --all
No ignora las entradas que empiezan por .

-A, --almost-all
No lista los . y .. implícitos.

--author
Con -l, imprime el autor de cada archivo.

-b, --escape
Imprime escapes de estilo C para caracteres no gráficos.

--block-size=SIZE
Con -l, escala los tamaños por SIZE al imprimirlos; p. ej., '--block-size=M';  Ver el formato SIZE a continuación

-B, --ignore-backups
No listar las entradas implícitas que terminan en ~

-c con -lt: ordenar por y mostrar ctime (hora del último cambio de la información de estado del archivo); con -l: mostrar ctime y ordenar por nombre;
de lo contrario: ordenar por ctime, primero el más reciente

-C listar las entradas por columnas

--color[=CUÁNDO]
Colorear la salida CUÁNDO;  Más información a continuación

-d, --directory
Lista los directorios en sí, no su contenido

-D, --dired
Genera una salida diseñada para el modo dired de Emacs

-f Igual que -a -U

-F, --classify[=WHEN]
Añade un indicador (uno de */=>@|) a las entradas WHEN

--file-type
Igualmente, excepto que no añade '*'

--format=WORD
Horizontal, horizontal (-x), comas (-m), largo (-l), columna única (-1), verboso (-l), vertical (-C)

---full-time
Similar a -l ----time-style=full-iso

--g Similar a -l, pero no muestra el propietario

--group-directories-first
Agrupar directorios antes que archivos

-G, --no-group
En una lista larga, no imprimir nombres de grupos.

-h, --human-readable
Con -l y -s, imprimir tamaños como 1K, 234M, 2G, etc.

--si de la misma manera, pero usar potencias de 1000 en lugar de 1024.

-H, --dereference-command-line
Seguir enlaces simbólicos listados en la línea de comandos.

--dereference-command-line-symlink-to-dir
Seguir cada enlace simbólico de la línea de comandos que apunte a un directorio.

--hide=PATTERN
No listar entradas implícitas que coincidan con el patrón del shell (se sobrescribe con -a o -A).

--hyperlink[=WHEN]
Hiperenlace de nombres de archivos.

--indicator-style=WORD
Añadir indicador con estilo WORD a los nombres de entrada: ninguno (predeterminado), barra diagonal (-p), tipo de archivo (--file-type), clasificar.  (-F)

-i, --inode
Imprime el número de índice de cada archivo

-I, --ignore=PATTERN
No lista las entradas implícitas que coinciden con el patrón del shell

-k, --kibibytes
Por defecto, bloques de 1024 bytes para el uso del sistema de archivos; se usa solo con -s y totales por directorio

-l Usa un formato de listado largo

-L, --dereference
Al mostrar información de archivo para un enlace simbólico, muestra información del archivo al que hace referencia el enlace en lugar del enlace en sí

-m Rellena el ancho con una lista de entradas separadas por comas

-n, --numeric-uid-gid
Igual que -l, pero lista los ID numéricos de usuario y grupo

-N, --literal
Imprime los nombres de las entradas sin comillas

-o Igual que -l, pero no lista la información del grupo

-p, --indicator-style=slash
Añade/indicador a los directorios

-q, --hide-control-chars
Imprime ? en lugar de caracteres no gráficos

--show-control-chars
Mostrar caracteres no gráficos tal cual (predeterminado, a menos que el programa sea 'ls' y la salida sea una terminal)

-Q, --quote-name
Encierra los nombres de las entradas entre comillas dobles

--quoting-style=WORD
Usa el estilo de comillas WORD para los nombres de las entradas: literal, locale, shell,
shell-always, shell-escape, shell-escape-always, c, escape
(anula la variable de entorno QUOTING_STYLE)

--r, --reverse
Invierte el orden al ordenar

--R, --recursive
Lista los subdirectorios recursivamente

--s, --size
Imprime el tamaño asignado a cada archivo, en bloques

--S Ordena por tamaño de archivo, primero el más grande

--sort=WORD
Cambia el orden predeterminado de 'nombre' a WORD: ninguno (-U), tamaño (-S), hora (-t), versión (-v), extensión (-X), nombre, ancho

---time=WORD
Selecciona la marca de tiempo que se mostrará o  Ordenar; hora de acceso
(-u): atime, acceso, uso; hora de cambio de metadatos (-c): ctime, estado; hora de modificación (predeterminado): mtime, modificación; hora de nacimiento
: nacimiento, creación;

Con -l, WORD determina la hora a mostrar; con --sort=time,
ordenar por WORD (primero lo más reciente)

- ...  0 significa ilimitado

-x lista las entradas por líneas en lugar de por columnas

-X ordena alfabéticamente por extensión de entrada

-Z, --context
imprime el contexto de seguridad de cada archivo

-Z, --context
Imprime el contexto de seguridad de cada archivo.

--zero termina cada línea de salida con NUL, no con nueva línea.

--1 lista un archivo por línea.

--help muestra esta ayuda y sale.

--version muestra la información de la versión y sale.

El argumento SIZE es un entero y la unidad es opcional (ejemplo: 10K es 10*1024). Las unidades son K, M, G, T, P, E, Z, Y, R, Q (potencias de 1024) o KB, MB, etc. (potencias de 1000). También se pueden usar prefijos binarios: KiB=K, MiB=M, etc.

El argumento TIME_STYLE puede ser full-iso, long-iso, iso, locale o +FORMAT. FORMAT se interpreta como en date(1). Si FORMAT es FORMAT1<newline>FORMAT2, FORMAT1 se aplica a los archivos no recientes y FORMAT2 a los recientes.  TIME_STYLE, con el prefijo 'posix-', solo tiene efecto fuera de la configuración regional POSIX. Además, la variable de entorno TIME_STYLE establece el estilo predeterminado.

El argumento WHEN tiene como valor predeterminado 'always' y también puede ser 'auto' o 'never'.

El uso de colores para distinguir los tipos de archivo está deshabilitado tanto por defecto como con --color=never. Con --color=auto, ls emite códigos de color solo cuando la salida estándar está conectada a una terminal. La variable de entorno LS_COLORS puede cambiar la configuración. Utilice el comando dircolors(1) para configurarla.

Estado de salida:
0 si todo está correcto,
1 si hay problemas menores (p. ej., no se puede acceder al subdirectorio),
2 si hay problemas graves (p. ej., no se puede acceder al argumento de la línea de comandos).

AUTOR
Escrito por Richard M. Stallman y David MacKenzie.