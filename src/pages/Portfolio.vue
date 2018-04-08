<template>
  <v-ons-page>
    <p class="intro">
      Ici vous avez plusieurs exemples de mes projets créer durant mes études.<br><br>
    </p>
    <v-ons-card v-for="page of portfolio" :key="page.label">
      <div class="title">{{ page.label }}</div>
      <div class="content">{{ page.desc }}</div>
      <br>
      <!-- <a v-if="page.href" :href="page.github">Voir le code sur github</a> -->
      <v-ons-button modifier="large" class="button-margin" @click="openURL(null, page.github)">Voir le code sur github</v-ons-button>
      <br><br>
      <v-ons-button modifier="large" class="button-margin" @click="openURL(page.href, null)">Tester l'application web</v-ons-button>
    </v-ons-card>
  </v-ons-page>
</template>

<script>
export default {
  data () {
    return {
      portfolio: [
        {
          href: 'https://danielricklin.github.io/Lightbox/',
          label: 'Lightbox',
          desc: 'Carousel créer avec Jquery sous forme de module',
          github: 'https://github.com/DanielRicklin/Lightbox'
        },
        {
          href: 'https://danielricklin.github.io/EnglishVlog/',
          label: 'EnglishVlog',
          desc: 'Site de présentation en anglais + un vlog pour présenter la reserve de l\'armée de terre',
          github: 'https://github.com/DanielRicklin/EnglishVlog'
        }
      ]
    };
  },

  methods: {
    openURL(url, git){
        if(url!== null){
            window.open(url, '_blank');
        }else{
            window.open(git, '_blank')
        }
    }
  }
};
</script>

<style>
.intro {
  text-align: left;
  padding: 0 22px;
  margin-top: 20px;
  font-size: 14px;
  line-height: 1.4;
  color: rgba(0, 0, 0, .54);
}

ons-card {
  cursor: pointer;
  color: #333;
}

.card__title, .card--material__title {
  font-size: 20px;
}
</style>
