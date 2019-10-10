<template>
  <div>
    <ul class="autumn-record_list" :class="{'autumn_marquee':marqueeshow}" ref="roll" @mouseover="stopMove" @mouseleave="getMove">
        <li v-for="(item) in items" :key="item.id">{{item.content}}</li>
        <!-- <li>账号169*****0190的用户获得了<span>绝地求套装道具2</span></li>
        <li>账号169*****0090的用户获得了<span>绝地求生粉兔套装道具3</span></li>
        <li>账号169*****0190的用户获得了<span>绝地求套装道具4</span></li>
        <li>账号169*****0090的用户获得了<span>绝地求生粉兔套装道具5</span></li>
        <li>账号169*****0190的用户获得了<span>绝地求套装道具6</span></li>
        <li>账号169*****0090的用户获得了<span>绝地求生粉兔套装道具7</span></li>
        <li>账号169*****0190的用户获得了<span>绝地求套装道具8</span></li>
        <li>账号169*****0090的用户获得了<span>绝地求生粉兔套装道具9</span></li>
        <li>账号169*****0190的用户获得了<span>绝地求套装道具10</span></li>
        <li>账号169*****0090的用户获得了<span>绝地求生粉兔套装道具11</span></li>
        <li>账号169*****0190的用户获得了<span>绝地求套装道具2</span></li>
        <li>账号169*****0090的用户获得了<span>绝地求生粉兔套装道具3</span></li>
        <li>账号169*****0190的用户获得了<span>绝地求套装道具4</span></li>
        <li>账号169*****0090的用户获得了<span>绝地求生粉兔套装道具5</span></li>
        <li>账号169*****0190的用户获得了<span>绝地求套装道具6</span></li>
        <li>账号169*****0090的用户获得了<span>绝地求生粉兔套装道具7</span></li>
        <li>账号169*****0190的用户获得了<span>绝地求套装道具8</span></li>
        <li>账号169*****0090的用户获得了<span>绝地求生粉兔套装道具9</span></li>
        <li>账号169*****0190的用户获得了<span>绝地求套装道具10</span></li> -->
    </ul>
  </div>
</template>

<script>
export default {
  name: '',
  data() {
    return {
        marqueeshow: false,//中奖纪录是否滚动
        moveTimer:null,
        items:null,
    };
  },
  props:{
      scrollList:{
          type:Array,
          default:function(){
              return []
          }
      }
  },
  methods: {
      roll() {
        this.marqueeshow = false;
        let _this = this;
        clearTimeout(this.moveTimer);
        this.moveTimer = setTimeout(function () {
            _this.items.push(_this.items[0]);
            _this.items.shift();
            _this.marqueeshow = true;
            _this.roll();
        }, 1500)
    },
    stopMove() {
        clearTimeout(this.moveTimer);
        // this.marqueeshow=false;
    },
    getMove() {
        // this.marqueeshow=true;
        this.roll();
    }
  },
  mounted(){
      this.items=this.scrollList;
      this.roll();
  }
};
</script>

<style scoped>
.autumn-record_list{
    position: absolute;
    top: 0; 
    list-style-type: none;
    transition: all 0.1s linear;
}
li{
    line-height: 14px;
    margin-bottom: 19px;
    font-size: 14px;
    color: #787cb2;
    width: 360px;
    text-overflow: ellipsis;
    white-space: nowrap;
    text-align: left;
    transition: all 0.1s linear;
        
}
.autumn_marquee{
    transition: all 1s linear;
}

</style>
