<template>
    <nav class="navbar navbar-dark bg-dark">
        <div class="container">
            <span class="navbar-brand">Simulador de Tweets</span>
            <button class="btn btn-info ps-4 pe-4" @click="openCloseForm" :class="{ 'btn-info': !showForm, 'btn-danger': showForm }">
                {{ !showForm ? "Nuevo Tweet" : "Cerrar Tweet"}}
            </button>
        </div>
    </nav>
</template>

<script>
export default {
    props: {
        showForm: Boolean,
        openCloseForm: Function,
    }
}
</script>

<style>

</style>