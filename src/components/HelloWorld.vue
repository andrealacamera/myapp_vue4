<template>
  <div class="container">
    <img alt="Vue logo" src="../assets/logo.png">
    <div class="locale-changer" v-if="viewlang">
        <span @click="langChange('en')" :class="{'selected': $i18n.locale==='en'}">En</span> | 
        <span @click="langChange('fr')" :class="{'selected': $i18n.locale==='fr'}">Fr</span> |
        <span @click="langChange('it')" :class="{'selected': $i18n.locale==='it'}">It</span>
        <!-- <img src="../assets/en.svg" alt="en" @click="langChange('en')">
        <img src="../assets/fr.svg" alt="fr" @click="langChange('fr')">
        <img src="../assets/it.svg" alt="it" @click="langChange('it')"> -->
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
      viewlang: true,
      langs: ['en', 'it', 'fr']
    }
  },
  created: function() {
    var cc = this.getCookie("pll_language");
    if (cc != "") {
      this.viewlang=false;
      this.$i18n.locale=cc;
    }
  },
  methods: {
    langChange(l) {
      this.$i18n.locale=l;
    },
    getCookie(cname) {
      var name = cname + "=";
      var decodedCookie = decodeURIComponent(document.cookie);
      var ca = decodedCookie.split(';');
      for(var i = 0; i <ca.length; i++) {
        var c = ca[i];
        while (c.charAt(0) == ' ') {
          c = c.substring(1);
        }
        if (c.indexOf(name) == 0) {
          return c.substring(name.length, c.length);
        }
  }
  return "";
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  display: block;
  justify-content: center;
}
.locale-changer {
  color: #888;
  position: flex;
  justify-content: end;
  cursor: pointer;
}
.selected {
  color: #222;
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
