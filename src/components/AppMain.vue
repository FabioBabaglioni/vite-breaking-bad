<script>
import AppCard from './AppCard.vue';
import { store } from '../store';

export default {
    components: {
        AppCard,
    },
    data() {
        return {
            store,
        }
    }

}

</script>

<template>
    <main class="container_app pt-5">
        <section class="">
            <button id="white_btn" class="mb-3">
                Select category
            </button>
        </section>
        <section id="Container_white" class="py-3">
            <h2>Found {{ store.characterList.length }} charcaters</h2>

            <div id="container_card" class="d-flex flex-wrap justify-content-between">
                <AppCard v-for="character in store.characterList" :key="character.id" :info="character" />
            </div>
        </section>

    </main>


</template>

<style scoped lang="scss">
@use "./style/partials/variables.scss" as *;

#white_btn {
    background-color: $brandSecondary;
    color: $brandNormalText;
    padding: 5px;
    border-radius: 10px;
}

#Container_white {
    background-color: $brandSecondary;

    min-height: 300px;

    h2 {
        background-color: #212529;
        width: 90%;
        margin: 0 auto;
        color: $brandSecondary;
        font-size: 15px;
        padding: 10px;
    }

    #container_card {
        width: 85%;
        margin: 0 auto;
    }
}
</style>