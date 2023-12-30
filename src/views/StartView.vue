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
        <h2 v-if="winner">Le gagnant est @{{ winner }} !</h2>
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
  font-size: 3rem;
}

.btn {
  font-size: 2rem;
  height: 4rem;
  padding-top: 0.5rem;
  background-color: #ffde37;
  border: none;
  text-transform: uppercase;
  cursor: pointer;
  font-family: "Helvetica Neue", Ubuntu, sans-serif;
}

.addplayer {
  margin-top: 2rem;
  font-size: 2rem;

  display: flex;
  flex-direction: column;
}

.addplayer input {
  border-radius: 0px;
  border: none;
  height: 4rem;
  padding: 1rem;
  margin-top: 1rem;
  margin-bottom: 1.5rem;
  font-size: 2rem;
}

.playerlist {
  max-height: 10rem;
  margin-top: 2rem;
  font-size: 2rem;
  max-height: 30vh;
  overflow-y: scroll;
}

.playerlist button {
  border: none;
  background: none;
  font-size: 2rem;
  color: red;
  cursor: pointer;
}

.playerwinner {
  margin-top: 2rem;
  font-size: 2rem;
}

.playerwinner button {
  padding-left: 2rem;
  padding-right: 2rem;
}

.playerwinner h2 {
  background: #ffde37;
  color: black;
  padding: 2rem;
  text-align: center;
  padding-top: 2rem;
  padding-bottom: 1.4rem;
  max-width: 100%;
}

@media (min-width: 1024px) {
  .start {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
