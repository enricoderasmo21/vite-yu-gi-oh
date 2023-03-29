<script>
import MainCardItem from './MainCardItem.vue';
import MainSearchItem from './MainSearchItem.vue';
import MainResItem from './MainResItem.vue';

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
    MainSearchItem,
    MainResItem
    },
    
    created() {
        
        axios.get(this.store.APIcall).then((res) => {
            
            console.log(res.data.data);
            this.store.cards = res.data.data;
        });
    },
    
    methods:{
        
        search() {
            
            let apiNewString = this.store.APIcall
            
            if(this.store.cardName != "") {
                
                apiNewString += `&fname=${this.store.cardName}`;
                
                axios.get(apiNewString).then((res) => {
                    
                    this.store.cards = res.data.data;
                    this.store.click = true;
                });
            }
        }
    }
}
</script>

<template>
    <main>
        
        <MainSearchItem @searchCard="search()"></MainSearchItem>
        <MainResItem></MainResItem>

        
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