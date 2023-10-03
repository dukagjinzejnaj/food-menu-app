<script>
import Card from './Card.vue';
import Header from './Header.vue';
import Footer from './Footer.vue';

export default {
    data() {
      return {
        darkMode: false
      }
    },
    components: {
        Card,
        Header,
        Footer
    },
    watch: {
        darkMode() {
            this.$emit('btn-click-darkMode');

            if(this.darkMode == true) {
              document.body.classList.add("theme-dark")
            } else {
              document.body.classList.remove("theme-dark")
            }

            localStorage.setItem("darkMode", JSON.stringify(this.darkMode));
        }
    },
    mounted() {
      this.darkMode = JSON.parse(localStorage.getItem("darkMode"));
    }
}
</script>

<template>
    <Header v-if="darkMode" @btn-click-darkMode="darkMode = !darkMode" switchMode="Lightmode" />
    <Header v-else @btn-click-darkMode="darkMode = !darkMode" switchMode="Darkmode" />
    <div class="container-md">
        <Card />
    </div>
    <Footer />
</template>