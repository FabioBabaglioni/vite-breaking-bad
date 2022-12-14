<script>

export default {


}

</script>

<template>

    <div class="card mt-2 mb-3">
        <div class="d-flex flex-column align-items-center">
            <img class="pt-3" src="https://rickandmortyapi.com/api/character/avatar/1.jpeg" alt="">
            <h4 class="pt-2">NAME</h4>
            <h6>Series</h6>
            <span>Vivo</span>
        </div>
    </div>

</template>

<style scoped lang="scss">
@use "./style/partials/variables.scss" as *;

.card {
    background-color: $brandPrimary;
    width: calc((100% / 5) - 20px);
    height: 300px;

    img {
        width: 80%;

    }

    h4 {
        color: $brandSecondary;
        font-size: 18px;
    }

    h6 {
        color: $brandSecondary;
        font-size: 15px;
    }

    span {
        color: $brandSecondary;
        font-size: 12px;
    }
}
</style>