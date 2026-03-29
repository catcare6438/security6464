<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,user-scalable=no">
<title>浪貓不浪 🐾</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700;900&family=Nunito:wght@700;800;900&display=swap" rel="stylesheet">
<style>
/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   DESIGN TOKENS  (user-specified palette)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
:root{
  --p1:#FFB7C5;--p2:#FF8FAB;--p3:#E05070;
  --y1:#FFE0A3;--y2:#FFCA6A;
  --b1:#B8E4FF;--b2:#7DC8F5;--b3:#4EA8D8;
  --g1:#B8F0C8;--g2:#7DD99A;--g3:#4EBB72;
  --lav:#E8D5FF;--lav2:#C8A8F0;
  --bg:#FFF0F5;--bg2:#FFF8FC;--bg3:#FFEAF2;
  --text:#3D2B35;--mid:#7A5C68;--soft:#B08A9A;
  --shadow:0 3px 14px rgba(224,80,112,.1);
  --shadow2:0 6px 24px rgba(224,80,112,.15);
  --card-r:20px;
  --font-d:'Nunito',sans-serif;
  --font-b:'Noto Sans TC',sans-serif;
}
*{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent;}
html,body{height:100%;overflow:hidden;background:var(--bg);}
body{font-family:var(--font-b);color:var(--text);}
input,textarea,select,button{font-family:inherit;}
::-webkit-scrollbar{width:5px;height:5px;}
::-webkit-scrollbar-track{background:transparent;}
::-webkit-scrollbar-thumb{background:var(--p1);border-radius:3px;}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   CRAYON TEXTURE + BACKGROUNDS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
body::before{
  content:'';position:fixed;inset:0;pointer-events:none;z-index:0;
  background-image:
    radial-gradient(circle at 15% 20%,rgba(255,183,197,.25) 0%,transparent 50%),
    radial-gradient(circle at 85% 75%,rgba(184,228,255,.25) 0%,transparent 50%),
    radial-gradient(circle at 50% 50%,rgba(255,224,163,.1) 0%,transparent 60%);
}
/* crayon paper grain */
body::after{
  content:'';position:fixed;inset:0;pointer-events:none;z-index:0;opacity:.03;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23n)' opacity='1'/%3E%3C/svg%3E");
}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   SCREEN SYSTEM
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.screen{display:none;position:fixed;inset:0;z-index:10;flex-direction:column;overflow:hidden;}
.screen.on{display:flex;}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   LOGIN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
#sLogin{
  align-items:center;justify-content:center;padding:20px;
  background:linear-gradient(160deg,#FFE8F0 0%,#FFF5FB 40%,#EAF6FF 100%);
}
/* deco paws behind login */
#sLogin::before{
  content:'🐾';position:absolute;font-size:8rem;opacity:.07;
  top:10%;right:5%;transform:rotate(20deg);
}
#sLogin::after{
  content:'🐾';position:absolute;font-size:5rem;opacity:.07;
  bottom:12%;left:8%;transform:rotate(-15deg);
}
.login-card{
  background:rgba(255,255,255,.85);
  border:2.5px solid var(--p1);
  border-radius:32px;
  padding:36px 32px 32px;
  width:100%;max-width:360px;
  text-align:center;
  box-shadow:var(--shadow2),inset 0 1px 0 rgba(255,255,255,.9);
  position:relative;z-index:1;
  /* crayon border-radius quirk */
  border-radius:32px 28px 34px 30px / 30px 34px 28px 32px;
}
/* hand-drawn top stripe */
.login-card::before{
  content:'';position:absolute;top:-1px;left:10%;right:10%;height:4px;
  background:linear-gradient(90deg,var(--p2),var(--b2),var(--y2),var(--g2));
  border-radius:2px;
}
.login-paw{font-size:3rem;animation:wiggle 2.5s ease-in-out infinite;display:block;margin-bottom:6px;}
@keyframes wiggle{0%,100%{transform:rotate(-5deg);}50%{transform:rotate(5deg);}}
.login-brand{
  font-family:var(--font-d);font-size:2rem;font-weight:900;
  color:var(--p3);letter-spacing:3px;text-shadow:2px 2px 0 rgba(255,143,171,.3);
}
.login-sub{font-size:.78rem;color:var(--soft);margin:4px 0 22px;line-height:1.6;}
.type-row{
  display:flex;gap:6px;background:var(--bg3);border-radius:14px;padding:4px;margin-bottom:18px;
  border:1.5px solid var(--p1);
}
.type-btn{
  flex:1;padding:9px 6px;border-radius:10px;border:none;cursor:pointer;
  font-size:.8rem;font-weight:800;color:var(--soft);background:transparent;
  transition:all .25s;font-family:var(--font-d);
}
.type-btn.on{
  background:linear-gradient(135deg,var(--p2),var(--b2));color:white;
  box-shadow:0 3px 10px rgba(255,143,171,.4);
}
.l-inp{
  width:100%;padding:12px 16px;margin-bottom:10px;
  background:var(--bg2);border:2px solid var(--p1);border-radius:14px 12px 15px 13px / 13px 15px 12px 14px;
  color:var(--text);font-size:.9rem;outline:none;transition:all .2s;
}
.l-inp:focus{border-color:var(--p2);box-shadow:0 0 0 3px rgba(255,143,171,.18);}
.l-btn{
  width:100%;padding:13px;border:none;border-radius:14px 12px 16px 13px / 13px 16px 12px 14px;
  background:linear-gradient(135deg,var(--p2) 0%,var(--b2) 100%);
  color:white;font-size:.95rem;font-weight:900;font-family:var(--font-d);
  cursor:pointer;box-shadow:0 5px 18px rgba(255,143,171,.4);transition:all .2s;
  letter-spacing:.5px;
}
.l-btn:active{transform:scale(.97);}
.l-err{color:var(--p3);font-size:.76rem;margin-top:8px;display:none;}
.l-hint{
  margin-top:14px;padding:10px 14px;background:rgba(184,228,255,.3);
  border:1.5px dashed var(--b2);border-radius:12px;font-size:.72rem;color:var(--mid);line-height:1.9;
}
.l-hint b{color:var(--b3);}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   HEADER
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.hdr{
  flex-shrink:0;z-index:50;
  background:rgba(255,248,252,.92);backdrop-filter:blur(16px);
  border-bottom:2.5px solid var(--p1);
  padding:10px 16px;
  display:flex;align-items:center;justify-content:space-between;
  position:relative;
}
/* rainbow bottom line */
.hdr::after{
  content:'';position:absolute;bottom:-2.5px;left:0;right:0;height:2.5px;
  background:linear-gradient(90deg,var(--p2),var(--y2),var(--g2),var(--b2),var(--lav2),var(--p2));
  background-size:200%;animation:rainbow 4s linear infinite;
}
@keyframes rainbow{to{background-position:200% 0;}}
.hdr-brand{
  font-family:var(--font-d);font-size:1.25rem;font-weight:900;
  color:var(--p3);letter-spacing:2px;display:flex;align-items:center;gap:6px;
}
.hdr-paw{font-size:1.3rem;animation:wiggle 3s infinite;}
.hdr-right{display:flex;align-items:center;gap:8px;}
.badge-user{
  padding:5px 12px;border-radius:20px;font-size:.72rem;font-weight:700;
  background:linear-gradient(135deg,rgba(255,183,197,.4),rgba(184,228,255,.4));
  border:1.5px solid var(--p1);color:var(--p3);max-width:140px;
  overflow:hidden;text-overflow:ellipsis;white-space:nowrap;
}
.hdr-logout{
  padding:6px 12px;border-radius:20px;border:1.5px solid var(--p1);
  background:transparent;color:var(--soft);font-size:.72rem;font-weight:700;cursor:pointer;transition:all .2s;
}
.hdr-logout:hover{background:var(--p1);color:white;}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   BOTTOM NAV
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.bnav{
  flex-shrink:0;display:flex;
  background:rgba(255,248,252,.95);backdrop-filter:blur(16px);
  border-top:2px solid var(--p1);
  padding:6px 0 max(6px,env(safe-area-inset-bottom));
}
.bn{
  flex:1;display:flex;flex-direction:column;align-items:center;justify-content:center;
  padding:6px 4px;border:none;background:transparent;cursor:pointer;transition:all .2s;
  position:relative;
}
.bn-ico{font-size:1.5rem;line-height:1;transition:transform .2s;}
.bn-lbl{font-size:.6rem;font-weight:800;font-family:var(--font-d);color:var(--soft);margin-top:2px;transition:color .2s;}
.bn.on .bn-ico{transform:scale(1.2);}
.bn.on .bn-lbl{color:var(--p2);}
.bn.on::after{
  content:'';position:absolute;top:0;left:50%;transform:translateX(-50%);
  width:28px;height:3px;border-radius:0 0 3px 3px;
  background:linear-gradient(90deg,var(--p2),var(--b2));
}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   SCROLL + PAGES
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.scroll{flex:1;overflow-y:auto;overflow-x:hidden;-webkit-overflow-scrolling:touch;position:relative;z-index:1;}
.page{display:none;padding:16px 14px 24px;}
.page.on{display:block;}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   SECTION DIVIDER (crayon hand-drawn look)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.sec-title{
  font-family:var(--font-d);font-size:1.05rem;font-weight:900;
  color:var(--text);margin:18px 0 12px;display:flex;align-items:center;gap:8px;
  position:relative;
}
.sec-title::after{
  content:'';flex:1;height:2.5px;
  background:linear-gradient(90deg,var(--p1),var(--b1),transparent);
  border-radius:2px;margin-left:4px;
}
.sec-label{
  background:linear-gradient(135deg,var(--p2),var(--p1));
  color:white;padding:3px 12px;border-radius:20px;font-size:.72rem;font-weight:800;
  box-shadow:0 2px 8px rgba(255,143,171,.3);
}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   CRAYON CARD BASE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.card{
  background:white;
  border:2px solid var(--p1);
  border-radius:20px 18px 22px 19px / 19px 22px 18px 21px;
  padding:16px;margin-bottom:14px;
  box-shadow:var(--shadow);
  position:relative;overflow:hidden;
}
.card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;
  background:linear-gradient(90deg,var(--p2),var(--b2));opacity:.7;}
.card-y{border-color:var(--y2);}
.card-y::before{background:linear-gradient(90deg,var(--y2),var(--g2));}
.card-b{border-color:var(--b2);}
.card-b::before{background:linear-gradient(90deg,var(--b2),var(--lav2));}
.card-g{border-color:var(--g2);}
.card-g::before{background:linear-gradient(90deg,var(--g2),var(--b2));}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   HERO BANNER (HOME)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.hero{
  background:linear-gradient(135deg,var(--p2) 0%,var(--b2) 60%,var(--lav2) 100%);
  border-radius:24px 20px 26px 22px / 22px 26px 20px 24px;
  padding:20px 18px 18px;margin-bottom:16px;
  position:relative;overflow:hidden;
  box-shadow:0 8px 28px rgba(255,143,171,.3);border:none;
}
.hero::before{content:'';position:absolute;inset:0;
  background-image:radial-gradient(circle at 80% 30%,rgba(255,255,255,.25) 0%,transparent 40%),
    radial-gradient(circle at 20% 80%,rgba(255,255,255,.15) 0%,transparent 35%);}
/* deco cats */
.hero-deco{position:absolute;right:12px;top:8px;font-size:2.5rem;opacity:.25;line-height:1;}
.hero-title{font-family:var(--font-d);font-size:1.5rem;font-weight:900;color:white;letter-spacing:2px;
  text-shadow:1px 2px 0 rgba(0,0,0,.1);position:relative;}
.hero-sub{font-size:.78rem;color:rgba(255,255,255,.9);line-height:1.7;margin:5px 0 14px;position:relative;}
.hero-nums{display:flex;gap:8px;position:relative;}
.hnum{
  flex:1;background:rgba(255,255,255,.28);backdrop-filter:blur(6px);
  border-radius:14px;padding:10px 6px;text-align:center;border:1.5px solid rgba(255,255,255,.4);
}
.hnum-n{font-family:var(--font-d);font-size:1.7rem;font-weight:900;color:white;line-height:1;}
.hnum-l{font-size:.62rem;color:rgba(255,255,255,.85);margin-top:2px;font-weight:700;}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   PROMO (保母宣傳)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.promo{
  background:linear-gradient(135deg,#FFF8E8,#EAF6FF);
  border:2.5px solid var(--y2);
  border-radius:22px 18px 24px 20px / 20px 24px 18px 22px;
  padding:16px;margin-bottom:14px;
  box-shadow:0 4px 16px rgba(255,202,106,.2);
  position:relative;overflow:hidden;
}
.promo::before{content:'';position:absolute;top:0;left:0;right:0;height:3.5px;
  background:linear-gradient(90deg,var(--y2),var(--b2),var(--g2));}
/* small house illustration */
.promo-deco{position:absolute;right:14px;bottom:12px;font-size:2.8rem;opacity:.18;}
.promo-tag{
  display:inline-flex;align-items:center;gap:5px;
  background:linear-gradient(135deg,var(--y2),var(--y1));color:var(--text);
  padding:4px 12px;border-radius:20px;font-size:.7rem;font-weight:800;
  margin-bottom:8px;box-shadow:0 2px 8px rgba(255,202,106,.3);
}
.promo-name{
  font-family:var(--font-d);font-size:1.1rem;font-weight:900;color:var(--text);margin-bottom:4px;
}
.promo-desc{font-size:.78rem;color:var(--mid);line-height:1.8;margin-bottom:10px;}
.svc-wrap{display:flex;flex-wrap:wrap;gap:5px;margin-bottom:10px;}
.svc-tag{
  padding:4px 10px;border-radius:20px;font-size:.7rem;font-weight:700;
  background:white;border:1.5px solid var(--b1);color:var(--b3);
}
.promo-line{
  display:inline-flex;align-items:center;gap:6px;
  background:white;border:1.5px solid var(--g2);border-radius:12px;
  padding:8px 14px;font-size:.78rem;color:var(--g3);font-weight:700;
}
.promo-line span{color:var(--mid);font-weight:400;}
/* LINE copy button */
.copy-line{
  padding:3px 8px;background:var(--g1);border:1px solid var(--g2);
  border-radius:8px;font-size:.65rem;color:var(--g3);cursor:pointer;
  font-weight:700;margin-left:4px;transition:all .15s;
}
.copy-line:active{transform:scale(.94);}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   SYNC STATUS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.sync-row{
  display:flex;align-items:center;gap:6px;padding:7px 12px;
  background:rgba(184,240,200,.35);border:1.5px solid var(--g2);
  border-radius:20px;font-size:.72rem;color:var(--g3);font-weight:700;
  margin-bottom:12px;
}
.sync-dot{width:7px;height:7px;border-radius:50%;background:var(--g3);flex-shrink:0;}
.sync-dot.spin{background:var(--y2);animation:pulse .8s infinite;}
@keyframes pulse{0%,100%{opacity:1;}50%{opacity:.2;}}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   SEARCH + FILTER
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.search-wrap{position:relative;margin-bottom:10px;}
.search-ico{position:absolute;left:12px;top:50%;transform:translateY(-50%);font-size:.95rem;pointer-events:none;}
.s-inp{
  width:100%;padding:10px 14px 10px 36px;
  background:white;border:2px solid var(--p1);
  border-radius:20px 18px 22px 19px / 19px 22px 18px 20px;
  color:var(--text);font-size:.85rem;outline:none;transition:all .2s;
}
.s-inp:focus{border-color:var(--p2);box-shadow:0 0 0 3px rgba(255,143,171,.12);}
.filter-row{display:flex;gap:6px;overflow-x:auto;padding-bottom:2px;margin-bottom:12px;}
.filter-row::-webkit-scrollbar{display:none;}
.fc{
  flex-shrink:0;padding:6px 14px;border-radius:20px;cursor:pointer;
  font-size:.72rem;font-weight:800;font-family:var(--font-d);
  background:white;border:2px solid var(--p1);color:var(--soft);transition:all .2s;
}
.fc.on{
  background:linear-gradient(135deg,var(--p2),var(--b2));border-color:transparent;
  color:white;box-shadow:0 3px 10px rgba(255,143,171,.3);
}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   CAT CARDS GRID
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.cats-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:10px;}
@media(min-width:480px){.cats-grid{grid-template-columns:repeat(3,1fr);}}
@media(min-width:700px){.cats-grid{grid-template-columns:repeat(4,1fr);}}

.cat-card{
  background:white;
  border:2px solid var(--p1);
  border-radius:18px 16px 20px 17px / 17px 20px 16px 18px;
  overflow:hidden;cursor:pointer;transition:all .22s;
  box-shadow:0 3px 12px rgba(255,143,171,.1);
  position:relative;
}
.cat-card:hover,.cat-card:active{transform:translateY(-3px) scale(1.01);
  box-shadow:0 8px 22px rgba(255,143,171,.25);border-color:var(--p2);}
.cat-photo{width:100%;height:130px;object-fit:cover;display:block;}
.cat-ph-ph{
  width:100%;height:130px;
  background:linear-gradient(135deg,var(--bg3),#FFF0FA);
  display:flex;align-items:center;justify-content:center;
  font-size:3rem;
}
.cat-body{padding:9px 10px 10px;}
.cat-name{font-family:var(--font-d);font-size:.95rem;font-weight:900;color:var(--p3);margin-bottom:2px;}
.cat-sub{font-size:.66rem;color:var(--soft);line-height:1.5;}
.cat-tags{display:flex;flex-wrap:wrap;gap:3px;margin-top:6px;}

/* status ribbons */
.ribbon{
  position:absolute;top:8px;right:-2px;
  font-size:.62rem;font-weight:800;padding:3px 10px 3px 8px;
  border-radius:3px 0 0 3px;color:white;
  box-shadow:1px 2px 6px rgba(0,0,0,.15);
}
.ribbon-adopted{background:linear-gradient(135deg,var(--g2),var(--g3));}
.ribbon-noadopt{background:linear-gradient(135deg,var(--lav2),var(--b3));}
.ribbon-rainbow{background:linear-gradient(135deg,#B8B8D0,#8888AA);}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   CUTE INFO TAGS / PILLS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.tag{
  display:inline-flex;align-items:center;gap:3px;
  padding:3px 9px;border-radius:20px;font-size:.65rem;font-weight:700;
  border:1.5px solid transparent;white-space:nowrap;
}
/* gender */
.tag-m{background:rgba(125,200,245,.2);color:var(--b3);border-color:var(--b2);}
.tag-f{background:rgba(255,143,171,.2);color:var(--p3);border-color:var(--p2);}
/* health */
.tag-ok{background:rgba(125,217,154,.2);color:var(--g3);border-color:var(--g2);}
.tag-warn{background:rgba(255,224,163,.3);color:#C07020;border-color:var(--y2);}
.tag-bad{background:rgba(224,80,112,.1);color:var(--p3);border-color:var(--p2);}
.tag-unk{background:rgba(176,138,154,.1);color:var(--soft);border-color:#DDD0D5;}
/* special */
.tag-neuter{background:rgba(232,213,255,.5);color:#7050A0;border-color:var(--lav2);}
.tag-vax{background:rgba(184,228,255,.4);color:var(--b3);border-color:var(--b1);}
.tag-status-wait{background:rgba(255,224,163,.4);color:#B06020;border-color:var(--y2);}
.tag-status-foster{background:rgba(184,228,255,.4);color:var(--b3);border-color:var(--b2);}
.tag-status-adopted{background:rgba(184,240,200,.5);color:var(--g3);border-color:var(--g2);}
.tag-status-perm{background:rgba(232,213,255,.5);color:#7050A0;border-color:var(--lav2);}
.tag-status-rainbow{background:rgba(184,184,208,.3);color:#6060A0;border-color:#C0C0D8;}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   ADOPTED HERO
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.adopted-hero{
  background:linear-gradient(135deg,rgba(184,240,200,.6),rgba(184,228,255,.6));
  border:2.5px solid var(--g2);
  border-radius:22px 20px 24px 21px / 20px 24px 21px 22px;
  padding:22px 18px;text-align:center;margin-bottom:16px;
  position:relative;overflow:hidden;
}
.ah-deco{position:absolute;opacity:.12;font-size:1.5rem;letter-spacing:8px;}
.ah-deco-t{top:6px;left:0;right:0;}
.ah-deco-b{bottom:4px;left:0;right:0;}
.ah-big{
  font-family:var(--font-d);font-size:4rem;font-weight:900;
  background:linear-gradient(135deg,var(--g3),var(--b3));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  line-height:1;
}
.ah-lbl{font-size:.85rem;font-weight:700;color:var(--g3);margin-top:4px;}
.ah-hearts{font-size:1.4rem;margin-top:8px;animation:heartbeat 2.5s ease-in-out infinite;}
@keyframes heartbeat{0%,100%{transform:scale(1);}50%{transform:scale(1.06);}}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   CAROUSEL
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.carousel-card{
  background:white;border:2px solid var(--b2);
  border-radius:22px;overflow:hidden;margin-bottom:16px;
  box-shadow:0 4px 18px rgba(125,200,245,.2);
}
.carousel-head{
  padding:12px 16px 8px;display:flex;align-items:center;justify-content:space-between;
}
.carousel-ttl{font-family:var(--font-d);font-size:.9rem;font-weight:900;color:var(--b3);}
.c-wrap{overflow:hidden;position:relative;}
.c-track{display:flex;transition:transform .5s cubic-bezier(.4,0,.2,1);}
.c-slide{flex-shrink:0;width:100%;position:relative;}
.c-img{width:100%;height:230px;object-fit:cover;display:block;cursor:zoom-in;}
.c-ph{width:100%;height:200px;background:linear-gradient(135deg,var(--bg3),#EAF6FF);
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  font-size:3rem;gap:6px;color:var(--soft);}
.c-cap{
  padding:10px 16px 4px;
  background:linear-gradient(0deg,rgba(255,255,255,1) 60%,rgba(255,255,255,0));
}
.c-cap-name{font-family:var(--font-d);font-size:.88rem;font-weight:900;color:var(--p3);}
.c-cap-txt{font-size:.72rem;color:var(--soft);margin-top:2px;}
.c-nav{display:flex;align-items:center;justify-content:center;gap:12px;padding:10px 0 14px;}
.c-btn{
  width:32px;height:32px;border-radius:50%;
  background:white;border:2px solid var(--p1);color:var(--p2);
  cursor:pointer;font-size:1rem;display:flex;align-items:center;justify-content:center;
  transition:all .2s;box-shadow:0 2px 8px rgba(255,143,171,.15);
}
.c-btn:hover{background:var(--p1);color:white;}
.c-dots{display:flex;gap:5px;}
.c-dot{width:7px;height:7px;border-radius:50%;background:var(--p1);cursor:pointer;transition:all .3s;}
.c-dot.on{background:var(--p2);width:20px;border-radius:4px;}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   MODAL
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.modal-bg{
  display:none;position:fixed;inset:0;background:rgba(61,43,53,.55);
  z-index:500;align-items:flex-end;justify-content:center;
}
.modal-bg.on{display:flex;}
@media(min-width:580px){.modal-bg{align-items:center;padding:20px;}}
.modal-box{
  background:var(--bg2);border:2.5px solid var(--p1);
  border-radius:28px 26px 0 0;
  width:100%;max-width:520px;max-height:90vh;overflow-y:auto;
  position:relative;
}
@media(min-width:580px){.modal-box{border-radius:28px 26px 30px 27px;}}
.modal-handle{width:38px;height:4px;background:var(--p1);border-radius:2px;margin:12px auto 14px;}
.m-photo{width:100%;height:200px;object-fit:cover;}
.m-ph{width:100%;height:160px;background:linear-gradient(135deg,var(--bg3),#EAF6FF);
  display:flex;align-items:center;justify-content:center;font-size:5rem;}
.m-body{padding:16px 18px 24px;}
.m-name{font-family:var(--font-d);font-size:1.55rem;font-weight:900;color:var(--p3);}
.m-no{font-size:.65rem;color:var(--soft);font-family:monospace;margin-bottom:10px;}
.m-tags{display:flex;flex-wrap:wrap;gap:5px;margin-bottom:14px;}
.m-info-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-bottom:12px;}
.mig{background:var(--bg3);border-radius:12px;padding:10px;}
.mig-l{font-size:.65rem;color:var(--soft);font-weight:700;margin-bottom:3px;}
.mig-v{font-size:.82rem;font-weight:700;color:var(--text);}
.m-health{
  background:linear-gradient(135deg,rgba(184,228,255,.2),rgba(184,240,200,.2));
  border:1.5px solid var(--b1);border-radius:14px;padding:12px;margin-bottom:12px;
}
.m-health-title{font-size:.72rem;font-weight:800;color:var(--b3);margin-bottom:6px;}
.m-health-row{display:flex;justify-content:space-between;align-items:flex-start;
  padding:5px 0;border-bottom:1px solid rgba(184,228,255,.3);font-size:.75rem;}
.m-health-row:last-child{border:none;}
.m-health-key{color:var(--soft);font-weight:600;flex-shrink:0;width:52px;}
.m-health-val{color:var(--text);text-align:right;line-height:1.5;flex:1;padding-left:8px;}
/* cred box (admin only) */
.cred-box{
  background:linear-gradient(135deg,rgba(184,228,255,.2),rgba(232,213,255,.2));
  border:1.5px dashed var(--b2);border-radius:14px;padding:12px;margin-bottom:10px;
}
.cred-title{font-size:.72rem;font-weight:800;color:var(--b3);margin-bottom:8px;}
.cred-row{display:flex;justify-content:space-between;align-items:center;
  padding:5px 0;border-bottom:1px solid rgba(184,228,255,.2);}
.cred-row:last-child{border:none;}
.cred-key{font-size:.72rem;color:var(--soft);}
.cred-val{font-family:monospace;font-size:.8rem;font-weight:700;color:var(--p3);}
.copy-sm{
  padding:2px 8px;background:var(--p1);border:none;border-radius:8px;
  color:white;font-size:.62rem;font-weight:700;cursor:pointer;margin-left:6px;transition:all .15s;
}
.copy-sm:active{transform:scale(.93);}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   SHARE / POSTS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.owner-banner{
  background:linear-gradient(135deg,rgba(255,183,197,.35),rgba(184,228,255,.35));
  border:2px solid var(--p1);border-radius:20px;padding:16px;
  text-align:center;margin-bottom:14px;
}
.ob-name{font-family:var(--font-d);font-size:1.1rem;font-weight:900;color:var(--p3);}
.ob-sub{font-size:.72rem;color:var(--soft);margin-top:3px;}

.post-form{
  background:white;border:2px solid var(--p1);
  border-radius:20px 18px 22px 19px;padding:14px;margin-bottom:14px;
}
.pf-title{font-family:var(--font-d);font-size:.88rem;font-weight:900;color:var(--p3);margin-bottom:10px;}
.post-txa{
  width:100%;padding:11px;background:var(--bg3);
  border:2px solid var(--p1);border-radius:14px;
  color:var(--text);font-size:.85rem;resize:none;outline:none;min-height:78px;
  transition:all .2s;
}
.post-txa:focus{border-color:var(--p2);box-shadow:0 0 0 3px rgba(255,143,171,.12);}
.upload-area{
  border:2.5px dashed var(--b2);border-radius:14px;
  padding:14px;text-align:center;margin:9px 0;cursor:pointer;
  transition:all .2s;position:relative;overflow:hidden;background:rgba(184,228,255,.08);
}
.upload-area:hover{border-color:var(--p2);background:rgba(255,143,171,.06);}
.upload-area input[type=file]{position:absolute;inset:0;opacity:0;cursor:pointer;width:100%;height:100%;}
.ua-ico{font-size:1.6rem;display:block;margin-bottom:4px;}
.ua-txt{font-size:.74rem;color:var(--soft);}
.previews{display:flex;flex-wrap:wrap;gap:6px;margin-top:7px;}
.prev-wrap{position:relative;display:inline-block;}
.prev-img{width:68px;height:68px;border-radius:10px;object-fit:cover;border:2px solid var(--p1);}
.prev-del{
  position:absolute;top:-5px;right:-5px;width:18px;height:18px;
  background:var(--p2);border-radius:50%;border:none;color:white;
  font-size:.6rem;cursor:pointer;display:flex;align-items:center;justify-content:center;
  box-shadow:0 2px 5px rgba(0,0,0,.15);
}
.post-btn{
  width:100%;padding:11px;border:none;border-radius:14px;
  background:linear-gradient(135deg,var(--p2),var(--b2));color:white;
  font-size:.9rem;font-weight:900;font-family:var(--font-d);
  cursor:pointer;box-shadow:0 4px 14px rgba(255,143,171,.3);transition:all .2s;
}
.post-btn:active{transform:scale(.97);}

.post-item{
  background:white;border:2px solid var(--p1);
  border-radius:18px 16px 20px 17px;padding:13px;margin-bottom:11px;
  box-shadow:0 2px 10px rgba(255,143,171,.08);
}
.pi-head{display:flex;align-items:center;gap:9px;margin-bottom:9px;}
.pi-ava{
  width:34px;height:34px;border-radius:50%;flex-shrink:0;
  background:linear-gradient(135deg,var(--p2),var(--b2));
  display:flex;align-items:center;justify-content:center;font-size:1rem;
}
.pi-name{font-family:var(--font-d);font-size:.82rem;font-weight:900;color:var(--p3);}
.pi-time{font-size:.64rem;color:var(--soft);}
.pi-text{font-size:.82rem;color:var(--text);line-height:1.8;margin-bottom:8px;}
.pi-photos{display:flex;flex-wrap:wrap;gap:6px;}
.pi-photo{width:95px;height:95px;object-fit:cover;border-radius:12px;cursor:zoom-in;
  border:2px solid var(--p1);transition:opacity .2s;}
.pi-photo:hover{opacity:.88;}
@media(max-width:380px){.pi-photo{width:78px;height:78px;}}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   ADMIN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.atabs{display:flex;gap:5px;overflow-x:auto;padding-bottom:2px;margin-bottom:14px;}
.atabs::-webkit-scrollbar{display:none;}
.atab{
  flex-shrink:0;padding:7px 14px;border-radius:20px;cursor:pointer;
  font-size:.72rem;font-weight:800;font-family:var(--font-d);
  background:white;border:2px solid var(--p1);color:var(--soft);transition:all .2s;
}
.atab.on{background:linear-gradient(135deg,var(--p2),var(--b2));border-color:transparent;color:white;
  box-shadow:0 3px 10px rgba(255,143,171,.3);}
.asec{display:none;}
.asec.on{display:block;}

/* admin stats */
.st-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:8px;margin-bottom:14px;}
@media(min-width:500px){.st-grid{grid-template-columns:repeat(4,1fr);}}
.st-card{
  background:white;border:2px solid var(--p1);border-radius:16px;padding:14px;text-align:center;
}
.st-num{font-family:var(--font-d);font-size:1.8rem;font-weight:900;
  background:linear-gradient(135deg,var(--p2),var(--b2));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;}
.st-lbl{font-size:.62rem;font-weight:800;color:var(--soft);margin-top:3px;}

/* admin table */
.tbl-wrap{overflow-x:auto;border-radius:16px;border:2px solid var(--p1);background:white;}
table{width:100%;border-collapse:collapse;font-size:.73rem;min-width:580px;}
th{background:linear-gradient(135deg,rgba(255,183,197,.3),rgba(184,228,255,.3));
  color:var(--mid);padding:10px 8px;text-align:left;
  border-bottom:2px solid var(--p1);white-space:nowrap;font-weight:800;}
td{padding:9px 8px;border-bottom:1px solid rgba(255,183,197,.3);vertical-align:middle;}
tr:last-child td{border-bottom:none;}
tr:hover td{background:rgba(255,183,197,.05);}
.tbl-name{font-weight:800;color:var(--p3);font-family:var(--font-d);}

/* form */
.form-card{
  background:linear-gradient(135deg,rgba(255,248,252,.9),rgba(240,250,255,.9));
  border:2px solid var(--p1);border-radius:20px;padding:16px;margin-bottom:14px;
}
.f-title{font-family:var(--font-d);font-size:.92rem;font-weight:900;color:var(--p3);margin-bottom:14px;}
.f-row{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
@media(max-width:400px){.f-row{grid-template-columns:1fr;}}
.f-grp{margin-bottom:10px;}
.f-lbl{font-size:.72rem;font-weight:800;color:var(--mid);margin-bottom:4px;display:block;}
.f-inp,.f-sel,.f-txa{
  width:100%;padding:10px 12px;
  background:white;border:2px solid var(--p1);
  border-radius:12px;color:var(--text);font-size:.85rem;outline:none;transition:all .2s;
}
.f-inp:focus,.f-sel:focus,.f-txa:focus{border-color:var(--p2);box-shadow:0 0 0 3px rgba(255,143,171,.12);}
.f-sel option{background:white;}
.f-txa{resize:vertical;min-height:72px;}

/* cred list */
.cred-card{
  background:white;border:2px solid var(--b1);border-radius:16px;padding:13px;margin-bottom:9px;
}
.cc-name{font-family:var(--font-d);font-size:.88rem;font-weight:900;color:var(--b3);margin-bottom:7px;}

/* button set */
.btn{
  padding:9px 18px;border-radius:12px;border:none;cursor:pointer;
  font-size:.8rem;font-weight:800;font-family:var(--font-d);transition:all .2s;
}
.btn-main{background:linear-gradient(135deg,var(--p2),var(--b2));color:white;
  box-shadow:0 3px 12px rgba(255,143,171,.3);}
.btn-main:active{transform:scale(.96);}
.btn-ghost{background:white;border:2px solid var(--p1);color:var(--soft);}
.btn-ghost:hover{border-color:var(--p2);color:var(--p2);}
.btn-g{background:rgba(125,217,154,.2);color:var(--g3);border:1.5px solid var(--g2);}
.btn-r{background:rgba(255,143,171,.12);color:var(--p3);border:1.5px solid var(--p2);}
.btn-y{background:rgba(255,224,163,.3);color:#B06020;border:1.5px solid var(--y2);}
.btn-sm{padding:5px 10px;font-size:.68rem;border-radius:8px;}

/* ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   TOAST + PHOTO VIEWER
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
.toast{
  position:fixed;bottom:80px;left:50%;transform:translateX(-50%) translateY(16px);opacity:0;
  background:white;border:2px solid var(--p1);border-radius:20px;
  padding:10px 22px;font-size:.8rem;font-weight:700;color:var(--text);
  z-index:9000;transition:all .28s;white-space:nowrap;
  box-shadow:0 6px 20px rgba(255,143,171,.25);
}
.toast.on{transform:translateX(-50%) translateY(0);opacity:1;}
.toast.ok{border-color:var(--g2);color:var(--g3);}
.toast.err{border-color:var(--p2);color:var(--p3);}

.pv-bg{display:none;position:fixed;inset:0;background:rgba(0,0,0,.88);z-index:9100;
  align-items:center;justify-content:center;}
.pv-bg.on{display:flex;}
.pv-img{max-width:96vw;max-height:90vh;object-fit:contain;border-radius:12px;}
.pv-x{position:absolute;top:14px;right:14px;width:38px;height:38px;border-radius:50%;
  background:rgba(255,255,255,.15);border:none;color:white;font-size:1.2rem;cursor:pointer;
  display:flex;align-items:center;justify-content:center;}

/* empty state */
.empty{text-align:center;padding:50px 20px;color:var(--soft);}
.empty-ico{font-size:3.5rem;margin-bottom:10px;opacity:.7;}
.empty-txt{font-size:.85rem;line-height:1.7;}
</style>
</head>
<body>

<!-- ══ TOAST ══ -->
<div class="toast" id="toast"></div>
<!-- ══ PHOTO VIEWER ══ -->
<div class="pv-bg" id="pvBg" onclick="closePV()">
  <button class="pv-x" onclick="closePV()">✕</button>
  <img class="pv-img" id="pvImg">
</div>

<!-- ════════════════════════════════════
     LOGIN
════════════════════════════════════ -->
<div class="screen on" id="sLogin">
  <!-- crayon SVG deco -->
  <svg style="position:absolute;top:0;left:0;width:100%;height:100%;pointer-events:none;opacity:.07" viewBox="0 0 400 700" fill="none">
    <circle cx="60" cy="80" r="40" fill="#FF8FAB" stroke="#FF8FAB" stroke-width="2"/>
    <circle cx="340" cy="200" r="28" fill="#7DC8F5" stroke="#7DC8F5" stroke-width="2"/>
    <circle cx="30" cy="600" r="22" fill="#FFE0A3" stroke="#FFE0A3" stroke-width="2"/>
    <circle cx="370" cy="550" r="35" fill="#7DD99A" stroke="#7DD99A" stroke-width="2"/>
    <path d="M80,300 Q120,260 160,300 Q200,340 240,300" stroke="#FFB7C5" stroke-width="6" fill="none" stroke-linecap="round"/>
    <path d="M200,500 Q240,470 280,500" stroke="#B8E4FF" stroke-width="5" fill="none" stroke-linecap="round"/>
  </svg>

  <div class="login-card">
    <span class="login-paw">🐾</span>
    <div class="login-brand">浪貓不浪</div>
    <div class="login-sub">我貓窩 · 每隻貓都值得被愛 🏠</div>

    <div class="type-row">
      <button class="type-btn on" id="lt-admin" onclick="setLT('admin')">🛡️ 管理員</button>
      <button class="type-btn" id="lt-owner" onclick="setLT('owner')">🐱 飼主登入</button>
    </div>

    <input class="l-inp" type="text" id="lU" placeholder="帳號" autocomplete="off" autocorrect="off" autocapitalize="none">
    <input class="l-inp" type="password" id="lP" placeholder="密碼" onkeydown="if(event.key==='Enter')doLogin()">
    <button class="l-btn" onclick="doLogin()">✨ 登入</button>
    <div class="l-err" id="lErr">帳號或密碼錯誤，請再試一次 🙈</div>

    <div class="l-hint" id="hint-admin">
      管理員：<b>app3811</b> / 密碼：<b>chch715715</b>
    </div>
    <div class="l-hint" id="hint-owner" style="display:none;">
      請使用貓咪專屬帳號密碼登入<br>
      <span style="font-size:.65rem;opacity:.75">帳號密碼由管理員提供給送養人</span>
    </div>
  </div>
</div>

<!-- ════════════════════════════════════
     MAIN APP
════════════════════════════════════ -->
<div class="screen" id="sApp">
  <!-- HEADER -->
  <div class="hdr">
    <div class="hdr-brand">
      <span class="hdr-paw">🐾</span>浪貓不浪
    </div>
    <div class="hdr-right">
      <div class="badge-user" id="userBadge">👤</div>
      <button class="hdr-logout" onclick="doLogout()">登出</button>
    </div>
  </div>

  <!-- SCROLL AREA -->
  <div class="scroll">

    <!-- ── 首頁 ── -->
    <div class="page on" id="p-home">
      <!-- hero -->
      <div class="hero">
        <div class="hero-deco">🐱🐾🐱</div>
        <div class="hero-title">🐱 浪貓不浪</div>
        <div class="hero-sub">我貓窩中途之家 · 讓每隻貓找到屬於牠的溫暖家 🏡</div>
        <div class="hero-nums">
          <div class="hnum"><div class="hnum-n" id="hn-wait">0</div><div class="hnum-l">🏠 等家中</div></div>
          <div class="hnum"><div class="hnum-n" id="hn-adopt">0</div><div class="hnum-l">💚 已送養</div></div>
          <div class="hnum"><div class="hnum-n" id="hn-total">0</div><div class="hnum-l">🐾 總數</div></div>
        </div>
      </div>

      <!-- 保母宣傳 -->
      <div class="promo">
        <div class="promo-deco">🏠</div>
        <div class="promo-tag">🐾 我貓窩服務</div>
        <div class="promo-name">貓窩裏到府保母</div>
        <div class="promo-desc">
          主人出門不在家，讓我們來守護您的毛孩！<br>
          🏠 在熟悉的家裡接受照顧，不用承受外出壓力。<br>
          每次服務都提供照片回報，讓您在外放心出遊 💕
        </div>
        <div class="svc-wrap">
          <div class="svc-tag">🍲 餵食服務</div>
          <div class="svc-tag">🧹 清貓砂</div>
          <div class="svc-tag">💊 餵藥協助</div>
          <div class="svc-tag">🎮 互動陪玩</div>
          <div class="svc-tag">📸 照片回報</div>
          <div class="svc-tag">💉 就醫陪同</div>
          <div class="svc-tag">🚿 洗澡梳毛</div>
          <div class="svc-tag">👴 老幼照護</div>
        </div>
        <div style="display:flex;align-items:center;gap:6px;flex-wrap:wrap;">
          <div class="promo-line">
            📍 <span>服務區域：</span>高雄市
          </div>
          <div class="promo-line" style="border-color:var(--b2);">
            💬 LINE官方：<b style="color:var(--b3);">@099nuhen</b>
            <button class="copy-line" onclick="copyTxt('@099nuhen')">複製</button>
          </div>
        </div>
      </div>

      <!-- 最新等家 -->
      <div class="sec-title">🏠 最新等家的貓咪 <span class="sec-label">找新家中</span></div>
      <div class="cats-grid" id="home-grid"></div>
      <button class="btn btn-ghost" style="width:100%;margin-top:10px;" onclick="goPage('waiting')">看全部等家貓咪 →</button>
    </div>

    <!-- ── 等家貓咪 ── -->
    <div class="page" id="p-waiting">
      <div class="sync-row">
        <div class="sync-dot" id="syncDot"></div>
        <span id="syncSt">資料已同步</span>
        <button style="margin-left:auto;padding:3px 10px;border-radius:12px;background:var(--g1);border:1px solid var(--g2);color:var(--g3);font-size:.68rem;font-weight:700;cursor:pointer;" onclick="doSync()">🔄 更新</button>
      </div>
      <div class="search-wrap">
        <span class="search-ico">🔍</span>
        <input class="s-inp" type="text" placeholder="搜尋貓咪名字或花色..." id="searchInp" oninput="filterWaiting()">
      </div>
      <div class="filter-row">
        <div class="fc on" onclick="setF('all',this)">🐾 全部</div>
        <div class="fc" onclick="setF('male',this)">🔵 公貓</div>
        <div class="fc" onclick="setF('female',this)">🩷 母貓</div>
        <div class="fc" onclick="setF('neutered',this)">✂️ 已結紮</div>
        <div class="fc" onclick="setF('vaccinated',this)">💉 已打疫苗</div>
        <div class="fc" onclick="setF('hiv_neg',this)">❤️ 愛滋陰性</div>
      </div>
      <div class="cats-grid" id="waiting-grid"></div>
    </div>

    <!-- ── 已找到家 ── -->
    <div class="page" id="p-adopted">
      <!-- counter -->
      <div class="adopted-hero">
        <div class="ah-deco ah-deco-t">💚 🐾 💚 🐾 💚 🐾 💚</div>
        <div class="ah-big" id="adopt-count">0</div>
        <div class="ah-lbl">隻貓咪已成功搬離，找到幸福的家 🏡</div>
        <div class="ah-hearts">💚 🐾 💚 🐾 💚</div>
        <div class="ah-deco ah-deco-b">🐾 🌈 🐾 🌈 🐾 🌈</div>
      </div>

      <!-- carousel -->
      <div class="carousel-card" id="carouselCard">
        <div class="carousel-head">
          <div class="carousel-ttl">📸 幸福日常輪播</div>
          <div style="font-size:.68rem;color:var(--soft);">已送養貓咪的近況</div>
        </div>
        <div class="c-wrap">
          <div class="c-track" id="cTrack"></div>
        </div>
        <div class="c-nav">
          <button class="c-btn" onclick="cPrev()">‹</button>
          <div class="c-dots" id="cDots"></div>
          <button class="c-btn" onclick="cNext()">›</button>
        </div>
      </div>

      <div class="sec-title">💚 所有已搬離的貓咪 <span class="sec-label" style="background:linear-gradient(135deg,var(--g2),var(--g3));">已找到家</span></div>
      <div class="cats-grid" id="adopted-grid"></div>
    </div>

    <!-- ── 近況分享 ── -->
    <div class="page" id="p-share">
      <div class="owner-banner" id="owner-banner">
        <div style="font-size:2rem;margin-bottom:6px;">📸</div>
        <div class="ob-name" id="ob-name">近況分享牆</div>
        <div class="ob-sub" id="ob-sub">飼主們分享毛孩的幸福日常 💕</div>
      </div>

      <!-- upload form (owner only) -->
      <div class="post-form" id="post-form" style="display:none;">
        <div class="pf-title">✏️ 分享今日日常</div>
        <textarea class="post-txa" id="postTxa" placeholder="說說貓咪今天做了什麼可愛的事吧 🐾"></textarea>
        <div class="upload-area" id="uploadArea">
          <input type="file" id="fileInp" accept="image/*,video/*" multiple capture="environment" onchange="onFile(event)">
          <span class="ua-ico">📷</span>
          <div class="ua-txt" id="uaTxt">點擊上傳照片 / 影片，或直接拍照<br><span style="font-size:.62rem;">支援 JPG·PNG·GIF·MP4，手機直接拍照也可以 📱</span></div>
          <div class="previews" id="previews"></div>
        </div>
        <button class="post-btn" onclick="submitPost()">🐾 發布分享</button>
      </div>

      <div id="postsList">
        <div class="empty"><div class="empty-ico">📸</div><div class="empty-txt">還沒有分享<br>快來第一個！</div></div>
      </div>
    </div>

    <!-- ── 管理後台 ── -->
    <div class="page" id="p-admin">
      <div class="atabs">
        <div class="atab on" onclick="switchAT('overview',this)">📊 總覽</div>
        <div class="atab" onclick="switchAT('cats',this)">🐱 貓咪管理</div>
        <div class="atab" onclick="switchAT('health',this)">🏥 健康紀錄</div>
        <div class="atab" onclick="switchAT('adoption',this)">💚 送養資料</div>
        <div class="atab" onclick="switchAT('creds',this)">🔑 飼主帳號</div>
        <div class="atab" onclick="switchAT('posts-admin',this)">📸 貼文</div>
        <div class="atab" onclick="switchAT('sync',this)">🔄 同步</div>
      </div>

      <!-- 總覽 -->
      <div class="asec on" id="at-overview">
        <div class="st-grid">
          <div class="st-card"><div class="st-num" id="st-w">0</div><div class="st-lbl">🏠 等家中</div></div>
          <div class="st-card"><div class="st-num" id="st-a">0</div><div class="st-lbl">💚 已送養</div></div>
          <div class="st-card"><div class="st-num" id="st-p">0</div><div class="st-lbl">📸 分享貼文</div></div>
          <div class="st-card"><div class="st-num" id="st-o">0</div><div class="st-lbl">👥 飼主帳號</div></div>
        </div>
        <div class="card">
          <div style="font-family:var(--font-d);font-size:.88rem;font-weight:900;color:var(--p3);margin-bottom:12px;">⚡ 快速操作</div>
          <div style="display:flex;gap:8px;flex-wrap:wrap;">
            <button class="btn btn-main btn-sm" onclick="switchAT('cats',document.querySelectorAll('.atab')[1])">+ 新增貓咪</button>
            <button class="btn btn-ghost btn-sm" onclick="doSync()">🔄 同步試算表</button>
            <button class="btn btn-ghost btn-sm" onclick="exportCreds()">📥 匯出帳號</button>
            <button class="btn btn-y btn-sm" onclick="exportAll()">📊 匯出全部資料</button>
          </div>
        </div>
      </div>

      <!-- 貓咪管理 -->
      <div class="asec" id="at-cats">
        <div class="form-card">
          <div class="f-title" id="fTitle">➕ 新增貓咪</div>
          <input type="hidden" id="editId">
          <div class="f-row">
            <div class="f-grp"><label class="f-lbl">🐱 名字 *</label><input class="f-inp" id="fn" placeholder="貓咪名字"></div>
            <div class="f-grp"><label class="f-lbl">🔢 編號</label><input class="f-inp" id="fno" placeholder="如 2024100901"></div>
          </div>
          <div class="f-row">
            <div class="f-grp"><label class="f-lbl">♀♂ 性別</label>
              <select class="f-sel" id="fg"><option value="">請選擇</option><option value="female">♀ 母貓</option><option value="male">♂ 公貓</option></select></div>
            <div class="f-grp"><label class="f-lbl">🎨 花色</label><input class="f-inp" id="fc" placeholder="如三花/橘白"></div>
          </div>
          <div class="f-row">
            <div class="f-grp"><label class="f-lbl">🎂 年紀</label><input class="f-inp" id="fa" placeholder="如 2024/08 出生"></div>
            <div class="f-grp"><label class="f-lbl">⚖️ 體重</label><input class="f-inp" id="fw" placeholder="如 2.5kg"></div>
          </div>
          <div class="f-row">
            <div class="f-grp"><label class="f-lbl">📋 狀態 *</label>
              <select class="f-sel" id="fst">
                <option value="waiting">🏠 等家中</option>
                <option value="foster">🏡 中途中</option>
                <option value="perm">💜 永久中途</option>
                <option value="adopted">💚 已送養搬離</option>
                <option value="rainbow">🌈 彩虹橋</option>
              </select></div>
            <div class="f-grp"><label class="f-lbl">✂️ 結紮</label>
              <select class="f-sel" id="fneu">
                <option value="">未知</option>
                <option value="yes">✔️ 已結紮</option>
                <option value="no">✖️ 未結紮</option>
              </select></div>
          </div>
          <div class="f-row">
            <div class="f-grp"><label class="f-lbl">🧪 愛滋</label>
              <select class="f-sel" id="fhiv"><option value="➖">➖ 陰性</option><option value="➕">➕ 陽性</option><option value="？">？ 未知</option></select></div>
            <div class="f-grp"><label class="f-lbl">🧬 白血病</label>
              <select class="f-sel" id="ffelv"><option value="➖">➖ 陰性</option><option value="➕">➕ 陽性</option><option value="？">？ 未知</option></select></div>
          </div>
          <div class="f-grp"><label class="f-lbl">💉 疫苗紀錄</label><textarea class="f-txa" id="fvac" placeholder="施打日期與種類"></textarea></div>
          <div class="f-grp"><label class="f-lbl">🐛 驅蟲紀錄</label><textarea class="f-txa" id="fdew" placeholder="驅蟲紀錄"></textarea></div>
          <div class="f-grp"><label class="f-lbl">🖼️ 照片網址</label><input class="f-inp" id="fpho" placeholder="https://... 或 Google Drive 連結"></div>
          <div class="f-grp"><label class="f-lbl">📝 備注</label><textarea class="f-txa" id="fnotes" placeholder="個性描述或特殊注意事項"></textarea></div>
          <div style="display:flex;gap:8px;">
            <button class="btn btn-ghost btn-sm" onclick="resetForm()">取消</button>
            <button class="btn btn-main" onclick="saveCat()">💾 儲存</button>
          </div>
        </div>

        <div class="tbl-wrap">
          <table><thead><tr>
            <th>名字</th><th>性別</th><th>花色</th><th>狀態</th><th>結紮</th><th>疫苗</th><th>操作</th>
          </tr></thead><tbody id="catTbody"></tbody></table>
        </div>
      </div>

      <!-- 健康紀錄 -->
      <div class="asec" id="at-health">
        <div style="font-family:var(--font-d);font-size:.88rem;font-weight:900;color:var(--b3);margin-bottom:12px;">🏥 所有貓咪健康紀錄</div>
        <div class="tbl-wrap">
          <table><thead><tr>
            <th>名字</th><th>疫苗</th><th>驅蟲</th><th>結紮</th><th>體重</th><th>愛滋</th><th>白血病</th>
          </tr></thead><tbody id="healthTbody"></tbody></table>
        </div>
      </div>

      <!-- 送養資料 -->
      <div class="asec" id="at-adoption">
        <div style="font-family:var(--font-d);font-size:.88rem;font-weight:900;color:var(--g3);margin-bottom:12px;">💚 送養搬離紀錄</div>
        <div class="tbl-wrap">
          <table><thead><tr>
            <th>貓名</th><th>送養日期</th><th>搬離日期</th><th>SNS</th>
          </tr></thead><tbody id="adoptTbody"></tbody></table>
        </div>
      </div>

      <!-- 飼主帳號 -->
      <div class="asec" id="at-creds">
        <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px;flex-wrap:wrap;gap:8px;">
          <div style="font-family:var(--font-d);font-size:.88rem;font-weight:900;color:var(--b3);">🔑 飼主帳號一覽</div>
          <button class="btn btn-ghost btn-sm" onclick="exportCreds()">📥 匯出全部</button>
        </div>
        <div id="credsList"></div>
      </div>

      <!-- 貼文管理 -->
      <div class="asec" id="at-posts-admin">
        <div style="font-family:var(--font-d);font-size:.88rem;font-weight:900;color:var(--p3);margin-bottom:12px;">📸 所有分享貼文</div>
        <div id="adminPostsList"></div>
      </div>

      <!-- 資料同步 -->
      <div class="asec" id="at-sync">
        <div class="card card-b">
          <div style="font-family:var(--font-d);font-size:.9rem;font-weight:900;color:var(--b3);margin-bottom:10px;">🔄 Google Sheets 同步設定</div>
          <div style="font-size:.76rem;color:var(--mid);line-height:1.9;margin-bottom:12px;">
            試算表更新後點下方按鈕即可同步。<br>
            試算表需設為「<b style="color:var(--b3)">知道連結的人可以檢視</b>」。<br>
            系統會讀取「貓咪們」和「已搬離」兩個分頁。
          </div>
          <div class="f-grp"><label class="f-lbl">試算表 ID</label>
            <input class="f-inp" id="sheetId" value="1TW2VudIow-Vzr5uz5nToFTQfxCCMyUVqi48pYmBw8fs"></div>
          <button class="btn btn-main" onclick="doSync()">🔄 立即同步兩個分頁</button>
          <div id="syncResult" style="margin-top:10px;font-size:.76rem;"></div>
        </div>
        <div class="card">
          <div style="font-family:var(--font-d);font-size:.85rem;font-weight:900;color:var(--p3);margin-bottom:8px;">📋 試算表欄位對應（貓咪們 分頁）</div>
          <div style="font-size:.7rem;color:var(--mid);line-height:2.1;">
            A:貓名 ／ B:日期 ／ C:編號 ／ D:搬離日期<br>
            E:疫苗 ／ F:驅蟲 ／ G:結紮 ／ H:性別 ／ I:花色<br>
            J:愛滋 ／ K:白血病 ／ L:年紀 ／ M:體重<br>
            Q:送養日期 ／ R:領養人名 ／ T:SNS帳號
          </div>
        </div>
      </div>
    </div>

  </div><!-- /scroll -->

  <!-- BOTTOM NAV -->
  <div class="bnav">
    <button class="bn on" id="bn-home" onclick="goPage('home')">
      <span class="bn-ico">🏠</span><span class="bn-lbl">首頁</span>
    </button>
    <button class="bn" id="bn-waiting" onclick="goPage('waiting')">
      <span class="bn-ico">🐱</span><span class="bn-lbl">等家</span>
    </button>
    <button class="bn" id="bn-adopted" onclick="goPage('adopted')">
      <span class="bn-ico">💚</span><span class="bn-lbl">找到家</span>
    </button>
    <button class="bn" id="bn-share" onclick="goPage('share')">
      <span class="bn-ico">📸</span><span class="bn-lbl">分享</span>
    </button>
    <button class="bn" id="bn-admin" onclick="goPage('admin')" style="display:none;">
      <span class="bn-ico">⚙️</span><span class="bn-lbl">管理</span>
    </button>
  </div>
</div>

<!-- CAT DETAIL MODAL -->
<div class="modal-bg" id="catModal">
  <div class="modal-box">
    <div class="modal-handle"></div>
    <div id="modalContent"></div>
  </div>
</div>

<script>
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// STATE
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
const S={user:null,role:null,ownerCatId:null,loginType:'admin',
  cats:[],uploads:[],filter:'all',search:'',
  cIdx:0,cItems:[],cTimer:null};
const ADMIN={u:'app3811',p:'chch715715'};
const SHEET_ID='1TW2VudIow-Vzr5uz5nToFTQfxCCMyUVqi48pYmBw8fs';

const gc=()=>JSON.parse(localStorage.getItem('wc_cats')||'[]');
const sc=v=>localStorage.setItem('wc_cats',JSON.stringify(v));
const gp=()=>JSON.parse(localStorage.getItem('wc_posts')||'[]');
const sp=v=>localStorage.setItem('wc_posts',JSON.stringify(v));
const gcr=()=>JSON.parse(localStorage.getItem('wc_creds')||'{}');
const scr=v=>localStorage.setItem('wc_creds',JSON.stringify(v));

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// PASSWORD GENERATOR
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function genPass(){
  const a='abcdefghjkmnpqrstuvwxyz';const n='23456789';const s='@#$!';
  let p='';
  for(let i=0;i<3;i++)p+=a[~~(Math.random()*a.length)];
  p+=n[~~(Math.random()*n.length)]+n[~~(Math.random()*n.length)];
  p+=s[~~(Math.random()*s.length)];
  for(let i=0;i<2;i++)p+=a[~~(Math.random()*a.length)];
  return p.split('').sort(()=>Math.random()-.5).join('');
}
function genUser(name){
  const map={花:'hua',貓:'mao',小:'xiao',大:'da',黑:'hei',白:'bai',橘:'ju',咪:'mi',奶:'nai',虎:'hu',月:'yue',陽:'yang',寶:'bao',采:'cai',暖:'nuan',春:'chun',夏:'xia',秋:'qiu',冬:'dong',七:'qi',米:'mi',可:'ke',太:'tai',乖:'gui',捲:'juan',莫:'mo',品:'pin',芬:'fen',佳:'jia',亮:'liang',甜:'tian',酸:'suan'};
  let p='';for(const c of name)if(map[c]){p=map[c];break;}
  if(!p)p='cat'+Math.random().toString(36).substr(2,3);
  return p+(100+~~(Math.random()*8900));
}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// SEED DATA (from spreadsheet)
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// Status logic: 搬離日期 有值且不含X = adopted; 含X = rainbow; 否則看原始標記
const RAW=[
  {name:'小梓',no:'2024100901',gender:'female',color:'全黑/米克斯',age:'2024/08',weight:'2.25kg',vaccine:'10/XX/2024 4-in-1, 11/12, 12/16/2024, 1/26/2025',deworm:'2025/02/18, 0614, 921',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'賓賓',no:'2024100902',gender:'male',color:'黑白賓士/米克斯',age:'2024/08',weight:'2.35kg',vaccine:'12/06 3-in-1, 02/03/25, 03/07/2025',deworm:'2025/02/03, 614, 0921',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'太陽',no:'2024100905',gender:'male',color:'橘虎斑/米克斯',vaccine:'10/XX/2024 3-in-1, 0520 五合一',deworm:'2025/03/05, 2025/05/26',neuter:'yes',hiv:'➖',felv:'➖',status:'adopted',adopterSns:'臉書張曉潔'},
  {name:'徒手抓',no:'2024101201',gender:'female',color:'白底虎斑/米克斯',age:'~2023/06',vaccine:'1224/2025',deworm:'614, 0921',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'阿諾',no:'2024101303',gender:'female',color:'白底虎斑/米克斯',vaccine:'10/11/2024',deworm:'614',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'小不點',no:'2024101304',gender:'female',color:'白底虎斑/米克斯',vaccine:'10/11/2024',deworm:'614',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'膽小',no:'2024101305',gender:'female',color:'棕黑虎斑/米克斯',age:'~2024/06',weight:'2.5kg',vaccine:'11/12, 12/28/2024, 02/03/25 五合一',deworm:'2025/02/03',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'勇氣',no:'2024101307',gender:'female',color:'棕黑虎斑/米克斯',age:'~2024/06',weight:'2.5kg',vaccine:'11/18/2024 4-in-1, 02/04/25, 03/05/25',deworm:'2025/02/04, 2025/03/05',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'希望',no:'2024101308',gender:'male',color:'棕黑虎斑/米克斯',age:'~2024/06',weight:'2.7kg',vaccine:'11/18, 12/26/2024, 02/17/2025',deworm:'2025/02/04',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'黑黑',no:'2024101801',gender:'female',color:'全黑/米克斯',age:'2023',weight:'2.5kg',vaccine:'20251117, 1224/2025',deworm:'2025/06/14',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'炭寶',no:'2024110601',gender:'male',color:'全黑/米克斯',weight:'3.9kg',vaccine:'11/06/2024 3-in-1, 0429 五合一',deworm:'2025/02/18, 0429, 0529',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'奔馳',no:'2024110802',gender:'male',color:'黑白賓士/米克斯',age:'2024/10',weight:'2.4kg',vaccine:'11/26, 12/25/2024, 02/03/25 五合一',deworm:'2025/02/03, 0426',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'小乳牛',no:'2024111002',gender:'female',color:'黑白乳牛/米克斯',age:'~2023',weight:'3.2kg',vaccine:'08/21/2024 4-in-1, 11/08 五合一',deworm:'全能貓S, 2025/06/25',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'媽寶',no:'2024111003',gender:'female',color:'棕黑虎斑/米克斯',age:'2024/03',weight:'3kg',vaccine:'08/08, 11/07/2024 4-in-1, 03/11/2025, 0408',deworm:'全能貓S 2025/02/19',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'莫愁',no:'2024111004',gender:'female',color:'玳瑁/米克斯',age:'2024/03',weight:'1.95kg',vaccine:'08/30/2024 3-in-1, 03/11/2025, 0408',deworm:'全能貓S 11/10',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'咪咪',no:'2024111006',gender:'female',color:'橘虎斑/米克斯',age:'~2020',weight:'3.9kg',vaccine:'10/10/2024 5-in-1, 11082025',deworm:'全能貓S 2025/02/19',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'二虎',no:'2024111007',gender:'female',color:'棕黑橘虎斑/混美短',age:'2024/05',weight:'2.1kg',vaccine:'08/08, 11/07/2024, 03/06/2025, 04/04',deworm:'全能貓S 2025/02/19',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'萌萌',no:'2024111101',gender:'female',color:'白底三花/米克斯',age:'2024/10',weight:'0.65kg',vaccine:'12/11/2024 4-in-1, 20251223',deworm:'20251223',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'寶拉',no:'2024111801',gender:'female',color:'棕黑虎斑/米克斯',weight:'2.8kg',vaccine:'12/31/2024 4-in-1',deworm:'全能貓S 2025/02/18',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'貝拉',no:'2024111802',gender:'female',color:'白底虎斑/米克斯',weight:'2.65kg',vaccine:'12/31/2024 4-in-1, 0505 五合一',deworm:'全能貓S, 0505',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'米洛',no:'2024111803',gender:'male',color:'米克斯',age:'2024/07',weight:'2.5kg',vaccine:'12/31/2024 4-in-1, 02/04/25, 03/05/25',deworm:'全能貓S 2025/02/04',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'米可',no:'2024111804',gender:'female',color:'白底虎斑/米克斯',age:'2024/07',weight:'1.8kg',vaccine:'12/31/2024 4-in-1, 02/03/25, 03/15/25',deworm:'全能貓S 2025/02/03',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'米奇',no:'2024111806',gender:'male',color:'棕黑虎斑/米克斯',age:'2024/07',weight:'2.5kg',vaccine:'12/25/2024 4-in-1, 02/04/25, 03/05/25',deworm:'全能貓S 2025/02/04',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'采采',no:'2024112201',gender:'female',color:'棕黑虎斑/米克斯',weight:'2.7kg',vaccine:'12/11/2024, 02/03/25, 03/06/25',deworm:'全能貓S 2025/02/03',neuter:'yes',hiv:'➖',felv:'➖',status:'adopted',adoptDate:'2025/01/15'},
  {name:'小美',no:'2024112202',gender:'female',color:'黑白乳牛/米克斯',age:'2024/08',weight:'2.05kg',vaccine:'12/25/2024, 02/03/25, 03/06/2025',deworm:'全能貓S 2025/02/03',neuter:'yes',hiv:'➖',felv:'➖',status:'adopted',adoptDate:'2025/03/06'},
  {name:'妙妙',no:'2024112302',gender:'female',color:'黑白乳牛/米克斯',age:'2024/03',vaccine:'0505 五合一',deworm:'0505 全能貓',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'七月',no:'2024120901',gender:'female',color:'棕黑虎斑/美短混摺耳',age:'2016',weight:'2.4kg',vaccine:'02/03/25, 0505 五合一',deworm:'全能貓S 2025/02/03',neuter:'no',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'乖乖',no:'2024121001',gender:'male',color:'白底虎斑/米克斯',weight:'2kg',vaccine:'12/09/2024 三合一, 01/25/2025, 03/10/2025',deworm:'1224',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'可樂',no:'2024123001',gender:'female',color:'虎斑',age:'2024/11',weight:'1.4kg',vaccine:'01/20/2025 5-in-1, 02/15, 03/15',deworm:'全能貓S 2025/02/15',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'麻吉',no:'2024123003',gender:'male',color:'橘貓',age:'2024/11',weight:'1.5kg',vaccine:'01/20/2025 5-in-1, 02/15, 03/15',deworm:'全能貓S 2025/02/15',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'奶昔',no:'2024123004',gender:'female',color:'三花虎斑/米克斯',age:'2023',vaccine:'2025/01/05',deworm:'全能貓S 2025/2/19',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'尤拿',no:'2025010301',gender:'male',color:'橘虎斑/米克斯',age:'2022',vaccine:'01/03/2025 3-in-1',deworm:'全能貓S 626',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'暖暖',no:'2025010401',gender:'female',color:'黑白橘/米克斯',age:'2023',vaccine:'02/2025 三合一, 0429 五合一',deworm:'全能貓S 2025/01/04',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'捲捲',no:'2025012001',gender:'male',color:'白底虎斑/米克斯',age:'2024/10',vaccine:'610 五合一',deworm:'627',neuter:'yes',status:'adopted',adoptDate:'2025/01/26'},
  {name:'索隆',no:'2025012205',gender:'male',color:'黑白賓士/米克斯',vaccine:'0408, 0709 五合一',deworm:'全能貓S 2025/02/10',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'初一',no:'2025012901',gender:'female',color:'三花虎斑/米克斯',age:'2024/11',weight:'1.4kg',vaccine:'02/04/2025 五合一, 03/06/25, 04/04',deworm:'全能貓S 2025/02/04',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'大可愛',no:'2025021001',gender:'female',color:'白底虎斑/米克斯',age:'~2021/02',weight:'3.95kg',vaccine:'02/17/2025 四合一, 0426 五合一',deworm:'全能貓S 2025/02/15',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'美生',no:'2025021101',gender:'male',color:'玳瑁/米克斯',age:'2024/02',vaccine:'2/1/2025, 03/18 五合一, 0425',deworm:'全能貓S 2025/02/11',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'土桑',no:'2025022101',gender:'male',color:'白底橘/米克斯',age:'~2024/08',vaccine:'03/05/2025 三合一, 0404, 0502 五合一',deworm:'全能貓S 2025/02/21',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'露露',no:'2025022701',gender:'female',color:'三花虎斑/米克斯',vaccine:'04/03/2025 五合一, 0429',deworm:'全能貓S 2025/03/01',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'廣志',no:'2025031201',gender:'male',color:'虎斑/米克斯',age:'2024/10',vaccine:'3/1/2025, 04/09, 0505 五合一',deworm:'全能貓 2025/03/27',hiv:'？',felv:'？',status:'waiting'},
  {name:'波妞',no:'2025032102',gender:'female',color:'乳牛/米克斯',age:'2024/10',vaccine:'3/1/2025, 0426, 0523 五合一',deworm:'全能貓 2025/03/27',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'虎二',no:'2025032701',gender:'male',color:'棕黑虎斑/米克斯',age:'2022/04',vaccine:'0410, 0516 五合一',deworm:'410, 0514',neuter:'yes',hiv:'➕',felv:'➖',status:'waiting',notes:'⚠️ 愛滋陽性，需特別注意'},
  {name:'尤佳',no:'2025032901',gender:'female',color:'棕黑虎斑/米克斯',age:'2022/04',vaccine:'04/09, 05/24 五合一',deworm:'0524 全能貓S',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'莫單',no:'2025050101',gender:'female',color:'全黑/米克斯',age:'2025/01',vaccine:'501 三合一, 526 五合一',deworm:'501, 0526',neuter:'yes',hiv:'？',felv:'？',status:'waiting'},
  {name:'品客',no:'2025053001',gender:'female',color:'黑白乳牛/米克斯',age:'2024',vaccine:'610, 0708',deworm:'530, 0708',neuter:'yes',status:'waiting'},
  {name:'芬達',no:'2025053002',gender:'male',color:'橘白虎斑/米克斯',age:'2024',vaccine:'610, 0708',deworm:'530, 0708',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'佳人',no:'2025060701',gender:'female',color:'玳瑁/米克斯',age:'2024/12',vaccine:'610, 0708',deworm:'607, 630',neuter:'yes',status:'waiting'},
  {name:'亮亮',no:'2025061002',gender:'male',color:'橘虎斑/米克斯',age:'2025/04',vaccine:'612, 708, 0820',deworm:'612, 701, 820',neuter:'yes',status:'waiting'},
  {name:'太妹',no:'2025061004',gender:'female',color:'棕黑虎斑/米克斯',age:'2025/04',vaccine:'612, 708, 822',deworm:'612, 701, 822',neuter:'yes',status:'waiting'},
  {name:'甜甜',no:'2025061205',gender:'female',color:'黑白乳牛/米克斯',age:'2025/05',vaccine:'612, 0709, 0820',deworm:'612, 701, 804',neuter:'yes',status:'waiting'},
  {name:'酸酸',no:'2025070502',gender:'female',color:'虎斑（尾巴比較長）',age:'2025/06',vaccine:'725, 821, 918',deworm:'705, 821, 921',neuter:'yes',status:'waiting'},
  {name:'春天',no:'2025071801',gender:'female',color:'黑白賓士/米克斯',age:'2025/06',vaccine:'814, 0911, 1011',deworm:'817, 921, 1219',neuter:'yes',status:'waiting'},
  {name:'小祕',no:'2025081601',gender:'female',vaccine:'811, 922',deworm:'811',neuter:'yes',status:'waiting'},
  {name:'春風',no:'2025083101',gender:'female',color:'白底虎斑',age:'2025/03',vaccine:'919, 1020, 1117',deworm:'1020, 1117',neuter:'yes',hiv:'陰',felv:'陰',status:'waiting'},
  {name:'阿花',no:'2025083102',gender:'female',color:'虎斑',vaccine:'11xx, 1203 四合一',deworm:'1229',hiv:'陽',felv:'陰',status:'waiting',notes:'⚠️ 愛滋陽性'},
  {name:'蜜月',no:'2025092601',gender:'male',color:'賓士',age:'2025/09',vaccine:'1107, 1205',deworm:'113',status:'waiting'},
  {name:'蜜寶',no:'2025092602',gender:'female',color:'虎斑',age:'2025/09',vaccine:'1107, 1205',deworm:'113',status:'waiting'},
  {name:'蜜糖',no:'2025092603',gender:'male',color:'賓士（鼻子黑白各半）',age:'2025/09',vaccine:'1107, 1205',deworm:'113',status:'waiting'},
  {name:'阿咪',no:'2025032101',gender:'female',color:'虎斑/米克斯',age:'2023/03',vaccine:'506, 0611 五合一',deworm:'全能貓 0321, 0505',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'小王子',no:'2025122701',gender:'male',color:'虎斑',vaccine:'20251227',deworm:'20251227',status:'waiting'},
  {name:'黃金',no:'2025123001',gender:'male',color:'橘貓',vaccine:'1230',deworm:'1230',neuter:'yes',status:'waiting'},
  {name:'奶油',no:'2026011301',gender:'male',color:'橘貓',vaccine:'113, 206',deworm:'113, 206',status:'waiting'},
  {name:'小小甫',no:'2026011501',gender:'female',color:'虎斑',vaccine:'115',deworm:'115',neuter:'yes',status:'waiting'},
  {name:'小黑',no:'2026011901',gender:'female',color:'玳瑁',vaccine:'119, 213',deworm:'119, 213',neuter:'yes',status:'waiting'},
  {name:'公主',no:'2026012801',gender:'female',color:'白底虎斑',vaccine:'128, 226',deworm:'123, 226',neuter:'yes',status:'waiting'},
  {name:'王冠',no:'2026012802',gender:'male',color:'白底虎斑',vaccine:'128, 226',deworm:'123, 226',neuter:'yes',status:'waiting'},
  // 搬離日期有X = 彩虹橋或暫離，這裡阿咪搬離日期20250917X特別標記
  {name:'水晶',no:'2024101101',gender:'male',color:'白底橘/米克斯',age:'~2024/06',weight:'1.86kg',vaccine:'11/20/2024 3in-1, 12/31, 04/10 五合一',deworm:'全能貓S 2025/02/12',neuter:'yes',hiv:'➖',felv:'➖',status:'waiting'},
  {name:'小寶',no:'2026022201',gender:'female',color:'虎斑',vaccine:'204, 226',deworm:'222',status:'waiting'},
  {name:'大寶',no:'2026022202',gender:'male',color:'虎斑',vaccine:'204, 226',deworm:'222',status:'waiting'},
  {name:'黑熊',no:'2026022301',gender:'male',color:'黑貓',vaccine:'223',deworm:'123, 223',neuter:'yes',status:'waiting'},
  {name:'墨墨',no:'2026022801',gender:'female',color:'虎斑',vaccine:'216, 310',deworm:'216, 318',neuter:'yes',status:'waiting'},
  {name:'斑斑',no:'2026022802',gender:'female',color:'賓士',vaccine:'216, 310',deworm:'216, 318',neuter:'yes',status:'waiting'},
  {name:'沐沐',no:'2026030501',gender:'male',color:'賓士',vaccine:'227, 320',deworm:'320',neuter:'yes',status:'waiting'},
  {name:'黑皮',no:'2026031001',status:'waiting'},
  {name:'毛毛蟲',no:'2026032001',status:'waiting'},
  {name:'嬛嬛',no:'2026032301',vaccine:'xxx',deworm:'323',status:'waiting'},
];

function init(){
  if(gc().length===0){
    const creds=gcr();
    const cats=RAW.map(d=>{
      const id='cat_'+d.no+'_'+Math.random().toString(36).substr(2,4);
      if(!creds[id]) creds[id]={catId:id,catName:d.name,username:genUser(d.name),password:genPass()};
      return{...d,id,addedAt:Date.now()};
    });
    sc(cats);scr(creds);
  }
}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// LOGIN
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function setLT(t){
  S.loginType=t;
  document.getElementById('lt-admin').classList.toggle('on',t==='admin');
  document.getElementById('lt-owner').classList.toggle('on',t==='owner');
  document.getElementById('hint-admin').style.display=t==='admin'?'block':'none';
  document.getElementById('hint-owner').style.display=t==='owner'?'block':'none';
}
function doLogin(){
  const u=document.getElementById('lU').value.trim();
  const p=document.getElementById('lP').value.trim();
  const err=document.getElementById('lErr');
  err.style.display='none';
  if(S.loginType==='admin'){
    if(u===ADMIN.u&&p===ADMIN.p){S.user='管理員';S.role='admin';enterApp();}
    else err.style.display='block';
  } else {
    const match=Object.values(gcr()).find(c=>c.username===u&&c.password===p);
    if(match){S.user=match.catName+'的飼主';S.role='owner';S.ownerCatId=match.catId;enterApp();}
    else err.style.display='block';
  }
}
function enterApp(){
  document.getElementById('sLogin').classList.remove('on');
  document.getElementById('sApp').classList.add('on');
  document.getElementById('userBadge').textContent=S.role==='admin'?'🛡️ 管理員':('🐱 '+S.user);
  document.getElementById('bn-admin').style.display=S.role==='admin'?'flex':'none';
  if(S.role==='owner'){
    document.getElementById('post-form').style.display='block';
    const cat=gc().find(c=>c.id===S.ownerCatId);
    if(cat){
      document.getElementById('ob-name').textContent='🐱 '+cat.name+'的幸福日記';
      document.getElementById('ob-sub').textContent='分享'+cat.name+'的日常 💕';
    }
  }
  renderAll();startCar();
}
function doLogout(){
  S.user=null;S.role=null;S.ownerCatId=null;
  document.getElementById('sApp').classList.remove('on');
  document.getElementById('sLogin').classList.add('on');
  document.getElementById('lU').value='';document.getElementById('lP').value='';
}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// RENDER HELPERS
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function photoUrl(cat){
  if(!cat.photo) return '';
  const m=cat.photo.match(/\/d\/([\w-]+)/);
  if(m) return `https://drive.google.com/thumbnail?id=${m[1]}&sz=w400`;
  return cat.photo;
}
function catEmoji(cat){
  const c=String(cat.color||'');
  if(c.includes('全黑')||c.includes('黑貓')) return '🐈‍⬛';
  if(c.includes('橘')) return '🟠';
  if(c.includes('三花')||c.includes('玳瑁')) return '🌈';
  if(c.includes('賓士')||c.includes('乳牛')) return '⚫';
  return '🐱';
}
function genderTag(g){
  if(!g) return '';
  const m=['male','♂','男','m'].some(x=>String(g).toLowerCase().includes(x));
  const f=['female','♀','女','f'].some(x=>String(g).toLowerCase().includes(x));
  if(m) return '<span class="tag tag-m">♂ 公貓</span>';
  if(f) return '<span class="tag tag-f">♀ 母貓</span>';
  return '';
}
function neuterTag(n){
  if(!n) return '';
  const y=['yes','✔️','✔','是'].some(x=>String(n).includes(x));
  const no2=['no','✖️','否'].some(x=>String(n).includes(x));
  if(y) return '<span class="tag tag-neuter">✂️ 已結紮</span>';
  if(no2) return '<span class="tag tag-warn">✖️ 未結紮</span>';
  return '';
}
function hivTag(h){
  if(!h||h==='➖'||h==='陰') return '<span class="tag tag-ok">💊 愛滋陰</span>';
  if(h==='➕'||h==='陽') return '<span class="tag tag-bad">⚠️ 愛滋陽</span>';
  return '<span class="tag tag-unk">❓ 愛滋未知</span>';
}
function felvTag(h){
  if(!h||h==='➖'||h==='陰') return '<span class="tag tag-ok">💉 白血陰</span>';
  if(h==='➕'||h==='陽') return '<span class="tag tag-bad">⚠️ 白血陽</span>';
  return '<span class="tag tag-unk">❓ 白血未知</span>';
}
function vacTag(v){
  return v&&v.length>1?'<span class="tag tag-vax">💉 有疫苗紀錄</span>':'';
}
function statusTag(s){
  const map={
    waiting:'<span class="tag tag-status-wait">🏠 等家中</span>',
    foster:'<span class="tag tag-status-foster">🏡 中途中</span>',
    perm:'<span class="tag tag-status-perm">💜 永久中途</span>',
    adopted:'<span class="tag tag-status-adopted">💚 已搬離</span>',
    rainbow:'<span class="tag tag-status-rainbow">🌈 彩虹橋</span>',
  };
  return map[s]||'';
}
function statusRibbon(s){
  const map={
    adopted:'<div class="ribbon ribbon-adopted">💚 已搬離</div>',
    perm:'<div class="ribbon ribbon-noadopt">💜 永久中途</div>',
    rainbow:'<div class="ribbon ribbon-rainbow">🌈 彩虹橋</div>',
    foster:'<div class="ribbon" style="background:linear-gradient(135deg,var(--b2),var(--b3))">🏡 中途</div>',
  };
  return map[s]||'';
}

function catCard(cat){
  const url=photoUrl(cat);
  return `<div class="cat-card" onclick="openModal('${cat.id}')">
    ${statusRibbon(cat.status)}
    ${url?`<img class="cat-photo" src="${url}" alt="${cat.name}" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'">
      <div class="cat-ph-ph" style="display:none">${catEmoji(cat)}</div>`
      :`<div class="cat-ph-ph">${catEmoji(cat)}</div>`}
    <div class="cat-body">
      <div class="cat-name">${cat.name}</div>
      <div class="cat-sub">${cat.color||''}${cat.age?' · '+cat.age:''}</div>
      <div class="cat-tags">
        ${genderTag(cat.gender)}
        ${neuterTag(cat.neuter)}
      </div>
    </div>
  </div>`;
}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// RENDER ALL
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function renderAll(){
  const cats=gc();
  renderHome(cats);renderWaiting(cats);renderAdopted(cats);
  renderAdminCats(cats);renderHealthTable(cats);renderAdoptionTable(cats);
  renderCreds();renderPosts();renderAdminPosts();updateStats(cats);
}

function renderHome(cats){
  const waiting=cats.filter(c=>c.status==='waiting'||c.status==='foster');
  const g=document.getElementById('home-grid');
  const latest=waiting.slice(0,6);
  g.innerHTML=latest.map(catCard).join('')||'<div class="empty"><div class="empty-ico">🐾</div><div class="empty-txt">暫無等家貓咪</div></div>';
  document.getElementById('hn-wait').textContent=waiting.length;
  document.getElementById('hn-adopt').textContent=cats.filter(c=>c.status==='adopted').length;
  document.getElementById('hn-total').textContent=cats.length;
}

function renderWaiting(cats){
  let list=cats.filter(c=>c.status==='waiting'||c.status==='foster'||c.status==='perm');
  if(S.search) list=list.filter(c=>c.name.includes(S.search)||String(c.color||'').includes(S.search));
  if(S.filter==='male') list=list.filter(c=>['male','♂','男'].some(x=>String(c.gender||'').toLowerCase().includes(x)));
  if(S.filter==='female') list=list.filter(c=>['female','♀','女','f'].some(x=>String(c.gender||'').toLowerCase().includes(x)));
  if(S.filter==='neutered') list=list.filter(c=>['yes','✔️','✔'].some(x=>String(c.neuter||'').includes(x)));
  if(S.filter==='vaccinated') list=list.filter(c=>c.vaccine&&c.vaccine.length>2);
  if(S.filter==='hiv_neg') list=list.filter(c=>!c.hiv||c.hiv==='➖'||c.hiv==='陰');
  const g=document.getElementById('waiting-grid');
  g.innerHTML=list.map(catCard).join('')||'<div class="empty"><div class="empty-ico">🔍</div><div class="empty-txt">沒有符合條件的貓咪</div></div>';
}

function renderAdopted(cats){
  const adopted=cats.filter(c=>c.status==='adopted');
  document.getElementById('adopt-count').textContent=adopted.length;
  const g=document.getElementById('adopted-grid');
  g.innerHTML=adopted.map(catCard).join('')||'<div class="empty"><div class="empty-ico">💚</div><div class="empty-txt">期待第一隻搬離的貓咪！</div></div>';
  buildCar(cats);
}

function buildCar(cats){
  const posts=gp();
  const items=[];
  // adopted cat own photos first
  cats.filter(c=>c.status==='adopted').forEach(c=>{
    const u=photoUrl(c);
    if(u) items.push({photo:u,name:c.name,text:c.notes||'已找到幸福的家 💚'});
  });
  // posts from all owners with photos
  posts.forEach(p=>{
    const cat=cats.find(c=>c.id===p.catId);
    if(p.photos) p.photos.forEach(ph=>items.push({photo:ph,name:cat?cat.name:p.ownerName,text:p.text||''}));
  });
  S.cItems=items;S.cIdx=0;
  const track=document.getElementById('cTrack');
  const dots=document.getElementById('cDots');
  if(!items.length){
    track.innerHTML='<div class="c-slide"><div class="c-ph"><span>📸</span><span style="font-size:.78rem">快來分享幸福照片！</span></div></div>';
    dots.innerHTML='';return;
  }
  track.innerHTML=items.map(it=>`
    <div class="c-slide" style="min-width:100%">
      <img class="c-img" src="${it.photo}" onclick="openPV('${it.photo.replace(/'/g,'')}')">
      <div class="c-cap">
        <div class="c-cap-name">🐱 ${it.name}</div>
        <div class="c-cap-txt">${String(it.text).slice(0,50)||'幸福日常'}</div>
      </div>
    </div>`).join('');
  dots.innerHTML=items.map((_,i)=>`<div class="c-dot${i===0?' on':''}" onclick="goCar(${i})"></div>`).join('');
  updateCar();
}
function updateCar(){
  document.getElementById('cTrack').style.transform=`translateX(-${S.cIdx*100}%)`;
  document.querySelectorAll('.c-dot').forEach((d,i)=>d.classList.toggle('on',i===S.cIdx));
}
function goCar(i){S.cIdx=((i%Math.max(1,S.cItems.length))+S.cItems.length)%Math.max(1,S.cItems.length);updateCar();}
function cNext(){if(S.cItems.length)goCar(S.cIdx+1);}
function cPrev(){if(S.cItems.length)goCar(S.cIdx-1);}
function startCar(){clearInterval(S.cTimer);S.cTimer=setInterval(()=>{if(S.cItems&&S.cItems.length>1)cNext();},4500);}

function updateStats(cats){
  const posts=gp(),creds=gcr();
  const w=cats.filter(c=>c.status!=='adopted'&&c.status!=='rainbow').length;
  const a=cats.filter(c=>c.status==='adopted').length;
  const set=(id,v)=>{const e=document.getElementById(id);if(e)e.textContent=v;};
  set('st-w',w);set('st-a',a);set('st-p',posts.length);set('st-o',Object.keys(creds).length);
}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// MODAL
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function openModal(catId){
  const cat=gc().find(c=>c.id===catId);if(!cat)return;
  const isAdmin=S.role==='admin';
  const creds=gcr()[catId];
  const url=photoUrl(cat);
  document.getElementById('modalContent').innerHTML=`
    ${url?`<img class="m-photo" src="${url}" onclick="openPV('${url}')" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'">
      <div class="m-ph" style="display:none">${catEmoji(cat)}</div>`:`<div class="m-ph">${catEmoji(cat)}</div>`}
    <div class="m-body">
      <div class="m-name">${cat.name}</div>
      <div class="m-no">No. ${cat.no||cat.id}</div>
      <div class="m-tags">
        ${genderTag(cat.gender)}${neuterTag(cat.neuter)}${statusTag(cat.status)}
        ${cat.hiv?hivTag(cat.hiv):''}${cat.felv?felvTag(cat.felv):''}
        ${vacTag(cat.vaccine)}
      </div>
      <div class="m-info-grid">
        <div class="mig"><div class="mig-l">🎨 花色</div><div class="mig-v">${cat.color||'不詳'}</div></div>
        <div class="mig"><div class="mig-l">🎂 年紀</div><div class="mig-v">${cat.age||'未知'}</div></div>
        <div class="mig"><div class="mig-l">⚖️ 體重</div><div class="mig-v">${cat.weight||'未量'}</div></div>
        <div class="mig"><div class="mig-l">📋 狀態</div><div class="mig-v">${{waiting:'🏠 等家中',foster:'🏡 中途中',perm:'💜 永久中途',adopted:'💚 已搬離',rainbow:'🌈 彩虹橋'}[cat.status]||cat.status}</div></div>
      </div>
      ${cat.vaccine||cat.deworm||cat.neuter?`
      <div class="m-health">
        <div class="m-health-title">🏥 健康資訊</div>
        ${cat.vaccine?`<div class="m-health-row"><span class="m-health-key">💉 疫苗</span><span class="m-health-val">${cat.vaccine}</span></div>`:''}
        ${cat.deworm?`<div class="m-health-row"><span class="m-health-key">🐛 驅蟲</span><span class="m-health-val">${cat.deworm}</span></div>`:''}
        ${cat.neuter?`<div class="m-health-row"><span class="m-health-key">✂️ 結紮</span><span class="m-health-val">${['yes','✔️','✔'].some(x=>String(cat.neuter).includes(x))?'✔️ 已結紮':'✖️ 未結紮'}</span></div>`:''}
      </div>`:''}
      ${cat.notes?`<div style="font-size:.8rem;color:var(--mid);line-height:1.9;margin-bottom:12px;background:rgba(255,224,163,.2);border-left:3px solid var(--y2);padding:8px 10px;border-radius:0 10px 10px 0;">${cat.notes}</div>`:''}
      ${isAdmin&&creds?`
      <div class="cred-box">
        <div class="cred-title">🔑 飼主登入帳號</div>
        <div class="cred-row"><span class="cred-key">帳號</span><span><span class="cred-val">${creds.username}</span><button class="copy-sm" onclick="copyTxt('${creds.username}')">複製</button></span></div>
        <div class="cred-row"><span class="cred-key">密碼</span><span><span class="cred-val">${creds.password}</span><button class="copy-sm" onclick="copyTxt('${creds.password}')">複製</button></span></div>
      </div>`:''}
      <div style="display:flex;gap:8px;margin-top:4px;">
        ${isAdmin?`<button class="btn btn-y btn-sm" onclick="editCat('${cat.id}');closeModal();goPage('admin');switchAT('cats',document.querySelectorAll('.atab')[1])">✏️ 編輯</button>`:''}
        ${isAdmin&&cat.status!=='adopted'?`<button class="btn btn-g btn-sm" onclick="markAdopted('${cat.id}');closeModal()">💚 標記送養</button>`:''}
        <button class="btn btn-ghost btn-sm" style="flex:1;" onclick="closeModal()">關閉</button>
      </div>
    </div>`;
  document.getElementById('catModal').classList.add('on');
}
function closeModal(){document.getElementById('catModal').classList.remove('on');}
document.getElementById('catModal').addEventListener('click',e=>{if(e.target===document.getElementById('catModal'))closeModal();});

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// ADMIN CAT TABLE
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function renderAdminCats(cats){
  const tb=document.getElementById('catTbody');if(!tb)return;
  tb.innerHTML=cats.map(c=>`<tr>
    <td class="tbl-name">${c.name}</td>
    <td>${genderTag(c.gender)}</td>
    <td style="font-size:.68rem">${c.color||'-'}</td>
    <td>${statusTag(c.status)}</td>
    <td>${neuterTag(c.neuter)||'<span class="tag tag-unk">-</span>'}</td>
    <td style="font-size:.62rem;max-width:100px;overflow:hidden;white-space:nowrap;text-overflow:ellipsis">${c.vaccine||'-'}</td>
    <td style="white-space:nowrap;">
      <button class="btn btn-y btn-sm" onclick="editCat('${c.id}')">✏️</button>
      <button class="btn btn-g btn-sm" onclick="markAdopted('${c.id}')">${c.status==='adopted'?'↩️':'✅'}</button>
      <button class="btn btn-r btn-sm" onclick="delCat('${c.id}')">🗑️</button>
    </td>
  </tr>`).join('');
}
function renderHealthTable(cats){
  const tb=document.getElementById('healthTbody');if(!tb)return;
  tb.innerHTML=cats.map(c=>`<tr>
    <td class="tbl-name">${c.name}</td>
    <td style="font-size:.62rem;max-width:130px;word-break:break-word">${c.vaccine||'-'}</td>
    <td style="font-size:.62rem;max-width:110px;word-break:break-word">${c.deworm||'-'}</td>
    <td>${neuterTag(c.neuter)||'<span class="tag tag-unk">-</span>'}</td>
    <td style="font-size:.72rem">${c.weight||'-'}</td>
    <td>${c.hiv?hivTag(c.hiv):'-'}</td>
    <td>${c.felv?felvTag(c.felv):'-'}</td>
  </tr>`).join('');
}
function renderAdoptionTable(cats){
  const tb=document.getElementById('adoptTbody');if(!tb)return;
  const adopted=cats.filter(c=>c.status==='adopted');
  tb.innerHTML=adopted.length?adopted.map(c=>`<tr>
    <td class="tbl-name">${c.name}</td>
    <td style="font-size:.72rem">${c.adoptDate||'-'}</td>
    <td style="font-size:.72rem">${c.leaveDate||'-'}</td>
    <td style="font-size:.72rem">${c.adopterSns||'-'}</td>
  </tr>`).join(''):'<tr><td colspan="4" style="text-align:center;color:var(--soft);padding:20px;">暫無送養紀錄</td></tr>';
}
function renderCreds(){
  const div=document.getElementById('credsList');if(!div)return;
  const entries=Object.values(gcr());
  if(!entries.length){div.innerHTML='<div class="empty"><div class="empty-ico">🔑</div><div class="empty-txt">尚無帳號</div></div>';return;}
  div.innerHTML=entries.map(c=>`
    <div class="cred-card">
      <div class="cc-name">🐱 ${c.catName}</div>
      <div class="cred-row"><span class="cred-key">帳號</span><span><span class="cred-val">${c.username}</span><button class="copy-sm" onclick="copyTxt('${c.username}')">複製</button></span></div>
      <div class="cred-row"><span class="cred-key">密碼</span><span><span class="cred-val">${c.password}</span><button class="copy-sm" onclick="copyTxt('${c.password}')">複製</button></span></div>
    </div>`).join('');
}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// CRUD
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function editCat(id){
  const cat=gc().find(c=>c.id===id);if(!cat)return;
  document.getElementById('editId').value=id;
  document.getElementById('fTitle').textContent='✏️ 編輯貓咪';
  const s=(fid,val)=>{const e=document.getElementById(fid);if(e)e.value=val||'';};
  s('fn',cat.name);s('fno',cat.no);s('fg',cat.gender);s('fc',cat.color);
  s('fa',cat.age);s('fw',cat.weight);s('fst',cat.status);s('fneu',cat.neuter||'');
  s('fhiv',cat.hiv||'➖');s('ffelv',cat.felv||'➖');
  s('fvac',cat.vaccine);s('fdew',cat.deworm);s('fpho',cat.photo);s('fnotes',cat.notes);
}
function saveCat(){
  const name=document.getElementById('fn').value.trim();
  if(!name){toast('請輸入貓咪名字 🐱','err');return;}
  const editId=document.getElementById('editId').value;
  const cats=gc();
  const data={
    name,no:document.getElementById('fno').value.trim(),
    gender:document.getElementById('fg').value,
    color:document.getElementById('fc').value.trim(),
    age:document.getElementById('fa').value.trim(),
    weight:document.getElementById('fw').value.trim(),
    status:document.getElementById('fst').value,
    neuter:document.getElementById('fneu').value,
    hiv:document.getElementById('fhiv').value,
    felv:document.getElementById('ffelv').value,
    vaccine:document.getElementById('fvac').value.trim(),
    deworm:document.getElementById('fdew').value.trim(),
    photo:document.getElementById('fpho').value.trim(),
    notes:document.getElementById('fnotes').value.trim(),
  };
  if(editId){const i=cats.findIndex(c=>c.id===editId);if(i>=0)cats[i]={...cats[i],...data};}
  else{
    const id='cat_'+Date.now()+'_'+Math.random().toString(36).substr(2,4);
    const creds=gcr();
    if(!creds[id])creds[id]={catId:id,catName:name,username:genUser(name),password:genPass()};
    scr(creds);cats.push({...data,id,addedAt:Date.now()});
  }
  sc(cats);resetForm();renderAll();toast(editId?'✅ 已更新！':'✅ 新增成功！','ok');
}
function resetForm(){
  document.getElementById('editId').value='';
  document.getElementById('fTitle').textContent='➕ 新增貓咪';
  ['fn','fno','fc','fa','fw','fvac','fdew','fpho','fnotes'].forEach(id=>{const e=document.getElementById(id);if(e)e.value='';});
  document.getElementById('fg').value='';
  document.getElementById('fst').value='waiting';
  document.getElementById('fneu').value='';
  document.getElementById('fhiv').value='➖';
  document.getElementById('ffelv').value='➖';
}
function markAdopted(id){
  const cats=gc();const c=cats.find(x=>x.id===id);if(!c)return;
  c.status=c.status==='adopted'?'waiting':'adopted';
  sc(cats);renderAll();toast(c.status==='adopted'?`🎉 ${c.name} 已標記為送養！`:`${c.name} 已改回等家`,'ok');
}
function delCat(id){
  if(!confirm('確定要刪除這隻貓咪的資料嗎？'))return;
  sc(gc().filter(c=>c.id!==id));renderAll();toast('已刪除','ok');
}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// POSTS
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function onFile(e){
  Array.from(e.target.files).forEach(f=>{
    const r=new FileReader();
    r.onload=ev=>{S.uploads.push(ev.target.result);renderPreviews();};
    r.readAsDataURL(f);
  });e.target.value='';
}
function renderPreviews(){
  const pv=document.getElementById('previews');
  const txt=document.getElementById('uaTxt');
  if(S.uploads.length){
    txt.style.display='none';
    pv.innerHTML=S.uploads.map((src,i)=>`
      <div class="prev-wrap">
        <img class="prev-img" src="${src}">
        <button class="prev-del" onclick="rmUpload(${i});event.stopPropagation()">✕</button>
      </div>`).join('');
  } else {txt.style.display='block';pv.innerHTML='';}
}
function rmUpload(i){S.uploads.splice(i,1);renderPreviews();}
function submitPost(){
  const text=document.getElementById('postTxa').value.trim();
  if(!text&&!S.uploads.length){toast('請輸入文字或照片 📸','err');return;}
  const posts=gp();
  posts.unshift({id:'p_'+Date.now(),catId:S.ownerCatId||null,ownerName:S.user,
    text,photos:[...S.uploads],createdAt:Date.now()});
  sp(posts);
  document.getElementById('postTxa').value='';
  S.uploads=[];renderPreviews();renderPosts();renderAdminPosts();updateStats(gc());buildCar(gc());
  toast('🐾 分享成功！','ok');
}
function renderPosts(){
  const posts=gp();
  const filter=S.role==='owner'?S.ownerCatId:null;
  const list=filter?posts.filter(p=>p.catId===filter):posts;
  const div=document.getElementById('postsList');
  if(!list.length){
    div.innerHTML='<div class="empty"><div class="empty-ico">📸</div><div class="empty-txt">還沒有分享<br>快來第一個！</div></div>';return;
  }
  div.innerHTML=list.map(p=>`
    <div class="post-item">
      <div class="pi-head">
        <div class="pi-ava">🐱</div>
        <div style="flex:1;">
          <div class="pi-name">${p.ownerName}</div>
          <div class="pi-time">${fmtT(p.createdAt)}</div>
        </div>
        ${S.role==='admin'?`<button class="btn btn-r btn-sm" onclick="delPost('${p.id}')">刪除</button>`:''}
      </div>
      ${p.text?`<div class="pi-text">${p.text}</div>`:''}
      ${p.photos&&p.photos.length?`<div class="pi-photos">${p.photos.map(s=>`<img class="pi-photo" src="${s}" onclick="openPV('${s.replace(/'/g,'')}')">`).join('')}</div>`:''}
    </div>`).join('');
}
function renderAdminPosts(){
  const div=document.getElementById('adminPostsList');if(!div)return;
  const posts=gp();
  if(!posts.length){div.innerHTML='<div class="empty"><div class="empty-ico">📸</div><div class="empty-txt">暫無貼文</div></div>';return;}
  div.innerHTML=posts.map(p=>`
    <div class="cred-card">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:6px;">
        <div style="font-family:var(--font-d);font-size:.85rem;font-weight:900;color:var(--p3)">${p.ownerName}</div>
        <div style="display:flex;gap:6px;align-items:center;">
          <span style="font-size:.62rem;color:var(--soft)">${fmtT(p.createdAt)}</span>
          <button class="btn btn-r btn-sm" onclick="delPost('${p.id}')">刪除</button>
        </div>
      </div>
      ${p.text?`<div style="font-size:.76rem;color:var(--mid);margin-bottom:6px">${p.text}</div>`:''}
      ${p.photos&&p.photos.length?`<div style="display:flex;flex-wrap:wrap;gap:5px">${p.photos.map(s=>`<img src="${s}" style="width:50px;height:50px;border-radius:8px;object-fit:cover;cursor:pointer;border:1.5px solid var(--p1)" onclick="openPV('${s.replace(/'/g,'')}')">`).join('')}</div>`:''}
    </div>`).join('');
}
function delPost(id){sp(gp().filter(p=>p.id!==id));renderPosts();renderAdminPosts();updateStats(gc());buildCar(gc());toast('已刪除','ok');}
function fmtT(ts){return new Date(ts).toLocaleString('zh-TW',{month:'short',day:'numeric',hour:'2-digit',minute:'2-digit'});}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// GOOGLE SHEETS SYNC
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
async function doSync(){
  const sid=document.getElementById('sheetId')?.value||SHEET_ID;
  const dot=document.getElementById('syncDot');
  const st=document.getElementById('syncSt');
  const res=document.getElementById('syncResult');
  if(dot)dot.classList.add('spin');
  if(st)st.textContent='同步中...';
  if(res)res.innerHTML='<span style="color:var(--y2)">🔄 讀取試算表中...</span>';
  toast('🔄 同步中...','');
  try{
    // Sheet 1: 貓咪們 (gid=0)
    const r1=await fetch(`https://docs.google.com/spreadsheets/d/${sid}/export?format=csv&gid=0`);
    if(!r1.ok)throw new Error('無法讀取試算表，請確認已公開');
    const csv1=await r1.text();
    const rows1=parseCSV(csv1).filter(r=>r.some(c=>c.trim()));

    // Sheet 2: 已搬離 (gid=1)  
    let rows2=[];
    try{
      const r2=await fetch(`https://docs.google.com/spreadsheets/d/${sid}/export?format=csv&gid=1`);
      if(r2.ok){const csv2=await r2.text();rows2=parseCSV(csv2).filter(r=>r.some(c=>c.trim()));}
    }catch(e){}

    const existingCats=gc();const creds=gcr();
    const newCats=[];const seen=new Set();

    function processRows(rows,defaultStatus){
      if(rows.length<2)return;
      const heads=rows[0];
      const fh=kws=>{ for(let i=0;i<heads.length;i++) if(kws.some(k=>heads[i].includes(k)))return i; return-1;};
      const iN=fh(['貓名','名字']);const iNo=fh(['編號']);const iLeave=fh(['搬離']);
      const iVac=fh(['疫苗']);const iDew=fh(['驅蟲']);const iNeu=fh(['結紮']);
      const iGend=fh(['性別']);const iCol=fh(['花色']);const iHiv=fh(['愛滋']);
      const iFelv=fh(['白血']);const iAge=fh(['年紀']);const iWt=fh(['體重']);
      const iAdoptD=fh(['送養日期']);const iSns=fh(['網路']);

      rows.slice(1).forEach(row=>{
        const name=row[iN]?.trim();if(!name)return;
        seen.add(name);
        const leaveRaw=iLeave>=0?row[iLeave]?.trim():'';
        // 搬離日期含X = 彩虹橋/暫時標記，不算送養
        let status=defaultStatus;
        if(leaveRaw&&leaveRaw.toUpperCase().includes('X')) status='rainbow';
        else if(leaveRaw&&leaveRaw.length>2) status='adopted';

        const existing=existingCats.find(c=>c.name===name);
        const catId=existing?existing.id:('cat_'+Date.now()+'_'+Math.random().toString(36).substr(2,5));
        if(!creds[catId]) creds[catId]={catId,catName:name,username:genUser(name),password:genPass()};

        newCats.push({
          id:catId,name,no:row[iNo]?.trim()||'',
          gender:row[iGend]?.trim()||'',color:row[iCol]?.trim()||'',
          age:row[iAge]?.trim()||'',weight:row[iWt]?.trim()||'',
          vaccine:row[iVac]?.trim()||'',deworm:row[iDew]?.trim()||'',
          neuter:row[iNeu]?.trim()||'',hiv:row[iHiv]?.trim()||'',
          felv:row[iFelv]?.trim()||'',
          adoptDate:row[iAdoptD]?.trim()||'',leaveDate:leaveRaw,
          adopterSns:iSns>=0?row[iSns]?.trim()||'':'',
          status,photo:existing?.photo||'',notes:existing?.notes||'',
          addedAt:existing?.addedAt||Date.now(),
        });
      });
    }

    processRows(rows1,'waiting');
    // 已搬離 sheet預設 adopted
    processRows(rows2,'adopted');
    // keep manually-added cats not in sheet
    existingCats.forEach(c=>{if(!seen.has(c.name))newCats.push(c);});

    sc(newCats);scr(creds);
    renderAll();
    if(dot)dot.classList.remove('spin');
    if(st)st.textContent='同步成功 · '+new Date().toLocaleTimeString('zh-TW');
    if(res)res.innerHTML=`<span style="color:var(--g3)">✅ 同步完成！共 ${newCats.length} 隻貓咪（等家+已搬離兩個分頁）</span>`;
    toast(`✅ 同步成功！${newCats.length} 筆資料`,'ok');
  }catch(e){
    if(dot)dot.classList.remove('spin');
    if(st)st.textContent='同步失敗';
    if(res)res.innerHTML=`<span style="color:var(--p3)">❌ ${e.message}</span>`;
    toast('❌ 同步失敗','err');
  }
}
function parseCSV(text){
  return text.split('\n').map(line=>{
    const row=[];let inQ=false,cell='';
    for(const c of line){
      if(c==='"'){inQ=!inQ;}else if(c===','&&!inQ){row.push(cell.trim());cell='';}else{cell+=c;}
    }
    row.push(cell.trim());return row;
  }).filter(r=>r.length>1);
}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// EXPORT
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function exportCreds(){
  const e=Object.values(gcr());if(!e.length){toast('尚無帳號','err');return;}
  let t='浪貓不浪 · 飼主帳號列表\n匯出：'+new Date().toLocaleString('zh-TW')+'\n'+'='.repeat(36)+'\n\n';
  e.forEach(c=>{t+=`貓咪：${c.catName}\n帳號：${c.username}\n密碼：${c.password}\n\n`;});
  dlFile(t,'浪貓不浪帳號.txt');toast('✅ 已匯出','ok');
}
function exportAll(){
  const cats=gc();
  let t='浪貓不浪 · 全部貓咪資料\n匯出：'+new Date().toLocaleString('zh-TW')+'\n'+'='.repeat(36)+'\n\n';
  cats.forEach(c=>{
    t+=`【${c.name}】${c.no||''}\n  性別：${c.gender||'?'} / 花色：${c.color||'?'} / 年紀：${c.age||'?'}\n  狀態：${{waiting:'等家中',foster:'中途',perm:'永久中途',adopted:'已送養搬離',rainbow:'彩虹橋'}[c.status]||c.status}\n  疫苗：${c.vaccine||'無'}\n  驅蟲：${c.deworm||'無'}\n  結紮：${c.neuter||'?'} / 愛滋：${c.hiv||'?'} / 白血：${c.felv||'?'}\n\n`;
  });
  dlFile(t,'浪貓不浪資料.txt');toast('✅ 已匯出','ok');
}
function dlFile(t,name){
  const a=document.createElement('a');
  a.href=URL.createObjectURL(new Blob([t],{type:'text/plain;charset=utf-8'}));
  a.download=name;a.click();
}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// NAVIGATION
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function goPage(page){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('on'));
  document.getElementById('p-'+page)?.classList.add('on');
  document.querySelectorAll('.bn').forEach(b=>b.classList.remove('on'));
  document.getElementById('bn-'+page)?.classList.add('on');
  document.querySelector('.scroll').scrollTop=0;
  if(page==='adopted')renderAdopted(gc());
  if(page==='share')renderPosts();
  if(page==='admin'){renderAdminCats(gc());renderHealthTable(gc());renderAdoptionTable(gc());renderCreds();renderAdminPosts();}
}
function switchAT(tab,el){
  document.querySelectorAll('.atab').forEach(t=>t.classList.remove('on'));
  if(el)el.classList.add('on');
  document.querySelectorAll('.asec').forEach(s=>s.classList.remove('on'));
  document.getElementById('at-'+tab)?.classList.add('on');
  const r={creds:renderCreds,'posts-admin':renderAdminPosts,health:()=>renderHealthTable(gc()),adoption:()=>renderAdoptionTable(gc())};
  if(r[tab])r[tab]();
}
function setF(f,el){
  S.filter=f;
  document.querySelectorAll('.fc').forEach(c=>c.classList.remove('on'));
  el.classList.add('on');
  renderWaiting(gc());
}
function filterWaiting(){S.search=document.getElementById('searchInp').value.trim();renderWaiting(gc());}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// UTILS
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
function openPV(src){document.getElementById('pvImg').src=src;document.getElementById('pvBg').classList.add('on');}
function closePV(){document.getElementById('pvBg').classList.remove('on');}
function copyTxt(t){
  navigator.clipboard?.writeText(t).then(()=>toast('✅ 已複製','ok')).catch(()=>{
    const e=document.createElement('textarea');e.value=t;document.body.appendChild(e);e.select();
    document.execCommand('copy');document.body.removeChild(e);toast('✅ 已複製','ok');
  });
}
let tT;
function toast(msg,type){
  const e=document.getElementById('toast');e.textContent=msg;e.className='toast '+(type||'');
  e.classList.add('on');clearTimeout(tT);tT=setTimeout(()=>e.classList.remove('on'),3000);
}

// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
// BOOT
// ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
init();
</script>
</body>
</html>
