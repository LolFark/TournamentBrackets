<template>
  <div class="players">
    <h1>{{ msg }}</h1>
    <div class="holder">
      <form @submit.prevent="addPlayer">
        <input type="text" placeholder="Enter player name.." v-model="player">
        <p>{{ player }}</p>
      </form>
      <ul>
        <li v-for="player in currentPlayers">{{ player.text }}
        <button v-on:click="remove(player)"></button>
        </li>
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
            },
            remove(p) {
                this.currentPlayers.splice(p,1);
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .holder {
    background: #fff;
  }

  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }

  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #EEEEEE;
    border-left: 1px solid #EEFFEE;
    margin-bottom: 2px;
    color: #3E5252;
  }

  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }
  button {
    float: right;
  }


</style>
