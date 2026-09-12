# Tarea #1: Gramática BNF

Proyecto del curso **Compiladores e Intérpretes**, II semestre de 2026, del Instituto Tecnológico de Costa Rica.

## Integrantes

- Angelo Piedra Castro - 2024101262
- Elian Trejos Quiros - 2024143262

## Descripción

Se diseñó la gramática BNF de un lenguaje de programación imperativo y ligero, orientado a la configuración de chips y al desarrollo de sistemas empotrados.

El lenguaje permite:

- Declarar variables globales y locales de tipo `int`, `float`, `bool`, `char` y `string`.
- Declarar arreglos estáticos unidimensionales de enteros o flotantes.
- Usar expresiones aritméticas, relacionales y lógicas con precedencia definida.
- Definir funciones con parámetros y retorno.
- Utilizar las estructuras `if`, `elif`, `else`, `while` y `for`.
- Leer y escribir valores mediante `read` y `write`.
- Usar `return`, `break` e incrementos y decrementos.
- Escribir comentarios de línea y de bloque.
- Incluir obligatoriamente un procedimiento de entrada llamado `principal`.

## Estructura del repositorio

La gramática se desarrolló por módulos para facilitar su organización y mantenimiento. El archivo consolidado contiene todas las producciones.

```text
.
├── Gramatica/
│   └── expresiones/
│       ├── comentarios.bnf
│       ├── expr_algebraicas.bnf
│       ├── expr_literales.bnf
│       ├── expr_logica.bnf
│       ├── expr_relacional.bnf
│       ├── funciones.bnf
│       ├── programa.bnf
│       ├── sent_control.bnf
│       ├── sent_read_write.bnf
│       └── var_arrays.bnf
├── documentacion/
│   ├── documentacion.docx
│   └── producciones.bnf
└── info.txt
```

### Módulos de la gramática

- [`expr_literales.bnf`](Gramatica/expresiones/expr_literales.bnf): literales enteros, flotantes, booleanos, caracteres y cadenas.
- [`expr_algebraicas.bnf`](Gramatica/expresiones/expr_algebraicas.bnf): identificadores, arreglos, llamadas a funciones y expresiones aritméticas.
- [`expr_relacional.bnf`](Gramatica/expresiones/expr_relacional.bnf): comparaciones de orden e igualdad.
- [`expr_logica.bnf`](Gramatica/expresiones/expr_logica.bnf): conjunción, disyunción y negación lógica.
- [`var_arrays.bnf`](Gramatica/expresiones/var_arrays.bnf): declaraciones, asignaciones y acceso a arreglos.
- [`comentarios.bnf`](Gramatica/expresiones/comentarios.bnf): comentarios de línea y de bloque.
- [`sent_read_write.bnf`](Gramatica/expresiones/sent_read_write.bnf): sentencias de entrada y salida.
- [`sent_control.bnf`](Gramatica/expresiones/sent_control.bnf): retornos, ciclos y estructuras condicionales.
- [`funciones.bnf`](Gramatica/expresiones/funciones.bnf): funciones, parámetros y función principal.
- [`programa.bnf`](Gramatica/expresiones/programa.bnf): composición completa de un programa.

La versión consolidada se encuentra en [`producciones.bnf`](documentacion/producciones.bnf).

## Símbolo inicial

El símbolo inicial es `programa`:

```bnf
programa ::= elemento_programa* funcion_principal elemento_programa*
```

Esto permite cero o más declaraciones globales y funciones antes y después de una única función principal obligatoria:

```bnf
funcion_principal ::= void principal open_paren close_paren bloque
```

## Notación propia

El lenguaje utiliza símbolos definidos específicamente para esta gramática:

| Elemento | Notación |
| --- | --- |
| Asignación | `Ͱ` |
| Fin de sentencia | `»` |
| Apertura y cierre de bloque | `¿:` y `:?` |
| Apertura y cierre de índice o comparación | `ʃ:` y `:ʅ` |
| Apertura y cierre de expresión lógica | `є:` y `:э` |
| Potencia | `pot` |
| División entera | `//` |
| Módulo | `mod` |
| Conjunción lógica | `λ` |
| Disyunción lógica | `θ` |
| Negación lógica | `Σ` |
| Incremento y decremento | `++` y `--` |

Las producciones separan los niveles de precedencia de las expresiones aritméticas, evitando una regla genérica de la forma `expr op expr`.

## Objetivos alcanzados

La gramática cubre los tipos de datos solicitados, expresiones aritméticas con precedencia y operadores unarios, expresiones relacionales y lógicas, variables y arreglos, estructuras de control, entrada y salida, comentarios, funciones con parámetros y retorno, y el procedimiento `principal` obligatorio.

## Documentación

La explicación completa del diseño, la lista de terminales y no terminales, el análisis de resultados, las lecciones aprendidas y la bitácora se encuentra en [`documentacion.docx`](documentacion/documentacion.docx).

## Repositorio

El historial de desarrollo, incluidos los commits y pull requests de cada módulo, está disponible en:

<https://github.com/StevenXoFk/Tarea-1-Compiladores-e-Interpretes>