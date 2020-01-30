<template>
    <div>
        <div class="clock" v-if="hourtime != ''">
            <div class="clock__hours">
                <span v-text="hours"></span>
            </div>
            <div class="clock__minutes" v-text="minutes"></div>
            <div class="clock__seconds">
                <span v-text="seconds"></span>
                <span class="clock__hourtime" v-text="hourtime"></span>
            </div>
            <div class="clock_date">
                <span class="clock_date_day" v-text="aDays[dayOfWeek]"></span>
                <span v-text="aMonths[month]"></span>.
                <span v-text="date"></span>,
                <span v-text="year"></span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            hours: 0,
            minutes: 0,
            seconds: 0,
            hourtime: '',
            dayOfWeek: '',
            month: '',
            date: '',
            year: '',
            aDays: [
                'Sun',
                'Mon',
                'Tues',
                'Weds',
                'Thurs',
                'Fri',
                'Sat'
            ],
            aMonths: [
                'Jan',
                'Feb',
                'Mar',
                'Apr',
                'May',
                'June',
                'July',
                'Aug',
                'Sept',
                'Oct',
                'Nov',
                'Dec'
            ]
        };
    },
    mounted () {
        this.$options.interval = setInterval(this.updateDateTime, 1000);
    },
    beforeDestroy () {
        clearInterval(this.$options.interval);
    },
    methods: {
        updateDateTime () {
            let now = new Date();
            this.hours = this.getZeroPad(now.getHours());
            this.minutes = this.getZeroPad(now.getMinutes());
            this.seconds = this.getZeroPad(now.getSeconds());
            this.hourtime = this.getHourTime(this.hours);
            this.hours = this.hours % 12 || 12;
            this.dayOfWeek = now.getDay();
            this.month = now.getMonth();
            this.date = now.getDate();
            this.year = now.getFullYear();
        },
        getZeroPad: function (n) {
            return (parseInt(n, 10) >= 10 ? '' : '0') + n;
        },
        getHourTime: function (h) {
            return h >= 12 ? 'PM' : 'AM';
        }
    }
};
</script>

<style lang="scss" scoped>
.clock {
  background: #fff;
  border: .3rem solid #fff;
  border-radius: .5rem;
  display: inline-block;
  margin-bottom: 1em;
}
.clock__hours,
.clock__minutes,
.clock__seconds {
  /* background: linear-gradient(to bottom, #26303b 50%, #2c3540 50%); */
  background-color: #26303b;
  display: inline-block;
  color: #fff;
  font-family: 'Nunito', sans-serif;
  font-size: 3rem;
  font-weight: 300;
  padding: .5rem 1rem;
  text-align: center;
  position: relative;
}
.clock__hours {
  border-right: .15rem solid #fff;
  border-radius: .5rem 0 0 .5rem;
}
.clock__minutes {
  border-right: .15rem solid #fff;
}
.clock__seconds {
  border-radius: 0 .5rem .5rem 0;
}
.clock__hourtime {
  font-size: 1rem;
  position: absolute;
  bottom: 2px;
  right: 8px;
}
.clock_date{
    color: #26303b;
    .clock_date_day{
        padding-right: .25rem;
    }
}
</style>
