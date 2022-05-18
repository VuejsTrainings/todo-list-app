<template>
  <form class="row">
    <h2>Ajouter une todo</h2>
    <div class="mb-3">
      <label for="titre" class="form-label">Titre</label>
      <input
        type="text"
        class="form-control"
        id="titre"
        placeholder="Titre"
        v-model="newTodoTitre"
      />
    </div>
    <div class="mb-3">
      <label for="importance" class="form-label">Importance</label>
      <select
        class="form-control"
        id="importance"
        placeholder="Importance"
        v-model="newTodoImportance"
      >
        <option
          v-for="importance in importances"
          :key="importance.id"
          :value="importance.intitule"
        >
          {{ importance.intitule }}
        </option>
      </select>
    </div>
    <div class="row">
      <button
        class="btn btn-primary col-5 col-md-2 col-lg-1"
        @click.prevent="ajouteTodo"
      >
        OK
      </button>
      <button
        class="btn btn-primary col-5 col-md-2 col-lg-1 ms-2"
        @click.prevent="$emit('ajout-annule')"
      >
        Annuler
      </button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      importances: [
        {
          id: 1,
          intitule: "Haute",
        },
        {
          id: 2,
          intitule: "Moyenne",
        },
        {
          id: 3,
          intitule: "Basse",
        },
      ],
      newTodoImportance: "",
      newTodoTitre: "",
    };
  },
  methods: {
    ajouteTodo() {
      this.$emit("ajoute", {
        titre: this.newTodoTitre,
        importance: this.newTodoImportance,
        finie: false,
      });
    },
  },
};
</script>

<style></style>
