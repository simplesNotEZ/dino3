<template>
    <div>
        <p id="message">{{message}}&nbsp;</p>
        <button id="preview-toggle" v-on:click="toggleHidden">Show Preview</button>
        <section id="application-preview" v-if="previewShow">
            {{appText}}
        </section>
    </div>

</template>

<script>

export default {
    name: "Preview",
    components: {

    },
    data() {
        return {
            previewShow: false
        }
    },
    methods: {
        toggleHidden() {
            this.previewShow = !this.previewShow;
        }
    },
    props: ['appText', 'message']
}

</script>

<style>

#application-preview {
    border-radius: 6px;
    box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
    border: 1px solid darkgrey;
    min-height: 100px;
    margin-top: 20px;
    padding: 10px;
}

section {
    font-weight: 500;
}


</style>