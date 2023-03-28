<script>
export default{
    data() {
        return{

            links: ["carte", "prodotti", "eventi", "gioca", "novità"],

            activeIndex: 0,
            
        }
    },

    methods: {

        activeLink(index){
            this.activeIndex = index; 
        }
    }
}
</script>

<template>
    <nav>
        <div id="container">
            <div id="logo-container">
                <img src="/img/logo.svg" alt="">
            </div>
            <div id="link-container">
                <ul>
                    <li v-for="(link, index) in links" @click="activeLink(index)" :class="index == activeIndex ? 'active' : ''"> {{ link.toUpperCase() }} </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<style scoped lang="scss">
#container{
    position: relative;

    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;

    height: 250px;

    background-color: #383635;

    box-shadow: 10px 15px 20px rgba(0,0,0,.6);

    #logo-container{
        width: 40%;

        img{
            width: 100%;
        }
    }

    #link-container{
        position: absolute;
        right: 0px;
        
        li{
            padding: 6px 50px;

            height: calc(100% / 5);

            font-weight: bold;
            font-size: 1.6em;

            cursor: pointer;

            &:hover{
                color: #f0533f;
            }
        }
    }
}
</style>