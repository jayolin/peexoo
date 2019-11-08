<template>
    <div>
        <section class="image-section"></section>
        <div class="secondary-nav primary">

            <div style="position: relative; height: 0; width: 0;">
                <div class="profile-image">

                </div>
            </div>

            <ul class="ul">
                <li
                        class="sub-link"
                        :style="{background: subLink.isActive ? 'dimgrey' : 'transparent'}"
                        v-for="(subLink, i) in subLinks"
                        :key="`sub-link-${i}`"
                >
                    {{subLink.text}}
                </li>
            </ul>
        </div>

        <div style="background: rgba(255, 165, 0, 0.1); padding: 0 0 100px 0">
            <div class="justify-content-space-between" style="padding: 20px 75px">
                <h1>Afroshots</h1>
                <div>
                    <button class="primary-outline">Message Photographer</button>
                    <button class="primary">Book Now</button>
                </div>
            </div>
            <calendar style="margin: 40px 0"></calendar>
        </div>

    </div>
</template>

<script>
    import Calendar from "./Calendar";
    export default {
        name: "AppSection",
        components: {Calendar},
        data(){
            return {
                subLinks: [
                    {
                        text: 'Details',
                        to: ''
                    },
                    {
                        text: 'Portfolio',
                        to: ''
                    },
                    {
                        text: 'Availability',
                        isActive: true,
                        to: ''
                    },
                    {
                        text: 'Pricing Packages',
                        to: ''
                    },
                    {
                        text: 'Reviews',
                        to: ''
                    }
                ]
            }
        }
    }
</script>

<style scoped>
    .primary{
        background: orange;
        color: #FFFFFF;
    }

    .primary-outline{
        background: transparent;
        border: 1px solid orange;
    }

    .justify-content-space-between{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }
    .secondary-nav{
        padding: 0 75px;
        text-align: right;
    }
    .ul{
        margin: 0 !important;
    }
    .ul li{
        display: inline;
    }
    .image-section{
        width: 100%;
        height: 70vh;
        background: dimgrey;
    }
    .profile-image{
        background: darkgrey;
        height: 120px;
        width: 120px;
        position: absolute;
        bottom: -70px;
    }
    .sub-link{
        padding: 14px 25px;
        line-height: 50px;
        min-height: 100%;
        margin: 0;
    }
    button{
        padding: 10px 50px;
        border-radius: 20px;
        border: none;
        margin: 0 5px;
    }
    button:focus {outline:0;}
</style>