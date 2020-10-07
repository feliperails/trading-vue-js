<template>
<trading-vue :data="chart" :width="this.width" :height="this.height"
        :color-back="colors.colorBack"
        :color-grid="colors.colorGrid"
        :color-text="colors.colorText">
</trading-vue>
</template>

<script>
import axios from 'axios'
import TradingVue from './TradingVue.vue'
import Data from '../data/data.json'

export default {
    name: 'app',
    components: {
        TradingVue
    },
    methods: {
        onResize() {
            this.width = window.innerWidth
            this.height = window.innerHeight
        }
    },
    mounted() {
        window.addEventListener('resize', this.onResize)
        setInterval(() => {
            // Async data setup
            axios.get('/data/data.txt')
                .then((response) => {
                    let lines = response.data.split(/[\r\n]+/)
                    lines.shift()
                    let chartData = {
                        chart: {
                            indexBased: true,
                            tf: "1H",
                            type: "Candles",
                            data: []
                        }
                    };
                    for (let line of lines)
                    {
                        let lineParts = line.split(/\s/);
                        if (lineParts.length < 5)
                        {
                            continue
                        }
                        let item = [
                            1584428400000,
                            parseInt(lineParts[1]), // open
                            parseInt(lineParts[3]), // high
                            parseInt(lineParts[2]), // low
                            parseInt(lineParts[4]), // close
                            parseInt(lineParts[5]) // volume
                        ];
                        if (item[5] == 0)
                        {
                            item.push({
                                colorCandleUp: "black",
                                colorCandleDw: "pink"
                            });
                        }
                        chartData.chart.data.push(item);
                    }
                    this.$set(this, 'chart', chartData)
                    console.log("pruu")
                });
        }, 2000)
    },
    beforeDestroy() {
        window.removeEventListener('resize', this.onResize)
    },
    data() {
        return {
            chart: {}, // Data will be here,
            width: window.innerWidth,
            height: window.innerHeight,
            colors: {
                colorBack: '#fff',
                colorGrid: '#eee',
                colorText: '#333',
            }
        };
    }
};
</script>

<style>
html,
body {
    background-color: #000;
    margin: 0;
    padding: 0;
    overflow: hidden;
}
</style>
