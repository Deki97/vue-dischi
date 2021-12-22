<template>
    <main>
        <div class="container">
            <div class="discs-list">
                <SingleDisc />
                <SingleDisc />
                <SingleDisc />
                <SingleDisc />
                <SingleDisc />
                <SingleDisc />
                <SingleDisc />
                <SingleDisc />
                <SingleDisc />
                <SingleDisc />
            </div>
        </div>
    </main>
</template>


<script>
import SingleDisc from "./SingleDisc.vue";

export default {
    name: 'Main',
    components: {
        SingleDisc
    }
}
</script>


<style scoped lang="scss">
@import '../style/variables';


main {
    background-color: $page_primary-color;
    padding: 50px 0;
    .container {
        .discs-list {
            display: flex;
            flex-wrap: wrap;
        }
    }
}
</style>
