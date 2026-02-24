# Broken Access Control Lab

Un laboratorio educativo completo per testare e comprendere le vulnerabilità [Broken Access Control](https://owasp.org/Top10/2025/A01_2025-Broken_Access_Control/) ([OWASP Top 10 #1](https://owasp.org/Top10/2025/A01_2025-Broken_Access_Control/) e [OWASP API Security Top 10 #1](https://owasp.org/API-Security/editions/2023/en/0xa1-broken-object-level-authorization/))  nelle applicazioni Java.

[![License: MIT](https://img.shields.io/badge/License-MIT-teal.svg)](https://opensource.org/licenses/MIT)
[![GitHub pages](https://img.shields.io/badge/GitHub-PAGES-blue.svg)](https://lab-sca.github.io/lab-broken-access-control/)
[![Slides HTML](https://img.shields.io/badge/Slides-HTML-orange.svg)](https://lab-sca.github.io/lab-broken-access-control/slidev/)
[![Slides PDF](https://img.shields.io/badge/Slides-PDF-red.svg)](https://lab-sca.github.io/lab-broken-access-control/lab-broken-access-control.pdf)
[![Fork Me](https://img.shields.io/github/forks/lab-sca/lab-broken-access-control?style=social&label=Fork)](https://github.com/lab-sca/lab-broken-access-control/fork)

## 🚀 Scegli il tuo Framework

Il laboratorio è disponibile in **due versioni** con funzionalità equivalenti:

---

### 🔷 Quarkus

**Cloud-native, supersonic, subatomic Java**

[![Quarkus](https://img.shields.io/badge/Quarkus-4695EB?style=for-the-badge&logo=quarkus&logoColor=white)](https://github.com/lab-sca/lab-broken-access-control-quarkus)

```bash
git clone https://github.com/lab-sca/lab-broken-access-control-quarkus.git
cd lab-broken-access-control-quarkus
mvn quarkus:dev
```

**Tecnologie**: [Quarkus](https://quarkus.io/), [MicroProfile](https://microprofile.io/), JAX-RS, SmallRye JWT, Panache, [Fugerit Venus Doc](https://venusdocs.fugerit.org/)

[📖 Vai al repository →](https://github.com/lab-sca/lab-broken-access-control-quarkus)

---

### 🍃 Spring Boot

**Framework Java più popolare per applicazioni standalone e microservice**

[![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)](https://github.com/lab-sca/lab-broken-access-control-springboot)

```bash
git clone https://github.com/lab-sca/lab-broken-access-control-springboot.git
cd lab-broken-access-control-springboot
mvn spring-boot:run
```

**Tecnologie**:  [Spring Boot](https://spring.io/projects/spring-boot), [Spring MVC](https://docs.spring.io/spring-framework/reference/web/webmvc.html), OAuth2 Resource Server, Spring Data JPA, [Fugerit Venus Doc](https://venusdocs.fugerit.org/)

[📖 Vai al repository →](https://github.com/lab-sca/lab-broken-access-control-springboot)

---

> 🛠️ Inizializzato con [fj-doc-maven-plugin:init](https://venusdocs.fugerit.org/guide/#maven-plugin-goal-init)

---

## 📝 Docs as Code

La presentazione di questo laboratorio è stata realizzata con un approccio **Docs as Code**: il contenuto è scritto in Markdown, versionato insieme al codice sorgente e pubblicato automaticamente tramite GitHub Actions.

Lo strumento utilizzato è [Slidev](https://sli.dev/) — un framework per presentazioni basato su Markdown e Vue.js, pensato per sviluppatori. Permette di scrivere slide come codice, con syntax highlighting, componenti Vue, diagrammi Mermaid e export PDF, il tutto integrato nel normale workflow Git.

> 🔗 Consulta la presentazione online: [HTML](https://lab-sca.github.io/lab-broken-access-control/slidev) · [PDF](https://lab-sca.github.io/lab-broken-access-control/lab-broken-access-control.pdf)