# rank-emoji
Vue component for easily adding ranking emoji to a list.

It will add the medal-emoji by default to the first three items in the list

* 🥇
* 🥈
* 🥉

The rest will get a normal unmarked medal by default 🏅

### Properties You can work with
Disable the unmarked medals from showing after the top 3

`v-bind:with-between="false"`
 
Show the special emoji character for last-place

`v-bind:is-last="true"`

`v-bind:is-last="index == winners.length-1"` (practical example) 

Set different Emoji

`v-bind:emojis="{top:['💝','💘','💖'],between:'❤',last:'💔'}"`

To set your own Emoji you can Extend the RankEmoji component, see /src/RankPies.vue for example

## installation
use npm to get this into your app, from the root :

`npm i rank-emoji`

## code example
Add this component in the loop, it will take care of the rest automatically.

```
<template>
  <div>
    <div v-for="(winner, index) in winners"
         v-bind:key="index"
    >

      <rank-emoji v-bind:rank="index"></rank-emoji>

      <span v-text="winner.name"></span>
    </div>
  </div>
</template>

<script>
    import RankEmoji from 'rank-emoji';
    
    export default {
        ...
        components:{
            ... ,
            RankEmoji
        },
        data:function () {
            return {
                winners: [
                    {name:'Neil Armstrong'},
                    {name:'Buzz Aldrin'},
                    {name:'Pete Conrad'},
                    {name:'Alan Bean'},
                    {name:'Alan Shepard'},
                    {name:'Edgar Mitchell'},
                ]
            }
        }
    }
</script>
```

