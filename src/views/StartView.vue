<template>
  <div class="about">
    <h2>Création de la liste</h2>

    <div class="wrapper">
      <div class="addplayer">
        <label for="newPlayer">Ajouter un joueur :</label>
        <input v-model="newPlayer" type="text" id="newPlayer" />
        <button class="btn" @click="addPlayer">Ajouter</button>
      </div>

      <div class="playerlist">
        <h3 v-for="(player, index) in players" :key="index">
          @{{ player }} <button @click="removePlayer(index)">✖</button>
        </h3>
      </div>

      <div class="playerwinner" v-if="players.length > 0">
        <button class="btn" @click="pickWinner">WHO WIN ?</button>
        <div v-if="winner" class="winnerbox">
          <h2>Le gagnant est</h2>
          <h2>{{ winner }} !</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newPlayer: "",
      players: [],
      winner: null,
    };
  },
  methods: {
    addPlayer() {
      if (this.newPlayer.trim() !== "") {
        this.players.push(this.newPlayer.trim());
        this.newPlayer = "";
      }
    },

    removePlayer(index) {
      this.players.splice(index, 1);
    },

    pickWinner() {
      const randomIndex = Math.floor(Math.random() * this.players.length);
      this.winner = this.players[randomIndex];
    },
  },
};
</script>

<style>
h2 {
  margin-top: 2rem;
  font-size: 2rem;
  text-align: right;
  cursor: default;
}

.btn {
  text-decoration: none;
  width: 50%;
  font-size: 1rem;
  height: 2rem;
  background-color: #ffde37;
  border: none;
  text-transform: uppercase;
  cursor: pointer;
  font-family: "Rubik", Ubuntu, sans-serif;
  -webkit-box-shadow: -1px 1px 5px 2px rgba(0, 0, 0, 0.6);
  box-shadow: -1px 1px 5px 2px rgba(0, 0, 0, 0.6);
}

.btn:hover {
  background-color: #fff2b4;
}

.addplayer {
  margin-top: 2rem;
  font-size: 1rem;

  display: flex;
  flex-direction: column;
}

.addplayer input {
  width: 100%;
  border-radius: 0px;
  border: none;
  height: 4rem;
  padding: 1rem;
  margin-top: 1rem;
  margin-bottom: 2rem;
  font-size: 2rem;
  -webkit-box-shadow: -1px 1px 5px 2px rgba(0, 0, 0, 0.6);
  box-shadow: -1px 1px 5px 2px rgba(0, 0, 0, 0.6);
}

.playerlist {
  margin-top: 1rem;
  font-size: 1rem;
  text-align: right;
}

.playerlist button {
  border: none;
  background: none;
  text-decoration: none;
  font-size: 1rem;
  color: rgb(230, 0, 0);
  cursor: pointer;
}

.winnerbox {
  background: #ffde37;
  color: black;
  margin-top: 2rem;
  padding: 2rem;
  -webkit-box-shadow: -1px 1px 5px 2px rgba(0, 0, 0, 0.6);
  box-shadow: -1px 1px 5px 2px rgba(0, 0, 0, 0.6);
}

.winnerbox h2 {
  padding: 0;
  margin: 0;
  font-size: 2rem;
  text-align: center;
  text-shadow: none;
}

@media (min-width: 1024px) {
}
</style>
