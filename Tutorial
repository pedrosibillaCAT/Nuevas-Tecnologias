# Tutorial_Vuejs

Vue es un marco progresivo para construir interfaces de usuario, está diseñado desde cero para ser adoptable gradualmente,
vuejs se centra solo en la capa de vista y es fácil de recoger e integrar con otras bibliotecas o proyectos existentes

## Instalación

lo primero que debemos hacer es instalar Vuejs con el comando npm
En el caso que no tengas instalado npm, se instala de la siguiente manera

<pre>
sudo apt-get install nodejs
</pre>
y luego 
<pre>
sudo apt-get install npm
</pre>
Una vez instalado npm vamos a instalar vuejs
<pre>
npm install -g @vue/cli
</pre>
ademas instalaremos la extencion de google de vuejs
Link de extencion de google: https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd?hl=es


## Empezando

Una vez que hayamos terminado de instalar todo. lo primero que debemos hacer es, iniciar un nuevo proyecto vue, donde este se creara con todos los archivos predeterminados ncesarios para correr el proyecto.
<pre>
vue create my-app
</pre>

Luego empezamos a desarrollar nuestra app, lo primero que debemos saber es que vue funciona a partir de componentes, entonces luego de crear el proyecto empezamos a crear cada componente que va a tener, cada componente se crea dentro de la carpeta components como un arvicho con .vue nuevo, por ej(archvio.vue)

## Ejemplo Nuevas tecnologias

Nuestra aplicacion contiene el archivo padre o ```app.vue``` y 4 componentes dentro de la carpeta components ```Search.vue```, ```TodoAdd.vue```, ```TodoIte.vue```, ```app.vue```. Despues de crear los componentes que vamos a utilizar en nuestra aplicacion debemos saber que cada componente debe tener su parte de ```<template>```,```<script>``` y ```<style>```, voy a pasar a mostrarles como se escribe un componente: 
```python
<template>
  <div>
    <form @submit="addTodo">
      <v-row align="center" justify="center" >
        <v-spacer></v-spacer>
        <v-col cols="12" md="11" align="center">
          <v-text-field label="Add" v-model="title"></v-text-field>
        </v-col>
        <v-spacer></v-spacer>
      </v-row>
    </form>
  </div>
</template>

<script>
import { uuid } from "vue-uuid";

export default {
  name: "TodoAdd",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();

      const newTodo = {
        id: uuid.v4(),
        title: this.title,
        completed: false,
      };

      this.title = "";
      this.$emit("add-todo", newTodo);
    },
  },
};
</script>
```


luego en la capa padre o ```app.vue``` importamos los componentes y definimos lo metodos, y se hace de la siguente manera:


```
<script>
import TodoAdd from "./components/TodoAdd";

export default {
  name: "App",
  components: {
    TodoAdd,
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo);
      this.copyTodos = [...this.todos];
    },
    querySearch(query) {
      if (query.trim() === "") {
        this.copyTodos = [...this.todos];
      } else {
        const temp = this.todos.filter((todo) => {
          return todo.title.includes(query);
        });
        this.copyTodos = [...temp];
      }
    },
  },
  data() {
    return {
      todos: [
        {
          id: 0,
          title: "Sol de medianoche",
          completed: false,
        },
        {
          id: 1,
          title: "Caste: The Origins of Our Discontents",
          completed: true,
        },
        {
          id: 2,
          title: "Mi historia",
          completed: false,
        },
        {
          id: 3,
          title: "White Fragility",
          completed: true,
        },
      ],
      copyTodos: [],
    };
  },
  created() {
    this.copyTodos = [...this.todos];
  },
};
</script>
```
Esto fue un ejemplo de un componente vue y como se importan en el archivo padre a continuacion les dejo el enlace del proyecto completo con todos los componentes y funciones: https://github.com/eduluduena/Nuevas-Tecnologias.git
