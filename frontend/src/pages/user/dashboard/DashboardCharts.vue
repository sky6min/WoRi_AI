<template>
  <div class="row row-equal">
    <!-- 제일 처음 뜨는 차트 -->
    <div class="flex xs12 xl8">
      <va-card v-if="lineChartData">
        <va-card-title>
          <h1>월별 탐지 상황</h1>
          <div class="mr-0 text-right"></div>
        </va-card-title>
        <va-card-content>
          <va-chart
            class="chart"
            ref="lineChart"
            :data="lineChartData"
            type="line"
          />
        </va-card-content>
      </va-card>
    </div>

    <!-- 원 차트 -->
    <div class="flex xs12 md6 xl4">
      <va-card class="d-flex">
        <va-card-title>
          <h1>놀이터 별 탐지상황</h1>
        </va-card-title>
        <va-card-content v-if="donutChartData">
          <va-chart
            class="chart chart--donut"
            :data="donutChartData"
            type="donut"
          />
        </va-card-content>
      </va-card>
    </div>
  </div>
</template>

<script>
import { getDonutChartData } from "@/data/charts/DonutChartData";
import { getLineChartData } from "@/data/charts/LineChartData";
import VaChart from "@/components/va-charts/VaChart.vue";
import DashboardContributorsChart from "./DashboardContributorsList";
import { useGlobalConfig } from "vuestic-ui";

export default {
  name: "dashboard-charts",
  components: { DashboardContributorsChart, VaChart },
  data() {
    return {
      lineChartData: null,
      donutChartData: null,
      lineChartFirstMonthIndex: 0,
    };
  },
  mounted() {
    this.lineChartData = getLineChartData(this.theme);
    this.donutChartData = getDonutChartData(this.theme);
  },
  watch: {
    "$themes.primary"() {
      this.lineChartData = getLineChartData(this.theme);
      this.donutChartData = getDonutChartData(this.theme);
    },

    "$themes.info"() {
      this.lineChartData = getLineChartData(this.theme);
      this.donutChartData = getDonutChartData(this.theme);
    },

    "$themes.danger"() {
      this.donutChartData = getDonutChartData(this.theme);
    },
  },
  methods: {
    deleteSection() {
      this.lineChartFirstMonthIndex += 1;
      this.lineChartData = getLineChartData(
        this.theme,
        this.lineChartFirstMonthIndex
      );
      this.$refs.lineChart.refresh();
    },
    printChart() {
      const win = window.open("", "Print", "height=600,width=800");
      win.document.write(`<br><img src='${this.donutChartDataURL}'/>`);
      // TODO: find better solution how to remove timeout
      setTimeout(() => {
        win.document.close();
        win.focus();
        win.print();
        win.close();
      }, 200);
    },
  },
  computed: {
    theme() {
      return useGlobalConfig().getGlobalConfig().colors;
    },
    donutChartDataURL() {
      return document
        .querySelector(".chart--donut canvas")
        .toDataURL("image/png");
    },
  },
};
</script>

<style scoped>
.chart {
  height: 400px;
}
.text-right {
  text-align: right;
}
</style>
