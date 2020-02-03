<template>
        <span v-bind:title="this.hashTag"
              v-text="this.emoji"
        ></span>
</template>

<script>
    import RankEmoji from "./RankEmoji";
    export default {
        extends: RankEmoji,
        name: "RankPies",
        props: {
            emojis: {
                type: Object,
                default: function () {
                    return {
                        top: [
                            '🎂',
                            '🥧',
                            '🥮',
                        ],
                        between: '🍰'
                    }
                }
            }
        }
    }
</script>

<style scoped>

</style>