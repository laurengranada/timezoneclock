<template>
    <v-container fluid class="main">
        <v-row justify="center">
            <v-col cols="6">
                <TimeZoneCard></TimeZoneCard>
            </v-col>
        </v-row>
        <v-row>
            <v-col
                v-for="n in 12"
                :key="n"
                class="d-flex child-flex"
                cols="4"
            >
                <TimeZoneCard></TimeZoneCard>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import TimeZoneCard from './../components/TimeZoneCard.vue';
export default {
    components: {
        TimeZoneCard
    },
    data () {
        return {
            //
        };
    }
};
</script>

<style lang="scss" scoped>
.main{
    // background-color: pink;
    padding: 1rem;
    height: 100%;
    width: 100%;
    overflow-y: scroll;
}
</style>
