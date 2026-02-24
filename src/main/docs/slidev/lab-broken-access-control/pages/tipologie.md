---
layout: default
---

# Broken Access Control — Tipologie

<div class="flex items-center justify-around h-4/5">

  <div class="flex flex-col items-center gap-4">
    <div class="text-6xl">↕️</div>
    <div class="text-center">
      <div class="text-2xl font-bold text-blue-700">Vertical</div>
      <div class="text-2xl font-bold text-blue-700">Access Control</div>
    </div>
    <div class="text-gray-700 text-sm mt-2">User → Admin <span class="text-gray-500">(privilegi superiori)</span></div>
  </div>

  <div class="text-5xl text-gray-400">|</div>

  <div class="flex flex-col items-center gap-4">
    <div class="text-6xl">↔️</div>
    <div class="text-center">
      <div class="text-2xl font-bold text-purple-700">Horizontal</div>
      <div class="text-2xl font-bold text-purple-700">Access Control</div>
    </div>
    <div class="text-gray-700 text-sm mt-2">User A → User B <span class="text-gray-500">(stesso livello)</span></div>
  </div>

</div>

---
layout: default
---

# Broken Access Control — Verticale

<div class="flex items-center gap-8 h-4/5">

  <div class="flex flex-col items-center gap-3 w-48 flex-shrink-0">
    <div class="text-7xl">↕️</div>
    <div class="text-center font-bold text-blue-700 text-xl">
      <div>Vertical</div>
      <div>Access Control</div>
    </div>
  </div>

  <div class="flex flex-col gap-4 flex-1">
    <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800 leading-relaxed">
      🎯 Il controllo accessi di tipo <strong class="text-blue-700">«verticale»</strong> è un meccanismo che regola l'accesso a funzionalità dell'applicazione in base al <strong class="text-blue-700">profilo</strong> dell'utente autenticato.
    </div>
    <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800 leading-relaxed">
      👥 Utenti con profili differenti hanno accesso a funzionalità differenti. Per esempio un utente può avere il permesso di <strong class="text-blue-700">modificare o cancellare</strong> alcuni documenti mentre un altro utente può solamente <strong class="text-blue-700">visualizzare</strong> i documenti presenti a sistema.
    </div>
    <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800 leading-relaxed">
      ⚙️ Ogni applicazione può avere regole estremamente personalizzate e dettagliate ed implementare principi come <strong class="text-blue-700"><em>separation of duties</em></strong> o <strong class="text-blue-700"><em>least privilege</em></strong>.
    </div>
  </div>

</div>

---
layout: default
---

# Broken Access Control — Verticale

<div class="flex items-center gap-8 h-4/5">

  <div class="flex flex-col items-center gap-3 w-48 flex-shrink-0">
    <div class="text-7xl">↕️</div>
    <div class="text-center font-bold text-blue-700 text-xl">
      <div>Vertical</div>
      <div>Access Control</div>
    </div>
  </div>

  <div class="flex-1">
    <div class="rounded-xl border border-blue-300 bg-blue-50 p-6">
      <div class="flex items-center gap-4 mb-4">
        <div class="text-5xl">🧑‍💻</div>
        <div class="flex-1">
          <div class="text-xs text-gray-600 mb-1">Utente autenticato — ruolo: <span class="text-blue-700 font-semibold">user</span></div>
          <code class="text-blue-700 text-sm bg-white border border-blue-200 px-3 py-1 rounded">GET /api/users/read_all_news</code>
        </div>
        <div class="text-3xl">🖥️</div>
      </div>
      <div class="border-t border-blue-200 pt-4 flex items-center gap-3">
        <div class="text-2xl">✅</div>
        <div class="text-sm text-green-700">Risposta: <code class="text-green-700 bg-white border border-green-200 px-2 py-0.5 rounded">200 OK</code> — accesso alle notizie consentito</div>
      </div>
    </div>
  </div>

</div>

---
layout: default
---

# Broken Access Control — Verticale

<div class="flex items-center gap-8 h-4/5">
  <div class="flex flex-col items-center gap-3 w-48 flex-shrink-0">
    <div class="text-7xl">↕️</div>
    <div class="text-center font-bold text-blue-700 text-xl">
      <div>Vertical</div>
      <div>Access Control</div>
    </div>
  </div>
  <div class="flex-1 flex flex-col gap-4">
    <div class="rounded-xl border border-blue-300 bg-blue-50 p-4">
      <div class="flex items-center gap-4">
        <div class="text-4xl">🧑‍💻</div>
        <div class="flex-1">
          <div class="text-xs text-gray-600 mb-1">Utente — ruolo: <span class="text-blue-700 font-semibold">user</span></div>
          <code class="text-blue-700 text-sm bg-white border border-blue-200 px-3 py-1 rounded">GET /api/users/read_all_news</code>
        </div>
        <div class="text-2xl">✅</div>
      </div>
    </div>
    <div class="rounded-xl border border-red-300 bg-red-50 p-4">
      <div class="flex items-center gap-4">
        <div class="text-4xl">🥷</div>
        <div class="flex-1">
          <div class="text-xs text-gray-600 mb-1">Attaccante — ruolo: <span class="text-red-700 font-semibold">user</span> che tenta accesso da <span class="text-red-700 font-semibold">redazione</span></div>
          <code class="text-red-700 text-sm bg-white border border-red-200 px-3 py-1 rounded">POST /api/redazione/write_news</code>
        </div>
        <div class="text-2xl">🔓</div>
      </div>
      <div class="mt-3 text-xs text-red-700 border-t border-red-200 pt-2">
        ⚠️ Se il controllo verticale è assente o rotto, l'utente user riesce a pubblicare notizie — funzionalità riservata alla redazione.
      </div>
    </div>
  </div>
</div>

---
layout: default
---

# Broken Access Control — Orizzontale

<div class="flex items-center gap-8 h-4/5">

  <div class="flex flex-col items-center gap-3 w-48 flex-shrink-0">
    <div class="text-7xl">↔️</div>
    <div class="text-center font-bold text-purple-700 text-xl">
      <div>Horizontal</div>
      <div>Access Control</div>
    </div>
  </div>

  <div class="flex flex-col gap-4 flex-1">
    <div class="rounded-xl border border-purple-300 bg-purple-50 p-4 text-sm text-gray-800 leading-relaxed">
      🎯 Il controllo accessi di tipo <strong class="text-purple-700">«orizzontale»</strong> è un meccanismo che regola l'accesso a risorse dell'applicazione in base all'<strong class="text-purple-700">identità</strong> dell'utente autenticato.
    </div>
    <div class="rounded-xl border border-purple-300 bg-purple-50 p-4 text-sm text-gray-800 leading-relaxed">
      👥 Utenti differenti con lo <strong class="text-purple-700">stesso profilo</strong> hanno accesso allo stesso insieme di funzionalità ma possono visualizzare <strong class="text-purple-700">dati differenti</strong>.
    </div>
    <div class="rounded-xl border border-purple-300 bg-purple-50 p-4 text-sm text-gray-800 leading-relaxed">
      📁 Per esempio un utente può avere il permesso di caricare e modificare i documenti <strong class="text-purple-700">personali o dell'ufficio di appartenenza</strong>, ma non di eseguire le stesse operazioni su documenti di <strong class="text-purple-700">altri utenti o altri uffici</strong>.
    </div>
  </div>

</div>

---
layout: default
---

# Broken Access Control — Orizzontale

<div class="flex items-center gap-8 h-4/5">

  <div class="flex flex-col items-center gap-3 w-48 flex-shrink-0">
    <div class="text-7xl">↔️</div>
    <div class="text-center font-bold text-purple-700 text-xl">
      <div>Horizontal</div>
      <div>Access Control</div>
    </div>
  </div>

  <div class="flex-1">
    <div class="rounded-xl border border-purple-300 bg-purple-50 p-6">
      <div class="flex items-center gap-4 mb-4">
        <div class="text-5xl">👩‍💻</div>
        <div class="flex-1">
          <div class="text-xs text-gray-600 mb-1">Utente autenticata — accede al <span class="text-purple-700 font-semibold">proprio</span> profilo</div>
          <code class="text-purple-700 text-sm bg-white border border-purple-200 px-3 py-1 rounded">GET /api/account/4df66f4/profile</code>
        </div>
        <div class="text-3xl">🖥️</div>
      </div>
      <div class="border-t border-purple-200 pt-4 flex items-center gap-3">
        <div class="text-2xl">✅</div>
        <div class="text-sm text-green-700">Risposta: <code class="text-green-700 bg-white border border-green-200 px-2 py-0.5 rounded">200 OK</code> — profilo personale restituito correttamente</div>
      </div>
    </div>
  </div>

</div>

---
layout: default
---

# Broken Access Control — Orizzontale

<div class="flex items-center gap-8 h-4/5">
  <div class="flex flex-col items-center gap-3 w-48 flex-shrink-0">
    <div class="text-7xl">↔️</div>
    <div class="text-center font-bold text-purple-700 text-xl">
      <div>Horizontal</div>
      <div>Access Control</div>
    </div>
  </div>
  <div class="flex-1 flex flex-col gap-4">
    <div class="rounded-xl border border-purple-300 bg-purple-50 p-4">
      <div class="flex items-center gap-4">
        <div class="text-4xl">👩‍💻</div>
        <div class="flex-1">
          <div class="text-xs text-gray-600 mb-1">Utente — accede al <span class="text-purple-700 font-semibold">proprio</span> profilo</div>
          <code class="text-purple-700 text-sm bg-white border border-purple-200 px-3 py-1 rounded">GET /api/account/4df66f4/profile</code>
        </div>
        <div class="text-2xl">✅</div>
      </div>
    </div>
    <div class="rounded-xl border border-red-300 bg-red-50 p-4">
      <div class="flex items-center gap-4">
        <div class="text-4xl">🥷</div>
        <div class="flex-1">
          <div class="text-xs text-gray-600 mb-1">Attaccante — stesso ruolo, modifica l'ID per accedere al profilo <span class="text-red-700 font-semibold">altrui</span></div>
          <code class="text-red-700 text-sm bg-white border border-red-200 px-3 py-1 rounded">GET /api/account/8rt77p6/profile</code>
        </div>
        <div class="text-2xl">🔓</div>
      </div>
      <div class="mt-3 text-xs text-red-700 border-t border-red-200 pt-2">
        ⚠️ Tecnica IDOR (Insecure Direct Object Reference): sostituendo l'ID nell'URL, l'attaccante accede ai dati di un altro utente con lo stesso livello di privilegi.
      </div>
    </div>
  </div>
</div>