NOMBRE
pwd - Imprime el nombre del directorio actual/de trabajo

SINOPSIS
pwd [OPCIÓN]...

DESCRIPCIÓN
Imprime el nombre completo del directorio de trabajo actual.

-L, --logical
Usa PWD del entorno, incluso si contiene enlaces simbólicos.

-P, --physical
Resuelve todos los enlaces simbólicos.

--help Muestra esta ayuda y sale.

--version
Muestra la información de la versión y sale.

Si no se especifica ninguna opción, se asume -P.

Tu shell puede tener su propia versión de pwd, que suele reemplazar la versión descrita aquí. Consulta la documentación de tu shell para obtener más información sobre las opciones compatibles.

AUTOR
Escrito por Jim Meyering.