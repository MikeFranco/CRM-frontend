<script>
  import { onMount } from "svelte";
  export let data;
  export let labels;

  const createChart = () => {
    var ctx = document.getElementById("myChart");
    var myChart = new Chart(ctx, {
      type: "pie",
      data: {
        datasets: [
          {
            data,
            backgroundColor: [
              "rgba(255, 0, 0, 0.8)",
              "rgba(128, 0, 0, 0.8)",
              "rgba(255, 255, 0, 0.8)",
              "rgba(128, 128, 0, 0.8)",
              "rgba(0, 255, 0, 0.8)",
              "rgba(0, 128, 0, 0.8)",
              "rgba(0, 255, 255, 0.8)",
              "rgba(0, 128, 128, 0.8)",
              "rgba(0, 0, 255, 0.8)",
              "rgba(0, 0, 128, 0.8)",
              "rgba(255, 0, 255, 0.8)",
              "rgba(128, 0, 128, 0.8)",
              "rgba(255, 255, 255, 0.8)",
              "rgba(192, 192, 192, 0.8)",
              "rgba(128, 128, 128, 0.8",
              "rgba(0, 0, 0, 0.8)",
            ],
            borderColor: [
              "rgb(255, 255, 255)",
              "rgb(192, 192, 192)",
              "rgb(128, 128, 128)",
              "rgb(0, 0, 0)",
              "rgb(255, 0, 0)",
              "rgb(128, 0, 0)",
              "rgb(255, 255, 0)",
              "rgb(128, 128, 0)",
              "rgb(0, 255, 0)",
              "rgb(0, 128, 0)",
              "rgb(0, 255, 255)",
              "rgb(0, 128, 128)",
              "rgb(0, 0, 255)",
              "rgb(0, 0, 128)",
              "rgb(255, 0, 255)",
              "rgb(128, 0, 128)"
            ],
            borderWidth: 1
          }
        ],
        labels: labels
      },
      option: {
        responsive: true,
        legend: {
          display: false,
          position: 'bottom',
          reverse: true
        },
        rotation: 0.5 * Math.PI
      }
    });
  };
  onMount(createChart);
</script>

<canvas id="myChart" width="100" height="100" />
