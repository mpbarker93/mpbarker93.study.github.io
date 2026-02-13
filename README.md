# mpbarker93.study.github.io
Study Website Github
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>ACRRM Fellowship Study Hub</title>
  <style>
    :root{
      --bg:#0b1220;
      --panel:#111a2e;
      --panel2:#0f1730;
      --text:#e8eefc;
      --muted:#a9b6d6;
      --border:rgba(255,255,255,.12);
      --accent:#6ee7ff;
      --accent2:#a78bfa;
      --ok:#34d399;
      --warn:#fbbf24;
      --bad:#fb7185;
      --shadow: 0 10px 30px rgba(0,0,0,.35);
      --radius: 18px;
      --mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono","Courier New", monospace;
      --sans: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
    }

    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:var(--sans);
      background: radial-gradient(1200px 700px at 20% 10%, rgba(110,231,255,.12), transparent 60%),
                  radial-gradient(1000px 700px at 80% 20%, rgba(167,139,250,.12), transparent 60%),
                  var(--bg);
      color:var(--text);
      line-height:1.5;
    }

    a{color:var(--accent); text-decoration:none}
    a:hover{text-decoration:underline}

    header{
      position:sticky; top:0; z-index:20;
      backdrop-filter: blur(10px);
      background: rgba(11,18,32,.75);
      border-bottom:1px solid var(--border);
    }

    .wrap{max-width:1100px; margin:0 auto; padding:18px 18px}
    .topbar{
      display:flex; gap:14px; align-items:center; justify-content:space-between;
    }
    .brand{
      display:flex; gap:12px; align-items:center;
    }
    .logo{
      width:38px;height:38px;border-radius:12px;
      background: linear-gradient(135deg, rgba(110,231,255,.9), rgba(167,139,250,.9));
      box-shadow: var(--shadow);
    }
    .brand h1{
      font-size:16px; margin:0;
      letter-spacing:.3px;
    }
    .brand p{margin:0; font-size:12px; color:var(--muted)}

    nav{
      display:flex; gap:8px; flex-wrap:wrap; justify-content:flex-end;
    }
    .tab{
      border:1px solid var(--border);
      background: rgba(17,26,46,.45);
      padding:9px 12px;
      border-radius:999px;
      color:var(--text);
      font-size:13px;
      cursor:pointer;
      transition:.15s ease;
    }
    .tab:hover{transform: translateY(-1px); border-color: rgba(255,255,255,.22)}
    .tab.active{
      background: linear-gradient(135deg, rgba(110,231,255,.22), rgba(167,139,250,.22));
      border-color: rgba(110,231,255,.55);
    }

    main{padding:22px 0 70px}
    .grid{
      display:grid;
      grid-template-columns: 1.2fr .8fr;
      gap:18px;
      align-items:start;
    }
    @media (max-width: 960px){
      .grid{grid-template-columns:1fr}
    }

    .card{
      background: linear-gradient(180deg, rgba(17,26,46,.82), rgba(15,23,48,.7));
      border:1px solid var(--border);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding:16px;
    }

    .card h2{
      margin:0 0 10px;
      font-size:18px;
      letter-spacing:.2px;
    }
    .sub{color:var(--muted); margin-top:-4px; margin-bottom:14px; font-size:13px}
    .pillrow{display:flex; gap:8px; flex-wrap:wrap}
    .pill{
      font-size:12px;
      border:1px solid var(--border);
      padding:6px 10px;
      border-radius:999px;
      background: rgba(255,255,255,.03);
      color:var(--muted);
    }

    .controls{display:grid; gap:12px}
    .row{display:flex; gap:10px; flex-wrap:wrap; align-items:center}
    label{font-size:13px; color:var(--muted)}
    select,input[type="number"],input[type="text"]{
      background: rgba(0,0,0,.15);
      border:1px solid var(--border);
      color:var(--text);
      padding:10px 12px;
      border-radius:12px;
      outline:none;
      min-width: 180px;
    }
    input[type="number"]{min-width:120px}
    .btn{
      border:1px solid rgba(110,231,255,.55);
      background: linear-gradient(135deg, rgba(110,231,255,.22), rgba(167,139,250,.18));
      color: var(--text);
      padding:10px 14px;
      border-radius:12px;
      cursor:pointer;
      font-weight:600;
      transition:.15s ease;
    }
    .btn:hover{transform: translateY(-1px)}
    .btn.secondary{
      border:1px solid var(--border);
      background: rgba(255,255,255,.04);
      font-weight:600;
    }
    .btn.danger{
      border-color: rgba(251,113,133,.6);
      background: rgba(251,113,133,.12);
    }

    .checkgrid{
      display:grid;
      grid-template-columns: repeat(2, minmax(0,1fr));
      gap:10px;
    }
    @media (max-width: 560px){
      .checkgrid{grid-template-columns:1fr}
    }
    .chk{
      display:flex; gap:10px; align-items:flex-start;
      padding:10px 10px;
      border:1px solid var(--border);
      border-radius:14px;
      background: rgba(255,255,255,.03);
    }
    .chk input{margin-top:3px}
    .chk b{font-size:13px}
    .chk span{display:block; color:var(--muted); font-size:12px; margin-top:2px}

    .qbox{
      border:1px solid var(--border);
      border-radius:16px;
      padding:14px;
      background: rgba(0,0,0,.12);
      margin-bottom:12px;
    }
    .qmeta{
      display:flex; gap:8px; flex-wrap:wrap; margin-bottom:10px;
      font-size:12px; color:var(--muted);
    }
    .tag{
      border:1px solid rgba(255,255,255,.12);
      border-radius:999px;
      padding:4px 8px;
      background: rgba(255,255,255,.03);
    }
    .qstem{font-size:15px; margin:0 0 10px}
    .opts{display:grid; gap:8px; margin:10px 0}
    .opt{
      border:1px solid var(--border);
      border-radius:12px;
      padding:10px;
      background: rgba(255,255,255,.03);
      cursor:pointer;
      transition:.12s ease;
    }
    .opt:hover{border-color: rgba(255,255,255,.22)}
    .opt.selected{border-color: rgba(110,231,255,.55); background: rgba(110,231,255,.12)}
    .opt.correct{border-color: rgba(52,211,153,.6); background: rgba(52,211,153,.12)}
    .opt.wrong{border-color: rgba(251,113,133,.65); background: rgba(251,113,133,.12)}
    .explain{
      margin-top:10px;
      color:var(--muted);
      font-size:13px;
      border-left:3px solid rgba(110,231,255,.55);
      padding-left:10px;
    }

    .hidden{display:none !important}
    .footer-note{color:var(--muted); font-size:12px; margin-top:10px}
    .mono{font-family:var(--mono)}
    .divider{height:1px;background:var(--border);margin:14px 0}
  </style>
</head>

<body>
<header>
  <div class="wrap topbar">
    <div class="brand">
      <div class="logo" aria-hidden="true"></div>
      <div>
        <h1>ACRRM Fellowship Study Hub</h1>
        <p>CGT + RG-SSSA anaesthetics • resources • MCQ/SAQ/LAQ generator</p>
      </div>
    </div>

    <nav aria-label="Primary navigation">
      <button class="tab active" data-page="home">Home</button>
      <button class="tab" data-page="curriculum">Curriculum outlines</button>
      <button class="tab" data-page="resources">Academic resources</button>
      <button class="tab" data-page="mcq">Practice MCQs</button>
      <button class="tab" data-page="saq">Short answers</button>
      <button class="tab" data-page="laq">Long answers</button>
    </nav>
  </div>
</header>

<main class="wrap">

  <!-- HOME -->
  <section id="page-home">
    <div class="grid">
      <div class="card">
        <h2>Welcome</h2>
        <p class="sub">
          Use this as your “single front door” for ACRRM study: curriculum structure, guidelines, and exam practice by module.
        </p>

        <div class="pillrow">
          <span class="pill">Randomised question sets</span>
          <span class="pill">Topic checkboxes</span>
          <span class="pill">Semester filters (A–D)</span>
          <span class="pill">MCQ + SAQ + LAQ</span>
        </div>

        <div class="divider"></div>

        <p>
          Tip: start by setting up your <b>Semester modules (A–D)</b> and <b>Topics</b> on the MCQ/SAQ/LAQ pages.
          The defaults below are a safe starting point and can be edited in the <span class="mono">QUESTION_BANK</span> section.
        </p>

        <p class="footer-note">
          This site includes starter items seeded from your uploaded RG-SSSA sample questions :contentReference[oaicite:4]{index=4} and NCSP cervical screening documents :contentReference[oaicite:5]{index=5}.
        </p>
      </div>

      <div class="card">
        <h2>Quick actions</h2>
        <div class="controls">
          <button class="btn" onclick="go('mcq')">Generate an MCQ set</button>
          <button class="btn secondary" onclick="go('saq')">Generate short answers</button>
          <button class="btn secondary" onclick="go('laq')">Generate long answers</button>
          <button class="btn danger" onclick="resetProgress()">Reset answers / progress</button>
        </div>
        <p class="footer-note">
          Your answers are stored locally in your browser (no cloud sync).
        </p>
      </div>
    </div>
  </section>

  <!-- CURRICULUM -->
  <section id="page-curriculum" class="hidden">
    <div class="grid">
      <div class="card">
        <h2>Curriculum outlines</h2>
        <p class="sub">
          High-level structure you can refine into your own modules. (You can paste your exact A–D outline once you have it.)
        </p>

        <h3 style="margin:10px 0 6px">Core Generalist Training (CGT)</h3>
        <ul>
          <li>Training is aligned to the Rural Generalist curriculum domains/learning areas. :contentReference[oaicite:6]{index=6}</li>
          <li>CGT includes mandatory breadth + rural context training, and structured assessment (including MCQ). :contentReference[oaicite:7]{index=7}</li>
          <li>ACRRM education program was restructured into online semesters; historical note includes Semesters A/B and later mandatory Semesters C/D. :contentReference[oaicite:8]{index=8} :contentReference[oaicite:9]{index=9}</li>
        </ul>

        <h3 style="margin:14px 0 6px">RG-SSSA Anaesthetics program (your exam practice section)</h3>
        <ul>
          <li>Use the RG-SSSA viva structure as “modules”: Resus/Trauma, Airway, GA/Sedation, Regional, Paeds, Pain, Obstetric, Peri-op. :contentReference[oaicite:10]{index=10}</li>
          <li>Anchor your question tags to the ACRRM Anaesthetics learning area + peri-op / crisis management. :contentReference[oaicite:11]{index=11}</li>
        </ul>

        <div class="divider"></div>
        <p class="footer-note">
          If you upload (or paste) your exact A–D module outline, I can wire it into the dropdowns and tags automatically.
        </p>
      </div>

      <div class="card">
        <h2>Learning areas (topic backbone)</h2>
        <p class="sub">
          Use these as checkbox topics across MCQ/SAQ/LAQ.
        </p>
        <ul style="columns:2; gap:16px">
          <li>Emergency</li><li>Chronic disease</li><li>Paediatrics</li><li>O&amp;G</li><li>Anaesthetics</li>
          <li>Mental health</li><li>Population health</li><li>Remote medicine</li><li>Aboriginal &amp; Torres Strait Islander health</li>
          <li>Pharmacology</li><li>Procedural skills</li><li>Professional / ethics</li>
        </ul>
        <p class="footer-note">
          Full learning-area list exists in the ACRRM Rural Generalist Curriculum document. :contentReference[oaicite:12]{index=12}
        </p>
      </div>
    </div>
  </section>

  <!-- RESOURCES -->
  <section id="page-resources" class="hidden">
    <div class="card">
      <h2>Academic (medical) resources</h2>
      <p class="sub">Suggested “primary guideline anchors” (Australian) + your uploaded references.</p>

      <h3 style="margin:10px 0 6px">Uploaded reference pack</h3>
      <ul>
        <li>NCSP Cervical Screening summary guide (2024). :contentReference[oaicite:13]{index=13}</li>
        <li>NCSP Cervical Screening Algorithms (2024) (flowcharts). :contentReference[oaicite:14]{index=14}</li>
        <li>RG-SSSA sample exam questions (Sept 2024). :contentReference[oaicite:15]{index=15}</li>
      </ul>

      <h3 style="margin:14px 0 6px">Recommended Australian guideline anchors (web)</h3>
      <ul>
        <li>RACGP “Red Book” preventive activities (10th ed; citation notes 2024; PDF access page updated 2025). :contentReference[oaicite:16]{index=16}</li>
        <li>National Bowel Cancer Screening Program – eligible ages now include 45–74. :contentReference[oaicite:17]{index=17}</li>
        <li>Queensland Health Maternity &amp; Neonatal Clinical Guideline: Primary Postpartum Haemorrhage (publication Aug 2024). :contentReference[oaicite:18]{index=18}</li>
      </ul>

      <p class="footer-note">
        You can add direct links inside Canva buttons, or link out to these resources from this site.
      </p>
    </div>
  </section>

  <!-- MCQ -->
  <section id="page-mcq" class="hidden">
    <div class="grid">
      <div class="card">
        <h2>Practice MCQs</h2>
        <p class="sub">Build a randomised MCQ set by semester + topic filters.</p>

        <div class="controls">
          <div class="row">
            <label for="mcq-sem">Semester</label>
            <select id="mcq-sem"></select>

            <label for="mcq-size">Quiz size</label>
            <input id="mcq-size" type="number" min="5" max="60" value="10" />
          </div>

          <div class="row">
            <label for="mcq-search">Search (stem/topic)</label>
            <input id="mcq-search" type="text" placeholder="e.g., cervical screening, PPH, airway…" />
          </div>

          <div>
            <label>Topic filters</label>
            <div id="mcq-topics" class="checkgrid" style="margin-top:8px"></div>
          </div>

          <div class="row">
            <button class="btn" onclick="generateSet('MCQ')">Generate MCQ set</button>
            <button class="btn secondary" onclick="selectAllTopics('MCQ', true)">Select all</button>
            <button class="btn secondary" onclick="selectAllTopics('MCQ', false)">Select none</button>
          </div>
        </div>
      </div>

      <div class="card">
        <h2>Session stats</h2>
        <div id="mcq-stats" class="sub">Generate a set to begin.</div>
        <p class="footer-note">
          This is a starter bank—add your own items by editing <span class="mono">QUESTION_BANK</span>.
        </p>
      </div>
    </div>

    <div class="card" style="margin-top:18px">
      <h2>Questions</h2>
      <div id="mcq-out"></div>
    </div>
  </section>

  <!-- SAQ -->
  <section id="page-saq" class="hidden">
    <div class="grid">
      <div class="card">
        <h2>Short answer practice</h2>
        <p class="sub">Generate SAQs by semester + topic filters (randomised).</p>

        <div class="controls">
          <div class="row">
            <label for="saq-sem">Semester</label>
            <select id="saq-sem"></select>

            <label for="saq-size">Set size</label>
            <input id="saq-size" type="number" min="3" max="30" value="6" />
          </div>

          <div class="row">
            <label for="saq-search">Search (stem/topic)</label>
            <input id="saq-search" type="text" placeholder="e.g., antenatal bleeding, HPV…" />
          </div>

          <div>
            <label>Topic filters</label>
            <div id="saq-topics" class="checkgrid" style="margin-top:8px"></div>
          </div>

          <div class="row">
            <button class="btn" onclick="generateSet('SAQ')">Generate SAQ set</button>
            <button class="btn secondary" onclick="selectAllTopics('SAQ', true)">Select all</button>
            <button class="btn secondary" onclick="selectAllTopics('SAQ', false)">Select none</button>
          </div>
        </div>
      </div>

      <div class="card">
        <h2>How to mark yourself</h2>
        <ul class="sub" style="margin-top:6px">
          <li>Use a consistent structure: definition → key differentials → red flags → investigations → management → safety-net.</li>
          <li>For rural context: mention resources, retrieval thresholds, and teamwork.</li>
        </ul>
      </div>
    </div>

    <div class="card" style="margin-top:18px">
      <h2>SAQs</h2>
      <div id="saq-out"></div>
    </div>
  </section>

  <!-- LAQ -->
  <section id="page-laq" class="hidden">
    <div class="grid">
      <div class="card">
        <h2>Long answer practice</h2>
        <p class="sub">Generate structured LAQs (essay / management plans / viva-style long form).</p>

        <div class="controls">
          <div class="row">
            <label for="laq-sem">Semester</label>
            <select id="laq-sem"></select>

            <label for="laq-size">Set size</label>
            <input id="laq-size" type="number" min="1" max="15" value="3" />
          </div>

          <div class="row">
            <label for="laq-search">Search (stem/topic)</label>
            <input id="laq-search" type="text" placeholder="e.g., maternal collapse, trauma RSI…" />
          </div>

          <div>
            <label>Topic filters</label>
            <div id="laq-topics" class="checkgrid" style="margin-top:8px"></div>
          </div>

          <div class="row">
            <button class="btn" onclick="generateSet('LAQ')">Generate LAQ set</button>
            <button class="btn secondary" onclick="selectAllTopics('LAQ', true)">Select all</button>
            <button class="btn secondary" onclick="selectAllTopics('LAQ', false)">Select none</button>
          </div>
        </div>
      </div>

      <div class="card">
        <h2>Suggested format</h2>
        <div class="sub">
          <div><b>1)</b> Situation + immediate priorities</div>
          <div><b>2)</b> Focused assessment (history/exam/investigations)</div>
          <div><b>3)</b> Differential + reasoning</div>
          <div><b>4)</b> Management plan (initial → definitive)</div>
          <div><b>5)</b> Rural context: limits, escalation/retrieval, documentation, communication</div>
          <div><b>6)</b> Safety net + follow-up</div>
        </div>
      </div>
    </div>

    <div class="card" style="margin-top:18px">
      <h2>LAQs</h2>
      <div id="laq-out"></div>
    </div>
  </section>

</main>

<script>
/**
 * =========================
 * CONFIG: Semesters & Topics
 * =========================
 * Replace the SEMESTERS object with your exact CGT A–D module map when ready.
 */
const SEMESTERS = {
  "Semester A": { description: "Foundations (edit to match your CGT outline)", topicsHint: ["Preventive care", "Approach to undifferentiated presentations"] },
  "Semester B": { description: "Core clinical breadth (edit to match your CGT outline)", topicsHint: ["Chronic disease", "Mental health"] },
  "Semester C": { description: "Online semester C (mandatory per program notes)", topicsHint: ["Emergency", "Women’s health"] },
  "Semester D": { description: "Online semester D (mandatory per program notes)", topicsHint: ["Paediatrics", "Rural systems / isolation"] },
  "All semesters": { description: "No semester filter", topicsHint: [] }
};

const TOPICS = [
  { key:"Cervical screening", desc:"NCSP CST, HPV, follow-up, colposcopy pathways" },
  { key:"Bowel screening", desc:"NBCSP iFOBT pathways, positives, risk" },
  { key:"Breast screening", desc:"Screening intervals, risk stratification" },
  { key:"Prostate screening", desc:"Shared decision-making, PSA considerations" },
  { key:"PPH / maternity emergencies", desc:"Postpartum haemorrhage, maternal collapse" },
  { key:"Anaesthesia – airway", desc:"RSI, difficult airway, oxygenation/ventilation" },
  { key:"Anaesthesia – obstetric", desc:"LSCS anaesthesia, aspiration, PPH, escalation" },
  { key:"Trauma / resus", desc:"Primary survey, shock differentials, transfer" },
  { key:"Pain medicine", desc:"Acute/neuropathic pain, opioids, tolerance" },
  { key:"Rural context", desc:"Resources, retrieval, scope, teamwork" }
];

/**
 * =========================
 * QUESTION BANK (starter)
 * =========================
 * Add items freely. Each item:
 * {
 *   id, type: "MCQ"|"SAQ"|"LAQ",
 *   semester: "Semester A"|"Semester B"|"Semester C"|"Semester D"|"All semesters",
 *   topics: [TOPIC keys...],
 *   stem: "Question text",
 *   options: ["A","B","C","D","E"] (MCQ only),
 *   answerIndex: 0-based (MCQ only),
 *   explanation: "Brief rationale / marking points",
 *   sourceTag: "NCSP 2024 / RG-SSSA / etc"
 * }
 */
const QUESTION_BANK = [
  // ---- MCQs ----
  {
    id:"mcq-001",
    type:"MCQ",
    semester:"Semester A",
    topics:["Cervical screening","Rural context"],
    stem:"In the National Cervical Screening Program (NCSP), who is eligible for routine cervical screening?",
    options:[
      "All people with a cervix aged 18–74 regardless of sexual history",
      "Women and people with a cervix aged 25–74 who have ever had any type of sexual contact",
      "Only people who are unvaccinated for HPV",
      "Only people currently sexually active",
      "Only those with symptoms suggestive of cervical cancer"
    ],
    answerIndex:1,
    explanation:"NCSP routine screening is for women and people with a cervix aged 25–74 who have ever had sexual contact; screening is recommended regardless of HPV vaccination status or current sexual activity.",
    sourceTag:"NCSP summary guide"
  },
  {
    id:"mcq-002",
    type:"MCQ",
    semester:"Semester A",
    topics:["Cervical screening"],
    stem:"Which situation generally requires a clinician-collected co-test (HPV + LBC) rather than HPV-only self-collection?",
    options:[
      "Routine screening in an asymptomatic 30-year-old",
      "Routine screening in an asymptomatic 60-year-old",
      "Persistent postcoital bleeding with concern for cervical pathology",
      "A person who prefers self-collection",
      "A person who is HPV vaccinated"
    ],
    answerIndex:2,
    explanation:"Co-testing is recommended for signs/symptoms suggestive of cervical cancer (e.g., unexplained postcoital bleeding), as HPV-only self-collection cannot provide cytology from the same sample.",
    sourceTag:"NCSP summary guide"
  },
  {
    id:"mcq-003",
    type:"MCQ",
    semester:"Semester B",
    topics:["Bowel screening","Preventive care"],
    stem:"Australia’s National Bowel Cancer Screening Program currently offers free population screening to eligible asymptomatic people in which age range?",
    options:["40–69","45–74","50–74 only","55–79","Any adult with a family history"],
    answerIndex:1,
    explanation:"The NBCSP eligibility has expanded to include ages 45–74 for average-risk population screening with iFOBT.",
    sourceTag:"Health.gov.au NBCSP"
  },
  {
    id:"mcq-004",
    type:"MCQ",
    semester:"Semester C",
    topics:["Trauma / resus","Rural context","Anaesthesia – airway"],
    stem:"A 30-year-old with trauma has BP 80/40 and GCS falls from 12 to 6. Which is the most appropriate next step?",
    options:[
      "Wait for CT brain before airway intervention",
      "Secure the airway and prevent secondary brain injury while preparing transfer/retrieval",
      "Give 2 L crystalloid before any other action",
      "Discharge if neuro observations stabilise for 30 minutes",
      "Avoid intubation because of aspiration risk"
    ],
    answerIndex:1,
    explanation:"Deteriorating GCS indicates need for airway protection with a structured approach to prevent secondary brain injury and coordinate retrieval in rural context.",
    sourceTag:"RG-SSSA viva themes"
  },
  {
    id:"mcq-005",
    type:"MCQ",
    semester:"Semester C",
    topics:["Anaesthesia – obstetric","PPH / maternity emergencies","Rural context"],
    stem:"During LSCS under spinal, 1.5 L blood loss and hypotension occur with retained placenta concerns. Which is the best immediate priority set?",
    options:[
      "Observe; spinal anaesthesia prevents shock",
      "Call for help, resuscitate, activate massive haemorrhage/critical bleeding pathway, give uterotonics/TxA as indicated, prepare for conversion to GA and escalation",
      "Give opioids only and continue surgery",
      "Give 2 L crystalloid before any blood products",
      "Transfer immediately without stabilisation"
    ],
    answerIndex:1,
    explanation:"Recognise PPH and treat early with leadership, resuscitation, haemorrhage protocol (including pharmacologic + blood products), and plan for escalation/retrieval if needed.",
    sourceTag:"RG-SSSA viva themes"
  },

  // ---- SAQs ----
  {
    id:"saq-001",
    type:"SAQ",
    semester:"Semester A",
    topics:["Cervical screening"],
    stem:"Explain how you counsel a patient choosing between clinician-collection and self-collection for a Cervical Screening Test (CST). Include accuracy, follow-up steps if HPV is detected, and when co-testing is needed.",
    explanation:"Marking points: explain equivalence for HPV detection; self-collection is HPV-only; possible need to return for clinician-collected LBC depending on results; co-test required if symptoms/concerns for cancer, AIS follow-up, DES exposure etc; shared decision-making.",
    sourceTag:"NCSP summary guide"
  },
  {
    id:"saq-002",
    type:"SAQ",
    semester:"Semester C",
    topics:["Anaesthesia – obstetric","Rural context"],
    stem:"You are called for an urgent LSCS in a patient with limited antenatal history, low-lying placenta on bedside US, and a meal 2 hours ago. List your key concerns and outline your pre-anaesthetic assessment approach.",
    explanation:"Marking points: placenta praevia/accreta risk; PPH; aspiration risk; uterine rupture risk; resource check; blood availability; IV access; airway assessment; consent; escalation thresholds and teamwork.",
    sourceTag:"RG-SSSA sample viva"
  },

  // ---- LAQs ----
  {
    id:"laq-001",
    type:"LAQ",
    semester:"Semester C",
    topics:["Trauma / resus","Rural context","Anaesthesia – airway"],
    stem:"Rural ED trauma: quad-bike rollover with hypotension, femur fracture and head injury; GCS later drops. Write a structured management plan from arrival through stabilisation and retrieval, including airway strategy and preventing secondary brain injury.",
    explanation:"Marking points: primary survey; shock differentials; haemorrhage control; analgesia; RSI considerations; ventilation/CO2 targets; BP/MAP targets; imaging timing; communication/retrieval logistics; documentation and team leadership.",
    sourceTag:"RG-SSSA sample viva themes"
  },
  {
    id:"laq-002",
    type:"LAQ",
    semester:"Semester A",
    topics:["Cervical screening","Preventive care"],
    stem:"Design a practice protocol for opportunistic preventive screening in a rural clinic: incorporate cervical and bowel screening eligibility, patient education, recall systems, and managing common abnormal results/referrals.",
    explanation:"Marking points: eligibility, informed consent, culturally safe approach, recall/registry, pathways for positives, colposcopy/referral timing, safety-netting.",
    sourceTag:"RACGP Red Book + NCSP + NBCSP"
  }
];


// =========================
// UI wiring
// =========================
const pages = ["home","curriculum","resources","mcq","saq","laq"];

function go(page){
  pages.forEach(p=>{
    document.getElementById(`page-${p}`).classList.toggle("hidden", p!==page);
    document.querySelector(`.tab[data-page="${p}"]`).classList.toggle("active", p===page);
  });
  window.scrollTo({top:0,behavior:"smooth"});
}

document.querySelectorAll(".tab").forEach(btn=>{
  btn.addEventListener("click", ()=> go(btn.dataset.page));
});

function buildSemesterSelect(id){
  const sel = document.getElementById(id);
  sel.innerHTML = "";
  Object.keys(SEMESTERS).forEach(k=>{
    const opt=document.createElement("option");
    opt.value=k; opt.textContent=k;
    sel.appendChild(opt);
  });
  sel.value = "All semesters";
}

function buildTopics(containerId, prefix){
  const box = document.getElementById(containerId);
  box.innerHTML="";
  TOPICS.forEach((t,i)=>{
    const id = `${prefix}-topic-${i}`;
    const div=document.createElement("label");
    div.className="chk";
    div.innerHTML = `
      <input type="checkbox" id="${id}" data-topic="${t.key}" checked />
      <div>
        <b>${t.key}</b>
        <span>${t.desc}</span>
      </div>
    `;
    box.appendChild(div);
  });
}

buildSemesterSelect("mcq-sem");
buildSemesterSelect("saq-sem");
buildSemesterSelect("laq-sem");

buildTopics("mcq-topics","mcq");
buildTopics("saq-topics","saq");
buildTopics("laq-topics","laq");

function selectedTopics(prefix){
  const nodes = document.querySelectorAll(`#${prefix}-topics input[type="checkbox"]`);
  return [...nodes].filter(n=>n.checked).map(n=>n.dataset.topic);
}

function selectAllTopics(type, on){
  const prefix = type.toLowerCase();
  document.querySelectorAll(`#${prefix}-topics input[type="checkbox"]`).forEach(n=>n.checked=on);
}

function shuffle(arr){
  const a=[...arr];
  for(let i=a.length-1;i>0;i--){
    const j=Math.floor(Math.random()*(i+1));
    [a[i],a[j]]=[a[j],a[i]];
  }
  return a;
}

function includesSearch(q, searchTerm){
  if(!searchTerm) return true;
  const s = searchTerm.trim().toLowerCase();
  if(!s) return true;
  return (q.stem.toLowerCase().includes(s) ||
          (q.topics||[]).some(t=>t.toLowerCase().includes(s)) ||
          (q.sourceTag||"").toLowerCase().includes(s));
}

function generateSet(type){
  const prefix = type.toLowerCase();
  const sem = document.getElementById(`${prefix}-sem`).value;
  const size = parseInt(document.getElementById(`${prefix}-size`).value,10);
  const searchTerm = document.getElementById(`${prefix}-search`).value || "";
  const topics = selectedTopics(prefix);

  const pool = QUESTION_BANK.filter(q=>{
    if(q.type !== type) return false;
    if(sem !== "All semesters" && q.semester !== sem) return false;
    if(!q.topics?.some(t=>topics.includes(t))) return false;
    if(!includesSearch(q, searchTerm)) return false;
    return true;
  });

  const picked = shuffle(pool).slice(0, Math.min(size, pool.length));

  const out = document.getElementById(`${prefix}-out`);
  out.innerHTML = "";

  if(type==="MCQ"){
    document.getElementById("mcq-stats").textContent =
      `Pool: ${pool.length} • Showing: ${picked.length} • Semester: ${sem} • Topics selected: ${topics.length}`;
  }

  if(picked.length===0){
    out.innerHTML = `<p class="sub">No matches. Try selecting more topics, choosing “All semesters”, or clearing the search field.</p>`;
    return;
  }

  picked.forEach((q, idx)=>{
    if(type==="MCQ") out.appendChild(renderMCQ(q, idx+1));
    if(type==="SAQ") out.appendChild(renderSAQ(q, idx+1));
    if(type==="LAQ") out.appendChild(renderLAQ(q, idx+1));
  });
}

function renderMeta(q){
  const meta=document.createElement("div");
  meta.className="qmeta";
  meta.innerHTML = `
    <span class="tag">${q.semester}</span>
    ${(q.topics||[]).map(t=>`<span class="tag">${t}</span>`).join("")}
    <span class="tag">${q.sourceTag || "—"}</span>
  `;
  return meta;
}

function renderMCQ(q, n){
  const box=document.createElement("div");
  box.className="qbox";
  box.dataset.qid = q.id;

  const p=document.createElement("p");
  p.className="qstem";
  p.innerHTML = `<b>Q${n}.</b> ${q.stem}`;

  const opts=document.createElement("div");
  opts.className="opts";

  q.options.forEach((opt, i)=>{
    const div=document.createElement("div");
    div.className="opt";
    div.textContent = `${String.fromCharCode(65+i)}. ${opt}`;
    div.addEventListener("click", ()=> selectMCQAnswer(q.id, i));
    opts.appendChild(div);
  });

  const btnRow=document.createElement("div");
  btnRow.className="row";
  btnRow.innerHTML = `
    <button class="btn secondary" onclick="revealMCQ('${q.id}')">Reveal answer</button>
    <button class="btn secondary" onclick="clearMCQ('${q.id}')">Clear</button>
  `;

  const explain=document.createElement("div");
  explain.className="explain hidden";
  explain.id = `explain-${q.id}`;
  explain.textContent = q.explanation || "";

  box.appendChild(renderMeta(q));
  box.appendChild(p);
  box.appendChild(opts);
  box.appendChild(btnRow);
  box.appendChild(explain);

  // restore previous choice
  const saved = getProgress(q.id);
  if(saved && typeof saved.answerIndex === "number"){
    markSelected(box, saved.answerIndex);
  }

  return box;
}

function selectMCQAnswer(qid, idx){
  setProgress(qid, {answerIndex: idx, revealed:false});
  const box = document.querySelector(`[data-qid="${qid}"]`);
  markSelected(box, idx);
}

function markSelected(box, idx){
  box.querySelectorAll(".opt").forEach((n,i)=>{
    n.classList.toggle("selected", i===idx);
    n.classList.remove("correct","wrong");
  });
  document.getElementById(`explain-${box.dataset.qid}`)?.classList.add("hidden");
}

function revealMCQ(qid){
  const q = QUESTION_BANK.find(x=>x.id===qid);
  const box = document.querySelector(`[data-qid="${qid}"]`);
  const saved = getProgress(qid) || {};
  const chosen = saved.answerIndex;

  box.querySelectorAll(".opt").forEach((n,i)=>{
    n.classList.remove("selected");
    if(i===q.answerIndex) n.classList.add("correct");
    if(typeof chosen==="number" && chosen===i && chosen!==q.answerIndex) n.classList.add("wrong");
  });

  document.getElementById(`explain-${qid}`)?.classList.remove("hidden");
  setProgress(qid, {answerIndex: chosen, revealed:true});
}

function clearMCQ(qid){
  setProgress(qid, null);
  const box = document.querySelector(`[data-qid="${qid}"]`);
  box.querySelectorAll(".opt").forEach(n=>n.className="opt");
  document.getElementById(`explain-${qid}`)?.classList.add("hidden");
}

function renderSAQ(q, n){
  const box=document.createElement("div");
  box.className="qbox";
  box.dataset.qid=q.id;

  box.appendChild(renderMeta(q));

  const p=document.createElement("p");
  p.className="qstem";
  p.innerHTML = `<b>SAQ${n}.</b> ${q.stem}`;
  box.appendChild(p);

  const ta=document.createElement("textarea");
  ta.style.width="100%";
  ta.style.minHeight="140px";
  ta.style.borderRadius="14px";
  ta.style.padding="12px";
  ta.style.border="1px solid rgba(255,255,255,.12)";
  ta.style.background="rgba(0,0,0,.15)";
  ta.style.color="var(--text)";
  ta.placeholder="Write your answer here (structure + rural context + safety-netting)…";
  ta.addEventListener("input", ()=>{
    setProgress(q.id, {text: ta.value});
  });

  const saved=getProgress(q.id);
  if(saved?.text) ta.value=saved.text;

  const btnRow=document.createElement("div");
  btnRow.className="row";
  btnRow.style.marginTop="10px";
  btnRow.innerHTML = `
    <button class="btn secondary" onclick="toggleExplain('${q.id}')">Show marking points</button>
    <button class="btn secondary" onclick="clearText('${q.id}')">Clear</button>
  `;

  const explain=document.createElement("div");
  explain.className="explain hidden";
  explain.id=`explain-${q.id}`;
  explain.textContent=q.explanation || "";

  box.appendChild(ta);
  box.appendChild(btnRow);
  box.appendChild(explain);

  return box;
}

function renderLAQ(q, n){
  const box=document.createElement("div");
  box.className="qbox";
  box.dataset.qid=q.id;

  box.appendChild(renderMeta(q));

  const p=document.createElement("p");
  p.className="qstem";
  p.innerHTML = `<b>LAQ${n}.</b> ${q.stem}`;
  box.appendChild(p);

  const ta=document.createElement("textarea");
  ta.style.width="100%";
  ta.style.minHeight="200px";
  ta.style.borderRadius="14px";
  ta.style.padding="12px";
  ta.style.border="1px solid rgba(255,255,255,.12)";
  ta.style.background="rgba(0,0,0,.15)";
  ta.style.color="var(--text)";
  ta.placeholder="Write a structured plan (priorities → assessment → differentials → management → rural escalation)…";
  ta.addEventListener("input", ()=>{
    setProgress(q.id, {text: ta.value});
  });

  const saved=getProgress(q.id);
  if(saved?.text) ta.value=saved.text;

  const btnRow=document.createElement("div");
  btnRow.className="row";
  btnRow.style.marginTop="10px";
  btnRow.innerHTML = `
    <button class="btn secondary" onclick="toggleExplain('${q.id}')">Show marking points</button>
    <button class="btn secondary" onclick="clearText('${q.id}')">Clear</button>
  `;

  const explain=document.createElement("div");
  explain.className="explain hidden";
  explain.id=`explain-${q.id}`;
  explain.textContent=q.explanation || "";

  box.appendChild(ta);
  box.appendChild(btnRow);
  box.appendChild(explain);

  return box;
}

function toggleExplain(qid){
  const el = document.getElementById(`explain-${qid}`);
  if(!el) return;
  el.classList.toggle("hidden");
}

function clearText(qid){
  setProgress(qid, null);
  const box=document.querySelector(`[data-qid="${qid}"]`);
  const ta=box?.querySelector("textarea");
  if(ta) ta.value="";
  document.getElementById(`explain-${qid}`)?.classList.add("hidden");
}

// =========================
// localStorage progress
// =========================
const STORE_KEY="acrrm_studyhub_progress_v1";

function loadStore(){
  try{ return JSON.parse(localStorage.getItem(STORE_KEY) || "{}"); }
  catch{ return {}; }
}
function saveStore(obj){
  localStorage.setItem(STORE_KEY, JSON.stringify(obj));
}
function setProgress(qid, value){
  const s=loadStore();
  if(value===null) delete s[qid];
  else s[qid]=value;
  saveStore(s);
}
function getProgress(qid){
  const s=loadStore();
  return s[qid];
}
function resetProgress(){
  localStorage.removeItem(STORE_KEY);
  alert("Progress cleared.");
  // re-render current visible page content if needed
}

// default: jump to Home
go("home");
</script>

</body>
</html>
