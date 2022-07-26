<template>
<main>
    <div class="container">
        <div class="box">
            <DiscCard />
        </div>
    </div>
</main>
</template>

<script>
import DiscCard from './DiscCard.vue';

export default {
    name: "ContentSection",
    components: { 
        DiscCard,
        }
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/vars';
    main{
        background-color: $dark_blue;
        height: 100vh;

        .box{
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;

            padding: 50px 0;
        }
    }
</style>