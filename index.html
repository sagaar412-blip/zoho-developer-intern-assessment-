<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>Zoho Developer Intern Assessment</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#060b18;--bg2:#0c1220;--bg3:#121929;
  --sur:rgba(255,255,255,.04);--sur2:rgba(255,255,255,.07);
  --bd:rgba(255,255,255,.08);--bd2:rgba(255,255,255,.14);
  --acc:#6366f1;--acc2:#818cf8;--vio:#8b5cf6;
  --tx:#f0f4ff;--tx2:#94a3b8;--tx3:#4b5a72;
  --grn:#22c55e;--red:#f43f5e;--amb:#f59e0b;--blu:#38bdf8;
  --r:14px;--rs:8px;
}
body{font-family:'Inter',system-ui,sans-serif;background:var(--bg);color:var(--tx);min-height:100vh;overflow-x:hidden;user-select:none}
::-webkit-scrollbar{width:4px}::-webkit-scrollbar-track{background:var(--bg2)}::-webkit-scrollbar-thumb{background:var(--tx3);border-radius:2px}
.bgfx{position:fixed;inset:0;z-index:0;pointer-events:none;
  background:radial-gradient(ellipse 80% 50% at 20% -10%,rgba(99,102,241,.14) 0%,transparent 60%),
             radial-gradient(ellipse 60% 40% at 80% 110%,rgba(139,92,246,.1) 0%,transparent 60%)}

/* ── OVERLAYS ── */
#termination,#blocker{position:fixed;inset:0;z-index:99999;background:rgba(0,0,0,.97);display:none;flex-direction:column;align-items:center;justify-content:center;backdrop-filter:blur(20px);padding:30px;text-align:center}
#termination h1{font-size:26px;font-weight:800;color:var(--red);margin:12px 0 8px}
#termination p,#blocker p{font-size:13px;color:var(--tx2);max-width:420px;line-height:1.8;margin-bottom:20px}
.ov-icon{font-size:72px;line-height:1}
#blocker h2{font-size:20px;font-weight:700;color:var(--amb);margin-bottom:10px}
.ov-badge{font-size:64px;font-weight:800;color:var(--red);line-height:1;margin-bottom:4px}
.ov-sub{font-size:12px;color:var(--tx3);margin-top:12px;padding:10px 16px;background:rgba(244,63,94,.08);border:1px solid rgba(244,63,94,.2);border-radius:var(--rs);max-width:420px;line-height:1.6}
.ov-btn{background:linear-gradient(135deg,var(--acc),var(--vio));color:#fff;border:none;padding:12px 28px;border-radius:var(--rs);font-size:14px;font-weight:700;cursor:pointer;font-family:inherit;margin-top:4px}

/* ── FACE VERIFY ── */
#face-verify{position:fixed;inset:0;z-index:9000;background:rgba(6,11,24,.97);display:none;flex-direction:column;align-items:center;justify-content:center;gap:14px;padding:24px;text-align:center}
#fv-video{width:320px;height:240px;border-radius:12px;border:2px solid var(--acc);object-fit:cover;transform:scaleX(-1)}
.fv-progress{display:flex;gap:8px;justify-content:center}
.fv-dot{width:12px;height:12px;border-radius:50%;border:2px solid var(--bd2);transition:all .3s}
.fv-dot.captured{background:var(--grn);border-color:var(--grn)}
.fv-dot.active{background:var(--acc);border-color:var(--acc);animation:pulse-dot .8s ease infinite}
@keyframes pulse-dot{0%,100%{transform:scale(1)}50%{transform:scale(1.3)}}
.fv-status{font-size:13px;color:var(--tx2);background:var(--sur2);padding:8px 18px;border-radius:20px;border:1px solid var(--bd)}
.fv-btn{background:linear-gradient(135deg,var(--acc),var(--vio));color:#fff;border:none;padding:11px 28px;border-radius:var(--rs);font-size:14px;font-weight:700;cursor:pointer;font-family:inherit;display:none}

/* ── PROCTOR ALERT (non-intrusive) ── */
#pa{position:fixed;top:72px;left:50%;transform:translateX(-50%);z-index:8000;
  background:rgba(245,158,11,.14);border:1px solid rgba(245,158,11,.4);
  border-radius:10px;padding:10px 16px;display:none;align-items:center;gap:10px;
  backdrop-filter:blur(12px);max-width:500px;width:92%;transition:opacity .3s}
#pa .pi{font-size:18px;flex-shrink:0}
#pa .pm{font-size:12px;color:var(--amb);line-height:1.5;flex:1}
#pa .px{color:var(--tx3);cursor:pointer;font-size:20px;line-height:1}

/* ── CAM PIP + FACE INDICATOR ── */
#cam-pip{position:fixed;bottom:80px;right:16px;z-index:600;border-radius:12px;overflow:hidden;border:1.5px solid var(--grn);box-shadow:0 0 16px rgba(34,197,94,.25);display:none;background:#000}
#cam-pip.blocked{border-color:var(--red)!important;animation:danger-pulse 1s infinite}
#cam-pip.no-face{border-color:var(--amb)!important;box-shadow:0 0 16px rgba(245,158,11,.5)!important}
#camvid{width:148px;height:102px;object-fit:cover;display:block;transform:scaleX(-1)}
.clabel{font-size:9px;font-weight:700;text-align:center;padding:3px 0;letter-spacing:.5px;border-top:1px solid rgba(255,255,255,.08);display:flex;align-items:center;justify-content:center;gap:4px}
.clabel.ok{background:rgba(34,197,94,.12);color:var(--grn)}
.clabel.warn{background:rgba(245,158,11,.15);color:var(--amb)}
.clabel.err{background:rgba(244,63,94,.2);color:var(--red)}
/* Face status pill */
#face-indicator{position:absolute;top:4px;left:4px;font-size:9px;font-weight:700;padding:2px 7px;border-radius:10px;transition:all .3s}
#face-indicator.ok{background:rgba(34,197,94,.85);color:#fff}
#face-indicator.miss{background:rgba(244,63,94,.9);color:#fff;animation:pulse-ind .6s infinite}
#face-indicator.warn{background:rgba(245,158,11,.9);color:#fff}
@keyframes pulse-ind{0%,100%{opacity:1}50%{opacity:.4}}
@keyframes danger-pulse{0%,100%{box-shadow:0 0 16px rgba(244,63,94,.4)}50%{box-shadow:0 0 32px rgba(244,63,94,.9)}}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.2}}
.dot{display:inline-block;width:6px;height:6px;border-radius:50%;animation:blink 1.2s infinite;vertical-align:middle;margin-right:2px}
.dot.grn{background:var(--grn)}.dot.red{background:var(--red);animation-duration:.4s}.dot.amb{background:var(--amb)}

/* ── TOAST ── */
#toast{position:fixed;bottom:24px;left:50%;transform:translateX(-50%);background:var(--bg3);color:var(--tx);border:1px solid var(--bd2);padding:9px 20px;border-radius:50px;font-size:13px;font-weight:500;z-index:9999;opacity:0;transition:opacity .3s;pointer-events:none;backdrop-filter:blur(10px);white-space:nowrap;max-width:90vw;text-align:center}

/* ── PRETEST SCREEN ── */
.pretest-page{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:32px 16px;position:relative;z-index:1}
.pretest-inner{max-width:560px;width:100%;text-align:center}
.pretest-logo{width:64px;height:64px;border-radius:16px;background:linear-gradient(135deg,var(--acc),var(--vio));display:flex;align-items:center;justify-content:center;font-size:30px;margin:0 auto 20px}
.pretest-title{font-size:26px;font-weight:800;margin-bottom:8px}
.pretest-sub{font-size:14px;color:var(--tx2);margin-bottom:28px;line-height:1.7}
.pretest-rules{background:var(--sur);border:1px solid var(--bd);border-radius:var(--r);padding:20px;margin-bottom:24px;text-align:left}
.pr-item{display:flex;gap:12px;align-items:flex-start;margin-bottom:14px;font-size:13px;color:var(--tx2);line-height:1.55}
.pr-item:last-child{margin-bottom:0}
.pr-icon{font-size:18px;flex-shrink:0;margin-top:-1px}
.pr-item b{color:var(--tx);display:block;font-weight:600;margin-bottom:1px}
.checklist{background:var(--sur2);border:1px solid var(--bd2);border-radius:var(--rs);padding:14px 18px;margin-bottom:24px;text-align:left}
.cl-item{display:flex;align-items:center;gap:10px;font-size:13px;color:var(--tx2);padding:5px 0;border-bottom:1px solid var(--bd)}
.cl-item:last-child{border-bottom:none}
.cl-item input[type=checkbox]{accent-color:var(--acc);width:15px;height:15px;cursor:pointer}
.btn-pretest{width:100%;padding:14px;background:linear-gradient(135deg,var(--acc),var(--vio));color:#fff;border:none;border-radius:var(--rs);font-size:15px;font-weight:700;cursor:pointer;font-family:inherit;transition:all .2s;box-shadow:0 4px 20px rgba(99,102,241,.35)}
.btn-pretest:disabled{opacity:.35;cursor:not-allowed;transform:none}

/* ── INFO PAGE ── */
.info-page{min-height:100vh;display:flex;align-items:flex-start;justify-content:center;padding:24px 16px;position:relative;z-index:1}
.info-inner{width:100%;max-width:940px;display:grid;grid-template-columns:290px 1fr;gap:20px;align-items:start}
@media(max-width:760px){.info-inner{grid-template-columns:1fr}}
.info-left{position:sticky;top:24px}
.card{background:var(--sur);border:1px solid var(--bd);border-radius:var(--r);padding:22px;margin-bottom:14px;backdrop-filter:blur(10px)}
.brand-logo{width:44px;height:44px;border-radius:11px;background:linear-gradient(135deg,var(--acc),var(--vio));display:flex;align-items:center;justify-content:center;font-size:20px;margin-bottom:12px}
.brand-name{font-size:17px;font-weight:800;margin-bottom:4px}
.brand-sub{font-size:12px;color:var(--tx2);line-height:1.6}
.istats{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:14px}
.istat{background:var(--sur2);border-radius:var(--rs);padding:10px 12px;border:1px solid var(--bd)}
.isv{font-size:19px;font-weight:800;color:var(--acc2)}
.isl{font-size:10px;color:var(--tx2);margin-top:1px}
.rule-title{font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.6px;color:var(--tx3);margin-bottom:10px}
.ri{display:flex;gap:8px;margin-bottom:9px;font-size:12px;color:var(--tx2);line-height:1.55;align-items:flex-start}
.form-card{background:var(--sur);border:1px solid var(--bd);border-radius:var(--r);padding:24px;backdrop-filter:blur(10px)}
.fs-title{font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.6px;color:var(--tx3);margin:0 0 12px;padding-bottom:8px;border-bottom:1px solid var(--bd)}
.fdivider{height:1px;background:var(--bd);margin:16px 0}
.fg{margin-bottom:12px}
.fg label{display:flex;align-items:center;gap:5px;font-size:10px;font-weight:600;color:var(--tx3);text-transform:uppercase;letter-spacing:.4px;margin-bottom:5px}
.badge{background:rgba(244,63,94,.12);color:var(--red);border-radius:4px;padding:1px 5px;font-size:9px;font-weight:700;border:1px solid rgba(244,63,94,.2)}
.badge.opt{background:rgba(99,102,241,.1);color:var(--acc2);border-color:rgba(99,102,241,.2)}
.fg input,.fg select{width:100%;padding:9px 12px;background:var(--bg2);border:1.5px solid var(--bd2);border-radius:var(--rs);font-size:13px;outline:none;font-family:inherit;color:var(--tx);transition:border-color .2s}
.fg input::placeholder{color:var(--tx3)}
.fg input:focus,.fg select:focus{border-color:var(--acc);box-shadow:0 0 0 3px rgba(99,102,241,.18)}
.fg input.err-field{border-color:var(--red)!important}.fg input.ok-field{border-color:var(--grn)!important}
.fg select option{background:var(--bg3)}
.fgrid{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:460px){.fgrid{grid-template-columns:1fr}}
.err-msg{color:var(--red);font-size:11px;margin-top:4px;display:none;font-weight:500;align-items:center;gap:3px}
.err-msg.show{display:flex}.err-msg::before{content:'⚠ '}
.rgroup{display:flex;gap:7px;flex-wrap:wrap;margin-top:4px}
.ropt{display:flex;align-items:center;gap:6px;background:var(--bg2);border:1.5px solid var(--bd2);border-radius:var(--rs);padding:7px 11px;cursor:pointer;transition:all .2s;font-size:12px;color:var(--tx2)}
.ropt:has(input:checked){border-color:var(--acc);background:rgba(99,102,241,.1);color:var(--tx)}
.ropt input{accent-color:var(--acc);width:13px;height:13px}
.uzone{border:1.5px dashed var(--bd2);border-radius:var(--rs);padding:16px;text-align:center;cursor:pointer;transition:all .2s;background:var(--bg2)}
.uzone:hover{border-color:var(--acc);background:rgba(99,102,241,.05)}
.uzone .uicon{font-size:24px;margin-bottom:5px}
.uzone p{font-size:12px;color:var(--tx2)}
.uzone .uhint{font-size:10px;color:var(--tx3);margin-top:3px}
.uzone .ufile{font-size:11px;color:var(--grn);margin-top:4px;font-weight:600}
.cam-box{background:var(--bg2);border:1.5px solid var(--bd2);border-radius:var(--rs);padding:14px;display:flex;align-items:center;gap:12px;transition:all .2s}
.cam-box.ok{border-color:rgba(34,197,94,.4);background:rgba(34,197,94,.05)}
.cam-box.fail{border-color:rgba(244,63,94,.4);background:rgba(244,63,94,.05)}
.cam-box .cicon{font-size:26px;flex-shrink:0}
.cam-box h4{font-size:13px;font-weight:600;margin-bottom:2px}
.cam-box p{font-size:11px;color:var(--tx2);line-height:1.5}
.btn-start{width:100%;padding:13px;background:linear-gradient(135deg,var(--acc),var(--vio));color:#fff;border:none;border-radius:var(--rs);font-size:15px;font-weight:700;cursor:pointer;font-family:inherit;transition:all .2s;box-shadow:0 4px 20px rgba(99,102,241,.35);margin-top:2px}
.btn-start:hover{transform:translateY(-2px)}

/* ── HEADER ── */
.app-hdr{position:sticky;top:0;z-index:500;background:rgba(6,11,24,.9);backdrop-filter:blur(20px);border-bottom:1px solid var(--bd)}
.hdr-main{display:flex;align-items:center;justify-content:space-between;padding:10px 18px;gap:10px}
.hdr-left{display:flex;align-items:center;gap:10px;min-width:0}
.hdr-logo{width:30px;height:30px;border-radius:8px;flex-shrink:0;background:linear-gradient(135deg,var(--acc),var(--vio));display:flex;align-items:center;justify-content:center;font-size:15px}
.hdr-sec .sub{font-size:10px;color:var(--tx3);text-transform:uppercase;letter-spacing:.5px}
.hdr-sec .ttl{font-size:14px;font-weight:700}
.hdr-right{display:flex;align-items:center;gap:10px;flex-shrink:0}
.timer-ring{position:relative;width:52px;height:52px;flex-shrink:0}
.timer-ring svg{position:absolute;inset:0;transform:rotate(-90deg)}
.tr-bg{fill:none;stroke:var(--bd2);stroke-width:3}
.tr-fill{fill:none;stroke:var(--acc);stroke-width:3;stroke-linecap:round;transition:stroke-dashoffset .9s linear}
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

/* ── SECTION ── */
.sec-page{max-width:760px;margin:0 auto;padding:20px 16px 90px;position:relative;z-index:1}
.sec-hdr{margin-bottom:14px}
.sec-badge{display:inline-flex;align-items:center;background:rgba(99,102,241,.1);border:1px solid rgba(99,102,241,.22);color:var(--acc2);border-radius:20px;padding:3px 11px;font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;margin-bottom:8px}
.sec-title{font-size:22px;font-weight:800;margin-bottom:3px}
.sec-sub{font-size:13px;color:var(--tx2)}
.schema-card{background:rgba(56,189,248,.05);border:1px solid rgba(56,189,248,.2);border-radius:var(--r);padding:16px;margin-bottom:16px}
.schema-hdr{display:flex;align-items:center;justify-content:space-between;margin-bottom:12px;cursor:pointer}
.schema-hdr-l{font-size:12px;font-weight:700;color:var(--blu)}
.schema-toggle{font-size:11px;color:var(--tx3);background:var(--sur2);border:1px solid var(--bd);border-radius:6px;padding:3px 9px;cursor:pointer;font-family:inherit}
.schema-tables{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:520px){.schema-tables{grid-template-columns:1fr}}
.schema-table{background:var(--bg2);border-radius:var(--rs);overflow:hidden;border:1px solid var(--bd2)}
.st-name{background:var(--bg3);padding:7px 12px;font-size:11px;font-weight:800;color:var(--acc2);font-family:monospace;border-bottom:1px solid var(--bd)}
.st-col{display:flex;align-items:center;justify-content:space-between;padding:5px 12px;border-bottom:1px solid var(--bd);font-size:11px;font-family:monospace}
.st-col:last-child{border-bottom:none}
.st-col .cn{color:var(--tx)}.st-col .ct{color:var(--tx3);font-size:10px}
.ck{font-size:9px;background:rgba(99,102,241,.15);color:var(--acc2);border-radius:4px;padding:1px 5px;margin-left:5px}
.cfk{font-size:9px;background:rgba(245,158,11,.12);color:var(--amb);border-radius:4px;padding:1px 5px;margin-left:5px}
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
.btn-primary{background:linear-gradient(135deg,var(--acc),var(--vio));color:#fff}
.btn-primary:hover{transform:translateY(-1px)}
.btn-danger{background:rgba(244,63,94,.12);color:var(--red);border:1px solid rgba(244,63,94,.25)}
.qac{font-size:12px;color:var(--tx2);background:var(--sur2);padding:4px 11px;border-radius:20px;border:1px solid var(--bd)}
.qac.complete{color:var(--grn);border-color:rgba(34,197,94,.3);background:rgba(34,197,94,.06)}

/* ── LOADING + DONE ── */
.center-page{min-height:100vh;display:flex;align-items:center;justify-content:center;flex-direction:column;text-align:center;padding:40px;position:relative;z-index:1}
.lring{width:64px;height:64px;border-radius:50%;border:3px solid var(--bd2);border-top-color:var(--acc);animation:spin .8s linear infinite;margin:0 auto 18px}
@keyframes spin{to{transform:rotate(360deg)}}
.ldots{display:flex;gap:6px;justify-content:center;margin-top:14px}
.ldots span{width:6px;height:6px;border-radius:50%;background:var(--acc);animation:dot .8s ease-in-out infinite}
.ldots span:nth-child(2){animation-delay:.15s}.ldots span:nth-child(3){animation-delay:.3s}
@keyframes dot{0%,100%{opacity:.2;transform:scale(.8)}50%{opacity:1;transform:scale(1.2)}}
.done-card{background:var(--sur);border:1px solid var(--bd);border-radius:var(--r);padding:20px 28px;margin-top:22px;text-align:left;max-width:460px;width:100%}
.done-row{display:flex;justify-content:space-between;padding:7px 0;border-bottom:1px solid var(--bd);font-size:13px}
.done-row:last-child{border-bottom:none}
.done-row span:first-child{color:var(--tx3)}.done-row span:last-child{font-weight:600}
</style>
</head>
<body>
<div class="bgfx"></div>

<!-- ══ TERMINATION OVERLAY ══ -->
<div id="termination">
  <div class="ov-icon">🚫</div>
  <h1>Exam Terminated</h1>
  <p id="term-msg">A critical violation was detected. Your exam has been terminated and all data has been flagged for review.</p>
  <div class="ov-sub" id="term-sub">All responses collected so far have been saved and forwarded to the recruitment team.</div>
</div>

<!-- ══ TAB BLOCKER ══ -->
<div id="blocker">
  <div class="ov-badge" id="blk-n">1</div>
  <h2>⚠ Tab Switch Detected</h2>
  <p>This violation is permanently logged. Repeated violations may result in disqualification.</p>
  <button class="ov-btn" onclick="dismissBlocker()">I Understand — Resume Test</button>
</div>

<!-- ══ FACE VERIFY SCREEN ══ -->
<div id="face-verify">
  <h2 style="font-size:20px;font-weight:800">Identity Verification</h2>
  <p style="font-size:13px;color:var(--tx2);max-width:340px;line-height:1.65">
    We capture <strong>3 reference frames</strong> before your exam starts. These are used to continuously verify your identity throughout the test.
  </p>
  <video id="fv-video" autoplay muted playsinline></video>
  <!-- Progress dots for 3 captures -->
  <div class="fv-progress">
    <div class="fv-dot active" id="fv-dot-0"></div>
    <div class="fv-dot" id="fv-dot-1"></div>
    <div class="fv-dot" id="fv-dot-2"></div>
  </div>
  <div class="fv-status" id="fv-status">📷 Position your face clearly — good lighting recommended</div>
  <button class="fv-btn" id="fv-btn" onclick="captureNextBaseline()">📸 Capture Frame 1 of 3</button>
</div>

<!-- ══ PROCTOR ALERT (non-intrusive top banner) ══ -->
<div id="pa">
  <span class="pi">⚠️</span>
  <span class="pm" id="pa-msg">Please stay visible on camera.</span>
  <span class="px" onclick="hideAlert()">×</span>
</div>

<!-- ══ CAMERA PIP ══ -->
<div id="cam-pip">
  <div id="face-indicator" class="ok">✓ Face</div>
  <video id="camvid" autoplay muted playsinline></video>
  <div class="clabel ok" id="cam-label"><span class="dot grn"></span>LIVE</div>
</div>

<div id="toast"></div>
<div id="hdr-area"></div>
<div id="app"></div>
<canvas id="snap-canvas" style="display:none" width="640" height="480"></canvas>
<canvas id="motion-canvas" style="display:none" width="160" height="120"></canvas>

<script>
// ════════════════════════════════════════════════════════
//  CONFIG
// ════════════════════════════════════════════════════════
const BACKEND_URL = "https://script.google.com/macros/s/AKfycbzTVwXJUJ3wdli6w-q1BfAQ0axOeDumapnje-zkdK3rGH5E0OPj70g3Ld5k969mwWqz/exec";
const TOTAL_TIME  = 1800;     // 30 minutes
const CIRC        = 2 * Math.PI * 22;

// Proctor thresholds
const NO_FACE_WARN_MS   = 4000;   // show warning after 4s no face
const NO_FACE_TERM_MS   = 9000;   // terminate after 9s no face
const AI_COOLDOWN_MS    = 15000;  // min gap between AI calls
const MOTION_SPIKE_THR  = 6;      // motion score to trigger AI check
const MOTION_HIGH_THR   = 28;     // instant movement violation
const MOVE_COOLDOWN_MS  = 12000;  // gap between movement alerts
const BASELINE_COUNT    = 3;      // number of baseline frames to capture
const MISMATCH_LIMIT    = 2;      // consecutive mismatches before terminate

const DB_SCHEMA = [
  {name:'customers',cols:[{n:'customer_id',t:'INT',k:'PK'},{n:'name',t:'VARCHAR',k:''},{n:'email',t:'VARCHAR',k:''},{n:'phone',t:'VARCHAR',k:''},{n:'created_at',t:'DATE',k:''}]},
  {name:'orders',cols:[{n:'order_id',t:'INT',k:'PK'},{n:'customer_id',t:'INT',k:'FK'},{n:'amount',t:'DECIMAL',k:''},{n:'order_date',t:'DATE',k:''},{n:'status',t:'VARCHAR',k:''}]}
];

const SECTIONS = [
  {title:"CRM & Lead Management",short:"CRM",showSchema:false,
   questions:["You have 100 leads daily. Only 3 salespeople available. How will you distribute leads and why?","A customer filled the form 3 times with slightly different names. What will you do?","Leads are coming but not converting. List 3 possible reasons and what you'd check first.","Two salespeople contacted the same customer. How would you prevent this in a system?","You want every new lead to get a welcome email automatically. Explain the logic.","Some leads don't have phone numbers. What process would you put in place?","A lead becomes a paying customer. What data changes should happen?","Manager wants a daily report of new leads. What data would you include?"],
   hints:["Prioritization, fairness, lead scoring","Deduplication — email match, fuzzy name matching, merge strategy","CRM data quality, follow-up cadence, lead qualification","Lead ownership rules, assignment lock, activity tracking","Describe trigger → condition → action in plain logic","Validation at entry, enrichment tools, alternative channels","Status change, deal creation, contact record update","Count, source, stage, owner, conversion rate"]},
  {title:"SQL",short:"SQL",showSchema:true,
   questions:["Get all customers who placed at least one order. (Write SQL)","Find total amount spent by each customer. (Write SQL)","Find top 3 customers by total spend. (Write SQL)","Find customers who never placed any order. (Write SQL)","Get the latest order for each customer. (Write SQL)","Explain the difference between INNER JOIN and LEFT JOIN. (2–4 lines)","Why might GROUP BY give wrong results? (2–4 lines)","You see duplicate rows in query results. What could cause this? (2–4 lines)","Filter orders placed in the last 7 days. (Write SQL)","A query is running slow. What will you check first? (2–4 lines)"],
   hints:["Use JOIN or EXISTS/IN subquery","GROUP BY with SUM()","ORDER BY DESC with LIMIT 3","LEFT JOIN ... WHERE IS NULL, or NOT IN / NOT EXISTS","MAX(order_date) with GROUP BY or window function","What each returns when no match exists","Non-aggregated columns in SELECT","Missing DISTINCT, bad JOINs, duplicate source data","CURDATE() or NOW() - 7","Indexes, EXPLAIN plan, full table scan vs index scan"]},
  {title:"Python",short:"Python",showSchema:false,
   questions:["What is a list in Python? Give an example.","Given data=[1,2,2,3,4,4], return the frequency of each element. Explain your approach.","What is a dictionary? How is it different from a list?","What will this output and why?\n  a=[1,2,3]\n  b=a\n  b.append(4)\n  print(a)","You get a list of numbers. Return only the even ones. Explain your approach.","You have a list of numbers. Explain the logic to remove duplicates."],
   hints:["Include definition and a short code example","Loops, dict counter, or collections.Counter","Key-value pairs vs indexed sequence","References vs copies (mutable objects)","Modulo operator and list comprehension or filter()","Sets or a 'seen' tracking approach"]},
  {title:"Math & Aptitude",short:"Quant",showSchema:false,
   questions:["20% of a number is 80. Find the number. Show all steps.","A price increases by 10%, then decreases by 10%. Final impact? Show steps.","Boys to girls ratio = 2:3, total = 50. Find number of boys. Show steps.","Find the average of 10, 20, 30. Explain the steps.","Daily sales: 100, 200, 150, 250, 300. What is the average? Show steps.","Next number in: 2, 6, 12, 20, ? — Explain your reasoning."],
   hints:["Set up: (20/100)×N=80, solve for N","Start with ₹100, apply % changes one by one","Total parts=2+3=5, boys=(2/5)×50","Add all values, divide by count","Sum all 5 values, divide by 5","Look at differences: 4, 6, 8, 10 — what's the pattern?"]}
];

// ════════════════════════════════════════════════════════
//  STATE
// ════════════════════════════════════════════════════════
// PART 5: Unique session ID per exam attempt
const SESSION_ID = Date.now() + "_" + Math.random().toString(36).substr(2,9);

let appState     = 'pretest'; // pretest → info → faceVerify → section → submitting → done
let curSec       = 0;
let timeLeft     = TOTAL_TIME;
let timerInt     = null;
let submitted    = false;  // prevent double-submit
let terminated   = false;

let candidate    = {name:'',email:'',phone:'',location:'',linkedin:'',fulltime:'',startdate:'',isstudent:'',resumeName:'',resumeData:null};
let answers      = Array(30).fill('');

// Proctor state
let proctorActive      = false;
let proctorLog         = [];
let snapshots          = [];
let violations         = 0;
let camGranted         = false;
let camStream          = null;

// PART 3: Multiple baseline frames
let baselineFrames     = [];    // stores up to BASELINE_COUNT b64 strings
let baselineCaptureIdx = 0;     // which frame we're capturing next
let consecutiveMismatches = 0;  // counts identity mismatches before terminate

// PART 2: No-face timer
let noFaceStartTime    = null;  // timestamp when face first disappeared
let noFaceToldUser     = false; // so we only show the warning once per absence

// PART 4: AI call management
let isRunningAI        = false;
let lastAICallTime     = 0;
let aiQueued           = false;

// Motion / frame analysis state
let motionCtx          = null;
let lastFrameData      = null;
let motionInt          = null;
let periodicInt        = null;
let moveCooldownUntil  = 0;
let camBlockCooldownUntil = 0;

let schemaCollapsed    = false;

// ────────────────────────────────────────────────────────
// HELPERS
// ────────────────────────────────────────────────────────
const totalQ  = SECTIONS.reduce((a,s) => a + s.questions.length, 0);
function secOff(si){ return SECTIONS.slice(0,si).reduce((a,s)=>a+s.questions.length,0) }
function fmt(s){ return `${String(Math.floor(s/60)).padStart(2,'0')}:${String(s%60).padStart(2,'0')}` }
function now(){ return Date.now() }

function toast(msg, dur=2800){
  const t = document.getElementById('toast');
  t.textContent = msg; t.style.opacity = '1';
  setTimeout(() => t.style.opacity = '0', dur);
}

// ── Form validation helpers ──
function validateName(v) { return v.trim().length >= 2 && /^[a-zA-Z\s]+$/.test(v.trim()) }
function validatePhone(v){ return v.replace(/\D/g,'').length >= 10 }
function validateEmail(v){ return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(v.trim()) }

function onNameInput(el){
  const p=el.selectionStart; el.value=el.value.replace(/[^a-zA-Z\s]/g,'');
  try{el.setSelectionRange(p,p)}catch(e){}
  liveValidate(el,'err-name',validateName(el.value));
}
function onPhoneInput(el){
  const p=el.selectionStart; el.value=el.value.replace(/[^\d+\-\s]/g,'');
  try{el.setSelectionRange(p,p)}catch(e){}
  liveValidate(el,'err-phone',validatePhone(el.value));
}
function liveValidate(el,errId,valid){
  const em = document.getElementById(errId);
  if(!el.value.trim()){el.classList.remove('err-field','ok-field');if(em)em.classList.remove('show');return}
  if(valid){el.classList.remove('err-field');el.classList.add('ok-field');if(em)em.classList.remove('show')}
  else{el.classList.add('err-field');el.classList.remove('ok-field');if(em)em.classList.add('show')}
}
function clearFE(el){
  el.classList.remove('err-field','ok-field');
  const em = el.parentElement?.querySelector('.err-msg');
  if(em) em.classList.remove('show');
}

// ── Alert system (non-intrusive) ──
let alertTimeout = null;
function showAlert(msg, level='warn'){
  clearTimeout(alertTimeout);
  const el = document.getElementById('pa');
  const pm = document.getElementById('pa-msg');
  pm.textContent = msg;
  // Color the border based on severity
  el.style.borderColor = level === 'critical'
    ? 'rgba(244,63,94,.6)' : level === 'info'
    ? 'rgba(99,102,241,.5)' : 'rgba(245,158,11,.4)';
  el.style.display = 'flex';
  alertTimeout = setTimeout(hideAlert, level === 'critical' ? 18000 : 10000);
}
function hideAlert(){ document.getElementById('pa').style.display='none' }

// ── Update face indicator in PIP ──
function setFaceIndicator(status, label){
  const ind = document.getElementById('face-indicator');
  const lbl = document.getElementById('cam-label');
  if(!ind || !lbl) return;
  ind.className = `ok`;  // reset
  if(status === 'ok'){
    ind.className='ok'; ind.textContent='✓ Face';
    lbl.className='clabel ok'; lbl.innerHTML='<span class="dot grn"></span>LIVE';
    document.getElementById('cam-pip')?.classList.remove('no-face','blocked');
  } else if(status === 'miss'){
    ind.className='miss'; ind.textContent='✗ No Face';
    lbl.className='clabel warn'; lbl.innerHTML='<span class="dot amb"></span>NO FACE';
    document.getElementById('cam-pip')?.classList.add('no-face');
  } else if(status === 'blocked'){
    ind.className='warn'; ind.textContent='⚠ Blocked';
    lbl.className='clabel err'; lbl.innerHTML='<span class="dot red"></span>BLOCKED';
    document.getElementById('cam-pip')?.classList.add('blocked');
  }
}

// ════════════════════════════════════════════════════════
//  UPLOAD
// ════════════════════════════════════════════════════════
async function uploadToBackend(payload){
  if(!BACKEND_URL) return;
  try{
    await fetch(BACKEND_URL, {
      method:'POST', mode:'no-cors',
      headers:{'Content-Type':'text/plain'},
      body: JSON.stringify({...payload, sessionId: SESSION_ID})
    });
  } catch(e){ console.warn('Upload failed:', e.message) }
}

// ════════════════════════════════════════════════════════
//  SNAPSHOT — capture on violation only
// ════════════════════════════════════════════════════════
async function captureSnapshot(reason){
  const v = document.getElementById('camvid');
  if(!v || !v.srcObject || v.readyState < 2) return null;
  return new Promise(resolve => {
    requestAnimationFrame(() => {
      try{
        const c = document.getElementById('snap-canvas');
        const ctx = c.getContext('2d');
        // Mirror flip to natural orientation
        ctx.save(); ctx.scale(-1,1); ctx.drawImage(v,-640,0,640,480); ctx.restore();
        // Burn label onto image
        ctx.fillStyle='rgba(0,0,0,.7)'; ctx.fillRect(0,0,640,30);
        ctx.fillStyle='#fff'; ctx.font='bold 13px monospace';
        ctx.fillText(`${new Date().toLocaleString('en-IN')} | ${reason} | ${candidate.name} | ${SESSION_ID}`,8,20);
        const img = c.toDataURL('image/jpeg', .82);
        const ts  = new Date().toLocaleTimeString('en-IN');
        snapshots.push({time:ts, reason, img});
        const fname = `${candidate.name.replace(/\s+/g,'_')}_${reason.replace(/[\s/]/g,'_')}_${Date.now()}.jpg`;
        uploadToBackend({type:'snapshot', candidateName:candidate.name, candidateEmail:candidate.email,
          timestamp:ts, reason, fileName:fname, mimeType:'image/jpeg', fileData:img.split(',')[1]});
        resolve(img);
      }catch(e){ console.warn('Snapshot err:',e); resolve(null) }
    });
  });
}

// ════════════════════════════════════════════════════════
//  PART 3: FACE VERIFICATION — 3 baseline frames
// ════════════════════════════════════════════════════════
async function showFaceVerify(){
  document.getElementById('face-verify').style.display='flex';
  // Camera should already be running from info page
  const fvv = document.getElementById('fv-video');
  fvv.srcObject = camStream;
  await new Promise(r=>{fvv.onloadedmetadata=r});
  document.getElementById('fv-status').textContent='📷 Position your face clearly — good lighting recommended';
  document.getElementById('fv-btn').style.display='inline-flex';
}

async function captureNextBaseline(){
  const v   = document.getElementById('fv-video');
  const btn = document.getElementById('fv-btn');
  if(!v || !v.srcObject) return;
  btn.disabled = true;
  const idx = baselineCaptureIdx;
  document.getElementById('fv-status').textContent = `📸 Capturing frame ${idx+1}…`;
  await new Promise(r => setTimeout(r, 350)); // let frame settle

  await new Promise(resolve => {
    requestAnimationFrame(() => {
      const c = document.getElementById('snap-canvas');
      const ctx = c.getContext('2d');
      ctx.save(); ctx.scale(-1,1); ctx.drawImage(v,-640,0,640,480); ctx.restore();
      ctx.fillStyle='rgba(0,0,0,.65)'; ctx.fillRect(0,0,640,28);
      ctx.fillStyle='#fff'; ctx.font='bold 12px monospace';
      ctx.fillText(`BASELINE ${idx+1}/${BASELINE_COUNT} | ${new Date().toLocaleString('en-IN')} | ${candidate.name}`,8,19);
      const img = c.toDataURL('image/jpeg', .88);
      baselineFrames.push(img.split(',')[1]);
      // Mark dot as captured
      document.getElementById(`fv-dot-${idx}`)?.classList.replace('active','captured');
      baselineCaptureIdx++;
      // Upload this baseline
      uploadToBackend({type:'snapshot', candidateName:candidate.name, candidateEmail:candidate.email,
        timestamp:new Date().toLocaleTimeString('en-IN'), reason:`baseline_${idx+1}`,
        fileName:`${candidate.name.replace(/\s+/g,'_')}_BASELINE${idx+1}_${Date.now()}.jpg`,
        mimeType:'image/jpeg', fileData:img.split(',')[1]});
      resolve();
    });
  });

  if(baselineCaptureIdx < BASELINE_COUNT){
    // Activate next dot
    document.getElementById(`fv-dot-${baselineCaptureIdx}`)?.classList.add('active');
    document.getElementById('fv-status').textContent = `✅ Frame ${idx+1} saved — now capture frame ${baselineCaptureIdx+1}`;
    btn.textContent = `📸 Capture Frame ${baselineCaptureIdx+1} of ${BASELINE_COUNT}`;
    btn.disabled = false;
  } else {
    // All baselines captured — start exam
    document.getElementById('fv-status').textContent = '✅ All frames captured — starting exam…';
    await new Promise(r => setTimeout(r, 700));
    document.getElementById('face-verify').style.display = 'none';
    beginExam();
  }
}

// ════════════════════════════════════════════════════════
//  PROCTOR SETUP
// ════════════════════════════════════════════════════════
function activateProctor(){
  proctorActive = true;

  // Tab switch detection
  document.addEventListener('visibilitychange', () => {
    if(document.hidden && proctorActive && !terminated){
      violations++;
      captureSnapshot('tab_switch');
      showBlocker();
    }
  });

  // Window blur detection
  window.addEventListener('blur', () => {
    if(proctorActive && !terminated){
      violations++;
      captureSnapshot('window_blur');
      showBlocker();
    }
  });

  // Block right-click and devtools shortcuts
  document.addEventListener('contextmenu', e => { if(proctorActive) e.preventDefault() });
  document.addEventListener('keydown', e => {
    if(!proctorActive) return;
    const blocked = (e.ctrlKey||e.metaKey) && ['c','v','a','u','s','p'].includes(e.key.toLowerCase());
    const devtools = e.key==='F12' || (e.ctrlKey&&e.shiftKey&&['i','j','c'].includes(e.key.toLowerCase()));
    if(blocked || devtools) e.preventDefault();
  });
}

function showBlocker(){ document.getElementById('blk-n').textContent=violations; document.getElementById('blocker').style.display='flex' }
function dismissBlocker(){ document.getElementById('blocker').style.display='none' }

// ── Termination ──
async function terminateExam(reason, msg){
  if(terminated) return;
  terminated = true;
  proctorActive = false;
  clearInterval(timerInt);
  await captureSnapshot('TERMINATION_' + reason);
  await submitData(true, reason);
  stopCam();
  document.getElementById('term-msg').textContent = msg;
  document.getElementById('termination').style.display = 'flex';
}

// ════════════════════════════════════════════════════════
//  PART 2: NO-FACE TIMER — called after each AI result
// ════════════════════════════════════════════════════════
function handleFacePresence(faceCount){
  const t = now();
  if(faceCount === 0){
    // Start absence timer if not already started
    if(!noFaceStartTime) noFaceStartTime = t;
    const absentMs = t - noFaceStartTime;

    // Show warning after NO_FACE_WARN_MS
    if(absentMs >= NO_FACE_WARN_MS && !noFaceToldUser){
      noFaceToldUser = true;
      setFaceIndicator('miss');
      showAlert('❌ Face not visible — adjust camera immediately. Exam will terminate in a few seconds.', 'critical');
    }

    // Terminate after NO_FACE_TERM_MS
    if(absentMs >= NO_FACE_TERM_MS){
      proctorLog.push({time:new Date().toLocaleTimeString('en-IN'), type:'no_face_timeout', msg:`Face absent for ${Math.round(absentMs/1000)}s — terminated`});
      terminateExam('no_face', `Your face was not visible for over ${Math.round(NO_FACE_TERM_MS/1000)} seconds. This is a serious violation. The exam has been terminated.`);
    }
  } else {
    // Face returned — reset timers
    noFaceStartTime = null;
    noFaceToldUser  = false;
    setFaceIndicator('ok');
  }
}

// ════════════════════════════════════════════════════════
//  FRAME ANALYSIS + MOTION DETECTION
// ════════════════════════════════════════════════════════
function analyzeFrameBrightness(imageData){
  const n = imageData.data.length / 4;
  let rS=0, gS=0, bS=0;
  for(let i=0; i<imageData.data.length; i+=4){ rS+=imageData.data[i]; gS+=imageData.data[i+1]; bS+=imageData.data[i+2] }
  const rA=rS/n, gA=gS/n, bA=bS/n, br=(rA+gA+bA)/3;
  let mad=0;
  for(let i=0; i<imageData.data.length; i+=4){ mad+=Math.abs(imageData.data[i]-rA)+Math.abs(imageData.data[i+1]-gA)+Math.abs(imageData.data[i+2]-bA) }
  return { brightness: br, mad: mad/(n*3) };
}

function computeMotionScore(curr, prev){
  let diff=0, cnt=0;
  for(let i=0; i<curr.data.length; i+=4){
    diff += Math.abs(curr.data[i]-prev[i]) + Math.abs(curr.data[i+1]-prev[i+1]) + Math.abs(curr.data[i+2]-prev[i+2]);
    cnt++;
  }
  return diff / (cnt * 3);
}

function startMotionDetection(){
  const mc = document.getElementById('motion-canvas');
  motionCtx = mc.getContext('2d', {willReadFrequently:true});

  motionInt = setInterval(() => {
    if(terminated) return;
    const v = document.getElementById('camvid');
    if(!v || !v.srcObject || v.readyState < 2) return;
    try{
      motionCtx.drawImage(v, 0, 0, 160, 120);
      const curr = motionCtx.getImageData(0, 0, 160, 120);
      const {brightness, mad} = analyzeFrameBrightness(curr);

      // ── Camera block detection ──
      const isBlocked = mad < 7 || brightness < 18;
      if(isBlocked){
        setFaceIndicator('blocked');
        if(now() > camBlockCooldownUntil){
          camBlockCooldownUntil = now() + 20000;
          proctorLog.push({time:new Date().toLocaleTimeString('en-IN'), type:'camera_blocked', msg:'Camera blocked or covered'});
          captureSnapshot('camera_blocked');
          showAlert('🚫 Camera is blocked — uncover immediately. This is a major violation.', 'critical');
        }
      }

      // ── Motion score ──
      if(lastFrameData && !isBlocked){
        const motionScore = computeMotionScore(curr, lastFrameData);

        // Low motion spike → schedule AI check
        if(motionScore > MOTION_SPIKE_THR) scheduleAICheck('motion_spike');

        // High motion → instant violation snapshot
        if(motionScore > MOTION_HIGH_THR && now() > moveCooldownUntil){
          moveCooldownUntil = now() + MOVE_COOLDOWN_MS;
          proctorLog.push({time:new Date().toLocaleTimeString('en-IN'), type:'excessive_movement', msg:'High movement detected'});
          captureSnapshot('excessive_movement');
          showAlert('⚠️ Significant movement detected — please remain seated and focused.');
        }
      }

      lastFrameData = new Uint8ClampedArray(curr.data);
    }catch(e){}
  }, 500);

  // PART 4: Periodic AI check every 30–45s
  periodicInt = setInterval(() => {
    if(!isRunningAI && !terminated) scheduleAICheck('periodic');
  }, 35000);
}

// ── AI call scheduling with cooldown ──
function scheduleAICheck(trigger){
  if(terminated) return;
  // PART 4: enforce 15s cooldown between AI calls
  if(now() - lastAICallTime < AI_COOLDOWN_MS){
    aiQueued = true; // will fire after cooldown
    return;
  }
  if(isRunningAI){
    aiQueued = true;
    return;
  }
  runProctorAI(trigger);
}

// ════════════════════════════════════════════════════════
//  PART 3+4: AI PROCTOR — identity matching + violation detection
// ════════════════════════════════════════════════════════
async function runProctorAI(trigger){
  if(!camGranted || !proctorActive || isRunningAI || terminated) return;
  isRunningAI    = true;
  lastAICallTime = now();
  aiQueued       = false;

  // Capture current frame
  const v = document.getElementById('camvid');
  if(!v || !v.srcObject || v.readyState < 2){ isRunningAI=false; return }
  const tmp = document.createElement('canvas'); tmp.width=320; tmp.height=240;
  const tctx = tmp.getContext('2d');
  tctx.save(); tctx.scale(-1,1); tctx.drawImage(v,-320,0,320,240); tctx.restore();
  const currentB64 = tmp.toDataURL('image/jpeg',.65).split(',')[1];

  try{
    // Build message content: include ALL baseline frames for comparison
    const content = [];

    if(baselineFrames.length > 0){
      // Add all baseline images first
      baselineFrames.forEach((b64, i) => {
        content.push({type:'image', source:{type:'base64', media_type:'image/jpeg', data:b64}});
      });
      content.push({type:'image', source:{type:'base64', media_type:'image/jpeg', data:currentB64}});
      content.push({type:'text', text:
        `First ${baselineFrames.length} image(s) = BASELINE reference photos of the registered candidate.
Last image = CURRENT live camera frame [trigger: ${trigger}].

Compare the face in the CURRENT frame against ALL baseline photos.
Return ONLY this JSON (no markdown):
{"face_count":0,"same_person":true,"multiple_people":false,"phone_or_notes":false,"phone_near_ear":false,"left_seat":false,"looking_away":false,"suspicious":false,"type":"none","msg":""}`
      });
    } else {
      // No baseline yet — basic check only
      content.push({type:'image', source:{type:'base64', media_type:'image/jpeg', data:currentB64}});
      content.push({type:'text', text:
        `Proctor check [${trigger}]. Return ONLY JSON:
{"face_count":0,"same_person":true,"multiple_people":false,"phone_or_notes":false,"phone_near_ear":false,"left_seat":false,"looking_away":false,"suspicious":false,"type":"none","msg":""}`
      });
    }

    const body = JSON.stringify({model:'claude-sonnet-4-20250514', max_tokens:160, messages:[{role:'user', content}]});
    const hdrs = {'Content-Type':'application/json','anthropic-version':'2023-06-01','anthropic-dangerous-direct-browser-calls':'true'};
    let pr;
    try{ pr = await fetch('https://api.anthropic.com/v1/messages',{method:'POST',headers:hdrs,body}) }
    catch(e){ pr = await fetch('https://corsproxy.io/?https://api.anthropic.com/v1/messages',{method:'POST',headers:hdrs,body}) }
    const pd = await pr.json();
    const r  = JSON.parse((pd.content?.[0]?.text||'{}').replace(/```json|```/g,'').trim());

    // ── Face presence check (feeds no-face timer) ──
    handleFacePresence(r.face_count ?? 1);

    // ── CRITICAL: Identity mismatch → accumulate + terminate ──
    if(baselineFrames.length > 0 && r.same_person === false && r.face_count > 0){
      consecutiveMismatches++;
      proctorLog.push({time:new Date().toLocaleTimeString('en-IN'), type:'identity_mismatch', msg:`Mismatch ${consecutiveMismatches}/${MISMATCH_LIMIT}`});
      captureSnapshot('identity_mismatch');
      if(consecutiveMismatches >= MISMATCH_LIMIT){
        // TERMINATE
        terminateExam('identity_mismatch', 'A different person was detected on camera during identity verification. This is a critical violation. Your exam has been terminated and this incident has been reported to the recruitment team.');
        return;
      } else {
        // First mismatch — strong warning, not yet terminated (tolerance for lighting/angle)
        showAlert('🚨 Identity mismatch detected. If this continues the exam will be terminated.', 'critical');
      }
    } else if(r.same_person !== false){
      consecutiveMismatches = 0; // reset on valid match
    }

    // ── Other violations ──
    let vmsg = '';
    if(r.multiple_people){ vmsg='Multiple people detected — serious violation.'; captureSnapshot('multiple_people') }
    else if(r.phone_near_ear){ vmsg='Phone usage near ear detected — unauthorized.'; captureSnapshot('phone_near_ear') }
    else if(r.phone_or_notes){ vmsg='Unauthorized materials detected — remove immediately.'; captureSnapshot('unauthorized_materials') }
    else if(r.left_seat){ vmsg='You appear to have left your seat.'; captureSnapshot('left_seat') }
    else if(r.looking_away){ vmsg='Please keep your eyes on the screen.' }
    else if(r.suspicious && r.msg){ vmsg=r.msg; captureSnapshot('suspicious') }

    if(vmsg){
      proctorLog.push({time:new Date().toLocaleTimeString('en-IN'), type:r.type||'ai_flag', msg:vmsg});
      showAlert('⚠️ '+vmsg);
    }
  }catch(e){ console.warn('AI proctor error:', e.message) }
  finally{
    isRunningAI = false;
    // Fire queued check after cooldown
    if(aiQueued) setTimeout(() => scheduleAICheck('queued'), AI_COOLDOWN_MS);
  }
}

// ════════════════════════════════════════════════════════
//  CAMERA
// ════════════════════════════════════════════════════════
async function startCam(){
  try{
    camStream = await navigator.mediaDevices.getUserMedia({video:{width:640,height:480,facingMode:'user'}, audio:false});
    const v = document.getElementById('camvid'); v.srcObject = camStream;
    await new Promise(r=>{v.onloadedmetadata=r});
    document.getElementById('cam-pip').style.display='block';
    camGranted = true; updateCamUI(true);
  }catch(e){ camGranted=false; updateCamUI(false) }
}
function updateCamUI(ok){
  const el = document.getElementById('cam-status-box'); if(!el) return;
  el.className = 'cam-box ' + (ok?'ok':'fail');
  el.innerHTML = ok
    ? `<div class="cicon">📷</div><div><h4 style="color:var(--grn)">Camera active</h4><p>3-frame identity baseline will be captured before exam starts.</p></div>`
    : `<div class="cicon">📷</div><div><h4 style="color:var(--red)">Camera denied</h4><p>Camera is required.<br><button class="btn btn-ghost" style="margin-top:6px;font-size:11px;padding:5px 12px" onclick="startCam()">Try Again</button></p></div>`;
}
function stopCam(){
  clearInterval(motionInt); clearInterval(periodicInt);
  if(camStream) camStream.getTracks().forEach(t=>t.stop());
  document.getElementById('cam-pip').style.display='none';
}

// ════════════════════════════════════════════════════════
//  TIMER
// ════════════════════════════════════════════════════════
function startTimer(){
  timerInt = setInterval(() => {
    if(terminated) return;
    timeLeft--;
    const warn   = timeLeft < 600;
    const offset = CIRC * (1 - timeLeft/TOTAL_TIME);
    const fill   = document.getElementById('tr-fill');
    const txt    = document.getElementById('timer-txt');
    if(fill){ fill.style.strokeDashoffset=offset; fill.className='tr-fill'+(warn?' warn':'') }
    if(txt){ txt.textContent=fmt(timeLeft); txt.className='timer-inner'+(warn?' warn':'') }
    if(timeLeft <= 0){ clearInterval(timerInt); doSubmit() }
    if(timeLeft % 60 === 0) autoSave();
  }, 1000);
}
function autoSave(){ try{ sessionStorage.setItem('zass', JSON.stringify(answers)) }catch(e){} }

// ════════════════════════════════════════════════════════
//  RENDER ENGINE
// ════════════════════════════════════════════════════════
function render(){ renderHdr(); renderApp() }

function renderHdr(){
  const ha = document.getElementById('hdr-area');
  if(appState !== 'section'){ ha.innerHTML=''; return }
  const sec  = SECTIONS[curSec];
  const pct  = Math.round((secOff(curSec)/totalQ)*100);
  const pills = SECTIONS.map((s,i) =>
    `<button class="spill ${i<curSec?'done':i===curSec?'active':''}" onclick="jumpToSection(${i})">${i+1}. ${s.short}</button>`
  ).join('');
  ha.innerHTML=`<div class="app-hdr">
    <div class="hdr-main">
      <div class="hdr-left"><div class="hdr-logo">🧩</div><div class="hdr-sec"><div class="sub">Section ${curSec+1}/4</div><div class="ttl">${sec.title}</div></div></div>
      <div class="hdr-right">
        ${camGranted?`<div style="display:flex;align-items:center;gap:5px;font-size:11px;color:var(--grn)"><span class="dot grn"></span>Monitored</div>`:''}
        <div class="timer-ring"><svg viewBox="0 0 56 56" width="52" height="52"><circle class="tr-bg" cx="28" cy="28" r="22"/><circle id="tr-fill" class="tr-fill" cx="28" cy="28" r="22" stroke-dasharray="${CIRC} ${CIRC}" stroke-dashoffset="${CIRC*(1-timeLeft/TOTAL_TIME)}"/></svg><div id="timer-txt" class="timer-inner">${fmt(timeLeft)}</div></div>
      </div>
    </div>
    <div class="pbar"><div class="pbar-fill" style="width:${pct}%"></div></div>
    <div class="sec-pills">${pills}</div>
  </div>`;
}

function renderApp(){
  const app = document.getElementById('app');
  if(appState==='pretest')  app.innerHTML = renderPretest();
  else if(appState==='info')     app.innerHTML = renderInfo();
  else if(appState==='section')  app.innerHTML = renderSection();
  else if(appState==='submitting') app.innerHTML = renderSubmitting();
  else if(appState==='done')    app.innerHTML = renderDone();
}

// ════════════════════════════════════════════════════════
//  PART 6: PRE-TEST SCREEN
// ════════════════════════════════════════════════════════
function renderPretest(){ return`<div class="pretest-page"><div class="pretest-inner">
  <div class="pretest-logo">🧩</div>
  <div style="font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:1px;color:var(--acc2);margin-bottom:8px">Zoho Developer Internship</div>
  <div class="pretest-title">AI-Proctored Assessment</div>
  <div class="pretest-sub">Before you begin, read the following carefully. This is a monitored test — all activity is logged.</div>
  <div class="pretest-rules">
    <div class="pr-item"><span class="pr-icon">📸</span><div><b>Identity Baseline (3 frames)</b>Your photo is captured in 3 frames before the exam. AI continuously compares live frames to verify it's you.</div></div>
    <div class="pr-item"><span class="pr-icon">🚫</span><div><b>Immediate Termination</b>A different person on camera = instant termination. Face absent for 9+ seconds = instant termination.</div></div>
    <div class="pr-item"><span class="pr-icon">🔒</span><div><b>Tab & Window Monitoring</b>Every tab switch or window blur is logged and photographed.</div></div>
    <div class="pr-item"><span class="pr-icon">📷</span><div><b>Violation Snapshots</b>Photos are taken automatically on any violation and stored with timestamps.</div></div>
    <div class="pr-item"><span class="pr-icon">📋</span><div><b>30 Questions · 30 Minutes</b>4 sections: CRM, SQL, Python, Aptitude. Answer what you can — no question is mandatory.</div></div>
  </div>
  <div class="checklist">
    <div class="cl-item"><input type="checkbox" id="ck1" onchange="checkProceed()"><label for="ck1">I am in a well-lit room with my face clearly visible</label></div>
    <div class="cl-item"><input type="checkbox" id="ck2" onchange="checkProceed()"><label for="ck2">I am alone — no other person is present</label></div>
    <div class="cl-item"><input type="checkbox" id="ck3" onchange="checkProceed()"><label for="ck3">I will not use my phone or any other device</label></div>
    <div class="cl-item"><input type="checkbox" id="ck4" onchange="checkProceed()"><label for="ck4">I understand violations are photographed and reported</label></div>
  </div>
  <button class="btn-pretest" id="proceed-btn" disabled onclick="goToInfo()">I Agree — Proceed to Registration →</button>
</div></div>` }

function checkProceed(){
  const all = ['ck1','ck2','ck3','ck4'].every(id => document.getElementById(id)?.checked);
  const btn = document.getElementById('proceed-btn');
  if(btn) btn.disabled = !all;
}
function goToInfo(){ appState='info'; render(); window.scrollTo(0,0) }

// ════════════════════════════════════════════════════════
//  INFO / REGISTRATION
// ════════════════════════════════════════════════════════
function renderInfo(){ return`<div class="info-page"><div class="info-inner">
  <div class="info-left">
    <div class="card">
      <div class="brand-logo">🧩</div>
      <div class="brand-name">Zoho Developer Intern</div>
      <div class="brand-sub">Complete your registration below. All fields marked Required must be filled.</div>
      <div class="istats">
        <div class="istat"><div class="isv">4</div><div class="isl">Sections</div></div>
        <div class="istat"><div class="isv">30</div><div class="isl">Questions</div></div>
        <div class="istat"><div class="isv">30m</div><div class="isl">Time Limit</div></div>
        <div class="istat"><div class="isv">📷</div><div class="isl">Proctored</div></div>
      </div>
    </div>
    <div class="card" style="padding:18px">
      <div class="rule-title">Reminders</div>
      <div class="ri">📸 3-frame baseline photo taken before exam starts</div>
      <div class="ri">🤖 AI monitors identity every 30–35 seconds</div>
      <div class="ri">🚫 Face absent 9s or identity mismatch = termination</div>
      <div class="ri">✏️ Answer as many questions as you can — no question is mandatory</div>
    </div>
  </div>
  <div class="form-card">
    <div class="fs-title">Personal Information</div>
    <div class="fgrid">
      <div class="fg"><label>Full Name <span class="badge">Required</span></label>
        <input type="text" id="cname" placeholder="e.g. Sagar Ganatra" oninput="onNameInput(this)">
        <div class="err-msg" id="err-name">Letters only, minimum 2 characters</div></div>
      <div class="fg"><label>Email Address <span class="badge">Required</span></label>
        <input type="email" id="cemail" placeholder="you@email.com" oninput="liveValidate(this,'err-email',validateEmail(this.value))">
        <div class="err-msg" id="err-email">Enter a valid email address</div></div>
    </div>
    <div class="fgrid">
      <div class="fg"><label>Phone Number <span class="badge">Required</span></label>
        <input type="tel" id="cphone" placeholder="9876543210" oninput="onPhoneInput(this)" maxlength="15">
        <div class="err-msg" id="err-phone">Enter a valid 10-digit number</div></div>
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
    <div id="cam-status-box" class="cam-box">
      <div class="cicon">📷</div>
      <div><h4>Camera access required</h4>
        <p>3 reference frames will be captured before the exam begins for identity verification.<br>
        <button class="btn btn-ghost" style="margin-top:7px;font-size:12px;padding:6px 14px" onclick="startCam()">Enable Camera</button></p>
      </div>
    </div>
    <div class="err-msg" id="err-cam" style="margin-top:5px">Camera access is required to proceed</div>
    <div class="fdivider"></div>
    <button class="btn-start" onclick="validateAndProceed()">Continue to Identity Verification →</button>
  </div>
</div></div>` }

function handleResume(e){
  const f = e.target.files[0]; if(!f) return;
  if(f.size > 5*1024*1024){ toast('File too large — max 5 MB'); return }
  candidate.resumeName = f.name;
  const r = new FileReader(); r.onload=()=>{candidate.resumeData=r.result}; r.readAsDataURL(f);
  document.getElementById('rfile-name').textContent = '✓ '+f.name;
  document.getElementById('err-resume').classList.remove('show');
}

function validateAndProceed(){
  document.querySelectorAll('.err-msg').forEach(e=>e.classList.remove('show'));
  document.querySelectorAll('.err-field').forEach(e=>e.classList.remove('err-field'));
  let ok = true;
  const n  = document.getElementById('cname').value.trim();
  const em = document.getElementById('cemail').value.trim();
  const ph = document.getElementById('cphone').value.trim();
  const lo = document.getElementById('cloc').value.trim();
  const ft = document.querySelector('input[name=fulltime]:checked');
  const st = document.getElementById('cstart').value;
  const is = document.querySelector('input[name=isstudent]:checked');
  function fe(id,fid){const e=document.getElementById(id);if(e)e.classList.add('show');if(fid){const f=document.getElementById(fid);if(f)f.classList.add('err-field')}ok=false}
  if(!validateName(n)) fe('err-name','cname');
  if(!validateEmail(em)) fe('err-email','cemail');
  if(!validatePhone(ph)) fe('err-phone','cphone');
  if(!lo) fe('err-loc','cloc');
  if(!ft) fe('err-ft',null);
  if(!st) fe('err-start','cstart');
  if(!is) fe('err-st',null);
  if(!candidate.resumeData) fe('err-resume',null);
  if(!camGranted) fe('err-cam',null);
  if(!ok){ document.querySelector('.err-msg.show')?.scrollIntoView({behavior:'smooth',block:'center'}); return }
  candidate = {...candidate, name:n, email:em, phone:ph, location:lo,
    linkedin: document.getElementById('clinkedin').value.trim(),
    fulltime:ft.value, startdate:st, isstudent:is.value};
  showFaceVerify();
}

function beginExam(){
  try{const s=sessionStorage.getItem('zass');if(s)answers=JSON.parse(s)}catch(e){}
  document.getElementById('cam-pip').style.display='block';
  activateProctor();
  startMotionDetection();
  // Initial AI check 3s after exam starts
  setTimeout(() => scheduleAICheck('exam_start'), 3000);
  appState='section'; curSec=0; startTimer(); render(); window.scrollTo(0,0);
}

// ════════════════════════════════════════════════════════
//  SECTION
// ════════════════════════════════════════════════════════
function renderSection(){
  const sec     = SECTIONS[curSec];
  const off     = secOff(curSec);
  const isLast  = curSec === SECTIONS.length-1;
  const answered = answers.slice(off, off+sec.questions.length).filter(a=>a&&a.trim()).length;

  let schemaHTML = '';
  if(sec.showSchema){
    const tables = DB_SCHEMA.map(t=>`<div class="schema-table"><div class="st-name">📋 ${t.name}</div>${t.cols.map(c=>`<div class="st-col"><span class="cn">${c.n}</span><span style="display:flex;align-items:center">${c.k==='PK'?`<span class="ck">PK</span>`:c.k==='FK'?`<span class="cfk">FK</span>`:''}<span class="ct">${c.t}</span></span></div>`).join('')}</div>`).join('');
    schemaHTML=`<div class="schema-card ${schemaCollapsed?'schema-collapsed':''}">
      <div class="schema-hdr" onclick="schemaCollapsed=!schemaCollapsed;renderApp()">
        <div class="schema-hdr-l">🗃 Database Schema Reference</div>
        <button class="schema-toggle">${schemaCollapsed?'Show ↓':'Hide ↑'}</button>
      </div>
      <div class="schema-tables">${tables}</div>
      <div class="schema-note">Use these exact table and column names in your queries.</div>
    </div>`;
  }

  const qs = sec.questions.map((q,i)=>{
    const absIdx = off+i, ans = answers[absIdx]||'';
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
      <span class="qac ${answered===sec.questions.length?'complete':''}">${answered}/${sec.questions.length} answered</span>
    </div>
    <div class="nfr">
      ${isLast
        ?`<button class="btn btn-danger" onclick="doSubmit()">Submit Assessment ✓</button>`
        :`<button class="btn btn-primary" onclick="nextSection()">Next Section →</button>`}
    </div>
  </div>`;
}

function onTaInput(el,i){
  const off = secOff(curSec); answers[off+i]=el.value;
  const cc = document.getElementById('cc'+i); if(cc) cc.textContent=el.value.length+' chars';
  autoSave();
}
function saveAns(){ const off=secOff(curSec); SECTIONS[curSec].questions.forEach((_,i)=>{const ta=document.getElementById('ta'+i);if(ta)answers[off+i]=ta.value}) }
function nextSection(){ saveAns(); curSec++; render(); window.scrollTo(0,0) }
function goBack(){ if(curSec===0)return; saveAns(); curSec--; render(); window.scrollTo(0,0) }
function jumpToSection(i){ if(i===curSec)return; saveAns(); curSec=i; render(); window.scrollTo(0,0) }

// ════════════════════════════════════════════════════════
//  SUBMIT
// ════════════════════════════════════════════════════════
function renderSubmitting(){ return`<div class="center-page">
  <div class="lring"></div>
  <h2 style="font-size:22px;font-weight:800;margin-bottom:8px">Submitting your responses…</h2>
  <p style="color:var(--tx2);font-size:14px;max-width:360px;line-height:1.7">Please wait while we securely upload your answers and proctor data.</p>
  <div class="ldots"><span></span><span></span><span></span></div>
</div>` }

async function submitData(isTerminated=false, terminationReason=''){
  saveAns();
  const violationSummary = proctorLog.map((l,i)=>`${i+1}. [${l.time}] ${l.type} — ${l.msg}`).join('\n') || 'None';
  const snapshotLog      = snapshots.map((s,i)=>`${i+1}. [${s.time}] ${s.reason}`).join('\n') || 'None';
  const payload = {
    type:'response', sessionId:SESSION_ID,
    timestamp:new Date().toLocaleString('en-IN'),
    name:candidate.name, email:candidate.email, phone:candidate.phone,
    location:candidate.location, linkedin:candidate.linkedin||'—',
    fulltime:candidate.fulltime, startdate:candidate.startdate, isstudent:candidate.isstudent,
    timeTaken:fmt(TOTAL_TIME-timeLeft),
    questionsAnswered:answers.filter(a=>a&&a.trim()).length,
    tabViolations:violations,
    proctorEventCount:proctorLog.length,
    snapshotCount:snapshots.length,
    baselinesCaptured:baselineFrames.length,
    terminated:isTerminated?'YES':'NO',
    terminationReason:terminationReason||'—',
    violationSummary, snapshotLog,
    ...Object.fromEntries(answers.map((a,i)=>[`Q${i+1}`,a||'']))
  };
  await uploadToBackend(payload);
  if(candidate.resumeData){
    const ext = candidate.resumeName.split('.').pop().toLowerCase();
    await uploadToBackend({type:'resume',
      fileName:`${candidate.name.replace(/\s+/g,'_')}_resume.${ext}`,
      fileData:candidate.resumeData.split(',')[1],
      mimeType:ext==='pdf'?'application/pdf':'application/msword',
      candidateName:candidate.name, candidateEmail:candidate.email});
  }
  try{ sessionStorage.removeItem('zass') }catch(e){}
}

// PART 5: Submit guard — prevent double-submit
async function doSubmit(){
  if(submitted || terminated) return;
  submitted = true;
  clearInterval(timerInt); proctorActive=false;
  appState='submitting'; render();
  await submitData(false);
  stopCam();
  appState='done'; render(); window.scrollTo(0,0);
}

// ════════════════════════════════════════════════════════
//  DONE
// ════════════════════════════════════════════════════════
function renderDone(){
  const snapGrid = snapshots.length
    ? `<div style="margin-top:20px;max-width:600px;width:100%">
        <div style="font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--amb);margin-bottom:10px">📸 Captured Snapshots (${snapshots.length})</div>
        <div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(170px,1fr));gap:8px">
          ${snapshots.map(s=>`<div style="border-radius:8px;overflow:hidden;border:1px solid var(--bd)">
            <img src="${s.img}" style="width:100%;display:block">
            <div style="background:var(--bg3);padding:4px 6px;font-size:9px;color:var(--tx3)">${s.time} — ${s.reason}</div>
          </div>`).join('')}
        </div></div>` : '';
  const logHTML = proctorLog.length
    ? `<div style="margin-top:16px;max-width:500px;width:100%;background:var(--sur);border:1px solid var(--bd);border-radius:var(--r);padding:16px;text-align:left">
        <div style="font-size:11px;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--amb);margin-bottom:10px">⚠ Proctor Event Log</div>
        ${proctorLog.map(l=>`<div style="display:flex;gap:10px;padding:6px 0;border-bottom:1px solid var(--bd);font-size:12px">
          <span style="color:var(--tx3);font-family:monospace;font-size:10px;flex-shrink:0">${l.time}</span>
          <span style="color:var(--amb);font-weight:600;flex-shrink:0">${l.type}</span>
          <span style="color:var(--tx2)">${l.msg}</span>
        </div>`).join('')}
      </div>` : '';
  return`<div class="center-page">
    <div style="font-size:64px;margin-bottom:14px">✅</div>
    <h2 style="font-size:24px;font-weight:800;color:var(--grn);margin-bottom:8px">Assessment Submitted!</h2>
    <p style="color:var(--tx2);font-size:14px;max-width:420px;line-height:1.8">Thank you, <strong>${candidate.name}</strong>. Your responses have been received and will be reviewed by our team. You will hear back within 3–5 business days.</p>
    <div class="done-card">
      <div class="done-row"><span>Name</span><span>${candidate.name}</span></div>
      <div class="done-row"><span>Email</span><span>${candidate.email}</span></div>
      <div class="done-row"><span>Session ID</span><span style="font-family:monospace;font-size:11px">${SESSION_ID}</span></div>
      <div class="done-row"><span>Time taken</span><span>${fmt(TOTAL_TIME-timeLeft)}</span></div>
      <div class="done-row"><span>Questions answered</span><span>${answers.filter(a=>a&&a.trim()).length}/30</span></div>
      <div class="done-row"><span>Tab violations</span><span style="color:${violations>0?'var(--red)':'var(--grn)'}">${violations}</span></div>
      <div class="done-row"><span>Proctor events</span><span style="color:${proctorLog.length>0?'var(--amb)':'var(--grn)'}">${proctorLog.length}</span></div>
      <div class="done-row"><span>Snapshots saved</span><span style="color:${snapshots.length>0?'var(--amb)':'var(--grn)'}">${snapshots.length}</span></div>
    </div>
    ${logHTML}${snapGrid}
  </div>`;
}

render();
</script>
</body>
</html>
