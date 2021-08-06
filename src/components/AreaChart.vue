<script>
import { Line } from "vue-chartjs";

export default {
  extends: Line,
  data() {
    return {
      gradient: null,
      gradient2: null
    };
  },
  mounted() {
    this.gradient = this.$refs.canvas
      .getContext("2d")
      .createLinearGradient(0, 0, 0, 450);
    this.gradient2 = this.$refs.canvas
      .getContext("2d")
      .createLinearGradient(0, 0, 0, 450);

    this.gradient.addColorStop(0, "rgba(250, 192, 50, 0.5)");
    this.gradient.addColorStop(0.5, "rgba(250, 192, 50, 0.25)");
    this.gradient.addColorStop(1, "rgba(250, 192, 50, 0)");

    this.gradient2.addColorStop(0, "rgba(51, 108, 251, 0.5)");
    this.gradient2.addColorStop(0.5, "rgba(51, 108, 251, 0.25)");
    this.gradient2.addColorStop(1, "rgba(51, 108, 251, 0)");

    this.renderChart(
      {
        labels: [
          "January",
          "February",
          "March",
          "April",
          "May",
          "June",
          "July"
        ],
        datasets: [
          {
            label: "Patients 2019",
            borderColor: "#FAC032",
            pointBackgroundColor: "#FCDF98",
            borderWidth: 1,
            pointBorderColor: "white",
            backgroundColor: this.gradient,
            data: [40, 39, 10, 40, 39, 80, 40]
          },
          {
            label: "Patients 2020",
            borderColor: "#336CFB",
            pointBackgroundColor: "#A9C1FD",
            pointBorderColor: "white",
            borderWidth: 1,
            backgroundColor: this.gradient2,
            data: [60, 55, 32, 10, 2, 12, 53]
          }
        ]
      },
      { responsive: true, maintainAspectRatio: false }
    );
  }
};
</script>
