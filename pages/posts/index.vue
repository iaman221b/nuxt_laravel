<template>
    <div>
        <div>
        <h2>Making API request - Nuxt way</h2>

    </div>
    <div class="container row">
        <!-- {{posts}} -->
        <Card v-for="post in posts" :key="post.id" :post = "post" 
        class="ml-auto mr-auto" />                
        <button class="btn btn danger" v-scroll-to="'body'">Back to Top</button>
    </div>
    </div>
</template>


<script>
import axios from 'axios'
import Card from '@/components/Card'
import Vuex from 'vuex';
import {mapGetters} from 'vuex';
// import store from '../../store'
export default {
    components:{
        Card
    },
    data(){
        return {
            allposts:[]
        }
    },
    computed: {
        ...mapGetters(['posts'])
        // allPosts(){
        //     return this.$store.getters.posts
        // }
    },
    async asyncData({store}){
        let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts')
        // console.log(context);
        // return {posts: data}
        //  console.log(this.store)
         store.dispatch('setPosts' , data)
            
        
    },
    head: {
        title: "List of Posts"
    }
}
</script>



<!--
<script>
import axios from 'axios'
export default {
    data(){
        return{
            posts: []
        }
    },
     asyncData(context){
        // console.log(context);
        // let vim = this
       return axios.get('https://jsonplaceholder.typicode.com/todos')
        .then(res => {
            // console.log(vim)
            return {posts: res.data} 
            // vim.posts = res.data
        })
        .catch(error => {
                console.log(error)
        })
    //    return {posts: '100 posts'}
    //     console.log(context)
    //     if (process.server) {
    //   { host: req.headers.host }
    //   console.log(context)
    // }
    }
}
</script>

<!--
// <script>
// import axios from 'axios'
// export default {
//     data(){
//         return{
//             posts:[]
//         }
//     },
//     mounted(){
//         axios.get('https://jsonplaceholder.typicode.com/todos')
//         .then(response => {
//             console.log(response)
//             this.posts = response.data
//         })
//         .catch(error => {
//                 console.log(error)
//         })
//     }
// }
// </script>

