<template>
  <div class="recommend">
    <div class="recommend-content">
      <div class="slider-wrapper">
        <slider>
          <div v-for="item in recommends">
            <a :href="item.linkUrl">
              <img :src="item.picUrl" alt="">
            </a>
          </div>
        </slider>
      </div>
      <div class="recommend-list">
        <h1 class="list-title">热门歌曲推荐</h1>
        <ul></ul>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import Slider from 'base/slider/slider'
  import {getRecommend} from 'api/recommend'
  import {ERR_OK} from 'api/config'

  export default {
    created() {
      this._getRecommend()
    },
    data() {
      return {
        recommends: []
      }
    },
    methods: {
      _getRecommend() {
        getRecommend().then((res) => {
          if (ERR_OK === res.code) {
            this.recommends = res.data.slider
          }
        })
      }
    },
    components: {
      Slider
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">

</style>
