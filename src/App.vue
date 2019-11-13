<template>
  <div id="app">
    <label>
      Arbol de Relacion
      <input type="checkbox" v-model="landscape" value="1">
    </label>

    <TreeChart :json="data" :class="{landscape: landscape.length}" @click-node="clickNode" />

    <!-- <footer class="foot">
        <p>© 2018 - 3018 Author
            <a href="https://refined-x.com/" target="_blank">雅X共赏</a> 
            Github 
            <a href="https://github.com/tower1229/Vue-Tree-Chart" target="_blank">Vue-Tree-Chart</a>
        </p>
    </footer> -->
  </div>
</template>

<script>
import TreeChart from "@/components/TreeChart";

export default {
  name: 'app',
  components: {
    TreeChart
  },
  data() {
    return {
      landscape: [],
      data: {
        image_url: "https://cdn.pixabay.com/photo/2015/03/26/09/47/sky-690293_960_720.jpg",
        name: 'OUTLOKK',
        children:[
          {
            image_url: "https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885_960_720.jpg",
            name: 'sunny',
            children:[
              {
                image_url: "https://cdn.pixabay.com/photo/2016/11/25/23/15/moon-1859616_960_720.jpg",
                name: 'HUMIDITY',
                children:[
                {
                  image_url: "https://cdn.pixabay.com/photo/2015/07/09/22/45/tree-838667_960_720.jpg",
                  name: 'high',
                  children:[
                    {
                      image_url: "https://cdn.pixabay.com/photo/2014/11/21/03/27/coast-540123_960_720.jpg",
                      name: 'NO',
                    }
                  ]
                },
                {
                  image_url: "https://cdn.pixabay.com/photo/2015/07/09/22/45/tree-838667_960_720.jpg",
                  name: 'normal',
                  children:[
                    {
                      image_url: "https://cdn.pixabay.com/photo/2014/11/21/03/27/coast-540123_960_720.jpg",
                      name: 'YES',
                    }
                  ]
                }
                ]
              }
            ]
          },
          {
            image_url: "https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885_960_720.jpg",
            name: 'Overcast',
            children:[
              {
                image_url: "https://cdn.pixabay.com/photo/2014/11/21/03/27/coast-540123_960_720.jpg",
                name: 'YES',
              }
            ]
          },
          {
            image_url: "https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885_960_720.jpg",
            name: 'Rain',
            children:[
              {
                image_url: "https://cdn.pixabay.com/photo/2016/11/25/23/15/moon-1859616_960_720.jpg",
                name: 'WIND',
                children:[
                {
                  image_url: "https://cdn.pixabay.com/photo/2015/07/09/22/45/tree-838667_960_720.jpg",
                  name: 'strong',
                  children:[
                    {
                      image_url: "https://cdn.pixabay.com/photo/2014/11/21/03/27/coast-540123_960_720.jpg",
                      name: 'NO',
                    }
                  ]
                },
                {
                  image_url: "https://cdn.pixabay.com/photo/2015/07/09/22/45/tree-838667_960_720.jpg",
                  name: 'weak',
                  children:[
                    {
                      image_url: "https://cdn.pixabay.com/photo/2014/11/21/03/27/coast-540123_960_720.jpg",
                      name: 'YES',
                    }
                  ]
                }
                ]
              }
            ]
          }

        ]
        
      }
    }
  },
  methods: {
    clickNode: function(node){
      // eslint-disable-next-line
      console.log(node)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#app .avat{border-radius: 2em;border-width:2px;}
#app .name{font-weight:700;}
.foot {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    background: #333;
    padding: 24px;
    overflow: hidden;
    color: #999;
    font-size: 14px;
    text-align: center;
}
.foot a{color:#fff;margin:0 .5em}
</style>
