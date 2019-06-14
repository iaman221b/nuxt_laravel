<template>
    <div>
        <div>
        <h2>Making API request - Vue way</h2>

    </div>
    <div>
        <!-- {{posts}} -->
        <h4 v-for="post in posts" :key="post.id">
            {{post.title}}
        </h4>
    </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return{
            posts: []
        }
    },
    asyncData(){
        let vim = this
       axios.get('https://jsonplaceholder.typicode.com/todos')
        .then(res => {
            console.log(vim)
            // return {posts: response.data} 
            vim.posts = res.data
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

