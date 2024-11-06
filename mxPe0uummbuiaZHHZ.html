<html><head><base href="." /><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1">
<title>Simulador de Fundos Imobiliários</title>
<style>
:root {
  --primary: #2c3e50;
  --secondary: #34495e;
  --accent: #3498db;
  --text: #ecf0f1;
  --success: #2ecc71;
  --warning: #f1c40f;
}

body {
  font-family: 'Segoe UI', system-ui, sans-serif;
  margin: 0;
  padding: 20px;
  background: var(--primary);
  color: var(--text);
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.dashboard {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  margin-bottom: 30px;
}

.card {
  background: var(--secondary);
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  transition: transform 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
}

.fund-table {
  width: 100%;
  border-collapse: collapse;
  background: var(--secondary);
  border-radius: 10px;
  overflow: hidden;
}

.fund-table th,
.fund-table td {
  padding: 15px;
  text-align: left;
  border-bottom: 1px solid rgba(255,255,255,0.1);
}

.fund-table th {
  background: var(--accent);
  font-weight: bold;
}

.simulator {
  background: var(--secondary);
  padding: 20px;
  border-radius: 10px;
  margin-top: 30px;
}

.input-group {
  margin-bottom: 15px;
}

input, select {
  width: 100%;
  padding: 10px;
  border: none;
  border-radius: 5px;
  margin-top: 5px;
  background: var(--primary);
  color: var(--text);
}

button {
  background: var(--accent);
  color: var(--text);
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s ease;
}

button:hover {
  background: #2980b9;
}

.chart-container {
  height: 300px;
  margin: 20px 0;
}

.positive {
  color: var(--success);
}

.negative {
  color: #e74c3c;
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.02); }
  100% { transform: scale(1); }
}

.updating {
  animation: pulse 1s infinite;
}
</style>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script src="https://cdn.jsdelivr.net/npm/luxon@2.0.2/build/global/luxon.min.js"></script>
</head>
<body>
<div class="container">
  <h1>Simulador de Fundos Imobiliários</h1>
  
  <div class="dashboard">
    <div class="card">
      <h3>Patrimônio Total</h3>
      <h2 id="total-equity">R$ 0,00</h2>
    </div>
    <div class="card">
      <h3>Dividendos Mensais</h3>
      <h2 id="monthly-dividends">R$ 0,00</h2>
    </div>
    <div class="card">
      <h3>Rentabilidade Média</h3>
      <h2 id="avg-yield">0,00%</h2>
    </div>
  </div>

  <div class="card">
    <h2>Top 10 Fundos Imobiliários</h2>
    <table class="fund-table" id="funds-table">
      <thead>
        <tr>
          <th>Código</th>
          <th>Nome</th>
          <th>Preço (R$)</th>
          <th>Dividend Yield</th>
          <th>Rentabilidade 12m</th>
          <th>Valor Patrimonial</th>
        </tr>
      </thead>
      <tbody id="funds-body"></tbody>
    </table>
  </div>

  <div class="simulator">
    <h2>Simulador de Investimento</h2>
    <div class="input-group">
      <label>Selecione o Fundo:</label>
      <select id="fund-select"></select>
    </div>
    <div class="input-group">
      <label>Valor do Investimento:</label>
      <input type="number" id="investment-amount" min="0" step="100">
    </div>
    <div class="input-group">
      <label>Período (meses):</label>
      <input type="number" id="investment-period" min="1" max="360" value="12">
    </div>
    <button onclick="calculateProjection()">Simular Investimento</button>

    <div class="chart-container">
      <canvas id="projection-chart"></canvas>
    </div>
  </div>
</div>

<script>
const fundsData = [
  { code: 'HGLG11', name: 'CGHG Logística', price: 172.50, dividendYield: 0.67, yield12m: 15.2, equity: 168.45 },
  { code: 'KNRI11', name: 'Kinea Real Estate', price: 138.75, dividendYield: 0.72, yield12m: 14.8, equity: 142.30 },
  { code: 'VILG11', name: 'Vinci Logística', price: 115.20, dividendYield: 0.65, yield12m: 13.9, equity: 112.80 },
  { code: 'XPLG11', name: 'XP Log', price: 121.90, dividendYield: 0.70, yield12m: 14.5, equity: 118.60 },
  { code: 'BTLG11', name: 'BTG Logística', price: 108.45, dividendYield: 0.68, yield12m: 13.2, equity: 105.90 },
  { code: 'MALL11', name: 'Malls Brasil', price: 98.30, dividendYield: 0.75, yield12m: 12.8, equity: 96.40 },
  { code: 'VISC11', name: 'Vinci Shopping', price: 112.60, dividendYield: 0.73, yield12m: 13.5, equity: 109.80 },
  { code: 'RBRP11', name: 'RBR Properties', price: 85.40, dividendYield: 0.69, yield12m: 11.9, equity: 83.70 },
  { code: 'PVBI11', name: 'VBI Prime', price: 94.80, dividendYield: 0.71, yield12m: 12.4, equity: 92.50 },
  { code: 'RECT11', name: 'REC Recebiveis', price: 102.30, dividendYield: 0.74, yield12m: 13.7, equity: 99.90 }
];

let projectionChart = null;

function updateFundsTable() {
  const tbody = document.getElementById('funds-body');
  tbody.innerHTML = '';
  
  fundsData.forEach(fund => {
    const row = document.createElement('tr');
    row.innerHTML = `
      <td>${fund.code}</td>
      <td>${fund.name}</td>
      <td>R$ ${fund.price.toFixed(2)}</td>
      <td>${(fund.dividendYield * 100).toFixed(2)}%</td>
      <td class="${fund.yield12m >= 0 ? 'positive' : 'negative'}">${fund.yield12m.toFixed(2)}%</td>
      <td>R$ ${fund.equity.toFixed(2)}</td>
    `;
    tbody.appendChild(row);
  });
}

function updateFundSelect() {
  const select = document.getElementById('fund-select');
  select.innerHTML = '';
  
  fundsData.forEach(fund => {
    const option = document.createElement('option');
    option.value = fund.code;
    option.textContent = `${fund.code} - ${fund.name}`;
    select.appendChild(option);
  });
}

function calculateProjection() {
  const fundCode = document.getElementById('fund-select').value;
  const amount = parseFloat(document.getElementById('investment-amount').value);
  const period = parseInt(document.getElementById('investment-period').value);
  
  const fund = fundsData.find(f => f.code === fundCode);
  if (!fund || isNaN(amount) || isNaN(period)) return;
  
  const monthlyDividend = (fund.price * fund.dividendYield) / 12;
  const quotas = Math.floor(amount / fund.price);
  const labels = [];
  const projectedValue = [];
  const projectedDividends = [];
  
  let totalValue = quotas * fund.price;
  let accumulatedDividends = 0;
  
  for (let i = 0; i <= period; i++) {
    labels.push(`Mês ${i}`);
    projectedValue.push(totalValue);
    projectedDividends.push(accumulatedDividends);
    
    accumulatedDividends += quotas * monthlyDividend;
    totalValue = quotas * fund.price * (1 + (fund.yield12m / 100 / 12));
  }
  
  if (projectionChart) {
    projectionChart.destroy();
  }
  
  const ctx = document.getElementById('projection-chart').getContext('2d');
  projectionChart = new Chart(ctx, {
    type: 'line',
    data: {
      labels: labels,
      datasets: [
        {
          label: 'Valor do Patrimônio',
          data: projectedValue,
          borderColor: '#3498db',
          fill: false
        },
        {
          label: 'Dividendos Acumulados',
          data: projectedDividends,
          borderColor: '#2ecc71',
          fill: false
        }
      ]
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      scales: {
        y: {
          beginAtZero: true,
          ticks: {
            callback: value => `R$ ${value.toFixed(2)}`
          }
        }
      }
    }
  });
}

// Simulação de atualização automática dos preços
function simulateMarketUpdates() {
  setInterval(() => {
    fundsData.forEach(fund => {
      const variation = (Math.random() - 0.5) * 2;
      fund.price = Math.max(fund.price * (1 + variation/100), 1);
      fund.dividendYield *= (1 + (Math.random() - 0.5) / 100);
    });
    updateFundsTable();
    document.querySelector('.fund-table').classList.add('updating');
    setTimeout(() => {
      document.querySelector('.fund-table').classList.remove('updating');
    }, 500);
  }, 5000);
}

// Inicialização
document.addEventListener('DOMContentLoaded', () => {
  updateFundsTable();
  updateFundSelect();
  simulateMarketUpdates();
});
</script>
</body></html>
