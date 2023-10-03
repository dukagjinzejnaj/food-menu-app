<script>
import image1 from "@/assets/img/cheeseburger-royal.jpg";
import image2 from "@/assets/img/double-cheeseburger-bacon.jpg";
import image3 from "@/assets/img/hamburger.jpg";
import image4 from "@/assets/img/chilli-cheese-nuggets.jpg";
import image5 from "@/assets/img/long-cajun-veggie.jpg";
import image6 from "@/assets/img/eiswaffel.jpg";
import image7 from "@/assets/img/cheese-bucket.jpg";
import image8 from "@/assets/img/cheesy-wrapper.jpg";
import image9 from "@/assets/img/cookie-chocolate.jpg";
import image10 from "@/assets/img/spicy-veggie-patty.jpg";
import image11 from "@/assets/img/potato-bites.jpg";
import image12 from "@/assets/img/chips.jpg";


export default {
    data() {
        return {
          search: "",
          textdata: [
            { title: "McDonalds Cheese Burger Royal", link: "https://www.mcdonalds.com/", image: image1 },
            { title: "McDonalds Double Cheese Burger Bacon", link: "https://www.mcdonalds.com/", image: image2 },
            { title: "McDonalds Hamburger", link: "https://www.mcdonalds.com/", image: image3 },
            { title: "Burger King 9 Chili Cheese Nuggets", link: "https://www.burger-king.ch/", image: image4 },
            { title: "Burger King Long Cajun Veggie", link: "https://www.burger-king.ch/", image: image5 },
            { title: "Burger King Eiswaffel", link: "https://www.burger-king.ch/", image: image6 },
            { title: "KFC Cheese Bucket", link: "https://www.kfc-suisse.ch/", image: image7 },
            { title: "KFC Cheesy Wrapper", link: "https://www.kfc-suisse.ch/", image: image8 },
            { title: "KFC Cookie Chocolate", link: "https://www.kfc-suisse.ch/", image: image9 },
            { title: "Subway Spicy Veggie Patty", link: "https://www.subway.com/", image: image10 },
            { title: "Subway Potato Bites", link: "https://www.subway.com/", image: image11 },
            { title: "Subway Chips", link: "https://www.subway.com/", image: image12 }
          ]
        }
    },
    computed: {
      searchFood() {
			  return this.textdata.filter(food => food.title.toLowerCase().includes(this.search.toLowerCase()));
		  }
    }
}
</script>

<template>
    <div class="search">
        <input type="text" v-model="search" class="searchform" placeholder="Essen suchen.."/>
        <br>
        <p class="text-center" v-if="searchFood.length === 0">Leider wurden keine Ergebnisse für Ihre Suchanfrage gefunden.</p>
    </div>
    <div class="row">
      <div class="col-lg-4" v-for="food in searchFood">
        <div class="card mb-3">
            <img class="card-img-top" :src="food.image" />
          <div class="card-body">
            <h3 class="card-title">{{ food.title }}</h3>
            <a class="card-button" :href="food.link" target="_blank">Seite besuchen</a>
          </div>
        </div>
      </div>
    </div>
</template>