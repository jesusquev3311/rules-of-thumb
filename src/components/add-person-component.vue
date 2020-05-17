<template>
    <div class="add-person-wrapper">
        <v-row>
            <v-col :md="8">
                <p class="add-person-text">Is there anyone else you would want us to add?</p>
            </v-col>
            <v-col :md="4">
                <v-button>Submit a Name</v-button>
            </v-col>
        </v-row>
    </div>
</template>

<script>
    export default {
        name: "add-person-component"
    }
</script>

<style scoped>

</style>
