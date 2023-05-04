<template>
  <div class="client-status">
  <highcharts :options="chartOptions"></highcharts>
  </div>
</template>

<script>

import {Chart} from 'highcharts-vue'

export default {
    name: 'ClientStatus',
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
                    plotBackgroundColor: null,
                    plotBorderWidth: null,
                    plotShadow: false,
                    type: 'pie'
                },
                title: {
                    text: 'CMC Clients Status',
                    align: 'left'
                },
                tooltip: {
                    pointFormat: '{series.name}: <b>{point.percentage:.1f}%</b>'
                },
                accessibility: {
                    point: {
                        valueSuffix: '%'
                    }
                },
                plotOptions: {
                    pie: {
                        allowPointSelect: true,
                        cursor: 'pointer',
                        dataLabels: {
                            enabled: true,
                            format: '<b>{point.name}</b>: {point.percentage:.1f} %'
                        }
                    }
                },
                series: [{
                    name: 'CMC Clients',
                    colorByPoint: true,
                    data: [{
                        name: 'Online',
                        y: 79,
                    }, {
                        name: 'Offline',
                        y: 21
                    }]
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
