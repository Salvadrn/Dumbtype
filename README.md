# dumbtype

**Un lenguaje de programación donde escribes español sencillo y se vuelve una app.**

Escribes `boton grande verde Entrar` y aparece un botón grande verde que dice "Entrar". Así de fácil — por eso el nombre.

No necesitas instalar nada: es un solo archivo HTML. Ábrelo en tu navegador y empieza a escribir.

```
👉 Abre index.html en tu navegador
```

---

## Cómo se escribe

Cada línea es **un elemento**. La regla es siempre la misma:

```
boton      grande verde      Entrar       saludar()
└ qué es   └ cómo se ve       └ qué dice   └ qué hace al tocarlo
```

- **Primera palabra** = qué es
- **Las siguientes** = cómo se ve (o qué dice)
- **La sangría** = mete cosas dentro de un contenedor
- **`()` o `->`** = qué pasa al tocar

### Ejemplo completo

```
centro
  emoji gigante 🚀
  titulo gigante Mi tienda
  subtitulo La mejor del mundo
  boton grande verde Comprar (mensaje ¡Gracias por tu compra!)

separador

fila
  tarjeta
    titulo Envío gratis
    texto En todos los pedidos.
  tarjeta
    titulo Garantía
    texto 30 días para devolver.
```

---

## Funciones 🆕

Una **función** es un grupo de pasos al que le pones nombre, y lo puedes reutilizar en los botones que quieras. Se define con `()` y sus pasos van con sangría debajo:

```
funcion comprar()
  mensaje ¡Gracias por tu compra!
  abre https://mitienda.com

boton grande verde Comprar comprar()
boton chico Comprar otra vez comprar()
```

Los dos botones llaman a la misma función `comprar()`. Cambias la función una vez y cambian los dos botones.

### Tres formas de darle comportamiento a un botón

| Forma | Ejemplo | Cuándo usarla |
|-------|---------|---------------|
| **Función nombrada** | `boton Hola saludar()` | Varios pasos, o reutilizar en varios botones |
| **Acción inline** | `boton Hola (mensaje Qué tal)` | Una sola acción rápida |
| **Atajo** | `boton Hola -> mensaje Qué tal` | Lo mismo que inline, otra forma de escribirlo |

---

## Diccionario

### Elementos
`titulo` · `subtitulo` · `texto` · `boton` · `campo` · `area` · `imagen` · `video` (también de YouTube) · `enlace` · `lista` (separa con comas) · `emoji` · `separador` · `espacio`

### Contenedores
Lo que escribas **con sangría** debajo va adentro.

`tarjeta` · `fila` (lado a lado) · `columna` · `centro`

### Cómo se ven (modificadores)
**Tamaño:** `grande` `gigante` `chico`
**Color:** `rojo` `azul` `verde` `amarillo` `naranja` `rosa` `morado` `gris` `negro`
**Estilo:** `redondo` `negrita` `cursiva` `subrayado` `centrado` `sombra` `ancho`

### Acciones (lo que un botón puede hacer)
`mensaje texto` — muestra un aviso bonito
`alerta texto` — muestra una alerta
`abre url` — abre un enlace

---

## Qué incluye

- ✏️ **Editor en vivo** — escribes a la izquierda, ves el resultado a la derecha al instante
- 🔧 **Funciones** reutilizables con `()`
- 📦 **Exportar a HTML** — descarga un archivo que funciona solo, sin dumbtype. Súbelo a internet y listo
- 📋 **Copiar HTML** al portapapeles
- 👀 Pestaña para ver el **HTML generado**
- 🧩 **Plantillas** de ejemplo (Hola, Landing, Formulario, Perfil)
- 💾 **Autoguardado** — no pierdes tu código al cerrar

---

## Cómo funciona por dentro

Todo está en un solo archivo, [`index.html`](index.html), en HTML + CSS + JavaScript (sin librerías). El intérprete tiene 3 pasos:

1. **`parsear()`** — lee tu texto, mide la sangría de cada línea y arma un **árbol** de elementos. Las definiciones `funcion x()` se guardan aparte con sus pasos.
2. **`dibujar()`** — recorre el árbol y lo convierte en HTML. Los botones guardan su comportamiento en atributos `data-fn` / `data-accion`.
3. **`generarHTMLApp()`** — empaqueta un archivo `.html` autónomo y exportable, con los estilos, las funciones y los manejadores de clic incluidos.

---

Hecho con ganas de aprender cómo funcionan los lenguajes de programación. 🛠️
