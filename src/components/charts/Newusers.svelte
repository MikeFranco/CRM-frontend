<script>
  import { onMount } from "svelte";
  export let datan;
  export let labels;
  const createChart = () => {
    var ctx = document.getElementById("myChart");
    var myChart = new Chart(ctx, {
      type: "pie",
      data: {
        datasets: [
          {
            data: datan,
            backgroundColor: ["rgba(255, 99, 132, 0.8)", "rgba(54, 162, 235, 0.8)"],
            borderColor: ["rgba(255, 99, 132, 1)", "rgba(54, 162, 235, 1)"],
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

<canvas id="myChart" width="400" height="400" />
