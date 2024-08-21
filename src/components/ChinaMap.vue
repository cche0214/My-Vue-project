<template>
  <div class="container" style="height: 100%; width: 100%">
    <div id="content-left" class="col-md-12" style="margin-top: 10px">
      <div id="main" style="width: 100%; height: 800px"></div>
    </div>
  </div>
</template>

<script>
import * as echarts from 'echarts';
import $ from 'jquery';

export default {
  name: 'ChinaMap',
  data() {
    return {
      myChart: null,
    };
  },
  mounted() {
    this.loadScripts();
  },
  methods: {
    loadScripts() {
      const scripts = [
        '/assets/js/ChinaMapecharts.js',
        '/assets/js/chinaMapchain.js',
        '/assets/js/ChinaMapjquery-3.5.1.js'
      ];

      const loadScript = (src) => {
        return new Promise((resolve, reject) => {
          const script = document.createElement('script');
          script.src = src;
          script.async = true;
          script.onload = () => resolve();
          script.onerror = () => reject(new Error(`Failed to load script ${src}`));
          document.head.appendChild(script);
        });
      };

      // Load scripts sequentially
      scripts.reduce((p, src) => p.then(() => loadScript(src)), Promise.resolve())
        .then(() => {
          this.initChart();
          this.loadMapData();
        })
        .catch(error => console.error(error));
    },
    loadMapData() {
      $.getJSON('/assets/json/ChinaMapPoint.json', (data) => {
        echarts.registerMap('china', data);
        this.loadChartData();
      }).fail(() => {
        console.error('Failed to load map data.');
      });
    },
    initChart() {
      this.myChart = echarts.init(document.getElementById('main'));
    },
    loadChartData() {
      $.ajax({
        url: "/assets/json/ChinaMapPoint.json",
        type: "GET",
        dataType: "json",
        success: (data) => {
          let res = data.map(item => ({
            name: item.name,
            value: item.value,
            sales: item.Sales
          }));
          this.renderChart(res);
        }
      });
    },
    renderChart(dataValue) {
      const option = {
        tooltip: {
          show: true,
          triggerOn: 'click'
        },
        geo: {
          map: 'china',
          roam: false,
          zoom: 1.2,
          center: [105, 36],
          itemStyle: {
            areaColor: '#f5f2f2',
            borderColor: "#835f5f",
          },
          label: {
            show: true,
            fontSize: "11.5",
            color: "rgb(107,102,102)"
          },
          emphasis: {
            itemStyle: {
              areaColor: '#d0a3a3',
            },
            label: {
              show: true,
              color: "rgb(255,255,255)"
            }
          }
        },
        series: [
          {
            name: '销量',
            type: 'scatter',
            coordinateSystem: 'geo',
            data: dataValue,
            symbolSize: 12,
            itemStyle: {
              color: "#f13434",
              shadowBlur: 2,
              shadowColor: "#333"
            },
            tooltip: {
              show: true,
              triggerOn: "click",
              formatter: (data1) => data1.data.sales
            }
          },
          {
            name: "产品销量",
            type: "effectScatter",
            coordinateSystem: "geo",
            data: dataValue,
            symbolSize: 4,
            showEffectOn: "render",
            rippleEffect: {
              brushType: "stroke",
              color: "#f13434",
              period: 10,
              scale: 10
            },
            emphasis: {
              scale: true
            },
            label: {
              formatter: "{b}",
              position: "top",
              show: true,
              fontSize: "10",
            },
            itemStyle: {
              color: "#f13434",
              shadowBlur: 2,
              shadowColor: "#333"
            },
            tooltip: {
              show: true,
              triggerOn: "click",
              formatter: (data1) => data1.data.sales
            },
            zlevel: 1
          }
        ]
      };
      this.myChart.setOption(option);
      this.myChart.on('dblclick', this.handleDoubleClick);
    },
    handleDoubleClick(param) {
      const data = param.data;
      if (data) {
        let url;
        switch (data.name) {
          case '内蒙古':
            url = 'https://www.cumt.edu.cn/';
            break;
          case '重庆':
            url = 'https://www.cumt.edu.cn/kdzc/list.htm';
            break;
          case '沈阳918历史博物馆':
            url = 'https://example.com/918';
            break;
          case '西安事变纪念馆':
            url = 'https://example.com/xian';
            break;
          case '南昌八一起义纪念馆':
            url = 'https://example.com/nanchang';
            break;
          case '商丘陈官庄':
            url = 'https://example.com/chenguangzhuang';
            break;
          case '浙江省台州市茅畲乡下街村，温岭市坞根镇':
            url = 'https://example.com/taizhou';
            break;
          default:
            url = 'https://example.com/default';
        }
        window.location.href = url;
      }
    }
  }
};
</script>

<style scoped>
/* @import '../assets/css/chinaMapout.css'; */
body {
  line-height: 1.6;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
}

.container {
  width: 80%;
  max-width: 1200px;
  margin: auto;
  overflow: hidden;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

header {
  background: #f4f4f4;
  padding: 20px 0;
  text-align: center;
}

nav {
  display: flex;
  justify-content: center;
  background: rgb(30,50,100);
  padding: 5px 0;
}

nav a {
  color: #fff;
  padding: 10px 30px;
  text-decoration: none;
  font-size: 16px;
}

nav a.active {
  background-color: rgba(173, 216, 230, 0.6);
}

nav a:hover {
  color: #ff9900;
  text-decoration: none;
}

.content {
  background: #fff;
  padding: 10px;
  color: #333;
  font-size: 18px;
}

.content h1 {
  text-align: center;
  color: rgb(30,50,100);
  font-size: 28px;
  margin-top: 0;
  margin-bottom: 3px;
}

.content hr {
  margin: 0;
  height: 2px;
  background-color:rgb(30,50,100);
  border: none;
}

.text {
  font-family: 宋体;
  font-size: 18px;
  text-indent: 2em;
}

.form {
  font-family: 宋体;
  font-size: 16px;
  font-weight: 700;
}

.info {
  font-size: 14px;
  color: #777;
  text-align: center;
  margin: 5px;
}

.footer {
  background: rgb(30,50,100);
  color: #fff;
  text-align: center;
  padding: 12px 0;
  font-size: 14px;
}

header img {
  width: 470px;
  height: 105px;
  display: inline;
}

header span {
  color: rgb(30,50,100);
  font-size: 50px;
  font-family: 楷体;
}

.textimg {
  display: block;
  margin: auto;
}

.textexp {
  display: flex;
  justify-content: center;
  font-size: 14px;
  color: #777;
}

#main {
  width: 80%;
  height: 100%;
}

#content-left {
  width: 100%;
  height: 100%;
}

* {
  margin: 0px;
  padding: 0px;
}
</style>
