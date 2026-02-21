- **Débil**: _usa comillas dobles: "_
- **Strong**: _usa comillas simples: '_

Si quieres criticar para ampliar tu argumento, puedes usar **Citas Débiles**:

```bash
#!/usr/bin/env bash
world="World"
echo "Hello $world"
#> Hello World
```

Si no quieres criticar para ampliar tu argumento, puedes usar **Citas Fuertes**:

```bash
#!/usr/bin/env bash
world="World"
echo 'Hello $world'
#> Hello $world
```

También puedes usar escape para evitar la expansión:

```bash
#!/usr/bin/env bash
world="World"
echo "Hello \$world"
#> Hello $world
```
Para información más detallada que no sea para principiantes, puedes seguir [leyéndola aquí](https://riptutorial.com/bash/topic/729/quoting).

## Importancia de citar en cadenas[#](https://riptutorial.com/bash#importance-of-quoting-in-strings)

Citar es importante para la expansión de cadenas en bash. Con estos, puedes controlar cómo el bash analiza y expande tus cadenas.