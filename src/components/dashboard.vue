<script>
import Chart from 'chart.js/auto';

export default {
  name: 'Dashboard',
  data() {
    return {
      selectedYear: 2024,
      selectedMonth: 0,
      months: ['Januari', 'Februari', 'Maret', 'April', 'Mei', 'Juni', 'Juli', 'Agustus', 'September', 'Oktober', 'November', 'Desember'],
      
      // Data terstruktur berdasarkan tahun dan bulan
      dataByYearMonth: {
        2022: {
          0: { // Januari
            summaryCards: [
              { amount: 12000000000, label: 'KONSENSI AERO' },
              { amount: 8000000000, label: 'KONSENSI NON-AERO' },
              { amount: 5000000000, label: 'KONSENSI DIGITAL & IKLAN' },
              { amount: 3000000000, label: 'LISTRIK' }
            ],
            pendapatanTahunan: 'Rp.850.000.000.000',
            pendapatanBulanan: 'Rp.750.000.000.000',
            contributions: [
              { label: 'Aeronautika', percentage: 40 },
              { label: 'Non Aeronautika', percentage: 30 },
              { label: 'Kerjasama', percentage: 20 },
              { label: 'Lain-lain', percentage: 10 }
            ],
            mitraData: [1000000, 1500000, 250000, 400000, 1800000, 280000, 900000, 450000, 600000, 1300000],
            pieChartData: [
              { label: 'Konsesi Tenan', value: 25000000, color: 'blue' },
              { label: 'Konsesi Wrapping', value: 35000000, color: 'red' },
              { label: 'Parkir Reguler', value: 20000000, color: 'yellow' },
              { label: 'Parkir Inap', value: 15000000, color: 'green' },
              { label: 'Konsesi Ground Handling', value: 30000000, color: 'purple' },
              { label: 'Fuel Throughput', value: 40000000, color: 'orange' }
            ]
          },
          1: { // Februari
            summaryCards: [
              { amount: 13000000000, label: 'KONSENSI AERO' },
              { amount: 9000000000, label: 'KONSENSI NON-AERO' },
              { amount: 6000000000, label: 'KONSENSI DIGITAL & IKLAN' },
              { amount: 3500000000, label: 'LISTRIK' }
            ],
            pendapatanTahunan: 'Rp.900.000.000.000',
            pendapatanBulanan: 'Rp.800.000.000.000',
            contributions: [
              { label: 'Aeronautika', percentage: 38 },
              { label: 'Non Aeronautika', percentage: 28 },
              { label: 'Kerjasama', percentage: 22 },
              { label: 'Lain-lain', percentage: 12 }
            ],
            mitraData: [1100000, 1600000, 300000, 450000, 1900000, 320000, 950000, 500000, 650000, 1400000],
            pieChartData: [
              { label: 'Konsesi Tenan', value: 28000000, color: 'blue' },
              { label: 'Konsesi Wrapping', value: 38000000, color: 'red' },
              { label: 'Parkir Reguler', value: 22000000, color: 'yellow' },
              { label: 'Parkir Inap', value: 18000000, color: 'green' },
              { label: 'Konsesi Ground Handling', value: 32000000, color: 'purple' },
              { label: 'Fuel Throughput', value: 42000000, color: 'orange' }
            ]
          }
        },
        2023: {
          0: { // Januari
            summaryCards: [
              { amount: 14000000000, label: 'KONSENSI AERO' },
              { amount: 10000000000, label: 'KONSENSI NON-AERO' },
              { amount: 7000000000, label: 'KONSENSI DIGITAL & IKLAN' },
              { amount: 4000000000, label: 'LISTRIK' }
            ],
            pendapatanTahunan: 'Rp.950.000.000.000',
            pendapatanBulanan: 'Rp.850.000.000.000',
            contributions: [
              { label: 'Aeronautika', percentage: 35 },
              { label: 'Non Aeronautika', percentage: 30 },
              { label: 'Kerjasama', percentage: 25 },
              { label: 'Lain-lain', percentage: 10 }
            ],
            mitraData: [1150000, 1700000, 350000, 500000, 1950000, 350000, 1000000, 550000, 700000, 1450000],
            pieChartData: [
              { label: 'Konsesi Tenan', value: 30000000, color: 'blue' },
              { label: 'Konsesi Wrapping', value: 45000000, color: 'red' },
              { label: 'Parkir Reguler', value: 25000000, color: 'yellow' },
              { label: 'Parkir Inap', value: 20000000, color: 'green' },
              { label: 'Konsesi Ground Handling', value: 35000000, color: 'purple' },
              { label: 'Fuel Throughput', value: 50000000, color: 'orange' }
            ]
          },
          1: { // Februari
            summaryCards: [
              { amount: 15500000000, label: 'KONSENSI AERO' },
              { amount: 11000000000, label: 'KONSENSI NON-AERO' },
              { amount: 8000000000, label: 'KONSENSI DIGITAL & IKLAN' },
              { amount: 4500000000, label: 'LISTRIK' }
            ],
            pendapatanTahunan: 'Rp.1.000.000.000.000',
            pendapatanBulanan: 'Rp.900.000.000.000',
            contributions: [
              { label: 'Aeronautika', percentage: 37 },
              { label: 'Non Aeronautika', percentage: 28 },
              { label: 'Kerjasama', percentage: 24 },
              { label: 'Lain-lain', percentage: 11 }
            ],
            mitraData: [1250000, 1800000, 400000, 550000, 2100000, 380000, 1100000, 600000, 750000, 1500000],
            pieChartData: [
              { label: 'Konsesi Tenan', value: 32000000, color: 'blue' },
              { label: 'Konsesi Wrapping', value: 48000000, color: 'red' },
              { label: 'Parkir Reguler', value: 28000000, color: 'yellow' },
              { label: 'Parkir Inap', value: 22000000, color: 'green' },
              { label: 'Konsesi Ground Handling', value: 38000000, color: 'purple' },
              { label: 'Fuel Throughput', value: 52000000, color: 'orange' }
            ]
          }
        },
        2024: {
          0: { // Januari (data default yang sudah ada)
            summaryCards: [
              { amount: 15000000000, label: 'KONSENSI AERO' },
              { amount: 15000000000, label: 'KONSENSI NON-AERO' },
              { amount: 15000000000, label: 'KONSENSI DIGITAL & IKLAN' },
              { amount: 15000000000, label: 'LISTRIK' }
            ],
            pendapatanTahunan: 'Rp.999.999.999.999',
            pendapatanBulanan: 'Rp.999.999.999.999',
            contributions: [
              { label: 'Aeronautika', percentage: 36 },
              { label: 'Non Aeronautika', percentage: 25 },
              { label: 'Kerjasama', percentage: 23 },
              { label: 'Lain-lain', percentage: 16 }
            ],
            mitraData: [1200000, 1900000, 300000, 500000, 2000000, 300000, 1000000, 500000, 700000, 1500000],
            pieChartData: [
              { label: 'Konsesi Tenan', value: 40000000, color: 'blue' },
              { label: 'Konsesi Wrapping', value: 40000000, color: 'red' },
              { label: 'Parkir Reguler', value: 40000000, color: 'yellow' },
              { label: 'Parkir Inap', value: 40000000, color: 'green' },
              { label: 'Konsesi Ground Handling', value: 40000000, color: 'purple' },
              { label: 'Fuel Throughput', value: 40000000, color: 'orange' }
            ]
          },
          1: { // Februari
            summaryCards: [
              { amount: 16000000000, label: 'KONSENSI AERO' },
              { amount: 16500000000, label: 'KONSENSI NON-AERO' },
              { amount: 14000000000, label: 'KONSENSI DIGITAL & IKLAN' },
              { amount: 13000000000, label: 'LISTRIK' }
            ],
            pendapatanTahunan: 'Rp.1.200.000.000.000',
            pendapatanBulanan: 'Rp.1.100.000.000.000',
            contributions: [
              { label: 'Aeronautika', percentage: 38 },
              { label: 'Non Aeronautika', percentage: 27 },
              { label: 'Kerjasama', percentage: 22 },
              { label: 'Lain-lain', percentage: 13 }
            ],
            mitraData: [1300000, 2000000, 350000, 550000, 2200000, 350000, 1100000, 550000, 750000, 1600000],
            pieChartData: [
              { label: 'Konsesi Tenan', value: 45000000, color: 'blue' },
              { label: 'Konsesi Wrapping', value: 35000000, color: 'red' },
              { label: 'Parkir Reguler', value: 30000000, color: 'yellow' },
              { label: 'Parkir Inap', value: 38000000, color: 'green' },
              { label: 'Konsesi Ground Handling', value: 42000000, color: 'purple' },
              { label: 'Fuel Throughput', value: 50000000, color: 'orange' }
            ]
          }
        }
      },
      
      mitraLabels: ['AngkasaPura', 'AirNavIndonesia', 'Citilink', 'PelitaAir', 'BatikAir', 'LionAir', 'GarudaIndonesia', 'GlobalSkyAviasi', 'Pertamina', 'Injourney'],
      chart: null,
      isChartReady: false
    };
  },
  
  computed: {
    // Dynamic year range computation
    years() {
      const currentYear = new Date().getFullYear();
      const startYear = 2022; // Keep data from 2022 onwards
      const futureYears = 3; // Show 3 years into the future
      const endYear = currentYear + futureYears;
      
      const yearArray = [];
      for (let year = startYear; year <= endYear; year++) {
        yearArray.push(year);
      }
      
      return yearArray;
    },
    
    // Computed property untuk mendapatkan data sesuai tahun dan bulan yang dipilih
    currentData() {
      const yearData = this.dataByYearMonth[this.selectedYear];
      if (!yearData) {
        return this.getDefaultData();
      }
      
      const monthData = yearData[this.selectedMonth];
      if (!monthData) {
        return this.getDefaultData();
      }
      
      return monthData;
    },
    
    summaryCards() {
      return this.currentData.summaryCards;
    },
    
    pendapatanTahunan() {
      return this.currentData.pendapatanTahunan;
    },
    
    pendapatanBulanan() {
      return this.currentData.pendapatanBulanan;
    },
    
    contributions() {
      return this.currentData.contributions;
    },
    
    mitraData() {
      return this.currentData.mitraData;
    },

    pieChartData() {
      return this.currentData.pieChartData;
    },

    // Computed property untuk mendapatkan persentase pie chart
    pieChartPercentages() {
      const total = this.pieChartData.reduce((sum, item) => sum + item.value, 0);
      let cumulativePercentage = 0;
      
      return this.pieChartData.map(item => {
        const percentage = (item.value / total) * 100;
        const result = {
          ...item,
          percentage,
          cumulativePercentage
        };
        cumulativePercentage += percentage;
        return result;
      });
    },

    // Computed property untuk CSS gradient pie chart
    pieChartGradient() {
      let gradient = 'conic-gradient(from 0deg,';
      let currentPercentage = 0;
      
      this.pieChartPercentages.forEach((item, index) => {
        if (index > 0) {
          gradient += `, ${item.color} ${currentPercentage}%`;
        } else {
          gradient += ` ${item.color} 0%`;
        }
        currentPercentage += item.percentage;
        gradient += `, ${item.color} ${currentPercentage}%`;
      });
      
      gradient += ')';
      return gradient;
    }
  },
  
  watch: {
    // Watch untuk memperbarui chart ketika tahun atau bulan berubah
    selectedYear() {
      this.updateChartData();
    },
    selectedMonth() {
      this.updateChartData();
    }
  },
  
  methods: {
    formatCurrency(value) {
      return new Intl.NumberFormat('id-ID', {
        style: 'currency',
        currency: 'IDR',
        minimumFractionDigits: 0
      }).format(value);
    },
    
    getDefaultData() {
      // Default data jika tidak ada data untuk tahun/bulan yang dipilih
      return {
        summaryCards: [
          { amount: 0, label: 'KONSENSI AERO' },
          { amount: 0, label: 'KONSENSI NON-AERO' },
          { amount: 0, label: 'KONSENSI DIGITAL & IKLAN' },
          { amount: 0, label: 'LISTRIK' }
        ],
        pendapatanTahunan: 'Rp.0',
        pendapatanBulanan: 'Rp.0',
        contributions: [
          { label: 'Aeronautika', percentage: 0 },
          { label: 'Non Aeronautika', percentage: 0 },
          { label: 'Kerjasama', percentage: 0 },
          { label: 'Lain-lain', percentage: 0 }
        ],
        mitraData: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
        pieChartData: [
          { label: 'Konsesi Tenan', value: 0, color: 'blue' },
          { label: 'Konsesi Wrapping', value: 0, color: 'red' },
          { label: 'Parkir Reguler', value: 0, color: 'yellow' },
          { label: 'Parkir Inap', value: 0, color: 'green' },
          { label: 'Konsesi Ground Handling', value: 0, color: 'purple' },
          { label: 'Fuel Throughput', value: 0, color: 'orange' }
        ]
      };
    },
    
    // Method to initialize selected year based on current year
    initializeSelectedYear() {
      const currentYear = new Date().getFullYear();
      // Set to current year if it exists in years array, otherwise keep default
      if (this.years.includes(currentYear)) {
        this.selectedYear = currentYear;
      } else {
        // If current year is not in range, set to the closest available year
        this.selectedYear = this.years.find(year => year >= currentYear) || this.years[this.years.length - 1];
      }
    },
    
    waitForElement(selector, timeout = 5000) {
      return new Promise((resolve, reject) => {
        const element = document.querySelector(selector);
        if (element) {
          resolve(element);
          return;
        }

        const observer = new MutationObserver(() => {
          const element = document.querySelector(selector);
          if (element) {
            observer.disconnect();
            resolve(element);
          }
        });

        observer.observe(document.body, {
          childList: true,
          subtree: true
        });

        setTimeout(() => {
          observer.disconnect();
          reject(new Error(`Element ${selector} not found within ${timeout}ms`));
        }, timeout);
      });
    },
    
    async createChart() {
      try {
        // Wait for the canvas element to be available
        const ctx = await this.waitForElement('#myChart');
        
        // Destroy existing chart if it exists
        this.destroyChart();
        
        // Verify canvas context is available
        if (!ctx || !ctx.getContext) {
          console.warn('Canvas element not properly initialized');
          return;
        }

        const canvasContext = ctx.getContext('2d');
        if (!canvasContext) {
          console.warn('Canvas 2D context not available');
          return;
        }
        
        this.chart = new Chart(canvasContext, {
          type: 'bar',
          data: {
            labels: this.mitraLabels,
            datasets: [{
              label: `Pendapatan ${this.months[this.selectedMonth]} ${this.selectedYear}`,
              data: [...this.mitraData], // Create a copy to avoid reference issues
              backgroundColor: '#4e73df',
              borderColor: '#4e73df',
              borderWidth: 1
            }]
          },
          options: {
            responsive: true,
            maintainAspectRatio: false,
            animation: {
              duration: 0 // Disable animations to prevent timing issues
            },
            plugins: {
              legend: {
                display: true,
                position: 'top'
              },
              tooltip: {
                callbacks: {
                  label: function(context) {
                    const val = context.parsed.y;
                    return `${context.dataset.label}: Rp.${val.toLocaleString('id-ID')}`;
                  }
                }
              }
            },
            scales: {
              y: {
                beginAtZero: true,
                ticks: {
                  callback: function(value) {
                    return 'Rp.' + value.toLocaleString('id-ID');
                  }
                }
              },
              x: {
                ticks: {
                  maxRotation: 45,
                  minRotation: 0
                }
              }
            }
          }
        });
        
        this.isChartReady = true;
        console.log('Chart created successfully');
      } catch (error) {
        console.error('Error creating chart:', error);
        this.isChartReady = false;
      }
    },

    destroyChart() {
      if (this.chart) {
        try {
          this.chart.destroy();
          this.chart = null;
          this.isChartReady = false;
        } catch (error) {
          console.error('Error destroying chart:', error);
          this.chart = null;
          this.isChartReady = false;
        }
      }
    },
    
    updateChartData() {
      if (!this.isChartReady || !this.chart) {
        console.log('Chart not ready, attempting to create...');
        this.createChart();
        return;
      }

      try {
        // Safely update chart data
        if (this.chart.data && this.chart.data.datasets && this.chart.data.datasets[0]) {
          this.chart.data.datasets[0].data = [...this.mitraData];
          this.chart.data.datasets[0].label = `Pendapatan ${this.months[this.selectedMonth]} ${this.selectedYear}`;
          this.chart.update('none'); // Update without animation
        }
      } catch (error) {
        console.error('Error updating chart:', error);
        // If update fails, recreate the chart
        this.createChart();
      }
    }
  },
  
  mounted() {
    // Initialize selected year based on current year
    this.initializeSelectedYear();
    
    // Use requestAnimationFrame to ensure DOM is fully rendered
    this.$nextTick(() => {
      requestAnimationFrame(() => {
        setTimeout(() => {
          this.createChart();
        }, 200); // Increased timeout for better reliability
      });
    });
  },
  
  beforeUnmount() {
    this.destroyChart();
  }
};
</script>

<template>
  <div class="dashboard-container">
    <!-- Header Section -->
    <div class="header-section">
      <div class="logo-container">
        <span><img src="../assets/img/logos/logohaluoleo.png" alt="BLU Haluoleo Airport" class="logo"></span>
      </div>
      
      <div class="dashboard-title">
        <div class="title-text">
          <h1>DASHBOARD</h1>
          <h2>CAPAIAN KINERJA PENAGIHAN</h2>
        </div>
      </div>

      <div class="filter-controls">
        <div class="filter-item">
          <label>TAHUN</label>
          <select v-model="selectedYear" class="filter-select">
            <option v-for="year in years" :key="year" :value="year">{{ year }}</option>
          </select>
        </div>
        <div class="filter-item">
          <label>BULAN</label>
          <select v-model="selectedMonth" class="filter-select">
            <option v-for="(month, index) in months" :key="index" :value="index">{{ month }}</option>
          </select>
        </div>
      </div>
    </div>

    <!-- Summary Cards -->
    <div class="summary-cards">
      <div class="summary-card" v-for="(card, index) in summaryCards" :key="index">
        <h3>TOTAL TAGIHAN</h3>
        <p class="amount">{{ formatCurrency(card.amount) }}</p>
        <span class="label">{{ card.label }}</span>
      </div>
    </div>

    <!-- Main Content -->
    <div class="main-content">
      <!-- Sidebar -->
      <div class="sidebar">
        <div class="info-card teal-card">
          <h3>Pendapatan / Tahun</h3>
          <p class="value">{{ pendapatanTahunan }}</p>
        </div>

        <div class="info-card blue-card">
          <h3>Pendapatan / Bulanan</h3>
          <p class="value">{{ pendapatanBulanan }}</p>
        </div>

        <div class="contribution-card">
          <h3>Kontribusi Nilai Pendapatan</h3>
          <div class="contribution-list">
            <div v-for="(item, index) in contributions" :key="index" class="contribution-item">
              <span>{{ item.label }}</span>
              <span>{{ item.percentage }}%</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Charts -->
      <div class="charts-section">
        <div class="chart-card">
          <h3>Bulanan</h3>
          <figure class="charts">
            <div class="pie" :style="{ backgroundImage: pieChartGradient }"></div>
            <figcaption class="legends">
              <span v-for="(item, index) in pieChartData" :key="index" :data-color="item.color">
                {{ item.label }} = {{ formatCurrency(item.value) }}
              </span>
            </figcaption>
          </figure>
        </div>
        <div class="chart-card">
          <h3>Jenis Pendapatan</h3>
          <div class="chart-placeholder">Chart Pendapatan</div>
        </div>
        <div class="chart-card highlight">
          <h3>10 Mitra Pendapatan Terbesar</h3>
          <div class="BarChart">
            <canvas id="myChart"></canvas>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.dashboard-container {
  min-height: 100vh;
  background: #f5f7fa;
}

.header-section {
  background: #3700ac;
  color: white;
  padding: 2rem;
  display: flex ; 
  align-items: center;
  gap: 2rem;
}

.logo {
  height: 100px;
  width: auto;
}

.dashboard-title {
  display: flex;
  align-items: center;
  gap: 1rem;
  flex: 1;
}

.title-text h1 {
  font-size: 3rem;
  margin: 0;
  color: #ffe23c;
  text-shadow: 2px 2px #000000;
}

.title-text h2 {
  font-size: 1.5rem;
  margin: 0;
  opacity: 0.9;
  color: #ffe342;
  text-shadow: 2px 2px #000000;
}

.filter-controls {
  display: flex;
  gap: 1rem;
}

.filter-item label {
  display: block;
  color: black;
  margin-bottom: 0.5rem;
  font-size: 1.5rem;
}

.filter-select {
  margin-right: 3rem;
  padding: 1rem;
  padding-right: 2rem;
  text-align: left;
  border-radius: 4px;
  border: none;
  background: white;
  color: black;
}

.summary-cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1.5rem;
  padding: 2rem;
  margin-top: -2rem;
}

.summary-card {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  border-style: groove;
  box-shadow: 0 2px 15px rgba(0,0,0,0.1);
  text-align: center;
}

.summary-card h3 {
  font-size: 0.875rem;
  color: #666;
  margin: 0;
}

.summary-card .amount {
  font-size: 1.75rem;
  font-weight: bold;
  color: #0066ff;
  margin: 0.5rem 0;
}

.summary-card .label {
  font-size: 0.875rem;
  color: #000000;
}

.main-content {
  display: grid;
  grid-template-columns: 300px 1fr;
  gap: 2rem;
  padding: 0 2rem 2rem;
}

.sidebar {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.info-card {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.teal-card {
  border-top: 4px solid #17a2b8;
}

.blue-card {
  border-top: 4px solid #4e73df;
}

.info-card h3 {
  font-size: 1rem;
  margin: 0 0 1rem 0;
}

.info-card .value {
  font-size: 1.5rem;
  font-weight: bold;
}

.contribution-card {
  background: #ffc107;
  padding: 1.5rem;
  border-radius: 8px;
}

.contribution-card h3 {
  margin: 0 0 1rem 0;
}

.contribution-item {
  display: flex;
  justify-content: space-between;
  margin-bottom: 0.5rem;
}

.charts-section {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.chart-card {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.chart-card.highlight {
  width: 1125px;
  grid-column: span 2;
  border: 2px solid #ffd700;
}

.BarChart {
  height: 400px;
  position: relative;
}

.BarChart canvas {
  max-height: 400px;
}

.chart-card h3 {
  margin: 0 0 1rem 0;
  font-size: 1rem;
}

.chart-placeholder {
  height: 200px;
  background: #f0f0f0;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #999;
  border-radius: 4px;
}

.charts {
  display: flex;
  place-content: center;
  flex-flow: wrap;
  gap: 2rem;
}

.pie {
  flex: 0 0 225px;
  max-width: 225px;
  aspect-ratio: 1;
  border-radius: 50%;
  transition: background-image 0.3s ease;
}

.legends {
  margin-block-end: 2rem;
  font-size: 0.9rem;
  flex-basis: 100%;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.legends span {
  position: relative;
  padding-inline-start: 1.25rem;
}

.legends span::before {
  position: absolute;
  top: 0.4rem;
  left: 0;
  content: '';
  width: 0.8rem;
  aspect-ratio: 1;
  border-radius: 50%;
}

.legends span[data-color="blue"]::before {
  background-color: blue;
}

.legends span[data-color="red"]::before {
  background-color: red;
}

.legends span[data-color="yellow"]::before {
  background-color: yellow;
}

.legends span[data-color="green"]::before {
  background-color: green;
}

.legends span[data-color="purple"]::before {
  background-color: purple;
}

.legends span[data-color="orange"]::before {
  background-color: orange;
}

@media (max-width: 1200px) {
  .summary-cards {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .charts-section {
    grid-template-columns: 1fr;
  }
  
  .chart-card.highlight {
    grid-column: span 1;
    width: auto;
  }
}

@media (max-width: 768px) {
  .header-section {
    flex-direction: column;
    text-align: center;
  }
  
  .summary-cards {
    grid-template-columns: 1fr;
  }
  
  .main-content {
    grid-template-columns: 1fr;
  }
}
</style>