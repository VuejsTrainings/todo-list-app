<template>
  <div>
    <section class="row todos">
      <todo-item
        v-for="(todo, index) in todos"
        :key="todo.id"
        :todo="todo"
        @change="todos[index].finie = !todos[index].finie"
      >
      </todo-item>
    </section>
    <!-- Bouton pour ajout -->
    <p classs="row" v-if="!ajoutEnCours">
      <button class="btn btn-success" @click.prevent="ajoutEnCours = true">
        <span class="icon">+</span> Ajouter
      </button>
    </p>
    <todo-form
      v-else
      @ajout-annule="annulerAjout"
      @ajoute="ajouterTodo"
    ></todo-form>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
import TodoForm from "./TodoForm.vue";

export default {
  name: "TodosModule",
  components: {
    TodoItem,
    TodoForm,
  },
  data() {
    return {
      ajoutEnCours: false,
      todos: [
        {
          id: 1,
          titre: "Réserver le logement pour les vacances",
          description: "Voir les campings et locations à Saint-Trompette",
          importance: 1,
          echeance: "2022-05-29",
          finie: false,
        },
        {
          id: 2,
          titre: "Faire la danse du soleil",
          description:
            "Surtout ne pas chanter, sous peine de faire revenir la pluie...",
          importance: 2,
          echeance: "2022-05-30",
          finie: false,
        },
        {
          id: 3,
          titre: "Signer la déclaration d'impôts",
          description: "Sur le site Web des impôts",
          importance: 3,
          echeance: "2022-05-29",
          finie: true,
        },
        {
          id: 4,
          titre: "Apprendre Vue.js",
          description: "",
          importance: 3,
          echeance: "2022-06-01",
          finie: false,
        },
        {
          id: 5,
          titre: "Courir 5km",
          description: "Si possible sans s'arrêter et en moins de 30mn",
          importance: 2,
          echeance: "2022-05-30",
          finie: false,
        },
        {
          id: 6,
          titre: "Commander du café",
          description: "En grande quantité!!!",
          importance: 1,
          echeance: "2022-05-07",
          finie: true,
        },
        {
          id: 7,
          titre: "Réparer le rétroprojecteur",
          description: "",
          importance: 1,
          echeance: "2022-05-12",
          finie: false,
        },
      ],
    };
  },
  methods: {
    annulerAjout() {
      this.ajoutEnCours = false;
    },
    ajouterTodo(todo) {
      this.todos.push(todo);
      this.ajoutEnCours = false;
    },
  },
};
</script>
<style scoped>
.icon {
  font-weight: bolder;
}
</style>
