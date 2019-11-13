<template>
  <div id="app">
    <label>
      Arbol de Relacion
      <input type="checkbox" v-model="landscape" value="1">
    </label>
    <TreeChart :json="data" :class="{landscape: landscape.length}" @click-node="clickNode" />

    <div>
      <input type="text" name="name" v-model="form.name">
      <input type="checkbox" name="padre" v-model="form.padre">
      <button @click="uno()"> OUTLOKK </button>
      <button @click="dos()"> sunny</button>
      <button @click="tres()"> Overcast</button>
      <button @click="cuatro()"> Rain</button>

      <button @click="cinco()"> HUMIDITY</button>
      <button @click="seis()"> WIND</button>
      <button @click="siete()"> high</button>
      <button @click="ocho()"> normal</button>
      <button @click="nueve()"> strong</button>
      <button @click="diez()"> weak</button>

    </div>



    <!-- <footer class="foot">
        <p>© 2018 - 3018 Author
            <a href="https://refined-x.com/" target="_blank">雅X共赏</a> 
            Github 
            <a href="https://github.com/tower1229/Vue-Tree-Chart" target="_blank">Vue-Tree-Chart</a>
        </p>
    </footer> -->
    <!-- <div>
      hr
      <pre>
        {{$data}}
      </pre>
    </div> -->


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
      form:{
        name:"",
        padre: false,
        children:[]
      },
      data: {
        image_url: "https://cdn.pixabay.com/photo/2015/03/26/09/47/sky-690293_960_720.jpg",
        name: 'OUTLOKK',
        padre: true,
        children:[
          {
            image_url: "https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885_960_720.jpg",
            name: 'sunny',
            padre: false,
            children:[
              {
                image_url: "https://cdn.pixabay.com/photo/2016/11/25/23/15/moon-1859616_960_720.jpg",
                name: 'HUMIDITY',
                padre:true,
                children:[
                {
                  image_url: "https://cdn.pixabay.com/photo/2015/07/09/22/45/tree-838667_960_720.jpg",
                  name: 'high',
                  padre:false,
                  children:[
                    {
                      image_url: "https://cdn.pixabay.com/photo/2014/11/21/03/27/coast-540123_960_720.jpg",
                      name: 'NO',
                      padre:true,
                      children:[]
                    }
                  ]
                },
                {
                  image_url: "https://cdn.pixabay.com/photo/2015/07/09/22/45/tree-838667_960_720.jpg",
                  name: 'normal',
                  padre:false,
                  children:[
                    {
                      image_url: "https://cdn.pixabay.com/photo/2014/11/21/03/27/coast-540123_960_720.jpg",
                      name: 'YES',
                      padre:true,
                      children:[]
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
            padre:false,
            children:[
              {
                image_url: "https://cdn.pixabay.com/photo/2014/11/21/03/27/coast-540123_960_720.jpg",
                name: 'YES',
                padre:true,
                children:[]
              }
            ]
          },
          {
            image_url: "https://cdn.pixabay.com/photo/2015/04/23/22/00/tree-736885_960_720.jpg",
            name: 'Rain',
            padre:false,
            children:[
              {
                image_url: "https://cdn.pixabay.com/photo/2016/11/25/23/15/moon-1859616_960_720.jpg",
                name: 'WIND',
                padre:true,
                children:[
                {
                  image_url: "https://cdn.pixabay.com/photo/2015/07/09/22/45/tree-838667_960_720.jpg",
                  name: 'strong',
                  padre:false,
                  children:[
                    {
                      image_url: "https://cdn.pixabay.com/photo/2014/11/21/03/27/coast-540123_960_720.jpg",
                      name: 'NO',
                      padre:true,
                      children:[]
                    }
                  ]
                },
                {
                  image_url: "https://cdn.pixabay.com/photo/2015/07/09/22/45/tree-838667_960_720.jpg",
                  name: 'weak',
                  padre:false,
                  children:[
                    {
                      image_url: "https://cdn.pixabay.com/photo/2014/11/21/03/27/coast-540123_960_720.jpg",
                      name: 'YES',
                      padre:true,
                      children:[]
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
    },
    uno(){
      this.data.children.push(this.form)
    },
    dos(){
      this.data.children[0].children.push(this.form)
    },
    tres(){
      this.data.children[1].children.push(this.form)
    },
    cuatro(){
      this.data.children[2].children.push(this.form)
    },
    cinco(){
      this.data.children[0].children[0].children.push(this.form)
    },
    seis(){
      this.data.children[2].children[0].children.push(this.form)
    },
    siete(){

    },
    ocho(){

    },
    nueve(){

    },
    diez(){

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
