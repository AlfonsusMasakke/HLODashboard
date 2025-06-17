<template>
  <div class="dashboard-container">
    <!-- Header Section -->
    <div class="header-section">
      <div class="logo-container">
        <img src="https://via.placeholder.com/150x80?text=Logo" alt="BLU Haluoleo Airport" class="logo">
      </div>
      
      <div class="dashboard-title">
        <div class="title-icon">
          <svg width="60" height="60" viewBox="0 0 24 24" fill="white">
            <path d="M4 6h2v2H4zm0 5h2v2H4zm0 5h2v2H4zm16-8V6h-8v2h8zm0 5v-2h-8v2h8zm0 5v-2h-8v2h8z"/>
          </svg>
        </div>
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
          <h3>Jenis Layanan Terbesar</h3>
          <p class="value">{{ topService }}</p>
        </div>

        <div class="info-card blue-card">
          <h3>Kategori Tertinggi</h3>
          <p class="value">{{ topCategory }}</p>
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
          <div class="chart-placeholder">Chart Bulanan</div>
        </div>
        <div class="chart-card">
          <h3>Jenis Pendapatan</h3>
          <div class="chart-placeholder">Chart Pendapatan</div>
        </div>
        <div class="chart-card highlight">
          <h3>10 Mitra Pendapatan Terbesar</h3>
          <div class="chart-placeholder">Chart Mitra</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dashboard',
  data() {
    return {
      selectedYear: 2024,
      selectedMonth: 0,
      years: [2022, 2023, 2024],
      months: ['Januari', 'Februari', 'Maret', 'April', 'Mei', 'Juni', 'Juli', 'Agustus', 'September', 'Oktober', 'November', 'Desember'],
      summaryCards: [
        { amount: 15000000000, label: 'Target' },
        { amount: 12500000000, label: 'Realisasi' },
        { amount: 14000000000, label: 'Proyeksi' },
        { amount: 2500000000, label: 'Outstanding' }
      ],
      topService: 'Aeronautika',
      topCategory: 'Pelayanan Jasa',
      contributions: [
        { label: 'Aeronautika', percentage: 36 },
        { label: 'Non Aeronautika', percentage: 25 },
        { label: 'Kerjasama', percentage: 23 },
        { label: 'Lain-lain', percentage: 16 }
      ]
    }
  },
  methods: {
    formatCurrency(value) {
      return new Intl.NumberFormat('id-ID', {
        style: 'currency',
        currency: 'IDR',
        minimumFractionDigits: 0
      }).format(value)
    }
  }
}
</script>

<style scoped>
.dashboard-container {
  min-height: 100vh;
  background: #f5f7fa;
}

.header-section {
  background: #0066ff;
  color: white;
  padding: 2rem;
  display: flex;
  align-items: center;
  gap: 2rem;
}

.logo {
  height: 80px;
  width: auto;
}

.dashboard-title {
  display: flex;
  align-items: center;
  gap: 1rem;
  flex: 1;
}

.title-text h1 {
  font-size: 2.5rem;
  margin: 0;
}

.title-text h2 {
  font-size: 1.2rem;
  margin: 0;
  opacity: 0.9;
}

.filter-controls {
  display: flex;
  gap: 1rem;
}

.filter-item label {
  display: block;
  margin-bottom: 0.5rem;
  font-size: 0.875rem;
}

.filter-select {
  padding: 0.5rem;
  border-radius: 4px;
  border: none;
  background: rgba(255,255,255,0.2);
  color: white;
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
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
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
  color: #999;
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
  gap: 1.5rem;
}

.chart-card {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.chart-card.highlight {
  grid-column: span 2;
  border: 2px solid #ffd700;
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

@media (max-width: 1200px) {
  .summary-cards {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .charts-section {
    grid-template-columns: 1fr;
  }
  
  .chart-card.highlight {
    grid-column: span 1;
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