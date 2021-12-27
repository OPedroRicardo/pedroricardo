<template lang="pug">
q-header(class="row items-top justify-center bg-dark")
  a(v-for="item in social" target="_blank" :href="item.link" :title="item.title").q-ma-md
    img(:src="item.img" :alt="item.title")
q-page-container(class="column items-center justify-between no-wrap" style="height: 100vh")
  main.row.items-center.justify-center
    .column.justify-center.no-wrap.about
      about-me
      .row.items-center.justify-start.techs
        .q-mr-xl
          h4 Utilizo no dia a dia
          img(v-for="tech in techs" :src="tech.img" :title="tech.title" :alt="tech.title")
        div
          h4 Aprendendo
          img(v-for="tech in learning" :src="tech.img" :title="tech.title" :alt="tech.title")
    img(src="astronauta.svg" class="astronauta" alt="Um astronauta, dando uma ideia de que estamos explorando o espaço.")
  .flex.flex-center
    a(href="https://www.freelancer.com/u/opedroricardo")
      q-btn(label="Meus Freelas" color="primary" no-caps size="xl" class="q-ma-xl")
</template>

<script>
import aboutMe from '../components/aboutMe.vue';

export default ({
  name: 'PageIndex',
  data() {
    return {
      social: [
        {
          link: 'https://www.buymeacoffee.com/pedroricardo',
          img: 'icons/social/buymeacoffee.svg',
          title: 'Buy me a coffee'
        },
        {
          link: 'https://github.com/OPedroRicardo',
          img: 'icons/social/github.svg',
          title: 'GitHub'
        },
        {
          link: 'https://www.linkedin.com/in/opedroricardo/',
          img: 'icons/social/linkedin.svg',
          title: 'LinkedIn'
        },
      ],
      techs: [
        {
          img: 'icons/techs/vue.svg',
          title: 'Vue.js'
        },
        {
          img: 'icons/techs/node.svg',
          title: 'Node.js'
        },
        {
          img: 'icons/techs/figma.svg',
          title: 'Figma'
        },
      ],
      learning: [
        {
          img: 'icons/techs/my-sql.svg',
          title: 'My SQL'
        },
        {
          img: 'icons/techs/python.svg',
          title: 'Python'
        },
      ],
    };
  },
  components: {
    aboutMe,
  }
});
</script>

<style lang="scss" scoped>
a img {
  transition: all 0.4s ease-in-out;
  padding: 0.5rem;

  &:hover {
    opacity: 0.4;
  }
}

main {
  flex-wrap: nowrap;
}

.about {
  width: 45vw;
  height: 90%;
  margin: 0 10%;
}

h4 {
  color: $secondary;
  font-size: 2rem;
  margin: 0;
  letter-spacing: -4px;
}

.astronauta {
  max-width: 577.96px;
  width: 40vw;
  animation: astronaut 40s linear infinite;
  z-index: 2;

  @keyframes astronaut {
      0% {
        top: 0;
      }

      50% {
        transform: rotate(20deg);
      }

      100% {
        transform: rotate(0deg);
      }
  }
}

.techs {
  img {
    width: 60px;
    margin: 1rem 1rem 1rem 0;
    cursor: pointer;

    &:hover {
      animation: upper 0.8s linear infinite;
    }

    

    @keyframes upper {
      0% {
        top: 0;
      }

      50% {
        position: relative;
        top: -10px
      }

      100% {
        top: 0;
      }
    }
  }
}

@media (max-width: 850px) {
  h4 {
    font-size: 1rem;
    letter-spacing: -2px;
  }

  main {
    flex-wrap: wrap;
  }

  .about {
    width: 100vw;
  }

  .techs img {
    margin: 0 8px 0 0;
    width: 2.5rem;
  }
}
</style>