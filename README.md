<!DOCTYPE html>
<html lang="lo">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ລະບົບຂາຍແຊນວິດ</title>
    <script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Lao:wght@100;200;300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Noto Sans Lao', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 10px;
            color: #333;
        }

        .container {
            max-width: 500px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            padding: 30px 20px;
            text-align: center;
            color: white;
        }

        .header h1 {
            font-size: 28px;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .header p {
            font-size: 16px;
            opacity: 0.9;
        }

        .nav-tabs {
            display: flex;
            background: #f8f9fa;
            border-bottom: 2px solid #e9ecef;
        }

        .nav-tab {
            flex: 1;
            padding: 15px 10px;
            text-align: center;
            background: none;
            border: none;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            color: #6c757d;
            transition: all 0.3s ease;
        }

        .nav-tab.active {
            background: #4facfe;
            color: white;
            transform: translateY(-2px);
        }

        .nav-tab:hover {
            background: #e9ecef;
            color: #495057;
        }

        .nav-tab.active:hover {
            background: #4facfe;
            color: white;
        }

        .content {
            padding: 20px;
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #495057;
            font-size: 14px;
        }

        .form-control {
            width: 100%;
            padding: 15px;
            border: 2px solid #e9ecef;
            border-radius: 12px;
            font-size: 16px;
            transition: all 0.3s ease;
            background: #f8f9fa;
        }

        .form-control:focus {
            outline: none;
            border-color: #4facfe;
            background: white;
            box-shadow: 0 0 0 3px rgba(79, 172, 254, 0.1);
        }

        .btn {
            width: 100%;
            padding: 18px;
            border: none;
            border-radius: 12px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .btn-primary {
            background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
            color: white;
            box-shadow: 0 8px 25px rgba(79, 172, 254, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 35px rgba(79, 172, 254, 0.4);
        }

        .btn-secondary {
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
            color: #495057;
            box-shadow: 0 8px 25px rgba(168, 237, 234, 0.3);
        }

        .btn-secondary:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 35px rgba(168, 237, 234, 0.4);
        }

        .btn-success {
            background: linear-gradient(135deg, #84fab0 0%, #8fd3f4 100%);
            color: white;
            box-shadow: 0 8px 25px rgba(132, 250, 176, 0.3);
        }

        .btn-success:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 35px rgba(132, 250, 176, 0.4);
        }

        .row {
            display: flex;
            gap: 10px;
        }

        .col-half {
            flex: 1;
        }

        .alert {
            padding: 15px;
            border-radius: 12px;
            margin-bottom: 20px;
            font-weight: 600;
            text-align: center;
            display: none;
        }

        .alert-success {
            background: #d4edda;
            color: #155724;
            border: 2px solid #c3e6cb;
        }

        .alert-error {
            background: #f8d7da;
            color: #721c24;
            border: 2px solid #f5c6cb;
        }

        .menu-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px;
            margin-bottom: 10px;
            background: #f8f9fa;
            border-radius: 12px;
            border: 2px solid #e9ecef;
        }

        .menu-item:hover {
            background: #e9ecef;
            border-color: #4facfe;
        }

        .menu-item span {
            font-weight: 600;
            color: #495057;
        }

        .menu-item .price {
            color: #4facfe;
            font-size: 18px;
            font-weight: 700;
        }

        .chart-container {
            margin: 20px 0;
            padding: 20px;
            background: #f8f9fa;
            border-radius: 12px;
            border: 2px solid #e9ecef;
        }

        .loading {
            text-align: center;
            padding: 40px;
            color: #6c757d;
        }

        .loading::after {
            content: "";
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid #f3f3f3;
            border-top: 3px solid #4facfe;
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin-left: 10px;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .stats-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 20px;
        }

        .stat-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.3);
        }

        .stat-card h3 {
            font-size: 24px;
            margin-bottom: 5px;
        }

        .stat-card p {
            font-size: 12px;
            opacity: 0.9;
        }

        .profit-sharing-container {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
            border: 2px solid #e9ecef;
        }

        .sharing-config {
            margin-bottom: 20px;
            padding: 15px;
            background: white;
            border-radius: 12px;
            border: 2px solid #e9ecef;
        }

        .expense-breakdown {
            margin-bottom: 20px;
        }

        .expense-cards {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-top: 10px;
        }

        .expense-card {
            background: linear-gradient(135deg, #ffeaa7 0%, #fab1a0 100%);
            padding: 15px;
            border-radius: 12px;
            text-align: center;
            color: white;
            box-shadow: 0 8px 25px rgba(255, 234, 167, 0.3);
        }

        .expense-person {
            font-weight: 600;
            font-size: 14px;
            margin-bottom: 5px;
        }

        .expense-amount {
            font-size: 18px;
            font-weight: 700;
        }

        .calculation-cards {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
        }

        .calculation-card {
            background: white;
            border-radius: 12px;
            padding: 20px;
            border: 2px solid #e9ecef;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .wife-card {
            border-left: 5px solid #ff7675;
        }

        .friend-card {
            border-left: 5px solid #74b9ff;
        }

        .person-name {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 15px;
            color: #2d3436;
        }

        .calculation-details {
            space-y: 10px;
        }

        .calculation-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 8px 0;
            border-bottom: 1px solid #f1f2f6;
        }

        .calculation-row.total {
            border-bottom: none;
            border-top: 2px solid #4facfe;
            font-weight: 700;
            font-size: 16px;
            color: #2d3436;
            margin-top: 10px;
            padding-top: 15px;
        }

        .calculation-row span:last-child {
            font-weight: 600;
            color: #4facfe;
        }

        .calculation-row.total span:last-child {
            color: #00b894;
            font-size: 18px;
        }

        .date-filter-container {
            background: #f8f9fa;
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
            border: 2px solid #e9ecef;
        }

        .quick-date-buttons {
            display: flex;
            gap: 8px;
            margin-top: 15px;
            flex-wrap: wrap;
        }

        .btn-quick {
            padding: 8px 15px;
            border: 2px solid #4facfe;
            background: white;
            color: #4facfe;
            border-radius: 20px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            flex: 1;
            min-width: 60px;
        }

        .btn-quick:hover {
            background: #4facfe;
            color: white;
            transform: translateY(-1px);
        }

        .btn-quick.active {
            background: #4facfe;
            color: white;
        }

        @media (max-width: 480px) {
            .container {
                margin: 0;
                border-radius: 0;
                min-height: 100vh;
            }
            
            .header {
                padding: 20px 15px;
            }
            
            .content {
                padding: 15px;
            }
            
            .nav-tab {
                font-size: 12px;
                padding: 12px 8px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🥪 ລະບົບຂາຍແຊນວິດ</h1>
            <p>ລະບົບຂາຍແຊນວິດງ່າຍໆ</p>
        </div>

        <div class="nav-tabs">
            <button class="nav-tab active" onclick="showTab('sale')">💰 ຂາຍ</button>
            <button class="nav-tab" onclick="showTab('expense')">📝 ລາຍຈ່າຍ</button>
            <button class="nav-tab" onclick="showTab('menu')">🍽️ ເມນູ</button>
            <button class="nav-tab" onclick="showTab('dashboard')">📊 ລາຍງານ</button>
        </div>

        <div class="content">
            <!-- แจ้งเตือน -->
            <div id="alert" class="alert"></div>

            <!-- ฟอร์มบันทึกการขาย -->
            <div id="sale-tab" class="tab-content active">
                <h2 style="margin-bottom: 20px; color: #495057;">ບັນທຶກການຂາຍ</h2>
                <form id="saleForm">
                    <div class="form-group">
                        <label>ວັນທີ່ຂາຍ</label>
                        <input type="date" id="saleDate" class="form-control" required>
                    </div>
                    <div class="form-group">
                        <label>ເລືອກເມນູ</label>
                        <select id="menuSelect" class="form-control" required>
                            <option value="">-- ເລືອກເມນູ --</option>
                        </select>
                    </div>
                    <div class="row">
                        <div class="col-half">
                            <div class="form-group">
                                <label>ຈຳນວນ</label>
                                <input type="number" id="quantity" class="form-control" min="1" required>
                            </div>
                        </div>
                        <div class="col-half">
                            <div class="form-group">
                                <label>ລາຄາ (ກີບ)</label>
                                <input type="number" id="price" class="form-control" min="0" step="0.01" required>
                            </div>
                        </div>
                    </div>
                    <div class="form-group">
                        <label>ຜູ້ຂາຍ</label>
                        <select id="sellerSelect" class="form-control" required>
                            <option value="">-- ເລືອກຜູ້ຂາຍ --</option>
                            <option value="Ms Nie">Ms Nie</option>
                            <option value="Ms Bie">Ms Bie</option>
                        </select>
                    </div>
                    <button type="submit" class="btn btn-primary">ບັນທຶກການຂາຍ</button>
                </form>
            </div>

            <!-- ฟอร์มบันทึกรายจ่าย -->
            <div id="expense-tab" class="tab-content">
                <h2 style="margin-bottom: 20px; color: #495057;">ບັນທຶກລາຍຈ່າຍ</h2>
                <form id="expenseForm">
                    <div class="form-group">
                        <label>ວັນທີ່ຈ່າຍ</label>
                        <input type="date" id="expenseDate" class="form-control" required>
                    </div>
                    <div class="form-group">
                        <label>ລາຍການ</label>
                        <input type="text" id="expenseItem" class="form-control" placeholder="ເຊັ່ນ: ວັດຖຸດິບ, ຄ່ານ້ຳມັນ" required>
                    </div>
                    <div class="form-group">
                        <label>ຈຳນວນເງິນ (ກີບ)</label>
                        <input type="number" id="expenseAmount" class="form-control" min="0" step="0.01" required>
                    </div>
                    <div class="form-group">
                        <label>ຜູ້ຈ່າຍ</label>
                        <select id="expensePayer" class="form-control" required>
                            <option value="">-- ເລືອກຜູ້ຈ່າຍ --</option>
                            <option value="Ms Nie">Ms Nie</option>
                            <option value="Ms Bie">Ms Bie</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>ໝາຍເຫດ</label>
                        <textarea id="expenseNote" class="form-control" rows="3" placeholder="ໝາຍເຫດເພີ່ມເຕີມ (ຖ້າມີ)"></textarea>
                    </div>
                    <button type="submit" class="btn btn-secondary">ບັນທຶກລາຍຈ່າຍ</button>
                </form>
            </div>

            <!-- ฟอร์มจัดการเมนู -->
            <div id="menu-tab" class="tab-content">
                <h2 style="margin-bottom: 20px; color: #495057;">ຈັດການເມນູ</h2>
                
                <div id="menuList" class="loading">ກຳລັງໂຫລດເມນູ...</div>

                <h3 style="margin: 30px 0 20px 0; color: #495057;">ເພີ່ມເມນູໃໝ່</h3>
                <form id="menuForm">
                    <div class="form-group">
                        <label>ຊື່ເມນູ</label>
                        <input type="text" id="menuName" class="form-control" placeholder="ເຊັ່ນ: Tuna Sandwich" required>
                    </div>
                    <div class="form-group">
                        <label>ລາຄາ (ກີບ)</label>
                        <input type="number" id="menuPrice" class="form-control" min="0" step="0.01" required>
                    </div>
                    <button type="submit" class="btn btn-success">ເພີ່ມເມນູ</button>
                </form>
            </div>

            <!-- แดชบอร์ด -->
            <div id="dashboard-tab" class="tab-content">
                <h2 style="margin-bottom: 20px; color: #495057;">สรุปยอดขาย</h2>
                
                <div class="stats-grid">
                    <div class="stat-card">
                        <h3 id="totalSales">0</h3>
                        <p>ยอดขายรวม</p>
                    </div>
                    <div class="stat-card">
                        <h3 id="totalExpenses">0</h3>
                        <p>รายจ่ายรวม</p>
                    </div>
                    <div class="stat-card">
                        <h3 id="netProfit">0</h3>
                        <p>กำไรสุทธิ</p>
                    </div>
                    <div class="stat-card">
                        <h3 id="profitPerPerson">0</h3>
                        <p>กำไรต่อคน</p>
                    </div>
                </div>

                <!-- การแบ่งกำไรแบบละเอียด -->
                <div class="profit-sharing-container">
                    <h3 style="margin-bottom: 15px; color: #495057;">💰 การแบ่งกำไรรายละเอียด</h3>
                    
                    <div class="sharing-config">
                        <label style="display: block; margin-bottom: 10px; font-weight: 600;">สัดส่วนการแบ่งกำไร:</label>
                        <div class="row">
                            <div class="col-half">
                                <div class="form-group">
                                    <label>ภรรยา (%)</label>
                                    <input type="number" id="wifePercent" class="form-control" value="50" min="0" max="100" onchange="updateProfitSharing()">
                                </div>
                            </div>
                            <div class="col-half">
                                <div class="form-group">
                                    <label>เพื่อน (%)</label>
                                    <input type="number" id="friendPercent" class="form-control" value="50" min="0" max="100" onchange="updateProfitSharing()">
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="sharing-details">
                        <div class="expense-breakdown">
                            <h4 style="color: #495057; margin-bottom: 10px;">📋 การออกเงินรายจ่าย</h4>
                            <div class="expense-cards">
                                <div class="expense-card">
                                    <div class="expense-person">👩 ภรรยา</div>
                                    <div class="expense-amount" id="wifeExpenses">0 บาท</div>
                                </div>
                                <div class="expense-card">
                                    <div class="expense-person">👨 เพื่อน</div>
                                    <div class="expense-amount" id="friendExpenses">0 บาท</div>
                                </div>
                            </div>
                        </div>

                        <div class="final-calculation">
                            <h4 style="color: #495057; margin: 20px 0 10px 0;">🧮 การคำนวณสุดท้าย</h4>
                            <div class="calculation-cards">
                                <div class="calculation-card wife-card">
                                    <div class="person-name">👩 ภรรยา</div>
                                    <div class="calculation-details">
                                        <div class="calculation-row">
                                            <span>กำไรที่ควรได้:</span>
                                            <span id="wifeDeservedProfit">0 บาท</span>
                                        </div>
                                        <div class="calculation-row">
                                            <span>เงินที่ออกไปแล้ว:</span>
                                            <span id="wifeExpensesCalc">0 บาท</span>
                                        </div>
                                        <div class="calculation-row total">
                                            <span>รับจริง:</span>
                                            <span id="wifeFinalAmount">0 บาท</span>
                                        </div>
                                    </div>
                                </div>
                                
                                <div class="calculation-card friend-card">
                                    <div class="person-name">👨 เพื่อน</div>
                                    <div class="calculation-details">
                                        <div class="calculation-row">
                                            <span>กำไรที่ควรได้:</span>
                                            <span id="friendDeservedProfit">0 บาท</span>
                                        </div>
                                        <div class="calculation-row">
                                            <span>เงินที่ออกไปแล้ว:</span>
                                            <span id="friendExpensesCalc">0 บาท</span>
                                        </div>
                                        <div class="calculation-row total">
                                            <span>รับจริง:</span>
                                            <span id="friendFinalAmount">0 บาท</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="chart-container">
                    <h3 style="margin-bottom: 15px; color: #495057;">📊 กราฟยอดขายรายวัน</h3>
                    <div id="salesChart" class="loading">กำลังโหลดข้อมูล...</div>
                </div>

                <button onclick="loadDashboard()" class="btn btn-primary">รีเฟรชข้อมูล</button>
            </div>
        </div>
    </div>

    <script>
        // ตั้งค่า Google Apps Script URL
        const SCRIPT_URL = 'https://script.google.com/macros/s/YOUR_SCRIPT_ID/exec';

        // โหลด Google Charts
        google.charts.load('current', {'packages':['corechart']});

        // ฟังก์ชันแสดงแท็บ
        function showTab(tabName) {
            // ซ่อนทุกแท็บ
            const tabs = document.querySelectorAll('.tab-content');
            tabs.forEach(tab => tab.classList.remove('active'));
            
            // ซ่อนทุกปุ่มแท็บ
            const navTabs = document.querySelectorAll('.nav-tab');
            navTabs.forEach(tab => tab.classList.remove('active'));
            
            // แสดงแท็บที่เลือก
            document.getElementById(tabName + '-tab').classList.add('active');
            event.target.classList.add('active');
            
            // โหลดข้อมูลตามแท็บ
            if (tabName === 'menu') {
                loadMenuList();
            } else if (tabName === 'dashboard') {
                loadDashboard();
            }
        }

        // ฟังก์ชันแสดงแจ้งเตือน
        function showAlert(message, type = 'success') {
            const alert = document.getElementById('alert');
            alert.textContent = message;
            alert.className = `alert alert-${type}`;
            alert.style.display = 'block';
            
            setTimeout(() => {
                alert.style.display = 'none';
            }, 3000);
        }

        // ฟังก์ชันส่งข้อมูลไป Google Apps Script
        async function sendToGoogleSheets(action, data) {
            try {
                const response = await fetch(SCRIPT_URL, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify({
                        action: action,
                        data: data
                    })
                });
                
                if (!response.ok) {
                    throw new Error('Network response was not ok');
                }
                
                const result = await response.json();
                return result;
            } catch (error) {
                console.error('Error:', error);
                throw error;
            }
        }

        // ฟังก์ชันโหลดเมนู
        async function loadMenuList() {
            try {
                const result = await sendToGoogleSheets('getMenu', {});
                const menuList = document.getElementById('menuList');
                const menuSelect = document.getElementById('menuSelect');
                
                if (result.success && result.data) {
                    // แสดงรายการเมนูในแท็บเมนู
                    menuList.innerHTML = '';
                    result.data.forEach(item => {
                        const menuItem = document.createElement('div');
                        menuItem.className = 'menu-item';
                        menuItem.innerHTML = `
                            <span>${item.name}</span>
                            <span class="price">${item.price} ກີບ</span>
                        `;
                        menuList.appendChild(menuItem);
                    });
                    
                    // อัปเดต dropdown ในฟอร์มขาย
                    menuSelect.innerHTML = '<option value="">-- ເລືອກເມນູ --</option>';
                    result.data.forEach(item => {
                        const option = document.createElement('option');
                        option.value = item.name;
                        option.textContent = `${item.name} (${item.price} ກີບ)`;
                        option.dataset.price = item.price;
                        menuSelect.appendChild(option);
                    });
                } else {
                    menuList.innerHTML = '<p>ບໍ່ພົບຂໍ້ມູນເມນູ</p>';
                }
            } catch (error) {
                document.getElementById('menuList').innerHTML = '<p>ເກີດຂໍ້ຜິດພາດໃນການໂຫລດເມນູ</p>';
            }
        }

        // ฟังก์ชันโหลดแดชบอร์ด
        async function loadDashboard() {
            try {
                const startDate = document.getElementById('startDate').value;
                const endDate = document.getElementById('endDate').value;
                
                const result = await sendToGoogleSheets('getSummary', {
                    startDate: startDate,
                    endDate: endDate
                });
                
                if (result.success && result.data) {
                    const data = result.data;
                    document.getElementById('totalSales').textContent = data.totalSales.toLocaleString();
                    document.getElementById('totalExpenses').textContent = data.totalExpenses.toLocaleString();
                    document.getElementById('netProfit').textContent = data.netProfit.toLocaleString();
                    document.getElementById('profitPerPerson').textContent = data.profitPerPerson.toLocaleString();
                    
                    // อัปเดตข้อมูลการแบ่งกำไร
                    if (data.expensesByPerson) {
                        document.getElementById('wifeExpenses').textContent = data.expensesByPerson['Ms Nie'].toLocaleString() + ' ກີບ';
                        document.getElementById('friendExpenses').textContent = data.expensesByPerson['Ms Bie'].toLocaleString() + ' ກີບ';
                        
                        // เก็บข้อมูลสำหรับการคำนวณ
                        window.dashboardData = data;
                        updateProfitSharing();
                    }
                    
                    // แสดงกราฟ
                    if (data.dailySales && data.dailySales.length > 0) {
                        drawSalesChart(data.dailySales);
                    }
                }
            } catch (error) {
                console.error('Error loading dashboard:', error);
            }
        }

        // ฟังก์ชันตั้งค่าวันที่แบบเร็ว
        function setQuickDate(type) {
            const today = new Date();
            const todayStr = today.toISOString().split('T')[0];
            
            // ลบ active class จากปุ่มทั้งหมด
            document.querySelectorAll('.btn-quick').forEach(btn => btn.classList.remove('active'));
            
            let startDate, endDate;
            
            switch(type) {
                case 'today':
                    startDate = endDate = todayStr;
                    event.target.classList.add('active');
                    break;
                case 'yesterday':
                    const yesterday = new Date(today);
                    yesterday.setDate(yesterday.getDate() - 1);
                    startDate = endDate = yesterday.toISOString().split('T')[0];
                    event.target.classList.add('active');
                    break;
                case 'week':
                    const weekAgo = new Date(today);
                    weekAgo.setDate(weekAgo.getDate() - 7);
                    startDate = weekAgo.toISOString().split('T')[0];
                    endDate = todayStr;
                    event.target.classList.add('active');
                    break;
                case 'month':
                    const monthAgo = new Date(today);
                    monthAgo.setDate(monthAgo.getDate() - 30);
                    startDate = monthAgo.toISOString().split('T')[0];
                    endDate = todayStr;
                    event.target.classList.add('active');
                    break;
                case 'all':
                    startDate = '';
                    endDate = '';
                    event.target.classList.add('active');
                    break;
            }
            
            document.getElementById('startDate').value = startDate;
            document.getElementById('endDate').value = endDate;
            
            // โหลดข้อมูลใหม่
            loadDashboard();
        }

        // ฟังก์ชันคำนวณการแบ่งกำไร
        function updateProfitSharing() {
            if (!window.dashboardData) return;
            
            const data = window.dashboardData;
            const wifePercent = parseFloat(document.getElementById('wifePercent').value) || 0;
            const friendPercent = parseFloat(document.getElementById('friendPercent').value) || 0;
            
            // ตรวจสอบให้รวมเป็น 100%
            if (wifePercent + friendPercent !== 100) {
                document.getElementById('friendPercent').value = 100 - wifePercent;
            }
            
            const netProfit = data.netProfit || 0;
            const wifeExpenses = data.expensesByPerson['Ms Nie'] || 0;
            const friendExpenses = data.expensesByPerson['Ms Bie'] || 0;
            
            // คำนวณกำไรที่แต่ละคนควรได้
            const wifeDeservedProfit = (netProfit * wifePercent) / 100;
            const friendDeservedProfit = (netProfit * friendPercent) / 100;
            
            // คำนวณเงินที่รับจริง (กำไรที่ควรได้ + เงินที่ออกไปแล้ว)
            const wifeFinalAmount = wifeDeservedProfit + wifeExpenses;
            const friendFinalAmount = friendDeservedProfit + friendExpenses;
            
            // อัปเดตการแสดงผล
            document.getElementById('wifeExpensesCalc').textContent = wifeExpenses.toLocaleString() + ' ກີບ';
            document.getElementById('friendExpensesCalc').textContent = friendExpenses.toLocaleString() + ' ກີບ';
            
            document.getElementById('wifeDeservedProfit').textContent = wifeDeservedProfit.toLocaleString() + ' ກີບ';
            document.getElementById('friendDeservedProfit').textContent = friendDeservedProfit.toLocaleString() + ' ກີບ';
            
            document.getElementById('wifeFinalAmount').textContent = wifeFinalAmount.toLocaleString() + ' ກີບ';
            document.getElementById('friendFinalAmount').textContent = friendFinalAmount.toLocaleString() + ' ກີບ';
        }

                // ฟังก์ชันแสดงกราฟ
        function drawSalesChart(dailySales) {
            const data = new google.visualization.DataTable();
            data.addColumn('string', 'ວັນທີ່');
            data.addColumn('number', 'ຍອດຂາຍ');
            
            dailySales.forEach(item => {
                data.addRow([item.date, item.sales]);
            });
            
            const options = {
                title: 'ກຣາຟຍອດຂາຍລາຍວັນ',
                titleTextStyle: {
                    fontSize: 16,
                    bold: true
                },
                hAxis: {
                    title: 'ວັນທີ່',
                    titleTextStyle: {fontSize: 12}
                },
                vAxis: {
                    title: 'ຍອດຂາຍ (ກີບ)',
                    titleTextStyle: {fontSize: 12}
                },
                legend: 'none',
                backgroundColor: 'transparent',
                colors: ['#4facfe'],
                curveType: 'function',
                pointSize: 5
            };
            
            const chart = new google.visualization.LineChart(document.getElementById('salesChart'));
            chart.draw(data, options);
        }

        // Event Listener สำหรับฟอร์มขาย
        document.getElementById('saleForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const formData = {
                menu: document.getElementById('menuSelect').value,
                quantity: parseInt(document.getElementById('quantity').value),
                price: parseFloat(document.getElementById('price').value),
                seller: document.getElementById('sellerSelect').value,
                total: parseInt(document.getElementById('quantity').value) * parseFloat(document.getElementById('price').value),
                date: document.getElementById('saleDate').value,
                time: new Date().toLocaleTimeString('lo-LA')
            };
            
            try {
                const result = await sendToGoogleSheets('addSale', formData);
                if (result.success) {
                    showAlert('ບັນທຶກການຂາຍສຳເລັດ!', 'success');
                    document.getElementById('saleForm').reset();
                } else {
                    showAlert('ເກີດຂໍ້ຜິດພາດ: ' + result.message, 'error');
                }
            } catch (error) {
                showAlert('ເກີດຂໍ້ຜິດພາດໃນການເຊື່ອມຕໍ່', 'error');
            }
        });

        // Event Listener สำหรับฟอร์มรายจ่าย
        document.getElementById('expenseForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const formData = {
                item: document.getElementById('expenseItem').value,
                amount: parseFloat(document.getElementById('expenseAmount').value),
                payer: document.getElementById('expensePayer').value,
                note: document.getElementById('expenseNote').value,
                date: document.getElementById('expenseDate').value,
                time: new Date().toLocaleTimeString('lo-LA')
            };
            
            try {
                const result = await sendToGoogleSheets('addExpense', formData);
                if (result.success) {
                    showAlert('ບັນທຶກລາຍຈ່າຍສຳເລັດ!', 'success');
                    document.getElementById('expenseForm').reset();
                } else {
                    showAlert('ເກີດຂໍ້ຜິດພາດ: ' + result.message, 'error');
                }
            } catch (error) {
                showAlert('ເກີດຂໍ້ຜິດພາດໃນການເຊື່ອມຕໍ່', 'error');
            }
        });

        // Event Listener สำหรับฟอร์มเมนู
        document.getElementById('menuForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const formData = {
                name: document.getElementById('menuName').value,
                price: parseFloat(document.getElementById('menuPrice').value)
            };
            
            try {
                const result = await sendToGoogleSheets('addMenu', formData);
                if (result.success) {
                    showAlert('ເພີ່ມເມນູສຳເລັດ!', 'success');
                    document.getElementById('menuForm').reset();
                    loadMenuList(); // รีโหลดรายการเมนู
                } else {
                    showAlert('ເກີດຂໍ້ຜິດພາດ: ' + result.message, 'error');
                }
            } catch (error) {
                showAlert('ເກີດຂໍ້ຜິດພາດໃນການເຊື່ອມຕໍ່', 'error');
            }
        });

        // เติมราคาอัตโนมัติเมื่อเลือกเมนู
        document.getElementById('menuSelect').addEventListener('change', function() {
            const selectedOption = this.options[this.selectedIndex];
            if (selectedOption.dataset.price) {
                document.getElementById('price').value = selectedOption.dataset.price;
            }
        });

        // Event listener สำหรับการเปลี่ยนแปลงวันที่
        document.getElementById('startDate').addEventListener('change', loadDashboard);
        document.getElementById('endDate').addEventListener('change', loadDashboard);

        // โหลดเมนูตอนเริ่มต้น
        window.addEventListener('load', function() {
            // ตั้งค่าวันที่เริ่มต้นเป็นวันนี้
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('saleDate').value = today;
            document.getElementById('expenseDate').value = today;
            document.getElementById('startDate').value = today;
            document.getElementById('endDate').value = today;
            
            loadMenuList();
        });
    </script>
</body>
</html>
