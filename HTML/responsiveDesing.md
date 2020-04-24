# Curso Responsive desing


### Tabla de contenido
- [Conceptos elementales de Responsive Design](#Conceptos-elementales-de-Responsive-Design)
- [Meta viewport](#Meta-viewport)
- [Medidas relativas útiles en Responsive Design](#Medidas-relativas-útiles-en-Responsive-Design)
- [Media queries](#Media-queries)
- [Formas de incluir media queries](#Formas-de-incluir-media-queries)
- [posiciones ](#posiciones)


### Conceptos elementales de Responsive Design
Para abordar el campo del Responsive Design es necesario que tengas claridad sobre algunos conceptos básicos.

Por este motivo, durante esta clase aprenderás qué es el Responsive Design, cuáles son los lenguajes de programación que lo hacen posible, qué medidas son necesarias aplicar para lograr que tus proyectos se adapten a pantallas de diversas medidas y condiciones, cuáles son los principios del Responsive Design (mostly fluid, colocación de columnas, layout shifter, tiny tweaks, off canvas).

Finalmente, aprenderás el objetivo principal del Responsive Design: la óptima visualización de las web sites en cualquier dispositivo y podrás tener referentes en www.mediaqueri.es .

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Meta viewport

Area visible del website, la podemos ajustar desde la etiketa meta con los atributos 
- content 
- initial-scale

```bash
<meta name=“viewport” content=“width=device-width, initial-scale=1.0”>
```

### Medidas relativas útiles en Responsive Design

- `%` (longitud referente al tamaño de los elementos padre)
- `em` (unidad relativa al tamaño de fuente especificada más cercano)
- `rem` (unidad relativa al tamaño de fuente especificada en el ancestro más lejano, como html o body)
- `viewport` vw/vh (longitud relativa porcentual con respecto al viewport).

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Media queries
Para que logres los resultados que deseas en tus proyectos, es necesario cambiar ciertas propiedades para modificar el tamaño de los textos, contenidos y hojas de estilo; la manera de hacer esto es el media queries.

El media queries es un módulo de css que hace posible al responsive design, éste existe desde el 2010 y se encarga de adaptar la representación del contenido a características del dispositiv

```bash

@media screen and (max-width: 768px) and (min-width:320px) { }

// Mobile first
@media screen and (min-width: 320px) { }
@media screen and (min-width: 480px) { }
@media screen and (min-width: 768px) { }
@media screen and (min-width: 1024px) { }

//Desktop first
@media screen and (max-width: 1024px) { }
@media screen and (max-width: 768px) { }
@media screen and (max-width: 480px) { }
@media screen and (max-width: 320px) { }

```

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Formas de incluir media queries

podemos incrustar nuestros estilos con media queri de 3 formas 

- incluir una Hoja de estilos externa que se ejecute cuando se cumpla nuestro mediaqueri
```bash
<linkrel="stylesheet" href="css/media.css" media="screen and (max-width: 400px)"/>
```
- desde la etiqueta style en nuestro html 
```bash
<style> 
	@media screen and (max-width: 768px) { 
		body { 
			border: 10px solid green; 
		} 
	} 
</style>
```
- desde un archivo css
```bash
@media screen and (max-width: 768px) { 
	body { 
		border: 10px solid green; 
	} 
}
```
<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### posiciones 
las posiciones nos indican como se comportaran los elementos en los documentos html

existen 5 tipos de posiciones

- static (posicion por defecto)
- relative (activa propiedades z-index y atributos para direccionar)
- absolute (se apega al objeto padre que tenga una posicion relativa o al ultimo elemento del codigo como body o html)
- fixed (se fija a la posicion asignada)
- sticky (elemento que sigue en pantalla cuando hacemos scroll)


al usar las posiciones se desbloquean los siguientes atributos 

- z-index
- top
- rigth 
- bottom
- left 

lo ejecutamos en css de la siguiente forma :
```bash
p span {

	position: relative;
};

```


