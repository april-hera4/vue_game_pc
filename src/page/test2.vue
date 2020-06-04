<template>
<div>
	 <table>
  <tr v-for="site in sites"  @click="link(site.num)" >
 <td>{{ site.name }}</td><td>{{ site.num }}</td>
  </tr>
 </table>
 <ul>
	 <li v-for="list in lists"></li>

 </ul>
</div>
 
</template>
<script>
export default {
    name: 'carrousel',
    data() {
      return {
        sites: [ { 
			name: '1' ,num: '中国',
			lists:[
				{
					name: '2' ,num: '俄罗斯',
				}
			]

			
			},
   { name: '2' ,num: '日本',},
   { name: '3' ,num: '缅甸',}
  ]
      }
    },
    mounted() {
    },
    methods:{
     link(lists){
 alert(lists);
  }

    }
  }
</script>
<style>
body{background: none;}
</style>
