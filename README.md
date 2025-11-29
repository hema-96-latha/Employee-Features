<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Employee Dashboard | Attendance System</title>
    <style>
        /* Basic CSS for structure and appearance */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }

        .container {
            display: flex;
            min-height: 100vh;
        }

        .sidebar {
            width: 250px;
            background-color: #2c3e50; /* Dark sidebar */
            color: white;
            padding: 20px 0;
            box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
        }

        .sidebar h2 {
            text-align: center;
            margin-bottom: 30px;
            color: #ecf0f1;
        }

        .sidebar nav a {
            display: block;
            padding: 15px 20px;
            text-decoration: none;
            color: #ecf0f1;
            transition: background-color 0.3s;
            border-left: 5px solid transparent;
        }

        .sidebar nav a:hover, .sidebar nav a.active {
            background-color: #34495e; /* Slightly lighter on hover/active */
            border-left: 5px solid #3498db; /* Highlight color */
        }

        .main-content {
            flex-grow: 1;
            padding: 40px;
        }

        /* Feature 2: Attendance Section */
        .attendance-card {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.05);
            text-align: center;
            margin-bottom: 40px;
        }

        .attendance-card h3 {
            margin-top: 0;
            color: #2980b9;
        }

        .attendance-card button {
            padding: 12px 25px;
            font-size: 16px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            margin: 0 10px;
            transition: background-color 0.3s;
        }

        #check-in {
            background-color: #2ecc71; /* Green */
            color: white;
        }

        #check-out {
            background-color: #e74c3c; /* Red */
            color: white;
        }

        #check-in:hover { background-color: #27ae60; }
        #check-out:hover { background-color: #c0392b; }

        /* Feature 5: Dashboard Stats */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
        }

        .stat-box {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
            text-align: center;
            border-left: 5px solid #3498db;
        }

        .stat-box .number {
            font-size: 2.5em;
            font-weight: bold;
            color: #3498db;
            margin-bottom: 5px;
        }

        .stat-box .label {
            font-size: 1em;
            color: #7f8c8d;
        }
    </style>
</head>
<body>

<div class="container">
    <div class="sidebar">
        <h2>Employee Portal</h2>
        <nav>
            <a href="login.html">🔑 Login / Register</a> 
            
            <a href="#" class="active">📊 Dashboard</a> 
            
            <a href="history.html">📅 Attendance History</a> 
            <a href="summary.html">📈 Monthly Summary</a> 
        </nav>
    </div>

    <div class="main-content">
        <h1>Welcome, [Employee Name]!</h1>
        <p>Today is: **<span id="current-date">Saturday, November 29, 2025</span>**</p>

        <div class="attendance-card">
            <h3>Mark Attendance</h3>
            <button id="check-in">✅ Check In</button>
            <button id="check-out">🛑 Check Out</button>
            <p id="status-message" style="margin-top: 15px; color: #f39c12;">Status: Please Check In</p>
        </div>

        <h2>Monthly Attendance Stats</h2>
        <div class="stats-grid">
            
            <div class="stat-box">
                <div class="number">18</div>
                <div class="label">Days Present</div>
            </div>

            <div class="stat-box">
                <div class="number">2</div>
                <div class="label">Days Absent</div>
            </div>

            <div class="stat-box">
                <div class="number">3</div>
                <div class="label">Times Late</div>
            </div>
            
            <div class="stat-box">
                <div class="number">144</div>
                <div class="label">Total Hours Worked</div>
            </div>
        </div>
        
        <h2 style="margin-top: 40px;">Recent Activity</h2>
        <table style="width: 100%; border-collapse: collapse; margin-top: 15px; background-color: white; border-radius: 8px; box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);">
            <thead>
                <tr style="background-color: #ecf0f1;">
                    <th style="padding: 10px; text-align: left; border-bottom: 1px solid #ddd;">Date</th>
                    <th style="padding: 10px; text-align: left; border-bottom: 1px solid #ddd;">Check In</th>
                    <th style="padding: 10px; text-align: left; border-bottom: 1px solid #ddd;">Check Out</th>
                    <th style="padding: 10px; text-align: left; border-bottom: 1px solid #ddd;">Status</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td style="padding: 10px; border-bottom: 1px solid #eee;">Nov 28</td>
                    <td style="padding: 10px; border-bottom: 1px solid #eee;">09:05 AM</td>
                    <td style="padding: 10px; border-bottom: 1px solid #eee;">05:00 PM</td>
                    <td style="padding: 10px; border-bottom: 1px solid #eee; color: #f39c12;">Late</td>
                </tr>
                <tr>
                    <td style="padding: 10px; border-bottom: 1px solid #eee;">Nov 27</td>
                    <td style="padding: 10px; border-bottom: 1px solid #eee;">08:58 AM</td>
                    <td style="padding: 10px; border-bottom: 1px solid #eee;">05:02 PM</td>
                    <td style="padding: 10px; border-bottom: 1px solid #eee; color: #2ecc71;">Present</td>
                </tr>
            </tbody>
        </table>

    </div>
</div>

<script>
    document.getElementById('check-in').onclick = function() {
        document.getElementById('status-message').textContent = 'Status: Checked In at ' + new Date().toLocaleTimeString();
        document.getElementById('status-message').style.color = '#2ecc71';
    };
    document.getElementById('check-out').onclick = function() {
        document.getElementById('status-message').textContent = 'Status: Checked Out at ' + new Date().toLocaleTimeString();
        document.getElementById('status-message').style.color = '#e74c3c';
    };
    // Update date on load
    document.getElementById('current-date').textContent = new Date().toLocaleDateString('en-US', {
        weekday: 'long', year: 'numeric', month: 'long', day: 'numeric'
    });
</script>

</body>
</html>
