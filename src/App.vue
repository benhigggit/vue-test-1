<template>
  <div id="app">
    <b-button variant="primary" @click="fetchCharacters"><h3>{{title}}</h3></b-button>
    <b-container v-if="characters">
      <b-row>
        <b-col cols="4" v-for="result in characters" :key="result.id">
          <CharacterCard :character="result"/>
        </b-col>
        
      </b-row>
    </b-container>
    
     </div>

    
</template>

<script>
import CharacterCard from './components/CharacterCard'

export default {
  name: 'App',
  data() {
    return {
      characters: [],
      title: "Create Your Team"
    }
  },
  components: {
    CharacterCard
  },
  methods: {
    fetchCharacters(){
      this.characters = []
      this.fetchCharacter(Math.floor(Math.random() * 83) + 1)
      this.fetchCharacter(Math.floor(Math.random() * 83) + 1)
      this.fetchCharacter(Math.floor(Math.random() * 83) + 1)
    },
    fetchCharacter(id) {
            fetch(`https://swapi.co/api/people/${id}`, {
            method: 'GET'
            })
            .then(response => response.json())
            .then(json => {
              let character = json
              character.id = id
              this.characters.push(character)
            })
        }
  }
    
    
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
