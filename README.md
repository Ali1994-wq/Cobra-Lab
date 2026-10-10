<!DOCTYPE html><html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#0b1220">
  <title>Cobra Lab | منصة الأمن السيبراني الدفاعي</title>
  <style>
    :root {
      color-scheme: dark;
      --bg: #0b1220;
      --panel: #131e30;
      --border: #26364d;
      --text: #edf4ff;
      --muted: #9eafc5;
      --accent: #38bdf8;
      --green: #34d399;
      --orange: #fbbf24;
      --red: #fb7185;
    }* { box-sizing: border-box; }

body {
  margin: 0;
  background: var(--bg);
  color: var(--text);
  font-family: system-ui, sans-serif;
  line-height: 1.7;
}

header {
  padding: 22px;
  border-bottom: 1px solid var(--border);
  background: #101a2b;
}

.container {
  max-width: 1150px;
  margin: auto;
  padding: 18px;
}

.brand {
  display: flex;
  align-items: center;
  gap: 12px;
}

.logo {
  width: 48px;
  height: 48px;
  display: grid;
  place-items: center;
  border-radius: 14px;
  background: #163653;
  font-size: 27px;
}

h1, h2, p { margin-top: 0; }
h1 { font-size: 23px; margin-bottom: 2px; }
h2 { font-size: 18px; }
.muted { color: var(--muted); font-size: 14px; }

.badge {
  display: inline-block;
  padding: 3px 10px;
  border-radius: 20px;
  color: var(--green);
  background: #10372f;
  font-size: 12px;
}

.notice {
  padding: 14px;
  margin: 18px 0;
  border: 1px solid #665222;
  border-radius: 12px;
  background: #292415;
  color: #fde68a;
  font-size: 14px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 14px;
}

.panel {
  min-width: 0;
  padding: 18px;
  margin-bottom: 16px;
  background: var(--panel);
  border: 1px solid var(--border);
  border-radius: 15px;
}

.metric {
  font-size: 27px;
  font-weight: 750;
  margin: 8px 0;
}

.icon { font-size: 23px; }
.section { margin-top: 26px; }

.actions {
  display: flex;
  flex-wrap: wrap;
  gap: 9px;
  margin: 12px 0;
}

button, input, select, textarea {
  font: inherit;
  border-radius: 9px;
}

button {
  padding: 10px 14px;
  border: 1px solid #31516f;
  background: #173754;
  color: white;
  cursor: pointer;
}

button:hover { background: #20496c; }
button.primary {
  background: #0369a1;
  border-color: #0284c7;
}

input, select, textarea {
  width: 100%;
  padding: 10px;
  background: #0b1525;
  border: 1px solid var(--border);
  color: var(--text);
  margin: 5px 0 12px;
}

label { font-size: 14px; color: var(--muted); }
.form-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 12px;
}

.table-wrap { overflow-x: auto; }

table {
  width: 100%;
  border-collapse: collapse;
  min-width: 520px;
  font-size: 14px;
}

th, td {
  text-align: right;
  padding: 11px;
  border-bottom: 1px solid var(--border);
}

th { color: var(--muted); font-weight: 600; }
.empty { color: var(--muted); text-align: center; padding: 22px; }
.danger { color: var(--red); }
footer {
  padding: 24px;
  text-align: center;
  color: var(--muted);
  font-size: 12px;
}

@media (max-width: 760px) {
  .grid { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .form-grid { grid-template-columns: 1fr; }
  header { padding: 16px; }
  .container { padding: 12px; }
}

@media (max-width: 360px) {
  .grid { grid-template-columns: 1fr; }
}

  </style>
</head>
<body>
<header>
  <div class="brand">
    <div class="logo" aria-hidden="true">🐍</div>
    <div>
      <h1>Cobra Lab</h1>
      <div class="muted">منصة الأمن السيبراني الدفاعي</div>
    </div>
  </div>
</header><main class="container">
  <div class="actions">
    <span class="badge">واجهة أولية محلية</span>
  </div>  <div class="notice">
    تنبيه أمني: هذه الواجهة تسجل البيانات داخل متصفحك فقط. لا يوجد حتى الآن
    محرك فحص فعلي أو اتصال بخادم أو تحكم بالأجهزة. لا تُدخل كلمات مرور أو أسرارًا.
  </div>  <section class="grid" aria-label="ملخص النظام">
    <article class="panel">
      <div class="icon">▣</div>
      <div class="muted">الأجهزة المسجلة</div>
      <div class="metric" id="deviceCount">0</div>
      <span class="muted">سجل محلي</span>
    </article>
    <article class="panel">
      <div class="icon">⌕</div>
      <div class="muted">عمليات الفحص المسجلة</div>
      <div class="metric" id="scanCount">0</div>
      <span class="muted">ليست فحوصًا فعلية</span>
    </article>
    <article class="panel">
      <div class="icon">⚑</div>
      <div class="muted">التهديدات المسجلة</div>
      <div class="metric" id="threatCount">0</div>
      <span class="muted">إدخال يدوي</span>
    </article>
    <article class="panel">
      <div class="icon">◷</div>
      <div class="muted">سجل الأحداث</div>
      <div class="metric" id="eventCount">0</div>
      <span class="muted">محفوظ محليًا</span>
    </article>
  </section>  <section class="section panel">
    <h2>الأجهزة المُدارة</h2>
    <p class="muted">سجل الأجهزة التي تملكها أو لديك تصريح بإدارتها.</p>
    <form id="deviceForm">
      <div class="form-grid">
        <div>
          <label for="deviceName">اسم الجهاز</label>
          <input id="deviceName" maxlength="80" required placeholder="مثال: جهاز المكتب">
        </div>
        <div>
          <label for="deviceType">نوع الجهاز</label>
          <select id="deviceType">
            <option>Android</option>
            <option>Windows</option>
            <option>Linux</option>
            <option>Server</option>
            <option>Other</option>
          </select>
        </div>
      </div>
      <button class="primary" type="submit">إضافة إلى السجل</button>
    </form>
    <div class="table-wrap">
      <table>
        <thead><tr><th>الجهاز</th><th>النوع</th><th>الإجراء</th></tr></thead>
        <tbody id="deviceRows"></tbody>
      </table>
    </div>
  </section>  <section class="section panel">
    <h2>تحليل بصمة ملف</h2>
    <p class="muted">
      يحسب المتصفح بصمة SHA-256 للملف الذي تختاره. هذا لا يكشف وحده إن كان الملف ضارًا.
      لا يتم رفع الملف إلى أي خادم.
    </p>
    <label for="fileInput">اختر ملفًا</label>
    <input id="fileInput" type="file">
    <div class="actions">
      <button class="primary" id="hashButton" type="button">حساب البصمة</button>
    </div>
    <div id="hashResult" class="muted" aria-live="polite">لم يتم اختيار ملف.</div>
  </section>  <section class="section panel">
    <h2>مركز التهديدات</h2>
    <p class="muted">سجل الملاحظات والتهديدات التي جرى التحقق منها يدويًا.</p>
    <form id="threatForm">
      <label for="threatTitle">عنوان الملاحظة</label>
      <input id="threatTitle" maxlength="120" required placeholder="وصف مختصر">
      <label for="threatSeverity">مستوى الخطورة التقديري</label>
      <select id="threatSeverity">
        <option>منخفض</option>
        <option>متوسط</option>
        <option>مرتفع</option>
        <option>حرج</option>
      </select>
      <button class="primary" type="submit">تسجيل الملاحظة</button>
    </form>
    <div class="table-wrap">
      <table>
        <thead><tr><th>الملاحظة</th><th>الخطورة</th><th>التاريخ</th><th>الإجراء</th></tr></thead>
        <tbody id="threatRows"></tbody>
      </table>
    </div>
  </section>  <section class="section panel">
    <h2>سجل العمليات</h2>
    <p class="muted">تسجيل محلي للأنشطة التي ينفذها المستخدم من هذه الواجهة.</p>
    <div class="actions">
      <button id="exportButton" type="button">تصدير السجل CSV</button>
      <button id="clearButton" type="button">مسح بيانات المتصفح</button>
    </div>
    <div class="table-wrap">
      <table>
        <thead><tr><th>الوقت</th><th>الحدث</th></tr></thead>
        <tbody id="eventRows"></tbody>
      </table>
    </div>
  </section>
</main><footer>
  Cobra Lab · نموذج أولي دفاعي · لا ينفذ فحص شبكة أو استجابة آلية للتهديدات
</footer><script>
"use strict";

const STORAGE_KEY = "cobra-lab-prototype-v1";
const initialState = { devices: [], threats: [], events: [], scans: 0 };

function loadState() {
  try {
    const saved = JSON.parse(localStorage.getItem(STORAGE_KEY));
    if (saved && Array.isArray(saved.devices) &&
        Array.isArray(saved.threats) && Array.isArray(saved.events)) {
      return {
        devices: saved.devices,
        threats: saved.threats,
        events: saved.events,
        scans: Number(saved.scans) || 0
      };
    }
  } catch (_) {}
  return structuredClone(initialState);
}

let state = loadState();

function saveState() {
  try {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
  } catch (_) {
    alert("تعذر الحفظ في المتصفح. قد تكون مساحة التخزين ممتلئة.");
  }
  render();
}

function logEvent(message) {
  state.events.unshift({ time: new Date().toLocaleString("ar"), message });
  state.events = state.events.slice(0, 200);
}

function cell(text) {
  const td = document.createElement("td");
  td.textContent = String(text);
  return td;
}

function actionButton(label, callback) {
  const button = document.createElement("button");
  button.type = "button";
  button.textContent = label;
  button.addEventListener("click", callback);
  return button;
}

function render() {
  document.getElementById("deviceCount").textContent = state.devices.length;
  document.getElementById("scanCount").textContent = state.scans;
  document.getElementById("threatCount").textContent = state.threats.length;
  document.getElementById("eventCount").textContent = state.events.length;

  const deviceRows = document.getElementById("deviceRows");
  deviceRows.replaceChildren();
  if (!state.devices.length) {
    const tr = document.createElement("tr");
    const td = cell("لا توجد أجهزة مسجلة.");
    td.colSpan = 3;
    td.className = "empty";
    tr.append(td);
    deviceRows.append(tr);
  }
  state.devices.forEach((device, index) => {
    const tr = document.createElement("tr");
    tr.append(cell(device.name), cell(device.type));
    const td = document.createElement("td");
    td.append(actionButton("حذف", () => {
      state.devices.splice(index, 1);
      logEvent("حذف جهاز من السجل");
      saveState();
    }));
    tr.append(td);
    deviceRows.append(tr);
  });

  const threatRows = document.getElementById("threatRows");
  threatRows.replaceChildren();
  if (!state.threats.length) {
    const tr = document.createElement("tr");
    const td = cell("لا توجد ملاحظات مسجلة.");
    td.colSpan = 4;
    td.className = "empty";
    tr.append(td);
    threatRows.append(tr);
  }
  state.threats.forEach((threat, index) => {
    const tr = document.createElement("tr");
    tr.append(cell(threat.title), cell(threat.severity), cell(threat.time));
    const td = document.createElement("td");
    td.append(actionButton("حذف", () => {
      state.threats.splice(index, 1);
      logEvent("حذف ملاحظة تهديد");
      saveState();
    }));
    tr.append(td);
    threatRows.append(tr);
  });

  const eventRows = document.getElementById("eventRows");
  eventRows.replaceChildren();
  if (!state.events.length) {
    const tr = document.createElement("tr");
    const td = cell("لا توجد أحداث حتى الآن.");
    td.colSpan = 2;
    td.className = "empty";
    tr.append(td);
    eventRows.append(tr);
  }
  state.events.slice(0, 50).forEach(event => {
    const tr = document.createElement("tr");
    tr.append(cell(event.time), cell(event.message));
    eventRows.append(tr);
  });
}

document.getElementById("deviceForm").addEventListener("submit", event => {
  event.preventDefault();
  const name = document.getElementById("deviceName").value.trim();
  const type = document.getElementById("deviceType").value;
  if (!name) return;
  state.devices.push({ name, type });
  logEvent("إضافة جهاز إلى السجل");
  event.target.reset();
  saveState();
});

document.getElementById("threatForm").addEventListener("submit", event => {
  event.preventDefault();
  const title = document.getElementById("threatTitle").value.trim();
  const severity = document.getElementById("threatSeverity").value;
  if (!title) return;
  state.threats.unshift({
    title,
    severity,
    time: new Date().toLocaleString("ar")
  });
  logEvent("تسجيل ملاحظة تهديد");
  event.target.reset();
  saveState();
});

document.getElementById("hashButton").addEventListener("click", async () => {
  const input = document.getElementById("fileInput");
  const result = document.getElementById("hashResult");
  if (!input.files || !input.files[0]) {
    result.textContent = "اختر ملفًا أولًا.";
    return;
  }
  if (!window.crypto || !crypto.subtle) {
    result.textContent = "حساب البصمة يتطلب سياقًا آمنًا يدعم Web Crypto.";
    return;
  }
  const file = input.files[0];
  result.textContent = "جارٍ حساب البصمة...";
  try {
    const digest = await crypto.subtle.digest("SHA-256", await file.arrayBuffer());
    const hash = Array.from(new Uint8Array(digest))
      .map(byte => byte.toString(16).padStart(2, "0")).join("");
    result.textContent = "الملف: " + file.name +
      " | الحجم: " + file.size + " بايت | SHA-256: " + hash;
    state.scans++;
    logEvent("حساب بصمة SHA-256 محليًا لملف");
    saveState();
  } catch (_) {
    result.textContent = "تعذر حساب البصمة لهذا الملف.";
  }
});

document.getElementById("exportButton").addEventListener("click", () => {
  const rows = [["الوقت", "الحدث"], ...state.events.map(e => [e.time, e.message])];
  const csv = "\uFEFF" + rows.map(row =>
    row.map(value => '"' + String(value).replace(/"/g, '""') + '"').join(",")
  ).join("\r\n");
  const blob = new Blob([csv], { type: "text/csv;charset=utf-8;" });
  const url = URL.createObjectURL(blob);
  const link = document.createElement("a");
  link.href = url;
  link.download = "cobra-lab-events.csv";
  link.click();
  URL.revokeObjectURL(url);
});

document.getElementById("clearButton").addEventListener("click", () => {
  if (!confirm("هل تريد حذف جميع بيانات Cobra Lab المحفوظة في هذا المتصفح؟")) return;
  state = structuredClone(initialState);
  saveState();
});

render();
</script></body>
</html>
