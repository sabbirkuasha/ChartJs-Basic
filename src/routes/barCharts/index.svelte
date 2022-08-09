
<script>
    import {onMount} from 'svelte'
    // import Chart from 'chart.js/auto'; //This is not supported when building with es6 
    import Chart from '../../../node_modules/chart.js/auto/auto'

    let a = 20
    $:a
    // setInterval(()=>{
    //     console.log(a)
    //     a = a+2
    // },1000)

    let ctxb 
    let chartB_type = "bar"
    let labelsb = ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange', 'Gray']
    let chartB_dataA = [32, 15, 19, 5, 35, 15, 43]
    let chartB_dataB = [56, 39, 67, 25, 35, 13, 19]
    let chartB_dataC = [[a, 20],[0,23]]

    let chartB_datasetA = {
                        label: 'red',
                        data: chartB_dataA,
                        backgroundColor: [
                            'rgba(255, 99, 132, 0.2)',
                        ],
                        borderColor: [
                            'rgba(255, 99, 132, 1)',
                        ],
                        borderWidth: 1.5,
                        borderDash: [5,5],
                        tension:0.3,
                        radius: 5,
                        pointRadius: 5,
                        pointHoverRadius:20,
                        pointBackgroundColor: 'rgba(249, 249, 249, 1)',
                        pointHoverBackgroundColor: 'rgba(249, 249, 249, 0.24)',
                        pointHoverBorderWidth:4,
                        pointStyle: 'rectRot',
                        fill:true,
                        showLine: true,
                        spanGaps:true, //only when one of the data value is null
                        stepped: false,
                        // xAxisID: 'down-y-axis'
                        // yAxisID: 'x',
                        // xAxisID: "bar-x-axis1",
                        // yAxisID: "bar-y-axis1",
                        // stack: 1,
                    }
    let chartB_datasetB = {
                        label: 'Voters',
                        indexAxis: 'x',
                        data: chartB_dataB,
                        backgroundColor: [
                            'rgba(138, 185, 255, .5)',
                        ],
                        borderColor: [
                            'rgba(138, 185, 255, 1)',
                        ],
                        borderWidth: 1.5,
                        borderDash: [5,5],
                        tension:0.3,
                        radius: 5,
                        pointRadius: 5,
                        pointHoverRadius:20,
                        pointBackgroundColor: 'rgba(249, 249, 249, 1)',
                        pointHoverBackgroundColor: 'rgba(249, 249, 249, 0.24)',
                        pointHoverBorderWidth:4,
                        pointStyle: 'circle',
                        fill:true,
                        showLine: true,
                        spanGaps:false, //only when one of the data value is null
                        stepped: false,
                        // xAxisID: "bar-x-axis1",
                        // yAxisID: "bar-y-axis1"
                        // stack: 1,
                    }
    let chartB_datasetC = {
                        label: 'Green',
                        indexAxis: 'x',
                        data: chartB_dataC,
                        backgroundColor: [
                            'rgba(9, 172, 0, .5)',
                        ],
                        borderColor: [
                            'rgba(9, 172, 0, 1)',
                        ],
                        borderWidth: 1.5,
                        borderDash: [5,5],
                        tension:0.3,
                        radius: 5,
                        pointRadius: 5,
                        pointHoverRadius:20,
                        pointBackgroundColor: 'rgba(249, 249, 249, 1)',
                        pointHoverBackgroundColor: 'rgba(249, 249, 249, 0.24)',
                        pointHoverBorderWidth:4,
                        pointStyle: 'circle',
                        fill: false,
                        showLine: true,
                        spanGaps:false, //only when one of the data value is null
                        stepped: false,
                        stack: 0,
                        // xAxisID: "left-x-axis",
                        // yAxisID: 'left-y-axis'
                    }
    
    
    let image = "$lib/repeat.jpg"
    
    let options = {
                    scales: {
                        x: [
                                {
                                    stacked: true,
                                    id: "bar-x-axis1",
                                    barThickness: 30,
                                }, 
                                {
                                    display: false,
                                    stacked: true,
                                    id: "bar-x-axis1",
                                    barThickness: 70,
                                    // these are needed because the bar controller defaults set only the first x axis properties
                                    type: 'category',
                                    categoryPercentage: 0.8,
                                    barPercentage: 0.9,
                                    gridLines: {
                                                    offsetGridLines: true
                                                },
                                    offset: false
                                }
                            ],
                        y: [
                        {
                            id: "bar-y-axis2",
                            stacked: true,
                            ticks: {
                                        beginAtZero: true,
                                        min: 0,
                                        max: 40,
                                        autoSkip: false, 
                                    }
                        },
                        {
                            id: "bar-y-axis2",
                            stacked: false,
                            ticks: {
                                        beginAtZero: true,
                                        min: 0,
                                        max: 40,
                                        autoSkip: false,
                                        display: false
                                    },
                            gridLines: {
                                display: false
                            }
                        }]

                    }
                    }


    let optionActual = {
                    maintainAspectRatio: false,
                    legend: {
                      display: true,  
                    },
                    scales: {
                        
                        x:{
                            stacked:true,
                            grid: {
                                display: true,
                            }
                        },
                        y: {
                            stacked: true,
                            display:true,
                            // beginAtZero: false
                        }
                    }
                }
    
    onMount(
        async()=>{
            // line chart
            const myChartb = new Chart(ctxb, {
                type: chartB_type,
                data: {
                    labels: labelsb,
                    datasets: [chartB_datasetA, chartB_datasetB, chartB_datasetC]
                },
                options: optionActual
            })
        }
    )
</script>


<main>
    <div class="divider p-5">Line chart</div>
    <div class="max-w-xl h-96 border m-auto">
        <canvas id="myChartb" bind:this={ctxb}></canvas>
    </div>
</main>
