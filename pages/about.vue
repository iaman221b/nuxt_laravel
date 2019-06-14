<template>
    
    <div>
        <h1>About</h1>
        <AboutNobb/>
    </div>
</template>

<script>
import AboutNo from '~/components/AboutNo.vue'
export default {
    components: {
        'AboutNobb': AboutNo
    },
    layout: 'aboutlayout',
    auth: false,
}
</script>

