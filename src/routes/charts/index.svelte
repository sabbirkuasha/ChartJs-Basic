
<script>
    import {onMount} from 'svelte'
    // import Chart from 'chart.js/auto'; //This is not supported when building with es6 
    import Chart from '../../../node_modules/chart.js/auto/auto'

    let ctx
    let chartData = [12, 19, 17, 5, 15, 3]
    let labels = ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange']

    let ctxb
    let chartB_type = "line"
    let chartB_dataA = [12, 19, 17, 35, 15, 3]
    let chartB_dataB = [56, 39, 67, 25, 35, 13]
    let chartB_datasetA = {
                        label: '# of Votes',
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
                    }
    let chartB_datasetB = {
                        label: 'Voters',
                        data: chartB_dataB,
                        backgroundColor: [
                            'rgba(0, 114, 255, .5)',
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
                        spanGaps:true, //only when one of the data value is null
                        stepped: false,
                    }
    let labelsb = ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange']
    
    
    onMount(
        async()=>{
            const myChart = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: labels,
                    datasets: [{
                        label: '# of Votes',
                        data: chartData,
                        backgroundColor: [
                            'rgba(255, 99, 132, 0.2)',
                        ],
                        borderColor: [
                            'rgba(255, 99, 132, 1)',
                        ],
                        borderWidth: 3,
                        tension:0.3,
                        radius: 5,
                        pointHoverRadius:15,
                        pointBackgroundColor: 'white',
                        fill:true,
                        backgroundColor: 'orange'
                    }]
                },
                options: {
                    maintainAspectRatio: false,
                    scales: {
                        x:{
                            grid: {
                                display:true
                            }
                        },
                        y: {
                            display:true,
                            beginAtZero: true
                        }
                    }
                }
            })

            // line chart
            const myChartb = new Chart(ctxb, {
                type: chartB_type,
                data: {
                    labels: labelsb,
                    datasets: [chartB_datasetA, chartB_datasetB]
                },
                options: {
                    maintainAspectRatio: false,
                    scales: {
                        x:{
                            grid: {
                                display:true
                            }
                        },
                        y: {
                            display:true,
                            stacked: false,
                            beginAtZero: true
                        }
                    }
                }
            })
        }
    )
    
</script>


<main>
    <div class="divider p-5">Chart1</div>
    <div class="max-w-xl h-96 border m-auto">
        <canvas id="myChart" bind:this={ctx}></canvas>
    </div>

    <div class="divider p-5">Chart2</div>
    <div class="max-w-xl h-96 border m-auto">
        <canvas id="myChartb" bind:this={ctxb}></canvas>
    </div>
    
    <h1>Welcome to SvelteKit</h1>

</main>
