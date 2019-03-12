<template>
  <mu-container>
    <mu-tabs :value.sync="active3" center color="teal"  @change="slideTo">
      <mu-tab>
        <mu-icon value="phone"></mu-icon>
        RECENTS
      </mu-tab>
      <mu-tab>
        <mu-icon value="favorite"></mu-icon>
        FAVORITES
      </mu-tab>
      <mu-tab>
        <mu-icon value="person_pin"></mu-icon>
        NEARBY
      </mu-tab>
    </mu-tabs>
    <swiper ref="mySwiper" v-on:slideChangeTransitionStart="tabTo">
      <swiper-slide class="demo-text">
        <p>“……是的，我承认从很早以前我都害怕死亡，在医院里被人研究的时候，以前做出布局的时候，其实我很怕死的，因为除了死以外，我没有值得珍惜的东西，很奇怪是吧？恰好是这样我真的很怕死，因为我想要有值得珍惜的东西之后，死亡之后才会不寂寞，我才能够安然的面对死亡……”</p>
      </swiper-slide>
      <swiper-slide class="demo-text">
        <p>“我的心从来没有这么坚定过，所以我会为了补偿而死，也可以为了补偿而死……一辈子，急辈子都无所谓，我绝不后退！”</p>
        <p>“如果我后退呢？如果我想要死呢？我不想你再次背对着我逃跑了……”</p>
        <p>“那么就去地狱找到你，我绝对不逃！”</p>
        <p>“白痴，你也哭了？因为那些软弱拖累你的脚步？”</p>
      </swiper-slide>
      <swiper-slide class="demo-text">
        <p>“不，这泪水……是因为勇气，因为力量，因为信任，……你不会懂的！”</p>
        <p>“我不会帮你，想要什么样的未来……自己去追寻吧！”</p>
        <p>“我不需要你的帮忙！未来我会一手开启，什么样的敌人我也不会惧怕……还有，其实我们可以成为朋友的……”</p>
        <p>“也许吧，未来……给你了。”</p>
      </swiper-slide>
    </swiper>
  </mu-container>
</template>

<script>
export default {
  data () {
    return {
      active3: 0
    }
  },
  methods: {
    slideTo () {
      this.$refs.mySwiper.swiper.slideTo(this.$data.active3)
    },
    tabTo () {
      this.$data.active3 = this.$refs.mySwiper.swiper.activeIndex
    }
  },
  computed: {
    swiper() {
      console.log(this.$refs.mySwiper.swiper)
    }
  }
}
</script>

<style lang="stylus" scoped>
.demo-text
  padding 16px
  background #fff
  p
    margin 8px 0
</style>
