// src/components/BarChart.js
import React from 'react';
import { Bar } from 'react-chartjs-2';

const BarChart = () => {
  const data = {
    labels: ['Employee 1', 'Employee 2', 'Employee 3', 'Employee 4', 'Employee 5'],
    datasets: [
      {
        label: 'Productivity',
        data: [65, 59, 80, 81, 56],
        backgroundColor: 'rgba(75,192,192,1)',
        borderColor: 'rgba(0,0,0,1)',
        borderWidth: 1,
      },
    ],
  };

  const options = {
    scales: {
      y: {
        beginAtZero: true,
      },
    },
  };

  return <Bar data={data} options={options} />;
};

export default BarChart;




// src/components/TeamPieChart.js
import React from 'react';
import { Pie } from 'react-chartjs-2';

const TeamPieChart = () => {
  const data = {
    labels: ['Team A', 'Team B', 'Team C'],
    datasets: [
      {
        data: [30, 25, 45],
        backgroundColor: ['rgba(255, 99, 132, 0.6)', 'rgba(54, 162, 235, 0.6)', 'rgba(255, 206, 86, 0.6)'],
      },
    ],
  };

  return <Pie data={data} />;
};

export default TeamPieChart;




// src/components/IndividualPieChart.js
import React from 'react';
import { Pie } from 'react-chartjs-2';

const IndividualPieChart = () => {
  const data = {
    labels: ['Productive', 'Non-Productive'],
    datasets: [
      {
        data: [80, 20],
        backgroundColor: ['rgba(75, 192, 192, 0.6)', 'rgba(255, 99, 132, 0.6)'],
      },
    ],
  };

  return <Pie data={data} />;
};

export default IndividualPieChart;



// src/components/Dashboard.js
import React, { useState } from 'react';
import BarChart from './BarChart';
import TeamPieChart from './TeamPieChart';
import IndividualPieChart from './IndividualPieChart';

const Dashboard = () => {
  const [selectedOption, setSelectedOption] = useState('all');

  const handleOptionClick = (option) => {
    setSelectedOption(option);
  };

  return (
    <div style={{ display: 'flex', height: '100vh' }}>
      {/* Left Navigation Bar */}
      <div style={{ width: '200px', backgroundColor: '#f0f0f0', padding: '20px' }}>
        <button onClick={() => handleOptionClick('all')}>All</button>
        <button onClick={() => handleOptionClick('team')}>Team</button>
        <button onClick={() => handleOptionClick('individual')}>Individual</button>
      </div>

      {/* Display Chart based on selected option */}
      <div style={{ flex: 1, padding: '20px' }}>
        {selectedOption === 'all' && <BarChart />}
        {selectedOption === 'team' && <TeamPieChart />}
        {selectedOption === 'individual' && <IndividualPieChart />}
      </div>
    </div>
  );
};

export default Dashboard;



// src/App.js
import React from 'react';
import Dashboard from './components/Dashboard';

function App() {
  return (
    <div>
      <h1>Dashboard with Charts</h1>
      <Dashboard />
    </div>
  );
}

export default App;
