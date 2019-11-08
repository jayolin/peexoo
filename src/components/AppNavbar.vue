<template>
    <div>
        <nav class="main-nav justify-content-space-between">
            <div>
                Peexoo
            </div>

            <ul class="ul">
                <li style="padding: 0 10px;" v-for="(mainLink, i) in mainLinks" :key="`main-link-${i}`">
                    {{mainLink.text}}
                </li>
            </ul>

        </nav>
    </div>
</template>

<script>
    export default {
        name: "AppNavbar",
        data(){
            return {
                mainLinks: [
                    {
                        text: 'I am a Photographer',
                        to: ''
                    },
                    {
                        text: 'Explore Photos',
                        to: ''
                    },
                    {
                        text: 'Find a photographer',
                        to: ''
                    },
                    {
                        text: 'Find my photos',
                        to: ''
                    },
                    {
                        text: 'Login or Register',
                        to: ''
                    }
                ]
            }
        }
    }
</script>

<style scoped>

    .main-nav{
        padding: 20px 14px
    }

    .justify-content-space-between{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }

    .ul{
        margin: 0 !important;
    }
    .ul li{
        display: inline;
    }

</style>