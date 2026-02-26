---
layout: section
---

# Questions & Answers

<div class="text-center italic text-gray-400 text-sm mt-4">
  "I'm not a great programmer; I'm just a good programmer with great habits." — <strong class="text-gray-300">Kent Beck</strong>
</div>

<div class="mt-4"></div>

<div class="rounded-xl border border-blue-300 bg-blue-50 p-5 text-gray-800">
  <div class="text-blue-700 font-semibold text-base mb-3">
    ❓ Come possiamo assicurarci che l'applicazione sia stata testata correttamente?
  </div>
  <div class="text-sm text-gray-700 leading-relaxed">
    Una buona suite di test non si misura solo dal fatto che i test passino, ma da <strong class="text-blue-700">quanto codice viene effettivamente esercitato</strong> e da <strong class="text-blue-700">quanto i test rispecchiano scenari reali</strong> di utilizzo — inclusi quelli legati alla sicurezza. Le slide seguenti approfondiscono due pratiche fondamentali per rispondere a questa domanda.
  </div>
</div>

<div class="rounded-xl border border-purple-300 bg-purple-50 p-4 text-sm text-gray-800 leading-relaxed mt-3">
  💡 A tool di analisi statica della sicurezza come <strong class="text-purple-700">Checkmarx</strong> è possibile affiancare strumenti come <strong class="text-purple-700">SonarQube</strong> che monitorano la qualità e la coverage del codice — due prospettive complementari per una strategia di analisi completa.
</div>

---
layout: default
---

# Unit Test & Code Coverage

<div class="text-center italic text-gray-500 text-sm mb-4">
  "Testing shows the presence, not the absence, of bugs." — <strong class="text-gray-600">Edsger W. Dijkstra</strong>
</div>

<div class="flex flex-col gap-3">
  <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800 leading-relaxed">
    🧪 <strong class="text-blue-700">Code Coverage</strong>: misura la percentuale di codice sorgente eseguita durante i test. Gli unit test verificano che il codice funzioni correttamente e possono testare anche aspetti come la <strong class="text-blue-700">sicurezza</strong> — i test di questo laboratorio ne sono un esempio.
  </div>
  <div class="rounded-xl border border-orange-300 bg-orange-50 p-4 text-sm text-gray-800 leading-relaxed">
    ⚠️ <strong class="text-orange-700">Attenzione:</strong> una coverage bassa aumenta la probabilità di bug e regressioni. Codice mai eseguito durante i test è codice di cui non conosciamo il comportamento — un endpoint dimenticato o un controllo mancante potrebbero nascondere vulnerabilità come la <strong class="text-orange-700">Vuln (X)</strong> del laboratorio.
  </div>
  <div class="rounded-xl border border-green-300 bg-green-50 p-4 text-sm text-gray-800 leading-relaxed">
    ✅ <strong class="text-green-700">Buona pratica:</strong> integrare la misurazione della coverage nella pipeline CI/CD e definire una <strong class="text-green-700">soglia minima</strong> al di sotto della quale la build fallisce.
  </div>
</div>

<div class="flex gap-4 mt-3">
  <div class="flex-1 rounded-xl border border-gray-300 bg-gray-50 p-3 text-xs text-gray-800 text-center">
    <div class="text-2xl mb-1">📊</div>
    <div class="font-bold text-gray-700">JaCoCo</div>
    <div class="text-gray-600 mt-1">Strumento di coverage per Java, si integra con Maven e Gradle. Genera report HTML e XML.</div>
  </div>
  <div class="flex-1 rounded-xl border border-gray-300 bg-gray-50 p-3 text-xs text-gray-800 text-center">
    <div class="text-2xl mb-1">🔍</div>
    <div class="font-bold text-gray-700">SonarQube</div>
    <div class="text-gray-600 mt-1">Piattaforma di analisi statica del codice. Aggrega coverage, code smells, vulnerabilità e security hotspot in un'unica dashboard.</div>
  </div>
</div>

---
layout: default
---

# Integration Test

<div class="text-center italic text-gray-500 text-sm mb-4">
  "Il tutto è maggiore della somma delle sue parti." — <strong class="text-gray-600">Aristotele</strong>
</div>

<div class="flex flex-col gap-3">
  <div class="rounded-xl border border-blue-300 bg-blue-50 p-4 text-sm text-gray-800 leading-relaxed">
    🔗 <strong class="text-blue-700">Integration Test</strong>: verificano che i diversi componenti del sistema funzionino correttamente <strong class="text-blue-700">insieme</strong>. A differenza degli unit test, testano il comportamento dell'applicazione end-to-end — inclusi database, API e controlli di sicurezza.
  </div>
  <div class="rounded-xl border border-orange-300 bg-orange-50 p-4 text-sm text-gray-800 leading-relaxed">
    ⚠️ <strong class="text-orange-700">Attenzione:</strong> un componente può funzionare correttamente in isolamento ma fallire quando integrato con gli altri. I controlli di sicurezza come autenticazione e autorizzazione emergono spesso solo a livello di integrazione — i test di questo laboratorio ne sono un esempio concreto.
  </div>
  <div class="rounded-xl border border-green-300 bg-green-50 p-4 text-sm text-gray-800 leading-relaxed">
    ✅ <strong class="text-green-700">Buona pratica:</strong> affiancare gli unit test con integration test che verifichino i flussi critici, in particolare quelli legati a <strong class="text-green-700">autenticazione, autorizzazione e gestione dei dati sensibili</strong>.
  </div>
</div>

<div class="flex gap-4 mt-3">
  <div class="flex-1 rounded-xl border border-gray-300 bg-gray-50 p-3 text-xs text-gray-800 text-center">
    <div class="font-bold text-gray-700 mb-1">🔷 Quarkus Test</div>
    <div class="text-gray-600"><code>@QuarkusTest</code> + JUnit 5 + RestAssured — avvia l'intera applicazione in modalità test, inclusa la sicurezza.</div>
  </div>
  <div class="flex-1 rounded-xl border border-gray-300 bg-gray-50 p-3 text-xs text-gray-800 text-center">
    <div class="font-bold text-gray-700 mb-1">🍃 Spring Boot Test</div>
    <div class="text-gray-600"><code>@SpringBootTest</code> + JUnit 5 + MockMvc — carica il contesto completo, incluso il <code>SecurityFilterChain</code>.</div>
  </div>
</div>