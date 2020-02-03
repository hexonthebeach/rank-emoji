<template>
    <span v-bind:title="this.hashTag"
          v-text="this.emoji"
    ></span>
</template>

<script>
export default {
    name: 'RankEmoji',
    props: {
        rank: {
            type: Number,
            default: 0
        },
        isLast: {
            type: Boolean,
            default: false
        },
        withBetween: {
            type: Boolean,
            default: true
        },
        emojis: {
            type: Object,
            default: function(){
                return {
                    top: [
                        '🥇',
                        '🥈',
                        '🥉',
                    ],
                    between: '🏅',
                    last: '💩'
                }
            }
        }
    },
    computed: {
        hashTag: function () {
            return "#" + (1 + parseInt(this.rank))
        },
        emoji: function () {
            if(this.isLast){
                return this.emojis.last
            }
            if(this.emojis.top[this.rank]){
                return this.emojis.top[this.rank]
            }
            return this.withBetween ? this.emojis.between : ''
        }
    }
}
</script>