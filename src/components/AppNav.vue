<script>
export default{
    data() {
        return{

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
        </div>
    </nav>
</template>

<style scoped lang="scss">
#container{
    display: flex;
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
}
</style>