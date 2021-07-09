<template>
<div>
       <v-banner>
         <br>
         <h1>
           Hi {{user.name}}!
         </h1>    
         <br>
         <p>
          here are some suggestions based on what you like to watch, have fun alienating yourself from real life.
         </p>   
         
         </v-banner>

     

  
<br>
<v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6" lg="5" class="text-center ">
      <v-form
      >
              <v-autocomplete
                 v-model="value"
    
                
                  filled
                :enabled="isUpdating"

                :items="movies"
                solo
                
                color="dark"
                label="Search"
                item-value="name"
                item-text="name"
               
                clearable
                 @change="search(value)"
                :append-icon-cb="helo"
                :open-on-click="false"
              >

              </v-autocomplete>
      </v-form>
 
  </v-col>
  </v-row>


  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6" lg="11" class="text-center ">
      <v-sheet
      
    class="mx-auto shades transparent radius"
    max-width="100%"
  >

  <div
  v-for="categorie in categories"
      :key="categorie"
      class="text-left font-weight-bold"
      style="font-size:24px"
      >
      {{categorie.alias}}
    <v-slide-group
      v-lazy
      class="mb-16 mt-2"
      multiple
      show-arrows
    >
      <v-slide-item
        v-for="movie in categorie.movies"
        :key="movie"
      >
  
      <v-hover  v-slot="{ hover }">
        <v-card
        class="mx-1"
        width="250px"
        height="150px"
        >
         <v-expand-transition align="center">
          <v-card
            v-if="hover"
            class="d-flex transition-fast-in-fast-out v-card--reveal white--text "
            style="height:100%; margin:1; text-align: justify; text-justify: inter-word; padding: 7px;"
          >
          <v-card-text>

            {{ movie.description }}
          </v-card-text>
          </v-card>
        </v-expand-transition>
        <v-img
          width="100%"
          height="100%"
          class="rounded"
         :src=movie.backgroundUrl >
        </v-img>
  
    
        </v-card>
      </v-hover>
      </v-slide-item>
    
    </v-slide-group>
  </div>
  </v-sheet>
    </v-col>
  </v-row>


  


</div>
</template>

<script>

export default {
   data() {
    return {
      movies:[],
      image: 'hp5',
    data: 'nice',
    
    user:{
      name: "Bruno",
    },
    categories:[
       
       {
        alias:"Recomendados",
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
       },
      
       
       
    ],
  }
  },
  created() {
    for(let i in this.categories){
      for(let j in this.categories[i].movies){
        this.movies.push(this.categories[i].movies[j]);

      }
    }
  },

  methods: {
   async search(value){
      window.location.href="/search?name="+value;
    }

  },

 
  
}
</script>

<style scoped>
.rounded{
  border: 0;
  border-style: solid;
  border-radius: 7px;
  border-color: rgba(240, 248, 255, 0);
}
</style>