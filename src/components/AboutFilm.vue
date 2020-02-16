<template>
    <div>
        <p>Identifiant : {{ $route.params.id }}</p>
    </div>
</template>

<script>
export default {
    name: "AboutFilm",
    props: {film : Object},
    
}
</script>