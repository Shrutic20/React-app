import React from 'react';
import { Pie } from 'react-chartjs-2';


const data = {
  labels: ['Red', 'Blue', 'Yellow'],
  datasets: [
    {
      data: [300, 50, 100],
      backgroundColor: ['#FF6384', '#36A2EB', '#FFCE56'],
      hoverBackgroundColor: ['#FF6384', '#36A2EB', '#FFCE56'],
    },
  ],
};

const PieChart = () => {
  return (
    <div>
      <Pie data={data} />
    </div>
  );
};

const options = {
  maintainAspectRatio: false, // To adjust chart size according to container
  legend: {
    display: true,
    position: 'right',
  },
};

const PieChart = () => {
  return (
    <div>
      <Pie data={data} options={options} />
    </div>
  );
};

import React from 'react';
import { Pie } from 'react-chartjs-2';

const data = {
  labels: ['Red', 'Blue', 'Yellow'],
  datasets: [
    {
      data: [300, 50, 100],
      backgroundColor: ['#FF6384', '#36A2EB', '#FFCE56'],
      hoverBackgroundColor: ['#FF6384', '#36A2EB', '#FFCE56'],
    },
  ],
};

const options = {
  maintainAspectRatio: false,
  legend: {
    display: true,
    position: 'right',
  },
};

const PieChart = () => {
  return (
    <div>
      <Pie data={data} options={options} />
    </div>
  );
};

export default PieChart;
