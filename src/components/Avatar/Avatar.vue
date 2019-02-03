<template>
    <div :style="customContainerStyle">
        <img :src="bgImage" :style="customContainerStyle" class="container" />
        <div class="icons container" :style="customContainerStyle" >
            <img v-for="(icon, index) in icons" :src="iconMap[icon]" :style="getPosition(index)" :key="index" class="icon-item inner-circle" />
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            icons: {
                type: Array,
                required: true,
            },
            avatarSize: {
                type: Number,
                required: false,
                default: 200,
            },
            bgImage: {
                type: String,
                required: true,
            },
            duration: {
                type: Number,
                required: true,
            }
        },
        computed: {
            customContainerStyle(){
                let style = 'height:' + this. avatarSize + 'px;width:' + this.avatarSize + 'px;border-radius:' + this.avatarSize / 2 + 'px;'
                style += '-webkit-animation-duration: '+ this.duration + 's;'
                style += '-moz-animation-duration: '+ this.duration + 's;'
                style += 'animation-duration: '+ this.duration + 's;'
                return style
            },
            positions() {
                let pos = []
                switch (this.icons.length) {
                    case 2:
                        pos.push({ top: -(this.avatarSize / 8), left: this.avatarSize / 2.66 })
                        pos.push({ bottom: -(this.avatarSize / 8), left: this.avatarSize / 2.66 })
                        break;
                    case 3:
                        pos.push({ top: -(this.avatarSize / 13.3), left: this.avatarSize / 8 })
                        pos.push({ bottom: this.avatarSize / 2.66, right: -(this.avatarSize / 8) })
                        pos.push({ bottom: -(this.avatarSize / 13.3), left: this.avatarSize / 8 })
                        break;
                    case 4:
                        pos.push({ top: 0, left: this.avatarSize / 40 })
                        pos.push({ top: 0, right: this.avatarSize / 40 })
                        pos.push({ bottom: 0, right: this.avatarSize / 40 })
                        pos.push({ bottom: 0, left: this.avatarSize / 40 })
                        break;
                    case 5:
                        pos.push({ top: -(this.avatarSize / 8), left: this.avatarSize / 2.66 })
                        pos.push({ top: this.avatarSize / 5, right: -(this.avatarSize / 10) })
                        pos.push({ bottom: -(this.avatarSize / 40), right: this.avatarSize / 20 })
                        pos.push({ bottom: -(this.avatarSize / 40), left: this.avatarSize / 20 })
                        pos.push({ top: this.avatarSize / 5, left: -(this.avatarSize / 10) })
                        break;
                }
                return pos
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
        },
        methods: {
            getPosition(index) {
                let pos = this.positions[index]
                let style = ''
                if(pos.hasOwnProperty("top"))
                style += 'top:' + pos.top + 'px;'
                if(pos.hasOwnProperty("left"))
                style += 'left:' + pos.left + 'px;'
                if(pos.hasOwnProperty("right"))
                style += 'right:' + pos.right + 'px;'
                if(pos.hasOwnProperty("bottom"))
                style += 'bottom:' + pos.bottom + 'px;'
                // keep face straight code
                style += '-webkit-animation-duration: '+ this.duration + 's;'
                style += '-moz-animation-duration: '+ this.duration + 's;'
                style += 'animation-duration: '+ this.duration + 's;'
                return style
            }
        }
    }
</script>

<style scoped>
.container{
    position:absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: transparent;
}
.icons { 
    display: block;
    -webkit-animation-name: rotate; 
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-timing-function: linear;
    -moz-animation-name: rotate; 
    -moz-animation-iteration-count: infinite;
    -moz-animation-timing-function: linear;
    animation-name: rotate; 
    animation-iteration-count: infinite;
    animation-timing-function: linear;
}

.inner-circle { 
    display: block;
    -webkit-animation-name: inner-circle; 
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-timing-function: linear;
    -moz-animation-name: inner-circle; 
    -moz-animation-iteration-count: infinite;
    -moz-animation-timing-function: linear;
    animation-name: inner-circle; 
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
@-webkit-keyframes inner-circle {
    from { transform:rotate(0deg); }
    to { transform:rotate(-360deg); }
}
@-moz-keyframes inner-circle {
    from { transform:rotate(0deg); }
    to { transform:rotate(-360deg); }
}
@keyframes inner-circle {
    from { transform:rotate(0deg); }
    to { transform:rotate(-360deg); }
}
.icon-item{
    position: absolute;
    width: 50px;
    height: 50px;
}
</style>