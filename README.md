<html lang="am">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Oyaya Betting - Sub-Agent Registration</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background-color: #0f172a;
      color: #f8fafc;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
      padding: 20px 10px;
    }

    .container {
      width: 100%;
      max-width: 500px;
      background-color: #1e293b;
      border-radius: 12px;
      padding: 24px;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.5);
      border: 1px solid #334155;
      margin-top: 10px;
    }

    header {
      text-align: center;
      margin-bottom: 20px;
    }

    .logo {
      font-size: 28px;
      font-weight: 800;
      color: #f59e0b;
      text-transform: uppercase;
      letter-spacing: 2px;
      text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
    }

    .subtitle {
      font-size: 14px;
      color: #94a3b8;
      margin-top: 4px;
    }

    .form-group {
      margin-bottom: 16px;
    }

    label {
      display: block;
      font-size: 14px;
      margin-bottom: 6px;
      color: #cbd5e1;
    }

    input, select {
      width: 100%;
      padding: 12px;
      border-radius: 8px;
      border: 1px solid #475569;
      background-color: #0f172a;
      color: #ffffff;
      font-size: 15px;
      outline: none;
      transition: border-color 0.2s;
    }

    input:focus, select:focus {
      border-color: #f59e0b;
    }

    .btn {
      width: 100%;
      padding: 12px;
      background-color: #f59e0b;
      color: #0f172a;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      transition: background-color 0.2s;
      margin-top: 8px;
    }

    .btn:hover {
      background-color: #d97706;
    }

    .hidden {
      display: none !important;
    }

    .message-box {
      text-align: center;
      padding: 20px;
      background-color: #334155;
      border-radius: 8px;
      margin-top: 15px;
      font-size: 16px;
      color: #f1f5f9;
    }

    .admin-trigger {
      display: inline-block;
      margin-top: 15px;
      color: #64748b;
      font-size: 13px;
      cursor: pointer;
      text-decoration: none;
      user-select: none;
    }

    .admin-trigger:hover {
      color: #94a3b8;
    }

    /* Modal / Admin Panel */
    .modal-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.85);
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 1000;
      padding: 15px;
    }

    .modal-content {
      background: #1e293b;
      padding: 24px;
      border-radius: 12px;
      width: 100%;
      max-width: 400px;
      border: 1px solid #475569;
      text-align: center;
    }

    .dashboard-container {
      width: 100%;
      max-width: 800px;
      background: #1e293b;
      border-radius: 12px;
      padding: 20px;
      margin-top: 10px;
      border: 1px solid #334155;
    }

    .card {
      background: #0f172a;
      padding: 15px;
      border-radius: 8px;
      margin-bottom: 15px;
      border: 1px solid #334155;
    }

    .card-title {
      font-size: 14px;
      color: #94a3b8;
      margin-bottom: 5px;
    }

    .card-value {
      font-size: 22px;
      font-weight: bold;
      color: #10b981;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 10px;
      font-size: 13px;
    }

    th, td {
      padding: 10px;
      text-align: left;
      border-bottom: 1px solid #334155;
    }

    th {
      background-color: #0f172a;
      color: #f59e0b;
    }

    .action-btn {
      padding: 4px 8px;
      border: none;
      border-radius: 4px;
      font-size: 12px;
      cursor: pointer;
      margin-right: 4px;
    }

    .btn-approve {
      background-color: #10b981;
      color: #fff;
    }

    .btn-reject {
      background-color: #ef4444;
      color: #fff;
    }

    .badge {
      padding: 2px 6px;
      border-radius: 4px;
      font-size: 11px;
    }

    .badge-pending { background: #f59e0b; color: #000; }
    .badge-approved { background: #10b981; color: #fff; }
    .badge-rejected { background: #ef4444; color: #fff; }
  </style>
</head>
<body>

  <!-- Main Container -->
  <div id="mainContainer" class="container">
    <header>
      <div class="logo">Oyaya Betting</div>
      <div class="subtitle">የንኡስ ወኪሎች (Sub-Agent) መመዝገቢያ ፖርታል</div>
    </header>

    <!-- Step 1: Registration Form -->
    <div id="step1">
      <div class="form-group">
        <label>ስም</label>
        <input type="text" id="firstName" placeholder="ስምዎን ያስገቡ">
      </div>
      <div class="form-group">
        <label>የአባት ስም</label>
        <input type="text" id="fatherName" placeholder="የአባት ስምዎን ያስገቡ">
      </div>
      <div class="form-group">
        <label>የስልክ ቁጥር</label>
        <input type="tel" id="phone" placeholder="09........">
      </div>
      <div class="form-group">
        <label>የቴሌግራም አድራሻ (Username)</label>
        <input type="text" id="telegram" placeholder="@username">
      </div>
      <div class="form-group">
        <label>አድራሻ</label>
        <input type="text" id="address" placeholder="ከተማ / ክፍለ ከተማ / ወረዳ">
      </div>
      <button class="btn" onclick="submitStep1()">ቀጥል</button>

      <!-- Secret trigger 1234 right at the bottom of Step 1 form -->
      <div style="text-align: center;">
        <span class="admin-trigger" onclick="openPasswordModal()">1234</span>
      </div>
    </div>

    <!-- Step 2: ID Input -->
    <div id="step2" class="hidden">
      <div class="form-group">
        <label>እባክዎን የመታወቂያ ቁጥርዎን ያስገቡ (ID Number)</label>
        <input type="text" id="idNumber" placeholder="የመታወቂያ ቁጥር">
      </div>
      <button class="btn" onclick="submitStep2()">OK</button>
    </div>

    <!-- Step 3: Confirmation -->
    <div id="step3" class="hidden">
      <div class="message-box">
        ⏳ እባክዎን አድሚናችሁ እስኪቀበላችሁ ተጠበቁ!
      </div>
    </div>
  </div>

  <!-- Password Modal -->
  <div id="passwordModal" class="modal-overlay hidden">
    <div class="modal-content">
      <h3 style="margin-bottom: 15px; color: #f59e0b;">የአድሚን መግቢያ</h3>
      <div class="form-group">
        <input type="password" id="adminPassword" placeholder="የይለፍ ቃል ያስገቡ (8660)">
      </div>
      <button class="btn" onclick="verifyPassword()">ግባ</button>
      <button class="btn" style="background-color: #64748b; color: #fff; margin-top: 8px;" onclick="closePasswordModal()">ሰርዝ</button>
    </div>
  </div>

  <!-- Admin Dashboard -->
  <div id="adminDashboard" class="dashboard-container hidden">
    <header style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px;">
      <div>
        <div class="logo" style="text-align: left; font-size: 22px;">Oyaya Betting</div>
        <div class="subtitle" style="text-align: left;">Agent Workspace Dashboard</div>
      </div>
      <button class="action-btn btn-reject" style="padding: 8px 12px;" onclick="logoutAdmin()">ውጣ</button>
    </header>

    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px;">
      <div class="card">
        <div class="card-title">የወኪል ካፒታል (Balance)</div>
        <div class="card-value" id="agentBalance">50,000.00 ETB</div>
      </div>
      <div class="card">
        <div class="card-title">ጠቅላላ ንኡስ ወኪሎች</div>
        <div class="card-value" id="totalSubAgents">0</div>
      </div>
    </div>

<!-- Agent Operations -->
    <div class="card">
      <h4 style="margin-bottom: 10px; color: #cbd5e1;">የቀጥታ ግብይት (Deposit / Withdraw)</h4>
      <div style="display: flex; gap: 10px; flex-wrap: wrap;">
        <input type="text" id="targetUser" placeholder="የተጠቃሚ ID / ስልክ" style="flex: 1; min-width: 150px;">
        <input type="number" id="transAmount" placeholder="መጠን (ETB)" style="flex: 1; min-width: 120px;">
        <button class="action-btn btn-approve" style="padding: 10px 15px;" onclick="handleTransaction('Deposit')">Deposit</button>
        <button class="action-btn btn-reject" style="padding: 10px 15px;" onclick="handleTransaction('Withdraw')">Withdraw</button>
      </div>
    </div>

    <!-- Registered Applicants Table -->
    <div class="card" style="overflow-x: auto;">
      <h4 style="margin-bottom: 10px; color: #cbd5e1;">የተመዘገቡ አዳዲስ ንኡስ ወኪሎች ዝርዝር</h4>
      <table>
        <thead>
          <tr>
            <th>ስም</th>
            <th>ስልክ</th>
            <th>ቴሌግራም</th>
            <th>አድራሻ</th>
            <th>ID</th>
            <th>ሁኔታ</th>
            <th>እርምጃ</th>
          </tr>
        </thead>
        <tbody id="applicantTableBody">
          <!-- Dynamic Content -->
        </tbody>
      </table>
    </div>
  </div>

  <script>
    let tempUserData = {};
    let applicants = [];
    let currentBalance = 50000;

    function submitStep1() {
      const firstName = document.getElementById('firstName').value.trim();
      const fatherName = document.getElementById('fatherName').value.trim();
      const phone = document.getElementById('phone').value.trim();
      const telegram = document.getElementById('telegram').value.trim();
      const address = document.getElementById('address').value.trim();

      if (!firstName  !fatherName  !phone) {
        alert('እባክዎን ዋና ዋና መረጃዎችን ይሙሉ!');
        return;
      }

      tempUserData = { firstName, fatherName, phone, telegram, address };
      document.getElementById('step1').classList.add('hidden');
      document.getElementById('step2').classList.remove('hidden');
    }

    function submitStep2() {
      const idNumber = document.getElementById('idNumber').value.trim();
      if (!idNumber) {
        alert('እባክዎን የመታወቂያ ቁጥር ያስገቡ!');
        return;
      }

      tempUserData.idNumber = idNumber;
      tempUserData.status = 'Pending';
      applicants.push({...tempUserData});

      document.getElementById('step2').classList.add('hidden');
      document.getElementById('step3').classList.remove('hidden');
      renderApplicants();
    }

    function openPasswordModal() {
      document.getElementById('passwordModal').classList.remove('hidden');
    }

    function closePasswordModal() {
      document.getElementById('passwordModal').classList.add('hidden');
      document.getElementById('adminPassword').value = '';
    }

    function verifyPassword() {
      const pwd = document.getElementById('adminPassword').value;
      if (pwd === '8660') {
        closePasswordModal();
        document.getElementById('mainContainer').classList.add('hidden');
        document.getElementById('adminDashboard').classList.remove('hidden');
        renderApplicants();
      } else {
        alert('የተሳሳተ የይለፍ ቃል!');
      }
    }

    function logoutAdmin() {
      document.getElementById('adminDashboard').classList.add('hidden');
      document.getElementById('mainContainer').classList.remove('hidden');
    }

    function renderApplicants() {
      const tbody = document.getElementById('applicantTableBody');
      tbody.innerHTML = '';

      document.getElementById('totalSubAgents').innerText = applicants.length;

      if (applicants.length === 0) {
        tbody.innerHTML = '<tr><td colspan="7" style="text-align:center; color:#64748b;">ምንም የተመዘገበ ሰው የለም</td></tr>';
        return;
      }

      applicants.forEach((app, index) => {
        const tr = document.createElement('tr');
        tr.innerHTML = `
          <td>${app.firstName} ${app.fatherName}</td>
          <td>${app.phone}</td>
          <td>${app.telegram  '-'}</td>
          <td>${app.address  '-'}</td>
          <td>${app.idNumber}</td>
          <td><span class="badge badge-${app.status.toLowerCase()}">${app.status}</span></td>
          <td>
            ${app.status === 'Pending' ? `
              <button class="action-btn btn-approve" onclick="updateStatus(${index}, 'Approved')">አፕሩቭ</button>
              <button class="action-btn btn-reject" onclick="updateStatus(${index}, 'Rejected')">ሰርዝ</button>
            ` : '-'}
          </td>
        `;
        tbody.appendChild(tr);
      });
    }

    function updateStatus(index, status) {
      applicants[index].status = status;
      renderApplicants();
    }

    function handleTransaction(type) {
      const user = document.getElementById('targetUser').value.trim();
      const amount = parseFloat(document.getElementById('transAmount').value);

      if (!user  isNaN(amount)  amount <= 0) {
        alert('እባክዎን ትክክለኛ መረጃ ያስገቡ!');
        return;
      }

      if (type === 'Deposit') {
        if (amount > currentBalance) {
          alert('በቂ የሂሳብ መጠን የለዎትም!');
          return;
        }
        currentBalance -= amount;
        alert(`${amount} ETB ለ ${user} ዲፖዚት ተደርጓል!`);
      } else {
        currentBalance += amount;
        alert(`${amount} ETB ከ ${user} ዊዝድሮው ተደርጓል!`);
      }

      document.getElementById('agentBalance').innerText = currentBalance.toFixed(2) + ' ETB';
      document.getElementById('targetUser').value = '';
      document.getElementById('transAmount').value = '';
    }
  </script>
</body>
</html>
