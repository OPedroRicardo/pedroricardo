<template lang="pug">
q-page-container
  section
    .row.items-center.justify-center.card
        img(src="../assets/my-photo.png" alt="Pedro Ricardo")
        span
          h2 Pedro Ricardo
          p Desenvolvedor Web Estagiário
          p 17 anos
          .row
            img(src="../assets/vue.svg" alt="vue")
            img(src="../assets/node.svg" alt="node")
            img(src="../assets/github.svg" alt="github")
            img(src="../assets/figma.svg" alt="figma")
  section.info.column.items-center.justify-center
    .row.items-center.justify-center
      span
        h3 Bem-vindo(a) ao meu mundo,
        p tento utilizar programação para automatizar funções para ajudar pessoas e negócios...
      q-icon.code(name="code")
    .row.items-center.justify-center
      q-icon.book(name="auto_stories")
      span
        h3 Eu amo ensinar
        p e aprender para poder melhorar minha capacidade de programar...
    a(href="https://www.buymeacoffee.com/pedroricardo" target="_blank")
      q-btn(no-caps) Give me a coffee
        img(src="../assets/coffee.svg")
  footer
    .row.justify-between.items-center
      a(href="https://www.youtube.com/channel/UCKi6AjFHHuk52p8o9JoorHw" target="_blank" title="youtube")
        img(src="../assets/youtube.svg" alt="youtube")
      a(href="mailto:dev.pedroricardo@gmail.com" target="_blank" title="email")
        img(src="../assets/gmail.svg" alt="gmail")
      a(href="https://www.linkedin.com/in/pedro-ricardo-almeida-954444196/" target="_blank" title="linkedin")
        img(src="../assets/linkedin.svg" alt="linkedin")
      a(href="https://opedroricardo.medium.com/" target="_blank" title="medium")
        img(src="../assets/medium.svg" alt="medium")
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex',
  data() {
    return {
      
    }
  },
})
</script>

<style lang="scss" scoped>
.q-page-container {
  
  section {
    padding: 66px 0 0 0;
    
    &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(132.62deg, #e49331, #a10000);
    clip-path: circle(20% at 200px 100px);
    z-index: -1;
  }

  &::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(139.66deg, #070566 12.23%, #a137f1 85.99%);
    clip-path: circle(20% at 1100px 400px);
    z-index: -1;
  }

    .card {
      max-width: 832px;
      height: 392px;
      width: 100%;
      margin: 0 auto 216px;
      gap: 3rem;

      background-color: rgba(34, 22, 49, 0.85);
      border-radius: 1rem;
      box-shadow: 22px 22px 46px rgba(0, 0, 0, 0.4), 
      inset 8px 8px 24px -5px rgba(255, 255, 255, 0.4);
      backdrop-filter: blur(22px);

      transform: translateZ(20px);

      img {
        width: 250px;
        height: 250px;
        border-radius: 50%;
      }

      span {
        h2 {
          font-size: 2rem;
          font-family: 'Poppins Bold';
          color: #fff;
          margin: 0;
        }
        
        p {
          font-size: 1.5rem;
          font-family: 'Poppins SemiBold';
          color: #fff;
          opacity: 0.75;
          margin: 0;
        }

        img {
          width: 55px;
          height: 55px;
          border-radius: 0;
        }

        div {
          margin: 1rem 0;
          gap: 1.5rem;
        }
      }
    }

  }

  .info {
    width: 100%;
    padding: 0 1rem;
    margin: 0;
    color: #27094E;
    
    div {
      max-width: calc(832px -2rem);
      width: 100%;
      gap: 2rem;
      margin: 46px auto;
    }

    span {
      width: 610px;
    }

    h3 {
      font-size: 2rem;
      font-family: 'JetBrains ExtraBold';
      margin: 0 0 1rem;
    }

    p {
      font-size: 2rem;
      font-family: 'JetBrains';
      margin: 0;
    }

    .q-icon {
      font-size: 190px;
    }

    .code {
      color: transparent;
      background: linear-gradient(90deg, #27094E 25%, #CD0F0F 108.95%);
      background-clip: text;
    }

    .book {
      color: transparent;
      background: linear-gradient(268.06deg, #27094E -10%, #CD0F0F 140%);
      background-clip: text;
    }
    
    a {
      text-decoration: none;
    }

    .q-btn {
      font-family: 'JetBrains Bold';
      font-size: 2rem;
      color: #fff;
      background: #27094E;
      transition: box-shadow 0.3s ease-in;

      &:hover {
        box-shadow: 6px 6px 23px rgba(0, 0, 0, 0.4);
      }
    }
  }

  footer {
    margin: 3rem 0 0;
    height: 84px;
    width: 100%;
    background: #27094E;

    a {
      cursor: pointer;
      transition: 0.3s;

      &:hover {
        opacity: 0.8;
      }
    }
    
    .row {
      max-width: 832px;
      width: 100%;
      height: 100%;
      margin: 0 auto;
    }
  }
}
</style>