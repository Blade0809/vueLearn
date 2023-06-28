<template>
  <div class="echarts-box">
    <div id="myEcharts" :style="{ width: this.width, height: this.height }"></div>
  </div>
</template>

<script>
import * as echarts from "echarts";
import {onMounted, onUnmounted} from "vue";

export default {
  name: "App",
  props: ["width", "height"],
  setup() {
    let myEcharts = echarts;

    onMounted(() => {
      initChart();
    });

    onUnmounted(() => {
      myEcharts.dispose;
    });

    function initChart(){
      let chartDom = document.getElementById('main');
      let myChart = echarts.init(chartDom);
      let option;

      let data = [
        {
          name: '广州',
          itemStyle: {
            color: '#da0d68'
          },
          children: [
            {
              name: '新增546',
              value: 546,
              itemStyle: {
                color: '#975e6d'
              }
            },
            {
              name: '现有3764',
              value: 3764,
              itemStyle: {
                color: '#e0719c'
              },
              children: [
                {
                  name: '境外输入1270',
                  value: 1270,
                  itemStyle: {
                    color: '#ebb40f'
                  }
                }
              ]
            }
          ]
        },
        {
          name: '深圳',
          itemStyle: {
            color: '#da1d23'
          },
          children: [
            {
              name: '新增90',
              value: 90,
              itemStyle: {
                color: '#dd4c51'
              }
            },
            {
              name: '现有1790',
              value: 1790,
              itemStyle: {
                color: '##3e0317'
              }
            }
          ]
        },
        {
          name: '湛江',
          itemStyle: {
            color: '#ebb40f'
          },
          children: [
            {
              name: '新增121',
              value: 121,
              itemStyle: {
                color: '#e1c315'
              }
            },
            {
              name: '现有1487',
              value: 1487,
              itemStyle: {
                color: '#9ea718'
              }
            }
          ]
        },
        {
          name: '佛山',
          itemStyle: {
            color: '#187a2f'
          },
          children: [
            {
              name: '新增358',
              value: 358,
              itemStyle: {
                color: '#a2b029'
              }
            },
            {
              name: '现有1285',
              value: 1285,
              itemStyle: {
                color: '#718933'
              }
            }
          ]
        },
        {
          name: '汕头',
          itemStyle: {
            color: '#0aa3b5'
          },
          children: [
            {
              name: '新增93',
              value: 93,
              itemStyle: {
                color: '#9db2b7'
              }
            },
            {
              name: '现有1160',
              value: 1160,
              itemStyle: {
                color: '#8b8c90'
              }
            }
          ]
        },
        {
          name: '茂名',
          itemStyle: {
            color: '#c94930'
          },
          children: [
            {
              name: '新增86',
              value: 86,
              itemStyle: {
                color: '#caa465'
              }
            },
            {
              name: '现有1123',
              value: 1123,
              itemStyle: {
                color: '#dfbd7e'
              }
            }
          ]
        },
        {
          name: '中山',
          itemStyle: {
            color: '#ad213e'
          },
          children: [
            {
              name: '新增40',
              value: 40,
              itemStyle: {
                color: '#794752'
              }
            },
            {
              name: '现有885',
              value: 885,
              itemStyle: {
                color: '#cc3d41'
              }
            }
          ]
        },
        {
          name: '珠海',
          itemStyle: {
            color: '#a87b64'
          },
          children: [
            {
              name: '新增93',
              value: 93,
              itemStyle: {
                color: '#c78869'
              }
            },
            {
              name: '现有873',
              value: 873,
              itemStyle: {
                color: '#d4ad12'
              }
            }
          ]
        },
        {
          name: '惠州',
          itemStyle: {
            color: '#e65832'
          },
          children: [
            {
              name: '新增128',
              value: 128,
              itemStyle: {
                color: '#d45a59'
              }
            },
            {
              name: '现有843',
              value: 843,
              itemStyle: {
                color: '#310d0f'
              }
            }
          ]
        },
        {
          name: '东莞',
          itemStyle: {
            color: '#e65832'
          },
          children: [
            {
              name: '新增180',
              value: 180,
              itemStyle: {
                color: '#ae341f'
              }
            },
            {
              name: '现有734',
              value: 734,
              itemStyle: {
                color: '#d78823'
              }
            }
          ]
        },
        {
          name: '肇庆',
          itemStyle: {
            color: '#da5c1f'
          },
          children: [
            {
              name: '新增40',
              value: 40,
              itemStyle: {
                color: '#f89a80'
              }
            },
            {
              name: '现有690',
              value: 690,
              itemStyle: {
                color: '#f37674'
              }
            }
          ]
        }
      ];
      option = {
        title: {
          text: 'COVID IN GUANGDONG',
          // subtext: 'Source: https://worldcoffeeresearch.org/work/sensory-lexicon/',
          textStyle: {
            fontSize: 14,
            align: 'center'
          },
          subtextStyle: {
            align: 'center'
          }
          // sublink: 'https://worldcoffeeresearch.org/work/sensory-lexicon/'
        },
        series: {
          type: 'sunburst',
          data: data,
          radius: [0, '95%'],
          sort: undefined,
          emphasis: {
            focus: 'ancestor'
          },
          levels: [
            {},
            {
              r0: '15%',
              r: '35%',
              itemStyle: {
                borderWidth: 2
              },
              label: {
                rotate: 'tangential'
              }
            },
            {
              r0: '35%',
              r: '70%',
              label: {
                align: 'right'
              }
            },
            {
              r0: '70%',
              r: '72%',
              label: {
                position: 'outside',
                padding: 3,
                silent: false
              },
              itemStyle: {
                borderWidth: 3
              }
            }
          ]
        }
      };

      option && myChart.setOption(option);

      return {
        initChart
      };
    }
  }
}
</script>


