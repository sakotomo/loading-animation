<template>
  <div class="loadingImg">
    <transition-group name="list-complete">
      <span
        v-for="item in items"
        v-bind:key="item.id"
        class="list-complete-item">
        {{ item.val }}
      </span>
    </transition-group>
  </div>
</template>

<script>
export default {
  name: 'Loading',
  props: {
    loading: Boolean
  },
  data () {
    return {
      base: [{id:1,val:"L"},{id:2,val:"o"},{id:3,val:"a"},{id:4,val:"d"},{id:5,val:"i"},{id:6,val:"n"},{id:7,val:"g"},{id:8,val:"."},{id:9,val:"."},{id:10,val:"."}],
      items: [],
      timer_add: null,
      timer_remove: null
    }
  },
  methods: {
    randomIndex: function () {
      return Math.floor(Math.random() * this.items.length)
    },
    add: function () {
      this.items.splice(this.items.length, 0, this.base[this.items.length])
      this.timer_add = setTimeout(this.add, 700)
      if(this.items.length == this.base.length){
        clearTimeout(this.timer_add);
        if(this.loading) this.remove()
      }
    },
    remove: function () {
      this.items.splice(this.randomIndex(), 1)
      this.timer_remove = setTimeout(this.remove, 500)
      if(this.items.length == 0){
        clearTimeout(this.timer_remove);
        if(this.loading) this.add()
      }
    }
  },
  mounted(){
    this.add()
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .loadingImg{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
    -webkit- transform: translateY(-50%) translateX(-50%);
    width: 175px;
    color: #777;
  }
  .list-complete-item {
    transition: all 1s;
    display: inline-block;
    margin-right: 10px;
  }
  .list-complete-enter{
    opacity: 0;
    transform: translateX(30px);
  }
  .list-complete-leave-to
  /* .list-complete-leave-active below version 2.1.8 */ {
    opacity: 0;
    transform: translateY(30px);
  }
  .list-complete-leave-active {
    position: absolute;
  }
</style>
