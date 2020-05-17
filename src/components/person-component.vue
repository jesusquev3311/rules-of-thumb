<template>
    <article class="person">
        <div class="person-wrapper">
            <div class="person-body">
                <v-row>
                    <v-col :md="2">
                        <span class="votes-icon">
                           <v-icon>fas fa-thumbs-up</v-icon>
                        </span>
                    </v-col>
                    <v-col :md="10">
                        <h3>Kanye West</h3>
                        <span class="person-date"><strong>1 month ago</strong> in Entertainment</span>
                        <p class="person-text">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Autem beatae deleniti eveniet exercitationem illo, illum laudantium minima odit, omnis quos, rem temporibus veniam voluptas! Cumque earum illum iure quaerat quibusdam?</p>
                        <div class="person-btns">
                            <v-icon class="person-btn bg-green">fas fa-thumbs-up</v-icon>
                            <v-icon class="person-btn bg-orange">fas fa-thumbs-down</v-icon>
                            <v-btn class="btn-vote">Vote</v-btn>
                        </div>
                    </v-col>
                </v-row>
            </div>
            <div class="person-votes"></div>
        </div>
    </article>
</template>

<script>
    export default {
        name: "person-component",
        props:['persons']
    }
</script>

<style lang="scss" scoped>

</style>
