<template>
<div id="app">
  <Header />
  <AddWiet v-on:add-wiet="addWiet" />
  <Wiets v-bind:wiets="wiets" v-on:del-wiet="deleteWiet" />
</div>
</template>

<script>
import Header from '../components/layout/Header'
import Wiets from '../components/Wiets'
import AddWiet from '../components/AddWiet'
// import axios from 'axios'

export default {
  name: 'app',
  components: {
    Header,
    AddWiet,
    Wiets
  },
  data () {
    return {
      wiets: [
        {
          id: 1,
          title: 'Blue Berry Haze',
          description: 'Better then the real blue berries',
          image: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fdutchseedsshop.com%2Fwp-content%2Fuploads%2F2016%2F07%2Fblueberry-haze-seeds.jpg&f=1&nofb=1',
          price: '14',
          available: '20',
          completed: false
        },
        {
          id: 2,
          title: 'Amnesia Haze',
          description: 'With earthy flavors of lemons and citrus, Amnesia Haze is a perfect strain to start your day with a smile. The uplifting, energetic buzz is one you won’t soon forget.',
          image: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.royalqueenseeds.com%2F115-1427-thickbox%2Famnesia-haze.jpg&f=1&nofb=1',
          price: '11.50',
          available: '12',
          completed: false
        },
        {
          id: 3,
          title: 'Pineapple Express',
          description: 'Pineapple Express combines the potent and flavorful forces of parent strains Trainwreck and Hawaiian. The smell is likened to fresh apple and mango, with a taste of pineapple, pine, and cedar.',
          image: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fbuymyweedonline.ca%2Fwp-content%2Fuploads%2F2017%2F01%2F20170209_110103.jpg&f=1&nofb=1',
          price: '7.50',
          available: '420',
          completed: false
        },
        {
          id: 4,
          title: 'Pineapple Express',
          description: 'Gorilla Glue, also known as “Gorilla Glue #1” or "420 Glue" is an indica dominant hybrid (60% indica/40% sativa) strain created through crossing the classic Chocolate Diesel X Sour Diesel strains. This bud packs a crazy powerful high that leaves you feeling like your mind is filled with glue, all fueled by an insanely potent 25-28% average THC level. The high starts with a cerebral rush that leaves you feeling happy yet totally hazy, with no hope of focusing on anything any time soon. As your head high build and builds, your body will be washed over with a deep body buzz, leaving you feeling completely stoned and immovable. These effects last for hours on end and often end in a deep sleep for the lesser experienced.',
          image: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.wweek.com%2Fresizer%2FuQVg9TGt8rnxYpAq_qwUFKnt4TM%3D%2F1200x0%2Ffilters%3Aquality(100)%2Fs3.amazonaws.com%2Farc-wordpress-client-uploads%2Fwweek%2Fwp-content%2Fuploads%2F2017%2F07%2F26104526%2FFullSizeRender7.jpg&f=1&nofb=1',
          price: '18',
          available: '69',
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteWiet (id) {
      //  this.todo = this.todos.filter(todo => todo.id !== id)
      this.wiets = this.wiets.filter(wiet => wiet.id !== id)
      // .then(res => { this.todos = this.todos.filter(todo => todo.id !== id) })
      // .catch(err => console.log(err))
    },
    addWiet (newWiet) {
      this.wiets = [...this.wiets, newWiet]
      // .then(res => { this.todos = [...this.todos, res.data] })
      // .catch(err => console.log(err))
    }
  }
}

</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}

img{
  width: 100px;
}
</style>
