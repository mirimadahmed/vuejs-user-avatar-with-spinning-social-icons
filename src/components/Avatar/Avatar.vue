<template>
    <div>
        <img src="https://ubisafe.org/images/circle-vector-avatar-3.png" />
        <div class="icons">
            <img v-for="(icon, index) in icons" :src="iconMap[icon]" :key="index" class="icon-item" />
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            icons: {
                type: Array,
                required: true,
            }
        },
        data() {
            return {
                iconMap: {
                    instagram: require('./assets/instagram.png'),
                    medium: require('./assets/medium.png'),
                    pinterest: require('./assets/pinterest.png'),
                    spotify: require('./assets/spotify.png'),
                    twitch: require('./assets/twitch.png'),
                    twitter: require('./assets/twitter.png'),
                    youtube: require('./assets/youtube.png'),
                }
            }
        }
    }
</script>

<style scoped>
.icons { 
    display: block;
    -webkit-animation-name: rotate; 
    -webkit-animation-duration: 1s; 
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-timing-function: linear;
    -moz-animation-name: rotate; 
    -moz-animation-duration: 1s; 
    -moz-animation-iteration-count: infinite;
    -moz-animation-timing-function: linear;
    animation-name: rotate; 
    animation-duration: 1s; 
    animation-iteration-count: infinite;
    animation-timing-function: linear;
}

@-webkit-keyframes rotate {
    from {-webkit-transform: rotate(0deg);}
    to {-webkit-transform: rotate(360deg);}
}

@-moz-keyframes rotate {
    from {-moz-transform: rotate(0deg);}
    to {-moz-transform: rotate(360deg);}
}

@keyframes rotate {
    from {transform: rotate(0deg);}
    to {transform: rotate(360deg);}
}
.icon-item{
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: transparent;
    width: 50px;
    height: 50px;
}
</style>