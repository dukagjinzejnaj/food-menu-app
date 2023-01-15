<script>
import Header from './Header.vue'
import Card from './Card.vue'
import Footer from './Footer.vue'

export default {
    data() {
      return {
        darkMode: false
      }
    },
    components: {
        Header,
        Card,
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
    <div class="theme">
        <Header v-if="darkMode" @btn-click-darkMode="darkMode = !darkMode" switchMode="Light" />
        <Header v-else @btn-click-darkMode="darkMode = !darkMode" switchMode="Dark" />
        <Card />
        <Footer />
    </div>
</template>