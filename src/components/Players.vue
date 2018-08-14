<template>
  <div class="players">
    <h1>{{ msg }}</h1>
    <div class="holder">
      <form @submit.prevent="addPlayer">
        <input type="text" placeholder="Enter player name.." v-model="player">
        <p>{{ player }}</p>
      </form>
      <ul>
        <li v-for="player in currentPlayers">{{ player.text }}</li>
      </ul>
      <p v-if="currentPlayers.length < 1">No players added</p>
      <p v-else># of players: {{ currentPlayers.length}}</p>
    </div>
  </div>
</template>

<script>
    export default {
        name: 'players',
        data() {
            return {
                player: "",
                msg: 'Add players',
                currentPlayers: [
                ]
            }
        },
        methods: {
            addPlayer() {
                this.currentPlayers.push({text: this.player});
                this.player = "";
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h3 {
    margin: 40px 0 0;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    font-weight: bold;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
</style>
