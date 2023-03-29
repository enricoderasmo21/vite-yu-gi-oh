<script>
import {store} from "../store.js"

export default{

    data() {
        return{

            store,
        }
    },

}
</script>

<template>

    <div id="search-title">RICERCA CARTE</div>

    <div id="search-container">
        <input id="search-bar" v-model="store.cardName" @keyup.enter="$emit('searchCard')" type="text" placeholder="Inserisci una parola chiave...">
        <button id="search-btn" @click="$emit('searchCard')">CERCA</button>
    </div>
   
</template>

<style scoped lang="scss">
#search-title{
    padding-top: 30px;
    padding-left: 50px;

    font-size: 2em;
    font-weight: bold;

    border-bottom: 3px solid #f0533f;

    color: white;
}

#search-container{
    padding-top: 30px;
    padding-left: 50px;

    #search-bar{
        margin-right: 20px;
        padding: 8px 20px;

        font-size: 1.2em;

        width: 300px;
    }

    #search-btn{
        padding: 8px 16px;
        border-style: none;
        border: 1px solid #f0533f;

        font-weight: bold;
        font-size: 1.2em;

        background-color: none;

        cursor: pointer;
    }
}


</style>