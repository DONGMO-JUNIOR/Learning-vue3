<template>
    <div>
      <div class="bordure">
        <input type="text" v-model="tache" placeholder="Entrer une tâche">
        <button @click="ajouter">Ajouter</button>
        <p v-if="message" class="error">{{ message }}</p>
  
        <ul>
          <li v-for="(t, index) in liste" :key="index">
            <div v-if="editionIndex === index">
              <input v-model="tacheEditée" @keyup.enter="validerEdition(index)">
              <button @click="validerEdition(index)">valider</button>
            </div>
            <div v-else>
              {{ t }}
              <button @click="activerEdition(index, t)">edit</button>
            </div>
          </li>
        </ul>
      </div>
  
     
      <h2>Options - {{ o_firstname }}</h2>
      <h2>Options - {{ o_firstname }} {{ o_lastname }} a.k.a {{ o_Heroname }}</h2>
      <br><hr>
      <h2>Composition - {{ greet }}</h2>
      <h2>{{ greetHero }}</h2>
      <br><hr>
      <h2>Composition - {{ c_firstname }}</h2>
      <h2>Composition - {{ state.firstName }} {{ state.lastName }} {{ state.heroName }}</h2>
      <h2>Composition - {{ reactiveGreetHero }}</h2>
    </div>
  </template>
  
  <script>
  import { ref, reactive } from 'vue'
  
  export default {
    name: 'DataApp',
    setup() {
      const c_firstname = ref('Nior Le boss')
      const c_lastname = ref('Kent')
      const c_heroname = ref('Supermant')
  
      const greet = `Hello ${c_firstname.value}`
      const greetHero = `Hello ${c_firstname.value} ${c_lastname.value} a.k.a ${c_heroname.value}`
  
      const state = reactive({
        firstName: 'Princess',
        lastName: 'Diana',
        heroName: 'Wonder Woman'
      })
  
      const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`
  
      return {
        c_firstname,
        c_lastname,
        c_heroname,
        greet,
        greetHero,
        state,
        reactiveGreetHero
      }
    },
    data() {
      return {
        isdesable: false,
        tache: '',
        liste: [],
        message: '',
        editionIndex: null,
        tacheEditée: '',
        listRender: ['jojo', 'junior', 'use3', 'use4', 'use5'],
        yourName: '<b>bonjour monsieur</b>',
        o_firstname: 'Junior',
        o_lastname: 'Dongmo',
        o_Heroname: 'Batman'
      }
    },
    methods: {
      ajouter() {
        if (this.tache.trim() === '') {
          this.message = 'Faut mettre quelque chose avant de saisir';
        } else {
          this.liste.push(this.tache);
          this.tache = '';
          this.message = '';
        }
      },
      activerEdition(index, tache) {
        this.editionIndex = index;
        this.tacheEditée = tache;
      },
      validerEdition(index) {
        if (this.tacheEditée.trim() !== '') {
          this.liste[index] = this.tacheEditée;
          this.editionIndex = null;
          this.tacheEditée = '';
        }
      }
    }
  }
  </script>
  
  <style scoped>
  .divName {
    width: 200px;
    padding: 20px;
    background: blue;
    color: white;
    box-shadow: 0 4 2;
    border-radius: 10px;
  }
  .error {
    color: red;
  }
  .bordure {
    border-radius: 15px;
    width: 100vh;
    min-height: 200px;
    padding: 25px;
    border: solid black;
    margin-bottom: 40px;
  }
  </style>
  