<template>
  <div id="add-player-app">

    <div class="add-div">
      <img height="150" width="150" class="add-img" src="../assets/add_icon.png">
      <button class="select-button">Select Photo</button>
      <select name="cars" id="cars">
        <option @click="select442" value="442">4-4-2</option>
        <option @click="select433" value="433">4-3-3</option>
        <option @click="select352" value="352">3-5-2</option>
        <option @click="select343" value="343">3-4-3</option>
      </select>
      <button class="add-button" style="margin-top: 10px; width: 50%">OK</button>
    </div>

    <div class="input-div">

        <div class="card-body">
          <div class="form-group">
            <label>Player Name </label>
            <input type="text"  v-model="player.name" class="form-control" placeholder="Enter Player Name">
          </div>
          <div class="row">
            <div class="form-group col-md-12">
              <label>Player Number</label>
              <input type="number" v-model="player.number" class="form-control" placeholder="Enter Player Number...">
            </div>
            <div class="form-group col-md-12">
              <label>Player Price</label>
              <input type="number" v-model="player.price" class="form-control" placeholder="Enter Player Price">
            </div>
          </div>
          <button class="add-button" @click="addProduct">Add!</button>

        </div>


    </div>

  </div>
</template>

<script>

import { eventBus } from "../main";

export default {
    name: "AddPlayer",

      data () {
        return {
          playerList : [],
          defenceList : [],
          mfList : [],
          attackList : [],

          player : {
            name : null,
            number : null,
            price : null,
            selectedImage : null
          }
        }
      },
      methods :{
        addProduct(){
          eventBus.$emit("playerAdded", this.player);
          this.player ={
            name : null,
              number : null,
              price : null,
              selectedImage : null
          }

        },

        select442 : function (){
          console.log("442")
        },
        select433 : function (){
          console.log("433")
        },
        select352 : function (){
          console.log("352")
        },
        select343 : function (){
          console.log("343")
        }

      }
    }

</script>

<style scoped>

#add-player-app{
  flex-direction: row;
  display: flex;
  width: 1000px;
  margin-left: auto;
  margin-right: auto;
  border: 2px dashed black;
}

.add-div{
  flex-direction: column;
  display: flex;
  height: auto;
  width: 40%;
  height: 400px;
  border-right: 2px dashed black;
}
.input-div{
  flex-direction: column;
  display: flex;
  width: 60%;
  height: 400px;

}

.add-img{
  margin-left: auto;
  margin-right: auto;
  margin-top: 50px;
}
.select-button{
  border-radius: 5px;
  width: 120px;
  height: 40px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  background: #A71919;
  color: #fdbf00;
  cursor: pointer;
  border: none;
  margin-right: auto;
  margin-left: auto;
}
.add-button{
  border-radius: 5px;
  width: 100%;
  height: 40px;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  background: #A71919;
  color: #fdbf00;
  cursor: pointer;
  border: none;
  margin-right: auto;
  margin-left: auto;
}
button:hover{
  opacity: 50%;
}
.input-div label{
  color: #A71919;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  font-size: 20px;
}
select{
  border: none;
  background-color: #A71919;
  color: #fdbf00;
  font-style: oblique;
  width: 50%;
  margin-right: auto;
  margin-left: auto;
  margin-top: 50px;
}
</style>
