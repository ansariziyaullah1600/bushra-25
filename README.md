<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BUSHRA'2k25 - Cultural &amp; Educational Events Dashboard</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&amp;display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #6a11cb;
            --secondary-color: #2575fc;
            --accent-color: #ff416c;
            --highlight-color: #ffb347;
            --bg-color: #f8f9fa;
            --text-color: #333;
            --card-bg: white;
            --border-color: #e9ecef;
            --success-color: #28a745;
            --info-color: #007bff;
            --warning-color: #ffc107;
            --danger-color: #dc3545;
            --dark-color: #6c757d;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            --team1-color: #4361ee;
            --team2-color: #3a0ca3;
            --team3-color: #7209b7;
            --team4-color: #f72585;
            --gold-color: #FFD700;
            --silver-color: #C0C0C0;
            --bronze-color: #CD7F32;
            --gradient-primary: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            --gradient-accent: linear-gradient(135deg, var(--accent-color), var(--highlight-color));
        }

        [data-theme="dark"] {
            --bg-color: #1a1a1a;
            --text-color: #f8f9fa;
            --card-bg: #2d2d2d;
            --border-color: #404040;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.4);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d);
            min-height: 100vh;
            padding: 20px;
            color: var(--text-color);
            transition: background 0.3s ease, color 0.3s ease;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            background: var(--card-bg);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            transition: background 0.3s ease;
            position: relative;
        }
        
        header {
            background: var(--gradient-primary);
            color: white;
            padding: 40px 30px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: "";
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, rgba(255,255,255,0) 70%);
            animation: pulse 8s infinite alternate;
        }
        
        @keyframes pulse {
            0% { transform: scale(0.8); opacity: 0.5; }
            100% { transform: scale(1.2); opacity: 0.8; }
        }
        
        .theme-toggle {
            position: absolute;
            top: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.2);
            border: none;
            border-radius: 50%;
            width: 45px;
            height: 45px;
            color: white;
            cursor: pointer;
            font-size: 1.3rem;
            transition: all 0.3s ease;
            backdrop-filter: blur(5px);
            z-index: 10;
        }
        
        .theme-toggle:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: rotate(180deg);
        }
        
        header h1 {
            font-size: 3.5rem;
            margin-bottom: 15px;
            font-weight: 800;
            text-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            position: relative;
            z-index: 1;
        }
        
        .subtitle {
            font-size: 1.3rem;
            opacity: 0.9;
            font-weight: 500;
            position: relative;
            z-index: 1;
        }
        
        .festival-badge {
            display: inline-block;
            background: var(--gradient-accent);
            color: white;
            padding: 8px 20px;
            border-radius: 30px;
            font-weight: 600;
            margin-top: 15px;
            box-shadow: 0 4px 15px rgba(255, 65, 108, 0.4);
            position: relative;
            z-index: 1;
        }
        
        .dashboard-stats {
            display: flex;
            justify-content: space-around;
            padding: 30px;
            background: var(--bg-color);
            border-bottom: 1px solid var(--border-color);
            flex-wrap: wrap;
            gap: 20px;
            transition: background 0.3s ease, border-color 0.3s ease;
        }
        
        .stat-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px 20px;
            text-align: center;
            min-width: 150px;
            box-shadow: var(--shadow);
            transition: all 0.3s ease, transform 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .stat-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--gradient-primary);
        }
        
        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.15);
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            background: var(--gradient-primary);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
        }
        
        .stat-label {
            color: var(--dark-color);
            font-weight: 500;
            font-size: 1rem;
        }
        
        .main-tabs {
            display: flex;
            background: var(--bg-color);
            border-bottom: 1px solid var(--border-color);
            overflow-x: auto;
            transition: background 0.3s ease, border-color 0.3s ease;
            position: relative;
        }
        
        .main-tab {
            flex: 1;
            padding: 25px 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border-bottom: 4px solid transparent;
            font-weight: 600;
            color: var(--text-color);
            font-size: 1.1rem;
            position: relative;
        }
        
        .main-tab i {
            display: block;
            font-size: 1.8rem;
            margin-bottom: 8px;
        }
        
        .main-tab:hover {
            background: rgba(0, 0, 0, 0.05);
        }
        
        .main-tab.active {
            background: var(--card-bg);
            border-bottom: 4px solid var(--primary-color);
            color: var(--primary-color);
        }
        
        .team-tabs {
            display: flex;
            background: var(--bg-color);
            border-bottom: 1px solid var(--border-color);
            overflow-x: auto;
            transition: background 0.3s ease, border-color 0.3s ease;
            position: relative;
        }
        
        .team-tab {
            flex: 1;
            padding: 25px 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border-bottom: 4px solid transparent;
            font-weight: 600;
            color: var(--text-color);
            font-size: 1.1rem;
            position: relative;
        }
        
        .team-tab i {
            display: block;
            font-size: 1.8rem;
            margin-bottom: 8px;
        }
        
        .team-tab:hover {
            background: rgba(0, 0, 0, 0.05);
        }
        
        .team-tab.active {
            background: var(--card-bg);
            border-bottom: 4px solid var(--primary-color);
            color: var(--primary-color);
        }
        
        .team-tab.team1.active {
            border-bottom-color: var(--team1-color);
            color: var(--team1-color);
        }
        
        .team-tab.team2.active {
            border-bottom-color: var(--team2-color);
            color: var(--team2-color);
        }
        
        .team-tab.team3.active {
            border-bottom-color: var(--team3-color);
            color: var(--team3-color);
        }
        
        .team-tab.team4.active {
            border-bottom-color: var(--team4-color);
            color: var(--team4-color);
        }
        
        .team-content, .students-content {
            padding: 30px;
            display: none;
            transition: background 0.3s ease;
        }
        
        .team-content.active, .students-content.active {
            display: block;
        }
        
        .team-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .students-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .team-name, .students-title {
            font-size: 2.5rem;
            font-weight: 700;
            position: relative;
            display: inline-block;
        }
        
        .team-name::after, .students-title::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 4px;
            border-radius: 2px;
        }
        
        .students-title {
            color: var(--primary-color);
        }
        
        .students-title::after {
            background: var(--primary-color);
        }
        
        .team-name.team1 {
            color: var(--team1-color);
        }
        
        .team-name.team1::after {
            background: var(--team1-color);
        }
        
        .team-name.team2 {
            color: var(--team2-color);
        }
        
        .team-name.team2::after {
            background: var(--team2-color);
        }
        
        .team-name.team3 {
            color: var(--team3-color);
        }
        
        .team-name.team3::after {
            background: var(--team3-color);
        }
        
        .team-name.team4 {
            color: var(--team4-color);
        }
        
        .team-name.team4::after {
            background: var(--team4-color);
        }
        
        .team-stats {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }
        
        .stat-card.team1 {
            border-left: 4px solid var(--team1-color);
        }
        
        .stat-card.team2 {
            border-left: 4px solid var(--team2-color);
        }
        
        .stat-card.team3 {
            border-left: 4px solid var(--team3-color);
        }
        
        .stat-card.team4 {
            border-left: 4px solid var(--team4-color);
        }
        
        .stat-number.team1 {
            background: var(--team1-color);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .stat-number.team2 {
            background: var(--team2-color);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .stat-number.team3 {
            background: var(--team3-color);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .stat-number.team4 {
            background: var(--team4-color);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        /* Points System Styles */
        .points-section {
            background: var(--bg-color);
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 30px;
            transition: background 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .points-title {
            font-size: 1.8rem;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--primary-color);
        }
        
        .points-title i {
            font-size: 1.5rem;
        }
        
        .team-points-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 20px;
        }
        
        .team-points-card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 20px;
            box-shadow: var(--shadow);
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .team-points-card:hover {
            transform: translateY(-5px);
        }
        
        .team-points-card.team1 {
            border-top: 4px solid var(--team1-color);
        }
        
        .team-points-card.team2 {
            border-top: 4px solid var(--team2-color);
        }
        
        .team-points-card.team3 {
            border-top: 4px solid var(--team3-color);
        }
        
        .team-points-card.team4 {
            border-top: 4px solid var(--team4-color);
        }
        
        .team-points-name {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 10px;
        }
        
        .team-points-name.team1 {
            color: var(--team1-color);
        }
        
        .team-points-name.team2 {
            color: var(--team2-color);
        }
        
        .team-points-name.team3 {
            color: var(--team3-color);
        }
        
        .team-points-name.team4 {
            color: var(--team4-color);
        }
        
        .team-points-number {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 5px;
        }
        
        .team-points-number.team1 {
            color: var(--team1-color);
        }
        
        .team-points-number.team2 {
            color: var(--team2-color);
        }
        
        .team-points-number.team3 {
            color: var(--team3-color);
        }
        
        .team-points-number.team4 {
            color: var(--team4-color);
        }
        
        .team-points-label {
            color: var(--dark-color);
            font-size: 0.9rem;
        }
        
        .team-rank {
            position: absolute;
            top: 10px;
            right: 10px;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: white;
            font-size: 0.9rem;
        }
        
        .rank-1 {
            background: var(--gold-color);
            color: #333;
        }
        
        .rank-2 {
            background: var(--silver-color);
            color: #333;
        }
        
        .rank-3 {
            background: var(--bronze-color);
            color: #333;
        }
        
        .rank-other {
            background: var(--dark-color);
        }
        
        /* Students Section Styles */
        .students-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
            flex-wrap: wrap;
            gap: 15px;
        }
        
        .students-filter-group {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .students-filter-group label {
            font-weight: 500;
        }
        
        .students-search-box {
            position: relative;
            flex: 1;
            max-width: 300px;
        }
        
        .students-search-box input {
            padding-left: 45px;
            width: 100%;
            border-radius: 30px;
        }
        
        .students-search-box i {
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--dark-color);
        }
        
        .students-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 25px;
        }
        
        .student-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }
        
        .student-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--gradient-primary);
        }
        
        .student-card.team1::before {
            background: var(--team1-color);
        }
        
        .student-card.team2::before {
            background: var(--team2-color);
        }
        
        .student-card.team3::before {
            background: var(--team3-color);
        }
        
        .student-card.team4::before {
            background: var(--team4-color);
        }
        
        .student-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.15);
        }
        
        .student-header {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            gap: 15px;
        }
        
        .student-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--bg-color);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            position: relative;
            overflow: hidden;
        }
        
        .student-avatar.team1 {
            color: var(--team1-color);
        }
        
        .student-avatar.team2 {
            color: var(--team2-color);
        }
        
        .student-avatar.team3 {
            color: var(--team3-color);
        }
        
        .student-avatar.team4 {
            color: var(--team4-color);
        }
        
        .student-info h3 {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .student-info p {
            font-size: 0.9rem;
            color: var(--dark-color);
        }
        
        .student-details {
            margin-bottom: 20px;
        }
        
        .student-detail {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
            color: var(--dark-color);
            font-size: 0.9rem;
        }
        
        .student-detail i {
            width: 20px;
            text-align: center;
        }
        
        .student-detail.team1 i {
            color: var(--team1-color);
        }
        
        .student-detail.team2 i {
            color: var(--team2-color);
        }
        
        .student-detail.team3 i {
            color: var(--team3-color);
        }
        
        .student-detail.team4 i {
            color: var(--team4-color);
        }
        
        .student-points {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
            color: var(--dark-color);
            font-size: 0.9rem;
        }
        
        .student-points i {
            width: 20px;
            text-align: center;
            color: var(--warning-color);
        }
        
        .student-points-number {
            font-weight: 600;
            color: var(--warning-color);
        }
        
        .student-events {
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px dashed var(--border-color);
        }
        
        .student-events-title {
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 10px;
            color: var(--dark-color);
        }
        
        .student-events-list {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }
        
        .student-event-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 8px 12px;
            border-radius: 8px;
            background: var(--bg-color);
            font-size: 0.9rem;
        }
        
        .student-event-name {
            font-weight: 500;
        }
        
        .student-event-grade {
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .grade-badge-small {
            width: 20px;
            height: 20px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: white;
            font-size: 0.7rem;
        }
        
        .no-student-events {
            text-align: center;
            padding: 15px;
            color: var(--dark-color);
            font-style: italic;
        }
        
        .no-students {
            text-align: center;
            padding: 60px 20px;
            color: var(--dark-color);
        }
        
        .no-students i {
            font-size: 4rem;
            margin-bottom: 20px;
            color: var(--border-color);
        }
        
        .no-students h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
        }
        
        /* Team Members Section */
        .team-members-section {
            background: var(--bg-color);
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 30px;
            transition: background 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .team-members-title {
            font-size: 1.8rem;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .team-members-title i {
            font-size: 1.5rem;
        }
        
        .team-members-title.team1 {
            color: var(--team1-color);
        }
        
        .team-members-title.team2 {
            color: var(--team2-color);
        }
        
        .team-members-title.team3 {
            color: var(--team3-color);
        }
        
        .team-members-title.team4 {
            color: var(--team4-color);
        }
        
        .team-leaders {
            display: flex;
            gap: 20px;
            margin-bottom: 25px;
            flex-wrap: wrap;
        }
        
        .leader-card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 20px;
            box-shadow: var(--shadow);
            flex: 1;
            min-width: 200px;
            display: flex;
            align-items: center;
            gap: 15px;
            transition: all 0.3s ease;
        }
        
        .leader-card:hover {
            transform: translateY(-5px);
        }
        
        .leader-card.team1 {
            border-left: 4px solid var(--team1-color);
        }
        
        .leader-card.team2 {
            border-left: 4px solid var(--team2-color);
        }
        
        .leader-card.team3 {
            border-left: 4px solid var(--team3-color);
        }
        
        .leader-card.team4 {
            border-left: 4px solid var(--team4-color);
        }
        
        .leader-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--bg-color);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            position: relative;
            overflow: hidden;
        }
        
        .leader-avatar.team1 {
            color: var(--team1-color);
        }
        
        .leader-avatar.team2 {
            color: var(--team2-color);
        }
        
        .leader-avatar.team3 {
            color: var(--team3-color);
        }
        
        .leader-avatar.team4 {
            color: var(--team4-color);
        }
        
        .leader-info h3 {
            font-size: 1.2rem;
            margin-bottom: 5px;
            font-weight: 600;
        }
        
        .leader-info p {
            font-size: 0.9rem;
            color: var(--dark-color);
        }
        
        .team-members-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 15px;
        }
        
        .member-card {
            background: var(--card-bg);
            border-radius: 12px;
            padding: 15px;
            box-shadow: var(--shadow);
            display: flex;
            align-items: center;
            gap: 15px;
            transition: all 0.3s ease;
        }
        
        .member-card:hover {
            transform: translateY(-5px);
        }
        
        .member-card.team1 {
            border-left: 3px solid var(--team1-color);
        }
        
        .member-card.team2 {
            border-left: 3px solid var(--team2-color);
        }
        
        .member-card.team3 {
            border-left: 3px solid var(--team3-color);
        }
        
        .member-card.team4 {
            border-left: 3px solid var(--team4-color);
        }
        
        .member-avatar {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: var(--bg-color);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
        }
        
        .member-avatar.team1 {
            color: var(--team1-color);
        }
        
        .member-avatar.team2 {
            color: var(--team2-color);
        }
        
        .member-avatar.team3 {
            color: var(--team3-color);
        }
        
        .member-avatar.team4 {
            color: var(--team4-color);
        }
        
        .member-info h4 {
            font-size: 1rem;
            margin-bottom: 3px;
            font-weight: 600;
        }
        
        .member-info p {
            font-size: 0.8rem;
            color: var(--dark-color);
        }
        
        .member-chest {
            font-size: 0.8rem;
            color: var(--info-color);
            font-weight: 600;
        }
        
        .controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
            flex-wrap: wrap;
            gap: 15px;
        }
        
        .filter-group {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .filter-group label {
            font-weight: 500;
        }
        
        select, input {
            padding: 12px 15px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            font-size: 1rem;
            background: var(--card-bg);
            color: var(--text-color);
            transition: all 0.3s ease;
            font-family: 'Poppins', sans-serif;
        }
        
        select:focus, input:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(106, 17, 203, 0.2);
        }
        
        .search-box {
            position: relative;
            flex: 1;
            max-width: 300px;
        }
        
        .search-box input {
            padding-left: 45px;
            width: 100%;
            border-radius: 30px;
        }
        
        .search-box i {
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--dark-color);
        }
        
        .events-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 25px;
        }
        
        .event-card {
            background: var(--card-bg);
            border-radius: 15px;
            padding: 25px;
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            position: relative;
            cursor: pointer;
            overflow: hidden;
        }
        
        .event-card::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--gradient-primary);
        }
        
        .event-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.15);
        }
        
        .event-card.team1::before {
            background: var(--team1-color);
        }
        
        .event-card.team2::before {
            background: var(--team2-color);
        }
        
        .event-card.team3::before {
            background: var(--team3-color);
        }
        
        .event-card.team4::before {
            background: var(--team4-color);
        }
        
        .event-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 15px;
        }
        
        .event-title {
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 8px;
        }
        
        .event-title.team1 {
            color: var(--team1-color);
        }
        
        .event-title.team2 {
            color: var(--team2-color);
        }
        
        .event-title.team3 {
            color: var(--team3-color);
        }
        
        .event-title.team4 {
            color: var(--team4-color);
        }
        
        .event-category {
            display: inline-block;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            margin-bottom: 12px;
        }
        
        .category-language {
            background: rgba(0, 123, 255, 0.1);
            color: var(--info-color);
        }
        
        .category-quiz {
            background: rgba(40, 167, 69, 0.1);
            color: var(--success-color);
        }
        
        .category-talent {
            background: rgba(255, 193, 7, 0.1);
            color: var(--warning-color);
        }
        
        .category-technical {
            background: rgba(106, 17, 203, 0.1);
            color: var(--primary-color);
        }
        
        .category-magazine {
            background: rgba(220, 53, 69, 0.1);
            color: var(--danger-color);
        }
        
        .event-details {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-bottom: 15px;
            flex-grow: 1;
        }
        
        .event-detail {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--dark-color);
            font-size: 0.9rem;
        }
        
        .event-detail i {
            width: 20px;
            text-align: center;
        }
        
        .event-detail.team1 i {
            color: var(--team1-color);
        }
        
        .event-detail.team2 i {
            color: var(--team2-color);
        }
        
        .event-detail.team3 i {
            color: var(--team3-color);
        }
        
        .event-detail.team4 i {
            color: var(--team4-color);
        }
        
        .event-participants {
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px dashed var(--border-color);
        }
        
        .event-participants-title {
            font-size: 0.9rem;
            font-weight: 600;
            margin-bottom: 8px;
            color: var(--dark-color);
        }
        
        .event-participants-list {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }
        
        .participant-tag {
            background: var(--bg-color);
            border-radius: 20px;
            padding: 5px 12px;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            gap: 5px;
            font-weight: 500;
        }
        
        .participant-tag.team1 {
            background: rgba(67, 97, 238, 0.1);
            color: var(--team1-color);
        }
        
        .participant-tag.team2 {
            background: rgba(58, 12, 163, 0.1);
            color: var(--team2-color);
        }
        
        .participant-tag.team3 {
            background: rgba(114, 9, 183, 0.1);
            color: var(--team3-color);
        }
        
        .participant-tag.team4 {
            background: rgba(247, 37, 133, 0.1);
            color: var(--team4-color);
        }
        
        .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.9rem;
            font-weight: 500;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            font-family: 'Poppins', sans-serif;
        }
        
        .btn-primary {
            background: var(--gradient-primary);
            color: white;
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(106, 17, 203, 0.4);
        }
        
        .btn-outline {
            background: transparent;
            color: var(--primary-color);
            border: 1px solid var(--primary-color);
        }
        
        .btn-outline:hover {
            background: var(--primary-color);
            color: white;
        }
        
        .btn-edit {
            background: var(--warning-color);
            color: #333;
        }
        
        .btn-edit:hover {
            background: #e0a800;
        }
        
        .btn-delete {
            background: var(--danger-color);
            color: white;
        }
        
        .btn-delete:hover {
            background: #c82333;
        }
        
        .btn-primary.team1 {
            background: var(--team1-color);
        }
        
        .btn-primary.team1:hover {
            background: #3a56d4;
        }
        
        .btn-outline.team1 {
            color: var(--team1-color);
            border-color: var(--team1-color);
        }
        
        .btn-outline.team1:hover {
            background: var(--team1-color);
        }
        
        .btn-primary.team2 {
            background: var(--team2-color);
        }
        
        .btn-primary.team2:hover {
            background: #320a8a;
        }
        
        .btn-outline.team2 {
            color: var(--team2-color);
            border-color: var(--team2-color);
        }
        
        .btn-outline.team2:hover {
            background: var(--team2-color);
        }
        
        .btn-primary.team3 {
            background: var(--team3-color);
        }
        
        .btn-primary.team3:hover {
            background: #6208a0;
        }
        
        .btn-outline.team3 {
            color: var(--team3-color);
            border-color: var(--team3-color);
        }
        
        .btn-outline.team3:hover {
            background: var(--team3-color);
        }
        
        .btn-primary.team4 {
            background: var(--team4-color);
        }
        
        .btn-primary.team4:hover {
            background: #e61e73;
        }
        
        .btn-outline.team4 {
            color: var(--team4-color);
            border-color: var(--team4-color);
        }
        
        .btn-outline.team4:hover {
            background: var(--team4-color);
        }
        
        .btn-select-students {
            background: var(--info-color);
            color: white;
        }
        
        .btn-select-students:hover {
            background: #0069d9;
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            backdrop-filter: blur(5px);
        }
        
        .modal-content {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 30px;
            max-width: 800px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            transition: background 0.3s ease;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }
        
        .close-modal {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 1.8rem;
            cursor: pointer;
            color: var(--dark-color);
            transition: all 0.3s ease;
        }
        
        .close-modal:hover {
            color: var(--danger-color);
            transform: rotate(90deg);
        }
        
        .modal h2 {
            margin-bottom: 20px;
            font-weight: 700;
            position: relative;
            display: inline-block;
        }
        
        .modal h2::after {
            content: "";
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 50px;
            height: 3px;
            border-radius: 2px;
        }
        
        .modal h2.team1 {
            color: var(--team1-color);
        }
        
        .modal h2.team1::after {
            background: var(--team1-color);
        }
        
        .modal h2.team2 {
            color: var(--team2-color);
        }
        
        .modal h2.team2::after {
            background: var(--team2-color);
        }
        
        .modal h2.team3 {
            color: var(--team3-color);
        }
        
        .modal h2.team3::after {
            background: var(--team3-color);
        }
        
        .modal h2.team4 {
            color: var(--team4-color);
        }
        
        .modal h2.team4::after {
            background: var(--team4-color);
        }
        
        .modal-details {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 25px;
        }
        
        .modal-detail {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 10px;
            border-radius: 8px;
            background: var(--bg-color);
        }
        
        .modal-detail i {
            width: 20px;
            text-align: center;
        }
        
        .modal-detail.team1 i {
            color: var(--team1-color);
        }
        
        .modal-detail.team2 i {
            color: var(--team2-color);
        }
        
        .modal-detail.team3 i {
            color: var(--team3-color);
        }
        
        .modal-detail.team4 i {
            color: var(--team4-color);
        }
        
        .modal-description {
            margin-bottom: 25px;
            line-height: 1.6;
            padding: 15px;
            border-radius: 10px;
            background: var(--bg-color);
        }
        
        .modal-actions {
            display: flex;
            gap: 15px;
            margin-top: 25px;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        .registration-form, .add-member-form, .edit-program-form {
            background: var(--bg-color);
            border-radius: 15px;
            padding: 25px;
            margin-top: 25px;
            transition: background 0.3s ease;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }
        
        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            background: var(--card-bg);
            color: var(--text-color);
            font-family: 'Poppins', sans-serif;
        }
        
        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }
        
        .no-results {
            text-align: center;
            padding: 60px 20px;
            color: var(--dark-color);
        }
        
        .no-results i {
            font-size: 4rem;
            margin-bottom: 20px;
            color: var(--border-color);
        }
        
        .no-results h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
        }
        
        /* Grade/Ranking Badge Styles */
        .grade-badge {
            position: absolute;
            top: 15px;
            right: 15px;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: white;
            font-size: 1.1rem;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .grade-badge:hover {
            transform: scale(1.1);
        }
        
        .grade-first {
            background: var(--gold-color);
            color: #333;
        }
        
        .grade-second {
            background: var(--silver-color);
            color: #333;
        }
        
        .grade-third {
            background: var(--bronze-color);
            color: #333;
        }
        
        .grade-a {
            background: var(--success-color);
        }
        
        .grade-b {
            background: var(--info-color);
        }
        
        .grade-c {
            background: var(--warning-color);
            color: #333;
        }
        
        .grade-d {
            background: var(--danger-color);
        }
        
        .grade-participant {
            background: var(--dark-color);
        }
        
        .grade-honorable {
            background: var(--info-color);
        }
        
        .grade-round1, .grade-round2 {
            background: var(--warning-color);
            color: #333;
        }
        
        /* Grading Section Styles */
        .grading-section {
            background: var(--bg-color);
            border-radius: 15px;
            padding: 25px;
            margin-top: 25px;
            transition: background 0.3s ease;
        }
        
        .grade-options {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .grade-option {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 10px;
            border-radius: 8px;
            background: var(--card-bg);
            transition: all 0.3s ease;
        }
        
        .grade-option:hover {
            background: var(--bg-color);
        }
        
        .grade-option input[type="radio"] {
            width: auto;
        }
        
        /* Change Result Link */
        .change-result-link {
            display: inline-block;
            margin-top: 15px;
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .change-result-link:hover {
            color: var(--secondary-color);
            text-decoration: underline;
        }
        
        .change-result-link.team1:hover {
            color: var(--team1-color);
        }
        
        .change-result-link.team2:hover {
            color: var(--team2-color);
        }
        
        .change-result-link.team3:hover {
            color: var(--team3-color);
        }
        
        .change-result-link.team4:hover {
            color: var(--team4-color);
        }
        
        /* Student Selection Styles */
        .student-selection {
            background: var(--bg-color);
            border-radius: 15px;
            padding: 25px;
            margin-top: 25px;
            transition: background 0.3s ease;
        }
        
        .student-selection h3 {
            margin-bottom: 20px;
            font-weight: 600;
        }
        
        .student-selection h3.team1 {
            color: var(--team1-color);
        }
        
        .student-selection h3.team2 {
            color: var(--team2-color);
        }
        
        .student-selection h3.team3 {
            color: var(--team3-color);
        }
        
        .student-selection h3.team4 {
            color: var(--team4-color);
        }
        
        .student-select-container {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .student-select {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .student-select select {
            flex: 1;
        }
        
        .selected-students {
            margin-top: 20px;
        }
        
        .selected-student-tag {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: var(--primary-color);
            color: white;
            border-radius: 20px;
            padding: 8px 15px;
            margin-right: 10px;
            margin-bottom: 10px;
            font-size: 0.9rem;
            font-weight: 500;
        }
        
        .selected-student-tag.team1 {
            background: var(--team1-color);
        }
        
        .selected-student-tag.team2 {
            background: var(--team2-color);
        }
        
        .selected-student-tag.team3 {
            background: var(--team3-color);
        }
        
        .selected-student-tag.team4 {
            background: var(--team4-color);
        }
        
        .remove-student {
            background: none;
            border: none;
            color: white;
            cursor: pointer;
            font-size: 0.9rem;
            padding: 0;
            margin-left: 5px;
        }
        
        .student-checkboxes {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 15px;
        }
        
        .checkbox-item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px;
            border-radius: 8px;
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
        }
        
        .checkbox-item:hover {
            background: var(--bg-color);
            border-color: var(--primary-color);
        }
        
        .checkbox-item input[type="checkbox"] {
            width: auto;
        }
        
        .selection-counter {
            margin-top: 15px;
            font-weight: 600;
            color: var(--dark-color);
            font-size: 1.1rem;
        }
        
        .validation-message {
            margin-top: 15px;
            padding: 12px 15px;
            border-radius: 8px;
            font-size: 0.9rem;
            display: none;
            font-weight: 500;
        }
        
        .validation-error {
            background: rgba(220, 53, 69, 0.1);
            color: var(--danger-color);
            border: 1px solid rgba(220, 53, 69, 0.3);
        }
        
        .validation-success {
            background: rgba(40, 167, 69, 0.1);
            color: var(--success-color);
            border: 1px solid rgba(40, 167, 69, 0.3);
        }
        
        /* Student Grading Styles */
        .student-grading {
            background: var(--bg-color);
            border-radius: 15px;
            padding: 25px;
            margin-top: 25px;
            transition: background 0.3s ease;
        }
        
        .student-grading h3 {
            margin-bottom: 20px;
            font-weight: 600;
        }
        
        .student-grading h3.team1 {
            color: var(--team1-color);
        }
        
        .student-grading h3.team2 {
            color: var(--team2-color);
        }
        
        .student-grading h3.team3 {
            color: var(--team3-color);
        }
        
        .student-grading h3.team4 {
            color: var(--team4-color);
        }
        
        .student-grade-row {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
            padding: 15px;
            border-radius: 10px;
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
        }
        
        .student-grade-row:hover {
            background: var(--bg-color);
            border-color: var(--primary-color);
        }
        
        .student-name {
            flex: 1;
            font-weight: 600;
            font-size: 1.1rem;
        }
        
        .student-grade-select {
            flex: 2;
        }
        
        .student-grade-select select {
            width: 100%;
        }
        
        .grade-preview {
            margin-left: 15px;
            width: 35px;
            height: 35px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: white;
            font-size: 0.9rem;
        }
        
        /* Password Modal Styles */
        .password-modal {
            background: var(--bg-color);
            border-radius: 15px;
            padding: 25px;
            margin-top: 25px;
            transition: background 0.3s ease;
        }
        
        .password-modal h3 {
            margin-bottom: 20px;
            font-weight: 600;
            color: var(--primary-color);
        }
        
        .password-input-group {
            display: flex;
            gap: 15px;
            margin-bottom: 20px;
        }
        
        .password-input-group input {
            flex: 1;
        }
        
        .password-hint {
            font-size: 0.95rem;
            color: var(--dark-color);
            margin-bottom: 20px;
        }
        
        .password-error {
            color: var(--danger-color);
            font-size: 0.9rem;
            margin-top: 10px;
            display: none;
            font-weight: 500;
        }
        
        /* Email Confirmation Styles */
        .email-confirmation {
            background: var(--bg-color);
            border-radius: 15px;
            padding: 30px;
            margin-top: 25px;
            text-align: center;
            transition: background 0.3s ease;
        }
        
        .email-confirmation h3 {
            color: var(--success-color);
            margin-bottom: 20px;
            font-size: 1.5rem;
            font-weight: 600;
        }
        
        .email-confirmation p {
            margin-bottom: 15px;
            font-size: 1.1rem;
        }
        
        .email-confirmation .email-address {
            font-weight: 600;
            color: var(--info-color);
            font-size: 1.2rem;
        }
        
        /* Student Details Modal Styles */
        .student-details-modal {
            background: var(--bg-color);
            border-radius: 15px;
            padding: 25px;
            margin-top: 25px;
            transition: background 0.3s ease;
        }
        
        .student-details-header {
            display: flex;
            align-items: center;
            margin-bottom: 25px;
            gap: 20px;
        }
        
        .student-details-avatar {
            width: 80px;
            height: 80px;
            border-radius: 50%;
            background: var(--bg-color);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            position: relative;
            overflow: hidden;
        }
        
        .student-details-avatar.team1 {
            color: var(--team1-color);
        }
        
        .student-details-avatar.team2 {
            color: var(--team2-color);
        }
        
        .student-details-avatar.team3 {
            color: var(--team3-color);
        }
        
        .student-details-avatar.team4 {
            color: var(--team4-color);
        }
        
        .student-details-info h3 {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .student-details-info p {
            font-size: 1rem;
            color: var(--dark-color);
        }
        
        .student-details-section {
            margin-bottom: 25px;
        }
        
        .student-details-section h4 {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--primary-color);
        }
        
        .student-event-details {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 12px 15px;
            border-radius: 10px;
            background: var(--card-bg);
            margin-bottom: 10px;
            transition: all 0.3s ease;
        }
        
        .student-event-details:hover {
            background: var(--bg-color);
            transform: translateX(5px);
        }
        
        .student-event-details-left {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .student-event-details-right {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .student-event-grade-badge {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: white;
            font-size: 0.8rem;
        }
        
        /* Floating Action Button */
        .fab {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--gradient-primary);
            color: white;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            transition: all 0.3s ease;
            z-index: 100;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .fab:hover {
            transform: scale(1.1);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
        }
        
        /* Loading Spinner */
        .spinner {
            display: none;
            width: 50px;
            height: 50px;
            border: 5px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s ease-in-out infinite;
            margin: 20px auto;
        }
        
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
        
        /* Notification Toast */
        .toast {
            position: fixed;
            bottom: 30px;
            left: 30px;
            background: var(--card-bg);
            color: var(--text-color);
            padding: 15px 25px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            display: none;
            align-items: center;
            gap: 15px;
            z-index: 1000;
            max-width: 400px;
        }
        
        .toast.show {
            display: flex;
            animation: slideIn 0.3s ease-out;
        }
        
        @keyframes slideIn {
            from {
                transform: translateX(-100%);
                opacity: 0;
            }
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }
        
        .toast.success {
            border-left: 4px solid var(--success-color);
        }
        
        .toast.error {
            border-left: 4px solid var(--danger-color);
        }
        
        .toast.info {
            border-left: 4px solid var(--info-color);
        }
        
        .toast.warning {
            border-left: 4px solid var(--warning-color);
        }
        
        .toast i {
            font-size: 1.5rem;
        }
        
        .toast.success i {
            color: var(--success-color);
        }
        
        .toast.error i {
            color: var(--danger-color);
        }
        
        .toast.info i {
            color: var(--info-color);
        }
        
        .toast.warning i {
            color: var(--warning-color);
        }
        
        .toast-message {
            flex: 1;
        }
        
        .toast-title {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .toast-description {
            font-size: 0.9rem;
        }
        
        .toast-close {
            background: none;
            border: none;
            font-size: 1.2rem;
            cursor: pointer;
            color: var(--dark-color);
        }
        
        @media (max-width: 768px) {
            .dashboard-stats {
                justify-content: center;
            }
            
            .team-header, .students-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .team-members-title {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
            
            .team-leaders {
                flex-direction: column;
            }
            
            .controls, .students-controls {
                flex-direction: column;
            }
            
            .search-box, .students-search-box {
                max-width: 100%;
            }
            
            .events-container, .students-container {
                grid-template-columns: 1fr;
            }
            
            .modal-details {
                grid-template-columns: 1fr;
            }
            
            .grade-options {
                grid-template-columns: 1fr;
            }
            
            .team-members-grid {
                grid-template-columns: 1fr;
            }
            
            .modal-actions {
                flex-direction: column;
            }
            
            .student-select {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .student-select select {
                width: 100%;
            }
            
            .student-checkboxes {
                grid-template-columns: 1fr;
            }
            
            .password-input-group {
                flex-direction: column;
            }
            
            .student-grade-row {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
            
            .student-grade-select {
                width: 100%;
            }
            
            .student-details-header {
                flex-direction: column;
                text-align: center;
            }
            
            .student-event-details {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
            
            .toast {
                left: 20px;
                right: 20px;
                max-width: none;
            }
            
            .fab {
                bottom: 20px;
                right: 20px;
                width: 50px;
                height: 50px;
                font-size: 1.3rem;
            }
            
            .team-points-container {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <button class="theme-toggle" id="themeToggle">
                <i class="fas fa-moon"></i>
            </button>
            <h1>BUSHRA'2k25</h1>
            <p class="subtitle">SIDRA FRIENDS HOUSING</p>
            <div class="festival-badge">
                <i class="fas fa-star"></i> Cultural &amp; Educational Festival
            </div>
        </header>
        
        <div class="dashboard-stats">
            <div class="stat-card">
                <div class="stat-number">36</div>
                <div class="stat-label">Total Events</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">15</div>
                <div class="stat-label">Language Events</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">3</div>
                <div class="stat-label">Quiz Events</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">9</div>
                <div class="stat-label">Talent Events</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">2</div>
                <div class="stat-label">Technical Events</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">1</div>
                <div class="stat-label">Magazine Events</div>
            </div>
        </div>
        
        <!-- Points System Section -->
        <div class="points-section">
            <div class="points-title">
                <i class="fas fa-trophy"></i>
                Team Standings
            </div>
            <div class="team-points-container" id="teamPointsContainer">
                <!-- Team points will be populated by JavaScript -->
            </div>
        </div>
        
        <div class="main-tabs">
            <div class="main-tab active" data-tab="events">
                <i class="fas fa-calendar-alt"></i>
                Events
            </div>
            <div class="main-tab" data-tab="students">
                <i class="fas fa-user-graduate"></i>
                Students
            </div>
        </div>
        
        <div class="tab-content">
            <!-- Events Tab Content -->
            <div class="events-tab-content active">
                <div class="team-tabs">
                    <div class="team-tab team1 active" data-team="team1">
                        <i class="fas fa-crown"></i>&nbsp;Fustat
                    </div>
                    <div class="team-tab team2" data-team="team2">
                        <i class="fas fa-chess-rook"></i>&nbsp;Kufa
                    </div>
                    <div class="team-tab team3" data-team="team3">
                        <i class="fas fa-mosque"></i>Yathrib
                    </div>
                    <div class="team-tab team4" data-team="team4">
                        <i class="fas fa-landmark"><br><span style="background-color: rgb(255, 255, 255); font-size: 1.1rem;">&nbsp;Hebron</span></i>
                    </div>
                </div>
                
                <div class="team-content active" id="team1">
                    <div class="team-header">
                        <div class="team-name team1">&nbsp;Fustat</div>
                        <div class="team-stats">
                            <div class="stat-card team1">
                                <div class="stat-number team1">36</div>
                                <div class="stat-label">Total Events</div>
                            </div>
                            <div class="stat-card team1">
                                <div class="stat-number team1">15</div>
                                <div class="stat-label">Language Events</div>
                            </div>
                            <div class="stat-card team1">
                                <div class="stat-number team1">9</div>
                                <div class="stat-label">Talent Events</div>
                            </div>
                            <div class="stat-card team1">
                                <div class="stat-number team1" id="team1-points">0</div>
                                <div class="stat-label">Team Points</div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Team Members Section -->
                    <div class="team-members-section">
                        <div class="team-members-title team1">
                            <i class="fas fa-users"></i>
                            Team Members
                        </div>
                        
                        <div class="team-leaders">
                            <div class="leader-card team1">
                                <div class="leader-avatar team1">
                                    <i class="fas fa-crown"></i>
                                </div>
                                <div class="leader-info">
                                    <h3>ABU KHUZAIMA</h3>
                                    <p>C201 - Team Leader</p>
                                </div>
                            </div>
                            
                            <div class="leader-card team1">
                                <div class="leader-avatar team1">
                                    <i class="fas fa-user-tie"></i>
                                </div>
                                <div class="leader-info">
                                    <h3>FAIJAN ALI (BR)</h3>
                                    <p>C202 - Assistant Leader</p>
                                </div>
                            </div>
                        </div>
                        
                        <div class="team-members-grid" id="team1-members-grid">
                            <!-- Team 1 members will be populated by JavaScript -->
                        </div>
                    </div>
                    
                    <div class="controls">
                        <div class="filter-group">
                            <label for="team1-categoryFilter">Category:</label>
                            <select id="team1-categoryFilter">
                                <option value="all">All Categories</option>
                                <option value="language">Language</option>
                                <option value="quiz">Quiz</option>
                                <option value="talent">Talent</option>
                                <option value="technical">Technical</option>
                                <option value="magazine">Magazine</option>
                            </select>
                        </div>
                        
                        <div class="filter-group">
                            <label for="team1-languageFilter">Language:</label>
                            <select id="team1-languageFilter">
                                <option value="all">All Languages</option>
                                <option value="english">English</option>
                                <option value="urdu">Urdu</option>
                                <option value="arabic">Arabic</option>
                                <option value="hindi">Hindi</option>
                                <option value="multilingual">Multilingual</option>
                            </select>
                        </div>
                        
                        <div class="search-box">
                            <i class="fas fa-search"></i>
                            <input type="text" id="team1-searchInput" placeholder="Search events...">
                        </div>
                    </div>
                    
                    <div class="events-container" id="team1-events">
                        <!-- Team 1 events will be populated by JavaScript -->
                    </div>
                    <div class="no-results" id="team1-noResults" style="display: none;">
                        <i class="fas fa-search"></i>
                        <h3>No events found</h3>
                        <p>Try adjusting your filters or search query</p>
                    </div>
                </div>
                
                <div class="team-content" id="team2">
                    <div class="team-header">
                        <div class="team-name team2">&nbsp;Kufa</div>
                        <div class="team-stats">
                            <div class="stat-card team2">
                                <div class="stat-number team2">36</div>
                                <div class="stat-label">Total Events</div>
                            </div>
                            <div class="stat-card team2">
                                <div class="stat-number team2">15</div>
                                <div class="stat-label">Language Events</div>
                            </div>
                            <div class="stat-card team2">
                                <div class="stat-number team2">9</div>
                                <div class="stat-label">Talent Events</div>
                            </div>
                            <div class="stat-card team2">
                                <div class="stat-number team2" id="team2-points">0</div>
                                <div class="stat-label">Team Points</div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Team Members Section -->
                    <div class="team-members-section">
                        <div class="team-members-title team2">
                            <i class="fas fa-users"></i>
                            Team Members
                        </div>
                        
                        <div class="team-leaders">
                            <div class="leader-card team2">
                                <div class="leader-avatar team2">
                                    <i class="fas fa-crown"></i>
                                </div>
                                <div class="leader-info">
                                    <h3>MUDDASSIR</h3>
                                    <p>C401 - Team Leader</p>
                                </div>
                            </div>
                            
                            <div class="leader-card team2">
                                <div class="leader-avatar team2">
                                    <i class="fas fa-user-tie"></i>
                                </div>
                                <div class="leader-info">
                                    <h3>SAJID</h3>
                                    <p>C402 - Assistant Leader</p>
                                </div>
                            </div>
                        </div>
                        
                        <div class="team-members-grid" id="team2-members-grid">
                            <!-- Team 2 members will be populated by JavaScript -->
                        </div>
                    </div>
                    
                    <div class="controls">
                        <div class="filter-group">
                            <label for="team2-categoryFilter">Category:</label>
                            <select id="team2-categoryFilter">
                                <option value="all">All Categories</option>
                                <option value="language">Language</option>
                                <option value="quiz">Quiz</option>
                                <option value="talent">Talent</option>
                                <option value="technical">Technical</option>
                                <option value="magazine">Magazine</option>
                            </select>
                        </div>
                        
                        <div class="filter-group">
                            <label for="team2-languageFilter">Language:</label>
                            <select id="team2-languageFilter">
                                <option value="all">All Languages</option>
                                <option value="english">English</option>
                                <option value="urdu">Urdu</option>
                                <option value="arabic">Arabic</option>
                                <option value="hindi">Hindi</option>
                                <option value="multilingual">Multilingual</option>
                            </select>
                        </div>
                        
                        <div class="search-box">
                            <i class="fas fa-search"></i>
                            <input type="text" id="team2-searchInput" placeholder="Search events...">
                        </div>
                    </div>
                    
                    <div class="events-container" id="team2-events">
                        <!-- Team 2 events will be populated by JavaScript -->
                    </div>
                    <div class="no-results" id="team2-noResults" style="display: none;">
                        <i class="fas fa-search"></i>
                        <h3>No events found</h3>
                        <p>Try adjusting your filters or search query</p>
                    </div>
                </div>
                
                <div class="team-content" id="team3">
                    <div class="team-header">
                        <div class="team-name team3">Yathrib</div>
                        <div class="team-stats">
                            <div class="stat-card team3">
                                <div class="stat-number team3">36</div>
                                <div class="stat-label">Total Events</div>
                            </div>
                            <div class="stat-card team3">
                                <div class="stat-number team3">15</div>
                                <div class="stat-label">Language Events</div>
                            </div>
                            <div class="stat-card team3">
                                <div class="stat-number team3">9</div>
                                <div class="stat-label">Talent Events</div>
                            </div>
                            <div class="stat-card team3">
                                <div class="stat-number team3" id="team3-points">0</div>
                                <div class="stat-label">Team Points</div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Team Members Section -->
                    <div class="team-members-section">
                        <div class="team-members-title team3">
                            <i class="fas fa-users"></i>
                            Team Members
                        </div>
                        
                        <div class="team-leaders">
                            <div class="leader-card team3">
                                <div class="leader-avatar team3">
                                    <i class="fas fa-crown"></i>
                                </div>
                                <div class="leader-info">
                                    <h3>SAMEER</h3>
                                    <p>C601 - Team Leader</p>
                                </div>
                            </div>
                            
                            <div class="leader-card team3">
                                <div class="leader-avatar team3">
                                    <i class="fas fa-user-tie"></i>
                                </div>
                                <div class="leader-info">
                                    <h3>HIFZUR RAHMAN</h3>
                                    <p>C602 - Assistant Leader</p>
                                </div>
                            </div>
                        </div>
                        
                        <div class="team-members-grid" id="team3-members-grid">
                            <!-- Team 3 members will be populated by JavaScript -->
                        </div>
                    </div>
                    
                    <div class="controls">
                        <div class="filter-group">
                            <label for="team3-categoryFilter">Category:</label>
                            <select id="team3-categoryFilter">
                                <option value="all">All Categories</option>
                                <option value="language">Language</option>
                                <option value="quiz">Quiz</option>
                                <option value="talent">Talent</option>
                                <option value="technical">Technical</option>
                                <option value="magazine">Magazine</option>
                            </select>
                        </div>
                        
                        <div class="filter-group">
                            <label for="team3-languageFilter">Language:</label>
                            <select id="team3-languageFilter">
                                <option value="all">All Languages</option>
                                <option value="english">English</option>
                                <option value="urdu">Urdu</option>
                                <option value="arabic">Arabic</option>
                                <option value="hindi">Hindi</option>
                                <option value="multilingual">Multilingual</option>
                            </select>
                        </div>
                        
                        <div class="search-box">
                            <i class="fas fa-search"></i>
                            <input type="text" id="team3-searchInput" placeholder="Search events...">
                        </div>
                    </div>
                    
                    <div class="events-container" id="team3-events">
                        <!-- Team 3 events will be populated by JavaScript -->
                    </div>
                    <div class="no-results" id="team3-noResults" style="display: none;">
                        <i class="fas fa-search"></i>
                        <h3>No events found</h3>
                        <p>Try adjusting your filters or search query</p>
                    </div>
                </div>
                
                <div class="team-content" id="team4">
                    <div class="team-header">
                        <div class="team-name team4">&nbsp;Hebron</div>
                        <div class="team-stats">
                            <div class="stat-card team4">
                                <div class="stat-number team4">36</div>
                                <div class="stat-label">Total Events</div>
                            </div>
                            <div class="stat-card team4">
                                <div class="stat-number team4">15</div>
                                <div class="stat-label">Language Events</div>
                            </div>
                            <div class="stat-card team4">
                                <div class="stat-number team4">9</div>
                                <div class="stat-label">Talent Events</div>
                            </div>
                            <div class="stat-card team4">
                                <div class="stat-number team4" id="team4-points">0</div>
                                <div class="stat-label">Team Points</div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Team Members Section -->
                    <div class="team-members-section">
                        <div class="team-members-title team4">
                            <i class="fas fa-users"></i>
                            Team Members
                        </div>
                        
                        <div class="team-leaders">
                            <div class="leader-card team4">
                                <div class="leader-avatar team4">
                                    <i class="fas fa-crown"></i>
                                </div>
                                <div class="leader-info">
                                    <h3>IRFAN KHAN</h3>
                                    <p>C801 - Team Leader</p>
                                </div>
                            </div>
                            
                            <div class="leader-card team4">
                                <div class="leader-avatar team4">
                                    <i class="fas fa-user-tie"></i>
                                </div>
                                <div class="leader-info">
                                    <h3>TAHSEEN RAZA</h3>
                                    <p>C802 - Assistant Leader</p>
                                </div>
                            </div>
                        </div>
                        
                        <div class="team-members-grid" id="team4-members-grid">
                            <!-- Team 4 members will be populated by JavaScript -->
                        </div>
                    </div>
                    
                    <div class="controls">
                        <div class="filter-group">
                            <label for="team4-categoryFilter">Category:</label>
                            <select id="team4-categoryFilter">
                                <option value="all">All Categories</option>
                                <option value="language">Language</option>
                                <option value="quiz">Quiz</option>
                                <option value="talent">Talent</option>
                                <option value="technical">Technical</option>
                                <option value="magazine">Magazine</option>
                            </select>
                        </div>
                        
                        <div class="filter-group">
                            <label for="team4-languageFilter">Language:</label>
                            <select id="team4-languageFilter">
                                <option value="all">All Languages</option>
                                <option value="english">English</option>
                                <option value="urdu">Urdu</option>
                                <option value="arabic">Arabic</option>
                                <option value="hindi">Hindi</option>
                                <option value="multilingual">Multilingual</option>
                            </select>
                        </div>
                        
                        <div class="search-box">
                            <i class="fas fa-search"></i>
                            <input type="text" id="team4-searchInput" placeholder="Search events...">
                        </div>
                    </div>
                    
                    <div class="events-container" id="team4-events">
                        <!-- Team 4 events will be populated by JavaScript -->
                    </div>
                    <div class="no-results" id="team4-noResults" style="display: none;">
                        <i class="fas fa-search"></i>
                        <h3>No events found</h3>
                        <p>Try adjusting your filters or search query</p>
                    </div>
                </div>
            </div>
            
            <!-- Students Tab Content -->
            <div class="students-tab-content">
                <div class="students-content active" id="students">
                    <div class="students-header">
                        <div class="students-title">All Students</div>
                        <div class="team-stats">
                            <div class="stat-card">
                                <div class="stat-number">36</div>
                                <div class="stat-label">Total Students</div>
                            </div>
                            <div class="stat-card">
                                <div class="stat-number">9</div>
                                <div class="stat-label">Team 1 Students</div>
                            </div>
                            <div class="stat-card">
                                <div class="stat-number">9</div>
                                <div class="stat-label">Team 2 Students</div>
                            </div>
                            <div class="stat-card">
                                <div class="stat-number">9</div>
                                <div class="stat-label">Team 3 Students</div>
                            </div>
                            <div class="stat-card">
                                <div class="stat-number">9</div>
                                <div class="stat-label">Team 4 Students</div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="students-controls">
                        <div class="students-filter-group">
                            <label for="students-teamFilter">Team:</label>
                            <select id="students-teamFilter">
                                <option value="all">All Teams</option>
                                <option value="team1">Team 1: Fustat</option>
                                <option value="team2">Team 2: Kufa</option>
                                <option value="team3">Team 3: Yathrib</option>
                                <option value="team4">Team 4: Hebron</option>
                            </select>
                        </div>
                        
                        <div class="students-filter-group">
                            <label for="students-eventsFilter">Events:</label>
                            <select id="students-eventsFilter">
                                <option value="all">All Events</option>
                                <option value="assigned">Assigned Events</option>
                                <option value="graded">Graded Events</option>
                                <option value="ungraded">Ungraded Events</option>
                            </select>
                        </div>
                        
                        <div class="students-search-box">
                            <i class="fas fa-search"></i>
                            <input type="text" id="students-searchInput" placeholder="Search students...">
                        </div>
                    </div>
                    
                    <div class="students-container" id="students-container">
                        <!-- Students will be populated by JavaScript -->
                    </div>
                    <div class="no-students" id="no-students" style="display: none;">
                        <i class="fas fa-user-graduate"></i>
                        <h3>No students found</h3>
                        <p>Try adjusting your filters or search query</p>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Floating Action Button -->
        <button class="fab" id="fabButton">
            <i class="fas fa-plus"></i>
        </button>
        
        <!-- Event Details Modal -->
        <div class="modal" id="eventModal">
            <div class="modal-content">
                <span class="close-modal" id="closeModal">×</span>
                <h2 id="modalTitle">Event Details</h2>
                <div id="modalBody">
                    <!-- Modal content will be populated by JavaScript -->
                </div>
            </div>
        </div>
        
        <!-- Student Details Modal -->
        <div class="modal" id="studentDetailsModal">
            <div class="modal-content">
                <span class="close-modal" id="closeStudentDetailsModal">×</span>
                <h2 id="studentDetailsModalTitle">Student Details</h2>
                <div id="studentDetailsModalBody">
                    <!-- Modal content will be populated by JavaScript -->
                </div>
            </div>
        </div>
        
        <!-- Password Verification Modal -->
        <div class="modal" id="passwordModal">
            <div class="modal-content">
                <span class="close-modal" id="closePasswordModal">×</span>
                <h2 id="passwordModalTitle">Password Verification</h2>
                <div class="password-modal">
                    <div class="password-hint">
                        Please enter the password to access this function.
                    </div>
                    <div class="password-input-group">
                        <input type="password" id="passwordInput" placeholder="Enter password">
                        <button class="btn btn-primary" id="verifyPasswordBtn">Verify</button>
                    </div>
                    <div class="password-error" id="passwordError">
                        Incorrect password. Please try again.
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Student Selection Modal -->
        <div class="modal" id="studentSelectionModal">
            <div class="modal-content">
                <span class="close-modal" id="closeStudentSelectionModal">×</span>
                <h2 id="studentSelectionModalTitle">Select Students</h2>
                <div id="studentSelectionModalBody">
                    <!-- Modal content will be populated by JavaScript -->
                </div>
            </div>
        </div>
        
        <!-- Student Grading Modal -->
        <div class="modal" id="studentGradingModal">
            <div class="modal-content">
                <span class="close-modal" id="closeStudentGradingModal">×</span>
                <h2 id="studentGradingModalTitle">Assign Grades to Students</h2>
                <div id="studentGradingModalBody">
                    <!-- Modal content will be populated by JavaScript -->
                </div>
            </div>
        </div>
        
        <!-- Edit Program Modal -->
        <div class="modal" id="editProgramModal">
            <div class="modal-content">
                <span class="close-modal" id="closeEditProgramModal">×</span>
                <h2 id="editProgramModalTitle">Edit Program</h2>
                <div class="edit-program-form">
                    <form id="editProgramForm">
                        <div class="form-group">
                            <label for="editProgramName">Program Name</label>
                            <input type="text" id="editProgramName" required="">
                        </div>
                        <div class="form-group">
                            <label for="editProgramCategory">Category</label>
                            <select id="editProgramCategory" required="">
                                <option value="language">Language</option>
                                <option value="quiz">Quiz</option>
                                <option value="talent">Talent</option>
                                <option value="technical">Technical</option>
                                <option value="magazine">Magazine</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="editProgramLanguage">Language</label>
                            <select id="editProgramLanguage" required="">
                                <option value="english">English</option>
                                <option value="urdu">Urdu</option>
                                <option value="arabic">Arabic</option>
                                <option value="hindi">Hindi</option>
                                <option value="multilingual">Multilingual</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="editProgramDate">Date</label>
                            <input type="date" id="editProgramDate" required="">
                        </div>
                        <div class="form-group">
                            <label for="editProgramTime">Time</label>
                            <input type="text" id="editProgramTime" placeholder="e.g., 10:00 AM" required="">
                        </div>
                        <div class="form-group">
                            <label for="editProgramVenue">Venue</label>
                            <input type="text" id="editProgramVenue" required="">
                        </div>
                        <div class="form-group">
                            <label for="editProgramDescription">Description</label>
                            <textarea id="editProgramDescription" rows="4" required=""></textarea>
                        </div>
                        <div class="form-group">
                            <button type="submit" class="btn btn-primary" id="editProgramSubmitBtn">Save Changes</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
        
        <!-- Email Confirmation Modal -->
        <div class="modal" id="emailConfirmationModal">
            <div class="modal-content">
                <span class="close-modal" id="closeEmailConfirmationModal">×</span>
                <h2>Registration Confirmation</h2>
                <div class="email-confirmation">
                    <h3><i class="fas fa-check-circle"></i> Registration Successful!</h3>
                    <p>Thank you for registering for the event. Your registration details have been received.</p>
                    <p>A confirmation email has been sent to:</p>
                    <p class="email-address">CYBERWARRIOR1596@GMAIL.COM</p>
                    <p>Please check your email for further instructions.</p>
                    <div class="modal-actions">
                        <button class="btn btn-primary" id="closeEmailConfirmationBtn">OK</button>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Notification Toast -->
        <div class="toast" id="toast">
            <i class="fas fa-info-circle"></i>
            <div class="toast-message">
                <div class="toast-title">Notification</div>
                <div class="toast-description">This is a notification message</div>
            </div>
            <button class="toast-close">×</button>
        </div>
    </div>
    
    <script>
        // Base events data with simplified names
        const baseEvents = [
            { id: 1, name: "Multilingual Translation", category: "language", language: "multilingual", date: "2023-06-15", time: "10:00 AM", venue: "Main Hall", description: "Translation competition in English, Urdu, and Arabic. Participants will be given texts to translate accurately and efficiently." },
            { id: 2, name: "Multilingual Vocabulary", category: "language", language: "multilingual", date: "2023-06-16", time: "11:00 AM", venue: "Room A101", description: "Test your vocabulary skills in English, Urdu, and Arabic. Various rounds including word meanings, synonyms, and antonyms." },
            { id: 3, name: "English Word Battle", category: "quiz", language: "english", date: "2023-06-10", time: "2:00 PM", venue: "Auditorium", description: "English word battle competition where participants compete to form words, solve anagrams, and demonstrate language prowess." },
            { id: 4, name: "Arabic Elocution", category: "language", language: "arabic", date: "2023-06-17", time: "9:00 AM", venue: "Room B201", description: "Arabic elocution competition focusing on pronunciation, fluency, and expression in classical Arabic." },
            { id: 5, name: "Qawwali Performance", category: "talent", language: "urdu", date: "2023-06-18", time: "4:00 PM", venue: "Open Ground", description: "Traditional Qawwali music performance competition. Teams will perform classic and contemporary Qawwalis." },
            { id: 6, name: "General Knowledge Quiz", category: "quiz", language: "english", date: "2023-06-12", time: "1:00 PM", venue: "Conference Hall", description: "General knowledge quiz covering various topics including history, science, current affairs, and culture." },
            { id: 7, name: "Geography Competition", category: "technical", language: "english", date: "2023-06-20", time: "3:00 PM", venue: "Computer Lab", description: "Geography-based technical competition using GIS software and mapping tools to solve real-world problems." },
            { id: 8, name: "English Dictionary", category: "language", language: "english", date: "2023-06-21", time: "10:00 AM", venue: "Library", description: "Create a specialized English dictionary on a given topic. Focus on definitions, etymology, and usage examples." },
            { id: 9, name: "Urdu Dictionary", category: "language", language: "urdu", date: "2023-06-22", time: "11:00 AM", venue: "Library", description: "Compile a comprehensive Urdu dictionary for a specific domain, including regional variations and idioms." },
            { id: 10, name: "Arabic Dictionary", category: "language", language: "arabic", date: "2023-06-23", time: "9:00 AM", venue: "Library", description: "Arabic dictionary creation competition focusing on classical and modern Arabic vocabulary." },
            { id: 11, name: "English Conversation", category: "language", language: "english", date: "2023-06-13", time: "2:00 PM", venue: "Language Lab", description: "English conversation skills competition with impromptu topics and situational dialogues." },
            { id: 12, name: "Urdu Conversation", category: "language", language: "urdu", date: "2023-06-14", time: "3:00 PM", venue: "Language Lab", description: "Urdu conversation competition testing fluency, vocabulary, and cultural expressions in various scenarios." },
            { id: 13, name: "Arabic Conversation", category: "language", language: "arabic", date: "2023-06-24", time: "10:00 AM", venue: "Language Lab", description: "Arabic conversation competition focusing on modern standard Arabic and dialectal variations." },
            { id: 14, name: "Reverse Quiz", category: "quiz", language: "english", date: "2023-06-25", time: "2:00 PM", venue: "Quiz Hall", description: "Unique quiz format where participants provide questions for given answers, testing creativity and knowledge." },
            { id: 15, name: "Math & IQ Competition", category: "talent", language: "english", date: "2023-06-11", time: "11:00 AM", venue: "Math Lab", description: "Mathematics and intelligence quotient competition with logical reasoning, puzzles, and problem-solving challenges." },
            { id: 16, name: "Arabic Typing", category: "talent", language: "arabic", date: "2023-06-26", time: "1:00 PM", venue: "Computer Lab", description: "Arabic typing speed and accuracy competition using standard Arabic keyboard layouts." },
            { id: 17, name: "English Typing", category: "talent", language: "english", date: "2023-06-09", time: "10:00 AM", venue: "Computer Lab", description: "English typing competition measuring speed, accuracy, and efficiency in various typing tasks." },
            { id: 18, name: "Picture Description", category: "talent", language: "urdu", date: "2023-06-27", time: "3:00 PM", venue: "AV Room", description: "Urdu picture description competition where participants describe images with creativity and language skills." },
            { id: 19, name: "Multilingual Reading", category: "language", language: "multilingual", date: "2023-06-28", time: "11:00 AM", venue: "Library", description: "Multilingual reading competition with passages in English, Urdu, and Arabic testing comprehension and expression." },
            { id: 20, name: "English Reading", category: "language", language: "english", date: "2023-06-08", time: "2:00 PM", venue: "Library", description: "English reading competition focusing on pronunciation, fluency, and comprehension of various texts." },
            { id: 21, name: "Urdu Reading", category: "language", language: "urdu", date: "2023-06-07", time: "3:00 PM", venue: "Library", description: "Urdu reading competition with classical and contemporary texts, emphasizing proper pronunciation and expression." },
            { id: 22, name: "Hindi Reading", category: "language", language: "hindi", date: "2023-06-29", time: "10:00 AM", venue: "Library", description: "Hindi reading competition featuring diverse texts from literature, poetry, and current affairs." },
            { id: 23, name: "Arabic Reading", category: "language", language: "arabic", date: "2023-06-30", time: "9:00 AM", venue: "Library", description: "Arabic reading competition with classical and modern texts, focusing on tajweed and comprehension." },
            { id: 24, name: "Children Magazine", category: "magazine", language: "multilingual", date: "2023-07-01", time: "1:00 PM", venue: "Art Room", description: "Group competition to create a children's magazine with articles, stories, and illustrations in multiple languages." },
            { id: 25, name: "Sudoku", category: "talent", language: "english", date: "2023-06-05", time: "11:00 AM", venue: "Game Room", description: "Intermediate level Sudoku competition with time-based challenges and varying difficulty levels." },
            { id: 26, name: "Hindi Knowledge", category: "language", language: "hindi", date: "2023-07-02", time: "2:00 PM", venue: "Main Hall", description: "Hindi knowledge and literature competition testing expertise in Hindi language, poetry, and cultural knowledge." },
            { id: 27, name: "IT Presentation", category: "technical", language: "english", date: "2023-07-03", time: "10:00 AM", venue: "IT Lab", description: "IT-focused PowerPoint presentation competition on emerging technologies and innovations." },
            { id: 28, name: "Urdu Song", category: "talent", language: "urdu", date: "2023-07-04", time: "4:00 PM", venue: "Music Room", description: "Urdu song competition with categories for classical, folk, and contemporary Urdu music." },
            { id: 29, name: "English Song", category: "talent", language: "english", date: "2023-06-06", time: "3:00 PM", venue: "Music Room", description: "English song competition featuring various genres including pop, rock, classical, and musical theater." },
            { id: 30, name: "Arabic Song", category: "talent", language: "arabic", date: "2023-07-05", time: "5:00 PM", venue: "Music Room", description: "Arabic song competition showcasing traditional and modern Arabic music from different regions." },
            { id: 31, name: "Speech & Song", category: "talent", language: "multilingual", date: "2023-07-06", time: "2:00 PM", venue: "Auditorium", description: "Combined speech and song performance competition where participants deliver a speech followed by a related song." },
            { id: 32, name: "Arabic Speech", category: "language", language: "arabic", date: "2023-07-07", time: "11:00 AM", venue: "Main Hall", description: "Arabic speech competition on various topics, testing oratory skills, content, and delivery in Arabic." },
            { id: 33, name: "English Speech", category: "language", language: "english", date: "2023-06-04", time: "1:00 PM", venue: "Main Hall", description: "English speech competition with prepared and impromptu speeches on diverse topics." },
            { id: 34, name: "Urdu Speech", category: "language", language: "urdu", date: "2023-07-08", time: "3:00 PM", venue: "Main Hall", description: "Urdu speech competition focusing on eloquence, content, and delivery in formal Urdu." },
            { id: 35, name: "Group Song", category: "talent", language: "multilingual", date: "2023-07-09", time: "4:00 PM", venue: "Auditorium", description: "Group song competition with performances in multiple languages, harmony, and choreography." },
            { id: 36, name: "Group Song", category: "talent", language: "multilingual", date: "2023-07-10", time: "5:00 PM", venue: "Auditorium", description: "Additional group song competition for teams who couldn't participate in the first round." }
        ];
        
        // Base teams data with chest numbers
        const baseTeamsData = {
            team1: {
                name: "Team 1: Fustat",
                leader: "ABU KHUZAIMA",
                assistantLeader: "FAIJAN ALI (BR)",
                members: [
                    { name: "ABU KHUZAIMA", role: "leader", chestNumber: "C201" },
                    { name: "FAIJAN ALI (BR)", role: "assistant leader", chestNumber: "C202" },
                    { name: "IJMAMUL", role: "candidates", chestNumber: "C203" },
                    { name: "NURULAIN", role: "candidates", chestNumber: "C204" },
                    { name: "SAGIR", role: "candidates", chestNumber: "C205" },
                    { name: "MUZAMMIL", role: "candidates", chestNumber: "C206" },
                    { name: "MD ZIYAULLAH ANSARI", role: "candidates", chestNumber: "C207" },
                    { name: "KAIF", role: "candidates", chestNumber: "C208" },
                    { name: "HABIBULLAH", role: "candidates", chestNumber: "C209" }
                ]
            },
            team2: {
                name: "Team 2: Kufa",
                leader: "MUDDASSIR",
                assistantLeader: "SAJID",
                members: [
                    { name: "MUDDASSIR", role: "leader", chestNumber: "C401" },
                    { name: "SAJID", role: "assistant leader", chestNumber: "C402" },
                    { name: "SHAYAN", role: "candidates", chestNumber: "C403" },
                    { name: "BILAL", role: "candidates", chestNumber: "C404" },
                    { name: "AMMAR", role: "candidates", chestNumber: "C405" },
                    { name: "HAMID", role: "candidates", chestNumber: "C406" },
                    { name: "MUKADDAS", role: "candidates", chestNumber: "C407" },
                    { name: "JISHAN(JH)", role: "candidates", chestNumber: "C408" },
                    { name: "SUHEL RAZA", role: "candidates", chestNumber: "C409" }
                ]
            },
            team3: {
                name: "Team 3: Yathrib",
                leader: "SAMEER",
                assistantLeader: "HIFZUR RAHMAN",
                members: [
                    { name: "SAMEER", role: "leader", chestNumber: "C601" },
                    { name: "HIFZUR RAHMAN", role: "assistant leader", chestNumber: "C602" },
                    { name: "ASHAD", role: "candidates", chestNumber: "C603" },
                    { name: "ROOH FAIJ", role: "candidates", chestNumber: "C604" },
                    { name: "ABU SHAHMA", role: "candidates", chestNumber: "C605" },
                    { name: "ANAS", role: "candidates", chestNumber: "C606" },
                    { name: "FAIZAN ALI (MP)", role: "candidates", chestNumber: "C607" },
                    { name: "MOSHAHID", role: "candidates", chestNumber: "C608" },
                    { name: "ZIKRULLAH", role: "candidates", chestNumber: "C609" }
                ]
            },
            team4: {
                name: "Team 4: Hebron",
                leader: "IRFAN KHAN",
                assistantLeader: "TAHSEEN RAZA",
                members: [
                    { name: "IRFAN KHAN", role: "leader", chestNumber: "C801" },
                    { name: "TAHSEEN RAZA", role: "assistant leader", chestNumber: "C802" },
                    { name: "SAEED (JH)", role: "candidates", chestNumber: "C803" },
                    { name: "ASHRAF (UP)", role: "candidates", chestNumber: "C804" },
                    { name: "SAEEDUR RH", role: "candidates", chestNumber: "C805" },
                    { name: "SUFIYAN", role: "candidates", chestNumber: "C806" },
                    { name: "ZEESHAN (BR)", role: "candidates", chestNumber: "C807" },
                    { name: "ABU BAKAR", role: "candidates", chestNumber: "C808" },
                    { name: "ASHRAF ANSARI (JH)", role: "candidates", chestNumber: "C809" }
                ]
            }
        };
        
        // Password for protected actions
        const ADMIN_PASSWORD = "1600";
        
        // Team passwords
        const TEAM_PASSWORDS = {
            team1: "fustat2025",
            team2: "kufa2025",
            team3: "yathrib2025",
            team4: "hebron2025"
        };
        
        // Enhanced grade names mapping
        const gradeNames = {
            'first': '1st Place',
            'second': '2nd Place',
            'third': '3rd Place',
            'a': 'A Grade',
            'b': 'B Grade',
            'c': 'C Grade',
            'd': 'D Grade',
            'participant': 'Participant',
            'honorable': 'Honorable Mention',
            'round1': 'Round 1 Winner',
            'round2': 'Round 2 Winner'
        };
        
        // Points mapping for grades
        const gradePoints = {
            'first': 10,
            'second': 8,
            'third': 6,
            'a': 5,
            'b': 4,
            'c': 3,
            'd': 2,
            'participant': 1,
            'honorable': 1,
            'round1': 2,
            'round2': 3
        };
        
        // Current event for editing
        let currentEventForEditing = null;
        let currentTeamForEditing = '';
        
        // Current event for student selection
        let currentEventForSelection = null;
        let currentTeamForSelection = '';
        
        // Current event for student grading
        let currentEventForGrading = null;
        let currentTeamForGrading = '';
        
        // Current student for details
        let currentStudentForDetails = null;
        
        // Password verification callback
        let passwordVerifiedCallback = null;
        
        // DOM elements
        const mainTabs = document.querySelectorAll('.main-tab');
        const teamTabs = document.querySelectorAll('.team-tab');
        const teamContents = document.querySelectorAll('.team-content');
        const studentsContent = document.getElementById('students');
        const eventModal = document.getElementById('eventModal');
        const studentDetailsModal = document.getElementById('studentDetailsModal');
        const closeModal = document.getElementById('closeModal');
        const closeStudentDetailsModal = document.getElementById('closeStudentDetailsModal');
        const modalTitle = document.getElementById('modalTitle');
        const modalBody = document.getElementById('modalBody');
        const studentDetailsModalTitle = document.getElementById('studentDetailsModalTitle');
        const studentDetailsModalBody = document.getElementById('studentDetailsModalBody');
        const themeToggle = document.getElementById('themeToggle');
        const fabButton = document.getElementById('fabButton');
        const teamPointsContainer = document.getElementById('teamPointsContainer');
        
        // Password Modal elements
        const passwordModal = document.getElementById('passwordModal');
        const closePasswordModal = document.getElementById('closePasswordModal');
        const passwordModalTitle = document.getElementById('passwordModalTitle');
        const passwordInput = document.getElementById('passwordInput');
        const verifyPasswordBtn = document.getElementById('verifyPasswordBtn');
        const passwordError = document.getElementById('passwordError');
        
        // Student Selection Modal elements
        const studentSelectionModal = document.getElementById('studentSelectionModal');
        const closeStudentSelectionModal = document.getElementById('closeStudentSelectionModal');
        const studentSelectionModalTitle = document.getElementById('studentSelectionModalTitle');
        const studentSelectionModalBody = document.getElementById('studentSelectionModalBody');
        
        // Student Grading Modal elements
        const studentGradingModal = document.getElementById('studentGradingModal');
        const closeStudentGradingModal = document.getElementById('closeStudentGradingModal');
        const studentGradingModalTitle = document.getElementById('studentGradingModalTitle');
        const studentGradingModalBody = document.getElementById('studentGradingModalBody');
        
        // Edit Program Modal elements
        const editProgramModal = document.getElementById('editProgramModal');
        const closeEditProgramModal = document.getElementById('closeEditProgramModal');
        const editProgramModalTitle = document.getElementById('editProgramModalTitle');
        const editProgramForm = document.getElementById('editProgramForm');
        const editProgramNameInput = document.getElementById('editProgramName');
        const editProgramCategorySelect = document.getElementById('editProgramCategory');
        const editProgramLanguageSelect = document.getElementById('editProgramLanguage');
        const editProgramDateInput = document.getElementById('editProgramDate');
        const editProgramTimeInput = document.getElementById('editProgramTime');
        const editProgramVenueInput = document.getElementById('editProgramVenue');
        const editProgramDescriptionTextarea = document.getElementById('editProgramDescription');
        const editProgramSubmitBtn = document.getElementById('editProgramSubmitBtn');
        
        // Email Confirmation Modal elements
        const emailConfirmationModal = document.getElementById('emailConfirmationModal');
        const closeEmailConfirmationModal = document.getElementById('closeEmailConfirmationModal');
        const closeEmailConfirmationBtn = document.getElementById('closeEmailConfirmationBtn');
        
        // Students section elements
        const studentsTeamFilter = document.getElementById('students-teamFilter');
        const studentsEventsFilter = document.getElementById('students-eventsFilter');
        const studentsSearchInput = document.getElementById('students-searchInput');
        const studentsContainer = document.getElementById('students-container');
        const noStudents = document.getElementById('no-students');
        
        // Toast notification elements
        const toast = document.getElementById('toast');
        const toastClose = document.querySelector('.toast-close');
        const toastTitle = document.querySelector('.toast-title');
        const toastDescription = document.querySelector('.toast-description');
        
        // Initialize teams
        function initializeTeams() {
            Object.keys(baseTeamsData).forEach(teamId => {
                renderTeamEvents(teamId);
                renderTeamMembers(teamId);
                setupTeamEventListeners(teamId);
            });
            
            renderStudents();
            renderTeamPoints();
            setupStudentsEventListeners();
            setupThemeToggle();
            setupPasswordModal();
            setupStudentSelectionModal();
            setupStudentGradingModal();
            setupEditProgramModal();
            setupEmailConfirmationModal();
            setupToastNotifications();
            setupFabButton();
            setupMainTabs();
            setupTeamTabs();
        }
        
        // Load saved data from localStorage
        function loadSavedData() {
            // Load saved events
            const savedEvents = localStorage.getItem('editedEvents');
            if (savedEvents) {
                try {
                    const parsedEvents = JSON.parse(savedEvents);
                    // Update the baseEvents with saved data
                    parsedEvents.forEach(savedEvent => {
                        const index = baseEvents.findIndex(e => e.id === savedEvent.id);
                        if (index !== -1) {
                            baseEvents[index] = savedEvent;
                        }
                    });
                } catch (e) {
                    console.error('Error loading saved events:', e);
                }
            }
            
            // Load saved student grades
            const savedStudentGrades = localStorage.getItem('studentGrades');
            if (savedStudentGrades) {
                try {
                    window.studentGrades = JSON.parse(savedStudentGrades);
                } catch (e) {
                    console.error('Error loading saved student grades:', e);
                    window.studentGrades = {};
                }
            } else {
                window.studentGrades = {};
            }
            
            // Load saved participants
            const savedParticipants = localStorage.getItem('eventParticipants');
            if (savedParticipants) {
                try {
                    window.eventParticipants = JSON.parse(savedParticipants);
                } catch (e) {
                    console.error('Error loading saved participants:', e);
                    window.eventParticipants = {};
                }
            } else {
                window.eventParticipants = {};
            }
            
            // Initialize with the provided student data if no saved data exists
            if (!savedEvents && !savedStudentGrades && !savedParticipants) {
                // Set up participants for the "Multilingual Translation" event (event ID 1)
                window.eventParticipants["team1-1"] = [
                    "ABU KHUZAIMA",
                    "FAIJAN ALI (BR)",
                    "IJMAMUL",
                    "NURULAIN",
                    "SAGIR",
                    "MUZAMMIL",
                    "MD ZIYAULLAH ANSARI",
                    "KAIF",
                    "HABIBULLAH"
                ];
                
                // Set grades for Team 1 students
                window.studentGrades["team1-1-ABU KHUZAIMA"] = "first";
                window.studentGrades["team1-1-FAIJAN ALI (BR)"] = "first";
                window.studentGrades["team1-1-IJMAMUL"] = "second";
                window.studentGrades["team1-1-NURULAIN"] = "first";
                window.studentGrades["team1-1-SAGIR"] = "first";
                window.studentGrades["team1-1-MUZAMMIL"] = "first";
                window.studentGrades["team1-1-MD ZIYAULLAH ANSARI"] = "first";
                window.studentGrades["team1-1-KAIF"] = "first";
                window.studentGrades["team1-1-HABIBULLAH"] = "first";
                
                // Save the initial data
                saveData();
            }
        }
        
        // Save data to localStorage
        function saveData() {
            // Save events
            localStorage.setItem('editedEvents', JSON.stringify(baseEvents));
            
            // Save student grades
            localStorage.setItem('studentGrades', JSON.stringify(window.studentGrades));
            
            // Save participants
            localStorage.setItem('eventParticipants', JSON.stringify(window.eventParticipants));
        }
        
        // Get teams data with updated events
        function getTeamsData() {
            const teamsData = {};
            
            Object.keys(baseTeamsData).forEach(teamId => {
                teamsData[teamId] = {
                    ...baseTeamsData[teamId],
                    events: [...baseEvents] // Use the updated events
                };
            });
            
            return teamsData;
        }
        
        // Get all students data
        function getAllStudents() {
            const allStudents = [];
            
            Object.keys(baseTeamsData).forEach(teamId => {
                const team = baseTeamsData[teamId];
                team.members.forEach(member => {
                    allStudents.push({
                        ...member,
                        teamId: teamId,
                        teamName: team.name
                    });
                });
            });
            
            return allStudents;
        }
        
        // Get student events and grades
        function getStudentEventsAndGrades(studentName, teamId) {
            const studentEvents = [];
            
            // Check all events to see if this student is participating
            baseEvents.forEach(event => {
                const eventKey = `${teamId}-${event.id}`;
                
                if (window.eventParticipants && window.eventParticipants[eventKey] && 
                    window.eventParticipants[eventKey].includes(studentName)) {
                    
                    const studentGradeKey = `${eventKey}-${studentName}`;
                    const grade = (window.studentGrades && window.studentGrades[studentGradeKey]) || null;
                    
                    studentEvents.push({
                        ...event,
                        grade: grade
                    });
                }
            });
            
            return studentEvents;
        }
        
        // Calculate student points
        function calculateStudentPoints(studentName, teamId) {
            let points = 0;
            
            // Get all student events
            const studentEvents = getStudentEventsAndGrades(studentName, teamId);
            
            // Calculate points for each graded event
            studentEvents.forEach(event => {
                if (event.grade && gradePoints[event.grade]) {
                    points += gradePoints[event.grade];
                }
            });
            
            return points;
        }
        
        // Calculate team points
        function calculateTeamPoints(teamId) {
            let points = 0;
            
            // Get all team members
            const team = baseTeamsData[teamId];
            if (!team) return points;
            
            // Calculate points for each member
            team.members.forEach(member => {
                points += calculateStudentPoints(member.name, teamId);
            });
            
            return points;
        }
        
        // Render team points
        function renderTeamPoints() {
            teamPointsContainer.innerHTML = '';
            
            const teams = [
                { id: 'team1', name: 'Fustat', color: 'team1' },
                { id: 'team2', name: 'Kufa', color: 'team2' },
                { id: 'team3', name: 'Yathrib', color: 'team3' },
                { id: 'team4', name: 'Hebron', color: 'team4' }
            ];
            
            // Calculate points for each team
            const teamPoints = teams.map(team => ({
                ...team,
                points: calculateTeamPoints(team.id)
            }));
            
            // Sort teams by points (descending)
            teamPoints.sort((a, b) => b.points - a.points);
            
            // Render team points cards
            teamPoints.forEach((team, index) => {
                const teamPointsCard = document.createElement('div');
                teamPointsCard.className = `team-points-card ${team.color}`;
                
                // Determine rank
                let rankClass = 'rank-other';
                if (index === 0) rankClass = 'rank-1';
                else if (index === 1) rankClass = 'rank-2';
                else if (index === 2) rankClass = 'rank-3';
                
                teamPointsCard.innerHTML = `
                    <div class="team-rank ${rankClass}">${index + 1}</div>
                    <div class="team-points-name ${team.color}">${team.name}</div>
                    <div class="team-points-number ${team.color}">${team.points}</div>
                    <div class="team-points-label">Points</div>
                `;
                
                teamPointsContainer.appendChild(teamPointsCard);
                
                // Update team points in the team header
                const teamPointsElement = document.getElementById(`${team.id}-points`);
                if (teamPointsElement) {
                    teamPointsElement.textContent = team.points;
                }
            });
        }
        
        // Render team events
        function renderTeamEvents(teamId) {
            const eventsContainer = document.getElementById(`${teamId}-events`);
            const noResults = document.getElementById(`${teamId}-noResults`);
            const categoryFilter = document.getElementById(`${teamId}-categoryFilter`);
            const languageFilter = document.getElementById(`${teamId}-languageFilter`);
            const searchInput = document.getElementById(`${teamId}-searchInput`);
            
            if (!eventsContainer || !noResults || !categoryFilter || !languageFilter || !searchInput) return;
            
            // Get filter values
            const categoryValue = categoryFilter.value;
            const languageValue = languageFilter.value;
            const searchValue = searchInput.value.toLowerCase();
            
            // Filter events
            const filteredEvents = baseEvents.filter(event => {
                const matchesCategory = categoryValue === 'all' || event.category === categoryValue;
                const matchesLanguage = languageValue === 'all' || event.language === languageValue;
                const matchesSearch = event.name.toLowerCase().includes(searchValue) || 
                                     event.description.toLowerCase().includes(searchValue);
                
                return matchesCategory && matchesLanguage && matchesSearch;
            });
            
            // Clear events container
            eventsContainer.innerHTML = '';
            
            // Show/hide no results message
            if (filteredEvents.length === 0) {
                noResults.style.display = 'block';
                return;
            }
            
            noResults.style.display = 'none';
            
            // Render events
            filteredEvents.forEach(event => {
                const eventCard = document.createElement('div');
                eventCard.className = `event-card ${teamId}`;
                
                // Get event participants
                const eventKey = `${teamId}-${event.id}`;
                const participants = (window.eventParticipants && window.eventParticipants[eventKey]) || [];
                
                eventCard.innerHTML = `
                    <div class="event-header">
                        <div>
                            <div class="event-title ${teamId}">${event.name}</div>
                            <div class="event-category category-${event.category}">${event.category}</div>
                        </div>
                    </div>
                    <div class="event-details">
                        <div class="event-detail ${teamId}">
                            <i class="fas fa-calendar"></i>
                            <span>${event.date}</span>
                        </div>
                        <div class="event-detail ${teamId}">
                            <i class="fas fa-clock"></i>
                            <span>${event.time}</span>
                        </div>
                        <div class="event-detail ${teamId}">
                            <i class="fas fa-map-marker-alt"></i>
                            <span>${event.venue}</span>
                        </div>
                        <div class="event-detail ${teamId}">
                            <i class="fas fa-language"></i>
                            <span>${event.language}</span>
                        </div>
                    </div>
                    <div class="event-participants">
                        <div class="event-participants-title">Participants (${participants.length})</div>
                        <div class="event-participants-list">
                            ${participants.length > 0 ? 
                                participants.map(participant => `
                                    <div class="participant-tag ${teamId}">
                                        <i class="fas fa-user"></i>
                                        <span>${participant}</span>
                                    </div>
                                `).join('') : 
                                '<div class="no-student-events">No participants assigned</div>'
                            }
                        </div>
                    </div>
                `;
                
                // Add click event to show event details
                eventCard.addEventListener('click', () => {
                    showEventDetails(event, teamId);
                });
                
                eventsContainer.appendChild(eventCard);
            });
        }
        
        // Render team members
        function renderTeamMembers(teamId) {
            const teamMembersGrid = document.getElementById(`${teamId}-members-grid`);
            const team = baseTeamsData[teamId];
            
            if (!teamMembersGrid || !team) return;
            
            teamMembersGrid.innerHTML = '';
            
            // Filter out the leader and assistant leader since they are already displayed
            const members = team.members.filter(member => 
                member.role !== 'leader' && member.role !== 'assistant leader'
            );
            
            members.forEach(member => {
                const memberCard = document.createElement('div');
                memberCard.className = `member-card ${teamId}`;
                
                memberCard.innerHTML = `
                    <div class="member-avatar ${teamId}">
                        <i class="fas fa-user"></i>
                    </div>
                    <div class="member-info">
                        <h4>${member.name}</h4>
                        <p>${member.chestNumber} - ${member.role}</p>
                    </div>
                `;
                
                teamMembersGrid.appendChild(memberCard);
            });
        }
        
        // Render students
        function renderStudents() {
            const allStudents = getAllStudents();
            studentsContainer.innerHTML = '';
            
            if (allStudents.length === 0) {
                noStudents.style.display = 'block';
                return;
            }
            
            noStudents.style.display = 'none';
            
            // Get filter values
            const teamFilter = studentsTeamFilter.value;
            const eventsFilter = studentsEventsFilter.value;
            const searchValue = studentsSearchInput.value.toLowerCase();
            
            // Filter students
            const filteredStudents = allStudents.filter(student => {
                const matchesTeam = teamFilter === 'all' || student.teamId === teamFilter;
                const matchesSearch = student.name.toLowerCase().includes(searchValue) || 
                                     student.chestNumber.toLowerCase().includes(searchValue);
                
                // Check events filter
                let matchesEvents = true;
                if (eventsFilter !== 'all') {
                    const studentEvents = getStudentEventsAndGrades(student.name, student.teamId);
                    
                    if (eventsFilter === 'assigned') {
                        matchesEvents = studentEvents.length > 0;
                    } else if (eventsFilter === 'graded') {
                        matchesEvents = studentEvents.some(event => event.grade !== null);
                    } else if (eventsFilter === 'ungraded') {
                        matchesEvents = studentEvents.some(event => event.grade === null);
                    }
                }
                
                return matchesTeam && matchesSearch && matchesEvents;
            });
            
            // Render students
            filteredStudents.forEach(student => {
                const studentCard = document.createElement('div');
                studentCard.className = `student-card ${student.teamId}`;
                
                // Get student events and grades
                const studentEvents = getStudentEventsAndGrades(student.name, student.teamId);
                const totalPoints = calculateStudentPoints(student.name, student.teamId);
                
                studentCard.innerHTML = `
                    <div class="student-header">
                        <div class="student-avatar ${student.teamId}">
                            <i class="fas fa-user-graduate"></i>
                        </div>
                        <div class="student-info">
                            <h3>${student.name}</h3>
                            <p>${student.chestNumber} - ${student.teamName}</p>
                        </div>
                    </div>
                    <div class="student-details">
                        <div class="student-detail ${student.teamId}">
                            <i class="fas fa-id-card"></i>
                            <span>Chest Number: ${student.chestNumber}</span>
                        </div>
                        <div class="student-detail ${student.teamId}">
                            <i class="fas fa-users"></i>
                            <span>${student.role}</span>
                        </div>
                        <div class="student-points">
                            <i class="fas fa-star"></i>
                            <span>Total Points: </span>
                            <span class="student-points-number">${totalPoints}</span>
                        </div>
                    </div>
                    <div class="student-events">
                        <div class="student-events-title">Events Participated</div>
                        ${studentEvents.length > 0 ? `
                            <div class="student-events-list">
                                ${studentEvents.map(event => `
                                    <div class="student-event-item">
                                        <div class="student-event-name">${event.name}</div>
                                        <div class="student-event-grade">
                                            ${event.grade ? `
                                                <span class="grade-badge-small ${event.grade}">${gradeNames[event.grade].charAt(0)}</span>
                                            ` : '<span class="grade-badge-small participant">P</span>'}
                                        </div>
                                    </div>
                                `).join('')}
                            </div>
                        ` : '<div class="no-student-events">No events assigned</div>'}
                    </div>
                `;
                
                // Add click event to show student details
                studentCard.addEventListener('click', () => {
                    showStudentDetails(student);
                });
                
                studentsContainer.appendChild(studentCard);
            });
        }
        
        // Show event details
        function showEventDetails(event, teamId) {
            currentEventForEditing = event;
            currentTeamForEditing = teamId;
            
            // Set modal title
            modalTitle.textContent = event.name;
            modalTitle.className = teamId;
            
            // Get event participants
            const eventKey = `${teamId}-${event.id}`;
            const participants = (window.eventParticipants && window.eventParticipants[eventKey]) || [];
            
            // Build modal content
            modalBody.innerHTML = `
                <div class="modal-details">
                    <div class="modal-detail ${teamId}">
                        <i class="fas fa-tag"></i>
                        <span>Category: ${event.category}</span>
                    </div>
                    <div class="modal-detail ${teamId}">
                        <i class="fas fa-language"></i>
                        <span>Language: ${event.language}</span>
                    </div>
                    <div class="modal-detail ${teamId}">
                        <i class="fas fa-calendar"></i>
                        <span>Date: ${event.date}</span>
                    </div>
                    <div class="modal-detail ${teamId}">
                        <i class="fas fa-clock"></i>
                        <span>Time: ${event.time}</span>
                    </div>
                    <div class="modal-detail ${teamId}">
                        <i class="fas fa-map-marker-alt"></i>
                        <span>Venue: ${event.venue}</span>
                    </div>
                    <div class="modal-detail ${teamId}">
                        <i class="fas fa-users"></i>
                        <span>Participants: ${participants.length}</span>
                    </div>
                </div>
                
                <div class="modal-description">
                    ${event.description}
                </div>
                
                <div class="event-participants">
                    <div class="event-participants-title">Participants</div>
                    <div class="event-participants-list">
                        ${participants.length > 0 ? 
                            participants.map(participant => `
                                <div class="participant-tag ${teamId}">
                                    <i class="fas fa-user"></i>
                                    <span>${participant}</span>
                                </div>
                            `).join('') : 
                            '<div class="no-student-events">No participants assigned</div>'
                        }
                    </div>
                </div>
                
                <div class="modal-actions">
                    <button class="btn btn-primary ${teamId}" id="selectStudentsBtn">
                        <i class="fas fa-user-plus"></i>
                        Select Students
                    </button>
                    <button class="btn btn-outline ${teamId}" id="gradeStudentsBtn">
                        <i class="fas fa-star"></i>
                        Grade Students
                    </button>
                    <button class="btn btn-edit" id="editEventBtn">
                        <i class="fas fa-edit"></i>
                        Edit Event
                    </button>
                </div>
            `;
            
            // Add event listeners to buttons with password protection
            document.getElementById('selectStudentsBtn').addEventListener('click', () => {
                showPasswordModal(
                    'Verify Password to Select Students',
                    () => {
                        showStudentSelectionModal(event, teamId);
                    }
                );
            });
            
            document.getElementById('gradeStudentsBtn').addEventListener('click', () => {
                showPasswordModal(
                    'Verify Password to Grade Students',
                    () => {
                        showStudentGradingModal(event, teamId);
                    }
                );
            });
            
            document.getElementById('editEventBtn').addEventListener('click', () => {
                showPasswordModal(
                    'Verify Password to Edit Event',
                    () => {
                        showEditProgramModal(event, teamId);
                    }
                );
            });
            
            // Show modal
            eventModal.style.display = 'flex';
        }
        
        // Show student details
        function showStudentDetails(student) {
            currentStudentForDetails = student;
            
            // Set modal title
            studentDetailsModalTitle.textContent = `${student.name} - ${student.chestNumber}`;
            studentDetailsModalTitle.className = student.teamId;
            
            // Get student events and grades
            const studentEvents = getStudentEventsAndGrades(student.name, student.teamId);
            const totalPoints = calculateStudentPoints(student.name, student.teamId);
            
            // Build modal content
            studentDetailsModalBody.innerHTML = `
                <div class="student-details-modal">
                    <div class="student-details-header">
                        <div class="student-details-avatar ${student.teamId}">
                            <i class="fas fa-user-graduate"></i>
                        </div>
                        <div class="student-details-info">
                            <h3>${student.name}</h3>
                            <p>${student.chestNumber} - ${student.teamName}</p>
                        </div>
                    </div>
                    
                    <div class="student-details-section">
                        <h4>Personal Information</h4>
                        <div class="modal-details">
                            <div class="modal-detail ${student.teamId}">
                                <i class="fas fa-id-card"></i>
                                <span>Chest Number: ${student.chestNumber}</span>
                            </div>
                            <div class="modal-detail ${student.teamId}">
                                <i class="fas fa-users"></i>
                                <span>Role: ${student.role}</span>
                            </div>
                            <div class="modal-detail ${student.teamId}">
                                <i class="fas fa-trophy"></i>
                                <span>Total Points: ${totalPoints}</span>
                            </div>
                            <div class="modal-detail ${student.teamId}">
                                <i class="fas fa-calendar-check"></i>
                                <span>Events: ${studentEvents.length}</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="student-details-section">
                        <h4>Event Participation</h4>
                        ${studentEvents.length > 0 ? `
                            <div class="student-events-list">
                                ${studentEvents.map(event => `
                                    <div class="student-event-details">
                                        <div class="student-event-details-left">
                                            <i class="fas fa-calendar-alt"></i>
                                            <span>${event.name}</span>
                                        </div>
                                        <div class="student-event-details-right">
                                            ${event.grade ? `
                                                <span class="student-event-grade-badge ${event.grade}">${gradeNames[event.grade].charAt(0)}</span>
                                                <span>${gradeNames[event.grade]}</span>
                                            ` : '<span class="student-event-grade-badge participant">P</span><span>Not Graded</span>'}
                                        </div>
                                    </div>
                                `).join('')}
                            </div>
                        ` : '<div class="no-student-events">No events assigned</div>'}
                    </div>
                </div>
            `;
            
            // Show modal
            studentDetailsModal.style.display = 'flex';
        }
        
        // Show student selection modal
        function showStudentSelectionModal(event, teamId) {
            currentEventForSelection = event;
            currentTeamForSelection = teamId;
            
            // Set modal title
            studentSelectionModalTitle.textContent = `Select Students for ${event.name}`;
            studentSelectionModalTitle.className = teamId;
            
            // Get team members
            const team = baseTeamsData[teamId];
            if (!team) return;
            
            // Get current participants
            const eventKey = `${teamId}-${event.id}`;
            const currentParticipants = (window.eventParticipants && window.eventParticipants[eventKey]) || [];
            
            // Build modal content
            studentSelectionModalBody.innerHTML = `
                <div class="student-selection">
                    <h3 class="${teamId}">Select students for this event</h3>
                    
                    <div class="student-select-container">
                        <div class="student-checkboxes">
                            ${team.members.map(member => `
                                <div class="checkbox-item">
                                    <input type="checkbox" id="student-${member.chestNumber}" value="${member.name}" 
                                        ${currentParticipants.includes(member.name) ? 'checked' : ''}>
                                    <label for="student-${member.chestNumber}">
                                        <strong>${member.name}</strong> (${member.chestNumber})
                                    </label>
                                </div>
                            `).join('')}
                        </div>
                        
                        <div class="selection-counter">
                            Selected: <span id="selectedCount">${currentParticipants.length}</span> students
                        </div>
                        
                        <div class="validation-message validation-success" id="selectionSuccess">
                            Students selected successfully!
                        </div>
                    </div>
                    
                    <div class="modal-actions">
                        <button class="btn btn-primary ${teamId}" id="saveSelectionBtn">
                            <i class="fas fa-save"></i>
                            Save Selection
                        </button>
                        <button class="btn btn-outline ${teamId}" id="cancelSelectionBtn">
                            <i class="fas fa-times"></i>
                            Cancel
                        </button>
                    </div>
                </div>
            `;
            
            // Add event listeners
            const checkboxes = studentSelectionModalBody.querySelectorAll('input[type="checkbox"]');
            const selectedCount = document.getElementById('selectedCount');
            const selectionSuccess = document.getElementById('selectionSuccess');
            const saveSelectionBtn = document.getElementById('saveSelectionBtn');
            const cancelSelectionBtn = document.getElementById('cancelSelectionBtn');
            
            // Update selected count when checkboxes change
            checkboxes.forEach(checkbox => {
                checkbox.addEventListener('change', () => {
                    const checked = studentSelectionModalBody.querySelectorAll('input[type="checkbox"]:checked');
                    selectedCount.textContent = checked.length;
                    
                    // Hide messages
                    selectionSuccess.style.display = 'none';
                    
                    // Enable save button if at least one student is selected
                    saveSelectionBtn.disabled = checked.length === 0;
                });
            });
            
            // Set initial state of save button
            saveSelectionBtn.disabled = currentParticipants.length === 0;
            
            // Save selection
            saveSelectionBtn.addEventListener('click', () => {
                const checked = studentSelectionModalBody.querySelectorAll('input[type="checkbox"]:checked');
                
                // Get selected student names
                const selectedStudents = Array.from(checked).map(cb => cb.value);
                
                // Save participants
                if (!window.eventParticipants) {
                    window.eventParticipants = {};
                }
                
                window.eventParticipants[eventKey] = selectedStudents;
                
                // Save to localStorage
                saveData();
                
                // Show success message
                selectionSuccess.style.display = 'block';
                
                // Update UI
                setTimeout(() => {
                    // Refresh events and students
                    renderTeamEvents(teamId);
                    renderStudents();
                    renderTeamPoints();
                    
                    // Close modal
                    studentSelectionModal.style.display = 'none';
                    
                    // Show toast notification
                    showToast('success', 'Students Selected', `Successfully selected ${selectedStudents.length} students for ${event.name}`);
                }, 1500);
            });
            
            // Cancel selection
            cancelSelectionBtn.addEventListener('click', () => {
                studentSelectionModal.style.display = 'none';
            });
            
            // Show modal
            studentSelectionModal.style.display = 'flex';
        }
        
        // Show student grading modal
        function showStudentGradingModal(event, teamId) {
            currentEventForGrading = event;
            currentTeamForGrading = teamId;
            
            // Set modal title
            studentGradingModalTitle.textContent = `Grade Students for ${event.name}`;
            studentGradingModalTitle.className = teamId;
            
            // Get event participants
            const eventKey = `${teamId}-${event.id}`;
            const participants = (window.eventParticipants && window.eventParticipants[eventKey]) || [];
            
            if (participants.length === 0) {
                showToast('warning', 'No Participants', 'Please select students for this event first');
                return;
            }
            
            // Build modal content
            studentGradingModalBody.innerHTML = `
                <div class="student-grading">
                    <h3 class="${teamId}">Assign grades to participants</h3>
                    
                    <div class="student-grade-rows">
                        ${participants.map(participant => {
                            const studentGradeKey = `${eventKey}-${participant}`;
                            const currentGrade = (window.studentGrades && window.studentGrades[studentGradeKey]) || '';
                            
                            return `
                                <div class="student-grade-row">
                                    <div class="student-name">${participant}</div>
                                    <div class="student-grade-select">
                                        <select class="grade-select" data-student="${participant}">
                                            <option value="">Select Grade</option>
                                            <option value="first" ${currentGrade === 'first' ? 'selected' : ''}>1st Place</option>
                                            <option value="second" ${currentGrade === 'second' ? 'selected' : ''}>2nd Place</option>
                                            <option value="third" ${currentGrade === 'third' ? 'selected' : ''}>3rd Place</option>
                                            <option value="a" ${currentGrade === 'a' ? 'selected' : ''}>A Grade</option>
                                            <option value="b" ${currentGrade === 'b' ? 'selected' : ''}>B Grade</option>
                                            <option value="c" ${currentGrade === 'c' ? 'selected' : ''}>C Grade</option>
                                            <option value="d" ${currentGrade === 'd' ? 'selected' : ''}>D Grade</option>
                                            <option value="participant" ${currentGrade === 'participant' ? 'selected' : ''}>Participant</option>
                                            <option value="honorable" ${currentGrade === 'honorable' ? 'selected' : ''}>Honorable Mention</option>
                                            <option value="round1" ${currentGrade === 'round1' ? 'selected' : ''}>Round 1 Winner</option>
                                            <option value="round2" ${currentGrade === 'round2' ? 'selected' : ''}>Round 2 Winner</option>
                                        </select>
                                    </div>
                                    <div class="grade-preview ${currentGrade || 'participant'}">
                                        ${currentGrade ? gradeNames[currentGrade].charAt(0) : 'P'}
                                    </div>
                                </div>
                            `;
                        }).join('')}
                    </div>
                    
                    <div class="modal-actions">
                        <button class="btn btn-primary ${teamId}" id="saveGradesBtn">
                            <i class="fas fa-save"></i>
                            Save Grades
                        </button>
                        <button class="btn btn-outline ${teamId}" id="cancelGradesBtn">
                            <i class="fas fa-times"></i>
                            Cancel
                        </button>
                    </div>
                </div>
            `;
            
            // Add event listeners
            const gradeSelects = studentGradingModalBody.querySelectorAll('.grade-select');
            const saveGradesBtn = document.getElementById('saveGradesBtn');
            const cancelGradesBtn = document.getElementById('cancelGradesBtn');
            
            // Update grade preview when selection changes
            gradeSelects.forEach(select => {
                select.addEventListener('change', () => {
                    const gradePreview = select.parentElement.nextElementSibling;
                    const selectedGrade = select.value;
                    
                    // Update preview
                    gradePreview.className = `grade-preview ${selectedGrade || 'participant'}`;
                    gradePreview.textContent = selectedGrade ? gradeNames[selectedGrade].charAt(0) : 'P';
                });
            });
            
            // Save grades
            saveGradesBtn.addEventListener('click', () => {
                // Initialize student grades if not exists
                if (!window.studentGrades) {
                    window.studentGrades = {};
                }
                
                // Save grades for each participant
                gradeSelects.forEach(select => {
                    const studentName = select.dataset.student;
                    const grade = select.value;
                    const studentGradeKey = `${eventKey}-${studentName}`;
                    
                    window.studentGrades[studentGradeKey] = grade;
                });
                
                // Save to localStorage
                saveData();
                
                // Update UI
                renderTeamEvents(teamId);
                renderStudents();
                renderTeamPoints();
                
                // Close modal
                studentGradingModal.style.display = 'none';
                
                // Show toast notification
                showToast('success', 'Grades Saved', `Successfully saved grades for ${event.name}`);
            });
            
            // Cancel grading
            cancelGradesBtn.addEventListener('click', () => {
                studentGradingModal.style.display = 'none';
            });
            
            // Show modal
            studentGradingModal.style.display = 'flex';
        }
        
        // Show edit program modal
        function showEditProgramModal(event, teamId) {
            // Set modal title
            editProgramModalTitle.textContent = `Edit Event: ${event.name}`;
            editProgramModalTitle.className = teamId;
            
            // Fill form with event data
            editProgramNameInput.value = event.name;
            editProgramCategorySelect.value = event.category;
            editProgramLanguageSelect.value = event.language;
            editProgramDateInput.value = event.date;
            editProgramTimeInput.value = event.time;
            editProgramVenueInput.value = event.venue;
            editProgramDescriptionTextarea.value = event.description;
            
            // Show modal
            editProgramModal.style.display = 'flex';
        }
        
        // Setup team event listeners
        function setupTeamEventListeners(teamId) {
            const categoryFilter = document.getElementById(`${teamId}-categoryFilter`);
            const languageFilter = document.getElementById(`${teamId}-languageFilter`);
            const searchInput = document.getElementById(`${teamId}-searchInput`);
            
            if (!categoryFilter || !languageFilter || !searchInput) return;
            
            // Add event listeners for filters
            categoryFilter.addEventListener('change', () => {
                renderTeamEvents(teamId);
            });
            
            languageFilter.addEventListener('change', () => {
                renderTeamEvents(teamId);
            });
            
            searchInput.addEventListener('input', () => {
                renderTeamEvents(teamId);
            });
        }
        
        // Setup students event listeners
        function setupStudentsEventListeners() {
            studentsTeamFilter.addEventListener('change', () => {
                renderStudents();
            });
            
            studentsEventsFilter.addEventListener('change', () => {
                renderStudents();
            });
            
            studentsSearchInput.addEventListener('input', () => {
                renderStudents();
            });
        }
        
        // Setup theme toggle
        function setupThemeToggle() {
            themeToggle.addEventListener('click', () => {
                document.body.classList.toggle('dark-theme');
                
                // Update icon
                const icon = themeToggle.querySelector('i');
                if (document.body.classList.contains('dark-theme')) {
                    icon.className = 'fas fa-sun';
                    document.documentElement.setAttribute('data-theme', 'dark');
                } else {
                    icon.className = 'fas fa-moon';
                    document.documentElement.setAttribute('data-theme', 'light');
                }
            });
        }
        
        // Setup password modal
        function setupPasswordModal() {
            closePasswordModal.addEventListener('click', () => {
                passwordModal.style.display = 'none';
                passwordInput.value = '';
                passwordError.style.display = 'none';
            });
            
            verifyPasswordBtn.addEventListener('click', () => {
                const password = passwordInput.value;
                
                if (password === ADMIN_PASSWORD) {
                    passwordModal.style.display = 'none';
                    passwordInput.value = '';
                    passwordError.style.display = 'none';
                    
                    // Execute callback if exists
                    if (passwordVerifiedCallback) {
                        passwordVerifiedCallback();
                        passwordVerifiedCallback = null;
                    }
                } else {
                    passwordError.style.display = 'block';
                }
            });
            
            passwordInput.addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    verifyPasswordBtn.click();
                }
            });
        }
        
        // Setup student selection modal
        function setupStudentSelectionModal() {
            closeStudentSelectionModal.addEventListener('click', () => {
                studentSelectionModal.style.display = 'none';
            });
        }
        
        // Setup student grading modal
        function setupStudentGradingModal() {
            closeStudentGradingModal.addEventListener('click', () => {
                studentGradingModal.style.display = 'none';
            });
        }
        
        // Setup edit program modal
        function setupEditProgramModal() {
            closeEditProgramModal.addEventListener('click', () => {
                editProgramModal.style.display = 'none';
            });
            
            editProgramForm.addEventListener('submit', (e) => {
                e.preventDefault();
                
                // Verify password before saving
                passwordVerifiedCallback = () => {
                    // Update event data
                    const eventIndex = baseEvents.findIndex(e => e.id === currentEventForEditing.id);
                    if (eventIndex !== -1) {
                        baseEvents[eventIndex] = {
                            ...baseEvents[eventIndex],
                            name: editProgramNameInput.value,
                            category: editProgramCategorySelect.value,
                            language: editProgramLanguageSelect.value,
                            date: editProgramDateInput.value,
                            time: editProgramTimeInput.value,
                            venue: editProgramVenueInput.value,
                            description: editProgramDescriptionTextarea.value
                        };
                        
                        // Save to localStorage
                        saveData();
                        
                        // Update UI
                        renderTeamEvents(currentTeamForEditing);
                        
                        // Close modal
                        editProgramModal.style.display = 'none';
                        
                        // Show toast notification
                        showToast('success', 'Event Updated', 'Event details have been updated successfully');
                    }
                };
                
                // Show password modal
                passwordModalTitle.textContent = 'Verify Password to Edit Event';
                passwordModal.style.display = 'flex';
                passwordInput.focus();
            });
        }
        
        // Setup email confirmation modal
        function setupEmailConfirmationModal() {
            closeEmailConfirmationModal.addEventListener('click', () => {
                emailConfirmationModal.style.display = 'none';
            });
            
            closeEmailConfirmationBtn.addEventListener('click', () => {
                emailConfirmationModal.style.display = 'none';
            });
        }
        
        // Setup toast notifications
        function setupToastNotifications() {
            toastClose.addEventListener('click', () => {
                toast.classList.remove('show');
            });
        }
        
        // Show toast notification
        function showToast(type, title, message) {
            toast.className = `toast ${type}`;
            toastTitle.textContent = title;
            toastDescription.textContent = message;
            
            // Update icon based on type
            const icon = toast.querySelector('i');
            switch (type) {
                case 'success':
                    icon.className = 'fas fa-check-circle';
                    break;
                case 'error':
                    icon.className = 'fas fa-exclamation-circle';
                    break;
                case 'warning':
                    icon.className = 'fas fa-exclamation-triangle';
                    break;
                case 'info':
                default:
                    icon.className = 'fas fa-info-circle';
                    break;
            }
            
            // Show toast
            toast.classList.add('show');
            
            // Auto hide after 5 seconds
            setTimeout(() => {
                toast.classList.remove('show');
            }, 5000);
        }
        
        // Setup floating action button
        function setupFabButton() {
            fabButton.addEventListener('click', () => {
                // Show email confirmation modal
                emailConfirmationModal.style.display = 'flex';
            });
        }
        
        // Setup main tabs
        function setupMainTabs() {
            mainTabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    // Remove active class from all tabs
                    mainTabs.forEach(t => t.classList.remove('active'));
                    
                    // Add active class to clicked tab
                    tab.classList.add('active');
                    
                    // Get tab content
                    const tabName = tab.dataset.tab;
                    
                    // Hide all tab contents
                    document.querySelectorAll('.events-tab-content, .students-tab-content').forEach(content => {
                        content.classList.remove('active');
                    });
                    
                    // Show selected tab content
                    if (tabName === 'events') {
                        document.querySelector('.events-tab-content').classList.add('active');
                    } else if (tabName === 'students') {
                        document.querySelector('.students-tab-content').classList.add('active');
                    }
                });
            });
        }
        
        // Setup team tabs with password protection
        function setupTeamTabs() {
            teamTabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    const teamId = tab.dataset.team;
                    const teamName = baseTeamsData[teamId].name.split(': ')[1];
                    
                    // Check if already authenticated
                    if (sessionStorage.getItem(`team_${teamId}_authenticated`) === 'true') {
                        switchToTeam(teamId);
                    } else {
                        // Show password modal
                        passwordModalTitle.textContent = `Enter Password for ${teamName} Team`;
                        passwordInput.value = '';
                        passwordError.style.display = 'none';
                        passwordModal.style.display = 'flex';
                        passwordInput.focus();
                        
                        passwordVerifiedCallback = () => {
                            // Store authentication in sessionStorage
                            sessionStorage.setItem(`team_${teamId}_authenticated`, 'true');
                            switchToTeam(teamId);
                        };
                    }
                });
            });
        }
        
        // Switch to team tab
        function switchToTeam(teamId) {
            // Remove active class from all tabs
            teamTabs.forEach(t => t.classList.remove('active'));
            
            // Add active class to clicked tab
            const tab = document.querySelector(`.team-tab[data-team="${teamId}"]`);
            tab.classList.add('active');
            
            // Hide all team contents
            teamContents.forEach(content => {
                content.classList.remove('active');
            });
            
            // Show selected team content
            document.getElementById(teamId).classList.add('active');
        }
        
        // Add a helper function to show password modal with custom title and callback
        function showPasswordModal(title, successCallback) {
            passwordModalTitle.textContent = title;
            passwordInput.value = '';
            passwordError.style.display = 'none';
            passwordModal.style.display = 'flex';
            passwordInput.focus();
            
            passwordVerifiedCallback = successCallback;
        }
        
        // Update password verification to check team passwords
        verifyPasswordBtn.addEventListener('click', () => {
            const password = passwordInput.value;
            const teamId = currentTeamForEditing || Object.keys(TEAM_PASSWORDS).find(
                team => sessionStorage.getItem(`team_${team}_authenticated`) === 'true'
            );
            
            // Check if it's a team password or admin password
            if (teamId && password === TEAM_PASSWORDS[teamId]) {
                passwordModal.style.display = 'none';
                passwordInput.value = '';
                passwordError.style.display = 'none';
                
                if (passwordVerifiedCallback) {
                    passwordVerifiedCallback();
                    passwordVerifiedCallback = null;
                }
            } else if (password === ADMIN_PASSWORD) {
                passwordModal.style.display = 'none';
                passwordInput.value = '';
                passwordError.style.display = 'none';
                
                if (passwordVerifiedCallback) {
                    passwordVerifiedCallback();
                    passwordVerifiedCallback = null;
                }
            } else {
                passwordError.style.display = 'block';
            }
        });
        
        // Setup modal close buttons
        closeModal.addEventListener('click', () => {
            eventModal.style.display = 'none';
        });
        
        closeStudentDetailsModal.addEventListener('click', () => {
            studentDetailsModal.style.display = 'none';
        });
        
        // Close modals when clicking outside
        window.addEventListener('click', (e) => {
            if (e.target === eventModal) {
                eventModal.style.display = 'none';
            }
            
            if (e.target === studentDetailsModal) {
                studentDetailsModal.style.display = 'none';
            }
            
            if (e.target === passwordModal) {
                passwordModal.style.display = 'none';
                passwordInput.value = '';
                passwordError.style.display = 'none';
                passwordVerifiedCallback = null;
            }
            
            if (e.target === studentSelectionModal) {
                studentSelectionModal.style.display = 'none';
            }
            
            if (e.target === studentGradingModal) {
                studentGradingModal.style.display = 'none';
            }
            
            if (e.target === editProgramModal) {
                editProgramModal.style.display = 'none';
            }
            
            if (e.target === emailConfirmationModal) {
                emailConfirmationModal.style.display = 'none';
            }
        });
        
        // Initialize the application
        document.addEventListener('DOMContentLoaded', () => {
            // Load saved data
            loadSavedData();
            
            // Initialize teams
            initializeTeams();
            
            // Set initial active tab
            document.querySelector('.main-tab.active').click();
        });
    </script>
</body>
</html>
