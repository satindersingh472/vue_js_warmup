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
    let secrets = [`work hard`,`meditate`,`eat healthy`];
    for(let i = 0; i<secrets.length;i++){
       box[`innerHTML`] += `<p>${secrets[i]}</p>`;
       box.addEventListener(`click`,this.color_pink); 
    }
    let col = document.getElementById(`color`);
    col.addEventListener(`click`, this.change_color);
  },
  methods: {
    change_color(){
        let div = document.getElementById(`changing`);
        div[`style`][`backgroundColor`] = `blue`;
    },
    color_pink(details){
        details[`target`][`style`][`color`] = `pink`;
    }
  }
};
</script>

<style scoped>
div{
    height:100vh;
}
</style>