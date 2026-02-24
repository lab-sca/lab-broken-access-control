---
layout: default
---

# Testing — OWASP Testing Guide

<div class="flex flex-col gap-3 mt-4">
  <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800">
    <a href="https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/05-Authorization_Testing/01-Testing_Directory_Traversal_File_Include" class="text-blue-700 font-semibold">4.5.1 Testing Directory Traversal File Include</a>
  </div>
  <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800">
    <a href="https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/05-Authorization_Testing/02-Testing_for_Bypassing_Authorization_Schema" class="text-blue-700 font-semibold">4.5.2 Testing for Bypassing Authorization Schema</a>
  </div>
  <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800">
    <a href="https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/05-Authorization_Testing/03-Testing_for_Privilege_Escalation" class="text-blue-700 font-semibold">4.5.3 Testing for Privilege Escalation</a>
  </div>
  <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800">
    <a href="https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/05-Authorization_Testing/04-Testing_for_Insecure_Direct_Object_References" class="text-blue-700 font-semibold">4.5.4 Testing for Insecure Direct Object References</a>
  </div>
  <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800">
    <a href="https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/05-Authorization_Testing/05-Testing_for_OAuth_Weaknesses" class="text-blue-700 font-semibold">4.5.5 Testing for OAuth Weaknesses</a>
    <div class="ml-4 mt-2 flex flex-col gap-1">
      <div class="text-gray-600">↳ 4.5.5.1 Testing for OAuth Authorization Server Weaknesses</div>
      <div class="text-gray-600">↳ 4.5.5.2 Testing for OAuth Client Weaknesses</div>
    </div>
  </div>
</div>

---
layout: default
---

# Testing — OWASP Testing Guide

<div class="mt-2">
  <div class="text-blue-700 font-semibold text-lg mb-4">4.5.1 Testing Directory Traversal File Include</div>
  <div class="flex flex-col gap-3">
    <div class="rounded-xl border border-orange-300 bg-orange-50 p-4 text-sm text-gray-800 leading-relaxed">
      🔍 Verificare se l'applicazione permette di accedere a file o cartelle non autorizzate usando sequenze come <strong class="text-orange-700">../</strong> o <strong class="text-orange-700">..\</strong> o varianti con URL encoding.
    </div>
    <div class="rounded-xl border border-red-300 bg-red-50 p-4 text-sm text-gray-800 leading-relaxed">
      🥷 L'attaccante tenta di "uscire" dalla directory prevista e accedere a file di sistema, configurazioni, o dati di altri utenti. Testare anche varianti come <strong class="text-red-700">..%2F</strong> o sequenze multiple.
    </div>
    <div class="rounded-xl border border-green-300 bg-green-50 p-4 text-sm text-gray-800 leading-relaxed">
      ✅ Verificare che ci sia adeguata <strong class="text-green-700">sanitizzazione e validazione dei path</strong>. Usare <strong class="text-green-700">whitelist</strong> di file permessi piuttosto che blacklist di caratteri vietati.
    </div>
  </div>
</div>

---
layout: default
---

# Testing — OWASP Testing Guide

<div class="mt-2">
  <div class="text-blue-700 font-semibold text-lg mb-4">4.5.2 Testing for Bypassing Authorization Schema</div>
  <div class="flex flex-col gap-3">
    <div class="rounded-xl border border-red-300 bg-red-50 p-4 text-sm text-gray-800 leading-relaxed">
      🔓 <strong class="text-red-700">Accesso non autenticato</strong> (forced browsing): è possibile accedere a pagine o funzioni dell'applicazione senza autenticazione conoscendo semplicemente la URL?
    </div>
    <div class="rounded-xl border border-orange-300 bg-orange-50 p-4 text-sm text-gray-800 leading-relaxed">
      ↔️ <strong class="text-orange-700">Accesso orizzontale</strong>: con un utente normale è possibile vedere o modificare dati di un altro utente dello stesso ruolo?
    </div>
    <div class="rounded-xl border border-yellow-300 bg-yellow-50 p-4 text-sm text-gray-800 leading-relaxed">
      ↕️ <strong class="text-yellow-700">Accesso verticale</strong>: un utente normale può accedere a funzioni amministrative? Per testare efficacemente, creare utenti con ruoli diversi e provare sistematicamente ad accedere a risorse di altri ruoli.
    </div>
  </div>
</div>

---
layout: default
---

# Testing — OWASP Testing Guide

<div class="mt-2">
  <div class="text-blue-700 font-semibold text-lg mb-3">4.5.3 Testing for Privilege Escalation</div>
  <div class="text-gray-700 text-sm mb-3">Cercare di elevare i privilegi da utente normale ad amministratore. Tecniche comuni:</div>
  <div class="flex flex-col gap-2">
    <div class="rounded-xl border border-red-300 bg-red-50 p-3 text-sm text-gray-800">
      🎭 Manipolazione di <strong class="text-red-700">parametri di ruolo</strong> negli header o nel body (es. <code class="bg-white border border-red-200 px-1 rounded">role=user</code> → <code class="bg-white border border-red-200 px-1 rounded">role=admin</code>)
    </div>
    <div class="rounded-xl border border-red-300 bg-red-50 p-3 text-sm text-gray-800">
      🔑 Manipolazione di <strong class="text-red-700">cookie, JWT token</strong> o campi nascosti contenenti informazioni di ruolo
    </div>
    <div class="rounded-xl border border-red-300 bg-red-50 p-3 text-sm text-gray-800">
      🧪 Test con utenti di ruoli diversi tentando di accedere a funzioni riservate come <code class="bg-white border border-red-200 px-1 rounded">/admin/users</code>, <code class="bg-white border border-red-200 px-1 rounded">/admin/deleteUser</code>, <code class="bg-white border border-red-200 px-1 rounded">/admin/config</code>
    </div>
    <div class="rounded-xl border border-blue-300 bg-blue-50 p-3 text-sm text-gray-800">
      ❓ L'applicazione restituisce <strong class="text-blue-700">403 Forbidden</strong> o esegue l'operazione? Verificare anche cambio ruolo, promozione utenti, gestione permessi.
    </div>
  </div>
</div>

---
layout: default
---

# Testing — OWASP Testing Guide

<div class="mt-2">
  <div class="text-blue-700 font-semibold text-lg mb-4">4.5.4 Testing for Insecure Direct Object References</div>
  <div class="flex flex-col gap-3">
    <div class="rounded-xl border border-orange-300 bg-orange-50 p-4 text-sm text-gray-800 leading-relaxed">
      🔍 Identificare le chiamate HTTP contenenti parametri che referenziano oggetti: <strong class="text-orange-700">ID nelle URL, nei form, nelle API</strong>. Tipicamente sono numeri sequenziali o UUID.
    </div>
    <div class="rounded-xl border border-red-300 bg-red-50 p-4 text-sm text-gray-800 leading-relaxed">
      🥷 Creare risorse con un utente, leggere gli ID, poi con un altro utente tentare di accedere a quegli ID. L'applicazione lascia l'utente B <strong class="text-red-700">vedere, modificare o cancellare</strong> le risorse dell'utente A?
    </div>
    <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800 leading-relaxed">
      👥 Il test per essere efficace deve essere effettuato con <strong class="text-blue-700">almeno due utenti</strong>.
    </div>
  </div>
</div>

---
layout: default
---

# Testing — OWASP Testing Guide

<div class="mt-2">
  <div class="text-blue-700 font-semibold text-lg mb-3">4.5.5 Testing for OAuth Weaknesses</div>
  <div class="flex flex-col gap-3">
    <div class="rounded-xl border border-purple-300 bg-purple-50 p-4 text-sm text-gray-800 leading-relaxed">
      <div class="font-semibold text-purple-700 mb-1">1. Vulnerabilità dell'Authorization Server</div>
      Verificare la correttezza della <strong class="text-purple-700">redirect URI</strong>, la protezione contro <strong class="text-purple-700">CSRF</strong> sul flusso OAuth e la corretta validazione degli <strong class="text-purple-700">scope</strong>.
    </div>
    <div class="rounded-xl border border-purple-300 bg-purple-50 p-4 text-sm text-gray-800 leading-relaxed">
      <div class="font-semibold text-purple-700 mb-1">2. Vulnerabilità del Client</div>
      Il token viene salvato in modo sicuro? Viene trasmesso solo su <strong class="text-purple-700">HTTPS</strong>? Timeout e revoca sono gestiti correttamente? Gli scope richiesti rispettano il <strong class="text-purple-700">least privilege</strong>?
    </div>
    <div class="rounded-xl border border-red-300 bg-red-50 p-4 text-sm text-gray-800 leading-relaxed">
      ⚠️ OAuth è complesso e facile da sbagliare. Configurazioni errate possono permettere <strong class="text-red-700">authorization code interception</strong>, <strong class="text-red-700">token leakage</strong>, <strong class="text-red-700">scope escalation</strong>. Se si usano provider OAuth di terze parti, non presumere che siano sicuri: testare comunque l'integrazione.
    </div>
  </div>
</div>