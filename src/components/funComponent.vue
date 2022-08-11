<template>
  <div id=changing>
    <button id="color">change color</button>
    <div id="secrets">

    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    let box = document.getElementById(`secrets`);
    for(let i = 0; i< this.secrets.length;i++){
       box[`innerHTML`] += `<p class="indiv">${this.secrets[i]}</p>`;
    }
    let col = document.getElementById(`color`);
    col.addEventListener(`click`, this.change_color);

    let indiv = document.getElementsByClassName(`indiv`);
    for(let k = 0; k<indiv.length;k++){
      indiv[k].addEventListener(`click`,this.color_pink);
    }
  },


  methods: {
    change_color(){
        let div = document.getElementById(`changing`);
        div[`style`][`backgroundColor`] = `blue`;
    },
    color_pink(details){
        details[`target`][`style`][`color`] = `pink`;
    }
  },


  data() {
    return {
        secrets: [`work hard`,`meditate`,`eat healthy`]
    };
  },

};
</script>

<style scoped>
div{
    height:100vh;
}
</style>