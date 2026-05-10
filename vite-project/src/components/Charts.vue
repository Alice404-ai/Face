<template>
    <div ref="chartRef" class="chart"></div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount, nextTick } from 'vue'
import * as echarts from 'echarts'

const chartRef = ref(null)
let chartInstance = null

// 模拟数据
const hours = Array.from({ length: 24 }, (_, i) => `${i}:00`)
const passCounts = Array.from({ length: 24 }, () => Math.floor(Math.random() * 50 + 10))

const initChart = () => {
    chartInstance = echarts.init(chartRef.value)
    const option = {
        tooltip: {
            trigger: 'axis'
        },
        xAxis: {
            type: 'category',
            data: hours,    
            boundaryGap: false
        },
        yAxis: {
            type: 'value',  
            min: 0
        },
        series: [
            {
                name: '通行人数',
                type: 'line',
                data: passCounts,
                smooth: true,
                symbol: 'circle',       // hover 显示圆点
                symbolSize: 8,
                itemStyle: {
                    color: '#5470C6'
                },
                lineStyle: {
                    width: 3
                },
                areaStyle: {           // 渐变区域
                    color: {
                        type: 'linear',
                        x: 0,
                        y: 0,
                        x2: 0,
                        y2: 1,
                        colorStops: [
                            { offset: 0, color: 'rgba(84, 112, 198, 0.5)' },
                            { offset: 1, color: 'rgba(84, 112, 198, 0)' }
                        ]
                    }
                }
            }
        ]
    }
    chartInstance.setOption(option)
}

// 自适应大小
const resizeChart = () => {
    chartInstance?.resize()
}

onMounted(() => {
    nextTick(() => {
        initChart()
        window.addEventListener('resize', resizeChart)
    })
})

onBeforeUnmount(() => {
    window.removeEventListener('resize', resizeChart)
    chartInstance?.dispose()
})
</script>

<style scoped>
.chart {
    width: 100%;
    height: 500px;
}
</style>