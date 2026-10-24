HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard — Grid & Flexbox Combination</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Outer CSS Grid Layout Container -->
    <div class="dashboard-grid">

        <!-- 1. Header Section -->
        <header class="header">
            <div class="logo">NexusAdmin</div>
            <div class="user-profile">
                <span>Welcome back, Morgan</span>
                <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&w=100&q=80" alt="User Avatar">
            </div>
        </header>

        <!-- 1. Sidebar Section -->
        <aside class="sidebar">
            <ul class="sidebar-menu">
                <li><a href="#" class="active">📊 Dashboard</a></li>
                <li><a href="#">👥 Customers</a></li>
                <li><a href="#">📦 Orders</a></li>
                <li><a href="#">📈 Analytics</a></li>
                <li><a href="#">⚙️ Settings</a></li>
            </ul>
        </aside>

        <!-- 1 & 3. Main Content Area -->
        <main class="main-content">
            <div class="page-title">
                <h1>Performance Overview</h1>
                <p>Monitor key metrics, real-time analytics, and recent transactions.</p>
            </div>

            <!-- 3 & 4. Four Statistic Cards (Inner Flexbox Alignment) -->
            <div class="stats-container">
                
                <!-- Card 1 -->
                <div class="stat-card">
                    <div class="stat-info">
                        <span class="stat-title">Total Revenue</span>
                        <span class="stat-value">$54,239</span>
                        <span class="stat-trend positive">+14% this month</span>
                    </div>
                    <div class="stat-icon revenue-icon">💰</div>
                </div>

                <!-- Card 2 -->
                <div class="stat-card">
                    <div class="stat-info">
                        <span class="stat-title">Active Users</span>
                        <span class="stat-value">12,845</span>
                        <span class="stat-trend positive">+8.2% this week</span>
                    </div>
                    <div class="stat-icon users-icon">👥</div>
                </div>

                <!-- Card 3 -->
                <div class="stat-card">
                    <div class="stat-info">
                        <span class="stat-title">Bounce Rate</span>
                        <span class="stat-value">24.3%</span>
                        <span class="stat-trend negative">-1.5% today</span>
                    </div>
                    <div class="stat-icon bounce-icon">📉</div>
                </div>

                <!-- Card 4 -->
                <div class="stat-card">
                    <div class="stat-info">
                        <span class="stat-title">Pending Orders</span>
                        <span class="stat-value">384</span>
                        <span class="stat-trend positive">+3 new today</span>
                    </div>
                    <div class="stat-icon orders-icon">📦</div>
                </div>

            </div>

            <!-- 5. Recent Activity / Table Section -->
            <section class="activity-section">
                <div class="section-header">
                    <h2>Recent Transactions</h2>
                    <a href="#" class="view-all">View All</a>
                </div>

                <div class="table-responsive">
                    <table class="activity-table">
                        <thead>
                            <tr>
                                <th>Order ID</th>
                                <th>Customer</th>
                                <th>Status</th>
                                <th>Amount</th>
                                <th>Date</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>#ORD-9482</td>
                                <td>Emma Watson</td>
                                <td><span class="badge completed">Completed</span></td>
                                <td>$420.00</td>
                                <td>Oct 24, 2026</td>
                            </tr>
                            <tr>
                                <td>#ORD-9481</td>
                                <td>Liam Hemsworth</td>
                                <td><span class="badge pending">Pending</span></td>
                                <td>$150.50</td>
                                <td>Oct 24, 2026</td>
                            </tr>
                            <tr>
                                <td>#ORD-9480</td>
                                <td>Sophia Martinez</td>
                                <td><span class="badge completed">Completed</span></td>
                                <td>$1,299.00</td>
                                <td>Oct 23, 2026</td>
                            </tr>
                            <tr>
                                <td>#ORD-9479</td>
                                <td>Noah Sterling</td>
                                <td><span class="badge cancelled">Cancelled</span></td>
                                <td>$85.20</td>
                                <td>Oct 23, 2026</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </section>
        </main>

    </div>

</body>
</html>

CSS
/* Universal Resets */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
    background-color: #f1f5f9;
    color: #1e293b;
}

/* ==========================================================
   2. Outer Page Layout Using CSS Grid
   ========================================================== */
.dashboard-grid {
    display: grid; /* Activate Grid */
    grid-template-columns: 260px 1fr; /* Sidebar width + Flexible main content */
    grid-template-rows: 70px 1fr;    /* Header height + Flexible content area */
    grid-template-areas: 
        "header header"
        "sidebar main";
    min-height: 100vh;
}

/* ==========================================================
   1. Header Styling
   ========================================================== */
.header {
    grid-area: header;
    background-color: #ffffff;
    border-bottom: 1px solid #e2e8f0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 2rem;
}

.logo {
    font-size: 1.25rem;
    font-weight: 700;
    color: #2563eb;
    letter-spacing: -0.01em;
}

.user-profile {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    font-weight: 600;
    font-size: 0.95rem;
}

.user-profile img {
    width: 38px;
    height: 38px;
    border-radius: 50%;
    object-fit: cover;
}

/* ==========================================================
   1. Sidebar Styling
   ========================================================== */
.sidebar {
    grid-area: sidebar;
    background-color: #ffffff;
    border-right: 1px solid #e2e8f0;
    padding: 2rem 1.5rem;
}

.sidebar-menu {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

.sidebar-menu a {
    display: block;
    padding: 0.75rem 1rem;
    color: #64748b;
    text-decoration: none;
    font-weight: 500;
    border-radius: 8px;
    transition: all 0.2s ease;
}

.sidebar-menu a:hover, .sidebar-menu a.active {
    background-color: #eff6ff;
    color: #2563eb;
}

/* ==========================================================
   3 & 4. Main Content Area & Inner Flexbox Statistic Cards
   ========================================================== */
.main-content {
    grid-area: main;
    padding: 2.5rem;
    display: flex;
    flex-direction: column;
    gap: 2.5rem;
}

.page-title h1 {
    font-size: 1.75rem;
    font-weight: 700;
    color: #0f172a;
    margin-bottom: 0.25rem;
}

.page-title p {
    color: #64748b;
    font-size: 0.95rem;
}

/* Stats Container Grid */
.stats-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.5rem;
}

/* 4. Stat Card with Inner Flexbox Alignment */
.stat-card {
    background-color: #ffffff;
    border: 1px solid #e2e8f0;
    padding: 1.5rem;
    border-radius: 12px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.02);
    
    /* Inner Flexbox Setup */
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.stat-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.05);
}

.stat-info {
    display: flex;
    flex-direction: column;
}

.stat-title {
    font-size: 0.8rem;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    color: #64748b;
    font-weight: 600;
    margin-bottom: 0.35rem;
}

.stat-value {
    font-size: 1.75rem;
    font-weight: 700;
    color: #0f172a;
    margin-bottom: 0.35rem;
}

.stat-trend {
    font-size: 0.8rem;
    font-weight: 600;
}

.stat-trend.positive {
    color: #16a34a;
}

.stat-trend.negative {
    color: #dc2626;
}

.stat-icon {
    font-size: 1.5rem;
    width: 50px;
    height: 50px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #f8fafc;
}

/* ==========================================================
   5. Recent Activity / Table Section
   ========================================================== */
.activity-section {
    background-color: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 12px;
    padding: 1.75rem;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.02);
}

.section-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1.25rem;
}

.section-header h2 {
    font-size: 1.2rem;
    font-weight: 700;
    color: #0f172a;
}

.view-all {
    font-size: 0.9rem;
    text-decoration: none;
    color: #2563eb;
    font-weight: 600;
}

.view-all:hover {
    text-decoration: underline;
}

.table-responsive {
    overflow-x: auto;
}

.activity-table {
    width: 100%;
    border-collapse: collapse;
    text-align: left;
    font-size: 0.9rem;
}

.activity-table th {
    background-color: #f8fafc;
    color: #475569;
    font-weight: 600;
    padding: 0.75rem 1rem;
    border-bottom: 1px solid #e2e8f0;
}

.activity-table td {
    padding: 0.85rem 1rem;
    border-bottom: 1px solid #e2e8f0;
    color: #334155;
}

.activity-table tr:last-child td {
    border-bottom: none;
}

/* Badges */
.badge {
    padding: 0.25rem 0.6rem;
    border-radius: 20px;
    font-size: 0.75rem;
    font-weight: 600;
    text-transform: uppercase;
}

.badge.completed {
    background-color: #dcfce7;
    color: #15803d;
}

.badge.pending {
    background-color: #fef9c3;
    color: #a16207;
}

.badge.cancelled {
    background-color: #fee2e2;
    color: #b91c1c;
}

/* ==========================================================
   6. Browser Grid Inspector Check (Responsive Media Query)
   ========================================================== */
@media (max-width: 768px) {
    .dashboard-grid {
        grid-template-columns: 1fr;
        grid-template-rows: 70px auto 1fr;
        grid-template-areas: 
            "header"
            "sidebar"
            "main";
    }

    .sidebar {
        border-right: none;
        border-bottom: 1px solid #e2e8f0;
        padding: 1rem 1.5rem;
    }

    .sidebar-menu {
        flex-direction: row;
        overflow-x: auto;
    }

    .sidebar-menu a {
        white-space: nowrap;
    }
}