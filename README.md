# dumbtipe

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
boton      grande verde      Entrar       -> mensaje ¡Hola!
└ qué es   └ cómo se ve       └ qué dice   └ qué hace al tocarlo
```

- **Primera palabra** = qué es
- **Las siguientes** = cómo se ve (o qué dice)
- **La sangría** = mete cosas dentro de un contenedor
- **`->`** = qué pasa al tocar

### Ejemplo completo

```
centro
  emoji gigante 🚀
  titulo gigante Mi tienda
  subtitulo La mejor del mundo
  boton grande verde Comprar -> mensaje ¡Gracias por tu compra!

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

### Acciones (después de `->`)
`-> mensaje texto` — muestra un aviso bonito
`-> alerta texto` — muestra una alerta
`-> abre url` — abre un enlace

---

## Qué incluye

- ✏️ **Editor en vivo** — escribes a la izquierda, ves el resultado a la derecha al instante
- 📦 **Exportar a HTML** — descarga un archivo que funciona solo, sin dumbtipe. Súbelo a internet y listo
- 📋 **Copiar HTML** al portapapeles
- 👀 Pestaña para ver el **HTML generado**
- 🧩 **Plantillas** de ejemplo (Hola, Landing, Formulario, Perfil)
- 💾 **Autoguardado** — no pierdes tu código al cerrar

---

## Cómo funciona por dentro

Todo está en un solo archivo, [`index.html`](index.html), en ~450 líneas de HTML + CSS + JavaScript (sin librerías). El intérprete tiene 3 pasos:

1. **`parsear()`** — lee tu texto, mide la sangría de cada línea y arma un **árbol** de elementos.
2. **`dibujar()`** — recorre el árbol y lo convierte en HTML.
3. **`generarHTMLApp()`** — empaqueta un archivo `.html` autónomo y exportable, con los estilos y las acciones incluidos.

---

Hecho con ganas de aprender cómo funcionan los lenguajes de programación. 🛠️
