<template>
  <div class="hello">
    <img alt="Vue logo" src="../assets/logo.png">
    <div class="locale-changer">
        <!-- <select v-model="$i18n.locale">
          <option v-for="(lang, i) in langs" :key="i" :value="lang">{{ lang }}</option>
        </select> -->
        <img src="../assets/en.svg" alt="en" @click="langChange('en')">
        <img src="../assets/fr.svg" alt="fr" @click="langChange('fr')">
        <img src="../assets/it.svg" alt="it" @click="langChange('it')">
    </div>
    <h1>{{ $t('message') }}</h1>
    <p>{{ $t('text') }}</p>
    
    <div class="attribute">Icons made by <a href="https://www.flaticon.com/authors/freepik" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      langs: ['en', 'it', 'fr']
    }
  },
  methods: {
    langChange(l) {
      this.$i18n.locale=l;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.locale-changer {
  position: flex;
}
.locale-changer img {
  margin: 0 10px;
  width: 32px;
  height: auto;
  cursor: pointer;
}
.attribute {
  margin-top:70px;
  font-size: 0.6em;
}
</style>
