<template>
  <el-button type="primary" icon="el-icon-search" v-on:click="search">搜索</el-button>
</template>
<script>
    export default {
    name: 'carrousel',
    data() {
      return {
        list:[]
      }
    },
    mounted() {
    },
    methods:{
       get:function(){
        this.$api.post('/player', this.smallSwiper, response => {
            if (response.status >= 200 && response.status < 300) {
                this.imgThumbs = response.data.data.list
                console.log(response.data.data.list);//请求成功，response为成功信息参数
            } else {
                //console.log(response.message);//求失败，response为失败信息
            }
        });
      },
      playerDetail(id){
        this.smallSwiperDetail.id = id;
        this.$api.post('/player', this.smallSwiperDetail, response => {
            if (response.status >= 200 && response.status < 300) {
                this.imgThumbs = response.data.data.list
                console.log(response.data.data.list);//请求成功，response为成功信息参数
            } else {
                //console.log(response.message);//求失败，response为失败信息
            }
        });
      }
    },
      search(){
         this.$api.get('/v1/bpi/currentprice.json', {}, response => {
            console.log(list)
              if (response.status >= 200 && response.status < 300) {
                  console.log(response.data);//请求成功，response为成功信息参数
              } else {
                  console.log(response.message);//求失败，response为失败信息
              }
          });
      },
       submitForm(formName) {
         this.$api.post('/player', this.ruleForm, response => {
            console.log(list)
              if (response.status >= 200 && response.status < 300) {
                  console.log(response.data);//请求成功，response为成功信息参数
              } else {
                  console.log(response.message);//求失败，response为失败信息
              }
          });
      }

    }
  }
       
</script>

<style>
</style>