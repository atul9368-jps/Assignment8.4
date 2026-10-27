The HTML File (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hybrid Grid & Flexbox Dashboard</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Outer Grid Layout Wrapper -->
    <div class="dashboard-grid">
        
        <!-- Step 1: Dashboard Header -->
        <header class="header">
            <h2>Analytics Dashboard</h2>
            <div class="user-profile">
                <span>Welcome, Sarah</span>
            </div>
        </header>

        <!-- Step 1: Sidebar Navigation -->
        <aside class="sidebar">
            <div class="brand">MetricsPro</div>
            <nav>
                <ul>
                    <li><a href="#" class="active">Dashboard</a></li>
                    <li><a href="#">Analytics</a></li>
                    <li><a href="#">Users</a></li>
                    <li><a href="#">Settings</a></li>
                </ul>
            </nav>
        </aside>

        <!-- Step 1 & 3: Main Content Area with 4 Statistic Cards -->
        <main class="main-content">
            <h3>Overview</h3>
            
            <div class="stats-row">
                <!-- Card 1 -->
                <div class="stat-card">
                    <div class="card-icon blue">👥</div>
                    <div class="card-info">
                        <h4>Total Users</h4>
                        <p class="stat-value">24,500</p>
                    </div>
                </div>

                <!-- Card 2 -->
                <div class="stat-card">
                    <div class="card-icon green">💰</div>
                    <div class="card-info">
                        <h4>Revenue</h4>
                        <p class="stat-value">$12,840</p>
                    </div>
                </div>

                <!-- Card 3 -->
                <div class="stat-card">
                    <div class="card-icon orange">📦</div>
                    <div class="card-info">
                        <h4>Active Orders</h4>
                        <p class="stat-value">352</p>
                    </div>
                </div>

                <!-- Card 4 -->
                <div class="stat-card">
                    <div class="card-icon purple">⭐</div>
                    <div class="card-info">
                        <h4>Satisfaction</h4>
                        <p class="stat-value">98.2%</p>
                    </div>
                </div>
            </div>

            <!-- Step 5: Recent Activity Section / Table -->
            <section class="activity-section">
                <h3>Recent Activity</h3>
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>User</th>
                                <th>Action</th>
                                <th>Date</th>
                                <th>Status</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>Alex Johnson</td>
                                <td>Upgraded to Pro Plan</td>
                                <td>Oct 26, 2026</td>
                                <td><span class="badge success">Completed</span></td>
                            </tr>
                            <tr>
                                <td>Maria Garcia</td>
                                <td>Submitted Support Ticket</td>
                                <td>Oct 26, 2026</td>
                                <td><span class="badge pending">Pending</span></td>
                            </tr>
                            <tr>
                                <td>David Kim</td>
                                <td>New Account Registration</td>
                                <td>Oct 25, 2026</td>
                                <td><span class="badge success">Completed</span></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </section>
        </main>

    </div>

</body>
</html>
2. The CSS File (style.css)
CSS
/* Global Reset & Typography */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f8fafc;
    color: #1e293b;
    height: 100vh;
}

/* Steps 2 & 6: Outer Page Layout using CSS Grid */
.dashboard-grid {
    display: grid;
    grid-template-columns: 260px 1fr;
    grid-template-rows: 70px 1fr;
    grid-template-areas: 
        "sidebar header"
        "sidebar main";
    height: 100vh;
}

/* Header Grid Area */
.header {
    grid-area: header;
    background-color: #ffffff;
    border-bottom: 1px solid #e2e8f0;
    padding: 0 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.03);
}

.header h2 {
    font-size: 1.25rem;
    color: #0f172a;
}

.user-profile {
    font-weight: 600;
    color: #475569;
}

/* Sidebar Grid Area */
.sidebar {
    grid-area: sidebar;
    background-color: #0f172a;
    color: #ffffff;
    padding: 30px 20px;
}

.brand {
    font-size: 1.5rem;
    font-weight: 800;
    margin-bottom: 40px;
    color: #38bdf8;
    letter-spacing: -0.5px;
}

.sidebar ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.sidebar a {
    color: #94a3b8;
    text-decoration: none;
    font-weight: 600;
    display: block;
    padding: 12px 16px;
    border-radius: 6px;
    transition: background-color 0.2s, color 0.2s;
}

.sidebar a:hover, .sidebar a.active {
    background-color: #1e293b;
    color: #ffffff;
}

/* Main Content Area */
.main-content {
    grid-area: main;
    padding: 30px;
    overflow-y: auto;
}

.main-content > h3 {
    font-size: 1.5rem;
    margin-bottom: 20px;
    color: #0f172a;
}

/* Stats Cards Grid/Flex Row */
.stats-row {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 20px;
    margin-bottom: 40px;
}

/* Step 4: Inner Card Alignment using Flexbox */
.stat-card {
    background-color: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 10px;
    padding: 20px;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
    
    /* Flexbox inside card */
    display: flex;
    align-items: center;
    gap: 16px;
}

.card-icon {
    width: 50px;
    height: 50px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
}

.card-icon.blue { background-color: #eff6ff; }
.card-icon.green { background-color: #f0fdf4; }
.card-icon.orange { background-color: #fff7ed; }
.card-icon.purple { background-color: #faf5ff; }

.card-info h4 {
    font-size: 0.85rem;
    color: #64748b;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 4px;
}

.stat-value {
    font-size: 1.5rem;
    font-weight: 800;
    color: #0f172a;
}

/* Step 5: Recent Activity Table Styling */
.activity-section h3 {
    font-size: 1.25rem;
    margin-bottom: 16px;
    color: #0f172a;
}

.table-container {
    background-color: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
}

table {
    width: 100%;
    border-collapse: collapse;
    text-align: left;
}

th, td {
    padding: 16px 20px;
    border-bottom: 1px solid #e2e8f0;
    font-size: 0.95rem;
}

th {
    background-color: #f1f5f9;
    color: #475569;
    font-weight: 600;
}

tr:last-child td {
    border-bottom: none;
}

/* Badges */
.badge {
    padding: 4px 10px;
    border-radius: 20px;
    font-size: 0.75rem;
    font-weight: bold;
    text-transform: uppercase;
}

.badge.success {
    background-color: #d1fae5;
    color: #065f46;
}

.badge.pending {
    background-color: #fef3c7;
    color: #92400e;
}