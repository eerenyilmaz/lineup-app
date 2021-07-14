<template>
  <div>

    <h1 :style="[customStyle]">Goalkeeper</h1>
    <appGoalkeeper v-for="player in playerList">
      <!--<img class="card-img-top" :src="player.selectedImage" :alt="player.title">-->
      <div class="card-body">
        <h5 class="card-title"> {{ player.name }}</h5>
        <small><strong>Number : </strong> {{ player.number }}</small>
        <br>
        <small><strong>Price : </strong> {{ player.price }}</small>
        <br>
      </div>
    </appGoalkeeper>

    <h1>Defence</h1>
    <appDefence v-for="player in defenceList" >
      <!--<img class="card-img-top" :src="player.selectedImage" :alt="player.title">-->
      <div class="card-body">
        <h5 class="card-title"> {{ player.name }}</h5>
        <small><strong>Number : </strong> {{ player.number }}</small>
        <br>
        <small><strong>Price : </strong> {{ player.price }}</small>
        <br>
      </div>
    </appDefence>


    <h1>Midfielder</h1>
    <appMidfielders v-for="player in mfList">
      <!--<img class="card-img-top" :src="player.selectedImage" :alt="player.title">-->
      <div class="card-body">
        <h5 class="card-title"> {{ player.name }}</h5>
        <small><strong>Number : </strong> {{ player.number }}</small>
        <br>
        <small><strong>Price : </strong> {{ player.price }}</small>
        <br>
      </div>
    </appMidfielders>

    <h1>Attack</h1>
    <appAttack v-for="player in attackList">
      <!--<img class="card-img-top" :src="player.selectedImage" :alt="player.title">-->
      <div class="card-body">
        <h5 class="card-title"> {{ player.name }}</h5>
        <small><strong>Number : </strong> {{ player.number }}</small>
        <br>
        <small><strong>Price : </strong> {{ player.price }}</small>
        <br>
      </div>
    </appAttack>

  </div>
</template>

<script>
import Goalkeeper from "./positionComponents/Goalkeeper";
import Defence from "./positionComponents/Defence";
import Midfielders from "./positionComponents/Midfielders";
import Attack from "./positionComponents/Attack";
import { eventBus } from "../main";

export default {
  components : {
    appGoalkeeper : Goalkeeper,
    appDefence : Defence,
    appMidfielders : Midfielders,
    appAttack : Attack,
  },
  data (){
    return {
      playerList :[],
      defenceList : [],
      mfList : [],
      attackList : [],
      displayHeader : false,
    }
  },
  created() {
    eventBus.$on("playerAdded", (player) =>{

      if(this.playerList.length < 1){
        this.playerList.push(player);
      }else if(this.defenceList.length < 4){
        this.defenceList.push(player);
      }else if(this.mfList.length < 4){
        this.mfList.push(player);
      }else if(this.attackList.length < 2){
        this.attackList.push(player);
      }else{
        alert("Enough for team");
      }

    })
  },
  methods :{
    setTrueHeader : function (){
      if(this.playerList.length != 0 && this.defenceList.length != 0 && this.mfList.length != 0 && this.attackList.length != 0)
      {
        this.displayHeader = !this.displayHeader;
      }
    }
  },
  computed : {
    customStyle : function (){
      return {

      }
    }
  }
}
</script>

<style scoped>

</style>
