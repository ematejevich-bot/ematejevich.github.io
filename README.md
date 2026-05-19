Ej website final v5 · HTML
Copy

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>EJ Matejevich</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.44.0/tabler-icons.min.css">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --red:#8B1A1A;--red2:#a82020;--red-pale:#fdf0f0;
  --cream:#faf8f5;--text:#1a1a1a;--muted:#666;
  --border:rgba(139,26,26,0.15);
}
html{scroll-behavior:smooth}
body{font-family:'DM Sans',sans-serif;color:var(--text);background:var(--cream);min-height:100vh}
 
nav{display:flex;align-items:center;justify-content:space-between;padding:0 2.5rem;height:64px;background:var(--red);position:sticky;top:0;z-index:100}
.nav-brand{font-family:'Playfair Display',serif;color:#fff;font-size:19px;font-weight:700}
.nav-links{display:flex;gap:2px}
.nav-links button{background:none;border:none;color:rgba(255,255,255,0.72);font-family:'DM Sans',sans-serif;font-size:13px;padding:7px 15px;border-radius:5px;cursor:pointer;transition:all 0.2s}
.nav-links button:hover{color:#fff;background:rgba(255,255,255,0.12)}
.nav-links button.active{color:#fff;background:rgba(255,255,255,0.22);font-weight:500}
 
.page{display:none;padding:3rem 2.5rem 5rem;max-width:880px;margin:0 auto;animation:fadeIn 0.35s ease}
.page.active{display:block}
@keyframes fadeIn{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}
 
.section-label{font-size:10px;font-weight:500;letter-spacing:3px;text-transform:uppercase;color:var(--red);margin-bottom:1.5rem;padding-bottom:0.7rem;border-bottom:1.5px solid var(--red);display:inline-block}
 
/* ── ABOUT ── */
.hero{display:grid;grid-template-columns:1fr 210px;gap:3rem;align-items:center;padding-bottom:3rem;border-bottom:1px solid var(--border);margin-bottom:3rem}
.hero-eyebrow{font-size:10px;font-weight:500;letter-spacing:3px;text-transform:uppercase;color:var(--red);margin-bottom:0.9rem}
.hero h1{font-family:'Playfair Display',serif;font-size:46px;font-weight:900;color:var(--text);line-height:1.1;margin-bottom:0.5rem}
.hero-tagline{font-size:13px;color:var(--muted);font-weight:300;margin-bottom:1.5rem}
.hero-bio{font-size:14px;color:#444;line-height:1.85;font-weight:300}
.hero-photo{width:210px;height:250px;object-fit:cover;object-position:top;border-radius:12px;border:3px solid #fff;box-shadow:0 8px 32px rgba(139,26,26,0.18)}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.25rem;margin-top:2rem}
.about-card{background:#fff;border:0.5px solid var(--border);border-radius:12px;padding:1.5rem}
.about-card h3{font-size:10px;font-weight:500;letter-spacing:2.5px;text-transform:uppercase;color:var(--red);margin-bottom:0.75rem}
.about-card p{font-size:14px;line-height:1.8;color:#444;font-weight:300}
.about-card.full{grid-column:1/-1}
 
/* ── RESUME ── */
.resume-header{background:var(--red);border-radius:14px;padding:2.5rem 2.5rem 2rem;margin-bottom:2.5rem;position:relative;overflow:hidden}
.resume-header::before{content:'';position:absolute;top:-40px;right:-40px;width:180px;height:180px;border-radius:50%;background:rgba(255,255,255,0.06)}
.resume-header::after{content:'';position:absolute;bottom:-60px;left:40%;width:220px;height:220px;border-radius:50%;background:rgba(255,255,255,0.04)}
.rh-eyebrow{font-size:10px;letter-spacing:3px;text-transform:uppercase;color:rgba(255,255,255,0.6);margin-bottom:0.5rem}
.rh-name{font-family:'Playfair Display',serif;font-size:36px;font-weight:900;color:#fff;margin-bottom:0.25rem}
.rh-sub{font-size:13px;color:rgba(255,255,255,0.7);font-weight:300;margin-bottom:1.5rem}
.rh-tags{display:flex;flex-wrap:wrap;gap:8px}
.rh-tag{background:rgba(255,255,255,0.14);border:0.5px solid rgba(255,255,255,0.25);border-radius:20px;padding:4px 14px;font-size:12px;color:rgba(255,255,255,0.9)}
.resume-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.25rem;margin-bottom:2rem}
.stat-card{background:#fff;border:0.5px solid var(--border);border-radius:12px;padding:1.5rem;position:relative;overflow:hidden}
.stat-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:var(--red);border-radius:12px 12px 0 0}
.stat-num{font-family:'Playfair Display',serif;font-size:40px;font-weight:900;color:var(--red);line-height:1;margin-bottom:4px}
.stat-label{font-size:12px;color:var(--muted);font-weight:400}
.resume-section-title{font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--text);margin:2rem 0 1.25rem;display:flex;align-items:center;gap:0.75rem}
.resume-section-title::after{content:'';flex:1;height:0.5px;background:var(--border)}
.timeline{position:relative;padding-left:24px}
.timeline::before{content:'';position:absolute;left:6px;top:6px;bottom:0;width:1px;background:var(--border)}
.tl-item{position:relative;margin-bottom:1.75rem}
.tl-dot{position:absolute;left:-24px;top:4px;width:13px;height:13px;border-radius:50%;background:#fff;border:2px solid var(--red)}
.tl-date{font-size:11px;color:var(--red);font-weight:500;letter-spacing:0.5px;margin-bottom:2px}
.tl-title{font-size:15px;font-weight:500;color:var(--text);margin-bottom:2px}
.tl-sub{font-size:13px;color:var(--muted);font-style:italic;margin-bottom:6px}
.tl-body{font-size:13px;color:#555;line-height:1.7;font-weight:300}
.ach-grid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;margin-top:0.5rem}
.ach-card{background:#fff;border:0.5px solid var(--border);border-radius:12px;padding:1.25rem;display:flex;gap:1rem;align-items:flex-start}
.ach-icon{width:38px;height:38px;border-radius:10px;background:var(--red-pale);display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:18px;color:var(--red)}
.ach-title{font-size:13px;font-weight:500;color:var(--text);margin-bottom:3px}
.ach-text{font-size:13px;color:#444;line-height:1.65;font-weight:300}
 
/* ── ACTIVITIES (spiced) ── */
.act-hero{
  background:var(--red);border-radius:14px;
  padding:2rem 2.5rem;margin-bottom:2.5rem;
  display:flex;align-items:center;gap:1.5rem;
}
.act-hero-icon{font-size:42px;color:rgba(255,255,255,0.25)}
.act-hero h2{font-family:'Playfair Display',serif;font-size:28px;font-weight:900;color:#fff;margin-bottom:4px}
.act-hero p{font-size:13px;color:rgba(255,255,255,0.7);font-weight:300}
 
.act-card{
  background:#fff;border:0.5px solid var(--border);
  border-radius:14px;margin-bottom:1.5rem;
  overflow:hidden;transition:box-shadow 0.2s;
}
.act-card:hover{box-shadow:0 6px 28px rgba(139,26,26,0.1)}
.act-card-header{
  display:flex;align-items:center;gap:1rem;
  padding:1.25rem 1.5rem;
  border-bottom:0.5px solid var(--border);
  background:var(--red-pale);
}
.act-card-logo{
  width:52px;height:52px;border-radius:10px;
  background:#fff;border:0.5px solid var(--border);
  display:flex;align-items:center;justify-content:center;
  flex-shrink:0;overflow:hidden;
}
.act-card-logo img{width:100%;height:100%;object-fit:contain;padding:5px}
.act-card-logo i{font-size:24px;color:var(--red)}
.act-card-meta{font-size:11px;color:var(--red);font-weight:500;letter-spacing:0.5px;margin-bottom:2px}
.act-card-title{font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--text)}
.act-card-sub{font-size:12px;color:var(--muted);font-style:italic}
.act-card-body{padding:1.25rem 1.5rem}
.act-card-body ul{list-style:none;padding:0}
.act-card-body ul li{
  font-size:14px;color:#444;line-height:1.75;
  padding:5px 0 5px 22px;position:relative;font-weight:300;
}
.act-card-body ul li::before{
  content:'';position:absolute;left:0;top:14px;
  width:7px;height:7px;border-radius:50%;
  background:var(--red);opacity:0.45;
}
.act-photo{width:100%;max-height:300px;object-fit:cover;object-position:center top;display:block}
.act-photo-caption{padding:0.6rem 1.5rem;font-size:12px;color:var(--muted);font-style:italic;border-top:0.5px solid var(--border);background:var(--red-pale)}
 
/* ── SKILLS (spiced) ── */
.skills-hero{
  background:var(--red);border-radius:14px;
  padding:2rem 2.5rem;margin-bottom:2.5rem;
}
.skills-hero h2{font-family:'Playfair Display',serif;font-size:28px;font-weight:900;color:#fff;margin-bottom:4px}
.skills-hero p{font-size:13px;color:rgba(255,255,255,0.7);font-weight:300}
.skills-cols{display:grid;grid-template-columns:1fr 1fr;gap:1.25rem;margin-bottom:1.5rem}
.skill-block{background:#fff;border:0.5px solid var(--border);border-radius:14px;overflow:hidden;margin-bottom:0}
.skill-block-header{
  display:flex;align-items:center;gap:0.75rem;
  padding:1rem 1.5rem;background:var(--red-pale);
  border-bottom:0.5px solid var(--border);
  font-size:13px;font-weight:500;color:var(--red);
}
.skill-block-header i{font-size:18px}
.skill-block-body{padding:1rem 1.5rem}
.skill-item{display:flex;align-items:flex-start;gap:0.75rem;padding:0.55rem 0;border-bottom:0.5px solid rgba(139,26,26,0.07)}
.skill-item:last-child{border-bottom:none}
.skill-dot{width:30px;height:30px;border-radius:8px;background:var(--red-pale);display:flex;align-items:center;justify-content:center;flex-shrink:0;color:var(--red);font-size:15px}
.skill-item-text{font-size:13px;color:#444;line-height:1.65;font-weight:300;padding-top:5px}
 
/* ── PROFICIENCY BARS – scroll-triggered pop-out ── */
.bar-item{
  /* entrance state: invisible, shifted down, slightly scaled */
  opacity: 0;
  transform: translateY(22px) scale(0.97);
  transition:
    opacity 0.55s cubic-bezier(.22,.68,0,1.2),
    transform 0.55s cubic-bezier(.22,.68,0,1.2),
    box-shadow 0.3s ease;
  background:#fff;
  border:0.5px solid var(--border);
  border-radius:12px;
  padding:1rem 1.25rem;
  box-shadow: 0 2px 8px rgba(139,26,26,0.04);
}
.bar-item.bar-visible{
  opacity:1;
  transform:translateY(0) scale(1);
  box-shadow: 0 6px 24px rgba(139,26,26,0.10);
}
.bar-item:hover{
  transform: translateY(-3px) scale(1.015);
  box-shadow: 0 10px 32px rgba(139,26,26,0.15);
}
 
.bar-label{
  display:flex;justify-content:space-between;align-items:baseline;
  font-size:13px;font-weight:500;color:var(--text);
  margin-bottom:0.6rem;
}
.bar-label span{
  font-size:11px;font-weight:500;letter-spacing:0.5px;
  text-transform:uppercase;color:var(--red);
  background:var(--red-pale);
  padding:2px 9px;border-radius:20px;
}
.bar-track{
  height:9px;background:rgba(139,26,26,0.08);
  border-radius:99px;overflow:hidden;
}
.bar-fill{
  height:100%;
  background: linear-gradient(90deg, var(--red) 0%, #c94444 100%);
  border-radius:99px;
  /* start at 0, animate to real width when .bar-animated is added */
  width: 0 !important;
  transition: width 1.1s cubic-bezier(.4,0,.2,1) 0.15s;
  position:relative;
}
.bar-fill::after{
  content:'';
  position:absolute;top:0;left:0;right:0;bottom:0;
  background:linear-gradient(90deg,transparent 0%,rgba(255,255,255,0.3) 50%,transparent 100%);
  border-radius:99px;
}
.bar-item.bar-animated .bar-fill{
  /* restore the real width set inline on the element */
  width: var(--bar-target) !important;
}
 
/* ── CONTACT ── */
.contact-row{
  display:flex;align-items:center;gap:1rem;
  font-size:15px;color:#444;padding:1rem 0;
  border-bottom:0.5px solid var(--border);font-weight:300;
}
.contact-row i{font-size:20px;color:var(--red);width:24px;flex-shrink:0}
</style>
</head>
<body>
 
<nav>
  <div class="nav-brand">EJ Matejevich</div>
  <div class="nav-links">
    <button onclick="show('about')" class="active">About</button>
    <button onclick="show('resume')">Resume</button>
    <button onclick="show('activities')">Activities</button>
    <button onclick="show('skills')">Skills</button>
    <button onclick="show('contact')">Contact</button>
  </div>
</nav>
 
<!-- ABOUT -->
<div id="about" class="page active">
  <div class="hero">
    <div>
      <div class="hero-eyebrow">Portfolio</div>
      <h1>EJ Matejevich</h1>
      <div class="hero-tagline">Student · Entrepreneur · Competitor</div>
      <p class="hero-bio">A driven high school student at The Browning School in New York City with a passion for finance, entrepreneurship, and competitive athletics. I bring energy and commitment to everything I pursue — from Mock Trial courtrooms to the lacrosse field to the trading floor at SIFMA.</p>
    </div>
    <img class="hero-photo" src="https://placehold.co/210x250/8B1A1A/white?text=EJ" alt="EJ Matejevich">
  </div>
  <div class="about-grid">
    <div class="about-card">
      <h3>Education</h3>
      <p>The Browning School, New York City<br>Expected Graduation: 2027<br>Focus: Finance, Law &amp; Entrepreneurship</p>
    </div>
    <div class="about-card">
      <h3>Location</h3>
      <p>New York City, NY<br>Available for internships &amp; opportunities in the NYC metro area</p>
    </div>
    <div class="about-card full">
      <h3>What Drives Me</h3>
      <p>I'm passionate about understanding how markets work, how businesses are built, and how arguments are won. Whether I'm competing in Mock Trial, studying stocks through SIFMA, or building FocusQuest through UPenn's SIP program, I look for opportunities that sharpen my thinking and expand my capabilities.</p>
    </div>
  </div>
</div>
 
<!-- RESUME -->
<div id="resume" class="page">
  <div class="resume-header">
    <div class="rh-eyebrow">Curriculum Vitae</div>
    <div class="rh-name">EJ Matejevich</div>
    <div class="rh-sub">The Browning School · New York City</div>
    <div class="rh-tags">
      <span class="rh-tag">Finance</span>
      <span class="rh-tag">Mock Trial</span>
      <span class="rh-tag">Lacrosse</span>
      <span class="rh-tag">Entrepreneurship</span>
      <span class="rh-tag">Model UN</span>
    </div>
  </div>
 
  <div class="resume-grid">
    <div class="stat-card"><div class="stat-num">4+</div><div class="stat-label">Years at Browning</div></div>
    <div class="stat-card"><div class="stat-num">3</div><div class="stat-label">Competitive Programs</div></div>
  </div>
 
  <div class="resume-section-title">Education</div>
  <div class="timeline">
    <div class="tl-item">
      <div class="tl-dot"></div>
      <div class="tl-date">2021 – Present</div>
      <div class="tl-title">The Browning School</div>
      <div class="tl-sub">New York City, NY · Expected Graduation 2027</div>
      <div class="tl-body">College-preparatory curriculum with emphasis on critical thinking, writing, and leadership. Active in extracurricular programs across law, finance, and athletics.</div>
    </div>
  </div>
 
  <div class="resume-section-title">Experience &amp; Programs</div>
  <div class="timeline">
    <div class="tl-item">
      <div class="tl-dot"></div>
      <div class="tl-date">2024</div>
      <div class="tl-title">UPenn Summer Intensive Program (SIP)</div>
      <div class="tl-sub">Entrepreneurship &amp; App Development</div>
      <div class="tl-body">Built FocusQuest, a fully functional productivity app, from concept to completion. Gained hands-on experience in product development, user experience design, and entrepreneurial thinking.</div>
    </div>
    <div class="tl-item">
      <div class="tl-dot"></div>
      <div class="tl-date">Ongoing</div>
      <div class="tl-title">SIFMA Foundation – Stock Market Game</div>
      <div class="tl-sub">Finance &amp; Investment Education</div>
      <div class="tl-body">Competing in the national stock market simulation, managing a virtual portfolio and applying real-world investment strategies. Developing financial literacy and market analysis skills.</div>
    </div>
    <div class="tl-item">
      <div class="tl-dot"></div>
      <div class="tl-date">Ongoing</div>
      <div class="tl-title">Mock Trial – The Browning School</div>
      <div class="tl-sub">Legal Advocacy &amp; Public Speaking</div>
      <div class="tl-body">Competing in interscholastic mock trial tournaments. Roles include opening statements, witness examination, and closing arguments. Building skills in persuasion, legal reasoning, and performance under pressure.</div>
    </div>
  </div>
 
  <div class="resume-section-title">Achievements</div>
  <div class="ach-grid">
    <div class="ach-card">
      <div class="ach-icon"><i class="ti ti-trophy"></i></div>
      <div><div class="ach-title">UPenn SIP – FocusQuest App</div><div class="ach-text">Built and launched a fully functional app through Penn's competitive summer program</div></div>
    </div>
    <div class="ach-card">
      <div class="ach-icon"><i class="ti ti-chart-line"></i></div>
      <div><div class="ach-title">SIFMA Stock Market Game</div><div class="ach-text">Actively competing in national finance simulation with real investment strategy</div></div>
    </div>
    <div class="ach-card">
      <div class="ach-icon"><i class="ti ti-gavel"></i></div>
      <div><div class="ach-title">Mock Trial Competitor</div><div class="ach-text">Representing Browning in interscholastic legal competitions across NYC</div></div>
    </div>
    <div class="ach-card">
      <div class="ach-icon"><i class="ti ti-ball-football"></i></div>
      <div><div class="ach-title">Varsity Lacrosse</div><div class="ach-text">Multi-year varsity athlete demonstrating discipline and teamwork</div></div>
    </div>
  </div>
</div>
 
<!-- ACTIVITIES -->
<div id="activities" class="page">
  <div class="act-hero">
    <i class="ti ti-star act-hero-icon"></i>
    <div>
      <h2>Activities &amp; Involvement</h2>
      <p>Competing, building, and leading across academics, athletics, and entrepreneurship</p>
    </div>
  </div>
 
  <div class="act-card">
    <div class="act-card-header">
      <div class="act-card-logo"><i class="ti ti-gavel"></i></div>
      <div>
        <div class="act-card-meta">The Browning School · Ongoing</div>
        <div class="act-card-title">Mock Trial</div>
        <div class="act-card-sub">Competitor &amp; Advocate</div>
      </div>
    </div>
    <div class="act-card-body"><ul>
      <li>Competing in interscholastic mock trial tournaments representing The Browning School</li>
      <li>Delivering opening statements, conducting witness examinations, and presenting closing arguments</li>
      <li>Developing skills in legal reasoning, persuasive speaking, and quick thinking under pressure</li>
      <li>Collaborating with teammates to build case strategy and prepare for opposing arguments</li>
    </ul></div>
  </div>
 
  <div class="act-card">
    <div class="act-card-header">
      <div class="act-card-logo"><i class="ti ti-chart-line"></i></div>
      <div>
        <div class="act-card-meta">SIFMA Foundation · Ongoing</div>
        <div class="act-card-title">Stock Market Game</div>
        <div class="act-card-sub">Investor &amp; Analyst</div>
      </div>
    </div>
    <div class="act-card-body"><ul>
      <li>Competing in the SIFMA Foundation's national stock market simulation program</li>
      <li>Managing a virtual investment portfolio using real-world market data and financial analysis</li>
      <li>Researching companies, tracking market trends, and making strategic buy/sell decisions</li>
      <li>Building foundational knowledge in equities, risk management, and portfolio diversification</li>
    </ul></div>
  </div>
 
  <div class="act-card">
    <div class="act-card-header">
      <div class="act-card-logo"><i class="ti ti-device-mobile"></i></div>
      <div>
        <div class="act-card-meta">University of Pennsylvania · Summer 2024</div>
        <div class="act-card-title">SIP Program – FocusQuest App</div>
        <div class="act-card-sub">Founder &amp; Developer</div>
      </div>
    </div>
    <div class="act-card-body"><ul>
      <li>Selected for UPenn's competitive Summer Intensive Program focused on entrepreneurship and technology</li>
      <li>Conceptualized, designed, and built FocusQuest — a fully functional productivity app from scratch</li>
      <li>Gained hands-on experience in product development, user interface design, and app architecture</li>
      <li>Presented the final product to program faculty and peers, receiving strong feedback on execution</li>
    </ul></div>
  </div>
 
  <div class="act-card">
    <div class="act-card-header">
      <div class="act-card-logo"><i class="ti ti-ball-football"></i></div>
      <div>
        <div class="act-card-meta">The Browning School · Ongoing</div>
        <div class="act-card-title">Varsity Lacrosse</div>
        <div class="act-card-sub">Athlete</div>
      </div>
    </div>
    <div class="act-card-body"><ul>
      <li>Competing at the varsity level, demonstrating consistent commitment and athletic development</li>
      <li>Building leadership, resilience, and teamwork through high-intensity competitive play</li>
      <li>Balancing rigorous athletic schedule alongside academic and extracurricular commitments</li>
    </ul></div>
  </div>
 
  <div class="act-card">
    <div class="act-card-header">
      <div class="act-card-logo"><i class="ti ti-world"></i></div>
      <div>
        <div class="act-card-meta">The Browning School · Ongoing</div>
        <div class="act-card-title">Model United Nations &amp; Debate</div>
        <div class="act-card-sub">Competitor</div>
      </div>
    </div>
    <div class="act-card-body"><ul>
      <li>Actively involved in Model UN, working toward awards in competitive conferences</li>
      <li>Participating in debate tournaments, developing argumentation and critical thinking under pressure</li>
    </ul></div>
  </div>
</div>
 
<!-- SKILLS -->
<div id="skills" class="page">
  <div class="skills-hero">
    <h2>Skills &amp; Strengths</h2>
    <p>A blend of technical ability, academic rigor, and real-world competition experience</p>
  </div>
 
  <div class="skills-cols">
    <div class="skill-block">
      <div class="skill-block-header">
        <i class="ti ti-code" aria-hidden="true"></i>
        <span>Technical Skills</span>
      </div>
      <div class="skill-block-body">
        <div class="skill-item">
          <div class="skill-dot"><i class="ti ti-terminal-2" aria-hidden="true"></i></div>
          <div class="skill-item-text">Learning programming and web development fundamentals — building a foundation in coding logic and site structure</div>
        </div>
        <div class="skill-item">
          <div class="skill-dot"><i class="ti ti-layout" aria-hidden="true"></i></div>
          <div class="skill-item-text">Familiar with digital design and productivity tools — Google Workspace, document editors, and basic design software</div>
        </div>
        <div class="skill-item">
          <div class="skill-dot"><i class="ti ti-device-mobile" aria-hidden="true"></i></div>
          <div class="skill-item-text">Built FocusQuest, a fully functional app, through the UPenn SIP Program</div>
        </div>
      </div>
    </div>
 
    <div class="skill-block">
      <div class="skill-block-header">
        <i class="ti ti-book" aria-hidden="true"></i>
        <span>Academic Skills</span>
      </div>
      <div class="skill-block-body">
        <div class="skill-item">
          <div class="skill-dot"><i class="ti ti-file-text" aria-hidden="true"></i></div>
          <div class="skill-item-text">Strong reading comprehension — analyzes complex texts, identifies key arguments, and synthesizes across multiple sources</div>
        </div>
        <div class="skill-item">
          <div class="skill-dot"><i class="ti ti-pencil" aria-hidden="true"></i></div>
          <div class="skill-item-text">Strong written communication — clear, well-organized essays across varied subjects and formats</div>
        </div>
        <div class="skill-item">
          <div class="skill-dot"><i class="ti ti-microphone" aria-hidden="true"></i></div>
          <div class="skill-item-text">Developing public speaking through Mock Trial — argument delivery, cross-examination, and persuasive presentation under pressure</div>
        </div>
        <div class="skill-item">
          <div class="skill-dot"><i class="ti ti-search" aria-hidden="true"></i></div>
          <div class="skill-item-text">Sharpened critical thinking through Mock Trial — case analysis, evidence evaluation, and logical argumentation in legal frameworks</div>
        </div>
      </div>
    </div>
  </div>
 
  <div class="skill-block" style="margin-bottom:1.5rem">
    <div class="skill-block-header">
      <i class="ti ti-chart-bar" aria-hidden="true"></i>
      <span>Proficiency Overview</span>
    </div>
    <div class="skill-bars-body" id="proficiency-grid" style="padding:1.5rem;display:grid;grid-template-columns:1fr 1fr;gap:1.25rem 2rem;">
      <div class="bar-item" data-width="88%"><div class="bar-label">Research &amp; Analysis <span>Advanced</span></div><div class="bar-track"><div class="bar-fill" style="--bar-target:88%"></div></div></div>
      <div class="bar-item" data-width="85%"><div class="bar-label">Written Communication <span>Advanced</span></div><div class="bar-track"><div class="bar-fill" style="--bar-target:85%"></div></div></div>
      <div class="bar-item" data-width="68%"><div class="bar-label">Public Speaking <span>Developing</span></div><div class="bar-track"><div class="bar-fill" style="--bar-target:68%"></div></div></div>
      <div class="bar-item" data-width="80%"><div class="bar-label">Time Management <span>Strong</span></div><div class="bar-track"><div class="bar-fill" style="--bar-target:80%"></div></div></div>
      <div class="bar-item" data-width="65%"><div class="bar-label">Financial Literacy <span>Developing</span></div><div class="bar-track"><div class="bar-fill" style="--bar-target:65%"></div></div></div>
      <div class="bar-item" data-width="40%"><div class="bar-label">Web Development <span>Learning</span></div><div class="bar-track"><div class="bar-fill" style="--bar-target:40%"></div></div></div>
    </div>
  </div>
 
  <div class="skill-block">
    <div class="skill-block-header">
      <i class="ti ti-star" aria-hidden="true"></i>
      <span>Leadership &amp; Soft Skills</span>
    </div>
    <div class="skill-block-body" style="display:grid;grid-template-columns:1fr 1fr;gap:0 1rem;">
      <div class="skill-item"><div class="skill-dot"><i class="ti ti-users" aria-hidden="true"></i></div><div class="skill-item-text">Teamwork &amp; collaboration</div></div>
      <div class="skill-item"><div class="skill-dot"><i class="ti ti-target" aria-hidden="true"></i></div><div class="skill-item-text">Goal setting &amp; self-improvement</div></div>
      <div class="skill-item"><div class="skill-dot"><i class="ti ti-clock" aria-hidden="true"></i></div><div class="skill-item-text">Time management under pressure</div></div>
      <div class="skill-item"><div class="skill-dot"><i class="ti ti-brain" aria-hidden="true"></i></div><div class="skill-item-text">Critical &amp; analytical thinking</div></div>
      <div class="skill-item"><div class="skill-dot"><i class="ti ti-bulb" aria-hidden="true"></i></div><div class="skill-item-text">Entrepreneurial mindset</div></div>
      <div class="skill-item"><div class="skill-dot"><i class="ti ti-adjustments" aria-hidden="true"></i></div><div class="skill-item-text">Adaptability &amp; problem solving</div></div>
    </div>
  </div>
</div>
 
<!-- CONTACT -->
<div id="contact" class="page">
  <span class="section-label">Contact</span>
  <div style="font-family:'Playfair Display',serif;font-size:30px;font-weight:700;margin-bottom:2rem;color:var(--text)">Get in Touch</div>
  <div class="contact-row"><i class="ti ti-phone" aria-hidden="true"></i> (917) 494-6038</div>
  <div class="contact-row"><i class="ti ti-mail" aria-hidden="true"></i> ematejevich@browning.edu</div>
  <div class="contact-row"><i class="ti ti-map-pin" aria-hidden="true"></i> New York City, NY</div>
  <div class="contact-row"><i class="ti ti-school" aria-hidden="true"></i> The Browning School</div>
</div>
 
<script>
/* ── Page navigation ── */
function show(id){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.nav-links button').forEach(b=>b.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  const labels={about:'About',resume:'Resume',activities:'Activities',skills:'Skills',contact:'Contact'};
  document.querySelectorAll('.nav-links button').forEach(b=>{
    if(b.textContent.trim()===labels[id]) b.classList.add('active');
  });
  // If switching to skills page, trigger bar animations after a short delay
  if(id === 'skills'){
    setTimeout(triggerBarAnimations, 80);
  }
}
 
/* ── Proficiency bar scroll + pop-out animation ── */
function triggerBarAnimations(){
  const bars = document.querySelectorAll('#skills .bar-item');
  if(!bars.length) return;
 
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if(entry.isIntersecting){
        const el = entry.target;
        const idx = Array.from(bars).indexOf(el);
        // stagger each card by 80ms
        setTimeout(() => {
          el.classList.add('bar-visible');
          // slight additional delay before the bar fill animates
          setTimeout(() => {
            el.classList.add('bar-animated');
          }, 120);
        }, idx * 90);
        observer.unobserve(el);
      }
    });
  }, { threshold: 0.2 });
 
  bars.forEach(bar => observer.observe(bar));
}
 
// Also trigger if skills page is already active on load
if(document.getElementById('skills').classList.contains('active')){
  setTimeout(triggerBarAnimations, 200);
}
</script>
</body>
</html>
 
