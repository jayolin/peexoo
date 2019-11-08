<template>
    <div>
        <app-navbar></app-navbar>
        <app-section></app-section>
        <app-footer></app-footer>
    </div>
</template>

<script>
    import AppNavbar from "./AppNavbar"
    import AppSection from "./AppSection";
    import AppFooter from "./AppFooter";
    export default {
        name: "Index",
        components: {
            AppFooter,
            AppSection,
            AppNavbar
        }
    }
</script>

<style scoped>

</style>