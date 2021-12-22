<template>
    <main>
        <div class="container">
            <div class="discs-list">
                <SingleDisc v-for="(item, index) in discs" :key="index" :objectDisc="item"/>
            </div>
        </div>
    </main>
</template>


<script>
import axios from 'axios';
import SingleDisc from "./SingleDisc.vue";

export default {
    name: 'Main',
    components: {
        SingleDisc
    },
    data: function() {
        return {
            discs: []
        };
    },
    created: function() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.discs = response.data.response;
        });
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
