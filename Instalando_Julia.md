# Instalando Julia

## Instalación desde un binario

La forma mas sencilla de instalar Julia es usando un binario: descarga el instalador adecuado para tu sistema operativo desde [aquí](http://julialang.org/downloads/).

Si estás utilizando Windows, probablemente también querrás instalar [`git` para Windows](https://msysgit.github.io/), el cual proporciona una terminal estilo Unix

## Instalando desde el código fuente

La instalación desde el código fuente ( la cual requiere compilar Julia en tu maquina ) tarda aproximadamente una hora.
En la terminal ejecuta lo siguiente:

```
$ git clone git@github.com:JuliaLang/julia.git
$ cd julia
$ make -j 4
```
El “-j 4” en la ultima linea indica que se van a usar cuatro núcleos (procesadores) para compilar Julia.

Se requiere tener otras herramientas previamente instaladas, `cmake` y `m4`; puedes ver los detalles completos en el  README de Julia [aqui](https://github.com/JuliaLang/julia).

# Herramientas 
Existen muchas herramientas para hacer más agradable y eficiente trabajar con Julia. Las que usaremos serán:
1. La terminal de Julia, REPL
1. Juno, IDE para Atom
2. Jupyter Notebooks

> Juno es para escribir código y analizar resultados. Jupyter Notebooks es para compartir resultados

## Julia REPL
The julia program starts the interactive REPL, the Read/Evaluate/Print/Loop, by default. It lets you type expressions in Julia code and see the results of the evaluation printed on the screen immediately. It:

* (**R**eads) lee lo que escribes
* **E**valúa 
* (**P**rints) Muestra en pantalla el resultado
* (**L**oops) Corre nuevamente todo el código

La termina REPL es un buen lugar para experiemntar con el lenguaje, pero no es el mejor entorno para escribir códigos completos para eso es mejor usar un editor de texto (como *Atom*, *Gedit*, *Emacs*, o cualquier editor de texto plano)
Es muy buena opción para consultar documentación o probar funciones.

## Juno

Juno es un Entorno de Desarrollo Integrado (IDE), para Julia. Lo puedes descargar desde  [aquí](http://junolab.org).
Básicamente es el editor de texto **Atom** diseñado especialmente para escribir código. Es posible cargar distintos complementos especializados para Julia

## Jupyter Notebooks

[IJulia](https://github.com/JuliaLang/IJulia.jl) es una interfaz de Julia para [Jupyter (antes IPython) notebook](http://ipython.org/), el cual estaremos usando extensivamente.
En [Juliabox](https://juliabox.com) puedes hacer registrarte y comenzar a usar Julia sin instalar desde el entorno de Jupyter notebooks (Nota: Es recomendable usar Pkg.update() en la primera sesión para actualizar la base de paquetes).

##
Primero necesitaras instalar IPython. [Actualmente las partes de Ipython que no se relacionan directamente con Python se están separando en un paquete llamdo Jupyter.] La manera mas sencilla de hacer esto es instalar la distribución gratuita de [Anaconda](http://continuum.io/downloads), la cual incluye IPython, la librería de graficación `matplotlib`, y varios paquetes útiles de Python.
##
Para instalar Jupyter notebooks (IJulia), escribe los siguientes comandos en la REPL:

```julia
Pkg.add("IJulia") # Instala el paquete
Pkg.clone("https://github.com/mvillasante/Programacion_I.git") # Clonas el repositorio para este curso
### Cada que abras una REPL tendrás que escribir
using IJulia
notebook(detached=true))
```
## Instalando librerías

Durante el curso vamos a usar distintas librerías, se recomienda instalar:

- Plots.jl para graficar. Este necesitará algunos backends:
  - PyPlot.jl
  - GR.jl
  - Plotly.jl
- MultivariateStats.jl
- GLM.jl

Librerías opcionales para ciertos ejemplos:

- DifferentialEquations.jl
- LightGraphs.jl
- ForwardDiff.jl
- NLsolve.jl
- JuMP
- BenchmarkTools.jl
- ProfileView.jl
- PkgDev.jl
 