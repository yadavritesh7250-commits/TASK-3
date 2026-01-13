# TASK-3
Task 3 as a intern at apex planet in web development

````html

<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Intermediate HTML, CSS & JavaScript — Example (Improved)</title>
<style>
  :root{
    --brand:#0f7f78;
    --muted:#6b7b7a;
    --bg:#f4f6f7;
    --card:#ffffff;
    --accent:#0b5e5a;
    --danger:#d9534f;
    --success:#2a9d6f;
    --radius:12px;
    --gap:18px;
    --text:#133;
    font-family: "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
    font-size:16px;
  }

  /* Page base */
  *{box-sizing:border-box}
  html,body{height:100%}
  body{
    margin:0;
    background:linear-gradient(180deg, var(--bg), #eef2f2);
    color:var(--text);
    line-height:1.45;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
  }
  .container{
    max-width:1100px;
    margin:28px auto;
    padding:20px;
  }

  /* Header / Nav (Flexbox) */
  header.site-header{
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:12px;
    background:linear-gradient(90deg,var(--brand),var(--accent));
    color:white;
    padding:18px;
    border-radius:16px;
  }
  .brand{display:flex;align-items:center;gap:12px}
  .brand .logo{
    width:56px;height:56px;border-radius:10px;
    background:rgba(255,255,255,0.12);
    display:flex;align-items:center;justify-content:center;font-weight:700;
    font-size:20px;color:white;
  }
  nav.primary{
    display:flex;gap:12px;align-items:center;
  }
  nav.primary a{
    color:white;text-decoration:none;padding:8px 12px;border-radius:8px;font-weight:600;
  }
  nav.primary a:focus,
  nav.primary a:hover{background:rgba(255,255,255,0.08)}

  /* Make focus outlines visible for keyboard users */
  a:focus, button:focus, input:focus, textarea:focus { outline: 3px solid rgba(11,94,90,0.18); outline-offset:2px; }

  /* Main grid */
  .main-grid{
    display:grid;
    grid-template-columns: 2fr 1fr;
    gap:var(--gap);
    margin-top:20px;
  }

  .card{
    background:var(--card);
    border-radius:var(--radius);
    box-shadow: 0 6px 18px rgba(20,40,40,0.06);
    padding:18px;
  }

  /* Contact form (task 1 + 2) */
  form.contact-form{display:flex;flex-direction:column;gap:12px}
  form .row{display:flex;gap:12px;flex-wrap:wrap}
  form label{display:flex;flex-direction:column;font-weight:600;color:var(--muted);font-size:14px}
  input[type="text"], input[type="email"], textarea{
    padding:10px;border:1px solid #d6e0df;border-radius:8px;font-size:15px;
    margin-top:6px;resize:vertical;
    background:white;
  }
  .form-actions{display:flex;gap:12px;align-items:center;flex-wrap:wrap}
  button.btn{
    background:var(--brand);color:white;border:none;padding:10px 14px;border-radius:10px;cursor:pointer;font-weight:700;
  }
  button.btn.secondary{background:#eef6f5;color:var(--accent);border:1px solid #d2e7e6}
  .msg{font-size:14px}
  .msg.error{color:var(--danger)}
  .msg.success{color:var(--success)}

  /* To-do list (task 4) */
  #todoApp h3{margin:0 0 8px 0}
  .todo-controls{display:flex;gap:8px}
  .todo-controls input{flex:1;padding:8px;border-radius:8px;border:1px solid #d6e0df}
  ul.todo-list{list-style:none;padding:0;margin:0;display:flex;flex-direction:column;gap:8px}
  .todo-item{display:flex;align-items:center;justify-content:space-between;padding:10px;border-radius:8px;border:1px solid #eef2f2;background:linear-gradient(180deg,#ffffff,#fbfcfc)}
  .todo-item .left{display:flex;align-items:center;gap:10px}
  .todo-item button{background:transparent;border:1px solid transparent;color:var(--danger);cursor:pointer;padding:6px 8px;border-radius:8px}
  .todo-item button:hover{background:rgba(209,74,73,0.08)}

  /* Sidebar extras */
  .aside-note{color:var(--muted);font-size:14px}

  /* Responsive & mobile first */
  @media (max-width:900px){
    .main-grid{grid-template-columns:1fr}
    nav.primary{display:none}
    header.site-header{flex-direction:column;align-items:flex-start}
  }

  /* Footer */
  footer.site-footer{text-align:center;color:var(--muted);margin-top:18px;font-size:14px}
  /* small utilities */
  .muted{color:var(--muted)}
  .small{font-size:13px}
  .kbd{font-family:monospace;border-radius:4px;padding:2px 6px;background:#f5f7f6;border:1px solid #e6eeed;font-size:13px}
</style>
</head>
<body>
  <div class="container">
    <header class="site-header" role="banner">
      <div class="brand">
        <div class="logo" aria-hidden="true">AP</div>
        <div>
          <div style="font-weight:800;font-size:18px">ApexPlanet — Practice Lab</div>
          <div style="font-size:13px;color:rgba(255,255,255,0.9)">Intermediate HTML, CSS & JavaScript</div>
        </div>
      </div>

      <nav class="primary" role="navigation" aria-label="Main navigation">
        <a href="#contact">Contact</a>
        <a href="#todo">To-Do</a>
        <a href="#learn">Learn</a>
      </nav>
    </header>

    <main>
      <div class="main-grid" role="main">
        <!-- Left: main content -->
        <section class="card" aria-labelledby="aboutTitle">
          <h2 id="aboutTitle">About this page</h2>
          <p class="muted">This page demonstrates the items on your task slide: a contact form with JavaScript validation, a responsive layout using Flexbox & Grid, a dynamic to-do list using DOM manipulation, and an example of fetching data from a public API (joke API).</p>

          <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-top:12px">
            <div style="grid-column:1/-1">
              <img src="/mnt/data/be267ba0-cd3f-45ba-8858-547a07a39638.png" alt="Decorative sample: slide showing advanced styling and JavaScript tasks" style="width:100%;border-radius:10px;display:block" />
            </div>

            <!-- Contact form -->
            <div id="contact" style="grid-column:1/-1">
              <h3>Contact Us</h3>
              <form class="contact-form" id="contactForm" novalidate aria-describedby="formMsg" autocomplete="on">
                <div class="row">
                  <label>
                    Full name
                    <input type="text" name="name" id="name" required placeholder="Your full name" autocomplete="name" />
                  </label>
                  <label>
                    Email
                    <input type="email" name="email" id="email" required placeholder="name@example.com" autocomplete="email" />
                  </label>
                </div>
                <label>
                  Message
                  <textarea name="message" id="message" rows="4" required placeholder="Your message..."></textarea>
                </label>

                <div class="form-actions">
                  <button type="submit" class="btn" id="sendBtn">Send message</button>
                  <button type="button" class="btn secondary" id="clearBtn">Clear</button>
                  <div id="formMsg" class="msg" aria-live="polite" aria-atomic="true"></div>
                </div>
              </form>
            </div>

            <!-- Fetch demo (Task 3) -->
            <div style="padding:8px;border-radius:8px;border:1px dashed #e6efee;background:#fff;display:flex;flex-direction:column;gap:8px">
              <h4>Fetch a Joke (API demo)</h4>
              <p class="small muted">Example: show how to fetch and display data from a public API.</p>
              <div id="jokeBox" class="muted small">Click the button to load a joke.</div>
              <div style="display:flex;gap:8px">
                <button id="getJoke" class="btn">Get a joke</button>
                <button id="clearJoke" class="btn secondary">Clear</button>
              </div>
            </div>

            <!-- Learn links -->
            <div>
              <h4 id="learn">Learn more</h4>
              <p class="aside-note">Great references for web development:</p>
              <ul style="padding-left:18px;color:var(--muted)">
                <li><a href="https://developer.mozilla.org/en-US/" target="_blank" rel="noopener noreferrer">MDN Web Docs</a></li>
                <li><a href="https://css-tricks.com/" target="_blank" rel="noopener noreferrer">CSS-Tricks</a></li>
                <li><a href="https://javascript.info/" target="_blank" rel="noopener noreferrer">javascript.info</a></li>
              </ul>
            </div>

            <!-- To-do list -->
            <aside class="card" id="todo" style="grid-column:1/-1">
              <div id="todoApp">
                <h3>To-Do List (dynamic)</h3>
                <form id="todoForm" class="todo-controls" aria-label="Add task">
                  <input id="taskInput" placeholder="Add a new task..." aria-label="Task" required />
                  <button class="btn" type="submit">Add</button>
                </form>
                <ul class="todo-list" id="tasks" aria-live="polite" aria-atomic="true"></ul>
                <div style="margin-top:10px;display:flex;gap:8px;align-items:center">
                  <button id="clearCompleted" class="btn secondary" type="button">Clear All</button>
                  <div style="flex:1;color:var(--muted);font-size:13px;text-align:right" id="todoCount">0 tasks</div>
                </div>
              </div>
            </aside>

          </div>
        </section>

        <!-- Right: sidebar -->
        <aside class="card" aria-labelledby="sidebarTitle">
          <h3 id="sidebarTitle">Quick Notes</h3>
          <p class="aside-note">Tips & reminders:</p>
          <ul style="padding-left:18px;color:var(--muted)">
            <li>Design mobile-first and use media queries.</li>
            <li>Use browser validation + server-side checks for production.</li>
            <li>Persist small client state with <code>localStorage</code>.</li>
          </ul>
        </aside>
      </div>
    </main>

    <footer class="site-footer">
      <small>&copy; <span id="year"></span> ApexPlanet Software Pvt Ltd — Example lab</small>
    </footer>
  </div>

<script>
/* ---------------- Utilities ---------------- */
const $ = id => document.getElementById(id);
$('year').textContent = new Date().getFullYear();

/* ---------- Contact form validation & handling (Task 2) ---------- */
const contactForm = $('contactForm');
const formMsg = $('formMsg');
const clearBtn = $('clearBtn');

function validateEmail(email){
  // simple, readable regex
  return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
}

function showFormMessage(msg, type = '') {
  formMsg.textContent = msg;
  formMsg.className = 'msg';
  if (type === 'error') formMsg.classList.add('error');
  else if (type === 'success') formMsg.classList.add('success');
}

contactForm.addEventListener('submit', (e) => {
  e.preventDefault();
  showFormMessage('', '');
  const name = $('name').value.trim();
  const email = $('email').value.trim();
  const message = $('message').value.trim();

  // Basic validation
  if (!name) { showFormMessage('Name is required.', 'error'); $('name').focus(); return; }
  if (!email) { showFormMessage('Email is required.', 'error'); $('email').focus(); return; }
  if (!validateEmail(email)) { showFormMessage('Please enter a valid email address.', 'error'); $('email').focus(); return; }
  if (!message) { showFormMessage('Message cannot be empty.', 'error'); $('message').focus(); return; }

  // Simulate async submission - replace with fetch() to real endpoint
  try {
    console.info('Submitting contact form', {name, email, message});
    showFormMessage('Thanks — your message has been received (demo).', 'success');
    contactForm.reset();
    // move focus to confirmation for screen readers
    formMsg.setAttribute('tabindex', '-1');
    formMsg.focus();
  } catch (err) {
    console.error(err);
    showFormMessage('An unexpected error occurred. Please try again.', 'error');
  }
});

clearBtn.addEventListener('click', () => {
  contactForm.reset();
  showFormMessage('', '');
});

/* ---------- Fetch demo (Task 3) ---------- */
const getJokeBtn = $('getJoke');
const clearJokeBtn = $('clearJoke');
const jokeBox = $('jokeBox');

async function fetchJoke(){
  jokeBox.textContent = 'Loading...';
  try {
    // icanhazdadjoke supports CORS and returns plain json with Accept header
    const res = await fetch('https://icanhazdadjoke.com/', { headers: { Accept: 'application/json' }});
    if (!res.ok) throw new Error('Network error');
    const data = await res.json();
    jokeBox.textContent = data?.joke || 'No joke found.';
  } catch (err) {
    console.warn(err);
    jokeBox.textContent = 'Could not fetch a joke. (Demo offline or blocked)';
  }
}

getJokeBtn.addEventListener('click', fetchJoke);
clearJokeBtn.addEventListener('click', () => { jokeBox.textContent = 'Click the button to load a joke.'; });

/* ---------- Dynamic To-Do List (Task 4) ---------- */
const todoForm = $('todoForm');
const taskInput = $('taskInput');
const tasksEl = $('tasks');
const clearAllBtn = $('clearCompleted');
const todoCount = $('todoCount');

const STORAGE_KEY = 'apx_todo_v1';

// safe storage helpers
function loadTasks() {
  try {
    const raw = localStorage.getItem(STORAGE_KEY);
    return raw ? JSON.parse(raw) : [];
  } catch (err) {
    console.warn('Failed to parse tasks from storage', err);
    return [];
  }
}
function saveTasks(tasks) {
  try {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(tasks));
  } catch (err) {
    console.warn('Could not save tasks to storage', err);
  }
}

let tasks = loadTasks();

function renderTasks() {
  tasksEl.innerHTML = '';
  if (tasks.length === 0) {
    const li = document.createElement('li');
    li.className = 'todo-item';
    li.textContent = 'No tasks yet. Add one above!';
    tasksEl.appendChild(li);
  } else {
    tasks.forEach((t, idx) => {
      const li = document.createElement('li');
      li.className = 'todo-item';
      li.dataset.index = idx;

      const left = document.createElement('div');
      left.className = 'left';

      const chk = document.createElement('input');
      chk.type = 'checkbox';
      chk.checked = !!t.done;
      chk.setAttribute('aria-label', `Mark "${t.text}" as done`);

      const span = document.createElement('span');
      span.textContent = t.text;
      span.style.textDecoration = t.done ? 'line-through' : 'none';

      left.appendChild(chk);
      left.appendChild(span);

      const actions = document.createElement('div');
      const del = document.createElement('button');
      del.type = 'button';
      del.textContent = 'Remove';
      del.className = 'remove-btn';
      del.setAttribute('aria-label', `Remove "${t.text}"`);

      actions.appendChild(del);
      li.appendChild(left);
      li.appendChild(actions);
      tasksEl.appendChild(li);
    });
  }
  todoCount.textContent = `${tasks.length} task${tasks.length !== 1 ? 's' : ''}`;
}

// Event delegation on the list for performance & simplicity
tasksEl.addEventListener('change', (e) => {
  const li = e.target.closest('li');
  if (!li) return;
  const idx = Number(li.dataset.index);
  if (Number.isNaN(idx)) return;
  if (e.target.type === 'checkbox') {
    tasks[idx].done = e.target.checked;
    saveTasks(tasks);
    renderTasks();
  }
});

tasksEl.addEventListener('click', (e) => {
  if (e.target.matches('.remove-btn')) {
    const li = e.target.closest('li');
    const idx = Number(li.dataset.index);
    if (!Number.isNaN(idx)) {
      tasks.splice(idx, 1);
      saveTasks(tasks);
      renderTasks();
    }
  }
});

todoForm.addEventListener('submit', (e) => {
  e.preventDefault();
  const text = taskInput.value.trim();
  if (!text) {
    // small client-side guard
    taskInput.focus();
    return;
  }
  tasks.unshift({ text, done:false, created:Date.now() });
  saveTasks(tasks);
  taskInput.value = '';
  taskInput.focus();
  renderTasks();
});

clearAllBtn.addEventListener('click', () => {
  if (!confirm('Clear all tasks?')) return;
  tasks = [];
  saveTasks(tasks);
  renderTasks();
});

/* initial render */
renderTasks();

console.log('Interactive demo loaded — contact form + todo list + fetch demo active.');
</script>
</body>
</html>
