# Animaciones Web

### Tabla de contenido
- [Introducción a las animaciones y micro interacciones en la web](#Introducción-a-las-animaciones-y-micro-interacciones-en-la-web)
- [Sintaxis de transiciones](#Sintaxis-de-transiciones)
- [Sintaxis de Transformaciones](#Sintaxis-de-Transformaciones)
- [Transformaciones de rotación](#Transformaciones-de-rotación)
- [Transformaciones de translacion](#Transformaciones-de-translacion)
- [perspectiva](#perspectiva)
- [Transformaciones de escala](#Transformaciones-de-escala)
- [Transformaciones de sesgados](#Transformaciones-de-sesgados)
- [Punto de transformación](#Punto-de-transformación)
- [Sintaxis animaciones](#Sintaxis-animaciones)



### Introducción a las animaciones y micro interacciones en la web
¿Qué son la animaciones?

- La transición que ocurre entre un punto A y un punto B.
- Son parte natural de las interfaces web.
- Son una forma natural de enseñanza para el usuario.
- Ayudan a conectar una interfaz que solo está programada en algo que realmente está vivo.
- La acción de un usuario interactuando con la interfaz y que ésta le de feedback de lo que está ocurriendo.

**Recuerda:**
Las animaciones en una interfaz web son necesarias, ya que ninguna acción que ocurre en ésta se da de forma instantánea.

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Sintaxis de transiciones

- transition-property: propiedad que se aplicara
- transition-duration: duracion de la transision
- transition-delay: tiempo de demora para que se ejecute 
- transition-timing-function: aceleracion


```
.pelota {
  width: 100px;
  heigth:100px;
  background-color:red;
  transition-property: width, height;
  transition-duration: 1s;
  transition-delay: 1s;
  transition-timing-function: ease;
}

.pelota:hover {
  width:200px;
  heigth: 200px;
}
```

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>


### Sintaxis de Transformaciones

Algunas de las cosas que podemos lograr en un elemento con `transform` son:

- `rotate` Rotar un elemento.
- `skew` Sesgar un elemento.
- `translate`Cambiar la posición de un elemento.
- `scale` Cambiar el tamaño de un elemento (0-1).

```
.canasta {
transform: rotate(5deg) skew(10deg) translate(100px) scale(1.5);
}
```

### Transformaciones de rotación
- transform: rotate(45deg) // giro con reloj 
- transform: rotate(-45deg) // giro contra reloj 
- transform: rotatex(45dg) // giro sobre su eje X
- transform: rotatey(45dg) // giro sobre su eje y
- transform: rotatez(45dg) // giro sobre su eje y
<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Transformaciones de translacion
- transform: translate(x, y)
- transform: translate(-x, -y)
- transform: translatex(100px)
- transform: translatey(100px)
- transform: translatez(100px)
- transform: translate3d(x,y,z)

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### perspectiva
- perspective: 200px
- perspective-origin: center // perspectiva por defecto 
- perspective-origin: x y 
- perspective-origin: top
- perspective-origin: bottom
- perspective-origin: left
- perspective-origin: right
- perspective-origin: top right
- perspective-origin: top left
- perspective-origin: bottom left
- perspective-origin: bottom right

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Transformaciones de escala
`Transform-scale` nos permite modificar el tamaño de nuestros elementos a nuestro gusto.

La medición del tamaño de un elemento con scale, es la siguiente:

0 = 0% del tamaño.
1 = 100% del tamaño.

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Transformaciones de sesgados
Sesgar es esa inclinación que puede sufrir un elemento gracias a una transformación en CSS.

Se puede sesgar un elemento tanto de un solo eje, como de ambos:

- transform: skew (x);
- transform: skew (y);
- transform: skew (x, y);

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Punto de transformación
El punto de transformación de un elemento está clavado en alguna parte de la interfaz, y por defecto se encuentra en el centro.

Sin embargo, podemos jugar con la posición de este punto según el tipo de animación que queramos crear.

- transform-origin: 50% 50%
- transform-origin: x y 
- transform-origin: top
- transform-origin: bottom
- transform-origin: left
- transform-origin: right
- transform-origin: left top
- transform-origin: right top
- transform-origin: left bottom
- transform-origin: right bottom

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### Sintaxis animaciones

animation-name: cuadrado; // nombre de la animacion
animation-duration: 1s // tiempo de duracion 
animation-delay: 1s // tuempo de espera para ejecutarse
animation-oiteration-count: 2, infinite // veses que se repite
animation-timing-function:ease, ease-in, ease-out, easein-out, linear // velocidad
animation-timing-function: cubic-besier(1,1,1,1) // velocidad
animation-direction: reverse, alternate // direccion 
animation-fill-mode: forwards // como queda nuestra animacion al terminar
animation-play-state: paused, running

```
@keyframe "nombre" {
	0% { opacity: 1;}
	100% { opacity: 0;}
}
```

```
@keyframe "nombre" {
	from { opacity: 1;}
	to{ opacity: 0;}
}
```
<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>


### Optimizar render con will-change y developer tools
usando el inspector de elementos podemos ver y depurar nuestras animaciones 

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>


### Propiedades animables
```
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties
```
<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>

### element.animate
```
<script>
    const $pelota = document.getElementById('pelota');

    // element.animate(keyframes = [], option = {})
    const animation = $pelota.animate([
      // from
      {
        transform: 'translateX(0)'
      },
      // to
      {
        transform: 'translateX(500px)' // 250
      }
    ],{
      duration: 1000,
      delay: 1000,
      direction: 'normal',
      easing: 'linear',
      iterations: Infinity,
      fill: 'forwards',
      iterationStart: .5, // = 50%
      // endDelay: 5000,
    })
  </script>
```

<div align ="right">
  <small><a href="#tabla-de-contenido">🡡 volver al inicio</a></small>
</div>
