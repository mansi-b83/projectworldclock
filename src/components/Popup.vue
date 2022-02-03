<template>
    <v-dialog max-width ="800px">
        <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="red "
          dark
          v-bind="attrs"
          v-on="on"
        >
           Search Time
        </v-btn>
      </template>
        <v-card>
            <v-card-title>
              <h3>Search Time as per city</h3>
            </v-card-title>
            <v-card-text>
              <v-form class="px-3" method="post" >
                  <v-text-field label ="Country" v-model="country"></v-text-field>
                  <v-text-field label ="City" v-model="city"></v-text-field>
                  <v-btn flat color=#C5E1A5 type="submit" @click ="postData">Show Time</v-btn>
                  <div class = "center" style= "text-align: center">
                      <br>
                    <h2>{{datetimeres}}</h2>
                  </div>
              </v-form> 
            </v-card-text>
        </v-card>
    </v-dialog>
</template>


<script>
import Vue from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios, axios)
export default {
    name: 'Popup',
    data(){
        // return{list:null}
        return{
            country:'',
            city:'',
            result:'',
            search_city:''
        }
    },
    // mounted()
    // {
    //     Vue.axios.get('http://worldtimeapi.org/api/timezone/'+this.country+'/'+this.city)
    //     .then((resp)=>{
    //         //this.list=resp.data;
    //         console.log('hello')
    //         console.warn(resp,this.country,this.city)
    //         //console.warn(this.list);
    //     })
    // },
   
    methods:{
        postData(e){
            Vue.axios.get('http://worldtimeapi.org/api/timezone/'+this.country+'/'+this.city)
            .then((resp)=>{
                
                console.log('hello')
                
                console.warn(resp.data.datetime)
                this.result = resp.data.datetime.toString()
                this.search_city = this.city
                // console.warn(resp.data)
                //console.warn(this.list);
             }),
            
            // console.log(this.country,this.city)
            e.preventDefault();
         
        },
    },
    computed: {
    datetimeres: function () {
    //   result =this
      return this.result.slice(11,26) + ' ' + this.search_city 
    }
  }   
};
</script>