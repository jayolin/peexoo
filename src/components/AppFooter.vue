<template>
    <div>
        <div class="top-footer">
            <div v-for="(link, i) in links" :key="i">
                <div style="margin: 10px 0">
                    <b>{{link.title}}</b>
                </div>
                <div  v-for="(subLink, j) in link.subLinks" :key="i + j">
                    <small>{{subLink.text}}</small>
                </div>
            </div>
        </div>
        <div class="bottom-footer">
            <small>&copy; Copyright, Peexoo</small>
        </div>
    </div>
</template>

<script>
    export default {
        name: "AppFooter",
        data(){
            return {
                links: [
                    {
                        title: 'Quick Links',
                        subLinks: [
                            {text: 'Find a photographer'},
                            {text: 'Find my photos'},
                            {text: 'Peexoomemories'},
                            {text: 'Become a photographer'}
                        ]
                    },

                    {
                        title: 'Company',
                        subLinks: [
                            {text: 'About Us'},
                            {text: 'FAQs'},
                            {text: 'Pricing'},
                            {text: 'Careers'},
                            {text: 'Help and Support'},
                            {text: 'Terms of Service'},
                            {text: 'Privacy Policy'},
                        ]
                    },

                    {
                        title: 'Connect with Us',
                        subLinks: [
                            {text: '5A, Awudu Egheda, Lekki, Lagos'},
                            {text: '+234 8003229932'},
                            {text: 'customer.service@peexo.ai'}
                        ]
                    }
                ]
            }
        }
    }
</script>

<style scoped>
    .top-footer{
        background: #FFFFFF;
        display: flex;
        justify-content: space-around;
        padding: 20px 0
    }

    .bottom-footer{
        background: #2c3e50;
        color: #FFFFFF;
        text-align: center;
        padding: 20px
    }
</style>