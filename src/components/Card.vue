<script>
export default {
    data() {
        return {
            search: "",
            textdata: [
                { title: "McDonalds Cheese Burger Royal", link: "https://www.mcdonalds.com/", image: "./img/cheeseburger-royal.jpg" },
                { title: "McDonalds Double Cheese Burger Bacon", link: "https://www.mcdonalds.com/", image: "./img/double-cheeseburger-bacon.jpg" },
                { title: "McDonalds Hamburger", link: "https://www.mcdonalds.com/", image: "./img/hamburger.jpg" },
                { title: "Burger King 9 Chili Cheese Nuggets", link: "https://www.burger-king.ch/", image: "./img/chilli-cheese-nuggets.jpg" },
                { title: "Burger King Long Cajun Veggie", link: "https://www.burger-king.ch/", image: "./img/long-cajun-veggie.jpg" },
                { title: "Burger King Eiswaffel", link: "https://www.burger-king.ch/", image: "./img/eiswaffel.jpg" },
                { title: "KFC Cheese Bucket", link: "https://www.kfc-suisse.ch/", image: "./img/cheese-bucket.jpg" },
                { title: "KFC Cheesy Wrapper", link: "https://www.kfc-suisse.ch/", image: "./img/cheesy-wrapper.jpg" },
                { title: "KFC Cookie Chocolate", link: "https://www.kfc-suisse.ch/", image: "./img/cookie-chocolate.jpg" },
                { title: "Subway Spicy Veggie Patty", link: "https://www.subway.com/", image: "./img/spicy-veggie-patty.jpg" },
                { title: "Subway Potato Bites", link: "https://www.subway.com/", image: "./img/potato-bites.jpg" },
                { title: "Subway Chips", link: "https://www.subway.com/", image: "./img/chips.jpg" }
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
    </div>
    <div class="cards">
        <div class="card" v-for="food in searchFood">
            <img :src="food.image" />
            <div class="card-description">
                <h4>{{ food.title }}</h4>
                <a class="card-button" :href="food.link" target="_blank">Visit Homepage</a>
            </div>
        </div>
    </div>
</template>