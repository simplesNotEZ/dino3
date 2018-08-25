<template>
    <footer>
        <small>&copy; 2018</small>
    </footer>
</template>

<script>
export default {
    name: "Footer"

}

</script>


<style>

small {
    color: black;
    font-size: .5rem;
    margin-left: 10px;
}

footer {
    position: fixed;
    bottom: 0;
    padding: 5px;
}

footer small {
    margin: 0 auto;
}

</style>
