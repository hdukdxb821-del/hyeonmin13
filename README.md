# hyeonmin13[index.html](https://github.com/user-attachments/files/29195187/index.html)
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>현민 | Game QA Engineer</title>
<style>
  :root {
    --neon-cyan: #00f5ff;
    --neon-pink: #ff006e;
    --neon-purple: #8b00ff;
    --neon-green: #39ff14;
    --bg-dark: #050510;
    --bg-card: #0a0a1a;
    --bg-card2: #0d0d20;
    --text-main: #e0e0ff;
    --text-muted: #7070a0;
    --border-neon: rgba(0, 245, 255, 0.3);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg-dark);
    color: var(--text-main);
    font-family: 'Segoe UI', 'Noto Sans KR', sans-serif;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* Scanline overlay */
  body::before {
    content: '';
    position: fixed;
    top: 0; left: 0; right: 0; bottom: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.08) 2px,
      rgba(0,0,0,0.08) 4px
    );
    pointer-events: none;
    z-index: 999;
  }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    padding: 1rem 2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: rgba(5, 5, 16, 0.85);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid var(--border-neon);
    z-index: 100;
  }

  .logo {
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--neon-cyan);
    letter-spacing: 2px;
    text-shadow: 0 0 10px var(--neon-cyan);
  }

  nav ul {
    display: flex;
    gap: 2rem;
    list-style: none;
  }

  nav a {
    color: var(--text-muted);
    text-decoration: none;
    font-size: 0.85rem;
    letter-spacing: 1px;
    text-transform: uppercase;
    transition: color 0.3s;
  }

  nav a:hover { color: var(--neon-cyan); text-shadow: 0 0 8px var(--neon-cyan); }

  /* HERO */
  #hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 6rem 2rem 3rem;
    position: relative;
    text-align: center;
  }

  .hero-grid {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,245,255,0.05) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,245,255,0.05) 1px, transparent 1px);
    background-size: 50px 50px;
  }

  .hero-content { position: relative; z-index: 1; }

  .hero-badge {
    display: inline-block;
    border: 1px solid var(--neon-pink);
    color: var(--neon-pink);
    font-size: 0.75rem;
    letter-spacing: 3px;
    padding: 0.4rem 1.2rem;
    text-transform: uppercase;
    margin-bottom: 1.5rem;
    box-shadow: 0 0 12px rgba(255,0,110,0.3), inset 0 0 12px rgba(255,0,110,0.05);
  }

  h1 {
    font-size: clamp(2.5rem, 8vw, 5rem);
    font-weight: 700;
    line-height: 1.1;
    margin-bottom: 0.5rem;
    color: #fff;
  }

  .neon-text {
    color: var(--neon-cyan);
    text-shadow: 0 0 20px var(--neon-cyan), 0 0 40px rgba(0,245,255,0.4);
  }

  .hero-sub {
    font-size: 1.1rem;
    color: var(--text-muted);
    margin: 1rem 0 2rem;
    max-width: 500px;
    margin-left: auto;
    margin-right: auto;
  }

  .hero-btns {
    display: flex;
    gap: 1rem;
    justify-content: center;
    flex-wrap: wrap;
  }

  .btn {
    padding: 0.75rem 2rem;
    font-size: 0.9rem;
    letter-spacing: 1px;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.3s;
    display: inline-block;
  }

  .btn-primary {
    background: var(--neon-cyan);
    color: #000;
    font-weight: 700;
    border: none;
    box-shadow: 0 0 20px rgba(0,245,255,0.5);
  }

  .btn-primary:hover {
    background: #fff;
    box-shadow: 0 0 30px rgba(0,245,255,0.8);
    transform: translateY(-2px);
  }

  .btn-outline {
    background: transparent;
    color: var(--neon-cyan);
    border: 1px solid var(--neon-cyan);
  }

  .btn-outline:hover {
    background: rgba(0,245,255,0.1);
    box-shadow: 0 0 20px rgba(0,245,255,0.3);
    transform: translateY(-2px);
  }

  /* SECTIONS */
  section {
    padding: 5rem 2rem;
    max-width: 1000px;
    margin: 0 auto;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin-bottom: 3rem;
  }

  .section-num {
    font-size: 0.75rem;
    color: var(--neon-pink);
    letter-spacing: 2px;
  }

  h2 {
    font-size: 1.8rem;
    font-weight: 700;
    color: #fff;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: linear-gradient(90deg, var(--border-neon), transparent);
  }

  /* ABOUT */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    align-items: center;
  }

  .about-text p {
    color: var(--text-muted);
    margin-bottom: 1rem;
    font-size: 0.95rem;
  }

  .about-text p span {
    color: var(--neon-cyan);
  }

  .about-stats {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }

  .stat-card {
    background: var(--bg-card);
    border: 1px solid var(--border-neon);
    padding: 1.2rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .stat-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: var(--neon-cyan);
    box-shadow: 0 0 8px var(--neon-cyan);
  }

  .stat-num {
    font-size: 2rem;
    font-weight: 700;
    color: var(--neon-cyan);
    text-shadow: 0 0 12px var(--neon-cyan);
    display: block;
  }

  .stat-label {
    font-size: 0.75rem;
    color: var(--text-muted);
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  /* SKILLS */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
  }

  .skill-category {
    background: var(--bg-card);
    border: 1px solid var(--border-neon);
    padding: 1.5rem;
    position: relative;
  }

  .skill-category-title {
    font-size: 0.8rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--neon-pink);
    margin-bottom: 1.2rem;
  }

  .skill-list {
    display: flex;
    flex-wrap: wrap;
    gap: 0.6rem;
  }

  .skill-tag {
    background: rgba(0,245,255,0.07);
    border: 1px solid rgba(0,245,255,0.25);
    color: var(--neon-cyan);
    font-size: 0.78rem;
    padding: 0.3rem 0.8rem;
    letter-spacing: 0.5px;
    transition: all 0.2s;
  }

  .skill-tag:hover {
    background: rgba(0,245,255,0.15);
    border-color: var(--neon-cyan);
    box-shadow: 0 0 10px rgba(0,245,255,0.2);
  }

  .skill-bar-wrap {
    margin-top: 1rem;
  }

  .skill-bar-row {
    margin-bottom: 0.8rem;
  }

  .skill-bar-label {
    display: flex;
    justify-content: space-between;
    font-size: 0.78rem;
    color: var(--text-muted);
    margin-bottom: 0.3rem;
  }

  .skill-bar-bg {
    height: 4px;
    background: rgba(255,255,255,0.07);
    position: relative;
  }

  .skill-bar-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--neon-cyan), var(--neon-purple));
    box-shadow: 0 0 6px var(--neon-cyan);
    transition: width 1.2s ease;
    width: 0;
  }

  /* PROJECTS */
  .projects-list {
    display: grid;
    gap: 1.5rem;
  }

  .project-card {
    background: var(--bg-card);
    border: 1px solid var(--border-neon);
    padding: 1.8rem;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 1rem;
    align-items: start;
    transition: border-color 0.3s, box-shadow 0.3s;
    position: relative;
    overflow: hidden;
  }

  .project-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--neon-cyan), var(--neon-pink));
    transform: scaleX(0);
    transition: transform 0.3s;
    transform-origin: left;
  }

  .project-card:hover {
    border-color: rgba(0,245,255,0.6);
    box-shadow: 0 0 20px rgba(0,245,255,0.1);
  }

  .project-card:hover::after { transform: scaleX(1); }

  .project-title {
    font-size: 1.1rem;
    font-weight: 600;
    color: #fff;
    margin-bottom: 0.5rem;
  }

  .project-desc {
    font-size: 0.88rem;
    color: var(--text-muted);
    margin-bottom: 1rem;
    line-height: 1.6;
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .project-tag {
    font-size: 0.72rem;
    padding: 0.2rem 0.6rem;
    letter-spacing: 0.5px;
    border: 1px solid;
  }

  .tag-cyan { color: var(--neon-cyan); border-color: rgba(0,245,255,0.4); }
  .tag-pink { color: var(--neon-pink); border-color: rgba(255,0,110,0.4); }
  .tag-purple { color: #c084fc; border-color: rgba(139,0,255,0.4); }
  .tag-green { color: var(--neon-green); border-color: rgba(57,255,20,0.4); }

  .project-status {
    font-size: 0.72rem;
    padding: 0.3rem 0.8rem;
    letter-spacing: 1px;
    text-transform: uppercase;
    white-space: nowrap;
    height: fit-content;
  }

  .status-done { color: var(--neon-green); border: 1px solid rgba(57,255,20,0.4); }
  .status-wip { color: var(--neon-pink); border: 1px solid rgba(255,0,110,0.4); }

  /* CONTACT */
  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }

  .contact-info h3 {
    font-size: 1.2rem;
    color: #fff;
    margin-bottom: 0.75rem;
  }

  .contact-info p {
    color: var(--text-muted);
    font-size: 0.9rem;
    margin-bottom: 1.5rem;
  }

  .contact-links {
    display: flex;
    flex-direction: column;
    gap: 0.8rem;
  }

  .contact-link {
    display: flex;
    align-items: center;
    gap: 0.8rem;
    color: var(--text-muted);
    text-decoration: none;
    font-size: 0.88rem;
    transition: color 0.3s;
    padding: 0.6rem 0;
    border-bottom: 1px solid rgba(255,255,255,0.05);
  }

  .contact-link:hover { color: var(--neon-cyan); }

  .contact-link-icon {
    width: 32px;
    height: 32px;
    background: rgba(0,245,255,0.07);
    border: 1px solid rgba(0,245,255,0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.8rem;
    color: var(--neon-cyan);
  }

  .contact-form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .form-group input,
  .form-group textarea {
    width: 100%;
    background: var(--bg-card);
    border: 1px solid var(--border-neon);
    color: var(--text-main);
    padding: 0.75rem 1rem;
    font-family: inherit;
    font-size: 0.88rem;
    outline: none;
    transition: border-color 0.3s, box-shadow 0.3s;
    resize: none;
  }

  .form-group input:focus,
  .form-group textarea:focus {
    border-color: var(--neon-cyan);
    box-shadow: 0 0 10px rgba(0,245,255,0.15);
  }

  .form-group input::placeholder,
  .form-group textarea::placeholder { color: var(--text-muted); }

  .btn-send {
    background: transparent;
    border: 1px solid var(--neon-cyan);
    color: var(--neon-cyan);
    padding: 0.75rem;
    font-size: 0.88rem;
    letter-spacing: 2px;
    text-transform: uppercase;
    cursor: pointer;
    transition: all 0.3s;
    font-family: inherit;
  }

  .btn-send:hover {
    background: var(--neon-cyan);
    color: #000;
    font-weight: 700;
    box-shadow: 0 0 20px rgba(0,245,255,0.4);
  }

  /* FOOTER */
  footer {
    text-align: center;
    padding: 2rem;
    border-top: 1px solid var(--border-neon);
    color: var(--text-muted);
    font-size: 0.8rem;
    letter-spacing: 1px;
  }

  footer span { color: var(--neon-pink); }

  /* ANIMATIONS */
  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  .cursor {
    display: inline-block;
    width: 3px;
    height: 1em;
    background: var(--neon-cyan);
    animation: blink 1s infinite;
    vertical-align: text-bottom;
    margin-left: 2px;
  }

  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .fade-in { animation: fadeInUp 0.6s ease forwards; }

  /* RESPONSIVE */
  @media (max-width: 640px) {
    .about-grid { grid-template-columns: 1fr; }
    .contact-grid { grid-template-columns: 1fr; }
    .project-card { grid-template-columns: 1fr; }
    nav ul { gap: 1rem; }
    h1 { font-size: 2.2rem; }
  }
</style>
</head>
<body>

<nav>
  <div class="logo">HM.DEV</div>
  <ul>
    <li><a href="#about">소개</a></li>
    <li><a href="#skills">기술</a></li>
    <li><a href="#projects">프로젝트</a></li>
    <li><a href="#contact">연락처</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-grid"></div>
  <div class="hero-content fade-in">
    <div class="hero-badge">// Game QA Engineer</div>
    <h1>안녕하세요,<br><span class="neon-text">현민</span>입니다<span class="cursor"></span></h1>
    <p class="hero-sub">게임 QA 및 테스트 자동화를 공부하는 3학년 대학생입니다. 버그를 찾고, 자동화로 해결합니다.</p>
    <div class="hero-btns">
      <a href="#projects" class="btn btn-primary">프로젝트 보기</a>
      <a href="#contact" class="btn btn-outline">연락하기</a>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-header">
    <span class="section-num">01 //</span>
    <h2>소개</h2>
    <div class="section-line"></div>
  </div>
  <div class="about-grid">
    <div class="about-text">
      <p>게임 QA와 <span>테스트 자동화</span>에 집중하고 있는 대학교 3학년입니다.</p>
      <p>Python, OpenCV, PyAutoGUI를 활용한 <span>게임 UI 자동화</span>와 C# 소켓 프로그래밍을 학습 중이며, 반복적인 QA 작업을 스크립트로 해결하는 것에 흥미를 느낍니다.</p>
      <p>매일 <span>스모크 테스트</span> 자동화부터 인게임 매크로까지, 실무에 가까운 프로젝트를 통해 실력을 키워가고 있습니다.</p>
    </div>
    <div class="about-stats">
      <div class="stat-card">
        <span class="stat-num">3+</span>
        <span class="stat-label">자동화 프로젝트</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">QA</span>
        <span class="stat-label">전문 분야</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">5+</span>
        <span class="stat-label">사용 기술</span>
      </div>
      <div class="stat-card">
        <span class="stat-num">3년</span>
        <span class="stat-label">학습 기간</span>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-header">
    <span class="section-num">02 //</span>
    <h2>기술 스택</h2>
    <div class="section-line"></div>
  </div>
  <div class="skills-grid">
    <div class="skill-category">
      <div class="skill-category-title">// 테스트 자동화</div>
      <div class="skill-list">
        <span class="skill-tag">Python</span>
        <span class="skill-tag">PyAutoGUI</span>
        <span class="skill-tag">OpenCV</span>
        <span class="skill-tag">Tesseract OCR</span>
        <span class="skill-tag">cv2.matchTemplate</span>
      </div>
      <div class="skill-bar-wrap">
        <div class="skill-bar-row">
          <div class="skill-bar-label"><span>Python</span><span>75%</span></div>
          <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="75"></div></div>
        </div>
        <div class="skill-bar-row">
          <div class="skill-bar-label"><span>OpenCV</span><span>60%</span></div>
          <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="60"></div></div>
        </div>
      </div>
    </div>
    <div class="skill-category">
      <div class="skill-category-title">// 네트워크 / 개발</div>
      <div class="skill-list">
        <span class="skill-tag">C#</span>
        <span class="skill-tag">Socket</span>
        <span class="skill-tag">ThreadPool</span>
        <span class="skill-tag">Race Condition</span>
        <span class="skill-tag">.NET</span>
      </div>
      <div class="skill-bar-wrap">
        <div class="skill-bar-row">
          <div class="skill-bar-label"><span>C#</span><span>65%</span></div>
          <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="65"></div></div>
        </div>
        <div class="skill-bar-row">
          <div class="skill-bar-label"><span>네트워크 프로그래밍</span><span>55%</span></div>
          <div class="skill-bar-bg"><div class="skill-bar-fill" data-width="55"></div></div>
        </div>
      </div>
    </div>
    <div class="skill-category">
      <div class="skill-category-title">// 문서 / 도구</div>
      <div class="skill-list">
        <span class="skill-tag">PowerPoint</span>
        <span class="skill-tag">pptxgenjs</span>
        <span class="skill-tag">Mermaid</span>
        <span class="skill-tag">LibreOffice</span>
        <span class="skill-tag">Git</span>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="section-header">
    <span class="section-num">03 //</span>
    <h2>프로젝트</h2>
    <div class="section-line"></div>
  </div>
  <div class="projects-list">
    <div class="project-card">
      <div>
        <div class="project-title">게임 UI 자동화 — 무기 소환 매크로</div>
        <div class="project-desc">Python + PyAutoGUI + OpenCV를 활용한 인게임 반복 작업 자동화. cv2.matchTemplate으로 해상도에 무관한 UI 인식 구현. 스모크 테스트 시나리오(로그인 → 로비) 포함.</div>
        <div class="project-tags">
          <span class="project-tag tag-cyan">Python</span>
          <span class="project-tag tag-pink">OpenCV</span>
          <span class="project-tag tag-purple">PyAutoGUI</span>
          <span class="project-tag tag-green">Tesseract OCR</span>
        </div>
      </div>
      <span class="project-status status-done">완료</span>
    </div>
    <div class="project-card">
      <div>
        <div class="project-title">C# 멀티유저 채팅 앱</div>
        <div class="project-desc">Socket + ThreadPool 기반 다중 클라이언트 채팅 서버 구현. Race Condition 처리 및 연결 제한 핸들링 포함. 대학 과제 프로젝트.</div>
        <div class="project-tags">
          <span class="project-tag tag-cyan">C#</span>
          <span class="project-tag tag-pink">Socket</span>
          <span class="project-tag tag-purple">ThreadPool</span>
        </div>
      </div>
      <span class="project-status status-done">완료</span>
    </div>
    <div class="project-card">
      <div>
        <div class="project-title">AI QA 전략 분석 덱</div>
        <div class="project-desc">DNN/XGBoost 예측 시스템의 QA 리스크 분석. 10슬라이드 전문 PPT 덱으로 제작. AI 기반 게임 시스템의 테스트 전략 연구.</div>
        <div class="project-tags">
          <span class="project-tag tag-green">QA Strategy</span>
          <span class="project-tag tag-cyan">AI Testing</span>
          <span class="project-tag tag-pink">pptxgenjs</span>
        </div>
      </div>
      <span class="project-status status-done">완료</span>
    </div>
    <div class="project-card">
      <div>
        <div class="project-title">게임 성장 분석 — 포세이돈 → 크로노스</div>
        <div class="project-desc">게임 내 성장 장벽 및 미스릴 공급 분석. 15슬라이드 분석 덱. 게임 밸런스 QA 관점에서의 시스템 분석.</div>
        <div class="project-tags">
          <span class="project-tag tag-purple">Game Analysis</span>
          <span class="project-tag tag-cyan">Balance QA</span>
          <span class="project-tag tag-pink">PPT</span>
        </div>
      </div>
      <span class="project-status status-wip">진행중</span>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-header">
    <span class="section-num">04 //</span>
    <h2>연락처</h2>
    <div class="section-line"></div>
  </div>
  <div class="contact-grid">
    <div class="contact-info">
      <h3>함께 일해요</h3>
      <p>게임 QA, 테스트 자동화, 프로젝트 협업 등 연락 주세요.</p>
      <div class="contact-links">
        <a href="mailto:your@email.com" class="contact-link">
          <div class="contact-link-icon">@</div>
          your@email.com
        </a>
        <a href="https://github.com/" class="contact-link" target="_blank">
          <div class="contact-link-icon">GH</div>
          github.com/yourname
        </a>
        <a href="#" class="contact-link">
          <div class="contact-link-icon">LI</div>
          LinkedIn
        </a>
      </div>
    </div>
    <div class="contact-form">
      <div class="form-group">
        <input type="text" placeholder="이름" />
      </div>
      <div class="form-group">
        <input type="email" placeholder="이메일" />
      </div>
      <div class="form-group">
        <textarea rows="4" placeholder="메시지를 입력하세요..."></textarea>
      </div>
      <button class="btn-send">// 전송하기</button>
    </div>
  </div>
</section>

<footer>
  <p>© 2026 현민 — <span>Game QA Engineer</span> — 부천, 경기도</p>
</footer>

<script>
  // Skill bar animation on scroll
  const bars = document.querySelectorAll('.skill-bar-fill');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const bar = entry.target;
        bar.style.width = bar.dataset.width + '%';
      }
    });
  }, { threshold: 0.3 });
  bars.forEach(b => observer.observe(b));

  // Nav active on scroll
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('nav a');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(s => {
      if (window.scrollY >= s.offsetTop - 200) current = s.id;
    });
    navLinks.forEach(a => {
      a.style.color = a.getAttribute('href') === '#' + current ? 'var(--neon-cyan)' : '';
    });
  });
</script>

</body>
</html>
