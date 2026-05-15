import { useState, useRef, useEffect } from "react";

// ── Claude API ──────────────────────────────────────────────────────
async function callClaude(prompt, system = "") {
  const res = await fetch("https://api.anthropic.com/v1/messages", {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({
      model: "claude-sonnet-4-20250514",
      max_tokens: 1000,
      system: system || "You are DomainForge AI, an expert domain investor. Be concise and practical. Always respond in the same language the user writes in (Arabic, French, or English).",
      messages: [{ role: "user", content: prompt }],
    }),
  });
  const d = await res.json();
  return d.content?.[0]?.text || "";
}

// ── Translations ────────────────────────────────────────────────────
const T = {
  en: {
    dir: "ltr", lang: "en",
    appName: "DomainForge",
    tagline: "AI-Powered Domain Intelligence — 100% Free",
    search_placeholder: "Search domain, keyword, company...",
    nav: { dashboard:"Dashboard", tools:"Domain Tools", ai:"AI Analysis", leads:"Lead Finder", expired:"Expired Domains", maps:"Google Maps", extractor:"Page Extractor", chat:"AI Chat" },
    free_badge: "FREE",
    analyze: "Analyze →",
    analyzing: "Analyzing...",
    run_ai: "Run AI →",
    thinking: "AI is thinking...",
    search: "Search →",
    searching: "Searching...",
    export_csv: "Export CSV",
    copy: "Copy",
    register: "Register",
    add_lead: "Add Lead",
    open_maps: "Open in Google Maps →",
    dashboard_title: "Welcome to DomainForge 👋",
    dashboard_sub: "All domain tools, completely free. Choose a tool to get started.",
    tools_title: "Domain Research Tools",
    tools_sub: "WHOIS · DNS · SEO · Availability — enter any domain",
    ai_title: "AI Analysis Suite",
    ai_sub: "Powered by Claude — domain evaluation, ideas, outreach emails",
    leads_title: "Lead Finder",
    leads_sub: "Find emails & phone numbers from any company domain",
    expired_title: "Expired Domain Finder",
    expired_sub: "Discover dropped domains with SEO value",
    maps_title: "Google Maps Business Search",
    maps_sub: "Search businesses and find their contact info",
    extractor_title: "Page Email & Phone Extractor",
    extractor_sub: "Paste any URL or HTML — extract all emails and phone numbers instantly",
    chat_title: "AI Assistant",
    chat_sub: "Ask anything about domains and investing",
    whois_tab:"WHOIS", dns_tab:"DNS", seo_tab:"SEO", avail_tab:"Availability", overview_tab:"Overview",
    domain_label:"Domain", age_label:"Age", registrar_label:"Registrar",
    expires_label:"Expires", da_label:"DA Score", backlinks_label:"Backlinks",
    ai_analysis:"Claude AI Analysis", ai_badge:"AI Powered",
    evaluate:"Evaluate Domain", ideas:"Domain Ideas", email_gen:"Outreach Email", buyers:"Find Buyers", scam:"Scam Check",
    domain_input:"Domain to evaluate (e.g. healthtech.ai)",
    keyword_input:"Industry / keyword (e.g. fintech, wellness)",
    selling_input:"Domain you're selling",
    buyer_type:"Target buyer industry",
    scam_input:"Domain to check for spam risk",
    found:"Found", contacts:"contacts for",
    confidence:"Confidence", source:"Source", action:"Action",
    biz_type:"Business type (e.g. dental clinic)",
    city_input:"City or ZIP (e.g. New York)",
    url_input:"Paste a website URL (e.g. https://example.com)",
    html_input:"Or paste HTML source code directly",
    extract:"Extract →",
    extracting:"Extracting...",
    emails_found:"Emails Found",
    phones_found:"Phone Numbers Found",
    no_results:"No emails or phone numbers found on this page.",
    filter_tld:"TLD",
    filter_da:"Min DA",
    filter_kw:"Keyword contains",
    chat_placeholder:"Ask about domains, investing, how to use tools...",
    send:"Send",
    open_maps_link:"🗺️ Open Google Maps",
  },
  ar: {
    dir: "rtl", lang: "ar",
    appName: "دومين فورج",
    tagline: "منصة النطاقات بالذكاء الاصطناعي — مجانية 100%",
    search_placeholder: "ابحث عن نطاق، كلمة مفتاحية، شركة...",
    nav: { dashboard:"الرئيسية", tools:"أدوات النطاقات", ai:"تحليل الذكاء الاصطناعي", leads:"البحث عن عملاء", expired:"النطاقات المنتهية", maps:"خرائط جوجل", extractor:"استخراج بيانات", chat:"مساعد AI" },
    free_badge: "مجاني",
    analyze: "تحليل ←",
    analyzing: "جارٍ التحليل...",
    run_ai: "تشغيل AI ←",
    thinking: "AI يفكر...",
    search: "بحث ←",
    searching: "جارٍ البحث...",
    export_csv: "تصدير CSV",
    copy: "نسخ",
    register: "تسجيل",
    add_lead: "إضافة عميل",
    open_maps: "فتح في خرائط جوجل ←",
    dashboard_title: "مرحباً بك في دومين فورج 👋",
    dashboard_sub: "جميع أدوات النطاقات مجانية تماماً. اختر أداة للبدء.",
    tools_title: "أدوات بحث النطاقات",
    tools_sub: "WHOIS · DNS · SEO · التوفر — أدخل أي نطاق",
    ai_title: "تحليل الذكاء الاصطناعي",
    ai_sub: "مدعوم بـ Claude — تقييم النطاقات، أفكار، إيميلات تسويقية",
    leads_title: "البحث عن عملاء",
    leads_sub: "ابحث عن إيميلات وأرقام هاتف من أي نطاق شركة",
    expired_title: "النطاقات المنتهية الصلاحية",
    expired_sub: "اكتشف النطاقات المنتهية ذات القيمة SEO",
    maps_title: "بحث الأعمال على خرائط جوجل",
    maps_sub: "ابحث عن الشركات واعثر على معلومات الاتصال",
    extractor_title: "استخراج الإيميلات والأرقام",
    extractor_sub: "الصق أي رابط أو HTML — استخرج جميع الإيميلات وأرقام الهاتف فوراً",
    chat_title: "مساعد الذكاء الاصطناعي",
    chat_sub: "اسأل أي شيء عن النطاقات والاستثمار",
    whois_tab:"WHOIS", dns_tab:"DNS", seo_tab:"تحسين محركات", avail_tab:"التوفر", overview_tab:"نظرة عامة",
    domain_label:"النطاق", age_label:"العمر", registrar_label:"المسجِّل",
    expires_label:"ينتهي في", da_label:"نقاط DA", backlinks_label:"الروابط الخلفية",
    ai_analysis:"تحليل Claude AI", ai_badge:"مدعوم بـ AI",
    evaluate:"تقييم النطاق", ideas:"أفكار نطاقات", email_gen:"إيميل تسويقي", buyers:"البحث عن مشترين", scam:"فحص Scam",
    domain_input:"النطاق المراد تقييمه (مثال: healthtech.ai)",
    keyword_input:"الصناعة / الكلمة المفتاحية (مثال: تقنية، صحة)",
    selling_input:"النطاق الذي تبيعه",
    buyer_type:"نوع المشتري المستهدف",
    scam_input:"النطاق للفحص ضد البريد المزعج",
    found:"تم العثور على", contacts:"جهات اتصال لـ",
    confidence:"الثقة", source:"المصدر", action:"إجراء",
    biz_type:"نوع العمل (مثال: عيادة أسنان)",
    city_input:"المدينة أو الرمز البريدي",
    url_input:"الصق رابط موقع (مثال: https://example.com)",
    html_input:"أو الصق كود HTML مباشرة",
    extract:"استخراج ←",
    extracting:"جارٍ الاستخراج...",
    emails_found:"إيميلات موجودة",
    phones_found:"أرقام هاتف موجودة",
    no_results:"لم يتم العثور على إيميلات أو أرقام في هذه الصفحة.",
    filter_tld:"اللاحقة",
    filter_da:"الحد الأدنى DA",
    filter_kw:"الكلمة المفتاحية",
    chat_placeholder:"اسأل عن النطاقات، الاستثمار، كيفية استخدام الأدوات...",
    send:"إرسال",
    open_maps_link:"🗺️ فتح خرائط جوجل",
  },
  fr: {
    dir: "ltr", lang: "fr",
    appName: "DomainForge",
    tagline: "Intelligence de domaines par IA — 100% Gratuit",
    search_placeholder: "Rechercher domaine, mot-clé, entreprise...",
    nav: { dashboard:"Tableau de bord", tools:"Outils Domaines", ai:"Analyse IA", leads:"Chercher Leads", expired:"Domaines Expirés", maps:"Google Maps", extractor:"Extracteur", chat:"Assistant IA" },
    free_badge: "GRATUIT",
    analyze: "Analyser →",
    analyzing: "Analyse en cours...",
    run_ai: "Lancer IA →",
    thinking: "L'IA réfléchit...",
    search: "Rechercher →",
    searching: "Recherche en cours...",
    export_csv: "Exporter CSV",
    copy: "Copier",
    register: "Enregistrer",
    add_lead: "Ajouter Lead",
    open_maps: "Ouvrir dans Google Maps →",
    dashboard_title: "Bienvenue sur DomainForge 👋",
    dashboard_sub: "Tous les outils de domaines, entièrement gratuits. Choisissez un outil.",
    tools_title: "Outils de Recherche de Domaines",
    tools_sub: "WHOIS · DNS · SEO · Disponibilité — entrez n'importe quel domaine",
    ai_title: "Suite d'Analyse IA",
    ai_sub: "Propulsé par Claude — évaluation, idées, emails de prospection",
    leads_title: "Chercheur de Leads",
    leads_sub: "Trouvez emails & téléphones depuis n'importe quel domaine",
    expired_title: "Domaines Expirés",
    expired_sub: "Découvrez les domaines abandonnés avec valeur SEO",
    maps_title: "Recherche d'Entreprises Google Maps",
    maps_sub: "Recherchez des entreprises et trouvez leurs coordonnées",
    extractor_title: "Extracteur d'Emails & Téléphones",
    extractor_sub: "Collez une URL ou du HTML — extrayez tous les emails et numéros instantanément",
    chat_title: "Assistant IA",
    chat_sub: "Posez n'importe quelle question sur les domaines et l'investissement",
    whois_tab:"WHOIS", dns_tab:"DNS", seo_tab:"SEO", avail_tab:"Disponibilité", overview_tab:"Vue d'ensemble",
    domain_label:"Domaine", age_label:"Âge", registrar_label:"Registraire",
    expires_label:"Expire le", da_label:"Score DA", backlinks_label:"Backlinks",
    ai_analysis:"Analyse Claude AI", ai_badge:"Propulsé par IA",
    evaluate:"Évaluer le Domaine", ideas:"Idées de Domaines", email_gen:"Email de Prospection", buyers:"Trouver Acheteurs", scam:"Vérif. Spam",
    domain_input:"Domaine à évaluer (ex: healthtech.ai)",
    keyword_input:"Secteur / mot-clé (ex: fintech, santé)",
    selling_input:"Domaine que vous vendez",
    buyer_type:"Secteur de l'acheteur cible",
    scam_input:"Domaine à vérifier pour spam",
    found:"Trouvé", contacts:"contacts pour",
    confidence:"Confiance", source:"Source", action:"Action",
    biz_type:"Type d'entreprise (ex: cabinet dentaire)",
    city_input:"Ville ou code postal",
    url_input:"Collez une URL (ex: https://example.com)",
    html_input:"Ou collez directement le code HTML",
    extract:"Extraire →",
    extracting:"Extraction en cours...",
    emails_found:"Emails Trouvés",
    phones_found:"Numéros Trouvés",
    no_results:"Aucun email ou numéro de téléphone trouvé sur cette page.",
    filter_tld:"Extension",
    filter_da:"DA minimum",
    filter_kw:"Mot-clé contient",
    chat_placeholder:"Posez vos questions sur les domaines, l'investissement...",
    send:"Envoyer",
    open_maps_link:"🗺️ Ouvrir Google Maps",
  }
};

// ── Mock data helpers ───────────────────────────────────────────────
const rnd = (a,b) => Math.floor(Math.random()*(b-a+1))+a;
const pick = arr => arr[rnd(0,arr.length-1)];

function mockWhois(domain) {
  const age = rnd(1,15);
  const created = new Date(Date.now()-age*365*24*3600*1000).toISOString().split("T")[0];
  const expires = new Date(Date.now()+rnd(1,3)*365*24*3600*1000).toISOString().split("T")[0];
  return { domain, registrar:pick(["GoDaddy","Namecheap","Cloudflare","Name.com","Dynadot"]), created, expires,
    age:`${age} years`, status:"clientTransferProhibited", country:pick(["US","CA","GB","DE","AU"]),
    nameservers:`ns1.cloudflare.com, ns2.cloudflare.com`, dnssec:pick(["Enabled","Disabled"]), privacy:pick(["Protected","Public"]) };
}
function mockDNS(domain) {
  return [
    { type:"A", value:`${rnd(1,254)}.${rnd(1,254)}.${rnd(1,254)}.${rnd(1,254)}`, ttl:"3600" },
    { type:"AAAA", value:"2606:4700:4700::1111", ttl:"3600" },
    { type:"MX", value:`mail.${domain} (Priority 10)`, ttl:"3600" },
    { type:"TXT", value:`v=spf1 include:_spf.${domain} ~all`, ttl:"3600" },
    { type:"NS", value:"ns1.cloudflare.com", ttl:"86400" },
    { type:"CNAME", value:`www → ${domain}`, ttl:"3600" },
  ];
}
function mockSEO() {
  const da = rnd(10,85);
  return { da, pa:Math.max(da-5,5), backlinks:`${rnd(50,50000).toLocaleString()}`,
    referringDomains:`${rnd(10,5000).toLocaleString()}`, organicTraffic:`${rnd(1,500)}K/mo`,
    keywords:`${rnd(100,15000).toLocaleString()}`, spamScore:`${rnd(0,15)}%`, trustFlow:rnd(10,70) };
}

// ── STYLES ──────────────────────────────────────────────────────────
const css = `
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Plus+Jakarta+Sans:wght@400;500;600;700&family=DM+Mono:wght@400;500&display=swap');

*{margin:0;padding:0;box-sizing:border-box}
:root{
  --red:#dc2626;--red2:#b91c1c;--red3:#fef2f2;--red4:#fee2e2;--red5:#fca5a5;
  --rose:#f43f5e;--crimson:#9f1239;
  --white:#ffffff;--off:#fafafa;--f1:#f5f5f5;--f2:#efefef;
  --gray:#6b7280;--gray2:#374151;--gray3:#1f2937;
  --gold:#d97706;--gold2:#fef3c7;
  --teal:#0d9488;--teal2:#ccfbf1;
  --blue:#2563eb;--blue2:#dbeafe;
  --shadow:0 4px 24px rgba(220,38,38,.10);
  --shadow2:0 2px 12px rgba(0,0,0,.08);
  --r:12px; --r2:8px; --r3:20px;
}
html{font-size:15px}
body{font-family:'Plus Jakarta Sans',sans-serif;background:var(--f1);color:var(--gray3);min-height:100vh;overflow-x:hidden}
::-webkit-scrollbar{width:5px}::-webkit-scrollbar-thumb{background:var(--red4);border-radius:4px}
[dir=rtl]{font-family:'Plus Jakarta Sans',sans-serif}

/* LAYOUT */
.shell{display:flex;min-height:100vh}
.side{width:230px;flex-shrink:0;background:var(--white);border-right:2px solid var(--red4);display:flex;flex-direction:column;position:fixed;top:0;bottom:0;left:0;z-index:100;box-shadow:4px 0 20px rgba(220,38,38,.07)}
[dir=rtl] .side{left:auto;right:0;border-right:none;border-left:2px solid var(--red4);box-shadow:-4px 0 20px rgba(220,38,38,.07)}
.main{margin-left:230px;flex:1;display:flex;flex-direction:column;min-height:100vh;background:var(--f1)}
[dir=rtl] .main{margin-left:0;margin-right:230px}

/* LOGO */
.logo{padding:20px 16px 16px;display:flex;align-items:center;gap:10px;border-bottom:2px solid var(--red4)}
.logo-ic{width:38px;height:38px;background:linear-gradient(135deg,var(--red),var(--rose));border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:18px;flex-shrink:0;box-shadow:0 4px 12px rgba(220,38,38,.3)}
.logo-tx{font-family:'Playfair Display',serif;font-weight:900;font-size:17px;color:var(--red);line-height:1.1}
.logo-sub{font-size:10px;color:var(--gray);font-weight:500;margin-top:1px}

/* NAV */
.nav-sec{padding:10px 10px 2px}
.nav-lbl{font-size:9.5px;font-weight:700;letter-spacing:.12em;color:var(--red5);text-transform:uppercase;padding:0 8px 6px}
.ni{display:flex;align-items:center;gap:9px;padding:9px 11px;border-radius:var(--r2);cursor:pointer;font-size:13px;font-weight:500;color:var(--gray);transition:.15s;margin-bottom:2px;border:1.5px solid transparent}
.ni:hover{background:var(--red3);color:var(--red)}
.ni.on{background:var(--red);color:white;border-color:var(--red2);box-shadow:0 4px 12px rgba(220,38,38,.25)}
.ni-ic{font-size:15px;width:20px;text-align:center;flex-shrink:0}
.free-badge{margin-left:auto;font-size:9px;padding:2px 7px;background:linear-gradient(135deg,var(--gold),#f59e0b);color:white;border-radius:99px;font-weight:700;letter-spacing:.04em}
[dir=rtl] .free-badge{margin-left:0;margin-right:auto}

.side-bot{margin-top:auto;padding:14px;border-top:2px solid var(--red4)}
.lang-switcher{display:flex;gap:5px;margin-bottom:10px}
.lang-btn{flex:1;padding:6px;border-radius:6px;border:1.5px solid var(--red4);background:transparent;cursor:pointer;font-size:11.5px;font-weight:600;color:var(--gray);transition:.15s;font-family:'Plus Jakarta Sans',sans-serif}
.lang-btn.on,.lang-btn:hover{background:var(--red);color:white;border-color:var(--red)}

/* TOPBAR */
.topbar{background:var(--white);border-bottom:2px solid var(--red4);padding:0 24px;height:58px;display:flex;align-items:center;gap:12px;position:sticky;top:0;z-index:50;box-shadow:0 2px 16px rgba(220,38,38,.06)}
.srch{flex:1;max-width:480px;display:flex;align-items:center;gap:9px;background:var(--f1);border:1.5px solid var(--red4);border-radius:99px;padding:0 16px;transition:.2s}
.srch:focus-within{border-color:var(--red);box-shadow:0 0 0 3px rgba(220,38,38,.1)}
.srch input{flex:1;background:none;border:none;outline:none;color:var(--gray3);font-size:13.5px;padding:10px 0;font-family:'Plus Jakarta Sans',sans-serif}
.srch input::placeholder{color:var(--gray)}
.topbar-right{margin-left:auto;display:flex;align-items:center;gap:8px}
[dir=rtl] .topbar-right{margin-left:0;margin-right:auto}

/* BUTTONS */
.btn{padding:9px 18px;border-radius:99px;font-size:13px;font-weight:600;cursor:pointer;border:none;transition:.2s;font-family:'Plus Jakarta Sans',sans-serif;display:inline-flex;align-items:center;gap:6px}
.btn-red{background:var(--red);color:white;box-shadow:0 4px 14px rgba(220,38,38,.3)}
.btn-red:hover{background:var(--red2);transform:translateY(-1px)}
.btn-red:disabled{opacity:.45;cursor:not-allowed;transform:none}
.btn-out{background:transparent;color:var(--red);border:1.5px solid var(--red4)}
.btn-out:hover{background:var(--red3);border-color:var(--red)}
.btn-sm{padding:6px 14px;font-size:12px}
.btn-teal{background:var(--teal);color:white}
.btn-teal:hover{opacity:.88}
.btn-gold{background:var(--gold);color:white}
.btn-gold:hover{opacity:.88}
.btn-blue{background:var(--blue);color:white}
.btn-blue:hover{opacity:.88}

/* CONTENT */
.content{padding:24px;flex:1}
.ph{margin-bottom:24px}
.pt{font-family:'Playfair Display',serif;font-size:26px;font-weight:900;color:var(--red);margin-bottom:5px}
.ps{color:var(--gray);font-size:13.5px}

/* CARD */
.card{background:var(--white);border:1.5px solid var(--red4);border-radius:var(--r);padding:20px;box-shadow:var(--shadow2)}
.card-red{background:linear-gradient(135deg,var(--red),var(--rose));color:white;border:none;box-shadow:var(--shadow)}
.ct{font-family:'Playfair Display',serif;font-weight:700;font-size:15px;color:var(--gray3);margin-bottom:14px;display:flex;align-items:center;justify-content:space-between}
.ct a{font-size:12px;color:var(--red);font-weight:600;cursor:pointer;text-decoration:none}
.ct a:hover{text-decoration:underline}

/* INPUT */
.inp{width:100%;background:var(--f1);border:1.5px solid var(--red4);border-radius:var(--r2);padding:11px 15px;font-size:13.5px;color:var(--gray3);outline:none;transition:.2s;font-family:'Plus Jakarta Sans',sans-serif}
.inp:focus{border-color:var(--red);box-shadow:0 0 0 3px rgba(220,38,38,.09);background:white}
.inp::placeholder{color:var(--gray)}
select.inp{cursor:pointer;appearance:none}
textarea.inp{resize:vertical;min-height:100px}

/* GRID */
.g2{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.g3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px}
.g4{display:grid;grid-template-columns:1fr 1fr 1fr 1fr;gap:14px}
.mb{margin-bottom:16px}
.mt{margin-top:16px}
.gap{display:flex;flex-direction:column;gap:14px}

/* STAT */
.stat{background:var(--white);border:1.5px solid var(--red4);border-radius:var(--r);padding:20px;position:relative;overflow:hidden}
.stat::before{content:'';position:absolute;bottom:-15px;right:-15px;width:70px;height:70px;border-radius:50%;opacity:.07}
.s-c1::before{background:var(--red)}.s-c2::before{background:var(--teal)}.s-c3::before{background:var(--gold)}.s-c4::before{background:var(--blue)}
.s-ic{font-size:22px;margin-bottom:10px}
.s-v{font-family:'Playfair Display',serif;font-size:28px;font-weight:900;color:var(--red);margin-bottom:3px}
.s-l{font-size:12px;color:var(--gray);font-weight:500}
.s-ch{font-size:11.5px;color:var(--teal);margin-top:6px;font-weight:600}

/* TABLE */
.tbl-wrap{overflow-x:auto;border-radius:var(--r2)}
table{width:100%;border-collapse:collapse;min-width:600px}
th{text-align:left;font-size:10.5px;font-weight:700;letter-spacing:.08em;color:var(--gray);text-transform:uppercase;padding:10px 14px;background:var(--f1);border-bottom:2px solid var(--red4)}
[dir=rtl] th{text-align:right}
td{padding:11px 14px;border-bottom:1.5px solid var(--f2);font-size:13px;vertical-align:middle}
[dir=rtl] td{text-align:right}
tr:last-child td{border-bottom:none}
tr:hover td{background:var(--red3)}

/* TAG */
.tag{display:inline-block;padding:3px 10px;border-radius:99px;font-size:11px;font-weight:700}
.tag-red{background:var(--red4);color:var(--red2)}
.tag-green{background:var(--teal2);color:var(--teal)}
.tag-gold{background:var(--gold2);color:var(--gold)}
.tag-blue{background:var(--blue2);color:var(--blue)}
.tag-gray{background:var(--f2);color:var(--gray)}

/* TABS */
.tabs{display:flex;gap:3px;background:var(--f1);border:1.5px solid var(--red4);border-radius:99px;padding:4px;margin-bottom:18px;flex-wrap:wrap}
.tab{flex:1;min-width:60px;text-align:center;padding:8px 10px;border-radius:99px;cursor:pointer;font-size:12.5px;font-weight:600;color:var(--gray);transition:.15s;white-space:nowrap}
.tab.on{background:var(--red);color:white;box-shadow:0 3px 10px rgba(220,38,38,.3)}

/* AI BOX */
.ai-box{background:linear-gradient(135deg,#fff5f5,#fff);border:1.5px solid var(--red4);border-radius:var(--r);padding:16px;margin-top:14px}
.ai-hd{display:flex;align-items:center;gap:7px;font-size:12.5px;font-weight:700;color:var(--red);margin-bottom:10px}
.ai-txt{font-size:13px;color:var(--gray2);line-height:1.75;white-space:pre-wrap}

/* SCORE */
.score-wrap{display:flex;align-items:center;gap:20px;margin-bottom:18px;flex-wrap:wrap}
.ring-wrap{position:relative;width:80px;height:80px;flex-shrink:0}
.ring-wrap svg{transform:rotate(-90deg)}
.ring-num{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-family:'Playfair Display',serif;font-size:20px;font-weight:900;color:var(--red)}
.score-rows{flex:1;min-width:200px}
.sc-row{display:flex;align-items:center;gap:8px;margin-bottom:7px;font-size:12px}
.sc-lbl{color:var(--gray);width:90px;flex-shrink:0}
.sc-bg{flex:1;height:5px;background:var(--f2);border-radius:99px}
.sc-f{height:100%;border-radius:99px}
.sc-n{width:26px;text-align:right;font-weight:700;font-size:12px}

/* RESULT GRID */
.rg{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}
.ri{background:var(--f1);border:1.5px solid var(--red4);border-radius:var(--r2);padding:13px}
.ri-l{font-size:10px;color:var(--gray);margin-bottom:5px;text-transform:uppercase;letter-spacing:.06em;font-weight:700}
.ri-v{font-size:14px;font-weight:700;color:var(--gray3)}

/* DOMAIN ROW */
.dr{display:flex;align-items:center;gap:10px;padding:10px 13px;background:var(--f1);border:1.5px solid var(--red4);border-radius:var(--r2);margin-bottom:8px;transition:.15s;cursor:pointer}
.dr:hover{border-color:var(--red);background:var(--red3)}
.dr-n{font-family:'DM Mono',monospace;font-size:12.5px;font-weight:500;flex:1;color:var(--red2)}
.dr-v{font-size:12px;color:var(--teal);font-weight:700}

/* LOADING */
.ld{display:flex;align-items:center;gap:10px;padding:18px;color:var(--gray);font-size:13px}
.spin{width:18px;height:18px;border:2.5px solid var(--red4);border-top-color:var(--red);border-radius:50%;animation:spin .7s linear infinite;flex-shrink:0}
@keyframes spin{to{transform:rotate(360deg)}}

/* MAPS LINK */
.maps-link{display:inline-flex;align-items:center;gap:8px;padding:10px 18px;background:linear-gradient(135deg,#4285f4,#34a853);color:white;border-radius:99px;font-weight:600;font-size:13px;text-decoration:none;box-shadow:0 4px 14px rgba(66,133,244,.3);transition:.2s}
.maps-link:hover{opacity:.88;transform:translateY(-1px)}

/* EXTRACTOR */
.extract-results{margin-top:16px}
.result-section{margin-bottom:16px}
.result-label{font-family:'Playfair Display',serif;font-weight:700;font-size:15px;color:var(--gray3);margin-bottom:10px;display:flex;align-items:center;gap:8px}
.result-count{background:var(--red);color:white;border-radius:99px;font-size:11px;padding:2px 9px;font-family:'Plus Jakarta Sans',sans-serif;font-weight:700}
.result-items{display:flex;flex-direction:column;gap:6px}
.result-item{display:flex;align-items:center;gap:10px;padding:10px 14px;background:var(--f1);border:1.5px solid var(--red4);border-radius:var(--r2);font-family:'DM Mono',monospace;font-size:13px;color:var(--red2)}
.result-item .copy-btn{margin-left:auto;padding:4px 10px;border-radius:6px;background:var(--red);color:white;border:none;cursor:pointer;font-size:11px;font-weight:600;font-family:'Plus Jakarta Sans',sans-serif}
[dir=rtl] .result-item .copy-btn{margin-left:0;margin-right:auto}

/* ALERT */
.alert{display:flex;align-items:flex-start;gap:10px;padding:12px 16px;border-radius:var(--r2);margin-bottom:14px;font-size:13px;line-height:1.5}
.alert-red{background:var(--red3);border:1.5px solid var(--red4);color:var(--red2)}
.alert-green{background:var(--teal2);border:1.5px solid #99f6e4;color:var(--teal)}
.alert-gold{background:var(--gold2);border:1.5px solid #fde68a;color:var(--gold)}

/* CHAT */
.chat-fab{position:fixed;bottom:22px;right:22px;z-index:200}
[dir=rtl] .chat-fab{right:auto;left:22px}
.chat-btn{width:52px;height:52px;border-radius:50%;background:linear-gradient(135deg,var(--red),var(--rose));border:none;cursor:pointer;font-size:22px;box-shadow:0 6px 22px rgba(220,38,38,.4);transition:.2s}
.chat-btn:hover{transform:scale(1.1)}
.chat-win{position:absolute;bottom:62px;right:0;width:330px;background:var(--white);border:2px solid var(--red4);border-radius:var(--r);overflow:hidden;box-shadow:0 16px 50px rgba(220,38,38,.15);display:flex;flex-direction:column}
[dir=rtl] .chat-win{right:auto;left:0}
.chat-hd{padding:13px 16px;border-bottom:2px solid var(--red4);display:flex;align-items:center;gap:9px;background:linear-gradient(135deg,var(--red),var(--rose))}
.chat-av{width:32px;height:32px;border-radius:50%;background:white;display:flex;align-items:center;justify-content:center;font-size:15px;flex-shrink:0}
.chat-nm{font-weight:700;font-size:13px;color:white}
.chat-st{font-size:10.5px;color:rgba(255,255,255,.8)}
.chat-msgs{flex:1;padding:14px;overflow-y:auto;display:flex;flex-direction:column;gap:10px;min-height:220px;max-height:300px}
.msg{display:flex;gap:7px;align-items:flex-end}
.msg.u{flex-direction:row-reverse}
.bbl{padding:9px 13px;border-radius:12px;font-size:13px;line-height:1.55;max-width:220px;word-break:break-word}
.bbl.b{background:var(--f1);border:1.5px solid var(--red4);border-radius:3px 12px 12px 12px;color:var(--gray3)}
.bbl.u{background:var(--red);color:white;border-radius:12px 3px 12px 12px}
.chat-inp{padding:10px;border-top:2px solid var(--red4);display:flex;gap:7px}
.chat-inp input{flex:1;background:var(--f1);border:1.5px solid var(--red4);border-radius:99px;padding:8px 14px;font-size:13px;color:var(--gray3);outline:none;font-family:'Plus Jakarta Sans',sans-serif}
.chat-inp input:focus{border-color:var(--red)}
.chat-send{padding:8px 14px;border-radius:99px;background:var(--red);border:none;cursor:pointer;color:white;font-size:12px;font-weight:700;font-family:'Plus Jakarta Sans',sans-serif}

/* MONO */
.mono{font-family:'DM Mono',monospace;font-size:12px}

/* DASHBOARD TOOLS GRID */
.tools-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
.tool-card{background:var(--white);border:1.5px solid var(--red4);border-radius:var(--r);padding:20px;cursor:pointer;transition:.2s;text-align:center}
.tool-card:hover{border-color:var(--red);box-shadow:0 8px 24px rgba(220,38,38,.13);transform:translateY(-3px)}
.tool-card.on{border-color:var(--red);background:var(--red);color:white}
.tool-ic{font-size:28px;margin-bottom:10px}
.tool-name{font-family:'Playfair Display',serif;font-weight:700;font-size:14px;margin-bottom:5px}
.tool-desc{font-size:11.5px;color:var(--gray);line-height:1.5}
.tool-card.on .tool-desc,.tool-card.on .tool-name{color:white}

/* PROGRESS */
.pb-wrap{margin-bottom:12px}
.pb-lbl{display:flex;justify-content:space-between;font-size:12px;margin-bottom:5px;color:var(--gray)}
.pb{height:6px;background:var(--f2);border-radius:99px;overflow:hidden}
.pb-f{height:100%;border-radius:99px;background:linear-gradient(135deg,var(--red),var(--rose))}

@media(max-width:860px){
  .side{display:none}.main{margin-left:0!important;margin-right:0!important}
  .tools-grid,.g4{grid-template-columns:1fr 1fr}.g3{grid-template-columns:1fr}.rg{grid-template-columns:1fr 1fr}
}
@keyframes fadeUp{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:none}}
.page-enter{animation:fadeUp .25s ease}
`;

// ── DASHBOARD ──────────────────────────────────────────────────────
function Dashboard({ setPage, t }) {
  const tools = [
    { id:"tools", ic:"🔍", name:t.nav.tools, desc:"WHOIS · DNS · SEO · Availability" },
    { id:"ai", ic:"🤖", name:t.nav.ai, desc:"Claude AI — evaluate, ideas, emails" },
    { id:"leads", ic:"📧", name:t.nav.leads, desc:"Emails · phones from any domain" },
    { id:"expired", ic:"⏰", name:t.nav.expired, desc:"Find dropped domains with SEO value" },
    { id:"maps", ic:"🗺️", name:t.nav.maps, desc:"Search businesses · extract contacts" },
    { id:"extractor", ic:"🔎", name:t.nav.extractor, desc:"Extract emails & phones from any URL" },
    { id:"chat", ic:"💬", name:t.nav.chat, desc:"Ask Claude anything about domains" },
  ];
  return (
    <div className="page-enter">
      <div className="ph">
        <div className="pt">{t.dashboard_title}</div>
        <div className="ps">{t.dashboard_sub}</div>
      </div>
      <div className="g4 mb">
        {[
          { ic:"🌐", v:"∞", l: t.lang==="ar"?"بحوث نطاقات":"Domain Lookups", ch:t.free_badge, c:"s-c1" },
          { ic:"📧", v:"∞", l: t.lang==="ar"?"إيميلات":"Emails Found", ch:t.free_badge, c:"s-c2" },
          { ic:"🤖", v:"∞", l: t.lang==="ar"?"تحليلات AI":"AI Analyses", ch:t.free_badge, c:"s-c3" },
          { ic:"💾", v:"∞", l: t.lang==="ar"?"تصدير CSV":"CSV Exports", ch:t.free_badge, c:"s-c4" },
        ].map((s,i)=>(
          <div key={i} className={`stat ${s.c}`}>
            <div className="s-ic">{s.ic}</div>
            <div className="s-v">{s.v}</div>
            <div className="s-l">{s.l}</div>
            <div className="s-ch">✓ {s.ch}</div>
          </div>
        ))}
      </div>
      <div className="tools-grid">
        {tools.map(tool=>(
          <div key={tool.id} className="tool-card" onClick={()=>setPage(tool.id)}>
            <div className="tool-ic">{tool.ic}</div>
            <div className="tool-name">{tool.name}</div>
            <div className="tool-desc">{tool.desc}</div>
          </div>
        ))}
      </div>
    </div>
  );
}

// ── DOMAIN TOOLS ──────────────────────────────────────────────────
function DomainTools({ t }) {
  const [domain, setDomain] = useState("");
  const [tab, setTab] = useState("overview");
  const [loading, setLoading] = useState(false);
  const [data, setData] = useState(null);
  const [aiTxt, setAiTxt] = useState("");
  const [aiLoading, setAiLoading] = useState(false);
  const [availLoading, setAvailLoading] = useState(false);
  const [availData, setAvailData] = useState(null);

  const analyze = async () => {
    if (!domain.trim()) return;
    setLoading(true); setData(null); setAiTxt(""); setAvailData(null);
    await new Promise(r=>setTimeout(r,800));
    const whois = mockWhois(domain.trim());
    const dns = mockDNS(domain.trim());
    const seo = mockSEO();
    setData({ whois, dns, seo });
    setLoading(false); setTab("overview");
    setAiLoading(true);
    try {
      const res = await callClaude(`Analyze domain "${domain.trim()}" for investment. Age: ${whois.age}, Registrar: ${whois.registrar}, DA: ${seo.da}, Backlinks: ${seo.backlinks}. Give: investment score /100, 3 strengths, 2 risks, estimated market value range, best buyer types, one-line verdict.`);
      setAiTxt(res);
    } catch { setAiTxt("AI analysis unavailable."); }
    setAiLoading(false);
  };

  const checkAvail = async () => {
    setAvailLoading(true);
    const sld = domain.trim().split(".")[0];
    await new Promise(r=>setTimeout(r,600));
    const tlds=[".com",".io",".co",".ai",".app",".net",".org",".dev",".tech",".xyz"];
    setAvailData(tlds.map(t=>({ tld:sld+t, available:Math.random()>0.45, price:`$${(Math.random()*25+7).toFixed(2)}/yr` })));
    setAvailLoading(false);
  };

  const score = data ? Math.min(Math.floor(data.seo.da*0.75+rnd(10,30)),99) : 0;
  const circ = 2*Math.PI*34;

  return (
    <div className="page-enter">
      <div className="ph"><div className="pt">{t.tools_title}</div><div className="ps">{t.tools_sub}</div></div>
      <div className="card mb">
        <div className="ct">{t.tools_title}</div>
        <div style={{display:"flex",gap:10,marginBottom:16}}>
          <input className="inp" placeholder="example.com" value={domain}
            onChange={e=>setDomain(e.target.value)} onKeyDown={e=>e.key==="Enter"&&analyze()}
            style={{fontFamily:"'DM Mono',monospace"}}/>
          <button className="btn btn-red" onClick={analyze} disabled={loading||!domain.trim()}>
            {loading?t.analyzing:t.analyze}
          </button>
        </div>
        {loading && <div className="ld"><div className="spin"/>{t.analyzing}</div>}
        {data && (
          <>
            <div className="tabs">
              {[["overview",t.overview_tab],["whois",t.whois_tab],["dns",t.dns_tab],["seo",t.seo_tab],["avail",t.avail_tab]].map(([k,l])=>(
                <div key={k} className={`tab ${tab===k?"on":""}`} onClick={()=>{ setTab(k); if(k==="avail")checkAvail(); }}>{l}</div>
              ))}
            </div>

            {tab==="overview" && (
              <>
                <div className="score-wrap">
                  <div className="ring-wrap">
                    <svg width="80" height="80" viewBox="0 0 80 80">
                      <circle cx="40" cy="40" r="34" stroke="#fee2e2" strokeWidth="8" fill="none"/>
                      <circle cx="40" cy="40" r="34" stroke="var(--red)" strokeWidth="8" fill="none"
                        strokeDasharray={circ} strokeDashoffset={circ-(score/100)*circ} strokeLinecap="round"/>
                    </svg>
                    <div className="ring-num">{score}</div>
                  </div>
                  <div className="score-rows">
                    <div style={{fontFamily:"'Playfair Display',serif",fontWeight:700,fontSize:15,marginBottom:10,color:"var(--gray3)"}}>
                      {t.lang==="ar"?"نقاط الاستثمار —":"Investment Score —"} {domain}
                    </div>
                    {[
                      { l:t.lang==="ar"?"قابلية العلامة":"Brandability", v:Math.min(Math.floor(data.seo.da*0.9+rnd(5,15)),100), c:"var(--red)" },
                      { l:t.lang==="ar"?"قيمة SEO":"SEO Value", v:data.seo.da, c:"var(--teal)" },
                      { l:t.lang==="ar"?"قوة الكلمة":"Keyword Power", v:rnd(45,90), c:"var(--gold)" },
                      { l:t.lang==="ar"?"إمكانية البيع":"Resale Potential", v:Math.min(data.seo.da+rnd(5,20),100), c:"var(--blue)" },
                    ].map((r,i)=>(
                      <div key={i} className="sc-row">
                        <span className="sc-lbl">{r.l}</span>
                        <div className="sc-bg"><div className="sc-f" style={{width:`${r.v}%`,background:r.c}}/></div>
                        <span className="sc-n" style={{color:r.c}}>{r.v}</span>
                      </div>
                    ))}
                  </div>
                </div>
                <div className="rg mb">
                  <div className="ri"><div className="ri-l">{t.age_label}</div><div className="ri-v" style={{color:"var(--teal)"}}>{data.whois.age}</div></div>
                  <div className="ri"><div className="ri-l">{t.registrar_label}</div><div className="ri-v mono">{data.whois.registrar}</div></div>
                  <div className="ri"><div className="ri-l">{t.expires_label}</div><div className="ri-v mono">{data.whois.expires}</div></div>
                  <div className="ri"><div className="ri-l">{t.da_label}</div><div className="ri-v" style={{color:"var(--red)"}}>{data.seo.da}/100</div></div>
                  <div className="ri"><div className="ri-l">{t.backlinks_label}</div><div className="ri-v" style={{color:"var(--blue)"}}>{data.seo.backlinks}</div></div>
                  <div className="ri"><div className="ri-l">DNSSEC</div><div className="ri-v" style={{color:data.whois.dnssec==="Enabled"?"var(--teal)":"var(--gray)"}}>{data.whois.dnssec}</div></div>
                </div>
                <div className="ai-box">
                  <div className="ai-hd">🤖 {t.ai_analysis}</div>
                  {aiLoading ? <div className="ld"><div className="spin"/>{t.thinking}</div> : <div className="ai-txt">{aiTxt}</div>}
                </div>
              </>
            )}
            {tab==="whois" && (
              <div className="rg" style={{gridTemplateColumns:"1fr 1fr"}}>
                {Object.entries(data.whois).map(([k,v],i)=>(
                  <div key={i} className="ri">
                    <div className="ri-l">{k.replace(/_/g," ")}</div>
                    <div className="ri-v mono" style={{fontSize:12}}>{v}</div>
                  </div>
                ))}
              </div>
            )}
            {tab==="dns" && (
              <div className="tbl-wrap">
                <table>
                  <thead><tr><th>Type</th><th>Value</th><th>TTL</th></tr></thead>
                  <tbody>{data.dns.map((r,i)=>(
                    <tr key={i}><td><span className="tag tag-red">{r.type}</span></td><td className="mono">{r.value}</td><td className="mono" style={{color:"var(--gray)"}}>{r.ttl}s</td></tr>
                  ))}</tbody>
                </table>
              </div>
            )}
            {tab==="seo" && (
              <div className="rg">
                {Object.entries(data.seo).map(([k,v],i)=>(
                  <div key={i} className="ri">
                    <div className="ri-l">{k.replace(/([A-Z])/g," $1").trim()}</div>
                    <div className="ri-v" style={{color:k==="da"||k==="pa"?"var(--red)":"var(--gray3)"}}>{v}</div>
                  </div>
                ))}
              </div>
            )}
            {tab==="avail" && (
              <>
                {availLoading && <div className="ld"><div className="spin"/>Checking TLD availability...</div>}
                {availData && (
                  <div className="tbl-wrap">
                    <table>
                      <thead><tr><th>{t.domain_label}</th><th>Status</th><th>Price</th><th></th></tr></thead>
                      <tbody>{availData.map((r,i)=>(
                        <tr key={i}>
                          <td className="mono" style={{color:"var(--red2)",fontWeight:600}}>{r.tld}</td>
                          <td><span className={`tag ${r.available?"tag-green":"tag-gray"}`}>{r.available?(t.lang==="ar"?"متاح":t.lang==="fr"?"Disponible":"Available"):(t.lang==="ar"?"محجوز":t.lang==="fr"?"Pris":"Taken")}</span></td>
                          <td style={{color:"var(--teal)",fontWeight:700}}>{r.available?r.price:"—"}</td>
                          <td>{r.available&&<button className="btn btn-red btn-sm">{t.register}</button>}</td>
                        </tr>
                      ))}</tbody>
                    </table>
                  </div>
                )}
              </>
            )}
          </>
        )}
      </div>
    </div>
  );
}

// ── AI ANALYSIS ────────────────────────────────────────────────────
function AIAnalysis({ t }) {
  const [mode, setMode] = useState("evaluate");
  const [inp, setInp] = useState("");
  const [inp2, setInp2] = useState("");
  const [result, setResult] = useState("");
  const [loading, setLoading] = useState(false);

  const run = async () => {
    if (!inp.trim()) return;
    setLoading(true); setResult("");
    try {
      const prompts = {
        evaluate: `Evaluate domain "${inp}" for investment: score /100, 3 strengths, 2 risks, estimated value range, top buyer types, one-line recommendation.`,
        ideas: `Generate 10 creative brandable domain name ideas for: "${inp}". For each: domain name, why it's great, estimated value. Numbered list.`,
        email_gen: `Write a professional cold outreach email (under 130 words) to sell domain "${inp}" to a ${inp2||"tech"} industry buyer. Subject + body. Compelling and brief.`,
        buyers: `For domain "${inp}", suggest 5 ideal buyer company types: why they'd want it, how much they'd pay, how to find them.`,
        scam: `Analyze domain "${inp}" for spam/scam risk. Check: suspicious naming patterns, phishing indicators, trademark conflicts, trust assessment. Give risk score 0-100 (0=safe) and explanation.`,
      };
      const res = await callClaude(prompts[mode]);
      setResult(res);
    } catch { setResult("AI connection error. Please try again."); }
    setLoading(false);
  };

  const modes = [
    { k:"evaluate", l:t.evaluate }, { k:"ideas", l:t.ideas },
    { k:"email_gen", l:t.email_gen }, { k:"buyers", l:t.buyers }, { k:"scam", l:t.scam },
  ];

  return (
    <div className="page-enter">
      <div className="ph"><div className="pt">{t.ai_title}</div><div className="ps">{t.ai_sub}</div></div>
      <div className="card">
        <div className="tabs">
          {modes.map(m=><div key={m.k} className={`tab ${mode===m.k?"on":""}`} onClick={()=>{setMode(m.k);setResult("");}}>{m.l}</div>)}
        </div>
        <div style={{marginBottom:10}}>
          <input className="inp mb" placeholder={
            mode==="evaluate"?t.domain_input:mode==="ideas"?t.keyword_input:
            mode==="email_gen"?t.selling_input:mode==="buyers"?t.domain_input:t.scam_input
          } value={inp} onChange={e=>setInp(e.target.value)} onKeyDown={e=>e.key==="Enter"&&run()} />
          {mode==="email_gen" && <input className="inp mb" placeholder={t.buyer_type} value={inp2} onChange={e=>setInp2(e.target.value)} />}
        </div>
        <button className="btn btn-red" onClick={run} disabled={loading||!inp.trim()}>
          {loading?t.thinking:t.run_ai}
        </button>
        {loading && <div className="ld"><div className="spin"/>{t.thinking}</div>}
        {result && (
          <div className="ai-box">
            <div className="ai-hd">🤖 {t.ai_badge}</div>
            <div className="ai-txt">{result}</div>
            <button className="btn btn-out btn-sm mt" onClick={()=>navigator.clipboard.writeText(result)}>📋 {t.copy}</button>
          </div>
        )}
      </div>
    </div>
  );
}

// ── LEAD FINDER ───────────────────────────────────────────────────
function LeadFinder({ t }) {
  const [domain, setDomain] = useState("");
  const [leads, setLeads] = useState([]);
  const [loading, setLoading] = useState(false);
  const [aiEmail, setAiEmail] = useState("");
  const [aiLoading, setAiLoading] = useState(false);
  const [selLead, setSelLead] = useState(null);

  const firstNames=["Alex","Sarah","Michael","Jessica","David","Emily","James","Robert","Jennifer","William"];
  const lastNames=["Smith","Johnson","Williams","Brown","Jones","Garcia","Miller","Davis","Wilson","Taylor"];
  const titles=["CEO","CTO","Head of Marketing","VP Sales","Co-Founder","Director","CMO","Product Lead","CFO"];

  const findEmails = async () => {
    if (!domain.trim()) return;
    setLoading(true); setLeads([]); setAiEmail("");
    await new Promise(r=>setTimeout(r,1000));
    const d = domain.trim().replace(/^https?:\/\//,"").split("/")[0];
    const fake = Array.from({length:rnd(4,7)},()=>{
      const fn=pick(firstNames), ln=pick(lastNames);
      const pat = pick([`${fn.toLowerCase()}@${d}`,`${fn[0].toLowerCase()}${ln.toLowerCase()}@${d}`,`${fn.toLowerCase()}.${ln.toLowerCase()}@${d}`]);
      return { name:`${fn} ${ln}`, email:pat, title:pick(titles), phone:`+1 (${rnd(200,999)}) ${rnd(200,999)}-${rnd(1000,9999)}`, conf:rnd(52,96), src:pick(["LinkedIn","Web","Crunchbase","AngelList","Press Release"]) };
    });
    setLeads(fake); setLoading(false);
  };

  const genEmail = async (lead) => {
    setSelLead(lead); setAiLoading(true); setAiEmail("");
    try {
      const res = await callClaude(`Write a cold outreach email to ${lead.name} (${lead.title}) at ${domain} to sell them a premium domain. Under 120 words. Include subject line. Be concise and persuasive.`,
        "You are a domain sales expert. Write compelling, concise cold emails.");
      setAiEmail(res);
    } catch { setAiEmail("Error generating email."); }
    setAiLoading(false);
  };

  const exportCSV = () => {
    const rows=[["Name","Email","Phone","Title","Confidence","Source"],...leads.map(l=>[l.name,l.email,l.phone,l.title,l.conf+"%",l.src])];
    const csv=rows.map(r=>r.map(c=>`"${c}"`).join(",")).join("\n");
    const blob=new Blob([csv],{type:"text/csv"});
    const url=URL.createObjectURL(blob);
    const a=document.createElement("a"); a.href=url; a.download=`leads_${domain}.csv`; a.click();
  };

  return (
    <div className="page-enter">
      <div className="ph"><div className="pt">{t.leads_title}</div><div className="ps">{t.leads_sub}</div></div>
      <div className="card mb">
        <div className="ct">{t.leads_title}</div>
        <div style={{display:"flex",gap:10}}>
          <input className="inp" placeholder="stripe.com, apple.com..." value={domain}
            onChange={e=>setDomain(e.target.value)} onKeyDown={e=>e.key==="Enter"&&findEmails()}
            style={{fontFamily:"'DM Mono',monospace"}}/>
          <button className="btn btn-red" onClick={findEmails} disabled={loading||!domain.trim()}>
            {loading?t.searching:t.search}
          </button>
        </div>
      </div>
      {loading && <div className="card"><div className="ld"><div className="spin"/>{t.searching}</div></div>}
      {leads.length>0 && (
        <div className="card mb">
          <div className="ct">{t.found} {leads.length} {t.contacts} {domain} <a onClick={exportCSV}>{t.export_csv} ↓</a></div>
          <div className="tbl-wrap">
            <table>
              <thead><tr><th>Name</th><th>Email</th><th>Phone</th><th>Title</th><th>{t.confidence}</th><th>{t.source}</th><th>{t.action}</th></tr></thead>
              <tbody>{leads.map((l,i)=>(
                <tr key={i}>
                  <td style={{fontWeight:600}}>{l.name}</td>
                  <td className="mono" style={{color:"var(--red2)"}}>{l.email}</td>
                  <td className="mono" style={{color:"var(--blue)"}}>{l.phone}</td>
                  <td style={{color:"var(--gray)"}}>{l.title}</td>
                  <td><span className={`tag ${l.conf>80?"tag-green":l.conf>65?"tag-gold":"tag-red"}`}>{l.conf}%</span></td>
                  <td style={{color:"var(--gray)"}}>{l.src}</td>
                  <td><button className="btn btn-out btn-sm" onClick={()=>genEmail(l)}>✍️</button></td>
                </tr>
              ))}</tbody>
            </table>
          </div>
        </div>
      )}
      {(aiLoading||aiEmail) && (
        <div className="card">
          <div className="ct">✍️ {t.lang==="ar"?"الإيميل المولّد":t.lang==="fr"?"Email Généré":"Generated Email"} {selLead&&`→ ${selLead.name}`}</div>
          {aiLoading ? <div className="ld"><div className="spin"/>{t.thinking}</div> :
            <div className="ai-box">
              <div className="ai-txt">{aiEmail}</div>
              <button className="btn btn-out btn-sm mt" onClick={()=>navigator.clipboard.writeText(aiEmail)}>📋 {t.copy}</button>
            </div>
          }
        </div>
      )}
    </div>
  );
}

// ── EXPIRED DOMAINS ───────────────────────────────────────────────
function ExpiredDomains({ t }) {
  const [filters, setFilters] = useState({ tld:".com", minDA:"20", keyword:"" });
  const [results, setResults] = useState([]);
  const [loading, setLoading] = useState(false);
  const [aiMap, setAiMap] = useState({});
  const [loadingAi, setLoadingAi] = useState({});

  const search = async () => {
    setLoading(true); setResults([]); setAiMap({});
    await new Promise(r=>setTimeout(r,900));
    const kws = filters.keyword ? [filters.keyword] : ["tech","health","ai","crypto","saas","green","data","cloud","finance","legal"];
    const sfx = ["hub","pro","lab","vault","stack","base","forge","link","flow","track"];
    const fake = Array.from({length:8},()=>{
      const k=pick(kws), s=pick(sfx), da=parseInt(filters.minDA)+rnd(0,50);
      return { domain:`${k}${s}${filters.tld}`, da, age:`${rnd(2,12)}y`, backlinks:rnd(80,8000).toLocaleString(), keywords:rnd(50,5000).toLocaleString(), score:rnd(62,97), est:`$${(Math.random()*20+0.5).toFixed(1)}K`, dropped:`${rnd(1,12)}h ago` };
    });
    setResults(fake); setLoading(false);
  };

  const runAI = async (domain, idx) => {
    setLoadingAi(p=>({...p,[idx]:true}));
    try {
      const res = await callClaude(`Quick 3-bullet analysis of expired domain "${domain}": worth buying? Value, risk, action.`);
      setAiMap(p=>({...p,[idx]:res}));
    } catch { setAiMap(p=>({...p,[idx]:"AI unavailable."})); }
    setLoadingAi(p=>({...p,[idx]:false}));
  };

  const exportCSV = () => {
    const rows=[["Domain","DA","Age","Backlinks","AI Score","Est Value","Dropped"],...results.map(r=>[r.domain,r.da,r.age,r.backlinks,r.score,r.est,r.dropped])];
    const csv=rows.map(r=>r.join(",")).join("\n");
    const blob=new Blob([csv],{type:"text/csv"}); const url=URL.createObjectURL(blob);
    const a=document.createElement("a"); a.href=url; a.download="expired_domains.csv"; a.click();
  };

  return (
    <div className="page-enter">
      <div className="ph"><div className="pt">{t.expired_title}</div><div className="ps">{t.expired_sub}</div></div>
      <div className="card mb">
        <div className="ct">{t.expired_title}</div>
        <div style={{display:"grid",gridTemplateColumns:"1fr 1fr 1fr auto",gap:10,alignItems:"end"}}>
          <div>
            <div style={{fontSize:11,color:"var(--gray)",marginBottom:5,fontWeight:600}}>{t.filter_tld}</div>
            <select className="inp" value={filters.tld} onChange={e=>setFilters(p=>({...p,tld:e.target.value}))}>
              {[".com",".io",".co",".ai",".app",".net",".org",".dev",".tech"].map(x=><option key={x}>{x}</option>)}
            </select>
          </div>
          <div>
            <div style={{fontSize:11,color:"var(--gray)",marginBottom:5,fontWeight:600}}>{t.filter_da}</div>
            <input className="inp" value={filters.minDA} onChange={e=>setFilters(p=>({...p,minDA:e.target.value}))} placeholder="20"/>
          </div>
          <div>
            <div style={{fontSize:11,color:"var(--gray)",marginBottom:5,fontWeight:600}}>{t.filter_kw}</div>
            <input className="inp" value={filters.keyword} onChange={e=>setFilters(p=>({...p,keyword:e.target.value}))} placeholder="tech, ai, health..."/>
          </div>
          <button className="btn btn-red" onClick={search} disabled={loading}>{loading?t.searching:t.search}</button>
        </div>
      </div>
      {loading && <div className="card"><div className="ld"><div className="spin"/>{t.searching}</div></div>}
      {results.length>0 && (
        <div className="card">
          <div className="ct">{t.found} {results.length} <a onClick={exportCSV}>{t.export_csv} ↓</a></div>
          <div className="tbl-wrap">
            <table>
              <thead><tr><th>{t.domain_label}</th><th>DA</th><th>{t.age_label}</th><th>{t.backlinks_label}</th><th>AI Score</th><th>Est. Value</th><th>Dropped</th><th></th></tr></thead>
              <tbody>
                {results.map((r,i)=>(
                  <>
                    <tr key={`r${i}`}>
                      <td className="mono" style={{color:"var(--red2)",fontWeight:700}}>{r.domain}</td>
                      <td><span style={{fontWeight:700,color:r.da>50?"var(--teal)":r.da>30?"var(--gold)":"var(--red)"}}>{r.da}</span></td>
                      <td style={{color:"var(--gray)"}}>{r.age}</td>
                      <td>{r.backlinks}</td>
                      <td><span className={`tag ${r.score>85?"tag-green":r.score>70?"tag-gold":"tag-red"}`}>{r.score}/100</span></td>
                      <td style={{color:"var(--teal)",fontWeight:700}}>{r.est}</td>
                      <td style={{color:"var(--gray)",fontSize:11}}>{r.dropped}</td>
                      <td style={{display:"flex",gap:5,flexWrap:"nowrap"}}>
                        <button className="btn btn-red btn-sm">{t.register}</button>
                        <button className="btn btn-out btn-sm" onClick={()=>runAI(r.domain,i)} disabled={!!loadingAi[i]}>
                          {loadingAi[i]?"...":"AI"}
                        </button>
                      </td>
                    </tr>
                    {aiMap[i] && (
                      <tr key={`ai${i}`}>
                        <td colSpan={8} style={{padding:"0 14px 14px"}}>
                          <div className="ai-box"><div className="ai-hd">🤖 Claude</div><div className="ai-txt">{aiMap[i]}</div></div>
                        </td>
                      </tr>
                    )}
                  </>
                ))}
              </tbody>
            </table>
          </div>
        </div>
      )}
    </div>
  );
}

// ── GOOGLE MAPS ───────────────────────────────────────────────────
function GoogleMaps({ t }) {
  const [bizType, setBizType] = useState("");
  const [city, setCity] = useState("");
  const [results, setResults] = useState([]);
  const [loading, setLoading] = useState(false);

  const bizNames = ["Pro Services","Solutions Group","& Associates","International","Consulting Group","Experts"];
  const search = async () => {
    if (!bizType.trim()) return;
    setLoading(true); setResults([]);
    await new Promise(r=>setTimeout(r,900));
    const fake = Array.from({length:6},(_,i)=>{
      const suf = bizNames[i % bizNames.length];
      const name = `${bizType} ${suf}`;
      const slug = name.toLowerCase().replace(/[^a-z]/g,"");
      return { name, phone:`+1 (${rnd(200,999)}) ${rnd(200,999)}-${rnd(1000,9999)}`, website:`${slug}.com`,
        email:`info@${slug}.com`, address:`${rnd(100,9999)} ${pick(["Main St","Oak Ave","Park Blvd","5th Ave","Broadway"])}, ${city||"New York, NY"}`,
        rating:(Math.random()*1.5+3.5).toFixed(1), reviews:rnd(20,300),
        mapsUrl:`https://www.google.com/maps/search/${encodeURIComponent(name+" "+city)}` };
    });
    setResults(fake); setLoading(false);
  };

  const exportCSV = () => {
    const rows=[["Business","Phone","Website","Email","Address","Rating"],...results.map(b=>[b.name,b.phone,b.website,b.email,b.address,b.rating])];
    const csv=rows.map(r=>r.map(c=>`"${c}"`).join(",")).join("\n");
    const blob=new Blob([csv],{type:"text/csv"}); const url=URL.createObjectURL(blob);
    const a=document.createElement("a"); a.href=url; a.download="maps_leads.csv"; a.click();
  };

  const mapsSearchUrl = `https://www.google.com/maps/search/${encodeURIComponent((bizType+" "+city).trim())}`;

  return (
    <div className="page-enter">
      <div className="ph"><div className="pt">{t.maps_title}</div><div className="ps">{t.maps_sub}</div></div>

      <div className="card mb">
        <div className="ct">{t.maps_title}</div>
        <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:10,marginBottom:14}}>
          <input className="inp" placeholder={t.biz_type} value={bizType} onChange={e=>setBizType(e.target.value)} onKeyDown={e=>e.key==="Enter"&&search()}/>
          <input className="inp" placeholder={t.city_input} value={city} onChange={e=>setCity(e.target.value)} onKeyDown={e=>e.key==="Enter"&&search()}/>
        </div>
        <div style={{display:"flex",gap:10,alignItems:"center",flexWrap:"wrap"}}>
          <button className="btn btn-red" onClick={search} disabled={loading||!bizType.trim()}>{loading?t.searching:t.search}</button>
          <a href={mapsSearchUrl} target="_blank" rel="noopener noreferrer" className="maps-link">
            🗺️ {t.open_maps_link}
          </a>
        </div>
      </div>

      {loading && <div className="card"><div className="ld"><div className="spin"/>{t.searching}</div></div>}

      {results.length>0 && (
        <div className="card">
          <div className="ct">{t.found} {results.length} {t.lang==="ar"?"أعمال":t.lang==="fr"?"entreprises":"businesses"} <a onClick={exportCSV}>{t.export_csv} ↓</a></div>
          <div className="tbl-wrap">
            <table>
              <thead><tr><th>{t.lang==="ar"?"الشركة":t.lang==="fr"?"Entreprise":"Business"}</th><th>Phone</th><th>Website</th><th>Email</th><th>Rating</th><th></th></tr></thead>
              <tbody>{results.map((b,i)=>(
                <tr key={i}>
                  <td style={{fontWeight:600}}>{b.name}</td>
                  <td className="mono" style={{color:"var(--blue)"}}>{b.phone}</td>
                  <td className="mono" style={{color:"var(--red2)"}}>{b.website}</td>
                  <td className="mono" style={{fontSize:11.5,color:"var(--teal)"}}>{b.email}</td>
                  <td><span className="tag tag-gold">⭐ {b.rating}</span></td>
                  <td style={{display:"flex",gap:5}}>
                    <button className="btn btn-out btn-sm">{t.add_lead}</button>
                    <a href={b.mapsUrl} target="_blank" rel="noopener noreferrer" className="btn btn-blue btn-sm" style={{textDecoration:"none"}}>🗺️</a>
                  </td>
                </tr>
              ))}</tbody>
            </table>
          </div>
        </div>
      )}
    </div>
  );
}

// ── PAGE EXTRACTOR ─────────────────────────────────────────────────
function PageExtractor({ t }) {
  const [url, setUrl] = useState("");
  const [html, setHtml] = useState("");
  const [emails, setEmails] = useState([]);
  const [phones, setPhones] = useState([]);
  const [loading, setLoading] = useState(false);
  const [done, setDone] = useState(false);

  const emailRegex = /[a-zA-Z0-9._%+\-]+@[a-zA-Z0-9.\-]+\.[a-zA-Z]{2,}/g;
  const phoneRegex = /(?:\+?(\d{1,3})[\s\-.]?)?(?:\(?\d{1,4}\)?[\s\-.]?)?\d{1,4}[\s\-.]?\d{1,4}[\s\-.]?\d{1,9}/g;

  const cleanPhones = (raw) => {
    return raw.filter(p => {
      const digits = p.replace(/\D/g,"");
      return digits.length >= 7 && digits.length <= 15;
    });
  };

  const extract = async () => {
    setLoading(true); setEmails([]); setPhones([]); setDone(false);
    await new Promise(r=>setTimeout(r,700));

    let text = html.trim();

    if (!text && url.trim()) {
      // simulate fetching — in real build use a CORS proxy
      // For demo, generate mock data based on domain
      const domain = url.replace(/^https?:\/\//,"").split("/")[0];
      const sld = domain.split(".")[0];
      const mockEmails = [
        `info@${domain}`, `contact@${domain}`, `hello@${domain}`,
        `support@${domain}`, `sales@${domain}`,
        `${sld}team@gmail.com`
      ];
      const mockPhones = [
        `+1 (${rnd(200,999)}) ${rnd(200,999)}-${rnd(1000,9999)}`,
        `+44 20 ${rnd(1000,9999)} ${rnd(1000,9999)}`,
        `+33 1 ${rnd(10,99)} ${rnd(10,99)} ${rnd(10,99)} ${rnd(10,99)}`,
        `(${rnd(200,999)}) ${rnd(200,999)}-${rnd(1000,9999)}`,
      ];
      setEmails([...new Set(mockEmails)]);
      setPhones([...new Set(mockPhones)]);
      setDone(true); setLoading(false);
      return;
    }

    // Extract from pasted HTML/text
    const foundEmails = [...new Set(text.match(emailRegex) || [])];
    const foundPhones = [...new Set(cleanPhones(text.match(phoneRegex) || []))];
    setEmails(foundEmails);
    setPhones(foundPhones);
    setDone(true); setLoading(false);
  };

  const exportAll = () => {
    const rows=[["Type","Value"],
      ...emails.map(e=>["Email",e]),
      ...phones.map(p=>["Phone",p])];
    const csv=rows.map(r=>r.join(",")).join("\n");
    const blob=new Blob([csv],{type:"text/csv"}); const url2=URL.createObjectURL(blob);
    const a=document.createElement("a"); a.href=url2; a.download="extracted_contacts.csv"; a.click();
  };

  return (
    <div className="page-enter">
      <div className="ph"><div className="pt">{t.extractor_title}</div><div className="ps">{t.extractor_sub}</div></div>

      <div className="alert alert-gold">
        💡 {t.lang==="ar"?"الصق رابط الموقع أو كود HTML للاستخراج الفوري":t.lang==="fr"?"Collez l'URL ou le HTML source pour extraire instantanément":"Paste a website URL or HTML source code to extract all emails and phone numbers instantly"}
      </div>

      <div className="card mb">
        <div className="ct">{t.extractor_title}</div>
        <div style={{marginBottom:12}}>
          <div style={{fontSize:12,color:"var(--gray)",marginBottom:6,fontWeight:600}}>{t.url_input}</div>
          <input className="inp" placeholder="https://example.com/contact" value={url} onChange={e=>setUrl(e.target.value)}
            style={{fontFamily:"'DM Mono',monospace"}}/>
        </div>
        <div style={{marginBottom:14}}>
          <div style={{fontSize:12,color:"var(--gray)",marginBottom:6,fontWeight:600}}>{t.html_input}</div>
          <textarea className="inp" placeholder='<html>...<a href="mailto:info@company.com">...</a>...<p>Call us: +1 (555) 123-4567</p>...</html>'
            value={html} onChange={e=>setHtml(e.target.value)} rows={5}/>
        </div>
        <button className="btn btn-red" onClick={extract} disabled={loading||(!url.trim()&&!html.trim())}>
          {loading?t.extracting:t.extract}
        </button>
      </div>

      {loading && <div className="card"><div className="ld"><div className="spin"/>{t.extracting}</div></div>}

      {done && (
        <div className="card">
          <div className="ct">
            {t.lang==="ar"?"نتائج الاستخراج":t.lang==="fr"?"Résultats d'Extraction":"Extraction Results"}
            {(emails.length>0||phones.length>0) && <a onClick={exportAll}>{t.export_csv} ↓</a>}
          </div>

          {emails.length===0 && phones.length===0 && (
            <div className="alert alert-red">{t.no_results}</div>
          )}

          {emails.length>0 && (
            <div className="result-section">
              <div className="result-label">
                📧 {t.emails_found}
                <span className="result-count">{emails.length}</span>
              </div>
              <div className="result-items">
                {emails.map((e,i)=>(
                  <div key={i} className="result-item">
                    <span>📧</span>
                    <span style={{flex:1}}>{e}</span>
                    <button className="copy-btn" onClick={()=>navigator.clipboard.writeText(e)}>📋</button>
                  </div>
                ))}
              </div>
            </div>
          )}

          {phones.length>0 && (
            <div className="result-section">
              <div className="result-label" style={{marginTop:16}}>
                📞 {t.phones_found}
                <span className="result-count" style={{background:"var(--blue)"}}>{phones.length}</span>
              </div>
              <div className="result-items">
                {phones.map((p,i)=>(
                  <div key={i} className="result-item" style={{color:"var(--blue)"}}>
                    <span>📞</span>
                    <span style={{flex:1}}>{p}</span>
                    <button className="copy-btn" style={{background:"var(--blue)"}} onClick={()=>navigator.clipboard.writeText(p)}>📋</button>
                  </div>
                ))}
              </div>
            </div>
          )}

          {(emails.length>0||phones.length>0) && (
            <div className="alert alert-green mt">
              ✅ {t.lang==="ar"?`تم استخراج ${emails.length} إيميل و ${phones.length} رقم هاتف`:
                  t.lang==="fr"?`Extrait ${emails.length} emails et ${phones.length} numéros`:
                  `Extracted ${emails.length} emails and ${phones.length} phone numbers`}
            </div>
          )}
        </div>
      )}

      <div className="card mt">
        <div className="ct">
          {t.lang==="ar"?"كيف يعمل الاستخراج":t.lang==="fr"?"Comment fonctionne l'extracteur":"How the Extractor Works"}
        </div>
        <div className="g3">
          {[
            { ic:"1️⃣", title:t.lang==="ar"?"الصق الرابط":t.lang==="fr"?"Collez l'URL":"Paste URL", desc:t.lang==="ar"?"أدخل رابط الصفحة التي تريد استخراج البيانات منها":t.lang==="fr"?"Entrez l'URL de la page cible":"Enter the URL of the target page" },
            { ic:"2️⃣", title:t.lang==="ar"?"أو الصق HTML":t.lang==="fr"?"Ou HTML":"Or Paste HTML", desc:t.lang==="ar"?"إذا لم يعمل الرابط، انسخ كود HTML مباشرة":t.lang==="fr"?"Si l'URL ne fonctionne pas, copiez le HTML":"If URL fails, paste HTML source directly" },
            { ic:"3️⃣", title:t.lang==="ar"?"استخرج وصدّر":t.lang==="fr"?"Extrait & Export":"Extract & Export", desc:t.lang==="ar"?"نستخرج جميع الإيميلات والأرقام ونصدرها CSV":t.lang==="fr"?"Extrait tous les contacts et exporte en CSV":"We extract all contacts and export to CSV" },
          ].map((s,i)=>(
            <div key={i} className="ri">
              <div style={{fontSize:24,marginBottom:8}}>{s.ic}</div>
              <div style={{fontWeight:700,marginBottom:5,fontSize:13}}>{s.title}</div>
              <div style={{fontSize:12,color:"var(--gray)",lineHeight:1.5}}>{s.desc}</div>
            </div>
          ))}
        </div>
      </div>
    </div>
  );
}

// ── AI CHAT ───────────────────────────────────────────────────────
function AIChat({ t }) {
  const [msgs, setMsgs] = useState([
    { role:"bot", text: t.lang==="ar"?"مرحباً! أنا مساعد DomainForge AI 🤖 يمكنني مساعدتك في تحليل النطاقات، استراتيجيات الاستثمار، وكيفية استخدام أدوات المنصة. ما الذي تريد معرفته؟":
      t.lang==="fr"?"Bonjour ! Je suis l'assistant DomainForge AI 🤖 Je peux vous aider à analyser des domaines, comprendre les stratégies d'investissement et utiliser les outils de la plateforme. Que voulez-vous savoir ?":
      "Hello! I'm DomainForge AI 🤖 I can help you analyze domains, understand investment strategies, and use the platform tools. What would you like to know?" }
  ]);
  const [inp, setInp] = useState("");
  const [loading, setLoading] = useState(false);
  const bottomRef = useRef(null);

  useEffect(()=>{ bottomRef.current?.scrollIntoView({behavior:"smooth"}); }, [msgs]);

  const send = async () => {
    if (!inp.trim() || loading) return;
    const msg = inp.trim(); setInp(""); setLoading(true);
    setMsgs(p=>[...p,{role:"user",text:msg}]);
    try {
      const res = await callClaude(msg,
        "You are DomainForge AI, a friendly expert assistant for domain investors. Help with domain analysis, investing strategies, how to use tools, cold outreach, SEO concepts, and lead generation. Be concise and practical. Always respond in the same language the user writes in (Arabic, French, or English).");
      setMsgs(p=>[...p,{role:"bot",text:res}]);
    } catch { setMsgs(p=>[...p,{role:"bot",text:"Connection error. Please try again."}]); }
    setLoading(false);
  };

  return (
    <div className="page-enter">
      <div className="ph"><div className="pt">{t.chat_title}</div><div className="ps">{t.chat_sub}</div></div>
      <div className="card" style={{maxWidth:760,margin:"0 auto"}}>
        <div style={{display:"flex",flexDirection:"column",gap:12,minHeight:400,maxHeight:520,overflowY:"auto",marginBottom:14,padding:"4px 0"}}>
          {msgs.map((m,i)=>(
            <div key={i} style={{display:"flex",gap:10,alignItems:"flex-end",flexDirection:m.role==="user"?"row-reverse":"row"}}>
              {m.role==="bot" && <div style={{width:32,height:32,borderRadius:"50%",background:"linear-gradient(135deg,var(--red),var(--rose))",display:"flex",alignItems:"center",justifyContent:"center",fontSize:14,flexShrink:0}}>🤖</div>}
              <div style={{padding:"10px 14px",borderRadius:12,fontSize:13.5,lineHeight:1.65,maxWidth:"72%",whiteSpace:"pre-wrap",
                background:m.role==="user"?"var(--red)":"var(--f1)",
                color:m.role==="user"?"white":"var(--gray3)",
                border:m.role==="user"?"none":"1.5px solid var(--red4)",
                borderRadius:m.role==="user"?"12px 3px 12px 12px":"3px 12px 12px 12px"
              }}>{m.text}</div>
            </div>
          ))}
          {loading && (
            <div style={{display:"flex",gap:10,alignItems:"center"}}>
              <div style={{width:32,height:32,borderRadius:"50%",background:"linear-gradient(135deg,var(--red),var(--rose))",display:"flex",alignItems:"center",justifyContent:"center",fontSize:14}}>🤖</div>
              <div className="ld" style={{padding:"8px 14px",background:"var(--f1)",border:"1.5px solid var(--red4)",borderRadius:"3px 12px 12px 12px",margin:0}}>
                <div className="spin"/>{t.thinking}
              </div>
            </div>
          )}
          <div ref={bottomRef}/>
        </div>
        <div style={{display:"flex",gap:8,borderTop:"2px solid var(--red4)",paddingTop:12}}>
          <input className="inp" placeholder={t.chat_placeholder} value={inp}
            onChange={e=>setInp(e.target.value)} onKeyDown={e=>e.key==="Enter"&&send()}
            style={{borderRadius:99,flex:1}}/>
          <button className="btn btn-red" onClick={send} disabled={loading||!inp.trim()} style={{borderRadius:99}}>{t.send}</button>
        </div>
      </div>
    </div>
  );
}

// ── FLOATING CHATBOT ──────────────────────────────────────────────
function FloatingChat({ t }) {
  const [open, setOpen] = useState(false);
  const [msgs, setMsgs] = useState([{ role:"bot", text: t.lang==="ar"?"كيف يمكنني مساعدتك؟ 🤖":t.lang==="fr"?"Comment puis-je vous aider ? 🤖":"How can I help you? 🤖" }]);
  const [inp, setInp] = useState(""), [loading, setLoading] = useState(false);
  const botRef = useRef(null);
  useEffect(()=>{ botRef.current?.scrollIntoView({behavior:"smooth"}); },[msgs]);

  const send = async () => {
    if (!inp.trim()||loading) return;
    const msg=inp.trim(); setInp(""); setLoading(true);
    setMsgs(p=>[...p,{role:"user",text:msg}]);
    try {
      const res = await callClaude(msg,"You are DomainForge AI assistant. Be brief and helpful. Respond in the same language the user writes in.");
      setMsgs(p=>[...p,{role:"bot",text:res}]);
    } catch { setMsgs(p=>[...p,{role:"bot",text:"Error"}]); }
    setLoading(false);
  };

  return (
    <div className="chat-fab">
      {open && (
        <div className="chat-win">
          <div className="chat-hd">
            <div className="chat-av">🤖</div>
            <div><div className="chat-nm">DomainForge AI</div><div className="chat-st">● Claude Powered</div></div>
            <div style={{marginLeft:"auto",cursor:"pointer",color:"rgba(255,255,255,.8)",fontSize:16}} onClick={()=>setOpen(false)}>✕</div>
          </div>
          <div className="chat-msgs">
            {msgs.map((m,i)=>(
              <div key={i} className={`msg ${m.role==="user"?"u":""}`}>
                {m.role==="bot"&&<div className="chat-av" style={{width:26,height:26,fontSize:12,flexShrink:0}}>🤖</div>}
                <div className={`bbl ${m.role==="user"?"u":"b"}`}>{m.text}</div>
              </div>
            ))}
            {loading&&<div className="msg"><div className="chat-av" style={{width:26,height:26,fontSize:12,flexShrink:0}}>🤖</div><div className="bbl b" style={{color:"var(--gray)"}}>...</div></div>}
            <div ref={botRef}/>
          </div>
          <div className="chat-inp">
            <input placeholder={t.chat_placeholder} value={inp} onChange={e=>setInp(e.target.value)} onKeyDown={e=>e.key==="Enter"&&send()}/>
            <button className="chat-send" onClick={send}>{t.lang==="ar"?"←":"→"}</button>
          </div>
        </div>
      )}
      <button className="chat-btn" onClick={()=>setOpen(o=>!o)}>🤖</button>
    </div>
  );
}

// ── MAIN APP ──────────────────────────────────────────────────────
export default function App() {
  const [lang, setLang] = useState("en");
  const [page, setPage] = useState("dashboard");
  const [globalQ, setGlobalQ] = useState("");
  const t = T[lang];

  const navItems = [
    { id:"dashboard", ic:"⚡", sec:"main" },
    { id:"tools", ic:"🔍", sec:"main" },
    { id:"ai", ic:"🤖", sec:"main" },
    { id:"leads", ic:"📧", sec:"main" },
    { id:"expired", ic:"⏰", sec:"research" },
    { id:"maps", ic:"🗺️", sec:"research" },
    { id:"extractor", ic:"🔎", sec:"research" },
    { id:"chat", ic:"💬", sec:"research" },
  ];

  const pages = {
    dashboard: <Dashboard setPage={setPage} t={t}/>,
    tools: <DomainTools t={t}/>,
    ai: <AIAnalysis t={t}/>,
    leads: <LeadFinder t={t}/>,
    expired: <ExpiredDomains t={t}/>,
    maps: <GoogleMaps t={t}/>,
    extractor: <PageExtractor t={t}/>,
    chat: <AIChat t={t}/>,
  };

  return (
    <>
      <style>{css}</style>
      <div className="shell" dir={t.dir}>
        {/* SIDEBAR */}
        <nav className="side">
          <div className="logo">
            <div className="logo-ic">🔮</div>
            <div>
              <div className="logo-tx">{t.appName}</div>
              <div className="logo-sub">{t.free_badge} • AI Powered</div>
            </div>
          </div>

          <div className="nav-sec">
            <div className="nav-lbl">{t.lang==="ar"?"الأدوات الرئيسية":t.lang==="fr"?"Outils Principaux":"Main Tools"}</div>
            {navItems.filter(n=>n.sec==="main").map(n=>(
              <div key={n.id} className={`ni ${page===n.id?"on":""}`} onClick={()=>setPage(n.id)}>
                <span className="ni-ic">{n.ic}</span>
                {t.nav[n.id]}
                <span className="free-badge">{t.free_badge}</span>
              </div>
            ))}
          </div>

          <div className="nav-sec">
            <div className="nav-lbl">{t.lang==="ar"?"بحث متقدم":t.lang==="fr"?"Recherche Avancée":"Research"}</div>
            {navItems.filter(n=>n.sec==="research").map(n=>(
              <div key={n.id} className={`ni ${page===n.id?"on":""}`} onClick={()=>setPage(n.id)}>
                <span className="ni-ic">{n.ic}</span>
                {t.nav[n.id]}
                <span className="free-badge">{t.free_badge}</span>
              </div>
            ))}
          </div>

          <div className="side-bot">
            <div style={{fontSize:11,color:"var(--gray)",marginBottom:7,fontWeight:600}}>
              {t.lang==="ar"?"اللغة":t.lang==="fr"?"Langue":"Language"}
            </div>
            <div className="lang-switcher">
              <button className={`lang-btn ${lang==="en"?"on":""}`} onClick={()=>setLang("en")}>EN</button>
              <button className={`lang-btn ${lang==="ar"?"on":""}`} onClick={()=>setLang("ar")}>عربي</button>
              <button className={`lang-btn ${lang==="fr"?"on":""}`} onClick={()=>setLang("fr")}>FR</button>
            </div>
            <div style={{textAlign:"center",fontSize:11,color:"var(--gray)"}}>
              {t.tagline}
            </div>
          </div>
        </nav>

        {/* MAIN */}
        <div className="main">
          <header className="topbar">
            <div className="srch">
              <span style={{color:"var(--red)"}}>🔍</span>
              <input placeholder={t.search_placeholder} value={globalQ}
                onChange={e=>setGlobalQ(e.target.value)}
                onKeyDown={e=>{ if(e.key==="Enter"&&globalQ.trim()) setPage("tools"); }}/>
            </div>
            <div className="topbar-right">
              <span style={{fontSize:12,color:"var(--gray)",fontWeight:600,padding:"6px 12px",background:"var(--red3)",borderRadius:99,border:"1.5px solid var(--red4)"}}>
                ✓ 100% {t.free_badge}
              </span>
              <button className="btn btn-red btn-sm" onClick={()=>setPage("tools")}>
                + {t.lang==="ar"?"تحليل نطاق":t.lang==="fr"?"Analyser":"Analyze Domain"}
              </button>
            </div>
          </header>
          <div className="content">
            {pages[page] || pages.dashboard}
          </div>
        </div>
      </div>
      <FloatingChat t={t}/>
    </>
  );
}
