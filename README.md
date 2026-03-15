
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
    <title>FitДефицит — твой фитнес помощник</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background: #f0f5fc;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
            padding: 0;
            margin: 0;
            transition: background 0.3s;
        }

        body.dark-theme {
            background: #121212;
        }

        .app-container {
            max-width: 500px;
            width: 100%;
            background: white;
            box-shadow: 0 0 40px rgba(0,10,30,0.1);
            min-height: 100vh;
            position: relative;
            transition: background 0.3s;
        }

        .dark-theme .app-container {
            background: #1e1e1e;
            color: #e0e0e0;
        }

        .login-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(145deg, #1a2a3a, #0f1c2c);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            padding: 20px;
        }

        .login-card {
            background: white;
            border-radius: 40px;
            padding: 40px 30px;
            width: 100%;
            max-width: 400px;
            box-shadow: 0 30px 60px rgba(0,0,0,0.3);
        }

        .dark-theme .login-card {
            background: #2d2d2d;
            color: #e0e0e0;
        }

        .login-card h2 {
            text-align: center;
            margin-bottom: 30px;
            color: #1a2a3a;
            font-size: 28px;
        }

        .dark-theme .login-card h2 {
            color: #e0e0e0;
        }

        .login-card h2 i {
            color: #ffaa33;
            margin-right: 10px;
        }

        .login-input {
            width: 100%;
            padding: 18px 20px;
            margin-bottom: 20px;
            border: 2px solid #e2edf8;
            border-radius: 60px;
            font-size: 16px;
            outline: none;
        }

        .dark-theme .login-input {
            background: #3d3d3d;
            border-color: #555;
            color: #e0e0e0;
        }

        .login-input:focus {
            border-color: #ffaa33;
        }

        .login-btn {
            width: 100%;
            padding: 18px;
            background: #ffaa33;
            border: none;
            border-radius: 60px;
            font-weight: 700;
            font-size: 18px;
            color: #1a2a3a;
            cursor: pointer;
            margin-bottom: 20px;
            transition: 0.2s;
        }

        .login-hint {
            text-align: center;
            color: #5e7b9c;
            font-size: 14px;
        }

        .dark-theme .login-hint {
            color: #aaa;
        }

        .login-hint i {
            color: #ffaa33;
        }

        .header {
            background: linear-gradient(145deg, #1a2a3a, #0f1c2c);
            color: white;
            padding: 16px 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .dark-theme .header {
            background: linear-gradient(145deg, #2d2d2d, #1a1a1a);
        }

        .logo h1 {
            font-size: 22px;
            font-weight: 600;
        }
        .logo span { color: #ffaa33; }

        .user-menu {
            display: flex;
            align-items: center;
            gap: 15px;
            background: #253645;
            padding: 8px 16px;
            border-radius: 40px;
        }

        .dark-theme .user-menu {
            background: #3d3d3d;
        }

        .user-avatar {
            width: 32px;
            height: 32px;
            background: #ffaa33;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 600;
            color: #1a2a3a;
            cursor: pointer;
            font-size: 18px;
        }

        .user-name {
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
        }

        .logout-btn {
            background: none;
            border: none;
            color: #ffaa33;
            cursor: pointer;
            font-size: 16px;
        }

        .tab-nav {
            display: flex;
            background: white;
            border-bottom: 1px solid #ecf2f9;
        }

        .dark-theme .tab-nav {
            background: #1e1e1e;
            border-bottom-color: #333;
        }

        .tab {
            flex: 1;
            text-align: center;
            padding: 16px 8px;
            font-weight: 600;
            font-size: 14px;
            color: #5e7b9c;
            cursor: pointer;
            transition: all 0.2s;
            border-bottom: 3px solid transparent;
        }

        .dark-theme .tab {
            color: #aaa;
        }

        .tab.active {
            color: #ffaa33;
            border-bottom: 3px solid #ffaa33;
        }

        .tab i {
            margin-right: 6px;
        }

        .tab-content {
            display: block;
        }

        .tab-content.hidden {
            display: none;
        }

        .calendar-section {
            padding: 16px 16px 8px;
            background: white;
            border-bottom: 1px solid #ecf2f9;
        }

        .dark-theme .calendar-section {
            background: #1e1e1e;
            border-bottom-color: #333;
        }

        .calendar-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            cursor: pointer;
        }

        .calendar-title {
            font-size: 16px;
            font-weight: 600;
            color: #1e2f42;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .dark-theme .calendar-title {
            color: #e0e0e0;
        }

        .calendar-title i {
            color: #ffaa33;
        }

        .toggle-icon {
            color: #ffaa33;
            font-size: 18px;
            transition: transform 0.3s;
        }

        .toggle-icon.rotated {
            transform: rotate(180deg);
        }

        .month-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 8px;
            margin-bottom: 8px;
            transition: all 0.3s ease;
            overflow: hidden;
        }

        .month-grid.collapsed {
            display: none;
        }

        .month-card {
            background: #f8fbfe;
            border: 1px solid #e2ecf9;
            border-radius: 16px;
            padding: 10px 4px;
            text-align: center;
            font-size: 13px;
            font-weight: 500;
            color: #1e2f42;
            cursor: pointer;
            transition: all 0.2s;
            box-shadow: 0 2px 6px rgba(0,0,0,0.02);
        }

        .dark-theme .month-card {
            background: #2d2d2d;
            border-color: #444;
            color: #e0e0e0;
        }

        .month-card.active {
            background: #ffaa33;
            border-color: #ffaa33;
            color: #1a2a3a;
            font-weight: 600;
            box-shadow: 0 6px 12px rgba(255,170,51,0.3);
            transform: translateY(-2px);
        }

        .month-card i {
            display: block;
            font-size: 18px;
            margin-bottom: 4px;
            color: #ffaa33;
        }

        .month-card.active i {
            color: #1a2a3a;
        }

        .week-nav {
            padding: 12px 16px;
            background: #f8fbfe;
            border-bottom: 1px solid #e5ecf5;
        }

        .dark-theme .week-nav {
            background: #1e1e1e;
            border-bottom-color: #333;
        }

        .week-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
            cursor: pointer;
        }

        .week-title {
            font-size: 14px;
            font-weight: 600;
            color: #1e2f42;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .dark-theme .week-title {
            color: #e0e0e0;
        }

        .week-title i {
            color: #ffaa33;
        }

        .week-toggle-icon {
            color: #ffaa33;
            font-size: 16px;
            transition: transform 0.3s;
        }

        .week-toggle-icon.rotated {
            transform: rotate(180deg);
        }

        .day-buttons {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            transition: all 0.3s ease;
            overflow: hidden;
            max-height: 500px;
        }

        .day-buttons.collapsed {
            display: none;
        }

        .day-btn {
            background: white;
            border: 1px solid #d5e2f2;
            padding: 8px 10px;
            border-radius: 30px;
            font-size: 12px;
            font-weight: 500;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 4px;
            transition: all 0.2s;
            flex: 0 0 calc(14.28% - 6px);
            justify-content: center;
        }

        .dark-theme .day-btn {
            background: #2d2d2d;
            border-color: #444;
            color: #e0e0e0;
        }

        .day-btn.active {
            background: #ffaa33;
            border-color: #ffaa33;
            color: #1e2b3a;
            font-weight: 600;
            box-shadow: 0 4px 8px rgba(255,170,51,0.2);
        }

        .day-btn.weekend {
            background: #fff4e5;
        }

        .dark-theme .day-btn.weekend {
            background: #3d3d3d;
        }

        .content {
            padding: 16px;
            display: flex;
            flex-direction: column;
            gap: 16px;
            padding-bottom: 80px;
        }

        .card {
            background: white;
            border-radius: 24px;
            padding: 18px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.02);
            border: 1px solid #ecf3fc;
        }

        .dark-theme .card {
            background: #2d2d2d;
            border-color: #444;
        }

        .card-title {
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 16px;
            display: flex;
            align-items: center;
            gap: 10px;
            color: #1a2c40;
            border-bottom: 2px solid #f0f6ff;
            padding-bottom: 12px;
        }

        .dark-theme .card-title {
            color: #e0e0e0;
            border-bottom-color: #444;
        }

        .card-title i { color: #ffaa33; font-size: 20px; }

        .theme-toggle {
            background: none;
            border: none;
            color: #ffaa33;
            font-size: 18px;
            cursor: pointer;
            margin-right: 10px;
        }

        .calorie-summary {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #f3f9ff;
            border-radius: 40px;
            padding: 14px 18px;
            margin-bottom: 16px;
        }

        .dark-theme .calorie-summary {
            background: #3d3d3d;
        }

        .calorie-number {
            font-size: 28px;
            font-weight: 700;
            color: #1e2f42;
        }

        .dark-theme .calorie-number {
            color: #e0e0e0;
        }

        .calorie-label {
            font-size: 14px;
            color: #5e7b9c;
        }

        .dark-theme .calorie-label {
            color: #aaa;
        }

        .deficit-badge {
            background: #ffaa33;
            padding: 6px 14px;
            border-radius: 30px;
            font-weight: 600;
            font-size: 14px;
        }

        .progress-bar {
            height: 12px;
            background: #e2ecf9;
            border-radius: 12px;
            margin: 10px 0;
        }

        .dark-theme .progress-bar {
            background: #444;
        }

        .progress-fill {
            height: 12px;
            background: #ffaa33;
            border-radius: 12px;
            width: 65%;
            transition: width 0.3s;
        }

        .meal-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #f8fcff;
            border-radius: 20px;
            padding: 12px 16px;
            margin-bottom: 10px;
            border-left: 5px solid #ffaa33;
        }

        .dark-theme .meal-item {
            background: #3d3d3d;
        }

        .meal-info h4 {
            font-size: 16px;
            font-weight: 600;
            color: #1b3349;
        }

        .dark-theme .meal-info h4 {
            color: #e0e0e0;
        }

        .meal-info p {
            font-size: 12px;
            color: #5e7b9e;
            margin-top: 4px;
        }

        .dark-theme .meal-info p {
            color: #aaa;
        }

        .meal-gramms {
            font-size: 11px;
            color: #888;
            margin-left: 5px;
            font-weight: normal;
        }

        .meal-kcal {
            background: white;
            padding: 6px 16px;
            border-radius: 30px;
            font-weight: 600;
            font-size: 14px;
            box-shadow: 0 2px 6px #e0eaf6;
        }

        .dark-theme .meal-kcal {
            background: #2d2d2d;
            color: #e0e0e0;
            box-shadow: none;
        }

        .btn-add {
            background: none;
            border: 2px dashed #c4d3e8;
            width: 100%;
            padding: 14px;
            border-radius: 40px;
            font-weight: 600;
            color: #2b405c;
            cursor: pointer;
            font-size: 15px;
            margin-top: 8px;
            transition: all 0.2s;
        }

        .dark-theme .btn-add {
            border-color: #555;
            color: #e0e0e0;
        }

        .btn-add:hover {
            background: #f0f7ff;
            border-color: #ffaa33;
        }

        .workout-card {
            background: #f4faff;
            border-radius: 22px;
            padding: 18px;
            margin-bottom: 16px;
            border: 2px solid transparent;
            cursor: pointer;
            transition: all 0.2s;
        }

        .dark-theme .workout-card {
            background: #3d3d3d;
        }

        .workout-card.completed {
            background: #e2f5e2;
            border-color: #2ecc71;
        }

        .dark-theme .workout-card.completed {
            background: #1e3a1e;
            border-color: #2ecc71;
        }

        .workout-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .workout-name {
            font-size: 18px;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .workout-burn {
            background: #ffecd8;
            padding: 6px 14px;
            border-radius: 30px;
            font-size: 13px;
            font-weight: 600;
        }

        .dark-theme .workout-burn {
            background: #5e5e5e;
            color: #e0e0e0;
        }

        .reminder-card {
            background: #f0f7ff;
            border-radius: 16px;
            padding: 16px;
            margin-top: 16px;
        }

        .dark-theme .reminder-card {
            background: #3d3d3d;
        }

        .reminder-time {
            display: flex;
            gap: 8px;
            align-items: center;
            margin: 12px 0;
        }

        .reminder-time input {
            flex: 1;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 30px;
        }

        .dark-theme .reminder-time input {
            background: #2d2d2d;
            border-color: #555;
            color: #e0e0e0;
        }

        .reminder-btn {
            background: #ffaa33;
            border: none;
            padding: 10px 20px;
            border-radius: 30px;
            font-weight: 600;
            cursor: pointer;
            width: 100%;
            margin: 8px 0;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
            margin-bottom: 20px;
        }

        .stat-card {
            background: #f8fbfe;
            border-radius: 20px;
            padding: 16px;
            text-align: center;
        }

        .dark-theme .stat-card {
            background: #3d3d3d;
        }

        .stat-value {
            font-size: 28px;
            font-weight: 700;
            color: #1e2f42;
        }

        .dark-theme .stat-value {
            color: #e0e0e0;
        }

        .stat-label {
            font-size: 12px;
            color: #5e7b9c;
            margin-top: 4px;
        }

        .dark-theme .stat-label {
            color: #aaa;
        }

        .progress-month {
            background: #f8fbfe;
            border-radius: 20px;
            padding: 16px;
            margin-bottom: 12px;
        }

        .dark-theme .progress-month {
            background: #3d3d3d;
        }

        .progress-month-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-weight: 600;
        }

        .month-bar {
            height: 8px;
            background: #e2ecf9;
            border-radius: 8px;
            margin-bottom: 8px;
        }

        .dark-theme .month-bar {
            background: #555;
        }

        .month-bar-fill {
            height: 8px;
            background: #ffaa33;
            border-radius: 8px;
            width: 0%;
        }

        .goal-card {
            background: #fff9f0;
            border-radius: 20px;
            padding: 16px;
            margin-bottom: 16px;
        }

        .dark-theme .goal-card {
            background: #3d3d3d;
        }

        .goal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
        }

        .goal-select {
            padding: 8px 16px;
            border-radius: 30px;
            border: 1px solid #ffaa33;
            background: white;
        }

        .dark-theme .goal-select {
            background: #2d2d2d;
            color: #e0e0e0;
        }

        .goal-progress {
            height: 8px;
            background: #e2ecf9;
            border-radius: 8px;
            margin: 12px 0;
        }

        .dark-theme .goal-progress {
            background: #555;
        }

        .goal-progress-fill {
            height: 8px;
            background: #ffaa33;
            border-radius: 8px;
            width: 0%;
        }

        .avatar-modal {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            justify-content: center;
            margin: 20px 0;
        }

        .avatar-option {
            width: 60px;
            height: 60px;
            border-radius: 30px;
            background: #f0f5fc;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
            cursor: pointer;
            border: 2px solid transparent;
        }

        .dark-theme .avatar-option {
            background: #3d3d3d;
        }

        .avatar-option.selected {
            border-color: #ffaa33;
        }

        .save-indicator {
            position: fixed;
            bottom: 0;
            max-width: 500px;
            width: 100%;
            background: #e8f0fe;
            padding: 12px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
            color: #2e4a73;
            border-top: 1px solid #d8e4f2;
            z-index: 150;
        }

        .dark-theme .save-indicator {
            background: #2d2d2d;
            color: #e0e0e0;
            border-top-color: #444;
        }

        .save-btn {
            background: #1e2b3a;
            color: white;
            border: none;
            padding: 8px 20px;
            border-radius: 30px;
            font-size: 13px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
        }

        .dark-theme .save-btn {
            background: #ffaa33;
            color: #1a2a3a;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            align-items: center;
            justify-content: center;
            z-index: 2000;
            padding: 16px;
        }

        .modal-card {
            background: white;
            border-radius: 36px;
            padding: 28px;
            width: 100%;
            max-width: 400px;
            max-height: 90vh;
            overflow-y: auto;
        }

        .dark-theme .modal-card {
            background: #2d2d2d;
            color: #e0e0e0;
        }

        .modal-card h2 {
            margin-bottom: 20px;
            color: #1a2a3a;
        }

        .dark-theme .modal-card h2 {
            color: #e0e0e0;
        }

        .modal-card input,
        .modal-card select {
            width: 100%;
            padding: 16px 18px;
            margin-bottom: 16px;
            border: 2px solid #e2edf8;
            border-radius: 50px;
            font-size: 15px;
            outline: none;
        }

        .dark-theme .modal-card input,
        .dark-theme .modal-card select {
            background: #3d3d3d;
            border-color: #555;
            color: #e0e0e0;
        }

        .modal-card input:focus,
        .modal-card select:focus {
            border-color: #ffaa33;
            box-shadow: 0 0 0 3px rgba(255,170,51,0.1);
        }

        .save-profile {
            background: #1e2b3a;
            color: white;
            border: none;
            padding: 16px;
            width: 100%;
            border-radius: 50px;
            font-weight: 600;
            font-size: 16px;
            cursor: pointer;
            margin-top: 10px;
            transition: all 0.2s;
        }

        .save-profile:hover {
            background: #2d4055;
        }

        .help-bubble {
            background: #fff9f0;
            border-left: 4px solid #ffaa33;
            padding: 16px;
            border-radius: 16px;
            margin-bottom: 16px;
            font-size: 14px;
            color: #2b405c;
            box-shadow: 0 4px 12px rgba(255,170,51,0.1);
        }

        .dark-theme .help-bubble {
            background: #3d3d3d;
            color: #e0e0e0;
        }

        .help-bubble i {
            color: #ffaa33;
            margin-right: 8px;
        }

        .help-bubble p {
            margin: 8px 0;
        }

        .help-close {
            float: right;
            background: none;
            border: none;
            font-size: 18px;
            cursor: pointer;
            color: #999;
            transition: all 0.2s;
        }

        .help-close:hover {
            color: #ffaa33;
        }

        .gramm-badge {
            background: #e8f0fe;
            padding: 2px 8px;
            border-radius: 30px;
            font-size: 10px;
            color: #2e4a73;
            margin-left: 8px;
        }

        .dark-theme .gramm-badge {
            background: #444;
            color: #e0e0e0;
        }

        @media (max-width: 400px) {
            .header { padding: 12px 16px; }
            .logo h1 { font-size: 20px; }
            .calorie-number { font-size: 24px; }
            .day-btn { font-size: 11px; padding: 6px 4px; }
        }
    </style>
</head>
<body>
    <div class="app-container" id="appContainer">
        <div class="login-screen" id="loginScreen">
            <div class="login-card">
                <h2><i class="fas fa-leaf"></i> FitДефицит</h2>
                <input type="text" class="login-input" id="loginUsername" placeholder="Ваше имя" autocomplete="off">
                <button class="login-btn" id="loginBtn">
                    <i class="fas fa-sign-in-alt"></i> Войти
                </button>
                <p class="login-hint">
                    <i class="fas fa-info-circle"></i> Просто введите имя — и начнём
                </p>
            </div>
        </div>

        <div class="header" id="header" style="display: none;">
            <div class="logo">
                <h1><span>Fit</span>Дефицит</h1>
            </div>
            <div class="user-menu">
                <button class="theme-toggle" id="themeToggle">
                    <i class="fas fa-moon"></i>
                </button>
                <div class="user-avatar" id="userAvatar" onclick="openProfileModal()">👤</div>
                <span class="user-name" id="currentUsername" onclick="openProfileModal()">Гость</span>
                <i class="fas fa-sign-out-alt logout-btn" id="logoutBtn"></i>
            </div>
        </div>

        <div class="tab-nav" id="tabNav" style="display: none;">
            <div class="tab active" id="planTab"><i class="fas fa-calendar-alt"></i> План</div>
            <div class="tab" id="statsTab"><i class="fas fa-chart-line"></i> Итоги</div>
        </div>

        <div id="planContent" class="tab-content">
            <div class="calendar-section" id="calendarSection">
                <div class="calendar-header" id="calendarHeader">
                    <div class="calendar-title">
                        <i class="fas fa-calendar-alt"></i> Выберите месяц
                    </div>
                    <i class="fas fa-chevron-up toggle-icon" id="toggleIcon"></i>
                </div>
                <div class="month-grid" id="monthGrid"></div>
            </div>

            <div class="week-nav" id="weekNav">
                <div class="week-header" id="weekHeader">
                    <div class="week-title">
                        <i class="fas fa-calendar-week"></i> Дни месяца
                    </div>
                    <i class="fas fa-chevron-up week-toggle-icon" id="weekToggleIcon"></i>
                </div>
                <div class="day-buttons" id="dayButtons"></div>
            </div>

            <div class="content" id="content">
                <div class="help-bubble" id="helpBubble">
                    <button class="help-close" id="closeHelp">×</button>
                    <i class="fas fa-lightbulb"></i> <strong>Как это работает:</strong>
                    <p>📅 Выберите месяц и день — меню на реальную дату</p>
                    <p>🍽️ Добавляйте перекусы кнопкой внизу</p>
                    <p>💪 Кликните по тренировке, чтобы отметить</p>
                    <p>⚡ Дефицит калорий показывается сверху</p>
                    <p>🌙 Кнопка луны — тёмная тема</p>
                    <p>🔔 Напоминания снизу — они будут приходить</p>
                    <p>⚖️ Порции автоматически подстраиваются под ваш вес</p>
                </div>

                <div class="card">
                    <div class="card-title">
                        <i class="fas fa-fire"></i> Калории сегодня
                    </div>
                    <div class="calorie-summary">
                        <div>
                            <span class="calorie-number" id="todayKcal">0</span>
                            <span class="calorie-label">/ <span id="todayTarget">1750</span> ккал</span>
                        </div>
                        <div class="deficit-badge" id="deficitBadge">+0</div>
                    </div>
                    <div class="progress-bar">
                        <div class="progress-fill" id="progressFill" style="width: 0%"></div>
                    </div>
                </div>

                <div class="card">
                    <div class="card-title">
                        <i class="fas fa-utensils"></i> Меню: <span id="currentDayName"></span>
                        <span class="gramm-badge" id="monthGramms">≈ 1500 г</span>
                    </div>
                    <div id="mealsList"></div>
                    <button class="btn-add" id="addSnackBtn">
                        <i class="fas fa-plus-circle"></i> Добавить перекус
                    </button>
                </div>

                <div class="card">
                    <div class="card-title">
                        <i class="fas fa-dumbbell"></i> Тренировка
                    </div>
                    <div id="workoutContainer"></div>
                </div>

                <div class="reminder-card">
                    <div class="card-title">
                        <i class="fas fa-bell"></i> Напоминания
                    </div>
                    <div class="reminder-time">
                        <i class="fas fa-morning"></i>
                        <input type="time" id="reminderTime" value="09:00">
                        <button class="reminder-btn" id="setMorningReminder">
                            <i class="fas fa-check"></i> Завтрак
                        </button>
                    </div>
                    <div class="reminder-time">
                        <i class="fas fa-utensils"></i>
                        <input type="time" id="lunchReminder" value="13:00">
                        <button class="reminder-btn" id="setLunchReminder">
                            <i class="fas fa-check"></i> Обед
                        </button>
                    </div>
                    <div class="reminder-time">
                        <i class="fas fa-dumbbell"></i>
                        <input type="time" id="workoutReminder" value="19:00">
                        <button class="reminder-btn" id="setWorkoutReminder">
                            <i class="fas fa-check"></i> Тренировка
                        </button>
                    </div>
                </div>
            </div>
        </div>

        <div id="statsContent" class="tab-content hidden">
            <div class="content">
                <div class="goal-card">
                    <div class="goal-header">
                        <h3><i class="fas fa-bullseye"></i> Моя цель</h3>
                        <select class="goal-select" id="goalSelect">
                            <option value="lose">Похудеть</option>
                            <option value="maintain">Поддержание</option>
                            <option value="gain">Набрать массу</option>
                        </select>
                    </div>
                    <div class="goal-progress">
                        <div class="goal-progress-fill" id="goalProgress" style="width: 45%"></div>
                    </div>
                    <p>Прогресс: <span id="goalProgressText">45%</span> к цели</p>
                    <p>Целевой вес: <span id="targetWeight">70</span> кг</p>
                </div>

                <div class="card">
                    <div class="card-title">
                        <i class="fas fa-trophy"></i> Общий прогресс
                    </div>
                    <div class="stats-grid">
                        <div class="stat-card">
                            <div class="stat-value" id="totalDeficit">0</div>
                            <div class="stat-label">Всего дефицит (ккал)</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-value" id="totalLoss">0</div>
                            <div class="stat-label">Потеряно (кг)</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-value" id="totalWorkouts">0</div>
                            <div class="stat-label">Тренировок</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-value" id="avgDeficit">0</div>
                            <div class="stat-label">В день (ккал)</div>
                        </div>
                    </div>
                </div>

                <div class="card">
                    <div class="card-title">
                        <i class="fas fa-calendar-check"></i> Прогресс по месяцам
                    </div>
                    <div id="monthlyProgress"></div>
                </div>

                <div class="card">
                    <div class="card-title">
                        <i class="fas fa-info-circle"></i> Рекомендации
                    </div>
                    <div style="font-size: 14px; color: #2b405c;">
                        <p>📌 <strong>1 кг жира = 7700 ккал</strong></p>
                        <p>📌 Оптимальный темп: 0.5-1 кг в неделю</p>
                        <p>📌 Спите 7-8 часов для лучших результатов</p>
                        <p>📌 Пейте 1.5-2 литра воды в день</p>
                        <p id="motivationText">💪 Продолжайте в том же духе!</p>
                    </div>
                </div>
            </div>
        </div>

        <div class="save-indicator" id="saveIndicator" style="display: none;">
            <span><i class="fas fa-database"></i> <span id="saveStatus">Сохранено</span></span>
            <button class="save-btn" id="manualSaveBtn"><i class="fas fa-save"></i> Сохранить</button>
        </div>
    </div>

    <div class="modal" id="profileModal">
        <div class="modal-card">
            <h2><i class="fas fa-user-edit"></i> Ваш профиль</h2>
            
            <h3>Выберите аватар</h3>
            <div class="avatar-modal" id="avatarModal">
                <div class="avatar-option" onclick="selectAvatar('👤')">👤</div>
                <div class="avatar-option" onclick="selectAvatar('👩')">👩</div>
                <div class="avatar-option" onclick="selectAvatar('👨')">👨</div>
                <div class="avatar-option" onclick="selectAvatar('🧔')">🧔</div>
                <div class="avatar-option" onclick="selectAvatar('👱‍♀️')">👱‍♀️</div>
                <div class="avatar-option" onclick="selectAvatar('👳')">👳</div>
                <div class="avatar-option" onclick="selectAvatar('🧑')">🧑</div>
                <div class="avatar-option" onclick="selectAvatar('👵')">👵</div>
            </div>
            
            <h3>Личные данные</h3>
            <select id="modalGender">
                <option value="male">Мужской</option>
                <option value="female">Женский</option>
            </select>
            <input type="number" id="modalAge" placeholder="Возраст">
            <input type="number" id="modalWeight" placeholder="Вес (кг)" step="0.1">
            <input type="number" id="modalHeight" placeholder="Рост (см)">
            <input type="number" id="modalTargetWeight" placeholder="Целевой вес (кг)" step="0.1">
            <select id="modalActivity">
                <option value="1.2">Сидячий образ жизни</option>
                <option value="1.375">Легкая активность (1-3 раза)</option>
                <option value="1.55">Умеренная (3-5 раз)</option>
                <option value="1.725">Высокая (6-7 раз)</option>
            </select>
            <button class="save-profile" id="saveProfileBtn">Сохранить</button>
        </div>
    </div>

    <audio id="notificationSound" src="data:audio/mp3;base64,SUQzBAAAAAAAI1RTU0UAAAAPAAADTGF2ZjU4LjI5LjEwMAAAAAAAAAAAAAAA//tQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAWGluZwAAAA8AAAACAAADYAD//f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39/f39"></audio>

    <script>
        let users = {};
        let currentUser = null;
        let appData = null;
        let currentMonth = new Date().getMonth();
        let currentYear = new Date().getFullYear();
        let calendarCollapsed = false;
        let weekCollapsed = false;
        let darkTheme = false;

        function isLeapYear(year) {
            return (year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0);
        }

        function getMonthDays(year, month) {
            if (month === 1 && isLeapYear(year)) return 29;
            return [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31][month];
        }

        function getFirstDayOfMonth(year, month) {
            return new Date(year, month, 1).getDay();
        }

        const foodDB = [
            {
                завтрак: [
                    { name: 'Овсяноблин с творогом', prot: 28, fat: 12, carbs: 35, kcal: 320, gramms: 250 },
                    { name: 'Яичница с овощами', prot: 24, fat: 20, carbs: 10, kcal: 310, gramms: 220 },
                    { name: 'Греческий йогурт с орехами', prot: 20, fat: 15, carbs: 18, kcal: 280, gramms: 200 },
                    { name: 'ПП-сырники со сметаной', prot: 26, fat: 14, carbs: 30, kcal: 340, gramms: 210 },
                    { name: 'Рисовая каша с яблоком', prot: 8, fat: 6, carbs: 48, kcal: 280, gramms: 280 },
                    { name: 'Тост с авокадо', prot: 12, fat: 18, carbs: 30, kcal: 320, gramms: 180 },
                    { name: 'Смузи с бананом', prot: 10, fat: 4, carbs: 42, kcal: 250, gramms: 350 },
                    { name: 'Омлет с помидорами', prot: 22, fat: 18, carbs: 8, kcal: 290, gramms: 230 },
                    { name: 'Пшенная каша с тыквой', prot: 8, fat: 6, carbs: 44, kcal: 260, gramms: 270 },
                    { name: 'Драники со сметаной', prot: 10, fat: 14, carbs: 38, kcal: 310, gramms: 200 },
                    { name: 'Чиа пудинг', prot: 12, fat: 12, carbs: 28, kcal: 260, gramms: 220 },
                    { name: 'Блинчики с творогом', prot: 18, fat: 10, carbs: 36, kcal: 320, gramms: 210 },
                    { name: 'Творожная запеканка', prot: 24, fat: 8, carbs: 28, kcal: 280, gramms: 200 },
                    { name: 'Овсяная каша с ягодами', prot: 12, fat: 8, carbs: 42, kcal: 290, gramms: 260 },
                    { name: 'Яйца пашот с тостом', prot: 18, fat: 14, carbs: 22, kcal: 260, gramms: 170 },
                    { name: 'Каша гречневая с молоком', prot: 12, fat: 8, carbs: 48, kcal: 300, gramms: 250 },
                    { name: 'Творог с бананом', prot: 22, fat: 6, carbs: 24, kcal: 240, gramms: 230 }
                ],
                обед: [
                    { name: 'Курица с гречкой', prot: 42, fat: 7, carbs: 40, kcal: 410, gramms: 320 },
                    { name: 'Лосось с овощами', prot: 38, fat: 22, carbs: 15, kcal: 430, gramms: 280 },
                    { name: 'Говядина с киноа', prot: 40, fat: 16, carbs: 42, kcal: 450, gramms: 310 },
                    { name: 'Индейка с булгуром', prot: 44, fat: 10, carbs: 48, kcal: 460, gramms: 330 },
                    { name: 'Паста с курицей', prot: 34, fat: 12, carbs: 58, kcal: 480, gramms: 350 },
                    { name: 'Рыбные котлеты с пюре', prot: 28, fat: 14, carbs: 42, kcal: 400, gramms: 300 },
                    { name: 'Суп с фрикадельками', prot: 22, fat: 10, carbs: 26, kcal: 280, gramms: 400 },
                    { name: 'Курица с рисом', prot: 38, fat: 8, carbs: 46, kcal: 420, gramms: 330 },
                    { name: 'Гречка с грибами', prot: 16, fat: 8, carbs: 48, kcal: 330, gramms: 340 },
                    { name: 'Уха', prot: 22, fat: 6, carbs: 18, kcal: 220, gramms: 380 },
                    { name: 'Плов с курицей', prot: 28, fat: 12, carbs: 52, kcal: 440, gramms: 320 },
                    { name: 'Лазанья с овощами', prot: 22, fat: 14, carbs: 48, kcal: 410, gramms: 350 },
                    { name: 'Борщ с мясом', prot: 18, fat: 8, carbs: 22, kcal: 240, gramms: 420 },
                    { name: 'Котлеты куриные с гречкой', prot: 36, fat: 12, carbs: 38, kcal: 400, gramms: 300 },
                    { name: 'Рыба запеченная с картофелем', prot: 32, fat: 14, carbs: 42, kcal: 420, gramms: 340 },
                    { name: 'Суп куриный с вермишелью', prot: 18, fat: 6, carbs: 24, kcal: 220, gramms: 380 },
                    { name: 'Тефтели с гречкой', prot: 32, fat: 14, carbs: 36, kcal: 390, gramms: 310 }
                ],
                ужин: [
                    { name: 'Творог с ягодами', prot: 24, fat: 6, carbs: 18, kcal: 210, gramms: 220 },
                    { name: 'Рыба с овощами', prot: 32, fat: 8, carbs: 12, kcal: 250, gramms: 260 },
                    { name: 'Куриное филе с салатом', prot: 38, fat: 10, carbs: 14, kcal: 290, gramms: 280 },
                    { name: 'Омлет с сыром', prot: 28, fat: 22, carbs: 8, kcal: 320, gramms: 210 },
                    { name: 'Запеканка творожная', prot: 24, fat: 8, carbs: 28, kcal: 280, gramms: 200 },
                    { name: 'Кальмары с овощами', prot: 26, fat: 6, carbs: 18, kcal: 240, gramms: 280 },
                    { name: 'Куриное суфле', prot: 28, fat: 12, carbs: 14, kcal: 260, gramms: 230 },
                    { name: 'Овощное рагу', prot: 8, fat: 6, carbs: 24, kcal: 180, gramms: 320 },
                    { name: 'Минтай запеченный', prot: 30, fat: 6, carbs: 12, kcal: 220, gramms: 250 },
                    { name: 'Цветная капуста с сыром', prot: 12, fat: 14, carbs: 16, kcal: 230, gramms: 280 },
                    { name: 'Куриные котлеты', prot: 32, fat: 14, carbs: 18, kcal: 320, gramms: 240 },
                    { name: 'Салат с тунцом', prot: 24, fat: 12, carbs: 10, kcal: 250, gramms: 280 },
                    { name: 'Рыбное филе на пару', prot: 28, fat: 6, carbs: 8, kcal: 210, gramms: 240 },
                    { name: 'Творог с зеленью', prot: 22, fat: 5, carbs: 8, kcal: 180, gramms: 210 },
                    { name: 'Грудка индейки с овощами', prot: 34, fat: 8, carbs: 16, kcal: 280, gramms: 270 },
                    { name: 'Запеченные овощи с сыром', prot: 10, fat: 12, carbs: 22, kcal: 220, gramms: 260 }
                ],
                перекус: [
                    { name: 'Протеиновый батон', prot: 15, fat: 6, carbs: 20, kcal: 170, gramms: 50 },
                    { name: 'Смузи боул', prot: 10, fat: 4, carbs: 34, kcal: 210, gramms: 280 },
                    { name: 'Орехи с фруктами', prot: 8, fat: 12, carbs: 22, kcal: 200, gramms: 100 },
                    { name: 'Греческий йогурт', prot: 12, fat: 5, carbs: 18, kcal: 160, gramms: 180 },
                    { name: 'Творожный сырок', prot: 14, fat: 8, carbs: 16, kcal: 190, gramms: 80 },
                    { name: 'Фруктовый салат', prot: 4, fat: 2, carbs: 32, kcal: 160, gramms: 220 },
                    { name: 'Кефир с отрубями', prot: 10, fat: 4, carbs: 14, kcal: 130, gramms: 250 },
                    { name: 'Яблоко с арахисовой пастой', prot: 6, fat: 10, carbs: 26, kcal: 210, gramms: 150 },
                    { name: 'Ряженка', prot: 8, fat: 6, carbs: 12, kcal: 130, gramms: 200 },
                    { name: 'Сухофрукты', prot: 4, fat: 2, carbs: 38, kcal: 180, gramms: 60 },
                    { name: 'Зеленый смузи', prot: 6, fat: 2, carbs: 22, kcal: 130, gramms: 300 },
                    { name: 'Творог с медом', prot: 16, fat: 6, carbs: 20, kcal: 200, gramms: 170 },
                    { name: 'Банан', prot: 2, fat: 0, carbs: 26, kcal: 110, gramms: 120 },
                    { name: 'Яблоко', prot: 0, fat: 0, carbs: 22, kcal: 90, gramms: 180 }
                ]
            }
        ];

        const workouts = {
            0: { name: '🏃 Кардио', desc: 'Бег 30 мин', burn: 350 },
            1: { name: '💪 Силовая', desc: 'Full body', burn: 350 },
            2: { name: '⚡ HIIT', desc: 'Интервалы', burn: 350 },
            3: { name: '🏊 Плавание', desc: '40 мин', burn: 350 },
            4: { name: '🏋️ Силовая', desc: 'Верх тела', burn: 350 },
            5: { name: '🚶 Активный отдых', desc: '10 000 шагов', burn: 200 },
            6: { name: '🧘 Йога', desc: 'Растяжка', burn: 150 }
        };

        const months = ['Январь', 'Февраль', 'Март', 'Апрель', 'Май', 'Июнь', 'Июль', 'Август', 'Сентябрь', 'Октябрь', 'Ноябрь', 'Декабрь'];
        const monthIcons = ['❄️', '⛄', '🌸', '🌷', '🌻', '☀️', '🏖️', '🍉', '🍂', '🍁', '🌧️', '🎄'];
        const weekDays = ['вс', 'пн', 'вт', 'ср', 'чт', 'пт', 'сб'];

        function loadUsers() {
            const saved = localStorage.getItem('fitDeficitUsers');
            users = saved ? JSON.parse(saved) : {};
        }

        function saveUsers() {
            localStorage.setItem('fitDeficitUsers', JSON.stringify(users));
        }

        function login(username) {
            if (!username || username.trim() === '') {
                alert('Введите имя');
                return;
            }
            username = username.trim();
            if (!users[username]) {
                users[username] = {
                    profile: {
                        gender: 'male',
                        age: 30,
                        weight: 75,
                        height: 175,
                        activity: 1.375,
                        name: username,
                        startWeight: 75,
                        targetWeight: 70,
                        avatar: '👤'
                    },
                    completedWorkouts: {},
                    consumedMeals: {},
                    monthlyData: {}
                };
            }
            currentUser = username;
            appData = users[username];
            sessionStorage.setItem('currentUser', username);
            document.getElementById('loginScreen').style.display = 'none';
            document.getElementById('header').style.display = 'flex';
            document.getElementById('tabNav').style.display = 'flex';
            document.getElementById('saveIndicator').style.display = 'flex';
            document.getElementById('currentUsername').innerText = username;
            document.getElementById('userAvatar').innerText = appData.profile.avatar || '👤';
            
            if (!appData.completedWorkouts) appData.completedWorkouts = {};
            if (!appData.consumedMeals) appData.consumedMeals = {};
            if (!appData.monthlyData) appData.monthlyData = {};
            if (!appData.profile.targetWeight) appData.profile.targetWeight = 70;
            if (!appData.profile.avatar) appData.profile.avatar = '👤';
            
            saveUsers();
            renderAll();
            
            if (Notification.permission === 'default') {
                Notification.requestPermission();
            }
        }

        function logout() {
            currentUser = null;
            appData = null;
            sessionStorage.removeItem('currentUser');
            document.getElementById('loginScreen').style.display = 'flex';
            document.getElementById('header').style.display = 'none';
            document.getElementById('tabNav').style.display = 'none';
            document.getElementById('planContent').classList.remove('hidden');
            document.getElementById('statsContent').classList.add('hidden');
            document.getElementById('saveIndicator').style.display = 'none';
        }

        function toggleTheme() {
            darkTheme = !darkTheme;
            if (darkTheme) {
                document.body.classList.add('dark-theme');
                document.getElementById('themeToggle').innerHTML = '<i class="fas fa-sun"></i>';
            } else {
                document.body.classList.remove('dark-theme');
                document.getElementById('themeToggle').innerHTML = '<i class="fas fa-moon"></i>';
            }
        }

        function openProfileModal() {
            if (!appData) return;
            document.getElementById('modalGender').value = appData.profile.gender;
            document.getElementById('modalAge').value = appData.profile.age;
            document.getElementById('modalWeight').value = appData.profile.weight;
            document.getElementById('modalHeight').value = appData.profile.height;
            document.getElementById('modalTargetWeight').value = appData.profile.targetWeight;
            document.getElementById('modalActivity').value = appData.profile.activity;
            
            document.querySelectorAll('.avatar-option').forEach(opt => {
                opt.classList.remove('selected');
                if (opt.innerText === appData.profile.avatar) {
                    opt.classList.add('selected');
                }
            });
            
            document.getElementById('profileModal').style.display = 'flex';
        }

        function selectAvatar(avatar) {
            document.querySelectorAll('.avatar-option').forEach(opt => opt.classList.remove('selected'));
            event.target.classList.add('selected');
            appData.profile.avatar = avatar;
            document.getElementById('userAvatar').innerText = avatar;
        }

        function setReminder(time, message) {
            const [hours, minutes] = time.split(':');
            const now = new Date();
            const reminderTime = new Date();
            reminderTime.setHours(parseInt(hours), parseInt(minutes), 0, 0);
            
            if (reminderTime < now) {
                reminderTime.setDate(reminderTime.getDate() + 1);
            }
            
            const timeUntilReminder = reminderTime - now;
            
            setTimeout(() => {
                if (Notification.permission === 'granted') {
                    new Notification('FitДефицит', {
                        body: message,
                        icon: '/icon.png'
                    });
                    document.getElementById('notificationSound').play();
                }
                setReminder(time, message);
            }, timeUntilReminder);
            
            document.getElementById('saveStatus').innerText = `Напоминание на ${time}`;
        }

        function calculateTargetKcal() {
            const p = appData.profile;
            
            // Формула Миффлина-Сан Жеора
            let bmr;
            if (p.gender === 'male') {
                bmr = 10 * p.weight + 6.25 * p.height - 5 * p.age + 5;
            } else {
                bmr = 10 * p.weight + 6.25 * p.height - 5 * p.age - 161;
            }
            
            let maintenance = Math.round(bmr * p.activity);
            
            // Адаптивный дефицит в зависимости от веса
            let deficit;
            if (p.weight > 150) {
                // При очень большом весе дефицит 25% (безопасно)
                deficit = Math.round(maintenance * 0.75);
            } else if (p.weight > 120) {
                // При большом весе дефицит 22%
                deficit = Math.round(maintenance * 0.78);
            } else if (p.weight > 90) {
                // При избыточном весе дефицит 20%
                deficit = Math.round(maintenance * 0.8);
            } else {
                // При нормальном весе дефицит 18%
                deficit = Math.round(maintenance * 0.82);
            }
            
            // Нижняя граница безопасности (никогда не опускаемся ниже)
            return Math.max(1500, deficit);
        }

        function getPortionMultiplier() {
            const weight = appData.profile.weight;
            
            if (weight >= 150) return 1.6;      // +60% еды
            if (weight >= 120) return 1.4;      // +40% еды
            if (weight >= 100) return 1.2;      // +20% еды
            if (weight >= 80) return 1.1;       // +10% еды
            return 1.0;                          // стандарт
        }

        function generateMealsForDay(day, month) {
            const monthData = foodDB[month % foodDB.length];
            const seed = (day * 7 + month * 13 + appData.profile.weight) % 17;
            const multiplier = getPortionMultiplier();
            
            return [
                adjustPortion({ ...monthData.завтрак[seed % monthData.завтрак.length] }, multiplier),
                adjustPortion({ ...monthData.обед[(seed + 4) % monthData.обед.length] }, multiplier),
                adjustPortion({ ...monthData.ужин[(seed + 8) % monthData.ужин.length] }, multiplier),
                adjustPortion({ ...monthData.перекус[(seed + 12) % monthData.перекус.length] }, multiplier)
            ];
        }

        function adjustPortion(meal, multiplier) {
            if (multiplier > 1) {
                // Увеличиваем граммовку и калории пропорционально
                meal.gramms = Math.round(meal.gramms * multiplier);
                meal.kcal = Math.round(meal.kcal * multiplier);
                meal.prot = Math.round(meal.prot * multiplier);
                meal.fat = Math.round(meal.fat * multiplier);
                meal.carbs = Math.round(meal.carbs * multiplier);
            }
            return meal;
        }

        function getCurrentDayNumber() {
            const dayName = document.getElementById('currentDayName').innerText;
            const match = dayName.match(/^(\d+)/);
            return match ? parseInt(match[1]) : new Date().getDate();
        }

        function calculateStats() {
            let totalDeficit = 0;
            let totalWorkouts = 0;
            let daysCount = 0;
            
            for (const key in appData.consumedMeals) {
                const [year, month, day] = key.split('_').map(Number);
                const meals = appData.consumedMeals[key];
                const totalKcal = meals.reduce((sum, m) => sum + m.kcal, 0);
                const target = calculateTargetKcal();
                const workoutKey = `${year}_${month}_${day}`;
                const workoutDone = appData.completedWorkouts[workoutKey] || false;
                const workoutBurn = workoutDone ? workouts[day % 7].burn : 0;
                const deficit = target - totalKcal + workoutBurn;
                if (deficit > 0) {
                    totalDeficit += deficit;
                    daysCount++;
                }
                if (workoutDone) totalWorkouts++;
            }
            
            return { totalDeficit, totalWorkouts, daysCount };
        }

        function renderMonthGrid() {
            const grid = document.getElementById('monthGrid');
            grid.innerHTML = '';
            for (let i = 0; i < 12; i++) {
                const card = document.createElement('div');
                card.className = `month-card ${i === currentMonth ? 'active' : ''}`;
                card.innerHTML = `<i>${monthIcons[i]}</i>${months[i]}`;
                card.onclick = () => setMonth(i);
                grid.appendChild(card);
            }
            if (calendarCollapsed) {
                grid.classList.add('collapsed');
            } else {
                grid.classList.remove('collapsed');
            }
        }

        function toggleCalendar() {
            calendarCollapsed = !calendarCollapsed;
            const grid = document.getElementById('monthGrid');
            const icon = document.getElementById('toggleIcon');
            if (calendarCollapsed) {
                grid.classList.add('collapsed');
                icon.classList.add('rotated');
            } else {
                grid.classList.remove('collapsed');
                icon.classList.remove('rotated');
            }
        }

        function toggleWeek() {
            weekCollapsed = !weekCollapsed;
            const buttons = document.getElementById('dayButtons');
            const icon = document.getElementById('weekToggleIcon');
            if (weekCollapsed) {
                buttons.classList.add('collapsed');
                icon.classList.add('rotated');
            } else {
                buttons.classList.remove('collapsed');
                icon.classList.remove('rotated');
            }
        }

        function setMonth(monthIndex) {
            currentMonth = monthIndex;
            renderDayButtons();
            renderCurrentDay();
        }

        function renderDayButtons() {
            const container = document.getElementById('dayButtons');
            const daysInMonth = getMonthDays(currentYear, currentMonth);
            const firstDay = getFirstDayOfMonth(currentYear, currentMonth);
            
            container.innerHTML = '';
            for (let i = 0; i < firstDay; i++) {
                container.innerHTML += `<div class="day-btn" style="visibility: hidden;"></div>`;
            }
            
            for (let day = 1; day <= daysInMonth; day++) {
                const date = new Date(currentYear, currentMonth, day);
                const dayOfWeek = date.getDay();
                const workoutKey = `${currentYear}_${currentMonth}_${day}`;
                const workoutDone = appData.completedWorkouts[workoutKey] || false;
                
                container.innerHTML += `
                    <button class="day-btn ${dayOfWeek === 0 || dayOfWeek === 6 ? 'weekend' : ''}" onclick="setDay(${day})">
                        ${day} ${workoutDone ? '✅' : ''}
                    </button>
                `;
            }
        }

        function setDay(day) {
            const mealKey = `${currentYear}_${currentMonth}_${day}`;
            const date = new Date(currentYear, currentMonth, day);
            const dayOfWeek = date.getDay();
            document.getElementById('currentDayName').innerHTML = `${day} ${months[currentMonth]} (${weekDays[dayOfWeek]})`;

            if (!appData.consumedMeals[mealKey]) {
                appData.consumedMeals[mealKey] = generateMealsForDay(day, currentMonth);
            }
            
            const meals = appData.consumedMeals[mealKey];
            const container = document.getElementById('mealsList');
            container.innerHTML = '';
            let totalGramms = 0;
            
            meals.forEach(meal => {
                totalGramms += meal.gramms || 150;
                container.innerHTML += `
                    <div class="meal-item">
                        <div class="meal-info">
                            <h4>${meal.name} <span class="meal-gramms">${meal.gramms || 150} г</span></h4>
                            <p>б ${meal.prot} · ж ${meal.fat} · у ${meal.carbs}</p>
                        </div>
                        <div class="meal-kcal">${meal.kcal}</div>
                    </div>
                `;
            });

            document.getElementById('monthGramms').innerHTML = `≈ ${totalGramms} г`;

            const totalKcal = meals.reduce((sum, m) => sum + m.kcal, 0);
            const target = calculateTargetKcal();
            const workoutKey = `${currentYear}_${currentMonth}_${day}`;
            const workoutDone = appData.completedWorkouts[workoutKey] || false;
            const workoutBurn = workoutDone ? workouts[dayOfWeek].burn : 0;
            const deficit = target - totalKcal + workoutBurn;
            
            document.getElementById('todayKcal').innerText = totalKcal;
            document.getElementById('todayTarget').innerText = target;
            document.getElementById('deficitBadge').innerHTML = (deficit > 0 ? '+' : '') + deficit + ' ккал';
            document.getElementById('progressFill').style.width = Math.min(100, (totalKcal / target) * 100) + '%';

            const w = workouts[dayOfWeek];
            document.getElementById('workoutContainer').innerHTML = `
                <div class="workout-card ${workoutDone ? 'completed' : ''}" onclick="toggleWorkout(${day})">
                    <div class="workout-header">
                        <span class="workout-name">${w.name}</span>
                        <span class="workout-burn"><i class="fas fa-bolt"></i> ${w.burn}</span>
                    </div>
                    <div class="workout-desc">${w.desc}</div>
                    ${workoutDone ? '<div style="color:#27ae60; margin-top:10px;"><i class="fas fa-check-circle"></i> Выполнено</div>' : ''}
                </div>
            `;
        }

        function toggleWorkout(day) {
            const workoutKey = `${currentYear}_${currentMonth}_${day}`;
            appData.completedWorkouts[workoutKey] = !appData.completedWorkouts[workoutKey];
            saveUsers();
            renderDayButtons();
            setDay(day);
            renderStats();
        }

        function renderStats() {
            const stats = calculateStats();
            const totalLoss = (stats.totalDeficit / 7700).toFixed(2);
            const avgDeficit = stats.daysCount > 0 ? Math.round(stats.totalDeficit / stats.daysCount) : 0;
            
            document.getElementById('totalDeficit').innerText = stats.totalDeficit;
            document.getElementById('totalLoss').innerText = totalLoss;
            document.getElementById('totalWorkouts').innerText = stats.totalWorkouts;
            document.getElementById('avgDeficit').innerText = avgDeficit;

            let motivation = '';
            if (stats.totalWorkouts > 50) motivation = '🔥 Вы настоящий чемпион!';
            else if (stats.totalWorkouts > 30) motivation = '💪 Отличная дисциплина!';
            else if (stats.totalWorkouts > 10) motivation = '👍 Хороший старт!';
            else motivation = '🌟 Начните с малого, каждый шаг важен!';
            
            document.getElementById('motivationText').innerHTML = `💪 ${motivation}`;

            const start = appData.profile.startWeight || appData.profile.weight;
            const current = appData.profile.weight;
            const target = appData.profile.targetWeight;
            const progress = ((start - current) / (start - target)) * 100;
            document.getElementById('goalProgress').style.width = Math.min(100, Math.max(0, progress)) + '%';
            document.getElementById('goalProgressText').innerText = Math.round(progress) + '%';
            document.getElementById('targetWeight').innerText = target;

            const monthlyContainer = document.getElementById('monthlyProgress');
            monthlyContainer.innerHTML = '';
            
            for (let month = 0; month < 12; month++) {
                let workoutsCount = 0;
                const daysInMonth = getMonthDays(currentYear, month);
                for (let day = 1; day <= daysInMonth; day++) {
                    const workoutKey = `${currentYear}_${month}_${day}`;
                    if (appData.completedWorkouts[workoutKey]) workoutsCount++;
                }
                const percent = (workoutsCount / (daysInMonth * 0.3)) * 100;
                
                monthlyContainer.innerHTML += `
                    <div class="progress-month">
                        <div class="progress-month-header">
                            <span>${months[month]}</span>
                            <span>${workoutsCount} тренировок</span>
                        </div>
                        <div class="month-bar">
                            <div class="month-bar-fill" style="width: ${Math.min(100, percent)}%"></div>
                        </div>
                    </div>
                `;
            }
        }

        function renderAll() {
            renderMonthGrid();
            renderDayButtons();
            setDay(new Date().getDate());
            renderStats();
            document.getElementById('saveStatus').innerText = 'Сохранено';
        }

        function saveToStorage() {
            if (currentUser) {
                users[currentUser] = appData;
                saveUsers();
                document.getElementById('saveStatus').innerText = 'Сохранено ' + new Date().toLocaleTimeString();
            }
        }

        window.addEventListener('load', () => {
            loadUsers();
            const savedUser = sessionStorage.getItem('currentUser');
            if (savedUser && users[savedUser]) {
                login(savedUser);
            }

            document.getElementById('closeHelp').addEventListener('click', () => {
                document.getElementById('helpBubble').style.display = 'none';
            });

            document.getElementById('calendarHeader').addEventListener('click', toggleCalendar);
            document.getElementById('weekHeader').addEventListener('click', toggleWeek);
            document.getElementById('themeToggle').addEventListener('click', toggleTheme);

            document.getElementById('planTab').addEventListener('click', () => {
                document.getElementById('planTab').classList.add('active');
                document.getElementById('statsTab').classList.remove('active');
                document.getElementById('planContent').classList.remove('hidden');
                document.getElementById('statsContent').classList.add('hidden');
            });

            document.getElementById('statsTab').addEventListener('click', () => {
                document.getElementById('statsTab').classList.add('active');
                document.getElementById('planTab').classList.remove('active');
                document.getElementById('statsContent').classList.remove('hidden');
                document.getElementById('planContent').classList.add('hidden');
                renderStats();
            });

            document.getElementById('loginBtn').addEventListener('click', () => {
                login(document.getElementById('loginUsername').value);
            });

            document.getElementById('loginUsername').addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    login(document.getElementById('loginUsername').value);
                }
            });

            document.getElementById('logoutBtn').addEventListener('click', logout);

            document.getElementById('setMorningReminder').addEventListener('click', () => {
                const time = document.getElementById('reminderTime').value;
                setReminder(time, 'Пора завтракать! 🌅');
            });

            document.getElementById('setLunchReminder').addEventListener('click', () => {
                const time = document.getElementById('lunchReminder').value;
                setReminder(time, 'Пора обедать! 🍲');
            });

            document.getElementById('setWorkoutReminder').addEventListener('click', () => {
                const time = document.getElementById('workoutReminder').value;
                setReminder(time, 'Время тренировки! 💪');
            });

            document.getElementById('addSnackBtn').addEventListener('click', () => {
                const day = getCurrentDayNumber();
                const mealKey = `${currentYear}_${currentMonth}_${day}`;
                if (!appData.consumedMeals[mealKey]) {
                    appData.consumedMeals[mealKey] = generateMealsForDay(day, currentMonth);
                }
                
                const multiplier = getPortionMultiplier();
                const snack = {
                    name: '🍎 Легкий перекус',
                    prot: 8,
                    fat: 5,
                    carbs: 15,
                    kcal: 150,
                    gramms: 180
                };
                
                appData.consumedMeals[mealKey].push(adjustPortion(snack, multiplier));
                saveToStorage();
                setDay(day);
                renderStats();
            });

            document.getElementById('manualSaveBtn').addEventListener('click', saveToStorage);

            document.getElementById('saveProfileBtn').addEventListener('click', () => {
                appData.profile.gender = document.getElementById('modalGender').value;
                appData.profile.age = parseInt(document.getElementById('modalAge').value) || 30;
                appData.profile.weight = parseFloat(document.getElementById('modalWeight').value) || 70;
                appData.profile.height = parseInt(document.getElementById('modalHeight').value) || 170;
                appData.profile.targetWeight = parseFloat(document.getElementById('modalTargetWeight').value) || 70;
                appData.profile.activity = parseFloat(document.getElementById('modalActivity').value) || 1.375;
                
                if (!appData.profile.startWeight) {
                    appData.profile.startWeight = appData.profile.weight;
                }
                
                // Очищаем сохранённое меню, чтобы пересчитать порции под новый вес
                appData.consumedMeals = {};
                
                saveToStorage();
                renderAll();
                document.getElementById('profileModal').style.display = 'none';
            });

            window.addEventListener('click', (e) => {
                if (e.target.classList.contains('modal')) {
                    e.target.style.display = 'none';
                }
            });

            setInterval(saveToStorage, 30000);
        });
    </script>
</body>
</html>
