<!doctype html>
<html lang="vi">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>MEME THCS KHÁNH LỢI — Admin Tools</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#0b1220; --card:#0f172a; --panel:#111827; --muted:#9aa7b6;
  --accent1:#7c3aed; --accent2:#06b6d4; --glow:#0ff;
}
*{box-sizing:border-box;font-family:'Poppins',sans-serif}
body{margin:0;background:linear-gradient(180deg,#030417,var(--bg));color:#e6eef8;min-height:100vh;position:relative;overflow-x:hidden;}

/* neon border */
@keyframes rainbowBorder{0%{border-color:#ef4444}14%{border-color:#f97316}28%{border-color:#f59e0b}42%{border-color:#10b981}57%{border-color:#06b6d4}71%{border-color:#6366f1}85%{border-color:#a78bfa}100%{border-color:#ef4444}}
body::before{content:"";position:fixed;inset:0;border:3px solid;animation:rainbowBorder 6s linear infinite;pointer-events:none;z-index:10;opacity:0.08}

/* heading neon */
@keyframes rainbowText{0%{color:#7c3aed}25%{color:#06b6d4}50%{color:#34d399}75%{color:#f59e0b}100%{color:#f472b6}}
.neon-header{
  position:fixed;top:8px;left:0;width:100%;padding:10px 0;text-align:center;font-size:20px;font-weight:700;z-index:50;
  animation:rainbowText 4s linear infinite;text-shadow:0 0 8px rgba(124,58,237,0.2),0 0 20px rgba(6,182,212,0.12);
}

/* admin + left */
.admin-btn{
  position:fixed;top:60px;left:18px;z-index:60;
  width:56px;height:56px;border-radius:14px;background:linear-gradient(135deg,var(--accent1),var(--accent2));
  display:flex;align-items:center;justify-content:center;color:#fff;font-size:30px;font-weight:800;cursor:pointer;
  box-shadow:0 8px 30px rgba(124,58,237,0.18);
  transition:transform .12s;
}
.admin-btn:active{transform:scale(.97)}

/* hamburger right */
.hamburger{position:fixed;top:60px;right:18px;z-index:60;width:56px;height:56px;border-radius:14px;background:linear-gradient(135deg,var(--accent2),#8b5cf6);
display:flex;flex-direction:column;align-items:center;justify-content:center;gap:5px;cursor:pointer;box-shadow:0 8px 30px rgba(99,102,241,0.12)}
.hamburger span{display:block;width:28px;height:3px;background:#fff;border-radius:3px}

/* side menu */
.side-menu{position:fixed;top:0;right:-100%;width:320px;height:100%;background:linear-gradient(180deg,#071026,#0e1b2a);padding:22px;transition:right .32s cubic-bezier(.2,.9,.2,1);z-index:55;box-shadow:-12px 0 40px rgba(2,6,23,.6)}
.side-menu.open{right:0}
.side-menu .logo{font-weight:800;margin-bottom:12px;font-size:18px;letter-spacing:0.6px}
.side-menu a{display:flex;justify-content:space-between;align-items:center;padding:12px;border-radius:10px;color:#e6eef8;text-decoration:none;margin-bottom:6px;background:linear-gradient(90deg,transparent,transparent);font-weight:600}
.side-menu a:hover{background:rgba(255,255,255,0.03);box-shadow:0 6px 18px rgba(12,18,26,0.6)}
.side-menu .time{margin-top:auto;padding-top:10px;border-top:1px dashed rgba(255,255,255,0.03);color:var(--muted);font-size:13px;}

/* container */
.container{padding:120px 20px 80px;max-width:1100px;margin:0 auto}

/* cards */
.card{background:linear-gradient(180deg,#071122,#0b1730);padding:20px;border-radius:14px;margin-bottom:18px;box-shadow:0 12px 40px rgba(2,6,23,0.6)}
h1,h2{margin:0 0 8px 0}
.hidden{display:none!important}

/* admin tools UI */
.admin-tools{display:flex;flex-direction:column;gap:14px}
.tab-pills{display:flex;gap:8px}
.pill{padding:10px 14px;border-radius:999px;background:transparent;border:1px solid rgba(255,255,255,0.04);cursor:pointer;font-weight:700}
.pill.active{background:linear-gradient(90deg,var(--accent1),var(--accent2));box-shadow:0 10px 30px rgba(99,102,241,0.12);color:#fff}

/* forms */
.input, textarea, select{width:100%;padding:12px;border-radius:10px;border:none;background:#061226;color:#e6eef8;margin-top:8px;resize:vertical}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.form-actions{display:flex;gap:10px;margin-top:10px;align-items:center}

/* member list */
.member{display:flex;gap:12px;align-items:center;padding:10px;border-radius:10px;background:linear-gradient(180deg,#051222,#082033)}
.member img{width:56px;height:56px;border-radius:8px;object-fit:cover;border:2px solid rgba(255,255,255,0.03)}
.member .meta{font-weight:700}

/* drama post styles */
.post{padding:12px;border-radius:10px;background:linear-gradient(180deg,#061226,#0a2233);margin-bottom:12px}
.post .meta{display:flex;justify-content:space-between;align-items:center;color:var(--muted);font-size:13px;margin-bottom:8px}
.post img, .post video{max-width:100%;border-radius:8px;margin-top:8px}

/* preview area */
.preview{border:1px dashed rgba(255,255,255,0.04);padding:10px;border-radius:10px;margin-top:8px}

/* telegram ticker */
.telegram-ticker{position:fixed;bottom:0;left:0;width:100%;padding:8px 0;background:linear-gradient(90deg,rgba(0,0,0,0.2),transparent);z-index:60;overflow:hidden}
.ticker-inner{display:inline-block;white-space:nowrap;animation:scroll 18s linear infinite;font-weight:700;font-size:15px}
@keyframes scroll{0%{transform:translateX(100%)}100%{transform:translateX(-100%)}}

/* responsive */
@media (max-width:760px){.form-row{grid-template-columns:1fr}.side-menu{width:90%}}

/* Modern modal */
.modal-overlay {
  background: rgba(0,0,0,0.6);
  animation: fadeIn 0.25s ease;
}
.modal-card {
  border-radius: 20px;
  box-shadow: 0 20px 60px rgba(0,0,0,0.5);
  transform: scale(0.85) translateY(20px);
  opacity: 0;
  animation: modalIn 0.3s ease forwards;
}
#modalClose {
  background: rgba(255,255,255,0.08);
  border-radius: 50%;
  width: 36px; height: 36px;
  display:flex;align-items:center;justify-content:center;
  transition: background 0.2s;
}
#modalClose:hover { background: rgba(255,255,255,0.18); }
@keyframes modalIn {
  to { transform: scale(1) translateY(0); opacity: 1; }
}
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}
</style>
</head>
<body>
<div class="neon-header">✨ MEME THCS KHÁNH LỢI — MEME BY PH TRỌNG ✨</div>

<div class="admin-btn" id="adminBtn" title="Admin tools">+</div>
<div class="hamburger" id="hamburgerBtn" title="Mở menu"><span></span><span></span><span></span></div>

<nav class="side-menu" id="sideMenu" aria-hidden="true">
  <div class="logo">MENU — MEME</div>
  <a href="#" data-tab="home">🏠 Home <span style="opacity:.6"> </span></a>
  <a href="#" data-tab="checkmeme">✅ Check Meme</a>
  <a href="#" data-tab="comments">💬 Bình luận</a>
  <a href="#" data-tab="drama">🔥 Drama</a>
  <a href="#" data-tab="admin">👑 Thông tin Admin</a>
  <a href="#" data-tab="support">🆘 Hỗ trợ</a>
  <div class="time" id="menuTime">--:--:-- — --/--/----</div>
</nav>

<div class="container">
  <section id="home" class="card">
    <h1>CHÀO MỪNG ĐẾN VỚI VỰA MEME THCS KHÁNH LỢI</h1>
    <p>Đây là nơi lưu trữ meme, drama, anti_phốt của trường. Dùng menu (3 gạch) để chuyển trang — bấm + để vào Admin Tools.</p>
  </section>

  <section id="checkmeme" class="card hidden">
    <h2>CHECK MEME — DANH SÁCH THÀNH VIÊN</h2>
    <input id="search" class="input" placeholder="Tìm theo tên...">
    <div id="names" style="margin-top:12px"></div>
  </section>

  <section id="comments" class="card hidden">
    <h2>BÌNH LUẬN</h2>
    <input id="commentInput" class="input" placeholder="Viết bình luận và Enter để đăng...">
    <div id="commentList" style="margin-top:12px"></div>
  </section>

  <section id="drama" class="card hidden">
    <h2>🔥 DRAMA</h2>
    <div id="dramaList" style="margin-top:12px"></div>
  </section>

  <section id="admin" class="card hidden">
    <h2>Thông tin Admin</h2>
    <div style="text-align:center">
      <img src="https://i.postimg.cc/fykXBJSg/IMG-20250705-204005-875.jpg" style="width:140px;height:140px;border-radius:50%;object-fit:cover;border:3px solid rgba(255,255,255,0.05);box-shadow:0 0 20px rgba(124,58,237,0.4)">
      <h3 style="margin:12px 0 4px 0">Ph Trọng</h3>
      <p style="color:var(--muted)">Quản trị viên MEME THCS Khánh Lợi</p>
      <div style="margin-top:14px">
        <a class="btn" href="mailto:phtrongfreefire@gmail.com">📧 Email: phtrongfreefire@gmail.com</a>
      </div>
    </div>
  </section>

  <section id="support" class="card hidden">
    <h2>HỖ TRỢ — LIÊN HỆ ADMIN</h2>
    <p>Nếu cần hỗ trợ, báo lỗi, hoặc yêu cầu xoá bài phốt, liên hệ admin qua các kênh sau:</p>
    <div class="contact-buttons small">
      <a class="btn" href="https://www.facebook.com/share/16kQydRwS9/" target="_blank">📘 Facebook</a>
      <a class="btn" href="https://t.me/@VTrongcheat" target="_blank">💬 Telegram</a>
      <a class="btn" href="mailto:phtrongfreefire@gmail.com">📧 Gmail</a>
      <a class="btn" href="tel:0395725267">📞 Gọi</a>
    </div>
  </section>

  <section id="admintools" class="card hidden">
    <h2>👑 Admin Tools</h2>
    <div class="admin-tools">
      <div class="tab-pills" role="tablist">
        <button class="pill active" data-tab="add">➕ Thêm thành viên</button>
        <button class="pill" data-tab="post">📝 Đăng Anti_phốt</button>
      </div>

      <div id="tab-add" class="tab-panel">
        <h3>Thêm thành viên</h3>
        <form id="addForm">
          <div class="form-row">
            <input id="name" class="input" placeholder="Tên thành viên" required>
            <input id="classSelect" class="input" placeholder="Lớp" required>
          </div>
          <div class="form-row">
            <input id="roleSelect" class="input" placeholder="Chức vụ" required>
            <input id="avatarInput" class="input" placeholder="Link ảnh đại diện (URL) hoặc bỏ trống">
          </div>
          <textarea id="bioInput" class="input" rows="3" placeholder="Tiểu sử / bio"></textarea>
          <div class="form-actions">
            <button class="btn" type="submit">Thêm thành viên</button>
            <button type="button" id="clearMembers" style="background:#ef4444;padding:10px;border-radius:10px;border:none;color:#fff;cursor:pointer">Xóa tất cả</button>
          </div>
        </form>
        <hr style="border:none;border-top:1px dashed rgba(255,255,255,0.03);margin:12px 0">
        <div id="memberList"></div>
      </div>

      <div id="tab-post" class="tab-panel hidden">
        <h3>Đăng Anti_phốt</h3>
        <form id="antiphotForm">
          <input id="postTitle" class="input" placeholder="Tiêu đề" required>
          <textarea id="postContent" class="input" rows="5" placeholder="Nội dung (tôn trọng quy định)"></textarea>

          <div style="margin-top:10px">
            <label style="font-weight:700">Thêm media (ảnh / video):</label>
            <div style="display:flex;gap:8px;margin-top:8px">
              <input id="mediaUrl" class="input" placeholder="Dán link ảnh hoặc video (mp4, webm, jpg, png)" style="flex:1">
              <input id="mediaFile" type="file" accept="image/*,video/*" style="flex:0 0 180px">
            </div>
            <div id="mediaPreview" class="preview hidden"></div>
          </div>

          <div class="form-actions">
            <button class="btn" type="submit">Đăng bài</button>
            <button type="button" id="previewBtn" style="background:#111827;padding:10px;border-radius:10px;border:none;color:#fff;cursor:pointer">Xem trước</button>
          </div>
        </form>
      </div>
    </div>
  </section>

</div>

<div class="telegram-ticker" aria-hidden="true">
  <div class="ticker-inner">💬 @VTrongcheat — Liên hệ nhanh với admin qua Telegram • 💬 @VTrongcheat •</div>
</div>

<!-- modal profile -->
<div id="modalOverlay" class="modal-overlay hidden" style="position:fixed;inset:0;display:flex;align-items:center;justify-content:center;z-index:120">
  <div class="modal-card card" style="max-width:560px;position:relative">
    <div id="modalClose" style="position:absolute;right:14px;top:12px;background:rgba(255,255,255,0.03);padding:8px;border-radius:8px;cursor:pointer">✕</div>
    <div style="text-align:center">
      <img id="modalAvatar" src="" style="width:140px;height:140px;border-radius:12px;object-fit:cover;border:3px solid rgba(255,255,255,0.03)">
      <h2 id="modalName" style="margin-top:12px"></h2>
      <div id="modalMeta" style="color:var(--muted);margin-top:6px"></div>
      <p id="modalBio" style="margin-top:12px"></p>
    </div>
  </div>
</div>

<script>
/* --- Utilities --- */
function qs(sel){return document.querySelector(sel)}
function qsa(sel){return Array.from(document.querySelectorAll(sel))}

/* --- Navigation & menu time --- */
function showSection(id){
  document.querySelectorAll('section').forEach(s=>s.classList.add('hidden'));
  const el = document.getElementById(id);
  if(el) el.classList.remove('hidden');
  document.getElementById('sideMenu').classList.remove('open');
  window.scrollTo({top:0,behavior:'smooth'});
}
qsa('#sideMenu a').forEach(a=>a.addEventListener('click', function(e){e.preventDefault(); showSection(this.dataset.tab)}));
qs('#hamburgerBtn').addEventListener('click', ()=> qs('#sideMenu').classList.toggle('open'));

/* menu time */
function updateMenuTime(){
  const el = qs('#menuTime');
  const d = new Date();
  const hh = String(d.getHours()).padStart(2,'0');
  const mm = String(d.getMinutes()).padStart(2,'0');
  const ss = String(d.getSeconds()).padStart(2,'0');
  const dd = String(d.getDate()).padStart(2,'0');
  const mo = String(d.getMonth()+1).padStart(2,'0');
  const yy = d.getFullYear();
  el.textContent = `${hh}:${mm}:${ss} — ${dd}/${mo}/${yy}`;
}
setInterval(updateMenuTime, 1000);
updateMenuTime();

/* --- Data stores (localStorage) --- */
let students = JSON.parse(localStorage.getItem('students') || '[]');
if(!Array.isArray(students)) students = [];
if(students.length === 0){
  students.push({id:Date.now(),name:'LE THI VAN ANH',class:'8B',role:'Lớp trưởng',avatar:'https://i.postimg.cc/3xNmNZGP/IMG20250810202103.jpg',bio:'Thích làm chó.'});
  localStorage.setItem('students', JSON.stringify(students));
}
function saveStudents(){ localStorage.setItem('students', JSON.stringify(students)) }

let dramaPosts = JSON.parse(localStorage.getItem('dramaPosts') || '[]');
if(!Array.isArray(dramaPosts)) dramaPosts = [];
function saveDrama(){ localStorage.setItem('dramaPosts', JSON.stringify(dramaPosts)) }

let comments = JSON.parse(localStorage.getItem('comments') || '[]');
if(!Array.isArray(comments)) comments = [];
function saveComments(){ localStorage.setItem('comments', JSON.stringify(comments)) }

/* --- Render members list --- */
function renderList(filter){
  const namesEl = qs('#names');
  if(!namesEl) return;
  namesEl.innerHTML = '';
  (filter || students).forEach((s,i)=>{
    const div = document.createElement('div');
    div.className = 'member';
    div.innerHTML = `<img src="${s.avatar}" alt=""><div><div class="meta">${escapeHtml(s.name)}</div><div style="color:var(--muted)">${escapeHtml(s.class)} · ${escapeHtml(s.role)}</div></div>`;
    div.addEventListener('click', ()=> openModal(s));
    namesEl.appendChild(div);
  });
}
function renderManageList(){
  const list = qs('#memberList');
  if(!list) return;
  list.innerHTML = '';
  students.forEach((s,i)=>{
    const row = document.createElement('div');
    row.className = 'member';
    row.style.justifyContent='space-between';
    row.innerHTML = `<div style="display:flex;gap:12px;align-items:center"><img src="${s.avatar}" style="width:64px;height:64px;border-radius:8px"><div><div style="font-weight:800">${escapeHtml(s.name)}</div><div style="color:var(--muted)">${escapeHtml(s.class)} · ${escapeHtml(s.role)}</div></div></div>
    <div style="display:flex;flex-direction:column;gap:8px"><button class="btn" onclick="viewMember(${i})">Xem</button><button style="background:#ef4444;padding:8px;border-radius:8px;border:none;color:#fff" onclick="deleteMember(${i})">Xóa</button></div>`;
    list.appendChild(row);
  });
}
function viewMember(i){ openModal(students[i]) }
function deleteMember(i){
  if(!confirm('Xóa thành viên?')) return;
  students.splice(i,1); saveStudents(); renderList(); renderManageList();
}

/* add member form */
qs('#addForm').addEventListener('submit', function(e){
  e.preventDefault();
  const name = qs('#name').value.trim();
  const cls = qs('#classSelect').value.trim();
  const role = qs('#roleSelect').value.trim();
  const avatar = qs('#avatarInput').value.trim() || 'https://i.postimg.cc/3xNmNZGP/IMG20250810202103.jpg';
  const bio = qs('#bioInput').value.trim();
  if(!name || !cls || !role){ alert('Vui lòng nhập đầy đủ: tên, lớp, chức vụ'); return; }
  students.push({id:Date.now(),name, class:cls, role, avatar, bio});
  saveStudents(); renderList(); renderManageList(); this.reset(); alert('Đã thêm thành viên');
});
qs('#clearMembers').addEventListener('click', function(){ if(confirm('Xóa tất cả thành viên?')){ students=[]; saveStudents(); renderList(); renderManageList(); }});

/* modal */
function openModal(s){
  qs('#modalAvatar').src = s.avatar || '';
  qs('#modalName').textContent = s.name || '';
  qs('#modalMeta').textContent = (s.class || '') + ' · ' + (s.role || '');
  qs('#modalBio').textContent = s.bio || '';
  qs('#modalOverlay').classList.remove('hidden');
}
qs('#modalClose').addEventListener('click', ()=> qs('#modalOverlay').classList.add('hidden'));
qs('#modalOverlay').addEventListener('click', function(e){ if(e.target===this) this.classList.add('hidden') });

/* escape */
function escapeHtml(str){ if(!str) return ''; return String(str).replaceAll('&','&amp;').replaceAll('<','&lt;').replaceAll('>','&gt;').replaceAll('"','&quot;').replaceAll("'",'&#039;'); }

/* comments */
function renderComments(){
  const list = qs('#commentList'); if(!list) return; list.innerHTML='';
  const render = (parent=null, indent=0)=>{
    comments.filter(c=>c.parentId===parent).sort((a,b)=>b.time-a.time).forEach(c=>{
      const d = document.createElement('div'); d.className='post'; d.style.marginLeft=indent+'px';
      d.innerHTML = `<div style="color:var(--muted);font-size:13px">${escapeHtml(new Date(c.time).toLocaleString())}</div><div>${escapeHtml(c.content)}</div>
        <div style="margin-top:6px"><button onclick="replyComment(${c.id})" class="pill">Trả lời</button></div>`;
      list.appendChild(d);
      render(c.id, indent+16);
    });
  };
  render();
}
function addComment(content, parent=null){ comments.push({id:Date.now()+Math.floor(Math.random()*999), parentId:parent, content, time:Date.now()}); saveComments(); renderComments(); }
function replyComment(id){ const t=prompt('Nhập trả lời:'); if(t) addComment(t,id); }
qs('#commentInput').addEventListener('keypress', function(e){ if(e.key==='Enter' && this.value.trim()){ addComment(this.value.trim()); this.value=''; }});
renderComments();

/* drama rendering */
function renderDrama(){
  const el = qs('#dramaList'); if(!el) return; el.innerHTML='';
  if(dramaPosts.length===0){ el.innerHTML='<div style="color:var(--muted)">Chưa có drama nào</div>'; return; }
  dramaPosts.slice().reverse().forEach(p=>{
    const div = document.createElement('div'); div.className='post';
    const time = new Date(p.time).toLocaleString();
    div.innerHTML = `<div class="meta"><strong>${escapeHtml(p.title)}</strong><div style="color:var(--muted)">${time}</div></div>
      <div>${escapeHtml(p.content)}</div>`;
    if(p.media){
      // detect if video or image by prefix
      if(p.mediaType && p.mediaType.startsWith('video')){
        const v = document.createElement('video'); v.controls = true; v.src = p.media; v.className=''; div.appendChild(v);
      } else {
        const img = document.createElement('img'); img.src = p.media; div.appendChild(img);
      }
    }
    el.appendChild(div);
  });
}

/* media handling for post */
let currentMedia = null;
let currentMediaType = null;
const mediaFile = qs('#mediaFile');
const mediaUrl = qs('#mediaUrl');
const mediaPreview = qs('#mediaPreview');

function showMediaPreview(src, type){
  mediaPreview.classList.remove('hidden'); mediaPreview.innerHTML = '';
  currentMedia = src; currentMediaType = type;
  if(type 
