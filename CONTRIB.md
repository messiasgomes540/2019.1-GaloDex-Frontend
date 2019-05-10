# Como contribuir com o projeto


## Construindo um componente

1. Crie um arquivo .vue na pasta components com o nome do componente
2. O conteudo deve serguir o seguinte padrão (consulte a documentação :thumbsup:)
```
/// src/components/menuInicial.vue
<script>
import Vue from "vue";
Vue.component("menu-inicial", {
  props: ["menu"],
  data() {
    return {
      ...
    };
  },
  methods: {
    ...
  },
  mounted() {
    ...
  },
  template: `
      <p> Hello World </p>
     `
});

export default {
  name: "menuInicial"
};

</script>
<style scoped>
</style>

```
3. Importe o componente no arquivo main.js
```
/// src/main.js
import Vue from "vue";
import App from "./App";
import router from "./router";

import "./components/cards/menuInicial";

new Vue({
  el: "#app",
  router,
  components: {
    App
  },
  template: "<App/>"
});

```

## Construindo uma tela com vue

1. Crie um arquivo .vue na pasta screens com o nome da tela e defina o html do layout
2. Importe a pagina criada no arquivo 'route/index.js' e adicione a pagina na lista de rotas
```
/// src/screens/HomePage.vue
import Vue from 'vue'
import Router from 'vue-router'
import HomePage from '@/components/HomePage'

Vue.use(Router)

export default new Router({
  routes: [
    {
      path: '/',
      name: 'HomePage',
      component: HomePage
    },
  ]
});
```
