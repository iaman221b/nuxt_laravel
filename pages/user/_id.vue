<template>
    <h1>This is user's id {{$route.params.id}}</h1>
</template>
<script>
export default {
    validate({params}) {
        return /^\d+$/.test(params.id);
    }
}
</script>


