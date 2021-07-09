<template>
  <v-row>
    <v-col class="text-center">
      
      <v-card>
        {{this.$router.currentRoute.query['name']}}
      </v-card>

    <v-card>
      <v-img
        :src=movieUrl
      >
       
      </v-img>
    </v-card>
    </v-col>
    <v-col>
      <v-btn
      href="/"
      >
        Exit
      </v-btn>
    </v-col>
  </v-row>
</template>


<script>

export default {
   data() {
    return { 

  
        movieUrl:'',
        movies:[
          {
            name: 'Harry Potter And the Philosopher Stone',
            description:'Crazy genius grandpa takes his grandson into adventures because he feels lonely and dont admit that. The grandson is stupid and fuck things up',
            backgroundUrl: require('~/assets/movie/rickyandmorty.png')
          },
          {
            name: 'GoodGirls',
            description:'old ladies in need of money heist a market and steal from a gang. The girls need to work for the gang in order to repay their debt',
            backgroundUrl: require('~/assets/movie/goodgirls.png')
          },
          {
            name: 'Resident Evil',
            description:'Biohazard company releases a virus that make people zombies. Not satisfied they release a BioWeapon Nemesis that they cant control',
            backgroundUrl: require('~/assets/movie/res.png')
          },
          {
            name: 'Harry Potter And the Philosopher Stone',
            description:'Crazy genius grandpa takes his grandson into adventures because he feels lonely and dont admit that. The grandson is stupid and fuck things up',
            backgroundUrl: require('~/assets/movie/rickyandmorty.png')
          },
          {
            name: 'GoodGirls',
            description:'old ladies in need of money heist a market and steal from a gang. The girls need to work for the gang in order to repay their debt',
            backgroundUrl: require('~/assets/movie/goodgirls.png')
          },
          {
            name: 'Resident Evil',
            description:'Biohazard company releases a virus that make people zombies. Not satisfied they release a BioWeapon Nemesis that they cant control',
            backgroundUrl: require('~/assets/movie/res.png')
          },
          {
            name: 'Harry Potter And the Philosopher Stone',
            description:'Crazy genius grandpa takes his grandson into adventures because he feels lonely and dont admit that. The grandson is stupid and fuck things up',
            backgroundUrl: require('~/assets/movie/rickyandmorty.png')
          },
          {
            name: 'GoodGirls',
            description:'old ladies in need of money heist a market and steal from a gang. The girls need to work for the gang in order to repay their debt',
            backgroundUrl: require('~/assets/movie/goodgirls.png')
          },
          {
            name: 'Resident Evil',
            description:'Biohazard company releases a virus that make people zombies. Not satisfied they release a BioWeapon Nemesis that they cant control',
            backgroundUrl: require('~/assets/movie/res.png')
          },
          
        ],
  }
  },
   created() {
      for(let i in this.movies){
        if(this.movies[i].name == this.$router.currentRoute.query['name']){
          this.movieUrl = this.movies[i].backgroundUrl;
        }
      }
    }
  
}
</script>