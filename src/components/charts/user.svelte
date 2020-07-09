<script>
  import { onMount } from "svelte";
  export let datac;
  export let labels;
  const createChart = () => {
    var ctx = document.getElementById("myChart1");
    var myChart = new Chart(ctx, {
      type: "pie",
      data: {
        datasets: [
          {
            data: datac,
            backgroundColor: [
              "rgba(255, 99, 132, 1)",
              "rgba(54, 162, 235, 1)",
              "rgba(255, 206, 86, 0.5)",
              "rgba(75, 192, 192, 0.5)",
              "rgba(153, 102, 255, 0.5)",
              "rgba(255, 159, 64, 0.5)"
            ],
            borderColor: [
              "rgba(255, 99, 132, 1)",
              "rgba(54, 162, 235, 1)",
              "rgba(255, 206, 86, 1)",
              "rgba(75, 192, 192, 1)",
              "rgba(153, 102, 255, 1)",
              "rgba(255, 159, 64, 1)"
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
          position: "bottom",
          reverse: true
        },
        rotation: 0.5 * Math.PI
      }
    });
  };
  onMount(createChart);
</script>

<canvas id="myChart1" width="400" height="400" />
