<script>
import MainCardItem from './MainCardItem.vue';
import axios from "axios";
import {store} from "../store.js"

export default{
    data() {
        return{

            store,
        }
    },

    components: {
        MainCardItem,

    },

    created() {

        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=1000&offset=0').then((res) => {

            console.log(res.data.data);
            this.store.cards = res.data.data;
        });
    }
}
</script>

<template>
    <main>
        
        <div id="cards-container" v-if="store.cards.length > 0">
            <MainCardItem v-for="card in store.cards" :card="card"></MainCardItem>
        </div>
        <div id="loading" v-else>
            Loading...
        </div>
    </main>
</template>

<style scoped lang="scss">
#loading{
    padding-top: 100px;

    text-align: center;

    font-weight: bold;
    font-size: 3em;
}
#cards-container{
    display: flex;
    flex-flow: row wrap;
    gap: 30px;

    padding: 50px 0;

    width: 90%;
    margin: 0 auto;
    
}
</style>