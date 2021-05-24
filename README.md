<p align="center">
    <img src="https://github.com/AJ-Wi/AJ-Wi.github.io/blob/master/images/AJ-Wi.svg" width="300" title="images">
</p>

## CustomMenu

Un pequeño componente de menu para proyectos pequeños y rapidos.

solo se incorpora en la carpeta de components de tu proyecto lo importas en la vista que lo requiera

```javascript
<script>
import navegacion from "@/components/BaseMenu.vue";

export default {
  name: "App",
  components: {
    navegacion,
  },
};
</script>
```

posteriormente lo llamas desde tu template y listo

```html
<template>
  <navegacion />
</template>
```

Para configurar los items del menu lo puedes hacer en el Data del componente

```javascript
<script>
export default {
  data() {
    return {
      lista: ["Item-uno", "Item-dos", "Item-tres"],
    };
  },
};
</script>
```

## BaseInput

Este componente solo incorpora estilos a un input normal, la estructura del custom input es la siguiente:

```html
<BaseInput v-model="text" name="text" type="text"> text </BaseInput>
```

## BaseSVG

Imagen SVG personalizada creada en vuejs, con una sintaxis limpia y fácil de utilizar, la estructura de esta imagen es la siguiente:

```html
<training
  level="2"
  locked="false"
  sublevel="2"
  bike="2"
  active="true"
></training>
```

La estructura generada en el html es un SVG con las especificaciones dadas en los atributos.

<p align="center">
    <img src="public/bike.png" width="250" title="images">
</p>
