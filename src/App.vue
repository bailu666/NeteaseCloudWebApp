<template>
  <div>
      <keep-alive>
        <router-view></router-view>
      </keep-alive>
    <Player v-show="songList.length > 0 && !showDetail"></Player>
     <Toast ref="alert"></Toast>
  </div>
</template>
<script>
  import Player from './components/playerBar'
  import { mapGetters } from 'vuex'
  export default {
    data () {
      return {
        toast: false
      }
    },
    components: {
      Player
    },
    computed: {
      ...mapGetters([
        'songList',
        'showDetail'
      ])
    }
  }
</script>
