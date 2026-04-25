<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>Zoho Developer Intern Assessment</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{--bg:#060b18;--bg2:#0c1220;--bg3:#121929;--sur:rgba(255,255,255,.04);--sur2:rgba(255,255,255,.07);--bd:rgba(255,255,255,.08);--bd2:rgba(255,255,255,.14);--acc:#6366f1;--acc2:#818cf8;--vio:#8b5cf6;--tx:#f0f4ff;--tx2:#94a3b8;--tx3:#4b5a72;--grn:#22c55e;--red:#f43f5e;--amb:#f59e0b;--blu:#38bdf8;--r:14px;--rs:8px}
body{font-family:'Inter',system-ui,sans-serif;background:var(--bg);color:var(--tx);min-height:100vh;overflow-x:hidden;user-select:none}
::-webkit-scrollbar{width:4px}::-webkit-scrollbar-track{background:var(--bg2)}::-webkit-scrollbar-thumb{background:var(--tx3);border-radius:2px}
.bgfx{position:fixed;inset:0;z-index:0;pointer-events:none;background:radial-gradient(ellipse 80% 50% at 20% -10%,rgba(99,102,241,.14) 0%,transparent 60%),radial-gradient(ellipse 60% 40% at 80% 110%,rgba(139,92,246,.1) 0%,transparent 60%)}
/* TERMINATION */
#termination{position:fixed;inset:0;z-index:999999;background:rgba(0,0,0,.98);display:none;flex-direction:column;align-items:center;justify-content:center;backdrop-filter:blur(20px);padding:30px;text-align:center}
#termination .ti{font-size:80px;margin-bottom:10px}
#termination h1{font-size:28px;font-weight:800;color:var(--red);margin-bottom:8px}
#termination p{font-size:14px;color:var(--tx2);max-width:440px;line-height:1.8}
.t-sub{font-size:12px;color:var(--tx3);margin-top:16px;padding:10px 16px;background:rgba(244,63,94,.08);border:1px solid rgba(244,63,94,.2);border-radius:var(--rs);max-width:440px}
/* TAB BLOCKER */
#blocker{position:fixed;inset:0;z-index:99999;background:rgba(0,0,0,.97);display:none;flex-direction:column;align-items:center;justify-content:center;backdrop-filter:blur(20px);padding:30px;text-align:center}
#blocker .bc{font-size:64px;font-weight:800;color:var(--red);line-height:1;margin-bottom:4px}
#blocker h2{font-size:20px;font-weight:700;color:var(--red);margin-bottom:10px}
#blocker p{font-size:13px;color:var(--tx2);max-width:400px;line-height:1.7;margin-bottom:24px}
.b-btn{background:linear-gradient(135deg,var(--acc),var(--vio));color:#fff;border:none;padding:12px 30px;border-radius:var(--rs);font-size:14px;font-weight:700;cursor:pointer;font-family:inherit}
/* FACE VERIFY */
#face-verify{position:fixed;inset:0;z-index:9000;background:rgba(6,11,24,.97);display:none;flex-direction:column;align-items:center;justify-content:center;gap:16px;padding:24px;text-align:center}
#fv-video{width:320px;height:240px;border-radius:12px;border:2px solid var(--acc);object-fit:cover;transform:scaleX(-1)}
.fv-status{font-size:13px;color:var(--tx2);background:var(--sur2);padding:8px 18px;border-radius:20px;border:1px solid var(--bd)}
.fv-btn{background:linear-gradient(135deg,var(--acc),var(--vio));color:#fff;border:none;padding:11px 28px;border-radius:var(--rs);font-size:14px;font-weight:700;cursor:pointer;font-family:inherit;display:none}
/* PROCTOR ALERT */
#pa{position:fixed;top:72px;left:50%;transform:translateX(-50%);z-index:8000;background:rgba(245,158,11,.12);border:1px solid rgba(245,158,11,.35);border-radius:10px;padding:11px 16px;display:none;align-items:center;gap:10px;backdrop-filter:blur(12px);max-width:500px;width:92%}
#pa .pi{font-size:20px;flex-shrink:0}
#pa .pm{font-size:12px;color:var(--amb);line-height:1.5;flex:1}
#pa .px{color:var(--tx3);cursor:pointer;font-size:22px;line-height:1;padding:2px}
/* CAM PIP */
#cam-pip{position:fixed;bottom:80px;right:16px;z-index:600;border-radius:12px;overflow:hidden;border:1.5px solid var(--grn);box-shadow:0 0 20px rgba(34,197,94,.3);display:none;background:#000}
#cam-pip.blocked{border-color:var(--red)!important;box-shadow:0 0 20px rgba(244,63,94,.6)!important;animation:danger-pulse 1s ease infinite}
#camvid{width:148px;height:102px;object-fit:cover;display:block;transform:scaleX(-1)}
.clabel{background:rgba(34,197,94,.12);color:var(--grn);font-size:9px;font-weight:700;text-align:center;padding:3px 0;letter-spacing:.5px;border-top:1px solid rgba(34,197,94,.2)}
#cam-pip.blocked .clabel{background:rgba(244,63,94,.2);color:var(--red);border-top-color:rgba(244,63,94,.3)}
@keyframes danger-pulse{0%,100%{box-shadow:0 0 20px rgba(244,63,94,.4)}50%{box-shadow:0 0 40px rgba(244,63,94,.9)}}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.2}}
.dot-live{display:inline-block;width:6px;height:6px;border-radius:50%;background:var(--grn);animation:blink 1.2s infinite;margin-right:4px;vertical-align:middle}
.dot-red{display:inline-block;width:6px;height:6px;border-radius:50%;background:var(--red);animation:blink .4s infinite;margin-right:4px;vertical-align:middle}
/* TOAST */
#toast{position:fixed;bottom:24px;left:50%;transform:translateX(-50%);background:var(--bg3);color:var(--tx);border:1px solid var(--bd2);padding:9px 20px;border-radius:50px;font-size:13px;font-weight:500;z-index:9999;opacity:0;transition:opacity .3s;pointer-events:none;backdrop-filter:blur(10px);white-space:nowrap;max-width:90vw;text-align:center}
/* INFO PAGE */
.info-page{min-height:100vh;display:flex;align-items:flex-start;justify-content:center;padding:24px 16px;position:relative;z-index:1}
.info-inner{width:100%;max-width:940px;display:grid;grid-template-columns:300px 1fr;gap:20px;align-items:start}
@media(max-width:760px){.info-inner{grid-template-columns:1fr}}
.info-left{position:sticky;top:24px}
.brand-card,.rules-card{background:var(--sur);border:1px solid var(--bd);border-radius:var(--r);padding:24px;margin-bottom:14px;backdrop-filter:blur(10px)}
.rules-card{padding:18px}
.blog{width:48px;height:48px;border-radius:12px;background:linear-gradient(135deg,var(--acc),var(--vio));display:flex;align-items:center;justify-content:center;font-size:22px;margin-bottom:14px}
.bname{font-size:18px;font-weight:800;margin-bottom:4px}
.bsub{font-size:12px;color:var(--tx2);line-height:1.6}
.istats{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:16px}
.istat{background:var(--sur2);border-radius:var(--rs);padding:10px 12px;border:1px solid var(--bd)}
.isv{font-size:20px;font-weight:800;color:var(--acc2)}
.isl{font-size:10px;color:var(--tx2);margin-top:1px}
.rtitle{font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.6px;color:var(--tx3);margin-bottom:10px}
.ri{display:flex;gap:9px;margin-bottom:9px;font-size:12px;color:var(--tx2);line-height:1.5;align-items:flex-start}
.form-card{background:var(--sur);border:1px solid var(--bd);border-radius:var(--r);padding:26px;backdrop-filter:blur(10px)}
.fs-title{font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.6px;color:var(--tx3);margin:0 0 12px;padding-bottom:8px;border-bottom:1px solid var(--bd)}
.fdivider{height:1px;background:var(--bd);margin:18px 0}
.fg{margin-bottom:12px;position:relative}
.fg label{display:flex;align-items:center;gap:5px;font-size:10px;font-weight:600;color:var(--tx3);text-transform:uppercase;letter-spacing:.4px;margin-bottom:5px}
.badge{background:rgba(244,63,94,.12);color:var(--red);border-radius:4px;padding:1px 5px;font-size:9px;font-weight:700;border:1px solid rgba(244,63,94,.2)}
.badge.opt{background:rgba(99,102,241,.1);color:var(--acc2);border-color:rgba(99,102,241,.2)}
.fg input,.fg select{width:100%;padding:9px 12px;background:var(--bg2);border:1.5px solid var(--bd2);border-radius:var(--rs);font-size:13px;outline:none;font-family:inherit;color:var(--tx);transition:border-color .2s}
.fg input::placeholder{color:var(--tx3)}
.fg input:focus,.fg select:focus{border-color:var(--acc);box-shadow:0 0 0 3px rgba(99,102,241,.18)}
.fg input.err-field{border-color:var(--red)!important}
.fg input.ok-field{border-color:var(--grn)!important}
.fg select option{background:var(--bg3)}
.fgrid{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:460px){.fgrid{grid-template-columns:1fr}}
.err-msg{color:var(--red);font-size:11px;margin-top:4px;display:none;font-weight:500}
.err-msg.show{display:flex;align-items:center;gap:4px}
.rgroup{display:flex;gap:7px;flex-wrap:wrap;margin-top:4px}
.ropt{display:flex;align-items:center;gap:6px;background:var(--bg2);border:1.5px solid var(--bd2);border-radius:var(--rs);padding:7px 11px;cursor:pointer;transition:all .2s;font-size:12px;color:var(--tx2)}
.ropt:has(input:checked){border-color:var(--acc);background:rgba(99,102,241,.1);color:var(--tx)}
.ropt input{accent-color:var(--acc);width:13px;height:13px}
.uzone{border:1.5px dashed var(--bd2);border-radius:var(--rs);padding:18px;text-align:center;cursor:pointer;transition:all .2s;background:var(--bg2)}
.uzone:hover{border-color:var(--acc);background:rgba(99,102,241,.05)}
.uzone .uicon{font-size:26px;margin-bottom:6px}
.uzone p{font-size:12px;color:var(--tx2)}
.uzone .uhint{font-size:10px;color:var(--tx3);margin-top:3px}
.uzone .ufile{font-size:11px;color:var(--grn);margin-top:5px;font-weight:600}
.cam-req-box{background:var(--bg2);border:1.5px solid var(--bd2);border-radius:var(--rs);padding:14px;display:flex;align-items:center;gap:12px;transition:all .2s}
.cam-req-box.ok{border-color:rgba(34,197,94,.4);background:rgba(34,197,94,.05)}
.cam-req-box.fail{border-color:rgba(244,63,94,.4);background:rgba(244,63,94,.05)}
.cam-req-box .cicon{font-size:26px;flex-shrink:0}
.cam-req-box h4{font-size:13px;font-weight:600;margin-bottom:2px}
.cam-req-box p{font-size:11px;color:var(--tx2);line-height:1.5}
.btn-start{width:100%;padding:13px;background:linear-gradient(135deg,var(--acc),var(--vio));color:#fff;border:none;border-radius:var(--rs);font-size:15px;font-weight:700;cursor:pointer;font-family:inherit;transition:all .2s;box-shadow:0 4px 20px rgba(99,102,241,.4);margin-top:2px}
.btn-start:hover{transform:translateY(-2px)}
/* HEADER */
.app-hdr{position:sticky;top:0;z-index:500;background:rgba(6,11,24,.88);backdrop-filter:blur(20px);border-bottom:1px solid var(--bd)}
.hdr-main{display:flex;align-items:center;justify-content:space-between;padding:10px 18px;gap:10px}
.hdr-left{display:flex;align-items:center;gap:10px;min-width:0}
.hdr-logo{width:30px;height:30px;border-radius:8px;flex-shrink:0;background:linear-gradient(135deg,var(--acc),var(--vio));display:flex;align-items:center;justify-content:center;font-size:15px}
.hdr-sec .sub{font-size:10px;color:var(--tx3);text-transform:uppercase;letter-spacing:.5px}
.hdr-sec .ttl{font-size:14px;font-weight:700}
.hdr-right{display:flex;align-items:center;gap:10px;flex-shrink:0}
.timer-ring{position:relative;width:52px;height:52px;flex-shrink:0}
.timer-ring svg{position:absolute;inset:0;transform:rotate(-90deg)}
.tr-bg{fill:none;stroke:var(--bd2);stroke-width:3}
.tr-fill{fill:none;stroke:var(--acc);stroke-width:3;stroke-linecap:round;transition:stroke-dashoffset .9s linear,stroke .5s}
.tr-fill.warn{stroke:var(--red)}
.timer-inner{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:800;letter-spacing:.3px}
.timer-inner.warn{color:var(--red)}
.sec-pills{display:flex;gap:4px;padding:8px 18px;overflow-x:auto;scrollbar-width:none;border-top:1px solid var(--bd)}
.sec-pills::-webkit-scrollbar{display:none}
.spill{display:flex;align-items:center;gap:5px;padding:4px 11px;border-radius:20px;font-size:11px;font-weight:600;border:1px solid var(--bd2);color:var(--tx3);cursor:pointer;white-space:nowrap;transition:all .2s;background:transparent;font-family:inherit}
.spill.active{background:rgba(99,102,241,.14);border-color:var(--acc);color:var(--acc2)}
.spill.done{background:rgba(34,197,94,.08);border-color:rgba(34,197,94,.3);color:var(--grn)}
.spill.done::before{content:'✓ '}
.pbar{height:2px;background:var(--bd)}
.pbar-fill{height:100%;background:linear-gradient(90deg,var(--acc),var(--vio));transition:width .4s}
/* SECTION */
.sec-page{max-width:760px;margin:0 auto;padding:20px 16px 90px;position:relative;z-index:1}
.sec-hdr{margin-bottom:14px}
.sec-badge{display:inline-flex;align-items:center;gap:5px;background:rgba(99,102,241,.1);border:1px solid rgba(99,102,241,.22);color:var(--acc2);border-radius:20px;padding:3px 11px;font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;margin-bottom:8px}
.sec-title{font-size:22px;font-weight:800;margin-bottom:3px}
.sec-sub{font-size:13px;color:var(--tx2)}
.schema-card{background:rgba(56,189,248,.05);border:1px solid rgba(56,189,248,.2);border-radius:var(--r);padding:16px;margin-bottom:16px}
.schema-hdr{display:flex;align-items:center;justify-content:space-between;margin-bottom:12px;cursor:pointer}
.schema-hdr-left{font-size:12px;font-weight:700;color:var(--blu)}
.schema-toggle{font-size:11px;color:var(--tx3);background:var(--sur2);border:1px solid var(--bd);border-radius:6px;padding:3px 9px;cursor:pointer;font-family:inherit}
.schema-tables{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:520px){.schema-tables{grid-template-columns:1fr}}
.schema-table{background:var(--bg2);border-radius:var(--rs);overflow:hidden;border:1px solid var(--bd2)}
.st-name{background:var(--bg3);padding:7px 12px;font-size:11px;font-weight:800;color:var(--acc2);font-family:monospace;border-bottom:1px solid var(--bd)}
.st-col{display:flex;align-items:center;justify-content:space-between;padding:5px 12px;border-bottom:1px solid var(--bd);font-size:11px;font-family:monospace}
.st-col:last-child{border-bottom:none}
.st-col .cn{color:var(--tx)}.st-col .ct{color:var(--tx3);font-size:10px}
.st-col .ck{font-size:9px;background:rgba(99,102,241,.15);color:var(--acc2);border-radius:4px;padding:1px 5px;margin-left:5px}
.st-col .cfk{font-size:9px;background:rgba(245,158,11,.12);color:var(--amb);border-radius:4px;padding:1px 5px;margin-left:5px}
.schema-note{font-size:10px;color:var(--tx3);margin-top:8px;font-style:italic}
.schema-collapsed .schema-tables,.schema-collapsed .schema-note{display:none}
.q-card{background:var(--sur);border:1px solid var(--bd);border-radius:var(--r);padding:18px;margin-bottom:10px;transition:border-color .3s}
.q-card:focus-within{border-color:rgba(99,102,241,.35)}
.q-top{display:flex;gap:11px;margin-bottom:11px;align-items:flex-start}
.qnum{width:27px;height:27px;border-radius:7px;flex-shrink:0;background:rgba(99,102,241,.13);border:1px solid rgba(99,102,241,.22);display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:800;color:var(--acc2)}
.qcontent{flex:1;min-width:0}
.qtext{font-size:14px;font-weight:600;line-height:1.65;color:var(--tx);margin-bottom:4px}
.qhint{font-size:11px;color:var(--tx3);font-style:italic;line-height:1.5}
.qhint::before{content:'💡 '}
textarea{width:100%;min-height:78px;background:var(--bg2);border:1.5px solid var(--bd2);border-radius:var(--rs);padding:9px 11px;font-size:13px;font-family:inherit;resize:vertical;outline:none;color:var(--tx);transition:border-color .2s;line-height:1.6;user-select:text}
textarea::placeholder{color:var(--tx3)}
textarea:focus{border-color:var(--acc);box-shadow:0 0 0 3px rgba(99,102,241,.14)}
.qcc{font-size:10px;color:var(--tx3);text-align:right;margin-top:3px}
.nav-footer{position:fixed;bottom:0;left:0;right:0;z-index:490;background:rgba(6,11,24,.92);backdrop-filter:blur(20px);border-top:1px solid var(--bd);padding:11px 18px;display:flex;align-items:center;justify-content:space-between;gap:10px}
.nfl,.nfr{display:flex;align-items:center;gap:8px}
.btn{display:inline-flex;align-items:center;gap:5px;padding:8px 16px;border-radius:var(--rs);font-size:13px;font-weight:600;cursor:pointer;border:none;font-family:inherit;transition:all .2s}
.btn-ghost{background:var(--sur2);color:var(--tx2);border:1px solid var(--bd2)}
.btn-ghost:hover{background:var(--sur);color:var(--tx)}
.btn-ghost:disabled{opacity:.3;cursor:not-allowed}
.btn-primary{background:linear-gradient(135deg,var(--acc),var(--vio));color:#fff;box-shadow:0 2px 12px rgba(99,102,241,.3)}
.btn-primary:hover{transform:translateY(-1px)}
.btn-danger{background:rgba(244,63,94,.12);color:var(--red);border:1px solid rgba(244,63,94,.25)}
.qac{font-size:12px;color:var(--tx2);background:var(--sur2);padding:4px 11px;border-radius:20px;border:1px solid var(--bd)}
.qac.complete{color:var(--grn);border-color:rgba(34,197,94,.3);background:rgba(34,197,94,.06)}
/* DONE */
.loading-page,.done-page{min-height:100vh;display:flex;align-items:center;justify-content:center;flex-direction:column;text-align:center;padding:40px;position:relative;z-index:1}
.lring{width:68px;height:68px;border-radius:50%;border:3px solid var(--bd2);border-top-color:var(--acc);animation:spin .8s linear infinite;margin:0 auto 18px}
@keyframes spin{to{transform:rotate(360deg)}}
.ldots{display:flex;gap:6px;justify-content:center;margin-top:14px}
.ldots span{width:6px;height:6px;border-radius:50%;background:var(--acc);animation:dot .8s ease-in-out infinite}
.ldots span:nth-child(2){animation-delay:.15s}.ldots span:nth-child(3){animation-delay:.3s}
@keyframes dot{0%,100%{opacity:.2;transform:scale(.8)}50%{opacity:1;transform:scale(1.2)}}
.done-icon{font-size:64px;margin-bottom:16px}
.done-title{font-size:26px;font-weight:800;margin-bottom:8px;color:var(--grn)}
.done-sub{font-size:14px;color:var(--tx2);max-width:420px;line-height:1.8}
.done-card{background:var(--sur);border:1px solid var(--bd);border-radius:var(--r);padding:20px 28px;margin-top:24px;text-align:left;max-width:440px;width:100%}
.done-row{display:flex;justify-content:space-between;padding:7px 0;border-bottom:1px solid var(--bd);font-size:13px}
.done-row:last-child{border-bottom:none}
.done-row span:first-child{color:var(--tx3)}
.done-row span:last-child{font-weight:600}
</style>
</head>
<body>
<div class="bgfx"></div>

<!-- TERMINATION -->
<div id="termination">
  <div class="ti">🚫</div>
  <h1>Exam Terminated</h1>
  <p id="term-msg">Your exam has been terminated due to a serious violation.</p>
  <div class="t-sub">All data and snapshots have been saved and flagged for review.</div>
</div>

<!-- TAB BLOCKER -->
<div id="blocker">
  <div class="bc" id="blk-n">1</div>
  <h2>⚠ Tab Switch Detected</h2>
  <p>This violation is permanently logged and photographed.</p>
  <button class="b-btn" onclick="dismissBlocker()">I Understand — Resume Test</button>
</div>

<!-- FACE VERIFY -->
<div id="face-verify">
  <h2 style="font-size:20px;font-weight:800">Identity Verification</h2>
  <p style="font-size:13px;color:var(--tx2);max-width:360px;line-height:1.6">Look directly at the camera. We are capturing your reference photo for identity verification throughout the exam.</p>
  <video id="fv-video" autoplay muted playsinline></video>
  <div class="fv-status" id="fv-status">📷 Position your face in the frame…</div>
  <button class="fv-btn" id="fv-btn" onclick="captureBaselineFace()">📸 Capture My Photo & Start Exam</button>
</div>

<div id="pa"><span class="pi">⚠️</span><span class="pm" id="pa-msg">Please stay visible on camera.</span><span class="px" onclick="this.parentElement.style.display='none'">×</span></div>
<div id="cam-pip"><video id="camvid" autoplay muted playsinline></video><div class="clabel" id="cam-label"><span class="dot-live"></span>LIVE</div></div>
<div id="toast"></div>
<div id="hdr-area"></div>
<div id="app"></div>
<canvas id="snap-canvas" style="display:none" width="640" height="480"></canvas>
<canvas id="motion-canvas" style="display:none" width="160" height="120"></canvas>

<script>
// ══════════════════════════════════════════════════════════════
//  CONFIG
// ══════════════════════════════════════════════════════════════
const BACKEND_URL = "https://script.google.com/macros/s/AKfycbzTVwXJUJ3wdli6w-q1BfAQ0axOeDumapnje-zkdK3rGH5E0OPj70g3Ld5k969mwWqz/exec";
const TOTAL_TIME = 1800;
const CIRC = 2 * Math.PI * 22;
const SNAPSHOT_INTERVAL_SEC = 60;  // session snapshot every 60s
const FACE_ABSENT_LIMIT_MS = 2000; // face must return within 2s
const MAX_FACE_STRIKES = 3;        // 3 strikes → terminate
const MAX_IDENTITY_WARNINGS = 2;   // 2 identity mismatches → terminate

// ══════════════════════════════════════════════════════════════
//  STATE
// ══════════════════════════════════════════════════════════════
let state = 'info', curSec = 0, timeLeft = TOTAL_TIME;
let timerInt = null, motionInt = null, periodicInt = null;
let periodicSnapInt = null, faceCheckInt = null;
let isRunningAI = false, isFaceChecking = false;
let camGranted = false, camStream = null, motionCtx = null;
let violations = 0, proctorActive = false;
let proctorLog = [], snapshots = [], snapshotSeq = 0;
let baselineFaceB64 = null, terminated = false;
let schemaCollapsed = false;

// Face absence tracking
let faceNotVisibleStart = null;
let faceNotVisibleStrikes = 0;

// Identity mismatch tracking
let identityWarningCount = 0;

let candidate = {name:'',email:'',phone:'',location:'',linkedin:'',fulltime:'',startdate:'',isstudent:'',resumeName:'',resumeData:null};
let answers = Array(30).fill('');

// ══════════════════════════════════════════════════════════════
//  DATA
// ══════════════════════════════════════════════════════════════
const DB_SCHEMA = [
  {name:'customers',cols:[{n:'customer_id',t:'INT',k:'PK'},{n:'name',t:'VARCHAR',k:''},{n:'email',t:'VARCHAR',k:''},{n:'phone',t:'VARCHAR',k:''},{n:'created_at',t:'DATE',k:''}]},
  {name:'orders',cols:[{n:'order_id',t:'INT',k:'PK'},{n:'customer_id',t:'INT',k:'FK'},{n:'amount',t:'DECIMAL',k:''},{n:'order_date',t:'DATE',k:''},{n:'status',t:'VARCHAR',k:''}]}
];
const SECTIONS = [
  {title:"CRM & Lead Management",short:"CRM",showSchema:false,
   questions:["You have 100 leads coming daily. Only 3 salespeople are available. How will you distribute leads and why?","A customer filled the form 3 times with slightly different names. What will you do to handle this?","Leads are coming but no one is converting them. List 3 possible reasons and what you would check first.","Two salespeople contacted the same customer and confused them. How would you prevent this in a system?","You want every new lead to get a welcome email automatically. Explain the logic (not tool steps).","Some leads don't have phone numbers. What process would you put in place?","A lead becomes a paying customer. What data changes should happen?","Manager wants daily report of new leads. What data would you include?"],
   hints:["Think about prioritization, fairness, and lead scoring","Consider deduplication — email match, fuzzy name matching, merge strategy","Think CRM data quality, follow-up cadence, and lead qualification criteria","Consider lead ownership rules, assignment lock, and activity tracking","Describe trigger → condition → action in plain logic","Validation at entry, enrichment tools, alternative contact channels","Status change, deal creation, contact record update, history preservation","Count, source, stage, owner, conversion rate, pending follow-ups"]},
  {title:"SQL",short:"SQL",showSchema:true,
   questions:["Get all customers who have placed at least one order. (Write SQL query)","Find total amount spent by each customer. (Write SQL query)","Find top 3 customers by total spend. (Write SQL query)","Find customers who never placed any order. (Write SQL query)","Get latest order for each customer. (Write SQL query)","Explain the difference between INNER JOIN and LEFT JOIN. (2–4 lines)","Why might GROUP BY give wrong results sometimes? (2–4 lines)","You see duplicate rows in query results. What could be the reason? (2–4 lines)","Filter orders placed in the last 7 days. (Write SQL query)","If a query is running slow, what will you check first? (2–4 lines)"],
   hints:["Use JOIN or EXISTS/IN subquery","Use GROUP BY with SUM()","Use ORDER BY DESC with LIMIT 3","Use LEFT JOIN ... WHERE IS NULL, or NOT IN / NOT EXISTS","Use MAX(order_date) with GROUP BY or a window function","Explain what each returns when no match exists","Think about non-aggregated columns in SELECT","Think about missing DISTINCT, bad JOINs, or duplicate source data","Use date functions like CURDATE() or NOW()","Think indexes, EXPLAIN plan, full table scan vs index scan"]},
  {title:"Python",short:"Python",showSchema:false,
   questions:["What is a list in Python? Give an example.","Given data = [1,2,2,3,4,4], return the frequency of each element. Explain your approach.","What is a dictionary? How is it different from a list?","What will this output and why?\n  a = [1,2,3]\n  b = a\n  b.append(4)\n  print(a)","You get a list of numbers. Return only the even numbers. Explain your approach.","You have a list of numbers. Explain the logic to remove duplicates."],
   hints:["Include definition and a short code example","Think loops, dict counter, or collections.Counter","Key-value pairs vs indexed sequence","Think about references vs copies (mutable objects)","Think modulo operator and list comprehension or filter()","Think about sets or a 'seen' tracking approach"]},
  {title:"Math & Aptitude",short:"Quant",showSchema:false,
   questions:["20% of a number is 80. Find the number. Show all steps.","A product's price increases by 10%, then decreases by 10%. Final impact? Show all steps.","Boys to girls ratio = 2:3, total students = 50. Find the number of boys. Show steps.","Find the average of 10, 20, 30 and explain the steps.","Daily sales for 5 days: 100, 200, 150, 250, 300. What is the average? Show steps.","Find the next number in the sequence: 2, 6, 12, 20, ? — Explain your reasoning."],
   hints:["Set up: (20/100) × N = 80, solve for N","Start with ₹100 as base price, apply % changes one by one","Total ratio parts = 2+3 = 5, boys = (2/5) × 50","Add all values, divide by count","Sum all 5 values, divide by 5","Look at differences: 4, 6, 8, 10 — what's the pattern?"]}
];

// ══════════════════════════════════════════════════════════════
//  HELPERS
// ══════════════════════════════════════════════════════════════
const totalQ = SECTIONS.reduce((a,s)=>a+s.questions.length,0);
function secOff(si){return SECTIONS.slice(0,si).reduce((a,s)=>a+s.questions.length,0)}
function fmt(s){return`${String(Math.floor(s/60)).padStart(2,'0')}:${String(s%60).padStart(2,'0')}`}
function toast(msg,dur=3000){const t=document.getElementById('toast');t.textContent=msg;t.style.opacity='1';setTimeout(()=>t.style.opacity='0',dur)}
function validateName(v){return v.trim().length>=2&&/^[a-zA-Z\s]+$/.test(v.trim())}
function validatePhone(v){return v.replace(/\D/g,'').length>=10}
function validateEmail(v){return/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(v.trim())}
function onNameInput(el){el.value=el.value.replace(/[^a-zA-Z\s]/g,'');vfl(el,'err-name',validateName(el.value))}
function onPhoneInput(el){el.value=el.value.replace(/[^\d+\-\s]/g,'');vfl(el,'err-phone',validatePhone(el.value))}
function vfl(el,errId,valid){const em=document.getElementById(errId);if(!el.value.trim()){el.classList.remove('err-field','ok-field');if(em)em.classList.remove('show');return}if(valid){el.classList.remove('err-field');el.classList.add('ok-field');if(em)em.classList.remove('show')}else{el.classList.add('err-field');el.classList.remove('ok-field');if(em)em.classList.add('show')}}
function clearFE(el){el.classList.remove('err-field','ok-field');const n=el.parentElement?.querySelector('.err-msg');if(n)n.classList.remove('show')}

// ══════════════════════════════════════════════════════════════
//  BACKEND
// ══════════════════════════════════════════════════════════════
async function uploadToBackend(payload){
  if(!BACKEND_URL)return;
  try{await fetch(BACKEND_URL,{method:'POST',mode:'no-cors',headers:{'Content-Type':'text/plain'},body:JSON.stringify(payload)})}
  catch(e){console.warn('Upload failed:',e)}
}

async function checkEmailDuplicate(email){
  try{
    const res=await fetch(`${BACKEND_URL}?action=checkEmail&email=${encodeURIComponent(email)}`);
    const d=await res.json();
    return d.exists===true;
  }catch(e){return false}
}

// ══════════════════════════════════════════════════════════════
//  SNAPSHOT
// ══════════════════════════════════════════════════════════════
async function captureSnapshot(reason){
  const v=document.getElementById('camvid');
  if(!v||!v.srcObject||v.readyState<2)return null;
  return new Promise(resolve=>{
    requestAnimationFrame(()=>{
      try{
        snapshotSeq++;
        const c=document.getElementById('snap-canvas');
        const ctx=c.getContext('2d');
        ctx.save();ctx.scale(-1,1);ctx.drawImage(v,-640,0,640,480);ctx.restore();
        ctx.fillStyle='rgba(0,0,0,.75)';ctx.fillRect(0,0,640,32);
        ctx.fillStyle='#fff';ctx.font='bold 13px monospace';
        ctx.fillText(`${new Date().toLocaleString('en-IN')} | ${reason} | ${candidate.name}`,8,21);
        const img=c.toDataURL('image/jpeg',.85);
        const ts=new Date().toLocaleTimeString('en-IN');
        snapshots.push({time:ts,reason,img});
        const safeName=(candidate.name||'Unknown').replace(/\s+/g,'_');
        const safeReason=reason.replace(/[\s\/\\'"]/g,'_').substring(0,40);
        const fname=`${safeName}_${String(snapshotSeq).padStart(3,'0')}_${safeReason}_${Date.now()}.jpg`;
        uploadToBackend({type:'snapshot',candidateName:candidate.name,candidateEmail:candidate.email,
          timestamp:ts,reason,fileName:fname,mimeType:'image/jpeg',fileData:img.split(',')[1]});
        resolve(img);
      }catch(e){resolve(null)}
    });
  });
}

// ══════════════════════════════════════════════════════════════
//  FACE VERIFY FLOW
// ══════════════════════════════════════════════════════════════
async function showFaceVerify(){
  document.getElementById('face-verify').style.display='flex';
  try{
    const vs=await navigator.mediaDevices.getUserMedia({video:{width:640,height:480,facingMode:'user'},audio:false});
    camStream=vs;
    document.getElementById('fv-video').srcObject=vs;
    document.getElementById('camvid').srcObject=vs;
    await new Promise(r=>{document.getElementById('fv-video').onloadedmetadata=r});
    camGranted=true;
    document.getElementById('fv-status').textContent='✅ Camera ready — look straight at the camera and press the button';
    document.getElementById('fv-btn').style.display='inline-flex';
  }catch(e){
    document.getElementById('fv-status').textContent='❌ Camera denied — cannot proceed without camera';
  }
}

async function captureBaselineFace(){
  const btn=document.getElementById('fv-btn');
  btn.disabled=true;btn.textContent='Capturing…';
  await new Promise(r=>setTimeout(r,400));
  return new Promise(resolve=>{
    requestAnimationFrame(async()=>{
      const v=document.getElementById('fv-video');
      const c=document.getElementById('snap-canvas');
      const ctx=c.getContext('2d');
      ctx.save();ctx.scale(-1,1);ctx.drawImage(v,-640,0,640,480);ctx.restore();
      ctx.fillStyle='rgba(0,0,0,.75)';ctx.fillRect(0,0,640,32);
      ctx.fillStyle='#fff';ctx.font='bold 13px monospace';
      ctx.fillText(`BASELINE | ${new Date().toLocaleString('en-IN')} | ${candidate.name}`,8,21);
      const img=c.toDataURL('image/jpeg',.92);
      baselineFaceB64=img.split(',')[1];
      await uploadToBackend({type:'snapshot',candidateName:candidate.name,candidateEmail:candidate.email,
        timestamp:new Date().toLocaleTimeString('en-IN'),reason:'baseline_face',
        fileName:`${(candidate.name||'Unknown').replace(/\s+/g,'_')}_BASELINE_${Date.now()}.jpg`,
        mimeType:'image/jpeg',fileData:baselineFaceB64});
      document.getElementById('face-verify').style.display='none';
      beginExam();
      resolve();
    });
  });
}

// ══════════════════════════════════════════════════════════════
//  PROCTOR SETUP
// ══════════════════════════════════════════════════════════════
function activateProctor(){
  proctorActive=true;
  document.addEventListener('visibilitychange',()=>{
    if(document.hidden&&proctorActive&&!terminated){violations++;captureSnapshot('tab_switch');showBlocker()}
  });
  window.addEventListener('blur',()=>{
    if(proctorActive&&!terminated){violations++;captureSnapshot('window_blur');showBlocker()}
  });
  document.addEventListener('contextmenu',e=>{if(proctorActive)e.preventDefault()});
  document.addEventListener('keydown',e=>{
    if(!proctorActive)return;
    if((e.ctrlKey||e.metaKey)&&['c','v','a','u','s','p'].includes(e.key.toLowerCase()))e.preventDefault();
    if(e.key==='F12'||(e.ctrlKey&&e.shiftKey&&['i','j','c'].includes(e.key.toLowerCase())))e.preventDefault();
  });
}
function showBlocker(){document.getElementById('blk-n').textContent=violations;document.getElementById('blocker').style.display='flex'}
function dismissBlocker(){document.getElementById('blocker').style.display='none'}

// ══════════════════════════════════════════════════════════════
//  TERMINATION
// ══════════════════════════════════════════════════════════════
async function terminateExam(reason,msg){
  if(terminated)return;
  terminated=true;proctorActive=false;
  clearInterval(timerInt);
  hideFaceWarningBar();
  await captureSnapshot('TERMINATION_'+reason);
  await submitData(true,reason);
  stopCam();
  document.getElementById('term-msg').textContent=msg;
  document.getElementById('termination').style.display='flex';
}

// ══════════════════════════════════════════════════════════════
//  FACE PRESENCE CHECKER (runs every 1s — no API, instant)
// ══════════════════════════════════════════════════════════════
function startFacePresenceChecker(){
  faceCheckInt=setInterval(()=>{
    if(terminated||!proctorActive||isFaceChecking)return;
    checkFacePresence();
  },1000);
}

function checkFacePresence(){
  isFaceChecking=true;
  const v=document.getElementById('camvid');
  if(!v||!v.srcObject||v.readyState<2){isFaceChecking=false;return}
  try{
    motionCtx.drawImage(v,0,0,160,120);
    const d=motionCtx.getImageData(0,0,160,120).data;
    let skinPx=0,total=d.length/4;
    for(let i=0;i<d.length;i+=4){
      const r=d[i],g=d[i+1],b=d[i+2];
      // Skin tone detection — works for all skin tones
      if(r>60&&g>40&&b>20&&r>g&&r>b&&(r-b)>15&&r<250)skinPx++;
    }
    const skinRatio=skinPx/total;
    const faceVisible=skinRatio>0.03; // at least 3% skin pixels
    handleFaceVisibility(faceVisible);
  }catch(e){}
  isFaceChecking=false;
}

function handleFaceVisibility(faceVisible){
  if(faceVisible){
    // Face is back — reset timer
    if(faceNotVisibleStart!==null){
      faceNotVisibleStart=null;
      hideFaceWarningBar();
    }
    return;
  }
  // Face NOT visible
  const now=Date.now();
  if(faceNotVisibleStart===null){
    faceNotVisibleStart=now;
    showFaceWarningBar();
    return;
  }
  const elapsed=now-faceNotVisibleStart;
  updateFaceWarningBar(elapsed);
  if(elapsed>=FACE_ABSENT_LIMIT_MS){
    // Strike!
    faceNotVisibleStart=null;
    faceNotVisibleStrikes++;
    captureSnapshot(`face_absent_strike_${faceNotVisibleStrikes}`);
    proctorLog.push({time:new Date().toLocaleTimeString('en-IN'),type:'FACE_ABSENT',
      msg:`Face absent >2s — Strike ${faceNotVisibleStrikes}/${MAX_FACE_STRIKES}`});
    if(faceNotVisibleStrikes>=MAX_FACE_STRIKES){
      terminateExam('face_absent',
        `Your face was not visible on camera ${MAX_FACE_STRIKES} times for more than 2 seconds each. This is a serious violation. Your exam has been terminated and all evidence has been submitted to the recruitment team.`);
    }else{
      showFaceStrikeAlert(faceNotVisibleStrikes);
    }
  }
}

// ── RED WARNING BAR (appears instantly when face disappears) ───
function showFaceWarningBar(){
  let bar=document.getElementById('face-warn-bar');
  if(!bar){
    bar=document.createElement('div');
    bar.id='face-warn-bar';
    bar.style.cssText=`position:fixed;top:0;left:0;right:0;z-index:99990;
      background:rgba(244,63,94,.97);color:#fff;text-align:center;
      padding:10px 16px;font-size:14px;font-weight:700;
      display:flex;align-items:center;justify-content:center;gap:14px;`;
    bar.innerHTML=`<span>🚨 FACE NOT VISIBLE — Show your face NOW!</span>
      <div style="width:180px;height:8px;background:rgba(255,255,255,.3);border-radius:4px;overflow:hidden">
        <div id="fwb-fill" style="height:100%;width:100%;background:#fff;border-radius:4px;transition:width .1s linear"></div>
      </div>
      <span id="fwb-secs" style="font-size:16px;font-weight:900;min-width:34px">2.0s</span>`;
    document.body.prepend(bar);
  }
  bar.style.display='flex';
}
function updateFaceWarningBar(elapsed){
  const fill=document.getElementById('fwb-fill');
  const secs=document.getElementById('fwb-secs');
  if(fill){const pct=Math.max(0,100-(elapsed/FACE_ABSENT_LIMIT_MS)*100);fill.style.width=pct+'%';fill.style.background=pct<40?'#fbbf24':'#fff'}
  if(secs)secs.textContent=Math.max(0,(FACE_ABSENT_LIMIT_MS-elapsed)/1000).toFixed(1)+'s';
}
function hideFaceWarningBar(){
  const bar=document.getElementById('face-warn-bar');
  if(bar)bar.style.display='none';
}

// ── STRIKE POPUP ───────────────────────────────────────────────
function showFaceStrikeAlert(n){
  document.getElementById('face-strike-overlay')?.remove();
  const remaining=MAX_FACE_STRIKES-n;
  const div=document.createElement('div');
  div.id='face-strike-overlay';
  div.style.cssText=`position:fixed;inset:0;z-index:99998;background:rgba(0,0,0,.93);
    display:flex;flex-direction:column;align-items:center;justify-content:center;
    text-align:center;padding:30px;backdrop-filter:blur(10px)`;
  div.innerHTML=`
    <div style="font-size:72px;margin-bottom:10px">⛔</div>
    <h1 style="font-size:26px;font-weight:900;color:#f43f5e;margin-bottom:10px">Face Not Visible — Strike ${n}/${MAX_FACE_STRIKES}</h1>
    <p style="font-size:15px;color:#94a3b8;max-width:460px;line-height:1.8;margin-bottom:8px">
      Your face was absent from the camera for more than 2 seconds.<br>
      <strong style="color:#f87171">This has been photographed and logged.</strong>
    </p>
    <p style="font-size:14px;color:#fbbf24;margin-bottom:24px">
      ⚠️ ${remaining} more strike${remaining!==1?'s':''} = <strong>immediate exam termination.</strong>
    </p>
    <button onclick="this.parentElement.remove()" style="background:linear-gradient(135deg,#6366f1,#8b5cf6);
      color:#fff;border:none;padding:13px 36px;border-radius:8px;font-size:15px;font-weight:700;cursor:pointer;font-family:inherit">
      I Understand — Resume Exam
    </button>`;
  document.body.appendChild(div);
  setTimeout(()=>div.remove(),15000);
}

// ══════════════════════════════════════════════════════════════
//  AI IDENTITY CHECK (every 5s)
// ══════════════════════════════════════════════════════════════
function scheduleAI(trigger){
  if(isRunningAI||terminated)return;
  runProctorAI(trigger);
}

async function runProctorAI(trigger){
  if(!camGranted||!proctorActive||isRunningAI||terminated)return;
  isRunningAI=true;
  const v=document.getElementById('camvid');
  if(!v||!v.srcObject||v.readyState<2){isRunningAI=false;return}
  const tmp=document.createElement('canvas');tmp.width=640;tmp.height=480;
  const tctx=tmp.getContext('2d');
  tctx.save();tctx.scale(-1,1);tctx.drawImage(v,-640,0,640,480);tctx.restore();
  const currentB64=tmp.toDataURL('image/jpeg',.92).split(',')[1];
  try{
    const content=[];
    if(baselineFaceB64){
      content.push({type:'image',source:{type:'base64',media_type:'image/jpeg',data:baselineFaceB64}});
      content.push({type:'image',source:{type:'base64',media_type:'image/jpeg',data:currentB64}});
      content.push({type:'text',text:`You are a STRICT exam proctoring AI.
IMAGE 1 = BASELINE photo of the registered candidate taken at exam start.
IMAGE 2 = CURRENT live camera frame.
Compare faces carefully: face shape, skin tone, hair, eyes, nose, jawline, gender, age.
Rules:
- Clearly same person → same_person:true, confidence:85-100
- Any doubt or different person → same_person:false, confidence:0-84
- No face visible in IMAGE 2 → face_count:0
- Different lighting/angle is NOT a reason to say different person
- Different gender, age, or face structure → same_person:false
Return ONLY JSON, nothing else:
{"face_count":1,"same_person":true,"multiple_people":false,"confidence":90,"phone_or_notes":false,"msg":""}`});
    }else{
      content.push({type:'image',source:{type:'base64',media_type:'image/jpeg',data:currentB64}});
      content.push({type:'text',text:`Proctor check. Return ONLY JSON:
{"face_count":1,"same_person":true,"multiple_people":false,"confidence":90,"phone_or_notes":false,"msg":""}`});
    }
    const hdrs={'Content-Type':'application/json','anthropic-version':'2023-06-01','anthropic-dangerous-direct-browser-calls':'true'};
    const body=JSON.stringify({model:'claude-sonnet-4-20250514',max_tokens:200,messages:[{role:'user',content}]});
    let pr;
    try{pr=await fetch('https://api.anthropic.com/v1/messages',{method:'POST',headers:hdrs,body})}
    catch(e){pr=await fetch('https://corsproxy.io/?https://api.anthropic.com/v1/messages',{method:'POST',headers:hdrs,body})}
    const pd=await pr.json();
    const raw=(pd.content?.[0]?.text||'{}').replace(/```json|```/g,'').trim();
    let r;try{r=JSON.parse(raw)}catch(e){isRunningAI=false;return}
    console.log('[Proctor AI]',r);

    // Identity mismatch
    if(baselineFaceB64&&r.face_count>0&&(r.same_person===false||r.confidence<85)){
      identityWarningCount++;
      captureSnapshot(`identity_mismatch_warning_${identityWarningCount}`);
      proctorLog.push({time:new Date().toLocaleTimeString('en-IN'),type:'IDENTITY_MISMATCH',
        msg:`Different person detected — warning ${identityWarningCount}/${MAX_IDENTITY_WARNINGS}`});
      if(identityWarningCount>=MAX_IDENTITY_WARNINGS){
        await terminateExam('identity_mismatch',
          `A different person was detected on camera ${MAX_IDENTITY_WARNINGS} times. This is the most serious violation. Your exam has been terminated and all captured evidence has been sent to the recruitment team.`);
        return;
      }else{showIdentityWarning(identityWarningCount)}
      isRunningAI=false;return;
    }
    if(r.same_person===true&&r.confidence>=85)identityWarningCount=0;

    // Other checks
    if(r.face_count===0){captureSnapshot('no_face');showAlert('⚠️ No face visible — stay on camera.')}
    else if(r.multiple_people){captureSnapshot('multiple_people');showAlert('🚨 Multiple people detected!')}
    else if(r.phone_or_notes){captureSnapshot('unauthorized_materials');showAlert('🚨 Unauthorized materials detected!')}
  }catch(e){console.warn('AI proctor error:',e)}
  finally{isRunningAI=false}
}

// ── IDENTITY WARNING POPUP ─────────────────────────────────────
function showIdentityWarning(n){
  document.getElementById('identity-warn-overlay')?.remove();
  const remaining=MAX_IDENTITY_WARNINGS-n;
  const div=document.createElement('div');
  div.id='identity-warn-overlay';
  div.style.cssText=`position:fixed;inset:0;z-index:99998;background:rgba(0,0,0,.93);
    display:flex;flex-direction:column;align-items:center;justify-content:center;
    text-align:center;padding:30px;backdrop-filter:blur(10px)`;
  div.innerHTML=`
    <div style="font-size:72px;margin-bottom:10px">🚨</div>
    <h1 style="font-size:26px;font-weight:900;color:#f43f5e;margin-bottom:10px">Identity Mismatch — Warning ${n}/${MAX_IDENTITY_WARNINGS}</h1>
    <p style="font-size:15px;color:#94a3b8;max-width:460px;line-height:1.8;margin-bottom:8px">
      The person on camera does not match the registered candidate.<br>
      <strong style="color:#f87171">This has been photographed and logged.</strong>
    </p>
    <p style="font-size:14px;color:#fbbf24;margin-bottom:24px">
      ⚠️ ${remaining} more violation${remaining!==1?'s':''} = <strong>immediate exam termination.</strong>
    </p>
    <button onclick="document.getElementById('identity-warn-overlay').remove()" style="background:linear-gradient(135deg,#6366f1,#8b5cf6);
      color:#fff;border:none;padding:13px 36px;border-radius:8px;font-size:15px;font-weight:700;cursor:pointer;font-family:inherit">
      I Understand — Resume Exam
    </button>`;
  document.body.appendChild(div);
  setTimeout(()=>div.remove(),20000);
}

function showAlert(msg){
  const el=document.getElementById('pa');
  document.getElementById('pa-msg').textContent=msg;
  el.style.display='flex';
  setTimeout(()=>el.style.display='none',10000);
}

// ══════════════════════════════════════════════════════════════
//  CAMERA
// ══════════════════════════════════════════════════════════════
async function startCam(){
  try{
    camStream=await navigator.mediaDevices.getUserMedia({video:{width:640,height:480,facingMode:'user'},audio:false});
    document.getElementById('camvid').srcObject=camStream;
    await new Promise(r=>{document.getElementById('camvid').onloadedmetadata=r});
    const mc=document.getElementById('motion-canvas');
    motionCtx=mc.getContext('2d',{willReadFrequently:true});
    document.getElementById('cam-pip').style.display='block';
    camGranted=true;updateCamUI(true);
  }catch(e){camGranted=false;updateCamUI(false)}
}
function updateCamUI(ok){
  const el=document.getElementById('cam-status-box');if(!el)return;
  el.className='cam-req-box '+(ok?'ok':'fail');
  el.innerHTML=ok
    ?`<div class="cicon">📷</div><div><h4 style="color:var(--grn)">Camera ready</h4><p>Baseline photo will be captured before exam. AI monitors every 5 seconds.</p></div>`
    :`<div class="cicon">📷</div><div><h4 style="color:var(--red)">Camera denied</h4><p>Required to proceed.<br><button class="btn btn-ghost" style="margin-top:6px;font-size:11px;padding:5px 12px" onclick="startCam()">Try Again</button></p></div>`;
}
function stopCam(){
  clearInterval(motionInt);clearInterval(periodicInt);
  clearInterval(periodicSnapInt);clearInterval(faceCheckInt);
  if(camStream)camStream.getTracks().forEach(t=>t.stop());
  document.getElementById('cam-pip').style.display='none';
  hideFaceWarningBar();
}

// ══════════════════════════════════════════════════════════════
//  TIMER
// ══════════════════════════════════════════════════════════════
function startTimer(){
  timerInt=setInterval(()=>{
    if(terminated)return;
    timeLeft--;
    const warn=timeLeft<600,off=CIRC*(1-timeLeft/TOTAL_TIME);
    const fill=document.getElementById('tr-fill'),txt=document.getElementById('timer-txt');
    if(fill){fill.style.strokeDashoffset=off;fill.className='tr-fill'+(warn?' warn':'')}
    if(txt){txt.textContent=fmt(timeLeft);txt.className='timer-inner'+(warn?' warn':'')}
    if(timeLeft<=0){clearInterval(timerInt);doSubmit()}
    if(timeLeft%60===0)autoSave();
  },1000);
}
function autoSave(){try{sessionStorage.setItem('zass',JSON.stringify(answers))}catch(e){}}

// ══════════════════════════════════════════════════════════════
//  RENDER
// ══════════════════════════════════════════════════════════════
function render(){renderHdr();renderApp()}
function renderHdr(){
  const ha=document.getElementById('hdr-area');
  if(state==='info'||state==='submitting'||state==='done'){ha.innerHTML='';return}
  const sec=SECTIONS[curSec];
  const pct=Math.round((secOff(curSec)/totalQ)*100);
  const pills=SECTIONS.map((s,i)=>`<button class="spill ${i<curSec?'done':i===curSec?'active':''}" onclick="jumpToSection(${i})">${i+1}. ${s.short}</button>`).join('');
  ha.innerHTML=`<div class="app-hdr">
    <div class="hdr-main">
      <div class="hdr-left"><div class="hdr-logo">🧩</div><div class="hdr-sec"><div class="sub">Section ${curSec+1}/4</div><div class="ttl">${sec.title}</div></div></div>
      <div class="hdr-right">
        ${camGranted?`<div style="display:flex;align-items:center;gap:5px;font-size:11px;color:var(--grn)"><span class="dot-live"></span>Monitored</div>`:''}
        <div class="timer-ring"><svg viewBox="0 0 56 56" width="52" height="52"><circle class="tr-bg" cx="28" cy="28" r="22"/><circle id="tr-fill" class="tr-fill" cx="28" cy="28" r="22" stroke-dasharray="${CIRC} ${CIRC}" stroke-dashoffset="${CIRC*(1-timeLeft/TOTAL_TIME)}"/></svg><div id="timer-txt" class="timer-inner">${fmt(timeLeft)}</div></div>
      </div>
    </div>
    <div class="pbar"><div class="pbar-fill" style="width:${pct}%"></div></div>
    <div class="sec-pills">${pills}</div>
  </div>`;
}
function renderApp(){
  const app=document.getElementById('app');
  if(state==='info')app.innerHTML=renderInfo();
  else if(state==='section')app.innerHTML=renderSection();
  else if(state==='submitting')app.innerHTML=renderSubmitting();
  else if(state==='done')app.innerHTML=renderDone();
}

// ══════════════════════════════════════════════════════════════
//  INFO PAGE
// ══════════════════════════════════════════════════════════════
function renderInfo(){return`<div class="info-page"><div class="info-inner">
  <div class="info-left">
    <div class="brand-card">
      <div class="blog">🧩</div>
      <div class="bname">Zoho Developer Intern Assessment</div>
      <div class="bsub">Complete all 4 sections. Responses are reviewed by our team.</div>
      <div class="istats">
        <div class="istat"><div class="isv">4</div><div class="isl">Sections</div></div>
        <div class="istat"><div class="isv">30</div><div class="isl">Questions</div></div>
        <div class="istat"><div class="isv">30m</div><div class="isl">Time Limit</div></div>
        <div class="istat"><div class="isv">📷</div><div class="isl">Proctored</div></div>
      </div>
    </div>
    <div class="rules-card">
      <div class="rtitle">Proctoring Rules</div>
      <div class="ri">📸 Baseline photo captured at start as your identity reference</div>
      <div class="ri">👁 Face must be visible at ALL times — 2 second grace period only</div>
      <div class="ri">⛔ 3 face-absent strikes = immediate termination</div>
      <div class="ri">🤖 AI checks identity every 5 seconds vs your baseline photo</div>
      <div class="ri">🚨 2 identity mismatches = immediate termination</div>
      <div class="ri">🔒 Tab switches and window blur are photographed and logged</div>
    </div>
  </div>
  <div class="form-card">
    <div class="fs-title">Personal Information</div>
    <div class="fgrid">
      <div class="fg"><label>Full Name <span class="badge">Required</span></label>
        <input type="text" id="cname" placeholder="e.g. Sagar Ganatra" oninput="onNameInput(this)">
        <div class="err-msg" id="err-name">Letters only, minimum 2 characters</div></div>
      <div class="fg"><label>Email Address <span class="badge">Required</span></label>
        <input type="email" id="cemail" placeholder="you@email.com" oninput="vfl(this,'err-email',validateEmail(this.value))">
        <div class="err-msg" id="err-email">Enter a valid email address</div></div>
    </div>
    <div class="fgrid">
      <div class="fg"><label>Phone Number <span class="badge">Required</span></label>
        <input type="tel" id="cphone" placeholder="9876543210" oninput="onPhoneInput(this)" maxlength="15">
        <div class="err-msg" id="err-phone">Enter a valid 10-digit phone number</div></div>
      <div class="fg"><label>Current Location <span class="badge">Required</span></label>
        <input type="text" id="cloc" placeholder="Mumbai, Maharashtra" oninput="clearFE(this)">
        <div class="err-msg" id="err-loc">Location is required</div></div>
    </div>
    <div class="fg"><label>LinkedIn Profile URL <span class="badge opt">Optional</span></label>
      <input type="url" id="clinkedin" placeholder="https://linkedin.com/in/yourprofile"></div>
    <div class="fdivider"></div>
    <div class="fs-title">Availability</div>
    <div class="fg"><label>Available for full-time in-office internship in Mumbai (6 months)? <span class="badge">Required</span></label>
      <div class="rgroup">
        <label class="ropt"><input type="radio" name="fulltime" value="Yes"> Yes</label>
        <label class="ropt"><input type="radio" name="fulltime" value="No"> No</label>
        <label class="ropt"><input type="radio" name="fulltime" value="Maybe"> Maybe</label>
      </div><div class="err-msg" id="err-ft">Please select an option</div></div>
    <div class="fgrid">
      <div class="fg"><label>When can you start? <span class="badge">Required</span></label>
        <select id="cstart" oninput="clearFE(this)">
          <option value="">— Select —</option><option>Immediately</option><option>Within 2 weeks</option>
          <option>Within 1 month</option><option>After 1–2 months</option><option>After 3+ months</option>
        </select><div class="err-msg" id="err-start">Please select a start date</div></div>
      <div class="fg"><label>Currently a student? <span class="badge">Required</span></label>
        <div class="rgroup" style="flex-direction:column;gap:5px">
          <label class="ropt"><input type="radio" name="isstudent" value="Yes, currently studying"> Yes, studying</label>
          <label class="ropt"><input type="radio" name="isstudent" value="No, graduated"> No, graduated</label>
          <label class="ropt"><input type="radio" name="isstudent" value="No, currently working"> No, working</label>
        </div><div class="err-msg" id="err-st">Please select an option</div></div>
    </div>
    <div class="fdivider"></div>
    <div class="fs-title">Resume</div>
    <div class="fg">
      <div class="uzone" onclick="document.getElementById('rfile').click()">
        <input type="file" id="rfile" accept=".pdf,.doc,.docx" style="display:none" onchange="handleResume(event)">
        <div class="uicon">📄</div><p>Click to upload resume</p>
        <div class="uhint">PDF, DOC or DOCX — max 5 MB</div>
        <div class="ufile" id="rfile-name"></div>
      </div>
      <div class="err-msg" id="err-resume">Resume is required</div></div>
    <div class="fdivider"></div>
    <div class="fs-title">Camera & Identity Verification</div>
    <div id="cam-status-box" class="cam-req-box">
      <div class="cicon">📷</div>
      <div><h4>Camera access required</h4>
        <p>Your face will be verified before and throughout the exam.<br>
        <button class="btn btn-ghost" style="margin-top:7px;font-size:12px;padding:6px 14px" onclick="startCam()">Enable Camera</button></p>
      </div>
    </div>
    <div class="err-msg" id="err-cam" style="margin-top:5px">Camera access is required to proceed</div>
    <div class="fdivider"></div>
    <button class="btn-start" onclick="startAssessment()">Continue to Identity Verification →</button>
  </div>
</div></div>`}

function handleResume(e){
  const f=e.target.files[0];if(!f)return;
  if(f.size>5*1024*1024){toast('File too large — max 5 MB');return}
  candidate.resumeName=f.name;
  const r=new FileReader();r.onload=()=>{candidate.resumeData=r.result};r.readAsDataURL(f);
  document.getElementById('rfile-name').textContent='✓ '+f.name;
  document.getElementById('err-resume').classList.remove('show');
}

async function startAssessment(){
  document.querySelectorAll('.err-msg').forEach(e=>e.classList.remove('show'));
  document.querySelectorAll('.err-field').forEach(e=>e.classList.remove('err-field'));
  let ok=true;
  const n=document.getElementById('cname').value.trim();
  const em=document.getElementById('cemail').value.trim();
  const ph=document.getElementById('cphone').value.trim();
  const lo=document.getElementById('cloc').value.trim();
  const ft=document.querySelector('input[name=fulltime]:checked');
  const st=document.getElementById('cstart').value;
  const is=document.querySelector('input[name=isstudent]:checked');
  function fe(id,fid){const e=document.getElementById(id);if(e)e.classList.add('show');if(fid){const f=document.getElementById(fid);if(f)f.classList.add('err-field')}ok=false}
  if(!validateName(n))fe('err-name','cname');
  if(!validateEmail(em))fe('err-email','cemail');
  if(!validatePhone(ph))fe('err-phone','cphone');
  if(!lo)fe('err-loc','cloc');
  if(!ft)fe('err-ft',null);
  if(!st)fe('err-start','cstart');
  if(!is)fe('err-st',null);
  if(!candidate.resumeData)fe('err-resume',null);
  if(!camGranted)fe('err-cam',null);
  if(!ok){document.querySelector('.err-msg.show')?.scrollIntoView({behavior:'smooth',block:'center'});return}
  const btn=document.querySelector('.btn-start');
  if(btn){btn.disabled=true;btn.textContent='Checking eligibility…'}
  const isDuplicate=await checkEmailDuplicate(em);
  if(isDuplicate){
    if(btn){btn.disabled=false;btn.textContent='Continue to Identity Verification →'}
    const eem=document.getElementById('err-email');
    if(eem){eem.textContent='⛔ This email has already submitted an assessment. Contact HR if this is a mistake.';eem.classList.add('show')}
    document.getElementById('cemail')?.classList.add('err-field');
    document.getElementById('cemail')?.scrollIntoView({behavior:'smooth',block:'center'});
    return;
  }
  if(btn){btn.disabled=false;btn.textContent='Continue to Identity Verification →'}
  candidate={...candidate,name:n,email:em,phone:ph,location:lo,
    linkedin:document.getElementById('clinkedin').value.trim(),
    fulltime:ft.value,startdate:st,isstudent:is.value};
  showFaceVerify();
}

// ══════════════════════════════════════════════════════════════
//  BEGIN EXAM
// ══════════════════════════════════════════════════════════════
function beginExam(){
  try{const s=sessionStorage.getItem('zass');if(s)answers=JSON.parse(s)}catch(e){}
  // Setup motion canvas for face checker
  const mc=document.getElementById('motion-canvas');
  motionCtx=mc.getContext('2d',{willReadFrequently:true});
  document.getElementById('cam-pip').style.display='block';
  activateProctor();
  startFacePresenceChecker();       // instant face presence — every 1s
  // AI identity check — every 5s
  periodicInt=setInterval(()=>{if(!isRunningAI&&!terminated)scheduleAI('periodic')},5000);
  // Session snapshot — every 60s
  let minCount=0;
  periodicSnapInt=setInterval(async()=>{
    if(terminated||!proctorActive)return;
    minCount++;await captureSnapshot(`session_minute_${minCount}`);
  },SNAPSHOT_INTERVAL_SEC*1000);
  state='section';curSec=0;startTimer();
  render();window.scrollTo(0,0);
}

// ══════════════════════════════════════════════════════════════
//  SECTION RENDER
// ══════════════════════════════════════════════════════════════
function renderSection(){
  const sec=SECTIONS[curSec];
  const off=secOff(curSec);
  const isLast=curSec===SECTIONS.length-1;
  const answered=answers.slice(off,off+sec.questions.length).filter(a=>a&&a.trim()).length;
  let schemaHTML='';
  if(sec.showSchema){
    const tables=DB_SCHEMA.map(t=>`<div class="schema-table"><div class="st-name">📋 ${t.name}</div>${t.cols.map(c=>`<div class="st-col"><span class="cn">${c.n}</span><span style="display:flex;align-items:center">${c.k==='PK'?`<span class="ck">PK</span>`:c.k==='FK'?`<span class="cfk">FK</span>`:''}<span class="ct">${c.t}</span></span></div>`).join('')}</div>`).join('');
    schemaHTML=`<div class="schema-card ${schemaCollapsed?'schema-collapsed':''}">
      <div class="schema-hdr" onclick="schemaCollapsed=!schemaCollapsed;renderApp()">
        <div class="schema-hdr-left">🗃 Database Schema Reference</div>
        <button class="schema-toggle">${schemaCollapsed?'Show ↓':'Hide ↑'}</button>
      </div>
      <div class="schema-tables">${tables}</div>
      <div class="schema-note">Use these exact table and column names.</div>
    </div>`;
  }
  const qs=sec.questions.map((q,i)=>{
    const absIdx=off+i,ans=answers[absIdx]||'';
    return`<div class="q-card" id="qcard${i}">
      <div class="q-top">
        <div class="qnum">${absIdx+1}</div>
        <div class="qcontent">
          <div class="qtext">${q.replace(/\n/g,'<br>')}</div>
          <div class="qhint">${sec.hints[i]}</div>
        </div>
      </div>
      <textarea id="ta${i}" placeholder="Write your answer here…" oninput="onTaInput(this,${i})">${ans}</textarea>
      <div class="qcc" id="cc${i}">${ans.length} chars</div>
    </div>`;
  }).join('');
  return`<div class="sec-page">
    <div class="sec-hdr">
      <div class="sec-badge">Section ${curSec+1} — ${sec.title}</div>
      <div class="sec-title">${sec.title}</div>
      <div class="sec-sub">${sec.questions.length} questions — answer what you can</div>
    </div>
    ${schemaHTML}${qs}
  </div>
  <div class="nav-footer">
    <div class="nfl">
      <button class="btn btn-ghost" onclick="goBack()" ${curSec===0?'disabled':''}>← Back</button>
      <span class="qac ${answered===sec.questions.length?'complete':''}" id="qac">${answered}/${sec.questions.length} answered</span>
    </div>
    <div class="nfr">
      ${isLast
        ?`<button class="btn btn-danger" onclick="doSubmit()">Submit Assessment ✓</button>`
        :`<button class="btn btn-primary" onclick="nextSection()">Next Section →</button>`}
    </div>
  </div>`;
}

function onTaInput(el,i){
  const off=secOff(curSec);answers[off+i]=el.value;
  const cc=document.getElementById('cc'+i);if(cc)cc.textContent=el.value.length+' chars';
  const ans=answers.slice(off,off+SECTIONS[curSec].questions.length).filter(a=>a&&a.trim()).length;
  const qac=document.getElementById('qac');
  if(qac){qac.textContent=`${ans}/${SECTIONS[curSec].questions.length} answered`;qac.className='qac '+(ans===SECTIONS[curSec].questions.length?'complete':'')}
  autoSave();
}
function saveAns(){const off=secOff(curSec);SECTIONS[curSec].questions.forEach((_,i)=>{const ta=document.getElementById('ta'+i);if(ta)answers[off+i]=ta.value})}
function nextSection(){saveAns();curSec++;render();window.scrollTo(0,0)}
function goBack(){if(curSec===0)return;saveAns();curSec--;render();window.scrollTo(0,0)}
function jumpToSection(i){if(i===curSec)return;saveAns();curSec=i;render();window.scrollTo(0,0)}

// ══════════════════════════════════════════════════════════════
//  SUBMIT
// ══════════════════════════════════════════════════════════════
function renderSubmitting(){return`<div class="loading-page">
  <div class="lring"></div>
  <h2 style="font-size:22px;font-weight:800;margin-bottom:8px">Submitting your responses…</h2>
  <p style="color:var(--tx2);font-size:14px;max-width:360px;line-height:1.7">Please wait while we securely send your data.</p>
  <div class="ldots"><span></span><span></span><span></span></div>
</div>`}

async function submitData(isTerminated=false,terminationReason=''){
  saveAns();
  const payload={
    type:'response',timestamp:new Date().toLocaleString('en-IN'),
    name:candidate.name,email:candidate.email,phone:candidate.phone,
    location:candidate.location,linkedin:candidate.linkedin||'—',
    fulltime:candidate.fulltime,startdate:candidate.startdate,isstudent:candidate.isstudent,
    resumeLink:'—',timeTaken:fmt(TOTAL_TIME-timeLeft),
    questionsAnswered:answers.filter(a=>a&&a.trim()).length,
    tabViolations:violations,proctorEventCount:proctorLog.length,
    snapshotCount:snapshots.length,
    terminated:isTerminated?'YES':'NO',terminationReason:terminationReason||'—',
    ...Object.fromEntries(answers.map((a,i)=>[`Q${i+1}`,a||'']))
  };
  await uploadToBackend(payload);
  if(candidate.resumeData){
    const ext=candidate.resumeName.split('.').pop().toLowerCase();
    await uploadToBackend({type:'resume',
      fileName:`${candidate.name.replace(/\s+/g,'_')}_resume.${ext}`,
      fileData:candidate.resumeData.split(',')[1],
      mimeType:ext==='pdf'?'application/pdf':'application/msword',
      candidateName:candidate.name,candidateEmail:candidate.email});
  }
  try{sessionStorage.removeItem('zass')}catch(e){}
}

async function doSubmit(){
  if(terminated)return;
  clearInterval(timerInt);proctorActive=false;
  state='submitting';render();
  await submitData(false);
  stopCam();
  state='done';render();window.scrollTo(0,0);
}

// ══════════════════════════════════════════════════════════════
//  DONE PAGE
// ══════════════════════════════════════════════════════════════
function renderDone(){
  return`<div class="done-page">
    <div class="done-icon">✅</div>
    <div class="done-title">Assessment Submitted!</div>
    <div class="done-sub">Thank you, <strong>${candidate.name}</strong>. Your responses have been received and will be reviewed by our team within 3–5 business days.</div>
    <div class="done-card">
      <div class="done-row"><span>Name</span><span>${candidate.name}</span></div>
      <div class="done-row"><span>Email</span><span>${candidate.email}</span></div>
      <div class="done-row"><span>Time taken</span><span>${fmt(TOTAL_TIME-timeLeft)}</span></div>
      <div class="done-row"><span>Questions answered</span><span>${answers.filter(a=>a&&a.trim()).length}/30</span></div>
      <div class="done-row"><span>Tab violations</span><span style="color:${violations>0?'var(--red)':'var(--grn)'}">${violations}</span></div>
      <div class="done-row"><span>Face absent strikes</span><span style="color:${faceNotVisibleStrikes>0?'var(--amb)':'var(--grn)'}">${faceNotVisibleStrikes}/${MAX_FACE_STRIKES}</span></div>
      <div class="done-row"><span>Snapshots saved</span><span>${snapshots.length}</span></div>
    </div>
  </div>`;
}

render();
</script>
</body>
</html>
