<template>
    <v-card
        class="timeCard ma-3 pa-6">
        <FlipClock></FlipClock>
        <v-card-text class="timeCard_body">
            <span class="timeCard_body_timezone">Time Zone</span>
            <span class="timeCard_body_label">Label/Nickname</span>
        </v-card-text>
        <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn icon>
                <v-icon>mdi-pencil-outline</v-icon>
            </v-btn>
            <v-btn icon>
                <v-icon>mdi-close</v-icon>
            </v-btn>
        </v-card-actions>
    </v-card>
</template>

<script>
import FlipClock from './FlipClock.vue';
export default {
    components: {
        FlipClock
    },
    data () {
        return {
            //
        };
    }
};
</script>

<style lang="scss" scoped>
.timeCard{
    text-align: center;
    .timeCard_body{
        text-align: center;
        .timeCard_body_timezone{
            display: block;
        }
        .timeCard_body_label{
            display: block;
        }
    }
}
</style>
