<template lang="pug">
div
  .row.items-center
    q-btn(
      v-show="!onFirst && !running"
      v-for="(frase, index) in frases"
      transition-show="slide-down"
      icon="circle"
      @click="carousel = index; onFirst = false; runAnimation();"
      :text-color="carousel === index ? 'primary' : 'secondary'"
      unelevated
    )
  span.q-ma-none.frase {{ fraseAtual }}
    span.q-ma-none(:class="console ? 'hidden' : ''") &#95;
</template>

<script>
export default ({
  name: 'PageIndex',
  data() {
    return {
      carousel: 0,
      running: false,
      console: true,
      onFirst: true,
      fraseAtual: '',
      frases: ['Olá, meu nome é Pedro Ricardo', ' Eu tenho 17 anos', ' Sou um dev ;)']
    };
  },
  methods: {
    runAnimation() {
      this.fraseAtual = '';
      this.running = true;
      let i = 0;
      const interval = setInterval(() => {
        this.fraseAtual += this.frases[this.carousel][i];
        if(!this.onFirst && i >= this.frases[this.carousel].length - 1) {
          clearInterval(interval);
          this.running = false;
          return;
        }
        if (this.carousel >= 2 && i >= this.frases[this.carousel].length - 1) {
          clearInterval(interval);
          this.onFirst = false;
          this.running = false;
          return;
        }
        if(i >= this.frases[this.carousel].length - 1) {
          clearInterval(interval);
          setTimeout(() => {
            this.carousel++;
            this.fraseAtual = '';
            this.running = false;
            this.runAnimation();
          }, 2000);
        }
        i++;
      }, 150);
    }
  },
  created() {
    setInterval(() => {
      this.console = !this.console;
    }, 500);
    this.runAnimation();
  },
});
</script>

<style lang="scss" scoped>
span {
  height: 102px;
  font-family: 'jetBrains';
  letter-spacing: -10px;
  font-size: 76px;
  color: $primary;
}

.hidden {
  opacity:0;
}

@media (max-width: 850px) {
  span {
    font-size: 2rem;
    letter-spacing: -1px;
    line-height: 2.6rem;
  }
}
</style>