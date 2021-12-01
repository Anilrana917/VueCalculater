<template>
<div id="Home">
 <input v-model="inputData" type="text"> 
 <br>
 <button @click="additions" class="btn">+</button>
 <button @click="deletion" class="btn">-</button>
 <button @click="multiplication" class="btn">*</button>
 <button @click="divided" class="btn">/</button>
 <button @click="isEqual" class="btn">=</button>
 <button @click="clear" class="btn">C</button>

</div>
</template>

<script>
export default {
  name: "Home",
  data(){
    return {
      inputData: "", 
      count:0,
      typeofOperation: ""
    }
  },
  watch: {
  },

  methods: {
    additions(){
      // console.log(this.inputData);
      this.inputData = this.inputData.concat("+");
      this.typeofOperation = "addition"
    },
    deletion(){
      // console.log(this.inputData);
      this.inputData = this.inputData.concat("-");
      this.typeofOperation = "deletion"
    },
    multiplication(){
      this.inputData = this.inputData.concat("*");
       this.typeofOperation = "multiplication"
    },
    divided(){
      this.inputData = this.inputData.concat("/");
      this.typeofOperation = "divided"
    },
    isEqual(){
      if(this.typeofOperation == "addition"){
      let data = this.inputData.split("+");
      let result = parseInt(data[0]) + parseInt(data[1])
      this.inputData = this.inputData.concat("=");
      this.inputData = this.inputData.concat(result)
      }

      else if (this.typeofOperation == "deletion"){
      let data = this.inputData.split("-");
      let result = parseInt(data[0]) - parseInt(data[1])
      this.inputData = this.inputData.concat("=");
      this.inputData = this.inputData.concat(result)
      }

      else if (this.typeofOperation == "multiplication"){
      let data = this.inputData.split("*");
      let result = parseInt(data[0]) * parseInt(data[1])
      this.inputData = this.inputData.concat("=");
      this.inputData = this.inputData.concat(result)
      }

      else if (this.typeofOperation == "divided"){
      let data = this.inputData.split("/");
      let result = parseInt(data[0]) / parseInt(data[1])
      this.inputData = this.inputData.concat("=");
      this.inputData = this.inputData.concat(result)
      }

      else{
        console.log("I'm from else")
      }
      

    },
    clear(){
      this.inputData = "";
    }
  }
  

}
</script>

<style>
button.btn {
    padding: 6px;
    margin: 5px;
}
</style>

