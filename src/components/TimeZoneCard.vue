<template>
    <v-card
        class="timeCard ma-3 pa-6">
        <!--  -->
        <div class="row">
            <div class="col-md-6">
                <div class="row counter">
                    <div class="col-md-4">
                        <button class="btn btn-default" id="sessDec">-</button>
                    </div>
                    <div class="col-md-2">
                        <div id="session"></div>
                    </div>
                    <div class="col-md-4">
                        <button class="btn btn-default" id="sessInc">+</button>
                    </div>
                </div>
            </div>
            <div class="col-md-6">
                <div class="row counter">
                    <div class="col-md-4">
                        <button class="btn btn-default" id="breakDec">-</button>
                    </div>
                    <div class="col-md-2">
                        <div id="break"></div>
                    </div>
                    <div class="col-md-4">
                        <button class="btn btn-default" id="breakInc">+</button>
                    </div>
                </div>
            </div>
        </div>
        <div id="clock" class="row">
            <div class="timer"><div class="middle"></div></div>
        </div>
        <!--  -->
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
export default {
    data () {
        return {
            //
        };
    }
};
</script>

<style lang="scss" scoped>
.timeCard{
     p {
  text-align: center;
}
.flip-clock-wrapper{
  max-width: 460px;
  margin: 3em auto 2em;
  display: flex;
  justify-content: center;
}
.col-md-4{
  display: flex;
  justify-content: center;
}
.col-md-2{
  display: flex;
  justify-content: center;
  height: 34px;
  align-items: center;
}
.counter{
  display: flex;
  justify-content: center;
}
.clock{
  margin-top: 30px;
}
.container {
  width: 500px;
}
.middle{
    display:inline-block;
}
#btns{
  display: flex;
  justify-content: center;
}
#stop {
  margin-left: 10px;
  margin-right: 10px;
}
.btn {
  background-color: #333333;
  color: #CCCCCC;
}
#sessInc, #sessDec, #breakInc, #breakDec {
  font-weight: bold;
}
#stats {
  background-color: #333333;
  width: 220px;
  height: 70px;
  border-radius: 10px;
  color: #CCCCCC;
  font-size: 45px;
  text-align: center;
}
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
