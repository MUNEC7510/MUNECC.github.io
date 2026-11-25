# MUNECC.github.io
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MUNEC — Museo Nacional El Changarrito</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700;800&family=Pirata+One&family=Rye&family=Oswald:wght@500;600;700&family=Pacifico&family=Archivo+Black&display=swap" rel="stylesheet">
<style>
:root{--yellow:#FF0082;--pink:#FF0082;--blue:#235FC2;--orange:#FF8A00;--cyan:#06C7D7;--green:#00968A;--ink:#171717;--paper:#F7F5EF;--line:#E7E3D9;--muted:#77746E}
*{box-sizing:border-box}body{margin:0;background:var(--paper);color:var(--ink);font-family:'DM Sans',sans-serif}
button,input,select,textarea{font:inherit}button{cursor:pointer;border:0}
.topbar{height:72px;background:#fff;border-bottom:1px solid var(--line);display:flex;align-items:center;justify-content:space-between;padding:0 25px;position:sticky;top:0;z-index:10}
.brand{display:flex;align-items:center;gap:12px}.brandmark{width:43px;height:43px;background:var(--yellow);display:grid;place-items:center;font-family:'Pirata One';font-size:27px;border-radius:50%;border:2px solid var(--ink);box-shadow:3px 3px 0 var(--ink)}
.brandname{font-family:'Pirata One';font-size:29px;line-height:1}.brandsub{font-size:9px;letter-spacing:1.4px;font-weight:800;margin-top:3px}
.top-actions{display:flex;gap:8px;align-items:center}.btn{padding:10px 14px;border-radius:8px;font-weight:700;font-size:12px;background:#fff;border:1px solid var(--line);transition:.18s}.btn:hover{transform:translateY(-1px);box-shadow:0 3px 0 #ddd}.btn.dark{background:var(--ink);color:#fff;border-color:var(--ink)}.btn.yellow{background:var(--yellow);border:1px solid var(--ink);box-shadow:3px 3px 0 var(--ink)}.btn.pink{background:var(--pink);color:white}.btn.small{padding:8px 10px;font-size:11px}
.welcome{padding:28px 30px 22px;background:var(--yellow);border-bottom:2px solid var(--ink);position:relative;overflow:hidden}.welcome:after{content:"✳";position:absolute;right:7%;top:-38px;font-size:170px;opacity:.13}.eyebrow{font-size:10px;font-weight:800;letter-spacing:2px;text-transform:uppercase}.welcome h1{font-family:'Pirata One';font-size:clamp(34px,5vw,58px);font-weight:400;margin:7px 0 2px}.welcome p{margin:0;font-size:13px;font-weight:600;max-width:620px}
.workspace{display:grid;grid-template-columns:270px minmax(300px,1fr) 275px;gap:15px;padding:17px;max-width:1600px;margin:auto;min-height:calc(100vh - 220px)}
.panel{background:#fff;border:1px solid var(--line);border-radius:12px;overflow:hidden;align-self:start}.panel-head{padding:15px 16px;border-bottom:1px solid var(--line);font-weight:800;font-size:12px;letter-spacing:.5px;display:flex;justify-content:space-between;align-items:center}.panel-body{padding:15px}.section{margin-bottom:19px}.section-title{font-size:10px;text-transform:uppercase;letter-spacing:1.2px;color:var(--muted);font-weight:800;margin-bottom:10px}.field{display:block;width:100%;border:1px solid var(--line);background:#FCFBF8;padding:10px;border-radius:7px;font-size:12px;outline:none}.field:focus{border-color:var(--blue);box-shadow:0 0 0 2px #235fc21c}textarea.field{resize:vertical;min-height:65px}.row{display:flex;gap:8px;align-items:center}.row>*{min-width:0;flex:1}.label{font-size:11px;font-weight:700;display:block;margin:10px 0 6px}.color-row{display:flex;gap:7px;align-items:center;flex-wrap:wrap}.swatch{width:27px;height:27px;border-radius:50%;border:2px solid #fff;outline:1px solid #ccc;padding:0}.swatch.active{outline:2px solid var(--ink)}input[type=color]{width:35px;height:30px;border:0;background:none;padding:0}
.center{min-width:0}.canvas-toolbar{display:flex;justify-content:space-between;align-items:center;margin-bottom:10px;gap:8px}.canvas-toolbar strong{font-size:12px}.canvas-wrap{background:#EAE8E1;border:1px solid #D9D5CA;border-radius:12px;min-height:510px;padding:24px;display:grid;place-items:center;overflow:auto;position:relative}.artboard{width:min(100%,720px);aspect-ratio:3/2;background:#fff;box-shadow:0 10px 35px #00000018;position:relative;overflow:hidden;touch-action:none}.artboard.checker{background-color:#fff;background-image:linear-gradient(45deg,#eee 25%,transparent 25%),linear-gradient(-45deg,#eee 25%,transparent 25%),linear-gradient(45deg,transparent 75%,#eee 75%),linear-gradient(-45deg,transparent 75%,#eee 75%);background-size:20px 20px;background-position:0 0,0 10px,10px -10px,-10px 0}
.art-text{position:absolute;white-space:pre-wrap;line-height:1.08;text-align:center;cursor:move;user-select:none;transform-origin:center center;padding:4px;min-width:30px;max-width:90%;overflow-wrap:anywhere}.art-text.selected{outline:1px dashed var(--blue);outline-offset:3px}.art-text .inner{display:block}.deco{position:absolute;cursor:move;user-select:none;transform-origin:center}.deco.selected{outline:1px dashed var(--blue)}
.empty-hint{position:absolute;inset:0;display:grid;place-items:center;text-align:center;color:#999;font-size:13px;pointer-events:none}
.hint{font-size:10px;color:var(--muted);line-height:1.5;margin-top:10px}
.template-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px}.template{border:1px solid var(--line);border-radius:8px;overflow:hidden;background:#fff;text-align:left;padding:0}.template-preview{height:68px;display:grid;place-items:center;font-family:'Rye';font-size:18px}.template span{display:block;padding:7px;font-size:10px;font-weight:700}
input[type=range]{width:100%;accent-color:var(--pink)}.range-line{display:flex;justify-content:space-between;font-size:11px;font-weight:700;margin:10px 0 4px}.toggleline{display:flex;align-items:center;gap:7px;font-size:11px;margin-top:9px}.toggleline input{accent-color:var(--pink)}
.canvas-footer{display:flex;justify-content:space-between;font-size:10px;color:var(--muted);padding:9px 3px}
.layers{display:flex;flex-direction:column;gap:6px}.layer{display:flex;align-items:center;gap:8px;border:1px solid var(--line);padding:8px;border-radius:7px;font-size:11px}.layer.active{border-color:var(--blue);background:#235fc20c}.layer button{background:transparent;font-size:13px}
.notice{background:#FFF6CF;border:1px solid #F1D96B;border-radius:8px;padding:10px;font-size:10px;line-height:1.5}
footer{padding:20px 25px;text-align:center;font-size:10px;color:var(--muted);border-top:1px solid var(--line)}footer b{color:var(--ink)}
@media(max-width:1050px){.workspace{grid-template-columns:235px minmax(280px,1fr)}.right-panel{grid-column:1/-1}.right-panel .panel-body{display:grid;grid-template-columns:1fr 1fr;gap:18px}}
@media(max-width:700px){.topbar{padding:10px 13px;height:auto;align-items:flex-start;gap:10px;flex-wrap:wrap}.top-actions{width:100%;overflow-x:auto}.welcome{padding:22px 17px}.workspace{display:flex;flex-direction:column;padding:10px}.panel,.center{width:100%}.canvas-wrap{min-height:330px;padding:12px}.right-panel .panel-body{display:block}.brandname{font-size:25px}}
.brandlogo{height:46px;width:auto;display:block}
</style>
</head>
<body>
<header class="topbar">
  <div class="brand"><img class="brandlogo" src="data:image/png;base64,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" alt="MUNEC"><div><div class="brandname">MUNEC</div><div class="brandsub">MUSEO NACIONAL EL CHANGARRITO</div></div></div>
  <div class="top-actions">
    <button class="btn small" id="undo">↶ Deshacer</button><button class="btn small" id="redo">↷ Rehacer</button>
    <button class="btn small" id="save">Guardar</button><button class="btn small" id="open">Abrir</button><input type="file" id="openfile" accept=".json" hidden>
    <button class="btn small" id="clear">Borrar todo</button><button class="btn yellow small" id="png">Descargar PNG</button><button class="btn small" id="pdf">PDF</button>
  </div>
</header>
<section class="welcome">
  <div class="eyebrow">Museo Nacional El Changarrito · Laboratorio gráfico</div>
  <h1>La cultura gráfica popular también se diseña.</h1>
  <p>Crea, juega y experimenta con letras. Un espacio gratuito para imaginar nuevos rótulos.</p>
</section>
<main class="workspace">
  <aside class="panel">
    <div class="panel-head">✳ HERRAMIENTAS <span>01</span></div>
    <div class="panel-body">
      <div class="section">
        <div class="section-title">Comienza con una plantilla</div>
        <div class="template-grid">
          <button class="template" data-template="tacos"><div class="template-preview" style="background:#ffda16;color:#e31c3d">¡TACOS!</div><span>Taquería popular</span></button>
          <button class="template" data-template="oferta"><div class="template-preview" style="background:#ff0082;color:#ffda16">OFERTA</div><span>Oferta comercial</span></button>
          <button class="template" data-template="mercado"><div class="template-preview" style="background:#06c7d7;color:#171717">MERCADO</div><span>Mercado</span></button>
          <button class="template" data-template="clasico"><div class="template-preview" style="background:#fff1d0;color:#00968a">ABARROTES</div><span>Clásico</span></button>
        </div>
      </div>
      <div class="section">
        <div class="section-title">Texto</div>
        <textarea class="field" id="newtext" placeholder="Escribe tu rótulo...">¡TACOS!</textarea>
        <button class="btn dark" style="width:100%;margin-top:8px" id="addtext">＋ Agregar texto</button>
        <div class="hint">Selecciona un texto del lienzo para editarlo. Arrástralo para cambiar su posición.</div>
      </div>
      <div class="section">
        <div class="section-title">Decoraciones rápidas</div>
        <div class="row"><button class="btn small" id="star">✦ Estrella</button><button class="btn small" id="flower">✿ Flor</button><button class="btn small" id="line">━ Línea</button></div>
      </div>
      <div class="section">
        <div class="section-title">Fondo del lienzo</div>
        <div class="row"><input type="color" id="bgcolor" value="#ffffff"><button class="btn small" id="transparent">Fondo transparente</button></div>
      </div>
      <div class="notice">MUNEC es un espacio de experimentación gráfica. Las herramientas de creación son gratuitas.</div>
    </div>
  </aside>

  <section class="center">
    <div class="canvas-toolbar"><strong>ÁREA DE TRABAJO</strong><div class="row" style="flex:0 0 auto"><button class="btn small" id="fit">Ajustar</button><select class="field" id="size" style="width:150px;padding:8px"><option value="3/2">Horizontal</option><option value="1/1">Cuadrado</option><option value="2/3">Vertical</option></select></div></div>
    <div class="canvas-wrap"><div class="artboard" id="artboard"><div class="empty-hint" id="empty" style="display:none">Agrega texto o una decoración para comenzar</div></div></div>
    <div class="canvas-footer"><span>Arrastra los elementos para acomodarlos</span><span id="dimensions">Lienzo horizontal</span></div>
  </section>

  <aside class="panel right-panel">
    <div class="panel-head">✳ PROPIEDADES <span>02</span></div>
    <div class="panel-body">
      <div>
        <div class="section">
          <div class="section-title">Elemento seleccionado</div>
          <label class="label">Contenido</label><textarea class="field" id="content" rows="2"></textarea>
          <label class="label">Tipografía</label>
          <select class="field" id="font">
            <option value="Rye">Rye · Rotulación</option><option value="Pirata One">Pirata One · MUNEC</option><option value="Oswald">Oswald · Comercial</option><option value="Pacifico">Pacifico · Cursiva</option><option value="Archivo Black">Archivo Black · Gruesa</option><option value="DM Sans">DM Sans · Sans serif</option><option value="Georgia">Georgia · Clásica</option>
          </select>
          <div class="range-line"><span>Tamaño</span><output id="sizeout">64</output></div><input type="range" id="fontsize" min="12" max="150" value="64">
          <div class="range-line"><span>Rotación</span><output id="rotateout">0°</output></div><input type="range" id="rotate" min="-180" max="180" value="0">
          <div class="range-line"><span>Espaciado</span><output id="spacingout">0</output></div><input type="range" id="spacing" min="-3" max="15" value="0">
        </div>
        <div class="section">
          <div class="section-title">Color y efectos</div>
          <label class="label">Relleno</label><div class="color-row"><input type="color" id="fill" value="#e52b3a"><span class="hint">Color principal de las letras</span></div>
          <label class="label">Contorno</label><div class="row"><input type="color" id="stroke" value="#171717"><input type="range" id="strokeWidth" min="0" max="12" value="2"></div>
          <label class="label">Sombra</label><div class="row"><input type="color" id="shadow" value="#235fc2"><input type="range" id="shadowBlur" min="0" max="20" value="0"></div>
          <label class="label">Desplazamiento de sombra</label><input type="range" id="shadowY" min="0" max="18" value="0">
          <label class="label">Alineación</label><div class="row"><button class="btn small" data-align="left">Izq.</button><button class="btn small" data-align="center">Centro</button><button class="btn small" data-align="right">Der.</button></div>
          <label class="toggleline"><input type="checkbox" id="bold"> Negrita</label><label class="toggleline"><input type="checkbox" id="italic"> Cursiva</label>
        </div>
      </div>
      <div>
        <div class="section">
          <div class="section-title">Organizar elemento</div>
          <div class="row"><button class="btn small" id="duplicate">Duplicar</button><button class="btn small" id="delete">Eliminar</button></div>
          <div class="row" style="margin-top:7px"><button class="btn small" id="front">Subir capa</button><button class="btn small" id="back">Bajar capa</button></div>
        </div>
        <div class="section">
          <div class="section-title">Alinear en el lienzo</div>
          <div class="row"><button class="btn small" id="centerx">Centrar ↔</button><button class="btn small" id="centery">Centrar ↕</button></div>
        </div>
        <div class="section">
          <div class="section-title">Elementos</div><div class="layers" id="layers"><div class="hint">Todavía no hay elementos.</div></div>
        </div>
      </div>
    </div>
  </aside>
</main>
<footer><b>MUNEC</b> · Museo Nacional El Changarrito · Laboratorio gratuito de rotulación</footer>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script>
const $ = id => document.getElementById(id);
const board = $('artboard');
let items = [];
let selectedId = null;
let undoStack = [], redoStack = [];
let drag = null;
let transparentBg = false;
const uid = () => 'el-' + Date.now().toString(36) + Math.random().toString(36).slice(2,8);
const clone = x => JSON.parse(JSON.stringify(x));
const current = () => items.find(x => x.id === selectedId);
const safe = s => String(s).replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
function remember(){undoStack.push(clone(items)); if(undoStack.length>50) undoStack.shift(); redoStack=[];}
function addText(text='Nuevo rótulo', extra={}){
 remember();
 const el={id:uid(),type:'text',text,font:'Rye',size:64,fill:'#e52b3a',stroke:'#171717',strokeWidth:0,shadow:'#235fc2',shadowBlur:0,shadowY:0,spacing:0,align:'center',bold:false,italic:false,x:50,y:50,rotation:0,...extra};
 items.push(el); selectedId=el.id; render();
}
function render(){
 board.querySelectorAll('.art-text,.deco').forEach(n=>n.remove());
 $('empty').style.display=items.length?'none':'grid';
 for(const it of items){
  const node=document.createElement('div');
  node.dataset.id=it.id;
  node.style.left=it.x+'%'; node.style.top=it.y+'%';
  node.style.transform=`translate(-50%,-50%) rotate(${it.rotation||0}deg)`;
  if(it.type==='text'){
   node.className='art-text'+(it.id===selectedId?' selected':'');
   node.innerHTML='<span class="inner">'+safe(it.text).replace(/\n/g,'<br>')+'</span>';
   Object.assign(node.style,{fontFamily:`"${it.font||'Rye'}",serif`,fontSize:(it.size||64)+'px',color:it.fill||'#222',WebkitTextStroke:`${it.strokeWidth||0}px ${it.stroke||'#171717'}`,textShadow:it.shadowBlur?`${it.shadowY||0}px ${it.shadowY||0}px ${it.shadowBlur}px ${it.shadow}`:'none',letterSpacing:(it.spacing||0)+'px',fontWeight:it.bold?'800':'400',fontStyle:it.italic?'italic':'normal',textAlign:it.align||'center'});
  } else {
   node.className='deco'+(it.id===selectedId?' selected':'');
   node.textContent=it.symbol; node.style.fontSize=(it.size||60)+'px'; node.style.color=it.fill||'#FF0082';
  }
  board.appendChild(node);
 }
 updateLayers(); syncPanel();
}
function updateLayers(){
 const box=$('layers'); box.innerHTML='';
 if(!items.length){box.innerHTML='<div class="hint">Todavía no hay elementos.</div>';return;}
 [...items].reverse().forEach(it=>{
  const row=document.createElement('div'); row.className='layer'+(it.id===selectedId?' active':'');
  const label=it.type==='text'?it.text:it.symbol;
  row.innerHTML=`<span>${it.type==='text'?'T':'✦'}</span><span style="flex:1;overflow:hidden;text-overflow:ellipsis;white-space:nowrap">${safe(label)}</span><button type="button">↗</button>`;
  row.addEventListener('click',()=>{selectedId=it.id;render();});
  box.appendChild(row);
 });
}
function syncPanel(){
 const it=current();
 ['content','font','fontsize','rotate','spacing','fill','stroke','strokeWidth','shadow','shadowBlur','shadowY','bold','italic'].forEach(id=>$(id).disabled=!it);
 if(!it)return;
 $('content').value=it.type==='text'?it.text:it.symbol;
 $('font').value=it.font||'Rye'; $('fontsize').value=it.size||64; $('sizeout').value=it.size||64;
 $('rotate').value=it.rotation||0; $('rotateout').value=(it.rotation||0)+'°';
 $('spacing').value=it.spacing||0; $('spacingout').value=it.spacing||0;
 $('fill').value=it.fill||'#e52b3a'; $('stroke').value=it.stroke||'#171717'; $('strokeWidth').value=it.strokeWidth||0;
 $('shadow').value=it.shadow||'#235fc2'; $('shadowBlur').value=it.shadowBlur||0; $('shadowY').value=it.shadowY||0;
 $('bold').checked=!!it.bold; $('italic').checked=!!it.italic;
}
function updateProp(key,value){const it=current();if(!it)return;remember();it[key]=value;render();}
function setLive(key,value){const it=current();if(!it)return;it[key]=value;render();}
function moveLayer(delta){const i=items.findIndex(x=>x.id===selectedId),j=i+delta;if(i<0||j<0||j>=items.length)return;remember();[items[i],items[j]]=[items[j],items[i]];render();}
function downloadBlob(blob,name){const a=document.createElement('a');const url=URL.createObjectURL(blob);a.href=url;a.download=name;document.body.appendChild(a);a.click();a.remove();setTimeout(()=>URL.revokeObjectURL(url),1500);}
function makeSVG(){
 const bg=transparentBg?'':`<rect width="1200" height="800" fill="${board.style.backgroundColor||'#ffffff'}"/>`;
 const body=items.map(it=>{
  const x=it.x*12,y=it.y*8;
  if(it.type==='deco')return `<text x="${x}" y="${y}" text-anchor="middle" dominant-baseline="middle" font-family="Arial" font-size="${it.size*1.5}" fill="${it.fill}" transform="rotate(${it.rotation||0} ${x} ${y})">${safe(it.symbol)}</text>`;
  const lines=String(it.text).split('\n');
  const spans=lines.map((line,i)=>`<tspan x="${x}" dy="${i?it.size*1.7:0}">${safe(line)}</tspan>`).join('');
  const anchor=it.align==='left'?'start':it.align==='right'?'end':'middle';
  const shadow=it.shadowBlur?`filter="url(#shadow)"`:'';
  return `<text x="${x}" y="${y}" text-anchor="${anchor}" dominant-baseline="middle" font-family="${safe(it.font||'serif')}" font-size="${it.size*1.5}" font-weight="${it.bold?800:400}" font-style="${it.italic?'italic':'normal'}" letter-spacing="${it.spacing||0}" fill="${it.fill||'#222'}" stroke="${it.strokeWidth?it.stroke:'none'}" stroke-width="${(it.strokeWidth||0)*1.5}" paint-order="stroke" transform="rotate(${it.rotation||0} ${x} ${y})" ${shadow}>${spans}</text>`;
 }).join('');
 return `<svg xmlns="http://www.w3.org/2000/svg" width="1200" height="800" viewBox="0 0 1200 800"><defs><filter id="shadow"><feGaussianBlur stdDeviation="5" result="b"/><feOffset dy="5"/><feMerge><feMergeNode/><feMergeNode in="SourceGraphic"/></feMerge></filter></defs>${bg}${body}</svg>`;
}
async function renderCanvas(){
 const cs=getComputedStyle(board),r=board.clientWidth/board.clientHeight;
 let W,H;if(r>1.001){W=2400;H=Math.round(W/r);}else if(r<.999){H=2400;W=Math.round(H*r);}else{W=H=2000;}
 const k=W/board.clientWidth;
 await Promise.all(items.map(it=>document.fonts.load(`${it.size||60}px "${it.font||'DM Sans'}"`).catch(()=>{})));
 await document.fonts.ready;
 const c=document.createElement('canvas');c.width=W;c.height=H;const ctx=c.getContext('2d');
 if(!transparentBg){ctx.fillStyle=cs.backgroundColor&&cs.backgroundColor!=='rgba(0, 0, 0, 0)'?cs.backgroundColor:'#ffffff';ctx.fillRect(0,0,W,H);}
 for(const it of items){
  ctx.save();ctx.translate(it.x/100*W,it.y/100*H);ctx.rotate((it.rotation||0)*Math.PI/180);
  ctx.textBaseline='middle';ctx.shadowColor='transparent';
  if(it.type==='deco'){ctx.font=`${(it.size||60)*k}px "DM Sans",Arial,sans-serif`;ctx.textAlign='center';ctx.fillStyle=it.fill||'#FF0082';ctx.fillText(it.symbol,0,0);ctx.restore();continue;}
  const fs=(it.size||64)*k,lh=fs*1.08,lines=String(it.text).split('\n');
  ctx.font=`${it.italic?'italic ':''}${it.bold?'800 ':'400 '}${fs}px "${it.font||'Rye'}",serif`;
  if('letterSpacing' in ctx)ctx.letterSpacing=((it.spacing||0)*k)+'px';
  const mw=Math.max(...lines.map(l=>ctx.measureText(l).width));
  const al=it.align||'center';ctx.textAlign=al;
  const px=al==='left'?-mw/2:al==='right'?mw/2:0;
  lines.forEach((l,i)=>{
   const y=(i-(lines.length-1)/2)*lh;
   if(it.shadowBlur){ctx.shadowColor=it.shadow;ctx.shadowBlur=it.shadowBlur*k;ctx.shadowOffsetX=(it.shadowY||0)*k;ctx.shadowOffsetY=(it.shadowY||0)*k;}
   ctx.fillStyle=it.fill||'#222';ctx.fillText(l,px,y);
   ctx.shadowColor='transparent';
   if(it.strokeWidth){ctx.lineJoin='round';ctx.lineWidth=it.strokeWidth*k;ctx.strokeStyle=it.stroke||'#171717';ctx.strokeText(l,px,y);}
  });
  ctx.restore();
 }
 return c;
}
async function exportPNG(){try{const c=await renderCanvas();c.toBlob(b=>downloadBlob(b,'munec-rotulo.png'),'image/png');}catch(e){alert('No se pudo generar la imagen.');}}
async function exportPDF(){
 try{const c=await renderCanvas(),{jsPDF}=window.jspdf,w=c.width/2,h=c.height/2;
  const p=new jsPDF({orientation:w>=h?'l':'p',unit:'px',format:[w,h],hotfixes:['px_scaling']});
  p.addImage(c.toDataURL('image/png'),'PNG',0,0,w,h);p.save('munec-rotulo.pdf');
 }catch(e){alert('No se pudo generar el PDF. Revisa tu conexión (se necesita la biblioteca jsPDF).');}
}
$('addtext').addEventListener('click',()=>addText($('newtext').value.trim()||'Nuevo rótulo'));
$('star').addEventListener('click',()=>{remember();items.push({id:uid(),type:'deco',symbol:'✦',size:65,fill:'#FF0082',x:50,y:50,rotation:0});selectedId=items.at(-1).id;render();});
$('flower').addEventListener('click',()=>{remember();items.push({id:uid(),type:'deco',symbol:'✿',size:70,fill:'#00968A',x:50,y:50,rotation:0});selectedId=items.at(-1).id;render();});
$('line').addEventListener('click',()=>{remember();items.push({id:uid(),type:'deco',symbol:'━',size:110,fill:'#235FC2',x:50,y:50,rotation:0});selectedId=items.at(-1).id;render();});
$('content').addEventListener('input',e=>{const it=current();if(!it||it.type!=='text')return;it.text=e.target.value;const node=board.querySelector(`[data-id="${it.id}"] .inner`);if(node)node.innerHTML=safe(it.text).replace(/\n/g,'<br>');updateLayers();});
$('content').addEventListener('change',()=>remember());
$('font').addEventListener('change',e=>updateProp('font',e.target.value));
$('fontsize').addEventListener('input',e=>{const it=current();if(it){it.size=+e.target.value;$('sizeout').value=it.size;const node=board.querySelector(`[data-id="${it.id}"]`);if(node)node.style.fontSize=it.size+'px';}});
$('fontsize').addEventListener('change',()=>remember());
$('rotate').addEventListener('input',e=>{const it=current();if(it){it.rotation=+e.target.value;$('rotateout').value=it.rotation+'°';const node=board.querySelector(`[data-id="${it.id}"]`);if(node)node.style.transform=`translate(-50%,-50%) rotate(${it.rotation}deg)`;}});
$('rotate').addEventListener('change',()=>remember());
$('spacing').addEventListener('input',e=>{const it=current();if(it){it.spacing=+e.target.value;$('spacingout').value=it.spacing;const node=board.querySelector(`[data-id="${it.id}"]`);if(node)node.style.letterSpacing=it.spacing+'px';}});
$('spacing').addEventListener('change',()=>remember());
[['fill','fill'],['stroke','stroke'],['strokeWidth','strokeWidth'],['shadow','shadow'],['shadowBlur','shadowBlur'],['shadowY','shadowY'],['bold','bold'],['italic','italic']].forEach(([id,key])=>{
 $(id).addEventListener('input',e=>{const it=current();if(!it)return;it[key]=e.target.type==='checkbox'?e.target.checked:(e.target.type==='range'?+e.target.value:e.target.value);render();});
 $(id).addEventListener('change',()=>remember());
});
document.querySelectorAll('[data-align]').forEach(b=>b.addEventListener('click',()=>updateProp('align',b.dataset.align)));
$('duplicate').addEventListener('click',()=>{const it=current();if(!it)return;remember();const copy=clone(it);copy.id=uid();copy.x=Math.min(94,copy.x+5);copy.y=Math.min(94,copy.y+5);items.push(copy);selectedId=copy.id;render();});
$('delete').addEventListener('click',()=>{if(!current())return;remember();items=items.filter(x=>x.id!==selectedId);selectedId=items.at(-1)?.id||null;render();});
$('front').addEventListener('click',()=>moveLayer(1)); $('back').addEventListener('click',()=>moveLayer(-1));
$('centerx').addEventListener('click',()=>updateProp('x',50)); $('centery').addEventListener('click',()=>updateProp('y',50));
board.addEventListener('pointerdown',e=>{
 const node=e.target.closest('[data-id]');
 if(!node){selectedId=null;render();return;}
 selectedId=node.dataset.id;const it=current();if(!it)return;
 drag={id:it.id,startX:e.clientX,startY:e.clientY,x:it.x,y:it.y,moved:false};
 board.setPointerCapture(e.pointerId);render();
});
board.addEventListener('pointermove',e=>{
 if(!drag)return;const it=items.find(x=>x.id===drag.id);if(!it)return;
 const r=board.getBoundingClientRect();it.x=Math.max(0,Math.min(100,drag.x+(e.clientX-drag.startX)/r.width*100));it.y=Math.max(0,Math.min(100,drag.y+(e.clientY-drag.startY)/r.height*100));drag.moved=true;
 const node=board.querySelector(`[data-id="${it.id}"]`);if(node){node.style.left=it.x+'%';node.style.top=it.y+'%';}
});
function endDrag(){if(drag&&drag.moved)remember();drag=null;}
board.addEventListener('pointerup',endDrag);board.addEventListener('pointercancel',endDrag);
$('bgcolor').addEventListener('input',e=>{transparentBg=false;board.classList.remove('checker');board.style.background=e.target.value;});
$('transparent').addEventListener('click',()=>{transparentBg=true;board.classList.add('checker');board.style.background='transparent';});
$('size').addEventListener('change',e=>{board.style.aspectRatio=e.target.value;$('dimensions').textContent=e.target.selectedOptions[0].textContent;});
const templates={
 tacos:{bg:'#FFDA16',a:['¡TACOS!','Rye',94,'#E52B3A',39],b:['HECHOS AL MOMENTO','Oswald',29,'#00968A',67]},
 oferta:{bg:'#FF0082',a:['¡OFERTA!','Archivo Black',90,'#FFDA16',42],b:['SOLO POR HOY','DM Sans',28,'#FFFFFF',68]},
 mercado:{bg:'#06C7D7',a:['MERCADO','Pirata One',94,'#171717',42],b:['FRESCO Y LOCAL','Oswald',30,'#FFFFFF',68]},
 clasico:{bg:'#FFF1D0',a:['ABARROTES','Rye',72,'#00968A',42],b:['DE TODO UN POCO','DM Sans',26,'#E52B3A',68]}
};
document.querySelectorAll('[data-template]').forEach(btn=>btn.addEventListener('click',()=>{
 const t=templates[btn.dataset.template];if(!t)return;remember();items=[];board.classList.remove('checker');transparentBg=false;board.style.background=t.bg;
 [t.a,t.b].forEach(v=>items.push({id:uid(),type:'text',text:v[0],font:v[1],size:v[2],fill:v[3],stroke:'#171717',strokeWidth:0,shadow:'#235fc2',shadowBlur:0,shadowY:0,spacing:0,align:'center',bold:false,italic:false,x:50,y:v[4],rotation:0}));
 selectedId=items[0].id;render();
}));
$('clear').addEventListener('click',()=>{if(confirm('¿Borrar todos los elementos?')){remember();items=[];selectedId=null;render();}});
$('undo').addEventListener('click',()=>{if(!undoStack.length)return;redoStack.push(clone(items));items=undoStack.pop();selectedId=items.at(-1)?.id||null;render();});
$('redo').addEventListener('click',()=>{if(!redoStack.length)return;undoStack.push(clone(items));items=redoStack.pop();selectedId=items.at(-1)?.id||null;render();});
$('save').addEventListener('click',()=>downloadBlob(new Blob([JSON.stringify({items,bg:board.style.background,aspect:board.style.aspectRatio,transparentBg},null,2)],{type:'application/json'}),'munec-proyecto.json'));
$('open').addEventListener('click',()=>$('openfile').click());
$('openfile').addEventListener('change',async e=>{const f=e.target.files[0];if(!f)return;try{const data=JSON.parse(await f.text());remember();items=Array.isArray(data.items)?data.items:[];selectedId=items.at(-1)?.id||null;board.style.background=data.bg||'#fff';board.style.aspectRatio=data.aspect||'3/2';transparentBg=!!data.transparentBg;board.classList.toggle('checker',transparentBg);render();}catch(err){alert('El archivo no es un proyecto MUNEC válido.');}e.target.value='';});
$('png').addEventListener('click',exportPNG);
$('pdf').addEventListener('click',exportPDF);
$('fit').addEventListener('click',()=>board.scrollIntoView({behavior:'smooth',block:'center'}));
render();
addText('¡TU RÓTULO AQUÍ!',{font:'Rye',size:70,fill:'#E52B3A',stroke:'#171717',strokeWidth:1,y:48});

</script>
</body>
</html>
