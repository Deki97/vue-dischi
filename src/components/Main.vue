<template>
    <main>
        <div class="container">
            <SelectFilter @selectClicked="selectDone" />
            
            <div v-if="!isLoadingApi">
                <div v-if="filteredGenres.length > 0" class="discs-list">
                    <SingleDisc v-for="(item, index) in filteredGenres" :key="index" :objectDisc="item"/>
                </div>

                <div class="no-results" v-else>
                    Nessun risultato per il tipo di genere selezionato
                </div>
            </div>

            <Loader v-else />
        </div>
    </main>
</template>


<script>
import axios from 'axios';
import SingleDisc from "./SingleDisc.vue";
import Loader from "./Loader.vue";
import SelectFilter from "./SelectFilter.vue";

export default {
    name: 'Main',
    components: {
        SingleDisc,
        Loader,
        SelectFilter
    },
    data: function() {
        return {
            discs: [],
            valueSelected: '',
            isLoadingApi: true
        };
    },
    methods: {
        selectDone: function(value) {
            this.valueSelected = value;
        }
    },
    computed: {
        filteredGenres: function() {
            if(this.valueSelected === '') {
                return this.discs;
            }

            const filteredArray = this.discs.filter((item) => {
                return item.genre.toLowerCase().includes(this.valueSelected.toLowerCase());
            });

            return filteredArray;
        }
    },
    created: function() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.discs = response.data.response;

            this.isLoadingApi = false;
        });
    }
}
</script>


<style scoped lang="scss">
@import '../style/variables';


main {
    height: calc(100vh - 75px);
    background-color: $page_primary-color;
    padding: 50px 0;
    .container {
        .discs-list {
            display: flex;
            flex-wrap: wrap;
        }

        .no-results {
            color: white;
            margin-left: 20px;
            margin-top: 50px;
        }
    }
}
</style>
