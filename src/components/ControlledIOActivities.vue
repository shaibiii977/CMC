<template>
<div class="client-status">
    <highcharts :options="chartOptions"></highcharts>
</div>
</template>

<script>
import {
    Chart
} from 'highcharts-vue'

export default {
    name: 'ControlledIOActivities',
    components: {
        highcharts: Chart
    },
    props: {
        msg: String
    },
    data() {
        return {
            chartOptions: {
                chart: {
                    type: 'line'
                },
                title: {
                    text: 'Controlled 1/O Activity By Computers'
                },
                xAxis: {
                    categories: ['Device 1', 'Device 2', 'Device 3', 'Device 4', 'Device 5']
                },
                yAxis: {
                    visible: false,
                    min: 0,
                    title: {
                        text: 'Device Name'
                    }
                },
                legend: {
                    reversed: true
                },
                plotOptions: {
                    series: {
                        stacking: 'normal',
                        dataLabels: {
                            enabled: false
                        }
                    }
                },
                series: [{
                    name: 'Computer',
                    data: [4, 4, 6, 5, 4]
                }]
            }
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
.client-status {
    border: 1px solid black;
}
</style>
