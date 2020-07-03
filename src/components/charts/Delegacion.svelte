<canvas id="myChart" width="100" height="100" />
<script>
  import { onMount } from "svelte";
  export let data;
  const createChart = () => {
    var ctx = document.getElementById("myChart");
    var myChart = new Chart(ctx, {
      type: "pie",
      data: {
       
        datasets: [
          {
            data,

            backgroundColor: [
              "rgba(255, 255, 255, 0.5)",
              "rgba(192, 192, 192, 0.5)",
              "rgba(128, 128, 128, 0.5",
              "rgba(0, 0, 0, 0.5)",
              "rgba(255, 0, 0, 0.5)",
              "rgba(128, 0, 0, 0.5)",
              "rgba(255, 255, 0, 0.5)",
              "rgba(128, 128, 0, 0.5)",
              "rgba(0, 255, 0, 0.5)",
              "rgba(0, 128, 0, 0.5)",
              "rgba(0, 255, 255, 0.5)",
              "rgba(0, 128, 128, 0.5)",
              "rgba(0, 0, 255, 0.5)",
              "rgba(0, 0, 128, 0.5)",
              "rgba(255, 0, 255, 0.5)",
              "rgba(128, 0, 128, 0.5)"
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
        ]
      },
      options: {
        scales: {
          yAxes: [
            {
              ticks: {
                beginAtZero: true
              }
            }
          ]
        }
      }
    });
  };
  onMount(createChart);
</script>
