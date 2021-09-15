<template>
  <div id="app">
    <div class="monochrome-color-picker">
      <label class="monochrome-color-picker-label" for="monochrome">Monochrome</label>
      <input class="monochrome-color-picker-input" type="color" id="monochrome" @change="setMonochromeColor" />
    </div>

    <div class="dark-mode-toggle-button">
      <label class="dark-mode-toggle-button-label">
        Dark Mode
        <input class="dark-mode-toggle-button-input" type="checkbox" v-model="darkMode" />
      </label>
    </div>


    <ul class="theme-swatches" v-for="(swatch, index) in palette" :key="index">
      <li class="theme-swatches-item" v-for="theme in swatch" :key="theme.name" @click="switchTheme(theme.name)">
        <label class="theme-swatches-label" :for="theme.name">
          <input class="theme-swatches-checkbox" type="checkbox" :id="theme.name" />
          <span class="theme-swatches-name">{{ theme.name }}</span>
          <span class="theme-swatches-palette">
            <span class="hue primary"></span>
            <span class="hue secondary"></span>
            <span class="hue third"></span>
            <span class="hue fourth"></span>
            <span class="hue fifth"></span>
          </span>
        </label>
      </li>
    </ul>

    <button class="editBtn" @click="layoutEditable = !layoutEditable">Edit</button>
    <vuetiful-board
      :theme="theme"
      :dark-mode="darkMode"
      :col-num="colNum"
      :row-height="rowHeight"
      :layout-editable="layoutEditable"
      :datasets="[
        {
          chartInfo: {
            series: [
              {

                data: [27, 38, 19, 26, 19, 31, 27, 20, 28, 36, 37, 38],
              },
              {

                data: [17, 11, 24, 26, 18, 14, 19, 12, 14, 17, 15, 16],
              },
              {

                data: [5, 5, 9, 12, 4, 6, 5, 3, 4, 4, 6, 8],
              },
              {

                data: [2, 5, 4, 4, 2, 3, 6, 2, 2, 7, 2, 1],
              },
              {

                data: [4, 1, 3, 1, 3, 3, 2, 2, 4, 4, 5, 4],
              },
              {

                data: [0, 0, 0, 1, 1, 0, 2, 1, 1, 0, 0, 0],
              },
              {

                data: [45, 1, 4, 7, 8, 7, 5, 3, 6, 4, 1, 1],
              },
            ],
            options: {
              chart: {
                type: 'bar',
                stacked: true,
                stackType: '100%',
              },
              plotOptions: {
                bar: {
                  horizontal: true,
                },
              },
              title: {

                align: 'center',
                style: {
                  fontSize: '18px',
                  fontWeight: 'bold',
                },
              },
              xaxis: {
                categories: [
                  '2020-07',
                  '2020-08',
                  '2020-09',
                  '2020-10',
                  '2020-11',
                  '2020-12',
                  '2021-01',
                  '2021-02',
                  '2021-03',
                  '2021-04',
                  '2021-05',
                  '2021-06',
                ],
              },
              fill: {
                opacity: 1,
              },
              legend: {
                position: 'bottom'
              },
            }
          },
          gridInfo: {
            x: 0, y: 0, w: 6, h: 12, i: '0', static: false
          },
        },
        {
          chartInfo: {
            series: [186, 93, 30, 20, 21, 4, 20],
            options: {
              chart: {
                type: 'pie',
              },
              title: {

                align: 'center',
                style: {
                  fontSize: '18px',
                  fontWeight: 'bold',
                },
              },

              fill: {
                opacity: 1,
              },
              legend: {
                position: 'bottom',
              }
            }
          },
          gridInfo: {
            x: 6, y: 0, w: 6, h: 15, i: '1', static: false
          },
        },
        {
          chartInfo: {
            series: [
              {

                type: 'bar',
                data: [46632870, 41584730, 52955270, 48567390, 58018330, 55539980, 58520700, 49065550, 50117730, 58495400, 48557530, 48517400],
              },
              {

                type: 'bar',
                data: [39924170, 41147250, 35482200, 40162390, 67997690, 64065550, 49789670, 46006220, 47063870, 50758110, 47677190, 49274240]
              },
              {

                type: 'line',
                data: [null, null, null, null, null, null, null, null, 160, 34, 13, 32]
              },
              {

                type: 'line',
                data: [-14, -1, -33, -17, 17, 15, -15, -6, -6, -13, -2, 2]
              },
            ],
            options: {
              chart: {
                type: 'line',
              },
              title: {

                align: 'center',
                style: {
                  fontSize: '18px',
                  fontWeight: 'bold',
                },
              },
              xaxis: {
                categories: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12],
                labels: {
                  formatter: function(value) {
                    return `${value}`;
                  }
                }
              },
              yaxis: [
                {

                  axisTicks: {
                    show: true
                  },
                  axisBorder: {
                    show: true,
                  },
                  title: {

                  },
                  max: 80000000
                },
                {

                  show: false,
                  max: 80000000
                },
                {
                  opposite: true,

                  axisTicks: {
                    show: true
                  },
                  axisBorder: {
                    show: true,
                  },
                  title: {

                  },
                  min: -50,
                  max: 200,
                  labels: {
                    formatter: function(value) {
                      return `${value}%`;
                    },
                  }
                },
                {

                  show: false,
                  min: -50,
                  max: 200,
                  labels: {
                    formatter: function(value) {
                      return `${value}%`;
                    },
                  }
                },
              ],
              tooltip: {
                y: [
                  {
                    formatter: function(value) {
                      return `${value}`
                    }
                  },
                  {
                    formatter: function(value) {
                      return `${value}`
                    }
                  },
                  {
                    formatter: function(value) {
                      return `${value}%`
                    }
                  },
                  {
                    formatter: function(value) {
                      return `${value}%`
                    }
                  },
                ]
              },
              legend: {
                position: 'bottom',
              }
            }
          },
          gridInfo: {
            x: 0, y: 10, w: 6, h: 12, i: '2', static: false
          },
        },
        {
          chartInfo: {
            series: [
              {

                data: [104, 87, 110, 105, 137, 112, 114, 108, 85, 103, 87, 78]
              },
              {

                data: [82, 60, 102, 114, 166, 142, 117, 104, 106, 136, 122, 105]
              },
              {

                data: [128, 87, 58, 74, 73, 73, null, null, null, null, null, null]
              }
            ],
            options: {
              chart: {
                type: 'bar',
              },
              title: {

                align: 'center',
                style: {
                  fontSize: '18px',
                  fontWeight: 'bold',
                },
              },
              xaxis: {
                categories: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12],
                labels: {
                  formatter: function(value) {
                    return `${value}`;
                  }
                },
              },
              dataLabels: {
                enabled: false
              },
              tooltip: {
                y: {
                  formatter: function(value) {
                    return `${value}`
                  }
                }
              },
              legend: {
                position: 'bottom',
              }
            }
          },
          gridInfo: {
            x: 6, y: 10, w: 6, h: 12, i: '3', static: false
          },
        },
        {
          chartInfo: {
            series: [
              {
                name: '2020',
                data: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
              },
              {
                name: '2021',
                data: [0, 0, 20, 17, 8, 10, 0, 0, 0, 0, 0, 0]
              }
            ],
            options: {
              chart: {
                type: 'line',
              },
              title: {
                align: 'center',
                style: {
                  fontSize: '18px',
                  fontWeight: 'bold',
                },
              },
              xaxis: {
                categories: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12],
                labels: {
                  formatter: function(value) {
                    return `${value}`;
                  }
                },
              },
              yaxis: {
                min: 0,
                max: 100,
                labels: {
                  formatter: function(value) {
                    return `${value}%`;
                  },
                }
              },
              dataLabels: {
                enabled: true,
                formatter: function(value) {
                  return `${value}%`;
                }
              },
              tooltip: {
                y: {
                  formatter: function(value) {
                    return `${value}%`
                  }
                }
              },
              legend: {
                position: 'bottom',
              }
            }
          },
          gridInfo: {
            x: 0, y: 20, w: 6, h: 12, i: '4', static: false
          },
        },
        {
          chartInfo: {
            series: [
              {
                type: 'column',
                data: [125, 207, 218, 191, 241, 258, 204, 217, 294, 252, 208, 126, 217, 259, 257, 213]
              },
              {
                type: 'line',
                data: [null, 66, 74, 53, 93, 106, 63, 74, 135, 102, 66, 1, 74, 107, 106, 70]
              }
            ],
            options: {
              chart: {
                type: 'line',
              },
              title: {
                align: 'center',
                style: {
                  fontSize: '18px',
                  fontWeight: 'bold',
                },
              },
              xaxis: {
                categories: ['2003', '2004', '2005', '2006', '2007', '2008', '2009', '2010', '2011', '2012', '2101', '2102', '2103', '2104', '2105', '2106'],
              },
              yaxis: [
                {
                  title: {

                  }
                },
                {
                  opposite: true,
                  title: {
                  },
                  min: -50,
                  max: 200,
                  labels: {
                    formatter: function(value) {
                      return `${value}%`;
                    },
                  }
                },
              ],
              annotations: {
                yaxis: [{
                  y: 125,
                  borderColor: '#ff4560',
                  label: {
                    borderColor: '#ff4560',
                    style: {
                      color: '#fff',
                      background: '#ff4560',
                    },
                  }
                }],
              },
              tooltip: {
                y: [
                  {
                    formatter: function(value) {
                      return `${value}`
                    }
                  },
                  {
                    formatter: function(value) {
                      return `${value}%`
                    }
                  },
                ]
              },
              legend: {
                position: 'bottom',
              }
            },
          },
          gridInfo: {
            x: 6, y: 20, w: 6, h: 12, i: '5', static: false
          }
        }
      ]"
    />
  </div>
</template>

<script>
import VuetifulBoard from '../../src/components/VuetifulBoard.vue';
import palette from '../../src/assets/palette.json';

export default {
  components: { VuetifulBoard },
  name: 'App',
  data() {
    return {
      theme: 'classic',
      darkMode: false,
      layoutEditable: true,
      colNum: 12,
      rowHeight: 30,
      palette: {
        type: Array,
        palette,
      },
    }
  },
  methods: {
    switchTheme(themeName) {
      this.theme = themeName;
    },
    setMonochromeColor(event) {
      this.theme = event.target.value;
    },
  },
};
</script>

<style lang="scss" scoped>
.theme-swatches {
  display: flex;
  justify-content: space-between;
  align-content: center;
  padding: 0;
}

.theme-swatches-item {
  background: #fff;
  border: 1px solid #e5e5e5;
  border-radius: 10px;
  text-align: center;
  transition: transform .2s cubic-bezier(.4, 0, .2, 1);

  &:hover {
    box-shadow: 0 2px 16px rgb(0 0 0 / 15%);
    transform: scale(1.05);
  }

  .theme-swatches-label {
    position: relative;
    display: block;
    width: 100%;
    height: 100%;
    padding: 10px 15px;
    cursor: pointer;
  }

  .theme-swatches-checkbox {
    display: none;
  }

  .theme-swatches-name {
    display: block;
    color: #232323;
    font-size: 14px;
  }

  .hue {
    display: inline-block;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    box-shadow: 0 0 0 2px #fff;
    vertical-align: middle;

    &.primary {
      background: #5975fe;
    }

    &.secondary {
      background: #54d2d2;
    }

    &.third {
      background: #ffcb00;
    }

    &.fourth {
      background: #ff6150;
    }

    &.fifth {
      background: #1360bf;
    }

    & + .hue {
      margin-left: -6px;
    }
  }
}

.editBtn {
  padding: 7px;
  border: 1px solid #fff;
  border-radius: 5px;
  background: #fff;
  cursor: pointer;
}
</style>