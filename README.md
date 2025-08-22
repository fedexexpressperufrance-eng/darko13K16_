<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>DARKO 13K16 — Boutique Auto</title>
  <meta name="description" content="Concessionnaire véhicules neufs Renault & Volkswagen. Achat et réservation en ligne." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
  <style>
    :root{--bg:#f7f7f8;--card:#fff;--ink:#0f172a;--muted:#64748b;--line:#e5e7eb;--brand:#111827}
    *{box-sizing:border-box}
    html,body{margin:0;padding:0;font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,"Helvetica Neue",Arial,sans-serif;color:var(--ink);background:linear-gradient(#fafafa,#fff)}
    a{color:inherit;text-decoration:none}
    img{max-width:100%;display:block}
    .container{max-width:1100px;margin:0 auto;padding:0 16px}
    .btn{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:16px;border:1px solid var(--line);background:#000;color:#fff;font-weight:700}
    .btn.outline{background:#fff;color:var(--ink)}
    .btn.ghost{background:#fff}
    .badge{display:inline-flex;align-items:center;border:1px solid var(--line);border-radius:999px;padding:4px 8px;font-size:12px}
    header{position:sticky;top:0;z-index:30;background:rgba(255,255,255,.8);backdrop-filter:saturate(180%) blur(8px);border-bottom:1px solid var(--line)}
    .nav{display:flex;align-items:center;justify-content:space-between;height:64px}
    .brand{font-size:22px;font-weight:900;letter-spacing:.3px}
    .hero{position:relative}
    .hero .bg{position:absolute;inset:0;overflow:hidden;z-index:-1}
    .hero .bg img{width:100%;height:100%;object-fit:cover;opacity:.28}
    .hero .veil{position:absolute;inset:0;background:linear-gradient(to bottom,rgba(255,255,255,.7),#fff)}
    .hero-inner{padding:32px 0 20px}
    .hero h1{font-size:40px;line-height:1.05;margin:0}
    .hero p{color:var(--muted);max-width:720px;margin-top:8px}
    .filters{display:grid;grid-template-columns:1fr;gap:12px;background:rgba(255,255,255,.9);border:1px solid var(--line);border-radius:20px;padding:14px}
    .filters input,.filters select{width:100%;padding:10px;border:1px solid var(--line);border-radius:12px}
    .range{display:flex;align-items:center;gap:12px}
    .catalogue{padding:8px 0 60px}
    .catalogue-head{display:flex;align-items:end;justify-content:space-between;margin:16px 0}
    .grid{display:grid;grid-template-columns:1fr;gap:18px}
    .card{border:1px solid var(--line);border-radius:22px;overflow:hidden;background:var(--card);box-shadow:0 1px 2px rgba(0,0,0,.04)}
    .card .cover{aspect-ratio:16/10;overflow:hidden}
    .card .cover img{width:100%;height:100%;object-fit:cover;transition:transform .4s}
    .card:hover .cover img{transform:scale(1.02)}
    .card .content{padding:14px}
    .card h3{margin:0;font-size:18px}
    .card .row{display:flex;align-items:start;justify-content:space-between;gap:10px}
    .card .muted{color:var(--muted);font-size:14px}
    .card .price{font-weight:900}
    .card .actions{display:flex;gap:10px;margin-top:8px}
    .banner{margin-top:22px;border:1px solid var(--line);border-radius:22px;padding:16px;display:flex;flex-wrap:wrap;align-items:center;justify-content:space-between;background:#fff;gap:12px}
    footer{border-top:1px solid var(--line);background:#fff}
    footer .cols{display:grid;grid-template-columns:1fr;gap:18px;padding:26px 0}
    .note{color:var(--muted);font-size:14px}
    /* Modal */
    .modal{position:fixed;inset:0;display:none;align-items:center;justify-content:center;z-index:50}
    .modal.open{display:flex}
    .modal .scrim{position:absolute;inset:0;background:rgba(0,0,0,.4)}
    .modal .panel{position:relative;width:min(640px,92vw);background:#fff;border-radius:22px;overflow:hidden;border:1px solid var(--line);box-shadow:0 10px 30px rgba(0,0,0,.15)}
    .modal .head{display:flex;align-items:center;justify-content:space-between;padding:14px 16px;border-bottom:1px solid var(--line)}
    .modal .body{padding:16px}
    .form-grid{display:grid;grid-template-columns:1fr;gap:12px}
    .form-grid .field{display:flex;flex-direction:column;gap:6px}
    .field input,.field textarea{padding:10px;border:1px solid var(--line);border-radius:12px;width:100%}
    .toast{position:fixed;left:50%;transform:translateX(-50%);bottom:18px;z-index:60;background:#fff;border:1px solid var(--line);border-radius:18px;padding:12px 14px;display:none;align-items:center;gap:14px;box-shadow:0 10px 30px rgba(0,0,0,.12)}
    .toast.show{display:flex}
    /* Responsive */
    @media (min-width:640px){
      .filters{grid-template-columns:1fr 180px 180px 1fr}
      .grid{grid-template-columns:repeat(2,1fr)}
      footer .cols{grid-template-columns:1.2fr 1fr 1fr}
    }
    @media (min-width:960px){
      .hero-inner{display:flex;align-items:flex-start;justify-content:space-between;gap:24px}
      .grid{grid-template-columns:repeat(3,1fr)}
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <div class="brand">DARKO 13K16</div>
      <div class="actions">
        <a id="waTop" class="btn" target="_blank" rel="noreferrer" href="#"> 
          <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M20.52 3.48A11.94 11.94 0 0 0 12.06 0 11.94 11.94 0 0 0 0 12c0 2.11.55 4.09 1.6 5.85L0 24l6.31-1.64A11.93 11.93 0 0 0 12.06 24 11.94 11.94 0 0 0 24 12c0-3.2-1.25-6.2-3.48-8.52ZM12.06 22a9.93 9.93 0 0 1-5.06-1.39l-.36-.22-3.74.97.99-3.65-.24-.38A9.93 9.93 0 1 1 22.06 12 10 10 0 0 1 12.06 22Zm5.58-7.43c-.31-.16-1.83-.91-2.11-1.01-.28-.1-.48-.16-.68.16-.2.31-.78 1.01-.95 1.22-.17.2-.35.23-.65.08-.31-.16-1.3-.48-2.47-1.53-.91-.8-1.53-1.78-1.71-2.08-.17-.31-.02-.48.13-.63.13-.13.31-.35.47-.52.16-.17.2-.3.31-.5.1-.2.05-.38-.03-.53-.08-.16-.68-1.65-.94-2.26-.25-.6-.5-.51-.68-.52h-.58c-.2 0-.53.07-.81.38-.28.31-1.06 1.03-1.06 2.51 0 1.48 1.09 2.9 1.25 3.1.16.2 2.16 3.3 5.23 4.62.73.31 1.3.49 1.74.63.73.23 1.39.2 1.92.12.59-.09 1.83-.75 2.09-1.47.26-.72.26-1.34.18-1.47-.08-.13-.28-.21-.59-.37Z"/></svg>
          WhatsApp
        </a>
      </div>
    </div>
  </header>

  <main>
    <!-- HERO -->
    <section class="hero">
      <div class="bg">
        <img src="https://images.unsplash.com/photo-1542282088-fe8426682b8f?q=80&w=2400&auto=format&fit=crop" alt="Showroom"/>
        <div class="veil"></div>
      </div>
      <div class="container hero-inner">
        <div>
          <h1>Concessionnaire véhicules neufs — Renault & Volkswagen</h1>
          <p>Découvrez notre sélection et réservez ou achetez directement en ligne. Service client réactif, livraisons rapides, garanties constructeurs.</p>
          <div style="display:flex;gap:10px;margin-top:12px">
            <a href="#catalogue" class="btn outline">Voir le catalogue</a>
            <a id="waHero" class="btn ghost" target="_blank" rel="noreferrer" href="#">Écrire sur WhatsApp</a>
          </div>
        </div>
        <!-- Filtres -->
        <div class="filters" aria-label="Filtres catalogue">
          <input id="q" placeholder="Rechercher un modèle..." />
          <select id="brand">
            <option value="Toutes">Toutes marques</option>
            <option>Renault</option>
            <option>Volkswagen</option>
          </select>
          <select id="fuel">
            <option value="Tous">Tous carburants</option>
            <option>Essence</option>
            <option>Diesel</option>
            <option>Hybride</option>
            <option>Électrique</option>
          </select>
          <div class="range">
            <input id="price" type="range" min="5000000" max="40000000" step="500000" value="40000000"/>
            <div class="note" id="priceLabel">≤ 40 000 000 FCFA</div>
          </div>
        </div>
      </div>
    </section>

    <!-- CATALOGUE -->
    <section id="catalogue" class="catalogue">
      <div class="container">
        <div class="catalogue-head">
          <h2 style="margin:0;font-size:24px;font-weight:900">Catalogue disponible</h2>
          <div class="note"><span id="count">0</span> véhicule(s) trouvé(s)</div>
        </div>
        <div class="grid" id="grid"></div>

        <div class="banner">
          <div>
            <div style="font-weight:800">Vous cherchez un modèle spécifique ?</div>
            <div class="note">Import sur commande : finitions, couleurs et options au choix.</div>
          </div>
          <a id="waBanner" class="btn" target="_blank" rel="noreferrer" href="#">WhatsApp</a>
        </div>
      </div>
    </section>
  </main>

  <!-- RÉCAP/TOAST -->
  <div id="toast" class="toast" role="status" aria-live="polite">
    <div style="font-weight:700">Demande prête</div>
    <div class="note" id="toastText"></div>
    <a id="waToast" class="btn" target="_blank" rel="noreferrer" href="#">Envoyer sur WhatsApp</a>
  </div>

  <!-- MODALE CHECKOUT -->
  <div id="modal" class="modal" aria-hidden="true">
    <div class="scrim" onclick="closeModal()"></div>
    <div class="panel" role="dialog" aria-modal="true">
      <div class="head">
        <div style="font-weight:800" id="modalTitle">Demande</div>
        <button class="btn outline" onclick="closeModal()">✕</button>
      </div>
      <div class="body">
        <form id="checkout" class="form-grid" onsubmit="submitCheckout(event)">
          <div class="field">
            <label>Nom complet</label>
            <input name="name" required />
          </div>
          <div class="field">
            <label>Téléphone</label>
            <input name="phone" required />
          </div>
          <div class="field">
            <label>Email</label>
            <input name="email" type="email" required />
          </div>
          <div class="field">
            <label>Message / Détails</label>
            <textarea name="note" rows="3" placeholder="Adresse de livraison, modalités, etc."></textarea>
          </div>
          <div style="display:flex;justify-content:space-between;align-items:center;gap:10px;margin-top:6px">
            <div class="note" id="checkoutInfo">Paiement sécurisé en agence ou par lien.</div>
            <button type="submit" class="btn">Continuer</button>
          </div>
        </form>
      </div>
    </div>
  </div>

  <footer>
    <div class="container cols">
      <div>
        <div style="font-size:20px;font-weight:900">DARKO 13K16</div>
        <p class="note">Vente de véhicules neufs Renault & Volkswagen. Réservation et achat en ligne.</p>
      </div>
      <div>
        <div style="font-weight:800;margin-bottom:8px">Contact</div>
        <ul class="note" style="list-style:none;padding:0;margin:0;display:grid;gap:6px">
          <li>Téléphone : <b>(+229) XX XX XX XX</b></li>
          <li>Email : contact@darko13k16.com</li>
          <li>Adresse : à compléter</li>
        </ul>
      </div>
      <div>
        <div style="font-weight:800;margin-bottom:8px">Action rapide</div>
        <a id="waFooter" class="btn" target="_blank" rel="noreferrer" href="#">Prendre rendez-vous</a>
      </div>
    </div>
    <div class="container" style="text-align:center;padding:0 0 26px 0">
      <div class="note">© <span id="year"></span> DARKO 13K16. Tous droits réservés.</div>
    </div>
  </footer>

  <script>
    // ---------------------------------------------------------
    // CONFIG — À PERSONNALISER
    // ---------------------------------------------------------
    const DEALERSHIP_NAME = 'DARKO 13K16';
    const WHATSAPP_NUMBER = '22900000000'; // ← Remplacez par votre numéro (ex: 22997xxxxxx)

    const CARS = [
      {
        id: 'clio5', brand: 'Renault', model: 'Clio V Intens', year: 2024,
        fuel: 'Essence', transmission: 'Automatique', price: 12500000,
        image: 'https://images.unsplash.com/photo-1619767886558-efdc259cde1a?q=80&w=1600&auto=format&fit=crop',
        badges: ['Neuf','Garantie 3 ans','Caméra de recul']
      },
      {
        id: 'captur', brand: 'Renault', model: 'Captur Techno', year: 2024,
        fuel: 'Essence', transmission: 'Manuelle', price: 16800000,
        image: 'https://images.unsplash.com/photo-1568572933382-74d440642117?q=80&w=1600&auto=format&fit=crop',
        badges: ['Neuf','Apple CarPlay','Jantes alliage']
      },
      {
        id: 'golf8', brand: 'Volkswagen', model: 'Golf 8 Life', year: 2024,
        fuel: 'Essence', transmission: 'Automatique', price: 17900000,
        image: 'https://images.unsplash.com/photo-1503376780353-7e6692767b70?q=80&w=1600&auto=format&fit=crop',
        badges: ['Neuf','LED','Écran 10\'']
      },
      {
        id: 'tiguan', brand: 'Volkswagen', model: 'Tiguan R-Line', year: 2025,
        fuel: 'Diesel', transmission: 'Automatique', price: 29500000,
        image: 'https://images.unsplash.com/photo-1619767886558-efdc259cde1a?q=80&w=1600&auto=format&fit=crop',
        badges: ['SUV','ADAS','Toit panoramique']
      }
    ];

    // ---------------------------------------------------------
    // OUTILS
    // ---------------------------------------------------------
    const fXOF = new Intl.NumberFormat('fr-FR',{style:'currency',currency:'XOF'});
    const qs = (s,p=document)=>p.querySelector(s);
    const qsa = (s,p=document)=>Array.from(p.querySelectorAll(s));

    function makeWA(text){
      const msg = encodeURIComponent(text);
      return `https://wa.me/${WHATSAPP_NUMBER}?text=${msg}`;
    }

    function el(tag, attrs={}, children=[]) {
      const e = document.createElement(tag);
      for (const [k,v] of Object.entries(attrs)){
        if(k==='class') e.className=v; else if(k==='html') e.innerHTML=v; else e.setAttribute(k,v);
      }
      for (const c of (Array.isArray(children)?children:[children])){
        if(c==null) continue;
        if(typeof c==='string') e.appendChild(document.createTextNode(c));
        else e.appendChild(c);
      }
      return e;
    }

    // ---------------------------------------------------------
    // RENDU DES CARTES
    // ---------------------------------------------------------
    function renderGrid(list){
      const grid = qs('#grid');
      grid.innerHTML='';
      list.forEach(car=>{
        const card = el('div',{class:'card'});
        const cover = el('div',{class:'cover'}, el('img',{src:car.image,alt:`${car.brand} ${car.model}`}));
        const content = el('div',{class:'content'});

        const row = el('div',{class:'row'});
        const left = el('div',{},[
          el('h3',{},`${car.brand} ${car.model}`),
          el('div',{class:'muted'},`${car.year} · ${car.fuel} · ${car.transmission}`)
        ]);
        const price = el('div',{class:'price'}, fXOF.format(car.price));
        row.append(left,price);

        const badges = el('div', {style:'display:flex;flex-wrap:wrap;gap:8px;margin-top:8px'});
        car.badges.forEach(b=> badges.append(el('span',{class:'badge'}, b)));

        const actions = el('div',{class:'actions'},[
          el('a',{href:'#',class:'btn outline',onclick:(e)=>{e.preventDefault(); openModal(car,'reservation');}},'Réserver'),
          el('a',{href:'#',class:'btn',onclick:(e)=>{e.preventDefault(); openModal(car,'achat');}},'Acheter')
        ]);

        content.append(row,badges,actions);
        card.append(cover,content);
        grid.append(card);
      });
      qs('#count').textContent = list.length;
    }

    // ---------------------------------------------------------
    // FILTRES
    // ---------------------------------------------------------
    const state = { q:'', brand:'Toutes', fuel:'Tous', price:40000000 };

    function applyFilters(){
      const res = CARS.filter(c =>
        (state.brand==='Toutes' || c.brand===state.brand) &&
        (state.fuel==='Tous' || c.fuel===state.fuel) &&
        (c.price <= state.price) &&
        (`${c.brand} ${c.model}`.toLowerCase().includes(state.q.toLowerCase()))
      );
      renderGrid(res);
    }

    function bindFilters(){
      const q=qs('#q'), brand=qs('#brand'), fuel=qs('#fuel'), price=qs('#price'), priceLabel=qs('#priceLabel');
      q.addEventListener('input',()=>{state.q=q.value; applyFilters();});
      brand.addEventListener('change',()=>{state.brand=brand.value; applyFilters();});
      fuel.addEventListener('change',()=>{state.fuel=fuel.value; applyFilters();});
      price.addEventListener('input',()=>{state.price=+price.value; priceLabel.textContent = `≤ ${fXOF.format(state.price)}`; applyFilters();});
    }

    // ---------------------------------------------------------
    // MODALE & CHECKOUT
    // ---------------------------------------------------------
    let current = { car:null, type:null };

    function openModal(car,type){
      current = {car,type};
      qs('#modalTitle').textContent = `${type==='reservation'?'Réserver':'Acheter'} — ${car.brand} ${car.model}`;
      qs('#checkoutInfo').textContent = type==='reservation' ? 'La réservation bloque le véhicule pour vous. Un acompte peut être requis.' : 'Paiement sécurisé en agence ou par lien.';
      qs('#modal').classList.add('open');
      qs('#modal').setAttribute('aria-hidden','false');
    }

    function closeModal(){
      qs('#modal').classList.remove('open');
      qs('#modal').setAttribute('aria-hidden','true');
    }

    function submitCheckout(e){
      e.preventDefault();
      const data = Object.fromEntries(new FormData(e.target).entries());
      const {car,type} = current;
      const title = `${car.brand} ${car.model} ${car.year}`;
      const action = type==='reservation'?'RÉSERVATION':'ACHAT';
      const text = [
        `Bonjour ${DEALERSHIP_NAME},`,
        `Je souhaite procéder à une ${action}.`,
        `Véhicule: ${title} (${fXOF.format(car.price)})`,
        `Nom: ${data.name}`,
        `Téléphone: ${data.phone}`,
        `Email: ${data.email}`,
        data.note?`Note: ${data.note}`:null
      ].filter(Boolean).join('\n');

      // Mise à jour des liens WhatsApp
      const wa = makeWA(text);
      qs('#waToast').setAttribute('href', wa);

      // Toast
      qs('#toastText').textContent = `${action} · ${car.brand} ${car.model} · ${fXOF.format(car.price)}`;
      qs('#toast').classList.add('show');
      setTimeout(()=>qs('#toast').classList.remove('show'), 12000);

      closeModal();
      e.target.reset();
    }

    // ---------------------------------------------------------
    // WHATSAPP QUICK LINKS
    // ---------------------------------------------------------
    function initWhatsAppShortcuts(){
      const base = `Bonjour ${DEALERSHIP_NAME}, j'ai une question.`;
      const links = [ ['#waTop', base], ['#waHero', base], ['#waBanner', `Bonjour ${DEALERSHIP_NAME}, je cherche un modèle spécifique.`], ['#waFooter', `Bonjour ${DEALERSHIP_NAME}, je souhaite un rendez-vous.`] ];
      links.forEach(([sel,msg])=>{ const a=qs(sel); if(a) a.href = makeWA(msg); });
    }

    // ---------------------------------------------------------
    // INIT
    // ---------------------------------------------------------
    document.addEventListener('DOMContentLoaded', ()=>{
      qs('#year').textContent = new Date().getFullYear();
      bindFilters();
      applyFilters();
      initWhatsAppShortcuts();
    });
  </script>
</body>
</html>
