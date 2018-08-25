<template>
    <div>
        <form id="application-input" v-on:submit="submitStuff">
            <label>Apply Here: </label>
            <textarea v-model="appText" id="application-text" rows="8" cols="100"></textarea>
            <input id="submit" type="submit" value="Submit" />
        </form>
        <Preview v-bind:appText="appText" v-bind:message="message"/>
    </div>

</template>

<script>
import Preview from './Preview'

export default {
    name: "Form",
    components: {
        Preview

    },
    data() { 
        return {
        appText: "",
        message: ""
        }
    },
    methods: {
        captureText() {
            const textArea = document.getElementById("application-text");
            return this.appText = textArea.value;
        },
        submitStuff(event) {
            event.preventDefault();
            event.target.reset();
            this.appText = "";
            this.message = "Your application was submitted!";
        }

    },
    props: []
}

</script>

<style>


</style>