<template>
<div class="myMain">

    <div class="myAlbums">
        <div v-for="(song, index) in mySongs" :key="index" class="SongCard">
            <div class="myCover">
                <img :src="mySongs[index].poster">
            </div>
                <h1>{{mySongs[index].title}}</h1>
                <h3>{{mySongs[index].author}}</h3>
                <h4>{{mySongs[index].year}}</h4>
                
            
        </div>
    </div>
</div>
</template>

<script>
import axios from 'axios';



export default {
    name: 'myMain',

    data () {
        return {

            mySongs: [],
            myApi: 'https://flynn.boolean.careers/exercises/api/array/music',
            genres: [],
            filteredSongs: []
            
        }
    },

    props: {

        genreFromHeader: String
    },

    created() {
        this.getSongs();

        axios.get(this.myApi)
        .then((res) => {
            this.mySongs = res.data.response
            this.mySongs.forEach(mySongs => {
                if (!this.genres.includes(mySongs.genre)){
                    this.genres.push(mySongs.genre);                   
                }

        
            })
            this.$emit('genresReady', this.genres)    
        })

    },

    computed: {

        filteredMusic(){ 
            if(this.genreFromHeader == ''){
                return this.mySongs
            } else {
                const filteredSongs = this.mySongs.filter(song => {
                    if(song.genre == this.genreFromHeader) {
                        return true 
                    } else {
                        return false
                    }
                })
                return this.mySongs = filteredSongs
            }
            }    
        },
    

    methods: { 

        getSongs(){
            let that = this
                axios.get(this.myApi)
                .then(function (response){
                that.mySongs = response.data.response
            })
        }
    

}
}

</script>

<style lang="scss">

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }


.myMain {

    background-color: #212D3A;
    display:flex;
    justify-content: center;
}

.myAlbums {

    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    width: 50%;
    gap: 20px 5px;

    .SongCard {
        
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;

        height: 200px;
        width: calc(90%/5);
        background-color: #5f6a76;
        
        
    }

    .myCover {

        width: 60%;
        height: 100px;
        img{
            width: 100%;
            object-fit: cover;
        
    }        

    }

    h1,h2,h3,h4 {

        font-size: 0.7em;
        
        
    }

    h1 {

        color: white;
    }

    
}
</style>
