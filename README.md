<!DOCTYPE html>
<html>
  <head>
    <title>Bar Chart Example</title>
    <style>
      #chart {
        width: 800px;
        height: 500px;
        background-color: #f5f5f5;
        border: 1px solid #ccc;
        padding: 10px;
      }
      .bar {
        width: 50px;
        height: 0;
        background-color: #0099ff;
        margin-right: 10px;
        display: inline-block;
        vertical-align: bottom;
        transition: height 0.5s ease;
      }
      .label {
        margin-top: 10px;
        text-align: center;
        font-weight: bold;
      }
    </style>
  </head>
  <body>
    <div id="chart"></div>
    <script>
      const data = [
        { company: 'LAZADA HCM', Jan: 36, Feb: 75, Mar: 134, Apr: 25 },
        { company: 'ASAHI HANOI', Jan: 6, Feb: 75, Mar: 30, Apr: 41 },
        { company: 'ASAHI HCM', Jan: 17, Feb: 23, Mar: 72, Apr: 44 },
        { company: 'MEAD JOHNSON', Jan: 86, Feb: 80, Mar: 119, Apr: 62 },
        { company: 'BAEMIN', Jan: 185, Feb: 84, Mar: 85, Apr: 120 },
        { company: 'MBAL', Jan: 33, Feb: 25, Mar: 65, Apr: 167 },
        { company: 'LAZADA HANOI', Jan: 220, Feb: 225, Mar: 64, Apr: 125 },
        { company: 'TCL', Jan: 100, Feb: 50, Mar: 100, Apr: 100 },
      ];

      const chart = document.getElementById('chart');
      data.forEach(company => {
        const companyLabel = document.createElement('div');
        companyLabel.textContent = company.company;
        companyLabel.classList.add('label');
        chart.appendChild(companyLabel);

        Object.entries(company).forEach(([key, value]) => {
          if (key !== 'company') {
            const bar = document.createElement('div');
            bar.classList.add('bar');
            bar.style.height = `${value}%`;
            chart.appendChild(bar);
          }
        });
      });
    </script>
  </body>
</html>
