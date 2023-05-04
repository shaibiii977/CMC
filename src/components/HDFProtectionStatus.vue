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
                    type: 'pie',
                    width: 450
                },
                legend: {
                    align: 'right',
                    verticalAlign: 'top',
                    layout: 'vertical',
                    x: 0,
                    y: 100
                },
                title: {
                    text: 'HDF Protection Status',
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
                // legend: {
                //     enabled: true
                // },
                plotOptions: {
                    pie: {
                        allowPointSelect: true,
                        cursor: 'pointer',
                        // dataLabels: {
                        //     enabled: true,
                        //     format: '<b>{point.name}</b>: {point.percentage:.1f} %'
                        // }
                        dataLabels: {
                            enabled: false,
                        }
                    }
                },
                series: [{
                    showInLegend:true,
                    // center: [150, 150],
                    name: 'HDF Protection Status',
                    colorByPoint: true,
                    data: [{
                        name: 'Protected',
                        y: 45,
                    }, {
                        name: 'Audit',
                        y: 20,
                    },{
                        name: 'Unprotected',
                        y: 20,
                    }, {
                        name: 'Unknown',
                        y: 15
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
