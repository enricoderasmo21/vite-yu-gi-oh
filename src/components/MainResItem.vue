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

    <div id="result" v-show="store.click">
       Carte trovate: <span id="num">{{ this.store.cards.length }}</span> 
    </div>
   
</template>

<style scoped lang="scss">
#result{
    display: flex;
    align-items: center;

    padding-left: 50px;
    padding-top: 6px;

    #num{
        font-weight: bold;
        font-size: 1.6em;

        color: #f0533f;
    }
}


</style>