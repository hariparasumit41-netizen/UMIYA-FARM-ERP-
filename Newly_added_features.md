<!DOCTYPE html>
<html lang="gu">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>AGRI.TECH</title>
<style>
:root{--bg:#0d1526;--panel:#131d33;--panel2:#0f1a2e;--border:#233052;--yellow:#eab308;--text:#e7ecf5;--muted:#8b98b3;--green:#22c55e;--red:#ef4444;}
*{box-sizing:border-box;}
body{margin:0;font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;background:var(--bg);color:var(--text);padding-top:env(safe-area-inset-top,0px);}
.topbar{display:flex;align-items:center;justify-content:space-between;padding:14px 24px;border-bottom:1px solid var(--border);background:var(--panel2);position:sticky;top:0;z-index:5;}
.brand{display:flex;align-items:center;gap:10px;font-weight:700;}
.brand .logo{width:34px;height:34px;border-radius:8px;background:var(--yellow);display:flex;align-items:center;justify-content:center;font-size:18px;}
.brand small{display:block;color:var(--muted);font-weight:400;font-size:11px;}
.layout{display:flex;min-height:100vh;}
.sidebar{width:230px;background:var(--panel2);border-right:1px solid var(--border);padding:14px 10px;flex-shrink:0;overflow-y:auto;}
.sidebar h4{font-size:11px;color:var(--muted);margin:14px 8px 6px;letter-spacing:.05em;}
.nav-item{display:flex;justify-content:space-between;padding:9px 10px;border-radius:8px;font-size:14px;cursor:pointer;margin:2px 0;}
.nav-item span.gu{color:var(--muted);font-size:12px;}
.nav-item:hover{background:#1a2540;}
.nav-item.active{background:var(--yellow);color:#1a1200;font-weight:600;}
.nav-item.active span.gu{color:#3a2c00;}
.nav-item.soon{opacity:.4;cursor:default;}
main{flex:1;padding:26px 30px;max-width:100%;overflow-x:auto;}
.eyebrow{color:var(--yellow);font-size:12px;font-weight:700;letter-spacing:.05em;}
h1{margin:4px 0 2px;font-size:26px;}
.sub{color:var(--muted);font-size:13px;margin-bottom:18px;}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:14px;margin-bottom:18px;}
.grid4{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;margin-bottom:18px;}
@media(max-width:1100px){.grid4{grid-template-columns:repeat(2,1fr);}}
@media(max-width:560px){.grid4{grid-template-columns:1fr;}}
.card{background:var(--panel);border:1px solid var(--border);border-radius:12px;padding:16px;}
.card .label{color:var(--muted);font-size:13px;margin-bottom:4px;}
.card .val{font-size:22px;font-weight:700;}
.card.green .val{color:var(--green);}
.card.red .val{color:var(--red);}
.card-top{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:14px;}
.card-top .icon{width:40px;height:40px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:18px;}
.card-top .gu{color:var(--muted);font-size:11px;padding-top:8px;}
.qbtn{background:var(--panel2);color:var(--text);border:1px solid var(--border);padding:9px 16px;border-radius:8px;font-weight:600;cursor:pointer;font-size:13px;margin-right:8px;margin-bottom:8px;}
.qbtn:hover{border-color:var(--yellow);}
.chartrow{display:grid;grid-template-columns:1.4fr 1fr;gap:16px;}
.bars{display:flex;align-items:flex-end;gap:10px;height:140px;margin-top:14px;}
.bars .b{flex:1;display:flex;flex-direction:column;align-items:center;justify-content:flex-end;height:100%;}
.bars .bfill{width:100%;background:#3b82f6;border-radius:4px 4px 0 0;min-height:2px;}
.bars .blabel{color:var(--muted);font-size:11px;margin-top:6px;}
@media(max-width:900px){.chartrow{grid-template-columns:1fr;}}
.panel{background:var(--panel);border:1px solid var(--border);border-radius:12px;padding:18px;margin-bottom:16px;}
.panel-head{display:flex;justify-content:space-between;align-items:center;margin-bottom:14px;flex-wrap:wrap;gap:8px;}
.panel-head h3{margin:0;font-size:16px;}
.btn{background:var(--yellow);color:#1a1200;border:none;padding:9px 16px;border-radius:8px;font-weight:700;cursor:pointer;font-size:13px;}
.btn.secondary{background:transparent;color:var(--muted);border:1px solid var(--border);}
table{width:100%;border-collapse:collapse;font-size:13px;}
th{text-align:left;color:var(--muted);font-weight:600;padding:8px 6px;border-bottom:1px solid var(--border);font-size:12px;white-space:nowrap;}
td{padding:10px 6px;border-bottom:1px solid var(--border);white-space:nowrap;}
tr:last-child td{border-bottom:none;}
.actions button{background:none;border:none;color:var(--muted);cursor:pointer;font-size:14px;margin-right:6px;}
.empty{color:var(--muted);font-size:13px;padding:14px 0;}
.search{width:100%;max-width:280px;background:var(--panel2);border:1px solid var(--border);color:var(--text);padding:9px 12px;border-radius:8px;font-size:13px;margin-bottom:14px;}
.modal-bg{position:fixed;inset:0;background:rgba(0,0,0,.55);display:none;align-items:center;justify-content:center;z-index:20;padding:16px;}
.modal-bg.open{display:flex;}
.modal{background:var(--panel);border:1px solid var(--border);border-radius:14px;padding:22px;width:100%;max-width:560px;max-height:90vh;overflow-y:auto;}
.modal-head{display:flex;justify-content:space-between;align-items:center;margin-bottom:16px;}
.modal-head h3{margin:0;}
.modal-head button{background:none;border:none;color:var(--muted);font-size:20px;cursor:pointer;}
.field-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;}
.field.full{grid-column:1/-1;}
.field label{display:block;font-size:13px;margin-bottom:5px;}
.field input,.field select,.field textarea{width:100%;background:var(--panel2);border:1px solid var(--border);color:var(--text);padding:9px 10px;border-radius:8px;font-size:14px;font-family:inherit;}
.field textarea{min-height:56px;resize:vertical;}
.field input:focus,.field select:focus,.field textarea:focus{outline:2px solid var(--yellow);border-color:var(--yellow);}
.hint{font-size:11px;color:var(--muted);margin-top:4px;}
.modal-foot{display:flex;justify-content:flex-end;gap:10px;margin-top:18px;}
.notice{background:#1a2a1a;border:1px solid #2f5a2f;color:#8fd98f;padding:10px 14px;border-radius:8px;font-size:13px;margin-bottom:16px;}
.foot{text-align:center;color:var(--muted);font-size:12px;padding:24px 0 8px;}
@media(max-width:760px){.sidebar{display:none;} main{padding:16px;} .field-grid{grid-template-columns:1fr;}}
</style>
</head>
<body>
<div class="topbar">
  <div class="brand"><img id="brandLogo" src="images/umiya-farm-logo.png" style="width: 60px;" alt="Umiya Farm logo"><div><span>UMIYA FARM</span></div></div>
  <div style="display:flex;align-items:center;gap:16px;color:var(--muted);font-size:14px;">
    <span id="today"></span>
    <span style="cursor:pointer;" title="Refresh" onclick="render()">🔄</span>
    <span style="cursor:pointer;" title="Theme">🌙</span>
    <span style="cursor:pointer;position:relative;" title="Notifications">🔔</span>
  </div>
</div>
<div class="layout">
  <div class="sidebar" id="sidebar"></div>
  <main id="main"></main>
</div>
<div class="modal-bg" id="modalBg">
  <div class="modal">
    <div class="modal-head"><h3 id="modalTitle">Add</h3><button onclick="closeModal()">✕</button></div>
    <div id="modalNotice"></div>
    <div class="field-grid" id="modalFields"></div>
    <div class="modal-foot">
      <button class="btn secondary" onclick="closeModal()">Cancel</button>
      <button class="btn" onclick="saveActive()">Save</button>
    </div>
  </div>
</div>

<script>
const todayISO = new Date().toISOString().slice(0,10);
const todayStr = new Date().toLocaleDateString('en-GB',{weekday:'short',day:'2-digit',month:'short',year:'numeric'});
document.getElementById('today').textContent = todayStr;

const store = k => JSON.parse(localStorage.getItem('agritech_'+k) || '[]');
const save = (k,v) => localStorage.setItem('agritech_'+k, JSON.stringify(v));
const money = n => '₹' + (Number(n)||0).toLocaleString('en-IN');
const names = k => store(k).map(r=>r.name);
const fmtK = v => v>=1000 ? (v/1000).toFixed(v%1000===0?0:1)+'k' : Math.round(v);
const niceCeil = v => { v=v||1; const p=Math.pow(10,Math.floor(Math.log10(v))); const n=v/p; const f=n<=1?1:n<=2?2:n<=5?5:10; return f*p; };
function barChartSVG(labels,series){
  const W=760,H=200,padL=34,padB=22,padT=10,padR=10;
  const innerW=W-padL-padR, innerH=H-padT-padB;
  const maxV=Math.max(1,...series.flatMap(s=>s.values)); const niceMax=niceCeil(maxV);
  const n=labels.length||1; const groupW=innerW/n; const barW=Math.min(22,groupW/(series.length+1));
  let bars='';
  labels.forEach((lab,i)=>{
    const gx=padL+i*groupW;
    series.forEach((s,si)=>{
      const v=s.values[i]||0; const h=innerH*(v/niceMax);
      const x=gx+groupW/2-(series.length*barW)/2+si*barW; const y=padT+innerH-h;
      bars+=`<rect x="${x}" y="${y}" width="${Math.max(1,barW-3)}" height="${Math.max(0,h)}" fill="${s.color}" rx="2"/>`;
    });
    bars+=`<text x="${gx+groupW/2}" y="${H-4}" font-size="10" fill="#8b98b3" text-anchor="middle">${lab}</text>`;
  });
  let grid='';
  for(let g=0;g<=4;g++){const v=niceMax*g/4; const y=padT+innerH-innerH*g/4;
    grid+=`<line x1="${padL}" y1="${y}" x2="${W-padR}" y2="${y}" stroke="#233052" stroke-dasharray="3,3"/><text x="${padL-6}" y="${y+3}" font-size="10" fill="#8b98b3" text-anchor="end">${fmtK(v)}</text>`;}
  return `<svg viewBox="0 0 ${W} ${H}" style="width:100%;height:180px;display:block;">${grid}${bars}</svg>`;
}
function lineChartSVG(labels,values,color){
  color=color||'#3b82f6';
  const W=760,H=200,padL=30,padB=22,padT=10,padR=10;
  const innerW=W-padL-padR, innerH=H-padT-padB;
  const maxV=Math.max(1,...values); const niceMax=niceCeil(maxV);
  const n=labels.length||1; const stepX=innerW/Math.max(1,n-1);
  const pts=values.map((v,i)=>[padL+i*stepX, padT+innerH-innerH*(v/niceMax)]);
  const path=pts.map((p,i)=>(i?'L':'M')+p[0].toFixed(1)+','+p[1].toFixed(1)).join(' ');
  let grid='';
  for(let g=0;g<=4;g++){const v=niceMax*g/4; const y=padT+innerH-innerH*g/4;
    grid+=`<line x1="${padL}" y1="${y}" x2="${W-padR}" y2="${y}" stroke="#233052" stroke-dasharray="3,3"/><text x="${padL-6}" y="${y+3}" font-size="10" fill="#8b98b3" text-anchor="end">${fmtK(v)}</text>`;}
  const labelsSvg=labels.map((l,i)=>`<text x="${(padL+i*stepX).toFixed(1)}" y="${H-4}" font-size="10" fill="#8b98b3" text-anchor="middle">${l}</text>`).join('');
  const dots=pts.map(p=>`<circle cx="${p[0].toFixed(1)}" cy="${p[1].toFixed(1)}" r="3" fill="${color}"/>`).join('');
  return `<svg viewBox="0 0 ${W} ${H}" style="width:100%;height:180px;display:block;">${grid}<path d="${path}" fill="none" stroke="${color}" stroke-width="2"/>${dots}${labelsSvg}</svg>`;
}
const PALETTE=['#eab308','#3b82f6','#22c55e','#ef4444','#a855f7','#f97316','#14b8a6','#ec4899'];
function pieChart(items){
  const total=items.reduce((s,i)=>s+Math.max(0,i.value),0)||1;
  let acc=0; const stops=items.map((i,idx)=>{const v=Math.max(0,i.value);const start=acc/total*360;acc+=v;const end=acc/total*360;return `${i.color||PALETTE[idx%PALETTE.length]} ${start}deg ${end}deg`;}).join(',');
  const legend=items.map((i,idx)=>`<span style="display:inline-flex;align-items:center;gap:4px;margin-right:14px;font-size:12px;color:var(--muted);"><span style="width:9px;height:9px;background:${i.color||PALETTE[idx%PALETTE.length]};display:inline-block;border-radius:2px;"></span>${i.label}</span>`).join('');
  return `<div style="display:flex;flex-direction:column;align-items:center;gap:12px;padding:14px 0;">
    <div style="width:180px;height:180px;border-radius:50%;background:conic-gradient(${stops});"></div>
    <div style="display:flex;flex-wrap:wrap;justify-content:center;">${legend}</div></div>`;
}

const M = {
  vadis:{route:'Fields / Vadi',gu:'વાડી',group:'FARM / ખેતર',eyebrow:'FIELDS',title:'Vadi / Fields Management',
    fields:[{k:'name',l:'Vadi Name',req:1},{k:'location',l:'Location'},{k:'area',l:'Total Area',t:'number',d:0},
      {k:'areaUnit',l:'Area Unit',t:'select',o:['Vigha','Acre','Bigha'],d:'Vigha'},{k:'soil',l:'Soil Type'},
      {k:'water',l:'Water Source'},{k:'notes',l:'Notes',t:'textarea'}],
    cols:[['name','Vadi Name'],['location','Location'],['area','Total Area'],['soil','Soil Type'],['water','Water Source']]},
  crops:{route:'Crop Management',gu:'પાક',group:'FARM / ખેતર',eyebrow:'CROPS',title:'Crop Management',
    fields:[{k:'name',l:'Crop Name',req:1},{k:'vadi',l:'Vadi',t:'select',o:()=>names('vadis')},
      {k:'season',l:'Season',t:'select',o:['Kharif','Rabi','Summer','Zaid']},
      {k:'status',l:'Status',t:'select',o:['Growing','Harvested','Planned'],d:'Growing'},
      {k:'sowingDate',l:'Sowing Date',t:'date'},{k:'seedName',l:'Seed Name'},
      {k:'seedQty',l:'Seed Qty',t:'number',d:0},{k:'seedCost',l:'Seed Cost',t:'number',d:0},
      {k:'area',l:'Area',t:'number',d:0},{k:'areaUnit',l:'Area Unit',t:'select',o:['Vigha','Acre','Bigha'],d:'Vigha'},
      {k:'nurseryCost',l:'Nursery Cost',t:'number',d:0},{k:'labourCost',l:'Labour Cost',t:'number',d:0},
      {k:'fertilizerCost',l:'Fertilizer Cost',t:'number',d:0},{k:'pesticideCost',l:'Pesticide Cost',t:'number',d:0},
      {k:'irrigationCost',l:'Irrigation Cost',t:'number',d:0},{k:'otherCost',l:'Other Cost',t:'number',d:0},
      {k:'expectedProd',l:'Expected Prod',t:'number',d:0},{k:'actualProd',l:'Actual Prod',t:'number',d:0},
      {k:'prodUnit',l:'Prod Unit',t:'select',o:['kg','quintal','ton'],d:'kg'},{k:'sellingRate',l:'Selling ₹/unit',t:'number',d:0},
      {k:'notes',l:'Notes',t:'textarea'}],
    cols:[['name','Crop Name'],['vadi','Vadi'],['season','Season'],['status','Status'],
      ['area','Area'],['actualProd','Actual Prod'],['sellingRate','Selling ₹/unit'],
      ['_expense','Expense'],['_revenue','Revenue'],['_profit','Profit']],
    calc:r=>{const exp=(+r.seedCost||0)+(+r.nurseryCost||0)+(+r.labourCost||0)+(+r.fertilizerCost||0)+(+r.pesticideCost||0)+(+r.irrigationCost||0)+(+r.otherCost||0);
      const rev=(+r.actualProd||0)*(+r.sellingRate||0);r._expense=money(exp);r._revenue=money(rev);r._profit=money(rev-exp);}},
  dailyEntries:{route:'Daily Entry',gu:'રોજની નોંધ',group:'DAILY OPERATIONS',eyebrow:'DAILY OPERATIONS',title:'Daily Entry',
    fields:[{k:'date',l:'Date',t:'date',req:1,d:todayISO},{k:'vadi',l:'Vadi',t:'select',o:()=>names('vadis')},
      {k:'crop',l:'Crop',t:'select',o:()=>names('crops')},
      {k:'activityType',l:'Activity Type',t:'select',o:['Sowing','Weeding','Fertilizer Application','Irrigation','Pesticide Spray','Harvesting','Other']},
      {k:'desc',l:'Description'},
      {k:'qty',l:'Quantity',t:'number',d:0},{k:'unit',l:'Unit',t:'select',o:['kg','litre','bag','piece']},
      {k:'rate',l:'Rate',t:'number',d:0},{k:'total',l:'Total Amount',t:'number',d:0},{k:'notes',l:'Notes',t:'textarea'}],
    cols:[['date','Date'],['vadi','Vadi'],['crop','Crop'],['activityType','Activity Type'],['desc','Activity'],['unit','Unit'],['rate','Rate'],['total','Total Amount']]},
  production:{route:'Production / Utaro',gu:'ઉતારો',group:'DAILY OPERATIONS',eyebrow:'PRODUCTION',title:'Production / Utaro',
    fields:[{k:'date',l:'Date',t:'date',req:1,d:todayISO},{k:'vadi',l:'Vadi',t:'select',o:()=>names('vadis')},
      {k:'crop',l:'Crop',t:'select',o:()=>names('crops'),req:1},{k:'qty',l:'Quantity',t:'number',req:1,d:0},
      {k:'unit',l:'Unit',t:'select',o:['kg','gram','quintal','ton','litre','bag','packet','piece'],d:'kg'},
      {k:'grade',l:'Grade',t:'select',o:['A','B','C']},{k:'sellingRate',l:'Selling Rate',t:'number',d:0},
      {k:'buyer',l:'Buyer'},{k:'notes',l:'Notes',t:'textarea'}],
    cols:[['date','Date'],['vadi','Vadi'],['crop','Crop'],['qty','Quantity'],['unit','Unit'],['grade','Grade'],['sellingRate','Selling Rate'],['buyer','Buyer']]},
  workers:{route:'Labour / Majur',gu:'મજૂર',group:'DAILY OPERATIONS',eyebrow:'LABOUR',title:'Labour / Majur Management',
    fields:[{k:'name',l:'Worker Name',req:1},{k:'mobile',l:'Mobile',mobile:1},{k:'address',l:'Address'},
      {k:'joinDate',l:'Joining Date',t:'date'},{k:'rate',l:'Daily Rate',t:'number',d:0},
      {k:'type',l:'Type',t:'select',o:['Daily Labour','Monthly','Contract']},
      {k:'active',l:'Active',t:'select',o:['true','false'],d:'true'},{k:'notes',l:'Notes',t:'textarea'}],
    cols:[['name','Worker Name'],['mobile','Mobile'],['type','Type'],['rate','Daily Rate'],['active','Active']],
    notice:'Mobile field accepts exactly 10 digits — extra characters are blocked automatically as you type.'},
  upads:{route:'Labour Payment',gu:'ઉપાડ',group:'DAILY OPERATIONS',eyebrow:'UPAD',title:'Upad / Advance & Payments',
    fields:[{k:'date',l:'Date',t:'date',req:1,d:todayISO},{k:'worker',l:'Worker',t:'select',o:()=>names('workers'),req:1},
      {k:'amount',l:'Amount',t:'number',req:1,d:0},{k:'reason',l:'Reason',t:'select',o:['Advance','Salary','Bonus','Other']},
      {k:'method',l:'Payment Method',t:'select',o:['Cash','Bank Transfer','UPI']},
      {k:'notes',l:'Notes',t:'textarea'}],
    cols:[['date','Date'],['worker','Worker'],['amount','Amount'],['reason','Reason'],['method','Payment Method']]},
  incomes:{route:'Income / Aavak',gu:'આવક',group:'FINANCE',eyebrow:'FINANCE',title:'Income / Aavak',
    fields:[{k:'date',l:'Date',t:'date',req:1,d:todayISO},{k:'crop',l:'Crop',t:'select',o:()=>names('crops')},
      {k:'vadi',l:'Vadi',t:'select',o:()=>names('vadis')},{k:'buyer',l:'Buyer'},
      {k:'qty',l:'Quantity',t:'number',d:0},{k:'unit',l:'Unit',t:'select',o:['kg','quintal','ton']},{k:'rate',l:'Rate',t:'number',d:0},
      {k:'total',l:'Total Amount',t:'number',d:0},{k:'status',l:'Payment Status',t:'select',o:['Paid','Pending'],d:'Paid'},
      {k:'notes',l:'Notes',t:'textarea'}],
    cols:[['date','Date'],['crop','Crop'],['vadi','Vadi'],['qty','Quantity'],['total','Total Amount'],['status','Payment Status']]},
  expenses:{route:'Expenses / Kharch',gu:'ખર્ચ',group:'FINANCE',eyebrow:'FINANCE',title:'Expenses / Kharch',
    fields:[{k:'date',l:'Date',t:'date',req:1,d:todayISO},
      {k:'category',l:'Category',t:'select',req:1,o:['Seed','Fertilizer','Pesticide','Labour','Labour Upad','Electricity','Diesel','Petrol','Tractor','Machinery','Irrigation','Transport','Repair','Rent','Farm Maintenance','Packaging','Other']},
      {k:'vadi',l:'Vadi',t:'select',o:()=>names('vadis')},{k:'crop',l:'Crop',t:'select',o:()=>names('crops')},{k:'desc',l:'Description'},
      {k:'amount',l:'Amount',t:'number',d:0},{k:'method',l:'Payment Method',t:'select',o:['Cash','Bank Transfer','UPI']},
      {k:'notes',l:'Notes',t:'textarea'}],
    cols:[['date','Date'],['category','Category'],['vadi','Vadi'],['crop','Crop'],['amount','Amount'],['method','Payment Method']]},
  seeds:{route:'Seeds',gu:'બીજ',group:'INVENTORY',eyebrow:'INVENTORY',title:'Seeds Inventory',
    fields:[{k:'name',l:'Name',req:1},{k:'crop',l:'Crop',t:'select',o:()=>names('crops')},
      {k:'qty',l:'Quantity',t:'number',d:0},{k:'unit',l:'Unit',t:'select',o:['kg','gram','packet','bag']},
      {k:'cost',l:'Cost',t:'number',d:0},{k:'purchaseDate',l:'Purchase Date',t:'date'},
      {k:'supplier',l:'Supplier'},{k:'notes',l:'Notes',t:'textarea'}],
    cols:[['name','Name'],['crop','Crop'],['qty','Quantity'],['unit','Unit'],['cost','Cost']]},
  fertilizer:{route:'Fertilizer',gu:'ખાતર',group:'INVENTORY',eyebrow:'INVENTORY',title:'Fertilizer Inventory',
    fields:[{k:'name',l:'Name',req:1},{k:'crop',l:'Crop',t:'select',o:()=>names('crops')},
      {k:'qty',l:'Quantity',t:'number',d:0},{k:'unit',l:'Unit',t:'select',o:['kg','gram','quintal','ton','litre','bag','packet','piece'],d:'kg'},
      {k:'cost',l:'Cost',t:'number',d:0},{k:'purchaseDate',l:'Purchase Date',t:'date'},
      {k:'supplier',l:'Supplier'},{k:'notes',l:'Notes',t:'textarea'}],
    cols:[['name','Name'],['crop','Crop'],['qty','Quantity'],['unit','Unit'],['cost','Cost']]},
  pesticides:{route:'Pesticides',gu:'દવા',group:'INVENTORY',eyebrow:'INVENTORY',title:'Pesticides Inventory',
    fields:[{k:'name',l:'Name',req:1},{k:'crop',l:'Crop',t:'select',o:()=>names('crops')},
      {k:'qty',l:'Quantity',t:'number',d:0},{k:'unit',l:'Unit',t:'select',o:['kg','gram','quintal','ton','litre','bag','packet','piece'],d:'kg'},
      {k:'cost',l:'Cost',t:'number',d:0},{k:'purchaseDate',l:'Purchase Date',t:'date'},
      {k:'supplier',l:'Supplier'},{k:'notes',l:'Notes',t:'textarea'}],
    cols:[['name','Name'],['crop','Crop'],['qty','Quantity'],['unit','Unit'],['cost','Cost']]}
};
const SOON = [];

let activeKey='dashboard', editIndex=null;

function buildSidebar(){
  const groups = {};
  Object.entries(M).forEach(([k,m])=>{(groups[m.group]=groups[m.group]||[]).push([k,m]);});
  let html = `<h4>DASHBOARD</h4><div class="nav-item" data-k="dashboard">Farm Dashboard <span class="gu">ડેશબોર્ડ</span></div>`;
  html += `<h4>FARM / ખેતર</h4><div class="nav-item" data-k="farmOverview">Farm Overview <span class="gu">ઝાંખી</span></div>`;
  (groups['FARM / ખેતર']||[]).forEach(([k,m])=>html+=`<div class="nav-item" data-k="${k}">${m.route} <span class="gu">${m.gu}</span></div>`);
  html += `<h4>DAILY OPERATIONS</h4>`;
  (groups['DAILY OPERATIONS']||[]).forEach(([k,m])=>html+=`<div class="nav-item" data-k="${k}">${m.route} <span class="gu">${m.gu}</span></div>`);
  html += `<h4>FINANCE</h4>`;
  (groups['FINANCE']||[]).forEach(([k,m])=>html+=`<div class="nav-item" data-k="${k}">${m.route} <span class="gu">${m.gu}</span></div>`);
  html += `<div class="nav-item" data-k="profitLoss">Profit &amp; Loss <span class="gu">નફો-નુકસાન</span></div>`;
  html += `<h4>INVENTORY</h4>`;
  (groups['INVENTORY']||[]).forEach(([k,m])=>html+=`<div class="nav-item" data-k="${k}">${m.route} <span class="gu">${m.gu}</span></div>`);
  html += `<h4>ANALYTICS</h4>
    <div class="nav-item" data-k="cropAnalysis">Crop An... <span class="gu">પાક વિશ્લેષણ</span></div>
    <div class="nav-item" data-k="productionAnalysis">Production A... <span class="gu">ઉત્પાદન</span></div>
    <div class="nav-item" data-k="yearlyReport">Yearly Report <span class="gu">વાર્ષિક</span></div>
    <h4>SETTINGS</h4>
    <div class="nav-item" data-k="settings">Settings <span class="gu">સેટિંગ્સ</span></div>`;
  SOON.forEach(s=>html+=`<div class="nav-item soon">${s}</div>`);
  document.getElementById('sidebar').innerHTML = html;
  document.querySelectorAll('.nav-item[data-k]').forEach(el=>el.addEventListener('click',()=>setActive(el.dataset.k)));
}

function setActive(k){
  activeKey=k;
  document.querySelectorAll('.nav-item').forEach(n=>n.classList.remove('active'));
  const el=[...document.querySelectorAll('.nav-item')].find(n=>n.dataset.k===k);
  if(el) el.classList.add('active');
  render();
}

function fieldHTML(f,val){
  val = val===undefined ? (f.d!==undefined?f.d:'') : val;
  const req = f.req?' *':'';
  let input;
  if(f.t==='select'){
    const opts = typeof f.o==='function'?f.o():(f.o||[]);
    input = `<select id="fx_${f.k}"><option value="">Select...</option>${opts.map(o=>`<option ${o==val?'selected':''}>${o}</option>`).join('')}</select>`;
  } else if(f.t==='textarea'){
    input = `<textarea id="fx_${f.k}">${val}</textarea>`;
  } else if(f.mobile){
    input = `<input id="fx_${f.k}" inputmode="numeric" maxlength="10" placeholder="10 digit number" value="${val}" oninput="this.value=this.value.replace(/\\D/g,'').slice(0,10)"><div class="hint">Only digits, max 10 — auto-trimmed while typing.</div>`;
  } else {
    input = `<input id="fx_${f.k}" type="${f.t||'text'}" value="${val}">`;
  }
  return `<div class="field${f.t==='textarea'?' full':''}"><label>${f.l}${req}</label>${input}</div>`;
}

function openModal(key,idx){
  editIndex = idx===undefined?null:idx;
  const m = M[key];
  document.getElementById('modalTitle').textContent = (editIndex===null?'Add ':'Edit ') + m.title.split(' /')[0];
  document.getElementById('modalNotice').innerHTML = m.notice?`<div class="notice">${m.notice}</div>`:'';
  const row = editIndex!==null ? store(key)[editIndex] : {};
  document.getElementById('modalFields').innerHTML = m.fields.map(f=>fieldHTML(f,row[f.k])).join('');
  document.getElementById('modalBg').classList.add('open');
  document.getElementById('modalBg').dataset.key = key;
}
function closeModal(){ document.getElementById('modalBg').classList.remove('open'); }

function saveActive(){
  const key = document.getElementById('modalBg').dataset.key;
  const m = M[key];
  const row = {};
  for(const f of m.fields){
    let v = document.getElementById('fx_'+f.k).value;
    if(f.mobile) v = v.replace(/\D/g,'').slice(0,10);
    if(f.req && !v){ alert(f.l+' is required'); return; }
    if(f.mobile && v && v.length!==10){ alert('Mobile must be exactly 10 digits'); return; }
    row[f.k] = v;
  }
  const rows = store(key);
  if(editIndex!==null) rows[editIndex]=row; else rows.push(row);
  save(key,rows);
  closeModal();
  render();
}
function delRow(key,i){ const rows=store(key); rows.splice(i,1); save(key,rows); render(); }

function renderModulePage(key){
  const m = M[key];
  const rows = store(key);
  if(m.calc) rows.forEach(m.calc);
  const cols = m.cols;
  document.getElementById('main').innerHTML = `
    <div class="eyebrow">${m.eyebrow}</div><h1>${m.title}</h1>
    <div class="sub">AGRI.TECH — ${todayStr}</div>
    ${m.notice?`<div class="notice">${m.notice}</div>`:''}
    <div class="panel">
      <div class="panel-head"><h3>${rows.length} records</h3><button class="btn" onclick="openModal('${key}')">+ Add</button></div>
      <input class="search" placeholder="Search ${m.route.toLowerCase()}..." oninput="filterRows(this,'${key}')">
      <table><thead><tr>${cols.map(c=>`<th>${c[1]}</th>`).join('')}<th>Actions</th></tr></thead>
      <tbody id="rows_${key}">${rowsHTML(key,rows,cols)}</tbody></table>
      ${rows.length===0?'<div class="empty">No records found</div>':''}
    </div>
    <div class="foot">© 2026 AGRI.TECH · Developed by Nirlep Kaila</div>`;
}
function rowsHTML(key,rows,cols){
  return rows.map((r,i)=>`<tr>${cols.map(c=>`<td>${r[c[0]]||'—'}</td>`).join('')}
    <td class="actions"><button onclick="openModal('${key}',${i})">✏️</button><button onclick="delRow('${key}',${i})">🗑</button></td></tr>`).join('');
}
function filterRows(input,key){
  const q=input.value.toLowerCase();
  const m=M[key]; let rows=store(key); if(m.calc) rows.forEach(m.calc);
  const filtered = rows.filter(r=>JSON.stringify(r).toLowerCase().includes(q));
  document.getElementById('rows_'+key).innerHTML = rowsHTML(key,filtered,m.cols);
}

function renderDashboard(){
  const inc=store('incomes'), exp=store('expenses'), prod=store('production'), work=store('workers');
  const todayInc = inc.filter(r=>r.date===todayISO).reduce((s,r)=>s+(+r.total||0),0);
  const todayExp = exp.filter(r=>r.date===todayISO).reduce((s,r)=>s+(+r.amount||0),0);
  const todayProd = prod.filter(r=>r.date===todayISO).reduce((s,r)=>s+(+r.qty||0),0);
  const labourCost = work.filter(w=>w.active!=='false').reduce((s,w)=>s+(+w.rate||0),0);
  const totInc = inc.reduce((s,r)=>s+(+r.total||0),0);
  const totExp = exp.reduce((s,r)=>s+(+r.amount||0),0);
  const totProd = prod.reduce((s,r)=>s+(+r.qty||0),0);

  const card=(icon,bg,gu,label,val,cls)=>`<div class="card ${cls||''}"><div class="card-top"><div class="icon" style="background:${bg}">${icon}</div><span class="gu">${gu}</span></div><div class="label">${label}</div><div class="val">${val}</div></div>`;

  // last 6 months profit
  const now=new Date(); const monthsBack=[...Array(6)].map((_,i)=>{const d=new Date(now.getFullYear(),now.getMonth()-(5-i),1);return d;});
  const barVals = monthsBack.map(d=>{
    const mi = inc.filter(r=>{const rd=new Date(r.date);return r.date && rd.getFullYear()===d.getFullYear() && rd.getMonth()===d.getMonth();}).reduce((s,r)=>s+(+r.total||0),0);
    const me = exp.filter(r=>{const rd=new Date(r.date);return r.date && rd.getFullYear()===d.getFullYear() && rd.getMonth()===d.getMonth();}).reduce((s,r)=>s+(+r.amount||0),0);
    return {label:d.toLocaleDateString('en',{month:'short'}), val:mi-me};
  });

  const byCat={}; exp.forEach(e=>{byCat[e.category||'Other']=(byCat[e.category||'Other']||0)+(+e.amount||0);});
  const growingCrops = store('crops').filter(c=>c.status==='Growing');

  document.getElementById('main').innerHTML = `
    <div class="eyebrow">EXECUTIVE OVERVIEW</div><h1>Farm Dashboard</h1>
    <div class="sub">AGRI.TECH — ${todayStr}</div>
    <div class="grid4">
      ${card('💰','#3d3410','આજની આવક',"Today's Income",money(todayInc))}
      ${card('🐷','#3d1a1a','આજનો ખર્ચ',"Today's Expenses",money(todayExp))}
      ${card('📦','#12243d','ઉત્પાદન',"Today's Production",todayProd+' kg')}
      ${card('👥','#241541','મજૂરી',"Today's Labour Cost",money(labourCost))}
      ${card('📉','#241a10','કુલ ખર્ચ',"Total Farm Expenses",money(totExp))}
      ${card('📈','#0f2e1c','કુલ આવક',"Total Farm Income",money(totInc),'green')}
      ${card('📈','#0f2e1c','નફો',"Current Profit",money(totInc-totExp),totInc-totExp<0?'red':'green')}
      ${card('🌾','#12243d','ઉતારો',"Total Production",totProd+' kg')}
    </div>
    <div style="margin-bottom:18px;">
      <button class="qbtn" onclick="openModal('production')">📦 Quick Production</button>
      <button class="qbtn" onclick="openModal('incomes')">💳 Quick Income</button>
      <button class="qbtn" onclick="openModal('expenses')">🔄 Quick Expense</button>
      <button class="qbtn" onclick="openModal('upads')">👤 Quick Upad</button>
      <button class="btn" onclick="setActive('dailyEntries')">→ Daily Entry</button>
    </div>
    <div class="chartrow">
      <div class="panel">
        <div class="panel-head"><div><h3>Monthly Profit</h3><div class="hint">Last 6 months</div></div><b style="color:var(--yellow)">${money(totInc-totExp)}</b></div>
        ${barChartSVG(barVals.map(b=>b.label),[{color:'#eab308',values:barVals.map(b=>b.val)}])}
      </div>
      <div class="panel">
        <div class="panel-head"><div><h3>Active Crops</h3><div class="hint">${growingCrops.length} growing</div></div><a href="#" onclick="setActive('crops');return false;" style="color:var(--yellow);font-size:12px;text-decoration:none;">View all</a></div>
        ${growingCrops.length?growingCrops.map(c=>`<div style="display:flex;justify-content:space-between;align-items:center;background:var(--panel2);border-radius:8px;padding:10px 14px;margin-bottom:8px;">
          <div style="display:flex;gap:10px;align-items:center;"><div style="width:34px;height:34px;border-radius:8px;background:#0f2e1c;display:flex;align-items:center;justify-content:center;">🌱</div>
          <div><b>${c.name}</b><div class="hint">${c.vadi||'—'} · ${c.area||0} ${c.areaUnit||''}</div></div></div>
          <div style="text-align:right;"><div class="hint">Selling ₹/${c.prodUnit||'kg'}</div><b>${c.sellingRate||0}</b></div>
        </div>`).join(''):'<div class="empty">No active crops</div>'}
      </div>
    </div>
    <div class="foot">© 2026 AGRI.TECH · Developed by Nirlep Kaila</div>`;
}

function renderFarmOverview(){
  const vadis=store('vadis'), crops=store('crops'), inc=store('incomes'), exp=store('expenses');
  crops.forEach(M.crops.calc);
  const growing = crops.filter(c=>c.status==='Growing');
  const now=new Date(); const monthsBack=[...Array(6)].map((_,i)=>new Date(now.getFullYear(),now.getMonth()-(5-i),1));
  const barVals = monthsBack.map(d=>{
    const mi = inc.filter(r=>{const rd=new Date(r.date);return r.date && rd.getFullYear()===d.getFullYear() && rd.getMonth()===d.getMonth();}).reduce((s,r)=>s+(+r.total||0),0);
    const me = exp.filter(r=>{const rd=new Date(r.date);return r.date && rd.getFullYear()===d.getFullYear() && rd.getMonth()===d.getMonth();}).reduce((s,r)=>s+(+r.amount||0),0);
    return {label:d.toLocaleDateString('en',{month:'short'}), val:mi-me};
  });
  const maxBar = Math.max(1,...barVals.map(b=>Math.abs(b.val)));
  const totProfit = inc.reduce((s,r)=>s+(+r.total||0),0) - exp.reduce((s,r)=>s+(+r.amount||0),0);
  document.getElementById('main').innerHTML = `
    <div class="eyebrow">FARM OVERVIEW</div><h1>Farm Overview</h1>
    <div class="sub">AGRI.TECH — ${todayStr}</div>
    <div class="grid">
      <div class="card"><div class="label">Total Vadis</div><div class="val">${vadis.length}</div></div>
      <div class="card"><div class="label">Total Area</div><div class="val">${vadis.reduce((s,v)=>s+(+v.area||0),0)}</div></div>
      <div class="card"><div class="label">Total Crops</div><div class="val">${crops.length}</div></div>
      <div class="card"><div class="label">Growing Now</div><div class="val">${growing.length}</div></div>
    </div>
    <div class="panel"><div class="panel-head"><h3>My Fields / Vadi</h3><span class="hint">Manage in Fields / Vadi</span></div>
      <div class="grid">${vadis.length? vadis.map(v=>`<div class="card"><b>${v.name}</b><div class="hint">${v.area||0} ${v.areaUnit||''} · Soil: ${v.soil||'—'}</div></div>`).join('') : '<div class="empty">No fields yet</div>'}</div>
    </div>
    <div class="chartrow">
      <div class="panel">
        <div class="panel-head"><div><h3>Monthly Profit</h3><div class="hint">Last 6 months</div></div><b style="color:var(--yellow)">${money(totProfit)}</b></div>
        <div class="bars">${barVals.map(b=>`<div class="b"><div class="bfill" style="background:var(--yellow);height:${Math.round(Math.abs(b.val)/maxBar*100)}%"></div><div class="blabel">${b.label}</div></div>`).join('')}</div>
      </div>
      <div class="panel">
        <div class="panel-head"><div><h3>Active Crops</h3><div class="hint">${growing.length} growing</div></div><a href="#" onclick="setActive('crops');return false;" style="color:var(--yellow);font-size:13px;">View all</a></div>
        ${growing.length? growing.map(c=>`<div style="display:flex;justify-content:space-between;align-items:center;background:var(--panel2);border-radius:8px;padding:10px 14px;margin-bottom:8px;">
          <div style="display:flex;gap:10px;align-items:center;"><div style="width:34px;height:34px;border-radius:8px;background:#0f2e1c;display:flex;align-items:center;justify-content:center;">🧬</div>
          <div><b>${c.name}</b><div class="hint">${c.vadi||'—'} · ${c.area||0} ${c.areaUnit||''}</div></div></div>
          <div style="text-align:right;"><div class="hint">Selling ₹/${c.prodUnit||'kg'}</div><b>${c.sellingRate||0}</b></div>
        </div>`).join('') : '<div class="empty">No active crops</div>'}
      </div>
    </div>
    <div class="foot">© 2026 AGRI.TECH · Developed by Nirlep Kaila</div>`;
}

function renderProfitLoss(){
  const inc=store('incomes'), exp=store('expenses'), crops=store('crops'), upads=store('upads');
  const totInc = inc.reduce((s,r)=>s+(+r.total||0),0);
  const totExp = exp.reduce((s,r)=>s+(+r.amount||0),0);
  const num=v=>+v||0;
  const labourCost=crops.reduce((s,c)=>s+num(c.labourCost),0);
  const seedCost=crops.reduce((s,c)=>s+num(c.seedCost),0);
  const fertCost=crops.reduce((s,c)=>s+num(c.fertilizerCost),0);
  const pestCost=crops.reduce((s,c)=>s+num(c.pesticideCost),0);
  const irrCost=crops.reduce((s,c)=>s+num(c.irrigationCost),0);
  const transportCost=exp.filter(e=>e.category==='Transport').reduce((s,e)=>s+num(e.amount),0);
  const otherExp = totExp - (labourCost+seedCost+fertCost+pestCost+irrCost+transportCost);
  const upadGiven = upads.reduce((s,u)=>s+num(u.amount),0);
  const netProfit = totInc-totExp;
  const row=(en,gu,val,neg)=>`<div style="display:flex;justify-content:space-between;padding:10px 0;border-bottom:1px solid var(--border);font-size:14px;">
    <span style="color:var(--muted);">— ${en} / <span>${gu}</span></span><b style="${neg?'color:var(--red)':''}">${money(val)}</b></div>`;
  document.getElementById('main').innerHTML = `
    <div class="eyebrow">FINANCE</div><h1>Profit &amp; Loss</h1>
    <div class="sub">AGRI.TECH — ${todayStr}</div>
    <div class="panel">
      <div class="panel-head"><h3>Profit &amp; Loss Statement</h3><div class="hint">Year ${new Date().getFullYear()}</div></div>
      <div style="display:flex;justify-content:space-between;padding:10px 0;border-bottom:1px solid var(--border);font-weight:700;">
        <span>Total Income / કુલ આવક</span><span style="color:var(--green);">${money(totInc)}</span></div>
      <div style="display:flex;justify-content:space-between;padding:10px 0;border-bottom:1px solid var(--border);font-weight:700;margin-bottom:6px;">
        <span>Total Expenses / કુલ ખર્ચ</span><span style="color:var(--red);">${money(totExp)}</span></div>
      ${row('Labour Cost','મજૂરી',labourCost)}
      ${row('Seed Cost','બીજ',seedCost)}
      ${row('Fertilizer Cost','ખાતર',fertCost)}
      ${row('Pesticide Cost','દવા',pestCost)}
      ${row('Irrigation Cost','સિંચાઈ',irrCost)}
      ${row('Transport Cost','ટ્રાન્સપોર્ટ',transportCost)}
      ${row('Other Expenses','અન્ય',otherExp,otherExp<0)}
      ${row('Upad Given','ઉપાડ',upadGiven)}
      <div style="display:flex;justify-content:space-between;padding-top:14px;font-weight:700;font-size:16px;">
        <span>NET PROFIT / નફો</span><span style="color:var(--yellow);">${money(netProfit)}</span></div>
    </div>
    <div class="foot">© 2026 AGRI.TECH · Developed by Nirlep Kaila</div>`;
}

function renderCropAnalysis(){
  const crops=store('crops'); crops.forEach(M.crops.calc);
  const num=s=>parseFloat((s||'₹0').replace(/[₹,]/g,''))||0;
  const rows=[...crops].sort((a,b)=>num(b._profit)-num(a._profit));
  const maxV=Math.max(1,...rows.flatMap(r=>[num(r._revenue),num(r._expense),Math.abs(num(r._profit))]));
  document.getElementById('main').innerHTML = `
    <div class="eyebrow">ANALYTICS</div><h1>Crop Analysis</h1>
    <div class="sub">AGRI.TECH — ${todayStr}</div>
    <div class="grid">
      <div class="card"><div class="label">Total Crops</div><div class="val">${crops.length}</div></div>
      <div class="card green"><div class="label">Total Revenue</div><div class="val">${money(rows.reduce((s,r)=>s+num(r._revenue),0))}</div></div>
      <div class="card red"><div class="label">Total Expense</div><div class="val">${money(rows.reduce((s,r)=>s+num(r._expense),0))}</div></div>
      <div class="card green"><div class="label">Most Profitable</div><div class="val" style="font-size:16px;">${rows[0]?rows[0].name:'—'}</div></div>
    </div>
    <div class="panel"><div class="panel-head"><h3>Crop-wise Comparison</h3><div class="hint">Revenue vs Expense vs Profit</div></div>
      <div style="display:flex;align-items:flex-end;gap:24px;height:160px;overflow-x:auto;padding:0 4px;">
        ${rows.length?rows.map(r=>`<div style="display:flex;flex-direction:column;align-items:center;gap:4px;height:100%;justify-content:flex-end;min-width:70px;">
          <div style="display:flex;gap:3px;align-items:flex-end;height:130px;">
            <div title="Revenue" style="width:14px;background:#3b82f6;border-radius:3px 3px 0 0;height:${Math.max(2,num(r._revenue)/maxV*130)}px;"></div>
            <div title="Expense" style="width:14px;background:#ef4444;border-radius:3px 3px 0 0;height:${Math.max(2,num(r._expense)/maxV*130)}px;"></div>
            <div title="Profit" style="width:14px;background:var(--yellow);border-radius:3px 3px 0 0;height:${Math.max(2,Math.abs(num(r._profit))/maxV*130)}px;"></div>
          </div><span class="hint">${r.name}</span></div>`).join(''):'<div class="empty">No crops yet</div>'}
      </div>
      <div style="margin-top:10px;font-size:12px;color:var(--muted);">🔵 Revenue &nbsp; 🔴 Expense &nbsp; 🟡 Profit</div>
    </div>
    <div class="panel"><div class="panel-head"><h3>Crop-wise Profit</h3><div class="hint">Profit distribution</div></div>
      ${(()=>{ const positives=rows.filter(r=>num(r._profit)>0); const totalP=positives.reduce((s,r)=>s+num(r._profit),0);
        if(!positives.length) return '<div class="empty">No profitable crops yet</div>';
        const colors=['#eab308','#3b82f6','#22c55e','#ef4444','#a855f7','#06b6d4','#f97316'];
        let acc=0; const segs=positives.map((r,i)=>{const pct=totalP?num(r._profit)/totalP*100:0; const seg=`${colors[i%colors.length]} ${acc}% ${acc+pct}%`; acc+=pct; return seg;});
        return `<div style="display:flex;align-items:center;gap:28px;flex-wrap:wrap;">
          <div style="width:180px;height:180px;border-radius:50%;background:conic-gradient(${segs.join(',')});display:flex;align-items:center;justify-content:center;">
            <div style="width:70%;height:70%;border-radius:50%;background:var(--panel);display:flex;align-items:center;justify-content:center;font-weight:700;color:var(--yellow);">${money(totalP)}</div>
          </div>
          <div>${positives.map((r,i)=>`<div style="display:flex;align-items:center;gap:8px;margin-bottom:6px;font-size:13px;"><span style="width:10px;height:10px;border-radius:2px;background:${colors[i%colors.length]};display:inline-block;"></span>${r.name}</div>`).join('')}</div>
        </div>`; })()}
    </div>
    <div class="panel"><div class="panel-head"><h3>Crop-wise Profitability</h3></div>
      <table><thead><tr><th>Crop</th><th>Vadi</th><th>Status</th><th>Expense</th><th>Revenue</th><th>Profit</th></tr></thead>
      <tbody>${rows.length?rows.map(r=>`<tr><td>${r.name}</td><td>${r.vadi||'—'}</td><td>${r.status||'—'}</td><td>${r._expense}</td><td>${r._revenue}</td><td>${r._profit}</td></tr>`).join(''):'<tr><td colspan="6" class="empty">No crops yet</td></tr>'}</tbody></table>
    </div>
    <div class="foot">© 2026 AGRI.TECH · Developed by Nirlep Kaila</div>`;
}
function renderProductionAnalysis(){
  const prod=store('production');
  const byCrop={}, byVadi={};
  prod.forEach(p=>{const c=p.crop||'Unspecified';byCrop[c]=(byCrop[c]||0)+(+p.qty||0);
    const v=p.vadi||'Unspecified';byVadi[v]=(byVadi[v]||0)+(+p.qty||0);});
  const cropRows=Object.entries(byCrop).sort((a,b)=>b[1]-a[1]);
  const vadiRows=Object.entries(byVadi).sort((a,b)=>b[1]-a[1]);
  const total=prod.reduce((s,p)=>s+(+p.qty||0),0);
  const avg = prod.length? Math.round(total/prod.length):0;
  const yr=new Date().getFullYear();
  const monthQty=[...Array(12)].map((_,i)=>prod.filter(p=>{const d=new Date(p.date);return p.date && d.getFullYear()===yr && d.getMonth()===i;}).reduce((s,p)=>s+(+p.qty||0),0));
  const maxM=Math.max(1,...monthQty);
  const pts=monthQty.map((v,i)=>`${(i/11*280).toFixed(1)},${(60-(v/maxM*55)).toFixed(1)}`).join(' ');
  const monthsLbl=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  document.getElementById('main').innerHTML = `
    <div class="eyebrow">ANALYTICS</div><h1>Production Analysis</h1>
    <div class="sub">AGRI.TECH — ${todayStr}</div>
    <div class="grid">
      <div class="card"><div class="label">Total Entries</div><div class="val">${prod.length}</div></div>
      <div class="card"><div class="label">Total Quantity</div><div class="val">${total} kg</div></div>
      <div class="card"><div class="label">Avg per Entry</div><div class="val">${avg} kg</div></div>
    </div>
    <div class="chartrow">
      <div class="panel"><div class="panel-head"><h3>Production by Crop</h3><div class="hint">kg</div></div>
        ${cropRows.length?cropRows.map(([c,v])=>`<div style="margin-bottom:10px;"><div style="display:flex;justify-content:space-between;font-size:13px;margin-bottom:4px;"><span>${c}</span><b>${v} kg</b></div><div style="background:var(--panel2);border-radius:6px;height:8px;"><div style="background:var(--yellow);height:8px;border-radius:6px;width:${total?Math.round(v/total*100):0}%;"></div></div></div>`).join(''):'<div class="empty">No production entries yet</div>'}
      </div>
      <div class="panel"><div class="panel-head"><h3>Production Trend</h3><div class="hint">Monthly kg</div></div>
        <svg viewBox="0 0 290 70" style="width:100%;height:140px;">
          <polyline points="${pts}" fill="none" stroke="#3b82f6" stroke-width="2"/>
          ${monthQty.map((v,i)=>`<circle cx="${(i/11*280).toFixed(1)}" cy="${(60-(v/maxM*55)).toFixed(1)}" r="2.5" fill="#3b82f6"/>`).join('')}
        </svg>
        <div style="display:flex;justify-content:space-between;font-size:10px;color:var(--muted);">${monthsLbl.map(m=>`<span>${m}</span>`).join('')}</div>
      </div>
    </div>
    <div class="panel"><div class="panel-head"><h3>Production by Vadi</h3><div class="hint">kg per field</div></div>
      ${vadiRows.length?vadiRows.map(([c,v])=>`<div style="margin-bottom:10px;"><div style="display:flex;justify-content:space-between;font-size:13px;margin-bottom:4px;"><span>${c}</span><b>${v} kg</b></div><div style="background:var(--panel2);border-radius:6px;height:8px;"><div style="background:#3b82f6;height:8px;border-radius:6px;width:${total?Math.round(v/total*100):0}%;"></div></div></div>`).join(''):'<div class="empty">No production entries yet</div>'}
    </div>
    <div class="foot">© 2026 AGRI.TECH · Developed by Nirlep Kaila</div>`;
}
let reportYear = new Date().getFullYear();
function renderYearlyReport(){
  const allInc=store('incomes'), allExp=store('expenses'), allProd=store('production');
  const cur=new Date().getFullYear();
  const years=[cur-2,cur-1,cur,cur+1].map(String);
  const yr=reportYear;
  const inc=allInc.filter(r=>(r.date||'').startsWith(yr));
  const exp=allExp.filter(r=>(r.date||'').startsWith(yr));
  const prod=allProd.filter(r=>(r.date||'').startsWith(yr));
  const months=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  const rows=months.map((mn,i)=>{
    const mi=inc.filter(r=>new Date(r.date).getMonth()===i).reduce((s,r)=>s+(+r.total||0),0);
    const me=exp.filter(r=>new Date(r.date).getMonth()===i).reduce((s,r)=>s+(+r.amount||0),0);
    const mp=prod.filter(r=>new Date(r.date).getMonth()===i).reduce((s,r)=>s+(+r.qty||0),0);
    return {mn,mi,me,mp};
  });
  const totInc=inc.reduce((s,r)=>s+(+r.total||0),0), totExp=exp.reduce((s,r)=>s+(+r.amount||0),0);
  const totProd=prod.reduce((s,r)=>s+(+r.qty||0),0);
  const byCrop={}; prod.forEach(p=>{byCrop[p.crop||'Unspecified']=(byCrop[p.crop||'Unspecified']||0)+(+p.qty||0);});
  const topCrops=Object.entries(byCrop).sort((a,b)=>b[1]-a[1]).slice(0,5);
  document.getElementById('main').innerHTML = `
    <div class="eyebrow">ANALYTICS</div><h1>Yearly Report</h1>
    <div class="sub">AGRI.TECH — ${todayStr}</div>
    <div style="margin-bottom:14px;">Year: <select id="yrSel" style="background:var(--panel2);border:1px solid var(--border);color:var(--text);padding:7px 10px;border-radius:8px;">${years.map(y=>`<option ${+y===yr?'selected':''}>${y}</option>`).join('')}</select></div>
    <div class="grid">
      <div class="card green"><div class="card-top"><div class="icon" style="background:#0f2e1c;">💰</div></div><div class="label">Year Income</div><div class="val">${money(totInc)}</div></div>
      <div class="card red"><div class="card-top"><div class="icon" style="background:#3d1a1a;">📦</div></div><div class="label">Year Expenses</div><div class="val">${money(totExp)}</div></div>
      <div class="card ${totInc-totExp<0?'red':'green'}"><div class="card-top"><div class="icon" style="background:#3d3410;">🌾</div></div><div class="label">Net Profit</div><div class="val">${money(totInc-totExp)}</div></div>
      <div class="card"><div class="card-top"><div class="icon" style="background:#12243d;">📦</div></div><div class="label">Total Production</div><div class="val">${totProd} kg</div></div>
    </div>
    <div class="panel"><div class="panel-head"><h3>Monthly Breakdown</h3><div class="hint">Year ${yr}</div></div>
      <table><thead><tr><th>Month</th><th>Income</th><th>Expense</th><th>Profit</th><th>Production (kg)</th></tr></thead>
      <tbody>${rows.map(r=>`<tr><td>${r.mn}</td><td style="color:var(--green);">${money(r.mi)}</td><td style="color:var(--red);">${money(r.me)}</td><td style="color:var(--yellow);">${money(r.mi-r.me)}</td><td>${r.mp}</td></tr>`).join('')}
      <tr style="font-weight:700;background:var(--panel2);"><td>TOTAL</td><td style="color:var(--green);">${money(totInc)}</td><td style="color:var(--red);">${money(totExp)}</td><td style="color:var(--yellow);">${money(totInc-totExp)}</td><td>${totProd}</td></tr>
      </tbody></table>
    </div>
    <div class="panel"><div class="panel-head"><h3>Top Crops (${yr})</h3></div>
      ${topCrops.length?`<table><thead><tr><th>Crop</th><th>Total Production</th></tr></thead><tbody>${topCrops.map(([c,v])=>`<tr><td>${c}</td><td>${v} kg</td></tr>`).join('')}</tbody></table>`:'<div class="empty">No production yet</div>'}
    </div>
    <div class="foot">© 2026 AGRI.TECH · Developed by Nirlep Kaila</div>`;
  document.getElementById('yrSel').addEventListener('change',e=>{reportYear=+e.target.value;renderYearlyReport();});
}
const EXPORT_ENTITIES = [['vadis','Vadi'],['crops','Crop'],['production','Production'],['incomes','Income'],
  ['expenses','Expense'],['workers','Worker'],['attendance','Attendance'],['upads','Upad'],
  ['dailyEntries','DailyEntry'],['seeds','Seed'],['fertilizer','Fertilizer'],['pesticides','Pesticide']];

function toCSV(rows){
  if(!rows.length) return '';
  const keys=[...new Set(rows.flatMap(r=>Object.keys(r)))];
  const esc=v=>`"${String(v??'').replace(/"/g,'""')}"`;
  return keys.join(',')+'\n'+rows.map(r=>keys.map(k=>esc(r[k])).join(',')).join('\n');
}
function downloadCSV(name,rows){
  const csv=toCSV(rows);
  const blob=new Blob([csv||'No data'],{type:'text/csv'});
  const a=document.createElement('a'); a.href=URL.createObjectURL(blob); a.download=name+'.csv';
  document.body.appendChild(a); a.click(); a.remove();
}
function exportOne(key,label){ downloadCSV(label, store(key)); }
function exportAll(){ EXPORT_ENTITIES.forEach(([k,l])=>downloadCSV(l, store(k))); }

function renderSettings(){
  document.getElementById('main').innerHTML = `
    <div class="eyebrow">ADMINISTRATION</div><h1>Settings</h1>
    <div class="sub">AGRI.TECH — ${todayStr}</div>
    <div class="panel">
      <div class="panel-head"><h3>Data Overview<div class="hint" style="font-weight:400;">Records per entity</div></h3></div>
      <div class="grid" style="grid-template-columns:repeat(4,1fr);">
        ${EXPORT_ENTITIES.map(([k,l])=>`<div style="background:var(--panel2);border:1px solid var(--border);border-radius:8px;padding:10px 14px;display:flex;justify-content:space-between;align-items:center;">
          <div><div class="hint">${l}</div><b style="font-size:16px;">${store(k).length}</b></div><span style="color:var(--muted);">🗄️</span>
        </div>`).join('')}
      </div>
    </div>
    <div class="panel">
      <div class="panel-head"><h3>Backup &amp; Export<div class="hint" style="font-weight:400;">Export your farm data to CSV</div></h3>
        <button class="btn" onclick="exportAll()">⬇ Export All</button></div>
      <div class="grid" style="grid-template-columns:1fr 1fr;">
        ${EXPORT_ENTITIES.map(([k,l])=>`<div style="display:flex;justify-content:space-between;align-items:center;background:var(--panel2);border:1px solid var(--border);border-radius:8px;padding:10px 14px;">
          <span>${l} (${store(k).length})</span>
          <button class="actions" style="background:none;border:none;color:var(--muted);cursor:pointer;font-size:15px;" onclick="exportOne('${k}','${l}')">⬇</button>
        </div>`).join('')}
      </div>
    </div>
    <div class="panel">
      <div class="panel-head"><h3>About<div class="hint" style="font-weight:400;">Application info</div></h3></div>
      <div style="display:flex;gap:12px;align-items:center;">
        <img src="images/umiya-farm-logo.png" style="width: 60px;" alt="Umiya Farm logo">
        <div><b>UMIYA FARM</b><div class="hint">Personal Farm Management System · v1.0</div></div>
      </div>
    </div>
    <div class="panel">
      <div class="panel-head"><h3>Appearance<div class="hint" style="font-weight:400;">Display preferences</div></h3></div>
      <div style="display:flex;justify-content:space-between;align-items:center;background:var(--panel2);border:1px solid var(--border);border-radius:8px;padding:10px 14px;">
        <span>Theme</span><span class="hint">🌙 Dark (default)</span>
      </div>
    </div>
    <div class="panel" style="border-color:#5a2323;">
      <div class="panel-head"><h3 style="color:var(--red);">Danger Zone</h3></div>
      <div style="display:flex;justify-content:space-between;align-items:center;">
        <div><b>Clear All Data</b><div class="hint">Permanently deletes every record from this browser</div></div>
        <button class="btn" style="background:var(--red);color:#fff;" onclick="clearAllData()">Clear All Data</button>
      </div>
    </div>
    <div class="foot">© 2026 AGRI.TECH · Developed by Nirlep Kaila</div>`;
}
function clearAllData(){
  if(!confirm('This will permanently delete all farm data from this browser. Continue?')) return;
  EXPORT_ENTITIES.forEach(([k])=>localStorage.removeItem('agritech_'+k));
  render();
}

function render(){
  if(activeKey==='dashboard') renderDashboard();
  else if(activeKey==='farmOverview') renderFarmOverview();
  else if(activeKey==='profitLoss') renderProfitLoss();
  else if(activeKey==='cropAnalysis') renderCropAnalysis();
  else if(activeKey==='productionAnalysis') renderProductionAnalysis();
  else if(activeKey==='yearlyReport') renderYearlyReport();
  else if(activeKey==='settings') renderSettings();
  else renderModulePage(activeKey);
}

buildSidebar();
setActive('dashboard');
</script>
</body>
</html>