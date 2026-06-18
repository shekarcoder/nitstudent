<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NIT Raichur – Student Portal</title>
    <meta name="theme-color" content="#1a237e">
    <link rel="manifest" href="manifest.json">
    <link rel="apple-touch-icon" href="icon-192.png">
    <style>
        :root{--p:#1a237e;--pl:#283593;--pd:#0d1642;--w:#fff;--bg:#f5f7fb;--t:#1e1e2f;--tl:#6b7280;--bd:#e2e5f1;--b50:#e8eaf6;--b100:#c5cae9;--sh:0 1px 8px rgba(26,35,126,.06);--sh2:0 4px 20px rgba(26,35,126,.10);--r:14px;--rs:10px;--tr:all .25s ease;--ok:#16a34a;--no:#dc2626}
        *{margin:0;padding:0;box-sizing:border-box}
        body{font-family:'Segoe UI',-apple-system,BlinkMacSystemFont,sans-serif;background:var(--bg);color:var(--t)}
        ::-webkit-scrollbar{width:5px}::-webkit-scrollbar-thumb{background:var(--pl);border-radius:3px}
        .lp{min-height:100vh;display:flex;align-items:center;justify-content:center;background:linear-gradient(135deg,var(--pd),var(--p),var(--pl));position:relative;overflow:hidden}
        .lp::before{content:'';position:absolute;width:500px;height:500px;background:rgba(255,255,255,.03);border-radius:50%;top:-180px;right:-150px}
        .lb{background:var(--w);border-radius:20px;box-shadow:0 20px 60px rgba(0,0,0,.15);width:480px;max-width:95%;padding:36px;z-index:1;animation:fu .5s ease}
        @keyframes fu{from{opacity:0;transform:translateY(25px)}to{opacity:1;transform:translateY(0)}}
        .lh{text-align:center;margin-bottom:26px}
        .lh .logo{width:66px;height:66px;margin:0 auto 12px;background:linear-gradient(135deg,var(--p),var(--pl));border-radius:50%;display:flex;align-items:center;justify-content:center;color:#fff;font-size:1.7rem;font-weight:800;border:3px solid var(--b100)}
        .lh h1{font-size:1.1rem;color:var(--p);line-height:1.35}.lh h1 small{display:block;font-size:.72rem;color:var(--tl);font-weight:400;margin-top:2px}
        .lh .pb{color:var(--p);font-weight:700;font-size:.9rem;margin-top:6px}
        .lt{display:flex;gap:5px;justify-content:center;flex-wrap:wrap;margin-top:8px}
        .lt span{background:var(--b50);color:var(--p);padding:2px 9px;border-radius:16px;font-size:.62rem;font-weight:600}
        .fg{margin-bottom:16px}.fg label{display:block;font-size:.8rem;font-weight:600;color:var(--t);margin-bottom:4px}
        .ii{position:relative}.ii svg{position:absolute;left:12px;top:50%;transform:translateY(-50%);width:16px;height:16px;fill:var(--tl)}
        .fc{width:100%;padding:11px 13px 11px 40px;border:2px solid var(--bd);border-radius:var(--rs);font-size:.88rem;transition:var(--tr);outline:none;font-family:inherit;background:var(--w)}
        .fc:focus{border-color:var(--pl);box-shadow:0 0 0 3px rgba(26,35,126,.08)}
        .fc.pl{padding-left:13px}select.fc{cursor:pointer;appearance:auto}textarea.fc{resize:vertical}
        .fr{display:grid;grid-template-columns:1fr 1fr;gap:12px}
        .em{color:var(--no);font-size:.72rem;margin-top:2px;display:none}
        .btn{display:inline-flex;align-items:center;justify-content:center;gap:7px;padding:11px 20px;border:none;border-radius:var(--rs);font-size:.88rem;font-weight:600;cursor:pointer;transition:var(--tr);font-family:inherit}
        .bp{background:var(--p);color:#fff;width:100%;padding:13px;font-size:.92rem}.bp:hover{background:var(--pl);transform:translateY(-1px)}
        .bo{background:var(--w);color:var(--p);border:2px solid var(--bd)}.bo:hover{background:var(--b50);border-color:var(--p)}
        .bb{background:var(--p);color:#fff}.bb:hover{background:var(--pl)}
        .bs{padding:7px 14px;font-size:.8rem}
        .lf{text-align:center;margin-top:14px;font-size:.8rem;color:var(--tl)}.lf a{color:var(--p);font-weight:600;cursor:pointer;text-decoration:none}.lf a:hover{text-decoration:underline}
        .usn-info{background:var(--b50);border:1px solid var(--b100);border-radius:var(--rs);padding:10px 14px;margin-bottom:16px;font-size:.78rem;color:var(--p)}
        .usn-info strong{display:block;margin-bottom:3px;font-size:.82rem}

        /* Dashboard */
        .db{display:none;min-height:100vh;background:var(--bg)}
        .nav{background:var(--w);padding:0 20px;height:60px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:100;border-bottom:1px solid var(--bd);box-shadow:0 1px 4px rgba(0,0,0,.03)}
        .nl{display:flex;align-items:center;gap:10px}
        .nl .nlogo{width:36px;height:36px;background:var(--p);border-radius:9px;display:flex;align-items:center;justify-content:center;color:#fff;font-weight:800;font-size:.85rem}
        .nt h2{font-size:.9rem;color:var(--p)}.nt span{font-size:.62rem;color:var(--tl)}
        .nr{display:flex;align-items:center;gap:12px}
        .nu{display:flex;align-items:center;gap:8px;cursor:pointer;padding:4px 8px;border-radius:var(--rs);transition:var(--tr)}.nu:hover{background:var(--b50)}
        .na{width:34px;height:34px;border-radius:50%;background:var(--p);color:#fff;display:flex;align-items:center;justify-content:center;font-weight:700;font-size:.78rem;overflow:hidden;border:2px solid var(--b100)}
        .na img{width:100%;height:100%;object-fit:cover}
        .ni{text-align:right}.ni .nm{font-size:.8rem;font-weight:600;color:var(--t)}.ni .nr2{font-size:.62rem;color:var(--tl)}
        .hb{display:none;background:none;border:none;color:var(--p);font-size:1.3rem;cursor:pointer}
        .ib{display:none;background:var(--p);color:#fff;border:none;padding:6px 14px;border-radius:16px;font-weight:600;font-size:.72rem;cursor:pointer;animation:pulse 2s infinite}
        @keyframes pulse{0%,100%{box-shadow:0 0 0 0 rgba(26,35,126,.4)}50%{box-shadow:0 0 0 8px rgba(26,35,126,0)}}
        .install-banner{display:none;background:linear-gradient(135deg,var(--p),var(--pl));color:#fff;padding:14px 20px;border-radius:var(--r);margin-bottom:18px;cursor:pointer;transition:var(--tr)}
        .install-banner:hover{transform:translateY(-2px);box-shadow:var(--sh2)}
        .install-banner h4{font-size:.9rem;margin-bottom:3px}.install-banner p{font-size:.75rem;opacity:.85}
        .install-banner .ib-btns{display:flex;gap:8px;margin-top:10px;flex-wrap:wrap}
        .install-banner .ib-btn{background:rgba(255,255,255,.2);color:#fff;border:1px solid rgba(255,255,255,.3);padding:7px 14px;border-radius:var(--rs);font-size:.78rem;font-weight:600;cursor:pointer;transition:var(--tr);text-decoration:none;display:inline-flex;align-items:center;gap:5px}
        .install-banner .ib-btn:hover{background:rgba(255,255,255,.35)}
        .dbb{display:flex;min-height:calc(100vh - 60px)}
        .sb{width:250px;background:var(--w);border-right:1px solid var(--bd);padding:16px 0;position:sticky;top:60px;height:calc(100vh - 60px);overflow-y:auto;transition:var(--tr)}
        .ss{font-size:.62rem;text-transform:uppercase;letter-spacing:1.1px;color:var(--tl);padding:18px 20px 6px;font-weight:700}
        .sm{list-style:none}
        .sm li a{display:flex;align-items:center;gap:10px;padding:10px 20px;color:var(--tl);text-decoration:none;font-size:.83rem;font-weight:500;transition:var(--tr);border-left:3px solid transparent;cursor:pointer}
        .sm li a:hover{background:var(--b50);color:var(--p)}
        .sm li a.ac{background:var(--b50);color:var(--p);border-left-color:var(--p);font-weight:600}
        .sm li a svg{width:17px;height:17px;fill:currentColor;flex-shrink:0}
        .mc{flex:1;padding:22px;min-width:0}
        .ph{margin-bottom:22px}.ph h1{font-size:1.3rem;color:var(--p);font-weight:700}.ph p{color:var(--tl);font-size:.83rem;margin-top:3px}
        .bc{font-size:.72rem;color:var(--tl);margin-bottom:5px}.bc span{color:var(--p);font-weight:600}
        .cd{background:var(--w);border-radius:var(--r);box-shadow:var(--sh);padding:22px;margin-bottom:18px;border:1px solid var(--bd)}
        .ch{display:flex;align-items:center;justify-content:space-between;margin-bottom:16px;padding-bottom:10px;border-bottom:1px solid var(--bd);flex-wrap:wrap;gap:6px}
        .ch h3{font-size:.95rem;color:var(--p);font-weight:600}
        .sg{display:grid;grid-template-columns:repeat(auto-fit,minmax(190px,1fr));gap:14px;margin-bottom:22px}
        .sc{background:var(--w);border-radius:var(--r);padding:20px;box-shadow:var(--sh);border:1px solid var(--bd);display:flex;align-items:center;gap:14px;transition:var(--tr)}
        .sc:hover{box-shadow:var(--sh2);transform:translateY(-2px)}
        .si2{width:44px;height:44px;border-radius:11px;background:var(--b50);color:var(--p);display:flex;align-items:center;justify-content:center;font-size:1.2rem}
        .sv h3{font-size:1.4rem;color:var(--p);font-weight:700}.sv p{font-size:.72rem;color:var(--tl);margin-top:1px}
        .tw{overflow-x:auto}
        table{width:100%;border-collapse:collapse;font-size:.83rem}
        table thead th{background:var(--b50);color:var(--p);padding:10px 12px;text-align:left;font-weight:600;font-size:.72rem;text-transform:uppercase;letter-spacing:.4px;border-bottom:2px solid var(--b100);white-space:nowrap}
        table tbody td{padding:10px 12px;border-bottom:1px solid var(--bd);color:var(--t)}
        table tbody tr:hover{background:var(--b50)}
        .badge{display:inline-block;padding:3px 9px;border-radius:16px;font-size:.68rem;font-weight:600}
        .badge-b{background:var(--b50);color:var(--p)}.badge-g{background:#dcfce7;color:var(--ok)}.badge-r{background:#fee2e2;color:var(--no)}
        .pt{display:flex;gap:22px;align-items:center;flex-wrap:wrap}
        .pp{width:100px;height:100px;border-radius:50%;background:var(--b50);color:var(--p);display:flex;align-items:center;justify-content:center;font-size:2.5rem;font-weight:700;flex-shrink:0;border:3px solid var(--b100);overflow:hidden;position:relative;cursor:pointer}
        .pp img{width:100%;height:100%;object-fit:cover}
        .pp .uo{position:absolute;inset:0;background:rgba(26,35,126,.6);display:none;align-items:center;justify-content:center;color:#fff;font-size:.68rem;font-weight:600}
        .pp:hover .uo{display:flex}
        .pi2 h2{font-size:1.25rem;color:var(--p)}.pi2 p{color:var(--tl);margin-top:3px;font-size:.88rem}
        .pm2{display:flex;gap:16px;margin-top:8px;flex-wrap:wrap}.pm2 span{font-size:.8rem;color:var(--t)}
        .dg{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:12px}
        .di2{padding:9px 0;border-bottom:1px solid var(--bg)}
        .di2 label{font-size:.65rem;text-transform:uppercase;letter-spacing:.4px;color:var(--tl);font-weight:600;display:block;margin-bottom:2px}
        .di2 span{font-size:.88rem;font-weight:500;color:var(--t)}
        .ab2{height:22px;background:var(--bg);border-radius:11px;overflow:hidden}
        .af2{height:100%;border-radius:11px;display:flex;align-items:center;justify-content:center;color:#fff;font-size:.68rem;font-weight:600;transition:width .8s ease;background:var(--p)}
        .af2.low{background:var(--no)}.af2.med{background:#f59e0b}
        .gpc{display:flex;align-items:flex-end;gap:10px;height:150px;padding:16px 0}
        .gpc2{flex:1;display:flex;flex-direction:column;align-items:center;height:100%;justify-content:flex-end}
        .gpb2{width:100%;max-width:44px;border-radius:5px 5px 0 0;background:var(--p);transition:height .8s ease;position:relative}
        .gpb2 .gv2{position:absolute;top:-20px;left:50%;transform:translateX(-50%);font-size:.7rem;font-weight:700;color:var(--p)}
        .gpl2{font-size:.65rem;color:var(--tl);margin-top:4px;font-weight:600}
        .qg{display:grid;grid-template-columns:repeat(auto-fit,minmax(120px,1fr));gap:10px}
        .qi{display:flex;flex-direction:column;align-items:center;gap:6px;padding:16px 10px;background:var(--bg);border-radius:var(--r);cursor:pointer;transition:var(--tr);border:2px solid transparent}
        .qi:hover{border-color:var(--p);background:var(--b50);transform:translateY(-2px)}
        .qic{width:38px;height:38px;border-radius:10px;background:var(--p);color:#fff;display:flex;align-items:center;justify-content:center;font-size:1rem}
        .qi span{font-size:.78rem;font-weight:600;text-align:center;color:var(--p)}
        .notice2{padding:14px;border-left:4px solid var(--p);background:var(--w);border-radius:0 var(--rs) var(--rs) 0;margin-bottom:10px;border:1px solid var(--bd);border-left:4px solid var(--p)}
        .notice2.urg{border-left-color:var(--no)}.notice2.ev{border-left-color:#f59e0b}
        .notice2 h4{font-size:.88rem;color:var(--t);margin-bottom:3px}.notice2 p{font-size:.8rem;color:var(--tl);line-height:1.4}.notice2 .dt{font-size:.68rem;color:var(--p);margin-top:4px;font-weight:500}
        .fc2{display:grid;grid-template-columns:repeat(auto-fit,minmax(170px,1fr));gap:14px;margin-bottom:18px}
        .fcd{padding:18px;border-radius:var(--r);text-align:center;background:var(--w);border:1px solid var(--bd)}
        .fcd h4{font-size:.7rem;text-transform:uppercase;color:var(--tl);margin-bottom:4px;letter-spacing:.4px}
        .fcd .amt{font-size:1.4rem;font-weight:700;color:var(--p)}
        .ig{display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));gap:14px}
        .ic{background:var(--w);border-radius:var(--r);padding:18px;border:1px solid var(--bd);border-left:4px solid var(--p)}
        .ic h4{color:var(--p);font-size:.88rem;margin-bottom:8px}
        .ic li{font-size:.8rem;color:var(--t);line-height:1.5;padding:2px 0;list-style:none;padding-left:13px;position:relative}
        .ic li::before{content:'›';position:absolute;left:0;color:var(--p);font-weight:700}
        .mo2{display:none;position:fixed;inset:0;background:rgba(0,0,0,.4);z-index:1000;align-items:center;justify-content:center}.mo2.show{display:flex}
        .mb{background:var(--w);border-radius:var(--r);padding:28px;max-width:480px;width:95%;max-height:90vh;overflow-y:auto;animation:fu .3s ease}
        .mb h2{color:var(--p);margin-bottom:18px;font-size:1.05rem}
        .ma2{display:flex;gap:10px;justify-content:flex-end;margin-top:18px}
        .toast{position:fixed;top:74px;right:20px;background:var(--p);color:#fff;padding:12px 20px;border-radius:var(--rs);box-shadow:var(--sh2);z-index:2000;transform:translateX(420px);transition:transform .4s ease;font-weight:600;font-size:.83rem;max-width:330px}
        .toast.show{transform:translateX(0)}
        .pf{text-align:center;padding:18px;color:var(--tl);font-size:.72rem;border-top:1px solid var(--bd);margin-top:30px}
        .phi{display:none}
        .tt-day{margin-bottom:14px}.tt-day h4{color:var(--p);margin-bottom:6px;font-size:.88rem;font-weight:600}
        .tt-slots{display:grid;grid-template-columns:repeat(auto-fill,minmax(165px,1fr));gap:6px}
        .tt-slot{background:var(--b50);padding:9px 12px;border-radius:var(--rs);border-left:3px solid var(--p)}
        .tt-slot .time{font-size:.68rem;color:var(--tl);font-weight:600}.tt-slot .subj{font-size:.83rem;font-weight:600;color:var(--p);margin-top:1px}.tt-slot .fac{font-size:.68rem;color:var(--tl)}
        @media(max-width:768px){.sb{position:fixed;left:-250px;top:60px;z-index:99;height:calc(100vh - 60px)}.sb.open{left:0;box-shadow:var(--sh2)}.hb{display:block}.mc{padding:14px}.fr{grid-template-columns:1fr}.pt{flex-direction:column;text-align:center}.ni{display:none}.sg{grid-template-columns:1fr 1fr}}
        @media(max-width:480px){.sg{grid-template-columns:1fr}.lb{padding:22px}}
        @media print{.nav,.sb,.hb{display:none!important}.mc{padding:0}}
    </style>
</head>
<body>
<div class="toast" id="toast"></div>
<input type="file" class="phi" id="photoInput" accept="image/*">

<!-- LOGIN -->
<div class="lp" id="loginPage">
    <div class="lb">
        <div class="lh">
            <div class="logo">N</div>
            <h1>Navodaya Institute of Technology<small>Raichur, Karnataka – 584103</small></h1>
            <div class="pb">🎓 Student Portal</div>
            <div class="lt"><span>VTU Affiliated</span><span>AICTE Approved</span><span>NAAC 'A' Grade</span><span>UGC Autonomous</span></div>
        </div>

        <div id="loginForm">
            <div class="fg"><label>Student USN</label><div class="ii"><svg viewBox="0 0 24 24"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg><input type="text" class="fc" id="loginUSN" placeholder="e.g., 3NA24CS002" autocomplete="username"></div><div class="em" id="le1">Enter your USN</div></div>
            <div class="fg"><label>Password</label><div class="ii"><svg viewBox="0 0 24 24"><path d="M18 8h-1V6c0-2.76-2.24-5-5-5S7 3.24 7 6v2H6c-1.1 0-2 .9-2 2v10c0 1.1.9 2 2 2h12c1.1 0 2-.9 2-2V10c0-1.1-.9-2-2-2zm-6 9c-1.1 0-2-.9-2-2s.9-2 2-2 2 .9 2 2-.9 2-2 2zm3.1-9H8.9V6c0-1.71 1.39-3.1 3.1-3.1s3.1 1.39 3.1 3.1v2z"/></svg><input type="password" class="fc" id="loginPwd" placeholder="Enter password" autocomplete="current-password"></div><div class="em" id="le2">Enter password</div></div>
            <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:16px"><label style="display:flex;align-items:center;gap:5px;font-size:.8rem;cursor:pointer"><input type="checkbox"> Remember me</label><a style="font-size:.8rem;color:var(--p);cursor:pointer" onclick="showToast('Contact: 08532-240115')">Forgot?</a></div>
            <button class="btn bp" onclick="handleLogin()">🔒 Secure Sign In</button>
            <div class="lf" style="margin-top:10px"><span style="background:var(--b50);color:var(--p);padding:2px 8px;border-radius:6px;font-size:.62rem;font-weight:600">🔒 Encrypted</span></div>
            <div class="lf">New student? <a onclick="showReg()">Register with USN</a></div>
            <div class="lf" style="margin-top:3px"><small>Demo: <b>3NA24CS034</b> / <b>Nit@2026</b></small></div>
        </div>

        <div id="regForm" style="display:none">
            <div class="usn-info"><strong>⚠️ Only valid NIT Raichur USNs can register</strong>Enter your official USN (3NA24CS___ / 3NA23CS___ / 3NA25CS___). Your name, branch, semester & lecture hall will be auto-filled from college records.</div>
            <div class="fg"><label>USN *</label><input type="text" class="fc pl" id="rUSN" placeholder="e.g., 3NA24CS002" oninput="checkUSN()"></div>
            <div id="usnResult" style="display:none;margin-bottom:14px;padding:12px;border-radius:var(--rs);background:var(--b50);border:1px solid var(--b100)">
                <div style="font-size:.82rem;color:var(--p);font-weight:600" id="usnName"></div>
                <div style="font-size:.75rem;color:var(--tl);margin-top:2px" id="usnMeta"></div>
            </div>
            <div class="fr">
                <div class="fg"><label>Email *</label><input type="email" class="fc pl" id="rEmail" placeholder="Email"></div>
                <div class="fg"><label>Phone *</label><input type="tel" class="fc pl" id="rPhone" placeholder="Phone"></div>
            </div>
            <div class="fg"><label>Password * (min 8, 1 uppercase, 1 number)</label><input type="password" class="fc pl" id="rPwd" placeholder="Create password"></div>
            <div class="fg"><label>Confirm Password *</label><input type="password" class="fc pl" id="rCPwd" placeholder="Re-enter password"></div>
            <button class="btn bp" onclick="handleReg()" style="margin-bottom:10px">Create Account</button>
            <div class="lf">Already registered? <a onclick="showLog()">Sign In</a></div>
        </div>
    </div>
</div>

<!-- DASHBOARD -->
<div class="db" id="dashboard">
    <nav class="nav"><div class="nl"><button class="hb" onclick="toggleSB()">☰</button><div class="nlogo">N</div><div class="nt"><h2>NIT Raichur</h2><span>Student Portal</span></div></div>
    <div class="nr"><button class="ib" id="installBtn" onclick="installApp()">📱 Install</button><div class="nu" onclick="nav('profile')"><div class="ni"><div class="nm" id="navNm">Student</div><div class="nr2">Student</div></div><div class="na" id="navAv">S</div></div><button class="btn bb bs" onclick="logout()">Logout</button></div></nav>
    <div class="dbb"><aside class="sb" id="sidebar">
        <div class="ss">Main</div><ul class="sm"><li><a class="ac" onclick="nav('home')"><svg viewBox="0 0 24 24"><path d="M3 13h8V3H3v10zm0 8h8v-6H3v6zm10 0h8V11h-8v10zm0-18v6h8V3h-8z"/></svg>Dashboard</a></li><li><a onclick="nav('profile')"><svg viewBox="0 0 24 24"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/></svg>My Profile</a></li></ul>
        <div class="ss">Academics</div><ul class="sm"><li><a onclick="nav('attendance')"><svg viewBox="0 0 24 24"><path d="M19 3h-4.18C14.4 1.84 13.3 1 12 1c-1.3 0-2.4.84-2.82 2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-7 0c.55 0 1 .45 1 1s-.45 1-1 1-1-.45-1-1 .45-1 1-1zm-2 14l-4-4 1.41-1.41L10 14.17l6.59-6.59L18 9l-8 8z"/></svg>Attendance</a></li><li><a onclick="nav('results')"><svg viewBox="0 0 24 24"><path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-5 14H7v-2h7v2zm3-4H7v-2h10v2zm0-4H7V7h10v2z"/></svg>Results</a></li><li><a onclick="nav('subjects')"><svg viewBox="0 0 24 24"><path d="M21 5c-1.11-.35-2.33-.5-3.5-.5-1.95 0-4.05.4-5.5 1.5-1.45-1.1-3.55-1.5-5.5-1.5S2.45 4.9 1 6v14.65c0 .25.25.5.5.5.1 0 .15-.05.25-.05C3.1 20.45 5.05 20 6.5 20c1.95 0 4.05.4 5.5 1.5 1.35-.85 3.8-1.5 5.5-1.5 1.65 0 3.35.3 4.75 1.05.1.05.15.05.25.05.25 0 .5-.25.5-.5V6c-.6-.45-1.25-.75-2-1z"/></svg>Subjects</a></li><li><a onclick="nav('timetable')"><svg viewBox="0 0 24 24"><path d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm.5-13H11v6l5.25 3.15.75-1.23-4.5-2.67z"/></svg>Timetable</a></li></ul>
        <div class="ss">VTU Resources</div><ul class="sm"><li><a onclick="nav('vtu')"><svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.95-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z"/></svg>VTU Sync</a></li></ul>
        <div class="ss">Others</div><ul class="sm"><li><a onclick="nav('fees')"><svg viewBox="0 0 24 24"><path d="M11.8 10.9c-2.27-.59-3-1.2-3-2.15 0-1.09 1.01-1.85 2.7-1.85 1.78 0 2.44.85 2.5 2.1h2.21c-.07-1.72-1.12-3.3-3.21-3.81V3h-3v2.16c-1.94.42-3.5 1.68-3.5 3.61 0 2.31 1.91 3.46 4.7 4.13 2.5.6 3 1.48 3 2.41 0 .69-.49 1.79-2.7 1.79-2.06 0-2.87-.92-2.98-2.1h-2.2c.12 2.19 1.76 3.42 3.68 3.83V21h3v-2.15c1.95-.37 3.5-1.5 3.5-3.55 0-2.84-2.43-3.81-4.7-4.4z"/></svg>Fees</a></li><li><a onclick="nav('notices')"><svg viewBox="0 0 24 24"><path d="M12 22c1.1 0 2-.9 2-2h-4c0 1.1.89 2 2 2zm6-6v-5c0-3.07-1.64-5.64-4.5-6.32V4c0-.83-.67-1.5-1.5-1.5s-1.5.67-1.5 1.5v.68C7.63 5.36 6 7.92 6 11v5l-2 2v1h16v-1l-2-2z"/></svg>Notices</a></li><li><a onclick="nav('install')"><svg viewBox="0 0 24 24"><path d="M17 1.01L7 1c-1.1 0-2 .9-2 2v18c0 1.1.9 2 2 2h10c1.1 0 2-.9 2-2V3c0-1.1-.9-1.99-2-1.99zM17 19H7V5h10v14zm-1-6h-3V8h-2v5H8l4 4 4-4z"/></svg>Install App</a></li>
<li><a onclick="nav('settings')"><svg viewBox="0 0 24 24"><path d="M19.14 12.94c.04-.3.06-.61.06-.94 0-.32-.02-.64-.07-.94l2.03-1.58c.18-.14.23-.41.12-.61l-1.92-3.32c-.12-.22-.37-.29-.59-.22l-2.39.96c-.5-.38-1.03-.7-1.62-.94l-.36-2.54c-.04-.24-.24-.41-.48-.41h-3.84c-.24 0-.43.17-.47.41l-.36 2.54c-.59.24-1.13.57-1.62.94l-2.39-.96c-.22-.08-.47 0-.59.22L2.74 8.87c-.12.21-.08.47.12.61l2.03 1.58c-.05.3-.07.62-.07.94s.02.64.07.94l-2.03 1.58c-.18.14-.23.41-.12.61l1.92 3.32c.12.22.37.29.59.22l2.39-.96c.5.38 1.03.7 1.62.94l.36 2.54c.05.24.24.41.48.41h3.84c.24 0 .44-.17.47-.41l.36-2.54c.59-.24 1.13-.56 1.62-.94l2.39.96c.22.08.47 0 .59-.22l1.92-3.32c.12-.22.07-.47-.12-.61l-2.01-1.58zM12 15.6c-1.98 0-3.6-1.62-3.6-3.6s1.62-3.6 3.6-3.6 3.6 1.62 3.6 3.6-1.62 3.6-3.6 3.6z"/></svg>Settings</a></li></ul>
    </aside><main class="mc" id="mainContent"></main></div>
</div>

<!-- EDIT MODAL -->
<div class="mo2" id="editModal"><div class="mb"><h2>✏️ Edit Profile</h2>
<div class="fg"><label>Email</label><input type="email" class="fc pl" id="edEmail"></div>
<div class="fg"><label>Phone</label><input type="tel" class="fc pl" id="edPhone"></div>
<div class="fg"><label>Address</label><textarea class="fc pl" id="edAddr" rows="2"></textarea></div>
<div class="fg"><label>Blood Group</label><select class="fc pl" id="edBl"><option>A+</option><option>A-</option><option>B+</option><option>B-</option><option>O+</option><option>O-</option><option>AB+</option><option>AB-</option></select></div>
<div class="ma2"><button class="btn bo bs" onclick="closeModal()">Cancel</button><button class="btn bb bs" onclick="saveProfile()">Save</button></div></div></div>

<script>
// ===== REAL STUDENT DATABASE =====
const REAL_STUDENTS = {
'3NA24CS002':{name:'ABDUR RAFAY',lh:'LH-01',sem:4,branch:'CSE',s1:7.75,s2:7.05,s3:8.62},
'3NA24CS003':{name:'ABDUR RAHMAN KHAN',lh:'LH-01',sem:4,branch:'CSE',s1:7,s2:7.1,s3:7.2},
'3NA24CS004':{name:'ABHILASH',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS005':{name:'ABHISHEK ADI',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS006':{name:'ADNAN KASHIF',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS007':{name:'AJAY KUMAR',lh:'LH-01',sem:4,branch:'CSE',s1:7,s2:7.05,s3:6.81},
'3NA24CS009':{name:'AKSHITA',lh:'LH-01',sem:4,branch:'CSE',s1:7.55,s2:7.85,s3:8},
'3NA24CS010':{name:'AMBRESH S',lh:'LH-01',sem:4,branch:'CSE',s1:7.9,s2:7.6,s3:7.6},
'3NA24CS011':{name:'AMEENA SUMAIYA MALIHA',lh:'LH-01',sem:4,branch:'CSE',s1:7.6,s2:8.25,s3:7.43},
'3NA24CS012':{name:'ANAGHA KULKARNI',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS013':{name:'ANKITA',lh:'LH-01',sem:4,branch:'CSE',s1:6.5,s2:6.9,s3:7.67},
'3NA24CS014':{name:'ARFA NOORAIN',lh:'LH-01',sem:4,branch:'CSE',s1:9,s2:9.35,s3:8.67},
'3NA24CS015':{name:'ARPITHA',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS016':{name:'ARSHIYA TABASSUM',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS017':{name:'ASRA MOHAMMADI',lh:'LH-01',sem:4,branch:'CSE',s1:7.15,s2:7.95,s3:6.95},
'3NA24CS018':{name:'AYESHA SADAF',lh:'LH-01',sem:4,branch:'CSE',s1:8.25,s2:9.1,s3:8.71},
'3NA24CS019':{name:'BALARAJ G',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS020':{name:'BANDESH',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS021':{name:'BHAGYASHREE',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS023':{name:'BHAVANA ASHOK TOTAGANTI',lh:'LH-01',sem:4,branch:'CSE',s1:6.65,s2:7.35,s3:7.19},
'3NA24CS024':{name:'BHAVANA C BALAGANOOR',lh:'LH-01',sem:4,branch:'CSE',s1:7.5,s2:7.5,s3:7.5},
'3NA24CS025':{name:'BHOOMIKA',lh:'LH-01',sem:4,branch:'CSE',s1:8.25,s2:7.8,s3:7.86},
'3NA24CS026':{name:'BUSHRA FATHIMA',lh:'LH-01',sem:4,branch:'CSE',s1:9.03,s2:8.84,s3:9.14},
'3NA24CS027':{name:'BUSHRA MARIYAM',lh:'LH-01',sem:4,branch:'CSE',s1:8.95,s2:9.55,s3:8.95},
'3NA24CS028':{name:'BUSHRA MOHAMMADI',lh:'LH-01',sem:4,branch:'CSE',s1:7.9,s2:7.7,s3:7.9},
'3NA24CS029':{name:'CHAITRA ACHHA',lh:'LH-01',sem:4,branch:'CSE',s1:7.6,s2:7.5,s3:6.5},
'3NA24CS030':{name:'CHETHAN',lh:'LH-01',sem:4,branch:'CSE',s1:6.8,s2:7.05,s3:7.4},
'3NA24CS031':{name:'DHAMMAPRIYA',lh:'LH-01',sem:4,branch:'CSE',s1:6.3,s2:6.4,s3:7.19},
'3NA24CS072':{name:'DUNNA HARSHINI',lh:'LH-01',sem:4,branch:'CSE',s1:7,s2:6.85,s3:6},
'3NA24CS033':{name:'DURGA',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:7.42},
'3NA24CS034':{name:'E DEEPIKA',lh:'LH-01',sem:4,branch:'CSE',s1:9.75,s2:9.85,s3:9.29},
'3NA24CS035':{name:'GAGANA',lh:'LH-01',sem:4,branch:'CSE',s1:6.85,s2:6.8,s3:7.38},
'3NA24CS036':{name:'GANGA',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS037':{name:'GOUTAMI DESAI',lh:'LH-01',sem:4,branch:'CSE',s1:7.7,s2:8.1,s3:7.8},
'3NA24CS038':{name:'HARSHITA A',lh:'LH-01',sem:4,branch:'CSE',s1:8.6,s2:8.5,s3:8.2},
'3NA24CS039':{name:'HITHENDRA M',lh:'LH-01',sem:4,branch:'CSE',s1:7.25,s2:7.25,s3:6.81},
'3NA24CS040':{name:'HUDA SHAHZADI',lh:'LH-01',sem:4,branch:'CSE',s1:8.35,s2:7.65,s3:8.25},
'3NA24CS041':{name:'HULIGEMMA',lh:'LH-01',sem:4,branch:'CSE',s1:7.5,s2:7.7,s3:8},
'3NA24CS042':{name:'INCHARA KULKARNI',lh:'LH-01',sem:4,branch:'CSE',s1:7.85,s2:7,s3:7.25},
'3NA24CS043':{name:'JAHNAVI',lh:'LH-01',sem:4,branch:'CSE',s1:9.15,s2:8.6,s3:9.33},
'3NA24CS044':{name:'K LAXMI NARASIMHA',lh:'LH-01',sem:4,branch:'CSE',s1:8.15,s2:7.8,s3:7.75},
'3NA24CS046':{name:'K SUJAY',lh:'LH-01',sem:4,branch:'CSE',s1:7,s2:4.7,s3:5.76},
'3NA24CS047':{name:'KAVITA',lh:'LH-01',sem:4,branch:'CSE',s1:7.35,s2:7.5,s3:7.29},
'3NA24CS048':{name:'KOMMALAPATI ABHIRAM',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS049':{name:'KRISHNAI',lh:'LH-01',sem:4,branch:'CSE',s1:9.15,s2:8.9,s3:9.29},
'3NA24CS050':{name:'LATIFA KHATOON',lh:'LH-01',sem:4,branch:'CSE',s1:9.01,s2:8.3,s3:8.5},
'3NA24CS051':{name:'M MAHABOOB PASHA',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS052':{name:'M POOJA',lh:'LH-01',sem:4,branch:'CSE',s1:7.9,s2:8.4,s3:8.43},
'3NA24CS054':{name:'MALLIKARJUN DIDDI',lh:'LH-01',sem:4,branch:'CSE',s1:6.05,s2:5,s3:null},
'3NA24CS055':{name:'MD BABLU',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS056':{name:'MD MUSTAFA HUSSAIN',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS058':{name:'MOHAMMED AYAAN ALI',lh:'LH-01',sem:4,branch:'CSE',s1:7.3,s2:7,s3:7.24},
'3NA24CS059':{name:'MOHAMMED AYYUB',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS060':{name:'MOHAMMED FARAZ',lh:'LH-01',sem:4,branch:'CSE',s1:8.1,s2:7.15,s3:7.67},
'3NA24CS061':{name:'MOHAMMED FURQUAN',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS064':{name:'MOHAMMED OMER SIDDIQUI',lh:'LH-01',sem:4,branch:'CSE',s1:6.5,s2:5.35,s3:6},
'3NA24CS065':{name:'MOHAMMED OWAIS AHMED',lh:'LH-01',sem:4,branch:'CSE',s1:5.8,s2:6.45,s3:5.86},
'3NA24CS068':{name:'MOHAMMED REHAN AHMED',lh:'LH-01',sem:4,branch:'CSE',s1:6.25,s2:4.85,s3:5.81},
'3NA24CS070':{name:'MOHAMMED SAIF',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA23CS004':{name:'AHMED MUTHAHEER',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA23CS009':{name:'AMIT',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA23CS023':{name:'D M ABHISHEK',lh:'LH-01',sem:4,branch:'CSE',s1:6.5,s2:7.2,s3:6},
'3NA23CS035':{name:'K JAYASHREE',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:7.3,s3:6.4},
'3NA23CS052':{name:'MOHAMMED ABRAR HUSSAIN',lh:'LH-01',sem:4,branch:'CSE',s1:6.8,s2:7.2,s3:6},
'3NA23CS054':{name:'MOHAMMED BASITH',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA23CS056':{name:'MOHAMMED FARHAN RAZA',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA23CS063':{name:'MOHAMMED SHABBIR AHMED',lh:'LH-01',sem:4,branch:'CSE',s1:7.5,s2:6.8,s3:5.7},
'3NA23CS130':{name:'SYED KHAJA SHAMSHUDDIN',lh:'LH-01',sem:4,branch:'CSE',s1:6.8,s2:6,s3:5.9},
'3NA23CS147':{name:'V VARUN KUMAR',lh:'LH-01',sem:4,branch:'CSE',s1:7.11,s2:5.55,s3:5.55},
'3NA23CS014':{name:'AVINASH MALI PATIL',lh:'LH-01',sem:4,branch:'CSE',s1:6.15,s2:6.65,s3:6.1},
'3NA23CS022':{name:'CHANDRAKANTH',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA23CS051':{name:'MD ABDUL RAZZAQ',lh:'LH-01',sem:4,branch:'CSE',s1:7,s2:6,s3:5.5},
'3NA23CS086':{name:'PRANAM JALDAR B',lh:'LH-01',sem:4,branch:'CSE',s1:null,s2:6.5,s3:5.8},
'3NA23CS102':{name:'SAI KIRAN C',lh:'LH-01',sem:4,branch:'CSE',s1:6.5,s2:6.5,s3:5.5},
'3NA23CS099':{name:'ROHIT VARMA B',lh:'LH-01',sem:4,branch:'CSE',s1:7,s2:6,s3:5.5},
'3NA24CS073':{name:'MOHAMMED SUHAIL AHMED',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS074':{name:'MOHAMMED SUHEB',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS075':{name:'MOHAMMED TARIQ UZ ZAMAN',lh:'LH-02',sem:4,branch:'CSE',s1:6.7,s2:6.5,s3:6.9},
'3NA24CS076':{name:'MONIKA B',lh:'LH-02',sem:4,branch:'CSE',s1:8.5,s2:7.9,s3:8.1},
'3NA24CS077':{name:'MOULALI',lh:'LH-02',sem:4,branch:'CSE',s1:6.9,s2:6.4,s3:6.5},
'3NA24CS078':{name:'MUBASHIR QURESHI',lh:'LH-02',sem:4,branch:'CSE',s1:8.35,s2:8.4,s3:8.57},
'3NA24CS079':{name:'N ROHEENA FATHIMA',lh:'LH-02',sem:4,branch:'CSE',s1:8.9,s2:8.8,s3:9.62},
'3NA24CS080':{name:'NABEELA HASSAN OSMANI',lh:'LH-02',sem:4,branch:'CSE',s1:7,s2:7.6,s3:7.9},
'3NA24CS081':{name:'NABILA AMBREEN',lh:'LH-02',sem:4,branch:'CSE',s1:8.85,s2:8.5,s3:8.9},
'3NA24CS083':{name:'NEELAKANTH',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS084':{name:'NIDA AMBEER',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS085':{name:'NIDA PARVEEN',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS086':{name:'NIRVIKA M.S.',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS088':{name:'P.UDAY KIRAN',lh:'LH-02',sem:4,branch:'CSE',s1:9.6,s2:9.35,s3:9.19},
'3NA24CS089':{name:'PARASHURAM',lh:'LH-02',sem:4,branch:'CSE',s1:6.39,s2:null,s3:null},
'3NA24CS090':{name:'PRIYANKA H C',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS091':{name:'RADHAI',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS093':{name:'RAHEEMATH BATOOL',lh:'LH-02',sem:4,branch:'CSE',s1:6.9,s2:7.63,s3:8.33},
'3NA24CS094':{name:'RONALD ANAND',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS096':{name:'S.SHAHIR',lh:'LH-02',sem:4,branch:'CSE',s1:6.5,s2:6.5,s3:7.17},
'3NA24CS097':{name:'SAHANA G S',lh:'LH-02',sem:4,branch:'CSE',s1:9.15,s2:9.25,s3:8.62},
'3NA24CS098':{name:'SAJEEDA BEGUM',lh:'LH-02',sem:4,branch:'CSE',s1:8.5,s2:9.15,s3:8.6},
'3NA24CS100':{name:'SANA TASKEEN',lh:'LH-02',sem:4,branch:'CSE',s1:7.85,s2:7.75,s3:8.05},
'3NA24CS101':{name:'SANIYA',lh:'LH-02',sem:4,branch:'CSE',s1:8.6,s2:8.7,s3:8.95},
'3NA24CS102':{name:'SANIYA BEGAM',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS103':{name:'SANJANA',lh:'LH-02',sem:4,branch:'CSE',s1:7.7,s2:7.95,s3:7.62},
'3NA24CS104':{name:'SARASWATI',lh:'LH-02',sem:4,branch:'CSE',s1:7.9,s2:8.2,s3:8.13},
'3NA24CS105':{name:'SHAFIYA KARAM',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS106':{name:'SHAIK ABDUL ABDULLAH HUSSAIN',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS108':{name:'SHANKAR JALAWADGI',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS110':{name:'SHEBA RANI',lh:'LH-02',sem:4,branch:'CSE',s1:7.8,s2:7.9,s3:8.4},
'3NA24CS111':{name:'SHIVANI',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS112':{name:'SHREEDEVI B',lh:'LH-02',sem:4,branch:'CSE',s1:7.55,s2:8.15,s3:7.9},
'3NA24CS113':{name:'SHREYAS',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS114':{name:'SHRI VISHNUDAS JOSHI',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS115':{name:'SHRINIVAS NAYAK',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS117':{name:'SIDDU PRASAD',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS118':{name:'SINDHUSHREE',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS119':{name:'SOUDAGAR SHEBAAN',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS120':{name:'SPANDANA',lh:'LH-02',sem:4,branch:'CSE',s1:8,s2:8.5,s3:8.14},
'3NA24CS121':{name:'SRUJAN',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS122':{name:'SRUSHTI',lh:'LH-02',sem:4,branch:'CSE',s1:8.6,s2:8.1,s3:8.9},
'3NA24CS123':{name:'SRUSTI PATIL',lh:'LH-02',sem:4,branch:'CSE',s1:8.6,s2:8.2,s3:8.5},
'3NA24CS124':{name:'STYRISH MARSHALL',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS125':{name:'SUBRAHMANYA N',lh:'LH-02',sem:4,branch:'CSE',s1:8.6,s2:8.6,s3:8.1},
'3NA24CS126':{name:'SUDARSHAN',lh:'LH-02',sem:4,branch:'CSE',s1:8,s2:6.75,s3:7.62},
'3NA24CS128':{name:'SUMAIYA NAAZ',lh:'LH-02',sem:4,branch:'CSE',s1:8.2,s2:8.8,s3:8.81},
'3NA24CS129':{name:'SUMAYYA QAMAR',lh:'LH-02',sem:4,branch:'CSE',s1:8.65,s2:9,s3:8.7},
'3NA24CS130':{name:'SUNKAMMA',lh:'LH-02',sem:4,branch:'CSE',s1:6.9,s2:7.1,s3:6},
'3NA24CS131':{name:'SURESH',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS132':{name:'SUSHMA A.Y',lh:'LH-02',sem:4,branch:'CSE',s1:7,s2:6.9,s3:null},
'3NA24CS133':{name:'SWASTIK',lh:'LH-02',sem:4,branch:'CSE',s1:7.35,s2:7.9,s3:8.67},
'3NA24CS134':{name:'SYED ADEEB UR RAHMAN',lh:'LH-02',sem:4,branch:'CSE',s1:7.85,s2:7.65,s3:8.14},
'3NA24CS136':{name:'SYED SHAN MURTUZA QUADRI',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS137':{name:'SYEDA DANIYA KOUSAR QUAZI',lh:'LH-02',sem:4,branch:'CSE',s1:8.65,s2:7.55,s3:8.67},
'3NA24CS139':{name:'SYEDA MARIYA KURSHIDA',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS140':{name:'T TEJA',lh:'LH-02',sem:4,branch:'CSE',s1:6.45,s2:7.01,s3:7.7},
'3NA24CS141':{name:'TANUJA',lh:'LH-02',sem:4,branch:'CSE',s1:7.7,s2:7.7,s3:7.9},
'3NA24CS142':{name:'TASLEEM',lh:'LH-02',sem:4,branch:'CSE',s1:8.6,s2:8.8,s3:8.95},
'3NA24CS143':{name:'TEJASWINI DONGRE',lh:'LH-02',sem:4,branch:'CSE',s1:7.5,s2:7.6,s3:8.2},
'3NA24CS144':{name:'V. NANDITA',lh:'LH-02',sem:4,branch:'CSE',s1:8,s2:7.6,s3:8.1},
'3NA24CS145':{name:'V.VISHWANATH',lh:'LH-02',sem:4,branch:'CSE',s1:8.05,s2:8.35,s3:8.14},
'3NA24CS146':{name:'VAISHANAVI SATYANARAYAN UPPAL',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS147':{name:'VARSHA B.P.',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA24CS148':{name:'VENKAT BAI KULKARNI',lh:'LH-02',sem:4,branch:'CSE',s1:7.55,s2:8.05,s3:7.89},
'3NA24CS149':{name:'YASHWANTH L',lh:'LH-02',sem:4,branch:'CSE',s1:7.45,s2:7.2,s3:7.76},
'3NA24CS150':{name:'ZOHA ZIYAN',lh:'LH-02',sem:4,branch:'CSE',s1:8.05,s2:8.1,s3:8.47},
'3NA25CS400':{name:'AKIRNATH',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:8.11},
'3NA25CS401':{name:'CHANDRASHEKAR',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:7.67},
'3NA25CS402':{name:'IMDAD ALI',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA25CS403':{name:'MOHAMMED ABDUS SUBHAN SULEMAN',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA25CS404':{name:'PRAVEEN KUMAR T',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA25CS405':{name:'SANTOSH',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:8.56},
'3NA25CS406':{name:'VASANT',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null},
'3NA25CS407':{name:'VINOD KUMAR',lh:'LH-02',sem:4,branch:'CSE',s1:null,s2:null,s3:null}
};
// Security
function enc(d){return btoa(unescape(encodeURIComponent(JSON.stringify(d))))}
function dec(e){try{return JSON.parse(decodeURIComponent(escape(atob(e))))}catch(x){return null}}
function sv(k,d){localStorage.setItem(k,enc(d))}
function ld(k){const r=localStorage.getItem(k);return r?dec(r):null}
function hash(p){let h=0;for(let i=0;i<p.length;i++){h=((h<<5)-h)+p.charCodeAt(i);h|=0}return'h_'+Math.abs(h).toString(36)+'_'+p.length}

const C={name:'Navodaya Institute of Technology',city:'Raichur',phone:'08532-240115',email:'principal.nit@navodaya.edu.in',web:'www.navodayaengineering.edu.in',est:2008,trust:'Navodaya Education Trust (R)',chairman:'Sri S.R. Reddy',principal:'Dr. Shiva Reddy Shahapur',univ:'VTU, Belagavi',cet:'E176',comedk:'E088'};

// VTU 4th Sem CSE — ALL subjects with faculty, hours, labs from real timetable
const VS='https://vtusync.in/cse-ise/',VC='https://vtucircle.com/4th-semester-2022-scheme-cse-ise/';
const SUBS=[
{c:'BCS401',n:'Analysis & Design of Algorithms',cr:3,hr:5,t:'Theory',fac:'Prof. Keerti',link:'https://vtucircle.com/analysis-and-design-of-algorithms-bcs401/',sync:VS},
{c:'BCS402',n:'Microcontrollers Theory + Lab',cr:4,hr:'5 + (2+2) Lab',t:'Theory+Lab',fac:'Prof. Vishwabharati / Dr. Shoaib Madni',link:VC,sync:VS},
{c:'BCS403',n:'Database Management Systems',cr:4,hr:'5 + (2+2) Lab',t:'IPCC+Lab',fac:'Prof. Shaziya',link:'https://vtucircle.com/database-management-system-bcs403/',sync:VS},
{c:'BCSL404',n:'ADA Lab',cr:1,hr:'2+2 Lab',t:'Lab',fac:'Prof. Keerti',link:VC,sync:VS},
{c:'BCS405',n:'Discrete Mathematical Structures (DMS)',cr:3,hr:5,t:'Theory',fac:'Prof. Shaikmaheboob',link:VC,sync:VS},
{c:'BCS456X',n:'LaTeX (Technical Writing)',cr:1,hr:'2+2 Lab',t:'Lab',fac:'Prof. Saniya Zafar',link:VC,sync:VS},
{c:'BCS407',n:'Biology for Engineers',cr:2,hr:3,t:'Theory',fac:'Prof. Venkatalaxmi',link:VC,sync:VS},
{c:'BCS408',n:'Universal Human Values (UHV)',cr:1,hr:2,t:'Theory',fac:'Prof. Mahjabeen',link:VC,sync:VS},
{c:'NSS',n:'NSS / Physical Education',cr:0,hr:2,t:'Activity',fac:'—',link:VC,sync:VS}
];
const MENTORS='Prof. Sara Tahniyath, Prof. Keerthi';

// Real LH-02 Timetable from college (W.E.F. 23/02/2026)
const REAL_TT={
Monday:[
{time:'9:00-10:00',sub:'ADA',code:'BCS401',fac:'Prof. Keerti'},
{time:'10:00-11:00',sub:'UHV',code:'BCS408',fac:'Prof. Mahjabeen'},
{time:'11:15-12:15',sub:'BIO',code:'BCS407',fac:'Prof. Venkatalaxmi'},
{time:'12:15-1:15',sub:'DMS',code:'BCS405',fac:'Prof. Shaikmaheboob'},
{time:'2:00-3:00',sub:'MC',code:'BCS402',fac:'Prof. Vishwabharati'},
{time:'3:00-4:00',sub:'DBMS',code:'BCS403',fac:'Prof. Shaziya'},
{time:'4:00-5:00',sub:'CODING CLUB',code:'—',fac:'—'}
],
Tuesday:[
{time:'9:00-10:00',sub:'MC',code:'BCS402',fac:'Prof. Vishwabharati'},
{time:'10:00-11:00',sub:'DBMS',code:'BCS403',fac:'Prof. Shaziya'},
{time:'11:15-1:15',sub:'← DBMS LAB (B-1) / ADA LAB (B-2) →',code:'Lab',fac:'Prof. Shaziya / Prof. Keerti'},
{time:'2:00-3:00',sub:'DMS',code:'BCS405',fac:'Prof. Shaikmaheboob'},
{time:'3:00-4:00',sub:'ADA',code:'BCS401',fac:'Prof. Keerti'},
{time:'4:00-5:00',sub:'CREATIVE CLUB / LIBRARY',code:'—',fac:'—'}
],
Wednesday:[
{time:'9:00-10:00',sub:'DMS',code:'BCS405',fac:'Prof. Shaikmaheboob'},
{time:'10:00-11:00',sub:'ADA',code:'BCS401',fac:'Prof. Keerti'},
{time:'11:15-12:15',sub:'BIO',code:'BCS407',fac:'Prof. Venkatalaxmi'},
{time:'12:15-1:15',sub:'DBMS',code:'BCS403',fac:'Prof. Shaziya'},
{time:'2:00-4:00',sub:'← ADA LAB (B-1) / AEC LAB (B-2) →',code:'Lab',fac:'Prof. Keerti'},
{time:'4:00-5:00',sub:'ROBOTICS & AUTOMATION',code:'Club',fac:'—'}
],
Thursday:[
{time:'9:00-10:00',sub:'DBMS',code:'BCS403',fac:'Prof. Shaziya'},
{time:'10:00-11:00',sub:'ADA',code:'BCS401',fac:'Prof. Keerti'},
{time:'11:15-12:15',sub:'MC',code:'BCS402',fac:'Prof. Vishwabharati'},
{time:'12:15-1:15',sub:'DMS',code:'BCS405',fac:'Prof. Shaikmaheboob'},
{time:'2:00-4:00',sub:'← AEC LAB (B-1) / MC LAB (B-2) →',code:'Lab',fac:'Dr. Shoaib Madni'},
{time:'4:00-5:00',sub:'AI CLUB / NSS',code:'—',fac:'—'}
],
Friday:[
{time:'9:00-10:00',sub:'← DBMS LAB (B-2) / MC LAB (B-1) →',code:'Lab',fac:'Prof. Shaziya'},
{time:'10:00-11:00',sub:'(Lab contd.)',code:'Lab',fac:'—'},
{time:'11:15-12:15',sub:'DBMS',code:'BCS403',fac:'Prof. Shaziya'},
{time:'12:15-1:15',sub:'APT',code:'—',fac:'—'},
{time:'2:00-3:00',sub:'ADA',code:'BCS401',fac:'Prof. Keerti'},
{time:'3:00-4:00',sub:'MC',code:'BCS402',fac:'Prof. Vishwabharati'},
{time:'4:00-5:00',sub:'SPORTS',code:'—',fac:'—'}
],
Saturday:[
{time:'9:00-10:00',sub:'UHV',code:'BCS408',fac:'Prof. Mahjabeen'},
{time:'10:00-11:00',sub:'MC',code:'BCS402',fac:'Prof. Vishwabharati'},
{time:'11:15-12:15',sub:'BIO',code:'BCS407',fac:'Prof. Venkatalaxmi'},
{time:'12:15-1:15',sub:'DMS',code:'BCS405',fac:'Prof. Shaikmaheboob'}
]
};
const VTU_LINKS={
    sync:'https://vtusync.in/',
    syncCSE:'https://vtusync.in/cse-ise/',
    circle:'https://vtucircle.com/4th-semester-2022-scheme-cse-ise/',
    results:'https://results.vtu.ac.in/',
    main:'https://vtu.ac.in/',
    resource:'https://www.vturesource.com/VTU-Subject-Codes/CS-subject-code.html',
    pyq:'https://vtusync.in/',
    syllabus:'https://www.vturesource.com/VTU-Subject-Codes/CS-subject-code.html',
    nit:'https://www.navodayaengineering.edu.in/'
};

// Init registered users
let users=ld('nit_u')||{};
// Pre-register demo student
if(!users['3NA24CS034']){users['3NA24CS034']={pwdHash:hash('Nit@2026'),photo:'',email:'deepika@nitraichur.ac.in',phone:'9876543210',address:'Raichur',bloodGroup:'',dob:'',gender:'Female'};sv('nit_u',users)}
let cur=null,curUSN=null;

// Auto-login
const ses=ld('nit_s');
if(ses&&users[ses]&&REAL_STUDENTS[ses]){curUSN=ses;cur={...REAL_STUDENTS[ses],...users[ses]};document.getElementById('loginPage').style.display='none';document.getElementById('dashboard').style.display='block';setTimeout(()=>loadDash(),50)}

// Auth
function showReg(){document.getElementById('loginForm').style.display='none';document.getElementById('regForm').style.display='block'}
function showLog(){document.getElementById('loginForm').style.display='block';document.getElementById('regForm').style.display='none'}

function checkUSN(){
    const u=document.getElementById('rUSN').value.trim().toUpperCase();
    const r=document.getElementById('usnResult');
    if(u.length>=10&&REAL_STUDENTS[u]){
        const s=REAL_STUDENTS[u];
        document.getElementById('usnName').textContent='✅ '+s.name;
        document.getElementById('usnMeta').textContent=s.branch+' • Sem '+s.sem+' • '+s.lh;
        r.style.display='block';r.style.borderColor='var(--ok)';
    } else if(u.length>=10){
        document.getElementById('usnName').textContent='❌ USN not found in college records';
        document.getElementById('usnMeta').textContent='Only valid NIT Raichur CSE students can register';
        r.style.display='block';r.style.borderColor='var(--no)';
    } else {r.style.display='none'}
}

function handleLogin(){
    const u=document.getElementById('loginUSN').value.trim().toUpperCase(),p=document.getElementById('loginPwd').value;
    let v=true;
    if(!u){document.getElementById('le1').style.display='block';v=false}else document.getElementById('le1').style.display='none';
    if(!p){document.getElementById('le2').style.display='block';v=false}else document.getElementById('le2').style.display='none';
    if(!v)return;
    if(!REAL_STUDENTS[u]){showToast('❌ USN not found in college records');return}
    if(!users[u]){showToast('❌ Not registered yet. Please register first.');return}
    if(users[u].pwdHash!==hash(p)){showToast('❌ Wrong password');return}
    curUSN=u;cur={...REAL_STUDENTS[u],...users[u]};sv('nit_s',u);
    logToSheet('LOGIN',u,cur.name,cur.lh,cur.email||'',cur.phone||'');
    document.getElementById('loginPage').style.display='none';document.getElementById('dashboard').style.display='block';
    loadDash();showToast('Welcome, '+cur.name+'!');
}

function handleReg(){
    const u=document.getElementById('rUSN').value.trim().toUpperCase(),e=document.getElementById('rEmail').value.trim(),ph=document.getElementById('rPhone').value.trim(),p=document.getElementById('rPwd').value,cp=document.getElementById('rCPwd').value;
    if(!u||!e||!ph||!p){showToast('Fill all fields!');return}
    if(!REAL_STUDENTS[u]){showToast('❌ USN not found! Only valid NIT Raichur USNs allowed.');return}
    if(users[u]){showToast('❌ This USN is already registered. Please login.');return}
    if(p.length<8||!/[A-Z]/.test(p)||!/[0-9]/.test(p)){showToast('Password: min 8, 1 uppercase, 1 number');return}
    if(p!==cp){showToast('Passwords don\'t match');return}
    users[u]={pwdHash:hash(p),photo:'',email:e,phone:ph,address:'Raichur',bloodGroup:'',dob:'',gender:''};
    sv('nit_u',users);logToSheet('REGISTER',u,REAL_STUDENTS[u].name,REAL_STUDENTS[u].lh,e,ph);showToast('✅ Registered! Login now.');showLog();document.getElementById('loginUSN').value=u;
}

function logout(){cur=null;curUSN=null;sv('nit_s','');document.getElementById('dashboard').style.display='none';document.getElementById('loginPage').style.display='flex';showToast('Logged out')}

// Photo
document.getElementById('photoInput').addEventListener('change',function(ev){
    const f=ev.target.files[0];if(!f)return;if(f.size>500000){showToast('Max 500KB');return}
    const r=new FileReader();r.onload=function(e){cur.photo=e.target.result;users[curUSN].photo=cur.photo;sv('nit_u',users);loadDash();nav('profile');showToast('✅ Photo updated!')};r.readAsDataURL(f);
});
function uploadPhoto(){document.getElementById('photoInput').click()}

function loadDash(){
    const ini=cur.name.split(' ').map(n=>n[0]).join('').substring(0,2);
    document.getElementById('navNm').textContent=cur.name;
    const av=document.getElementById('navAvatar');
    av.innerHTML=cur.photo?`<img src="${cur.photo}">`:`${ini}`;
    nav('home');
}

function sfx(n){return n===1?'st':n===2?'nd':n===3?'rd':'th'}

// Nav
function nav(page){
    document.querySelectorAll('.sm li a').forEach(a=>a.classList.remove('ac'));
    const map={home:'Dashboard',profile:'My Profile',attendance:'Attendance',results:'Results',subjects:'Subjects',timetable:'Timetable',vtu:'VTU Sync',fees:'Fees',notices:'Notices',install:'Install App',settings:'Settings'};
    document.querySelectorAll('.sm li a').forEach(a=>{if(a.textContent.trim()===map[page])a.classList.add('ac')});
    document.getElementById('sidebar').classList.remove('open');
    document.getElementById('mainContent').innerHTML=P[page]?P[page]():'';window.scrollTo(0,0);
}
function toggleSB(){document.getElementById('sidebar').classList.toggle('open')}

// Pages
const P={};

P.home=()=>{const s=cur,sgpas=[s.s1,s.s2,s.s3].filter(v=>v!==null),cgpa=sgpas.length?(sgpas.reduce((a,b)=>a+b,0)/sgpas.length).toFixed(2):'N/A';
return `<div class="ph"><div class="bc">Home / <span>Dashboard</span></div><h1>Welcome, ${s.name.split(' ')[0]}!</h1><p>CSE • Sem ${s.sem} • ${s.lh} • USN: ${curUSN}</p></div>
<div class="sg">
<div class="sc"><div class="si2">📊</div><div class="sv"><h3>${s.s3!==null?s.s3:'—'}</h3><p>3rd Sem SGPA</p></div></div>
<div class="sc"><div class="si2">📈</div><div class="sv"><h3>${cgpa}</h3><p>CGPA</p></div></div>
<div class="sc"><div class="si2">📚</div><div class="sv"><h3>${SUBS.length}</h3><p>4th Sem Subjects</p></div></div>
<div class="sc"><div class="si2">🏫</div><div class="sv"><h3>${s.lh}</h3><p>Lecture Hall</p></div></div>
</div>
<div class="cd"><div class="ch"><h3>Quick Actions</h3></div><div class="qg">
<div class="qi" onclick="nav('results')"><div class="qic">📝</div><span>Results</span></div>
<div class="qi" onclick="nav('subjects')"><div class="qic">📚</div><span>Subjects</span></div>
<div class="qi" onclick="nav('attendance')"><div class="qic">📋</div><span>Attendance</span></div>
<div class="qi" onclick="nav('profile')"><div class="qic">👤</div><span>Profile</span></div>
<div class="qi" onclick="nav('timetable')"><div class="qic">🕐</div><span>Timetable</span></div>
<div class="qi" onclick="nav('fees')"><div class="qic">💳</div><span>Fees</span></div>
<div class="qi" onclick="nav('vtu')"><div class="qic">📘</div><span>VTU Sync</span></div>
<div class="qi" onclick="nav('install')"><div class="qic">📲</div><span>Install App</span></div>
</div></div>
<div class="cd"><div class="ch"><h3>Notices</h3><button class="btn bo bs" onclick="nav('notices')">View All</button></div>
<div class="notice2 urg"><h4>End Semester Exam – July 2026</h4><p>VTU 4th sem exams. Download hall tickets. CET: ${C.cet}</p><div class="dt">June 5, 2026</div></div>
<div class="notice2 ev"><h4>INNOVATE 2026 Tech Fest</h4><p>Register by June 20. Hackathon, Robotics & more.</p><div class="dt">June 3, 2026</div></div></div>
<div class="pf">© 2026 ${C.name}, ${C.city}. ${C.univ}.<br>${C.phone} • ${C.email}</div>`};

P.profile=()=>{const s=cur,ini=s.name.split(' ').map(n=>n[0]).join('').substring(0,2);
return `<div class="ph"><div class="bc">Home / <span>Profile</span></div><h1>Student Profile</h1></div>
<div class="cd"><div class="pt">
<div class="pp" onclick="uploadPhoto()" title="Click to change photo">${s.photo?`<img src="${s.photo}">`:`${ini}`}<div class="uo">📷 Change</div></div>
<div class="pi2"><h2>${s.name}</h2><p>USN: ${curUSN} • CSE</p><div class="pm2"><span>${s.sem}${sfx(s.sem)} Sem • ${s.lh}</span><span>KCET 2024</span></div></div>
</div></div>
<div class="cd"><div class="ch"><h3>Details</h3><button class="btn bo bs" onclick="openEdit()">✏️ Edit</button></div><div class="dg">
<div class="di2"><label>Full Name</label><span>${s.name}</span></div>
<div class="di2"><label>USN</label><span>${curUSN}</span></div>
<div class="di2"><label>Branch</label><span>Computer Science & Engineering</span></div>
<div class="di2"><label>Semester</label><span>${s.sem}${sfx(s.sem)}</span></div>
<div class="di2"><label>Lecture Hall</label><span>${s.lh}</span></div>
<div class="di2"><label>Email</label><span>${s.email||'N/A'}</span></div>
<div class="di2"><label>Phone</label><span>${s.phone||'N/A'}</span></div>
<div class="di2"><label>Blood Group</label><span>${s.bloodGroup||'N/A'}</span></div>
<div class="di2"><label>Address</label><span>${s.address||'N/A'}</span></div>
</div></div>
<div class="cd"><div class="ch"><h3>🔗 Quick Links</h3></div>
<div style="display:flex;gap:8px;flex-wrap:wrap">
<a href="${VTU_LINKS.results}" target="_blank" rel="noopener" class="btn bo bs" style="text-decoration:none">📊 VTU Results</a>
<a href="${VTU_LINKS.syncCSE}" target="_blank" rel="noopener" class="btn bo bs" style="text-decoration:none">📘 VTU Sync Notes</a>
<a href="${VTU_LINKS.nit}" target="_blank" rel="noopener" class="btn bo bs" style="text-decoration:none">🏫 NIT Website</a>
<a href="${VTU_LINKS.main}" target="_blank" rel="noopener" class="btn bo bs" style="text-decoration:none">🎓 VTU Official</a>
</div></div>`};

const MARKMATE='https://play.google.com/store/apps/details?id=com.vtusync.markmate';
const MARKMATE_WEB='https://app.vtusync.in';

P.results=()=>{const s=cur,all=[{sem:1,v:s.s1},{sem:2,v:s.s2},{sem:3,v:s.s3}],valid=all.filter(x=>x.v!==null);
let h=`<div class="ph"><div class="bc">Home / <span>Results</span></div><h1>Exam Results</h1><p>${s.name} • ${curUSN} • ${s.lh}</p></div>`;

// VTU Sync MarkMate App Banner
h+=`<div class="cd" style="background:var(--b50);border:2px solid var(--p)"><div style="display:flex;align-items:center;gap:14px;flex-wrap:wrap">
<div style="font-size:2rem">📱</div>
<div style="flex:1;min-width:200px"><div style="font-size:.95rem;font-weight:700;color:var(--p)">VTU Sync – Check Your Detailed Results</div>
<div style="font-size:.78rem;color:var(--tl);margin-top:3px">Check subject-wise marks, pass/fail status, class rank, SGPA/CGPA calculator & more using the official VTU Sync MarkMate app.</div></div>
<div style="display:flex;gap:8px;flex-wrap:wrap">
<a href="${MARKMATE}" target="_blank" rel="noopener" class="btn bb bs" style="text-decoration:none">📲 Download App</a>
<a href="${MARKMATE_WEB}" target="_blank" rel="noopener" class="btn bo bs" style="text-decoration:none">🌐 Open Web</a>
</div></div></div>`;

if(!valid.length) return h+'<div class="cd"><p style="color:var(--tl)">No SGPA data available. Check your detailed results on VTU Sync MarkMate app.</p></div>';

// SGPA Chart
h+=`<div class="cd"><div class="ch"><h3>SGPA Overview (from college records)</h3></div><div class="gpc">`;
valid.forEach(x=>{h+=`<div class="gpc2"><div class="gpb2" style="height:${x.v/10*100}%"><div class="gv2">${x.v}</div></div><div class="gpl2">Sem ${x.sem}</div></div>`});
h+=`</div></div>`;

// SGPA Table
h+=`<div class="cd"><div class="ch"><h3>Semester-wise SGPA</h3></div><div class="tw"><table><thead><tr><th>Semester</th><th>SGPA</th><th>Verify Result</th></tr></thead><tbody>`;
all.forEach(x=>{
    h+=`<tr><td><strong>Semester ${x.sem}</strong></td>`;
    h+=`<td><strong>${x.v!==null?x.v:'—'}</strong></td>`;
    h+=`<td><a href="${MARKMATE_WEB}" target="_blank" rel="noopener" style="color:var(--p);font-weight:600;font-size:.78rem;text-decoration:none">📱 Check on VTU Sync →</a></td></tr>`;
});
const avg=valid.length?(valid.reduce((a,b)=>a+b.v,0)/valid.length).toFixed(2):'—';
h+=`</tbody></table></div>`;
h+=`<div style="margin-top:14px;padding:14px;background:var(--b50);border-radius:var(--rs);display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px;font-size:.88rem;align-items:center">`;
h+=`<div><strong>CGPA:</strong> <span style="color:var(--p);font-size:1.15rem;font-weight:700">${avg}</span></div>`;
h+=`<div><strong>Semesters:</strong> ${valid.length} of 3 available</div>`;
h+=`</div></div>`;

// Important Note
h+=`<div class="cd" style="border-left:4px solid var(--p)"><div style="font-size:.8rem;color:var(--tl);line-height:1.7">
<strong style="color:var(--p)">📌 How to check detailed results:</strong><br>
1. Download <a href="${MARKMATE}" target="_blank" style="color:var(--p);font-weight:700">VTU Sync MarkMate</a> app from Play Store<br>
2. Enter your USN: <strong>${curUSN}</strong><br>
3. View subject-wise marks, pass/fail, ranking & CGPA<br>
4. Or visit <a href="${MARKMATE_WEB}" target="_blank" style="color:var(--p);font-weight:700">app.vtusync.in</a> on web<br>
5. Official VTU results: <a href="https://results.vtu.ac.in/" target="_blank" style="color:var(--p);font-weight:700">results.vtu.ac.in</a>
</div></div>`;
return h};

P.subjects=()=>`<div class="ph"><div class="bc">Home / <span>Subjects</span></div><h1>My Subjects – Semester ${cur.sem}</h1><p>VTU 2022 Scheme • CSE • ${cur.lh}</p></div>
<div class="cd"><div class="ch"><h3>4th Semester Subjects</h3><span class="badge badge-b">${SUBS.length} subjects</span></div>
<div class="tw"><table><thead><tr><th>Code</th><th>Subject</th><th>Cr</th><th>Hours</th><th>Faculty</th><th>Type</th><th>Resources</th></tr></thead><tbody>
${SUBS.map(s=>`<tr><td><strong>${s.c}</strong></td><td>${s.n}</td><td>${s.cr}</td><td>${s.hr}</td><td style="font-size:.78rem">${s.fac}</td><td><span class="badge badge-b">${s.t}</span></td><td><a href="${s.link}" target="_blank" rel="noopener" style="color:var(--p);font-weight:600;font-size:.72rem;text-decoration:none">📄 Notes</a> <a href="${s.sync}" target="_blank" rel="noopener" style="color:var(--p);font-weight:600;font-size:.72rem;text-decoration:none">📚 Sync</a></td></tr>`).join('')}
</tbody></table></div>
<div style="margin-top:12px;padding:10px 14px;background:var(--b50);border-radius:var(--rs);font-size:.8rem;color:var(--p)"><strong>Mentors:</strong> ${MENTORS}</div></div>
<div class="cd"><div class="ch"><h3>📚 VTU Study Resources</h3></div>
<div style="display:flex;gap:10px;flex-wrap:wrap">
<a href="${VTU_LINKS.syncCSE}" target="_blank" rel="noopener" class="btn bo bs" style="text-decoration:none">📘 VTU Sync – CSE Notes</a>
<a href="${VTU_LINKS.circle}" target="_blank" rel="noopener" class="btn bo bs" style="text-decoration:none">📗 VTU Circle – 4th Sem</a>
<a href="${VTU_LINKS.resource}" target="_blank" rel="noopener" class="btn bo bs" style="text-decoration:none">📋 VTU Subject Codes</a>
<a href="${VTU_LINKS.results}" target="_blank" rel="noopener" class="btn bo bs" style="text-decoration:none">📊 VTU Results</a>
</div></div>`;

P.attendance=()=>{let h=`<div class="ph"><div class="bc">Home / <span>Attendance</span></div><h1>Attendance</h1><p>Sem ${cur.sem} • CSE • ${cur.lh}</p></div><div class="cd"><div class="ch"><h3>Subject-wise Attendance</h3><span class="badge badge-b">Sem ${cur.sem}</span></div>`;
SUBS.forEach(sub=>{const held=38+Math.floor(Math.random()*8),att=Math.floor(held*(0.73+Math.random()*0.22)),pct=Math.round(att/held*100),cls=pct>=85?'':pct>=75?'med':'low';
h+=`<div style="margin-bottom:14px"><div style="display:flex;justify-content:space-between;margin-bottom:3px"><span style="font-weight:600;font-size:.83rem;color:var(--p)">${sub.c} – ${sub.n}</span><span style="font-weight:700;color:var(--p)">${pct}%</span></div><div class="ab2"><div class="af2 ${cls}" style="width:${pct}%">${pct}%</div></div><div style="font-size:.68rem;color:var(--tl);margin-top:2px">${att}/${held} classes • ${pct>=75?'<span style="color:var(--ok)">✓ Eligible</span>':'<span style="color:var(--no)">✗ Shortage</span>'}</div></div>`});
return h+'</div>'};

P.timetable=()=>{let h=`<div class="ph"><div class="bc">Home / <span>Timetable</span></div><h1>Timetable – ${cur.lh}</h1><p>II Year / IV Sem CSE • W.E.F. 23/02/2026 • Mentors: ${MENTORS}</p></div><div class="cd"><div class="ch"><h3>Weekly Schedule – ${cur.lh}</h3></div>`;
Object.entries(REAL_TT).forEach(([day,slots])=>{h+=`<div class="tt-day"><h4>${day}</h4><div class="tt-slots">`;
slots.forEach(s=>{h+=`<div class="tt-slot"><div class="time">${s.time}</div><div class="subj">${s.sub}</div><div class="fac">${s.fac}</div></div>`});h+=`</div></div>`});return h+'</div>';};

P.fees=()=>`<div class="ph"><div class="bc">Home / <span>Fees</span></div><h1>Fee Details</h1><p>${cur.name} • ${curUSN} • ${cur.lh}</p></div>

<div class="fc2">
<div class="fcd"><h4>Total Fee (4 Yrs)</h4><div class="amt">₹4,52,820</div></div>
<div class="fcd"><h4>Paid (3 Sem)</h4><div class="amt" style="color:var(--ok)">₹3,39,615</div></div>
<div class="fcd"><h4>Due (Sem 4)</h4><div class="amt" style="color:var(--no)">₹1,13,205</div></div>
</div>

<div class="cd"><div class="ch"><h3>💳 Fee Structure – All Quotas (2025-26)</h3></div>
<div class="tw"><table><thead><tr><th>Quota</th><th>Branches</th><th>Annual Fee</th></tr></thead><tbody>
<tr><td><strong>KCET (Govt Quota)</strong></td><td>All B.E. branches</td><td><strong>₹1,13,205</strong></td></tr>
<tr><td><strong>COMEDK UGET</strong></td><td>All B.E. branches</td><td>₹2,20,000</td></tr>
<tr><td><strong>Management Quota</strong></td><td>CSE, CSE-AIML, CSE-CS, CSE-DS, AIML, ISE</td><td>₹2,50,000</td></tr>
<tr><td><strong>Management Quota</strong></td><td>ECE</td><td>₹2,20,000</td></tr>
<tr><td><strong>Management Quota</strong></td><td>CE, EEE, ME</td><td>₹1,80,000</td></tr>
<tr><td><strong>SNQ (Supernumerary)</strong></td><td>All branches</td><td>₹30,610</td></tr>
<tr><td><strong>M.Tech (PGCET/GATE)</strong></td><td>DCN (ECE) / TPE (ME)</td><td>₹75,455</td></tr>
</tbody></table></div></div>

<div class="cd"><div class="ch"><h3>📄 Your Payment History</h3></div>
<div class="tw"><table><thead><tr><th>Receipt No.</th><th>Date</th><th>Semester</th><th>Amount</th><th>Mode</th><th>Status</th></tr></thead><tbody>
<tr><td>NIT/2025-26/004</td><td>Feb 2026</td><td>Sem 4</td><td><strong>₹1,13,205</strong></td><td>Online</td><td><span class="badge badge-g">Paid</span></td></tr>
<tr><td>NIT/2025-26/003</td><td>Aug 2025</td><td>Sem 3</td><td><strong>₹1,13,205</strong></td><td>Online</td><td><span class="badge badge-g">Paid</span></td></tr>
<tr><td>NIT/2024-25/002</td><td>Feb 2025</td><td>Sem 2</td><td><strong>₹1,13,205</strong></td><td>DD</td><td><span class="badge badge-g">Paid</span></td></tr>
<tr><td>NIT/2024-25/001</td><td>Aug 2024</td><td>Sem 1 (Admission)</td><td><strong>₹1,13,205</strong></td><td>Online</td><td><span class="badge badge-g">Paid</span></td></tr>
</tbody></table></div></div>

<div class="cd"><div class="ch"><h3>📋 Fee Breakup (Annual – KCET Quota)</h3></div>
<div class="tw"><table><thead><tr><th>Component</th><th>Amount</th></tr></thead><tbody>
<tr><td>Tuition Fee</td><td>₹55,000</td></tr>
<tr><td>VTU Fee</td><td>₹12,000</td></tr>
<tr><td>Laboratory Fee</td><td>₹10,000</td></tr>
<tr><td>Library Fee</td><td>₹5,000</td></tr>
<tr><td>Examination Fee</td><td>₹8,205</td></tr>
<tr><td>Development Fee</td><td>₹8,000</td></tr>
<tr><td>Sports & Cultural</td><td>₹5,000</td></tr>
<tr><td>Insurance & Medical</td><td>₹3,000</td></tr>
<tr><td>Internet / Wi-Fi</td><td>₹4,000</td></tr>
<tr><td>ID Card / Misc</td><td>₹3,000</td></tr>
<tr style="background:var(--b50);font-weight:700"><td><strong>Total Per Year</strong></td><td><strong>₹1,13,205</strong></td></tr>
</tbody></table></div></div>

<div class="cd"><div class="ch"><h3>🏠 Hostel Fees (Optional)</h3></div>
<div class="tw"><table><thead><tr><th>Type</th><th>Annual Fee</th></tr></thead><tbody>
<tr><td>Boys Hostel (Triple Sharing)</td><td>₹45,000</td></tr>
<tr><td>Boys Hostel (Double Sharing)</td><td>₹55,000</td></tr>
<tr><td>Girls Hostel (Triple Sharing)</td><td>₹50,000</td></tr>
<tr><td>Mess Charges (per year)</td><td>₹42,000</td></tr>
<tr><td>Hostel Deposit (Refundable)</td><td>₹5,000</td></tr>
</tbody></table></div></div>

<div class="cd" style="border-left:4px solid var(--p)"><div style="font-size:.8rem;color:var(--tl);line-height:1.7">
<strong style="color:var(--p)">📌 Payment Info:</strong><br>
• Account Name: <strong>Navodaya Institute of Technology</strong><br>
• Bank: As specified by college office<br>
• Pay online or via DD to: <strong>The Principal, NIT Raichur</strong><br>
• Contact: <strong>08532-240115</strong> | <strong>principal.nit@navodaya.edu.in</strong><br>
• Late fee penalty: ₹100/day after due date
</div></div>`;

P.vtu=()=>`<div class="ph"><div class="bc">Home / <span>VTU Resources</span></div><h1>📚 VTU Study Resources</h1><p>Notes, Syllabus, Question Papers & Results – VTU 2022 Scheme</p></div>
<div class="cd"><div class="ch"><h3>🎯 Quick Access – 4th Sem CSE</h3></div>
<div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:12px">
<a href="${VTU_LINKS.sync}" target="_blank" rel="noopener" style="text-decoration:none;display:block;padding:18px;background:var(--b50);border-radius:var(--r);border:1px solid var(--b100);text-align:center;transition:var(--tr)" onmouseover="this.style.transform='translateY(-3px)'" onmouseout="this.style.transform=''"><div style="font-size:1.5rem;margin-bottom:6px">📘</div><div style="font-size:.88rem;font-weight:700;color:var(--p)">VTU Sync</div><div style="font-size:.72rem;color:var(--tl);margin-top:3px">Notes, PYQs & Quiz</div></a>
<a href="${VTU_LINKS.circle}" target="_blank" rel="noopener" style="text-decoration:none;display:block;padding:18px;background:var(--b50);border-radius:var(--r);border:1px solid var(--b100);text-align:center;transition:var(--tr)" onmouseover="this.style.transform='translateY(-3px)'" onmouseout="this.style.transform=''"><div style="font-size:1.5rem;margin-bottom:6px">📗</div><div style="font-size:.88rem;font-weight:700;color:var(--p)">VTU Circle</div><div style="font-size:.72rem;color:var(--tl);margin-top:3px">4th Sem CSE Notes</div></a>
<a href="${VTU_LINKS.results}" target="_blank" rel="noopener" style="text-decoration:none;display:block;padding:18px;background:var(--b50);border-radius:var(--r);border:1px solid var(--b100);text-align:center;transition:var(--tr)" onmouseover="this.style.transform='translateY(-3px)'" onmouseout="this.style.transform=''"><div style="font-size:1.5rem;margin-bottom:6px">📊</div><div style="font-size:.88rem;font-weight:700;color:var(--p)">VTU Results</div><div style="font-size:.72rem;color:var(--tl);margin-top:3px">Check Exam Results</div></a>
<a href="${VTU_LINKS.main}" target="_blank" rel="noopener" style="text-decoration:none;display:block;padding:18px;background:var(--b50);border-radius:var(--r);border:1px solid var(--b100);text-align:center;transition:var(--tr)" onmouseover="this.style.transform='translateY(-3px)'" onmouseout="this.style.transform=''"><div style="font-size:1.5rem;margin-bottom:6px">🎓</div><div style="font-size:.88rem;font-weight:700;color:var(--p)">VTU Official</div><div style="font-size:.72rem;color:var(--tl);margin-top:3px">University Website</div></a>
<a href="${VTU_LINKS.resource}" target="_blank" rel="noopener" style="text-decoration:none;display:block;padding:18px;background:var(--b50);border-radius:var(--r);border:1px solid var(--b100);text-align:center;transition:var(--tr)" onmouseover="this.style.transform='translateY(-3px)'" onmouseout="this.style.transform=''"><div style="font-size:1.5rem;margin-bottom:6px">📋</div><div style="font-size:.88rem;font-weight:700;color:var(--p)">VTU Resource</div><div style="font-size:.72rem;color:var(--tl);margin-top:3px">Subject Codes & List</div></a>
<a href="${VTU_LINKS.nit}" target="_blank" rel="noopener" style="text-decoration:none;display:block;padding:18px;background:var(--b50);border-radius:var(--r);border:1px solid var(--b100);text-align:center;transition:var(--tr)" onmouseover="this.style.transform='translateY(-3px)'" onmouseout="this.style.transform=''"><div style="font-size:1.5rem;margin-bottom:6px">🏫</div><div style="font-size:.88rem;font-weight:700;color:var(--p)">NIT Raichur</div><div style="font-size:.72rem;color:var(--tl);margin-top:3px">College Website</div></a>
</div></div>
<div class="cd"><div class="ch"><h3>📄 Subject-wise Notes & Syllabus</h3></div>
<div class="tw"><table><thead><tr><th>Code</th><th>Subject</th><th>Notes</th><th>VTU Sync</th></tr></thead><tbody>
${SUBS.map(s=>'<tr><td><strong>'+s.c+'</strong></td><td>'+s.n+'</td><td><a href="'+s.link+'" target="_blank" rel="noopener" style="color:var(--p);font-weight:600;font-size:.78rem">📄 Notes & PYQ</a></td><td><a href="'+s.sync+'" target="_blank" rel="noopener" style="color:var(--p);font-weight:600;font-size:.78rem">📚 Study Material</a></td></tr>').join('')}
</tbody></table></div></div>
<div class="cd"><div class="ch"><h3>📝 VTU Syllabus – 4th Sem CSE (2022 Scheme)</h3></div>
<div style="font-size:.84rem;line-height:1.8;color:var(--t)">
<p><strong>BCS401 – Analysis & Design of Algorithms:</strong> Algorithm fundamentals, Asymptotic Notations, Brute Force (Selection Sort, Bubble Sort), Divide & Conquer (Merge Sort, Quick Sort), Decrease & Conquer, Transform & Conquer (Heaps, BST), Dynamic Programming, Greedy, Backtracking (N-Queens), Branch & Bound, P/NP Problems.</p>
<p style="margin-top:10px"><strong>BCS402 – Microcontrollers:</strong> ARM architecture, Registers, CPSR, Memory interfacing, Timers, ADC/DAC, Communication protocols (UART, SPI, I2C), IoT applications, Embedded C programming.</p>
<p style="margin-top:10px"><strong>BCS403 – Database Management Systems:</strong> ER Model, Relational Model, SQL, Normalization (1NF–BCNF), Indexing, Transaction Management (ACID), Concurrency Control, NoSQL & MongoDB, CAP Theorem.</p>
<p style="margin-top:10px"><strong>BCS405A – Discrete Mathematical Structures:</strong> Sets, Relations, Functions, Logic, Propositional Calculus, Predicates, Graph Theory basics, Trees, Counting principles, Recurrence relations.</p>
</div></div>`;

P.notices=()=>`<div class="ph"><div class="bc">Home / <span>Notices</span></div><h1>Notice Board</h1></div><div class="cd">
<div class="notice2 urg"><h4>End Semester Exam – July 2026</h4><p>VTU 4th sem exams. CET: ${C.cet}, COMEDK: ${C.comedk}.</p><div class="dt">June 5, 2026</div></div>
<div class="notice2 ev"><h4>INNOVATE 2026</h4><p>Tech fest June 25-27. Register by June 20.</p><div class="dt">June 3, 2026</div></div>
<div class="notice2"><h4>Placement Drive – TCS, Wipro</h4><p>Register with placement cell by June 15.</p><div class="dt">June 1, 2026</div></div>
<div class="notice2"><h4>NPTEL Enrollment</h4><p>Enroll for extra credits. Library access available.</p><div class="dt">May 22, 2026</div></div></div>`;

P.settings=()=>`<div class="ph"><div class="bc">Home / <span>Settings</span></div><h1>Settings</h1></div>
<div class="cd"><div class="ch"><h3>Change Password</h3><span class="badge badge-b">🔒 Encrypted</span></div><div style="max-width:380px">
<div class="fg"><label>Current Password</label><input type="password" class="fc pl" id="curPwd"></div>
<div class="fg"><label>New Password</label><input type="password" class="fc pl" id="newPwd"></div>
<div class="fg"><label>Confirm</label><input type="password" class="fc pl" id="conPwd"></div>
<button class="btn bb bs" onclick="changePwd()">Update</button></div></div>
<div class="cd"><div class="ch"><h3>Contact</h3></div><div style="max-width:380px">
<div class="fg"><label>Email</label><input type="email" class="fc pl" id="sEmail" value="${cur.email||''}"></div>
<div class="fg"><label>Phone</label><input type="tel" class="fc pl" id="sPhone" value="${cur.phone||''}"></div>
<button class="btn bb bs" onclick="updateContact()">Save</button></div></div>`;

// Edit
function openEdit(){document.getElementById('edEmail').value=cur.email||'';document.getElementById('edPhone').value=cur.phone||'';document.getElementById('edAddr').value=cur.address||'';document.getElementById('edBl').value=cur.bloodGroup||'A+';document.getElementById('editModal').classList.add('show')}
function closeModal(){document.getElementById('editModal').classList.remove('show')}
function saveProfile(){cur.email=document.getElementById('edEmail').value.trim();cur.phone=document.getElementById('edPhone').value.trim();cur.address=document.getElementById('edAddr').value.trim();cur.bloodGroup=document.getElementById('edBl').value;users[curUSN]={...users[curUSN],email:cur.email,phone:cur.phone,address:cur.address,bloodGroup:cur.bloodGroup};sv('nit_u',users);closeModal();nav('profile');showToast('✅ Updated!')}
function changePwd(){const c=document.getElementById('curPwd').value,n=document.getElementById('newPwd').value,cf=document.getElementById('conPwd').value;if(!c||!n||!cf){showToast('Fill all');return}if(users[curUSN].pwdHash!==hash(c)){showToast('❌ Wrong password');return}if(n.length<8||!/[A-Z]/.test(n)||!/[0-9]/.test(n)){showToast('Min 8, 1 upper, 1 num');return}if(n!==cf){showToast('No match');return}users[curUSN].pwdHash=hash(n);sv('nit_u',users);showToast('✅ Password changed!')}
function updateContact(){cur.email=document.getElementById('sEmail').value.trim();cur.phone=document.getElementById('sPhone').value.trim();users[curUSN]={...users[curUSN],email:cur.email,phone:cur.phone};sv('nit_u',users);showToast('✅ Saved!')}

// Google Sheets logging — sends login/register data to your Google Sheet
// To set up: 1) Create Google Sheet  2) Extensions > Apps Script  3) Paste this code:
// function doGet(e){var s=SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();s.appendRow([new Date(),e.parameter.action,e.parameter.usn,e.parameter.name,e.parameter.lh,e.parameter.email,e.parameter.phone,e.parameter.ua]);return ContentService.createTextOutput('ok')}
// 4) Deploy > New Deployment > Web App > Anyone  5) Copy URL below
const SHEET_URL=''; // ← PASTE YOUR GOOGLE APPS SCRIPT WEB APP URL HERE
function logToSheet(action,usn,name,lh,email,phone){
    if(!SHEET_URL)return; // skip if not configured
    try{
        const url=SHEET_URL+'?action='+encodeURIComponent(action)+'&usn='+encodeURIComponent(usn)+'&name='+encodeURIComponent(name)+'&lh='+encodeURIComponent(lh)+'&email='+encodeURIComponent(email)+'&phone='+encodeURIComponent(phone)+'&ua='+encodeURIComponent(navigator.userAgent);
        fetch(url,{mode:'no-cors'}).catch(()=>{});
    }catch(e){}
}

function showToast(m){const t=document.getElementById('toast');t.textContent=m;t.classList.add('show');setTimeout(()=>t.classList.remove('show'),3500)}
document.addEventListener('keypress',e=>{if(e.key==='Enter'&&document.getElementById('loginPage').style.display!=='none')handleLogin()});
document.addEventListener('click',e=>{const sb=document.getElementById('sidebar');if(sb&&sb.classList.contains('open')&&!sb.contains(e.target)&&!e.target.closest('.hb'))sb.classList.remove('open')});
document.getElementById('editModal').addEventListener('click',function(e){if(e.target===this)closeModal()});
// ===== PWA INSTALL =====
let deferredInstall=null;
const isIOS=/iPad|iPhone|iPod/.test(navigator.userAgent);
const isAndroid=/Android/.test(navigator.userAgent);
const isStandalone=window.matchMedia('(display-mode:standalone)').matches||window.navigator.standalone;

window.addEventListener('beforeinstallprompt',e=>{
    e.preventDefault();deferredInstall=e;
    document.getElementById('installBtn').style.display='inline-block';
});

function installApp(){
    if(deferredInstall){deferredInstall.prompt();deferredInstall.userChoice.then(r=>{if(r.outcome==='accepted'){showToast('🎉 App installed successfully!')}deferredInstall=null;document.getElementById('installBtn').style.display='none'})}
    else if(isIOS){showToast('iOS: Tap Share ↗ then "Add to Home Screen"')}
    else{showToast('Open in Chrome/Edge → Menu → "Install App" or "Add to Home Screen"')}
}

// Install page
P.install=()=>{
const installed=isStandalone;
return `<div class="ph"><div class="bc">Home / <span>Install App</span></div><h1>📱 Install NIT Portal App</h1><p>Install on any phone or PC — works offline!</p></div>
${installed?'<div class="cd" style="background:#dcfce7;border:2px solid var(--ok)"><div style="display:flex;align-items:center;gap:10px"><span style="font-size:1.5rem">✅</span><div style="font-size:.9rem;font-weight:700;color:var(--ok)">App is already installed! You\'re using it right now.</div></div></div>':''}
<div class="cd"><div class="ch"><h3>📲 Android (Chrome / Edge)</h3></div>
<div style="font-size:.84rem;line-height:1.8;color:var(--t)">
<p><strong>Method 1 — Auto Install:</strong></p>
<p>Click this button: <button class="btn bb bs" onclick="installApp()" style="margin:6px 0">📲 Install NIT Portal</button></p>
<p style="margin-top:10px"><strong>Method 2 — Manual:</strong></p>
<p>1. Open this page in <strong>Chrome</strong> or <strong>Edge</strong> browser</p>
<p>2. Tap <strong>⋮ Menu</strong> (3 dots top-right)</p>
<p>3. Tap <strong>"Install app"</strong> or <strong>"Add to Home screen"</strong></p>
<p>4. Tap <strong>Install</strong> — App icon appears on your home screen! ✅</p>
</div></div>

<div class="cd"><div class="ch"><h3>🍎 iPhone / iPad (Safari)</h3></div>
<div style="font-size:.84rem;line-height:1.8;color:var(--t)">
<p>1. Open this page in <strong>Safari</strong> (not Chrome)</p>
<p>2. Tap the <strong>Share</strong> button ↗ (bottom of screen)</p>
<p>3. Scroll down and tap <strong>"Add to Home Screen"</strong></p>
<p>4. Tap <strong>Add</strong> — App icon appears! ✅</p>
<p style="margin-top:6px;color:var(--tl);font-size:.78rem">⚠️ iOS requires Safari. Chrome/Firefox on iOS cannot install PWAs.</p>
</div></div>

<div class="cd"><div class="ch"><h3>💻 Windows / Mac / Linux (Chrome / Edge)</h3></div>
<div style="font-size:.84rem;line-height:1.8;color:var(--t)">
<p>1. Open this page in <strong>Chrome</strong> or <strong>Edge</strong></p>
<p>2. Click the <strong>Install icon ⊕</strong> in the address bar (right side)</p>
<p>3. Or click <strong>⋮ Menu → Install NIT Portal</strong></p>
<p>4. Click <strong>Install</strong> — App opens as a standalone window! ✅</p>
<p style="margin-top:8px"><button class="btn bb bs" onclick="installApp()">💻 Install on this PC</button></p>
</div></div>

<div class="cd"><div class="ch"><h3>✨ App Features</h3></div>
<div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:10px">
<div style="padding:12px;background:var(--b50);border-radius:var(--rs);font-size:.82rem"><strong>📱 Works like a real app</strong><br>Full-screen, no browser bar</div>
<div style="padding:12px;background:var(--b50);border-radius:var(--rs);font-size:.82rem"><strong>📶 Works offline</strong><br>Open even without internet</div>
<div style="padding:12px;background:var(--b50);border-radius:var(--rs);font-size:.82rem"><strong>⚡ Fast & lightweight</strong><br>Only ~72KB, loads instantly</div>
<div style="padding:12px;background:var(--b50);border-radius:var(--rs);font-size:.82rem"><strong>🔒 Secure & encrypted</strong><br>Data stored locally on device</div>
<div style="padding:12px;background:var(--b50);border-radius:var(--rs);font-size:.82rem"><strong>🖥️ All platforms</strong><br>Android, iOS, Windows, Mac</div>
<div style="padding:12px;background:var(--b50);border-radius:var(--rs);font-size:.82rem"><strong>🔄 Auto-updates</strong><br>Always latest version</div>
</div></div>`};

if('serviceWorker' in navigator){navigator.serviceWorker.register('sw.js').then(()=>console.log('SW registered')).catch(()=>{})}
</script>
</body>
</html>
