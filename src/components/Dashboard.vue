<template>
    <div class="dashboard">
        <div class="sidebar">
          <!-- Top Section -->
          <div class="top">
            <div class="logo">
              <!-- Placeholder for logo -->
              <img src="../assets/logo.png" alt="Logo" />
            </div>
          </div>
  
          <!-- Middle Section -->
          <div class="middle">
            <ul>
              <li><a href="#">Dashboard</a></li>
              <li><a href="#">Reports</a></li>
              <li><a href="#">Analytics</a></li>
              <li><a href="#">Settings</a></li>
            </ul>
          </div>
  
          <!-- Bottom Section -->
          <div class="bottom">
            <p>Need Help?</p>
            <a href="#">Contact Support</a>
          </div>
        </div>
        <div class="mainbody">
            <div class="welcome">
                <h2>Welcome back</h2>
            </div>
            <div class="someanalytics">
                <div class="analyticcard">
                    <h3>89,935</h3>
                    <span>Total Users</span>
                </div>
                <div class="analyticcard">
                    <h3>89,935</h3>
                    <span>Total Users</span>
                </div>
                <div class="analyticcard">
                    <h3>89,935</h3>
                    <span>Total Users</span>
                </div>
                <div class="analyticcard">
                    <h3>89,935</h3>
                    <span>Total Users</span>
                </div>
            </div>
            <div class="mainchart">
                <div class="chart1">
                    <h3>Analytics</h3>
                    <canvas id="analyticsChart"></canvas>
                </div>
                <div class="chart2">
                    <h3>2nd Chart</h3>
                    <canvas id="secondaryChart"></canvas>
                    
                </div>
            </div>
            <div class="restofbody"></div>
        </div>
    </div>
  </template>
  
  <script>
  import { Chart, registerables } from "chart.js";
  export default {
    name: 'DashBoard',
    props: {
      msg: String
    },
    mounted() {
    // Register Chart.js components
    Chart.register(...registerables);

    // First Chart: Analytics
    const ctx1 = document.getElementById("analyticsChart").getContext("2d");
    new Chart(ctx1, {
      type: "line",
      data: {
        labels: ["January", "February", "March", "April", "May", "June"],
        datasets: [
          {
            label: "User Growth",
            data: [12, 19, 3, 5, 2, 3],
            borderColor: "#42b983",
            tension: 0.4,
          },
        ],
      },
      options: {
        responsive: true,
        plugins: {
          legend: {
            position: "top",
          },
          tooltip: {
            enabled: true,
          },
        },
      },
    });
    // Second Chart: 2nd Chart
    const ctx2 = document.getElementById("secondaryChart").getContext("2d");
    new Chart(ctx2, {
      type: "bar",
      data: {
        labels: ["A", "B", "C", "D", "E"],
        datasets: [
          {
            label: "Category Count",
            data: [5, 10, 15, 20, 25],
            backgroundColor: "#0F123F",
          },
        ],
      },
      options: {
        responsive: true,
        plugins: {
          legend: {
            position: "top",
          },
        },
      },
    });
  },
  }
  </script>
  
  <style scoped>

  .dashboard{
    display: flex;
  }
  /* Sidebar Styling */
  .sidebar {
    background-color: #0F123F;
    color: white;
    width: 250px;
    height: 100vh;
    display: flex;
    flex-direction: column;
    padding: 20px;
    box-sizing: border-box;
    border-top-right-radius: 20px;
    border-bottom-right-radius: 20px;
  }
  
  /* Top Section */
  .top {
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 20px;
  }
  
  .logo img {
    max-width: 100%;
    height: auto;
    display: block;
  }
  
  /* Middle Section */
  .middle {
    flex: 2;
  }
  
  .middle ul {
    list-style: none;
    padding: 0;
  }
  
  .middle li {
    margin: 15px 0;
  }
  
  .middle a {
    color: white;
    text-decoration: none;
    font-size: 16px;
    font-weight: bold;
    transition: color 0.3s ease;
  }
  
  .middle a:hover {
    color: #42b983; /* Highlight color */
  }
  
  /* Bottom Section */
  .bottom {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
  }
  
  .bottom p {
    margin: 0;
    font-size: 14px;
  }
  
  .bottom a {
    color: #42b983;
    text-decoration: none;
    font-size: 14px;
    margin-top: 5px;
  }

  .mainbody{
    margin: 0 auto;
  }

  .welcome{
    margin: 0 28px;
    justify-self: center;
  }
  .someanalytics{
    display: flex;
    margin: 0 auto;
    justify-content: center;
  }

  .analyticcard{
    border: solid 1px #e6edff;
    width: 120px;
    padding: 20px;
    border-radius: 12px;
    margin: 0 24px;
  }

  .chart1{
    width: 100%;
    
    margin: 0 auto;
  }


  .image-container{
    max-width: 100%;
  }

  .image-container img{
    width: 100%;
  }

  .image-container2{
    margin: 0 auto;
    max-width: 200px;
    max-height: 10px;
  }

  .image-container2 img{
    width: 100%;
    height: 100%;
  }
  </style>
  