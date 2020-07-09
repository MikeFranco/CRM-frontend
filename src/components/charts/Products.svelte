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
              "rgba(255, 99, 132, 0.8)",
              "rgba(54, 162, 235, 0.8)",
              "rgba(255, 206, 86, 0.8)",
              "rgba(153, 102, 255, 0.5)",
              "rgba(75, 192, 192, 0.5)",
              "rgba(255, 159, 64, 0.5)"
            ],
            borderColor: [
              "rgba(255, 99, 132, 1)",
              "rgba(54, 162, 235, 1)",
              "rgba(255, 206, 86, 1)",
              "rgba(153, 102, 255, 1)",
              "rgba(75, 192, 192, 1)",
              "rgba(255, 159, 64, 1)"
            ],
            borderWidth: 1
          }
        ],
        labels
      },
      option: {
        responsive: true,
        legend: {
          display: false,
          position: "bottom",
          reverse: true
        },
        rotation: 0.5 * Math.PI
      }
    });
  };
  onMount(createChart);
</script>

<canvas id="myChart" width="400" height="400" />
