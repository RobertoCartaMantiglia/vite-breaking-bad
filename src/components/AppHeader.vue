<script>
export default {
    name: 'AppHeader'
}
</script>

<template>
    <header>
        <div class="row">
            <div class="col-6 d-flex p-3">
                <img src="https://upload.wikimedia.org/wikipedia/commons/1/11/Yu-Gi-Oh%21_%28Logo%29.jpg" alt="logo">
                <h1 class="fs-4">Yu-Gi-Oh Api</h1>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
header {
    height: 80px;

    img {
        width: 60px;
    }
}
</style>