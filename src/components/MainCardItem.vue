<script>

export default{
    data() {
        return{

            hover: false,

        }
    },

    props: {
        card: Object,
    }
}
</script>

<template>
    <div class="card" @mouseover="hover = true" @mouseleave="hover = false" :class="hover == true ? 'hover' : ''">
        <div class="img-container">
            <img :src="card.card_images[0].image_url" alt="">
        </div>
        <div class="info" v-show="hover" >
            <span class="info-title">Name:</span> {{ card.name }} <br>
            <span class="info-title">Price:</span> {{ card.card_prices[0].amazon_price }} € <br>
            <span class="info-title">Type:</span> {{ card.frameType }} <br>
        </div>


    </div>
</template>

<style scoped lang="scss">

.card{
    position: relative;

    width: calc(100% / 4 - 30px);

    .img-container{
        width: 100%;

        img{
            width: 100%;

            box-shadow: 8px 8px 10px rgba(0,0,0, .4);

            transition: all .2s ease-in-out;

            &:hover{
                transform: scale(0.7);
                translate: (0px -60px);
            }
        };
    }

    .info{
        position: absolute;
        bottom: 0px;

        width: 100%;

        padding: 8px 10px;

        border: 3px solid #f0533f;

        font-size: 1.2em;
        font-weight: bold;

        color: white;

        z-index: 0;

        .info-title{
            color: #f0533f;

            font-size: 0.8em;
        }
    }

   
}

</style>