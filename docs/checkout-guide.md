# Checkout di questo fork

Guida documentale del 7 novembre 2026 per il clone locale di `GiacomoGal/agent-zero`. Serve a un lettore umano che deve capire quali contratti restano in vigore e che cosa questa modifica ha spostato.

Il commit di base da cui il testo di prodotto è stato conservato è `b5e110ad0d5915775175b4356c8ad4ca10b1c1f2`. Lo SHA del commit che introduce questa guida sta nella pull request. In questo clone, `HEAD` e il ref locale `origin/main` coincidevano con il commit di base prima della modifica. Quel fatto descrive il clone. Non certifica il ref remoto, la sincronizzazione, la canonicità né un uso vivo. Nessun fetch è stato eseguito.

## Stato che si può affermare

| Fonte | Affermazione |
| --- | --- |
| Inventario locale, sezione 5, 7 novembre 2026 | URL `https://github.com/GiacomoGal/agent-zero`. Ref d’inventario `main`. `fork=True`. `archived=False`. Linguaggio d’inventario non rilevato. Descrizione d’inventario: «Agent Zero AI framework.» |
| Stesso inventario, lifecycle | `identity_proven=false`. `unknowncurrentuse=true`. `nextdocscope=unresolved`. `identity_evidence` vuoto. `proposalOct`, `decisionlater` e `executionreceipt` vuoti. |
| Stesso inventario, UNMAPPED | Nessun abbinamento per nome con servizi, VPS o altri owner. Nessun giudizio di inutilità. |
| `git remote` locale | Origin del clone: `github.com/GiacomoGal/agent-zero`. Il token della URL non è riportato. |
| [`LICENSE`](../LICENSE) righe 3–5 | Copyright 2025 Agent Zero, s.r.o. Contatto `pr@agent-zero.ai`. Repository di progetto indicato: `https://github.com/agent0ai/agent-zero`. |
| [`AGENTS.md`](../AGENTS.md), panoramica | Il documento descrive il framework come in sviluppo attivo e ne elenca lo stack. La data in calce del documento è 2026-03-25. È un’affermazione della guida, non una prova di chi usi questo fork. |

L’albero contiene file Python e JavaScript. Questo è un fatto del checkout. Non corregge il campo «linguaggio non rilevato» dell’inventario e non prova un runtime acceso.

Nessuna proposta con `executed=false` è presente per questo repository. Non c’è una decisione di lifecycle da eseguire, né una riattivazione.

## Come sono stati letti i contratti

Sono stati aperti i Markdown di guida citati nella matrice, la licenza e l’indice dei nomi di `prompts/`. Non sono stati aperti credenziali, `.env`, backup, memorie di chat, il contenuto di `knowledge/`, i dati in `usr/`, il contenuto di `conf/`, i log, i prompt di framework e le sezioni di setup dei plugin che descrivono pairing o credenziali.

Una ricerca testuale di URL su `*.md` ha attraversato anche `knowledge/main/about/architecture.md` e `knowledge/main/about/setup-and-deployment.md` e ne ha mostrato due righe. Quei file non sono stati aperti. Il loro testo non è copiato qui e non è usato come obbligo.

Prompt applicativi, skill, esempi, roadmap e commenti restano al proprio rango. Non diventano policy di questa sessione e non diventano un mandato autonomo. Gli obblighi già scritti non vengono declassati né ristretti.

Gli host sono citati come riferimenti. Nessuno è stato aperto.

## Contratti ricostruiti

### Licenza

Destinatario: chiunque ottenga una copia del software e della documentazione associata. Rango: licenza. Condizioni: l’avviso di copyright e il permission notice vanno inclusi in ogni copia o porzione sostanziale; il software è fornito «AS IS», senza garanzia. Host ref, non aperti: `https://github.com/agent0ai/agent-zero`, `pr@agent-zero.ai`. Destinazione: file invariato.

[`plugins/_skills/LICENSE`](../plugins/_skills/LICENSE) è una seconda licenza MIT, copyright 2026, senza nome del titolare nel file. Stesse condizioni di inclusione dell’avviso. Destinazione: file invariato. Vale per la porzione a cui il file è allegato; non sostituisce la licenza di root.

### Guida operativa degli agenti

Destinatario di [`AGENTS.md`](../AGENTS.md): agenti di codice che lavorano in questo checkout. Rango: guida operativa del workspace. Le sezioni preesistenti restano, comprese Safety and Permissions:

- senza chiedere: leggere file del repository; aggiornare codice in `usr/`;
- chiedere prima: `pip install` di dipendenze nuove; cancellare file di core fuori da `usr/` o `tmp/`; modificare `agent.py` o `initialize.py`; commit o push git;
- mai: commit, hardcode o leak di segreti o `.env`; aggirare CSRF o autenticazione; hardcodare API key.

Le convenzioni di plugin, il runtime Docker descritto (`/opt/venv-a0` e `/opt/venv`) e le regole di release in `.github/workflows/docker-publish.yml` restano quelle scritte in `AGENTS.md`. I file di workflow non sono stati riletti in questo passaggio: la fonte dell’obbligo per gli agenti è il riepilogo già presente in `AGENTS.md`. Destinazione del riepilogo: invariato. Destinazione della guida: una sezione «Checkout scope» in testa, che non cambia rango, destinatario né condizioni delle sezioni sottostanti.

[`CLAUDE.md`](../CLAUDE.md) prima era assente. Destinazione: file nuovo di rinvio. Stesso destinatario. Nessuna seconda lista di permessi e nessuna sincronizzazione di memorie.

### Documentazione di prodotto

Destinatario: lettori umani del prodotto. Rango: documentazione upstream, non policy di sessione. Destinazione del corpo: invariato, sotto la prefazione di [`README.md`](../README.md).

Condizioni che restano in vigore, con la riga della fonte:

| Fonte | Condizione che resta |
| --- | --- |
| `README.md` storico, sezione «Keep in Mind» | Con istruzioni adeguate il framework può compiere azioni pericolose su computer, dati o account. L’ambiente isolato, Docker compreso, è la condizione scritta per l’uso. |
| `docs/setup/installation.md` circa riga 67 | Non cancellare il container vecchio finché il nuovo ha i dati. |
| `docs/setup/installation.md` circa riga 390 | Tenere al sicuro API key e password. Il procedimento di configurazione delle chiavi non è riprodotto qui. |
| `docs/setup/installation.md` circa riga 558 | Impostare username e password in Settings → Authentication prima di un tunnel. |
| `docs/guides/usage.md` circa riga 713 | Autenticazione prima di creare un tunnel. |
| `docs/guides/usage.md` circa riga 1125 | Provare backup e restore in un ambiente sicuro prima di dipenderne. |
| `docs/guides/projects.md` riga 408 | Non commitare `.a0proj/secrets.env`. I segreti di progetto non sono stati letti. |
| `docs/developer/contributing-skills.md`, Community Guidelines | Skill testate, documentate, una competenza per skill, originali; includere una licenza; rispettare le licenze del codice incluso; escludere contenuto proprietario o coperto da copyright altrui. Durante lo sviluppo le skill stanno in `usr/skills/`. |

`docs/guides/contribution.md` ha come destinatario chi contribuisce al progetto Agent Zero. Rango: guida di contributo upstream. Condizioni: fork del repository, branch dedicato, pull request verso il branch `development`, stile PEP 8, documentazione in Markdown. Questa pull request documentale è aperta sul fork `GiacomoGal/agent-zero`. La guida di contributo upstream resta invariata e continua a descrivere il contributo al progetto indicato nei documenti di prodotto.

### Guide tecniche annidate

Destinatario: chi estende interfaccia, plugin o skill. Rango: convenzioni di framework. Destinazione: invariate.

- `docs/agents/AGENTS.plugins.md` si presenta come riferimento per l’architettura plugin. Restano il layout `extensions/python/_functions/...`, il divieto della forma appiattita ritirata, l’uso delle notifiche A0, e la separazione fra `plugin.yaml` e `index.yaml`.
- `docs/agents/AGENTS.components.md` mantiene l’obbligo di avvolgere in un template i componenti che dipendono da uno store.
- `docs/agents/AGENTS.modals.md` mantiene, per il lavoro nuovo, il sistema di modali impilati `openModal` / `closeModal`.
- `docs/agents/AGENTS.banners.md` mantiene le convenzioni delle discovery card.
- `docs/developer/plugins.md` ripete, per il lettore umano, separazione dei manifest e notifiche A0.
- `plugins/README.md` riserva `plugins/` agli aggiornamenti del framework e indica `usr/plugins/` per i plugin custom. Per il Plugin Index richiede una `LICENSE` alla root del repository del plugin. Host ref non aperto: `https://github.com/agent0ai/a0-plugins`.
- `docs/developer/websockets.md` mantiene la validazione dei payload in ingresso. Il dettaglio di protocollo non è stato riesaminato riga per riga.

I README dei plugin in `plugins/_*/README.md` sono guide di prodotto di quei plugin. Ne sono stati letti i titoli. Le sezioni Setup, Configuration e pairing di WhatsApp, Telegram, email e degli altri plugin non sono state estratte. Destinazione: invariati.

### Skill, prompt, profili, esempi

Destinatario delle skill in `skills/*/SKILL.md`: l’agente del framework quando quella skill è caricata. Rango: istruzioni di skill. Non sono policy di questa sessione. Destinazione: invariate.

Obblighi che restano a quel rango, senza essere copiati come mandato di questa modifica:

- `skills/a0-development/SKILL.md`, Best Practices: estendere tramite plugin; sviluppare in `usr/` perché gli aggiornamenti non lo sovrascrivano; non modificare direttamente `plugins/` o `tools/` per le feature nuove; non hardcodare path o configurazioni.
- `skills/a0-review-plugin/SKILL.md`, Phase 4: niente segreti, API key, token o password hardcodati; le altre voci di quella checklist restano nella skill.
- `skills/a0-contribute-plugin/SKILL.md`: una plugin per pull request verso `agent0ai/a0-plugins`; `plugin.yaml` e `index.yaml` hanno schemi distinti. Host ref non aperti.

La stessa skill di sviluppo cita `/a0/docs/contribution.md`. Quel path non c’è in questo albero. Il path presente è `docs/guides/contribution.md`. La skill non è stata corretta: modificarla uscirebbe dal perimetro documentale di questa guida.

`prompts/`, `agents/**/prompts/` e i prompt sotto `plugins/` sono prompt di framework. Ne è stato usato l’elenco dei nomi in `prompts/` per controllare un path citato dal README. Il contenuto non è stato letto e non è policy di sessione. `prompts/agent.system.secrets.md` non è stato aperto. I profili in `agents/*/agent.yaml` non sono stati aperti: restano profili di framework.

Il README di prodotto cita `prompts/default/agent.system.md`. Quel file non è nell’albero. È presente, solo come nome, `prompts/agent.system.main.md`. Il corpo del README non è stato riscritto per aggiornare il path.

Esempi di codice in `AGENTS.md` e nelle skill, commenti e eventuali roadmap restano esempi o note. Non sono stati promossi a obbligo di sessione.

### Procedura VPS e altri comandi

`docs/setup/vps-deployment.md` ha destinatario chi segue la procedura di prodotto su un server Linux generico con Docker. Rango: procedura di prodotto. Intestazione: scopo «deploying Agent Zero instances on VPS/dedicated servers», autore «Auto-generated from deployment experience», data 21 dicembre 2025. Host di esempio nel testo già visto: `127.0.0.1`, `a0.example.com`, `your-domain.com`, oltre agli host di download Docker. Non sono stati aperti. Non identificano un VPS di questo fork. Le sezioni Authentication, SSL/TLS e Domain & DNS compaiono nell’indice; il loro dettaglio operativo non è stato copiato.

I comandi `curl` verso `https://bash.agent-zero.ai`, `irm` verso `https://ps.agent-zero.ai`, `docker run` e `pip install` nel README, in `docs/quickstart.md`, in `docs/setup/installation.md` e in `AGENTS.md` restano procedure soggette a un mandato distinto. Non sono stati eseguiti.

### Materiale non letto e lasciato dov’è

`knowledge/main/about/` è indicato da `AGENTS.md` come self-knowledge dell’agente, non come documentazione per l’utente. Non è stato usato. `usr/` nel checkout tracciato contiene directory con `.gitkeep`. Il contenuto non è stato letto. `conf/` è stato elencato per nome (`model_providers.yaml` e tre `.gitignore`); il contenuto non è stato letto. `.github/workflows/` non è stato modificato e non è stato riletto.

## Matrice fonti → destinazione

| Fonte | Destinatario | Rango | Condizioni che restano | Host ref, non aperti | Destinazione | Motivo |
| --- | --- | --- | --- | --- | --- | --- |
| Inventario locale sezione 5 e perimetro comune, 7 novembre 2026 | Chi scrive e chi rivede questa guida | Mandato documentale locale | Solo Markdown di guida; PR sul fork; uso e identità unknown; niente runtime, sync, deploy, merge, archive | URL del fork e dell’upstream solo come citazione | Prefazione di `README.md`, sezione in `AGENTS.md`, `CLAUDE.md`, questa guida, un rinvio in `docs/README.md` | È lo scopo del mandato: guida esplorativa sobria, adattamento minimo |
| `LICENSE` righe 1–22 | Chi ottiene una copia | Licenza | Includere avviso di copyright e permission; nessuna garanzia | `github.com/agent0ai/agent-zero`, `pr@agent-zero.ai` | Invariato | Il fork conserva la licenza upstream |
| `plugins/_skills/LICENSE` | Chi ottiene quella porzione | Licenza MIT 2026 | Includere l’avviso | Nessuno nel file | Invariato | Licenza annidata distinta, non assorbita |
| `README.md` corpo storico | Lettore umano del prodotto | Documentazione di prodotto | Avviso di pericolo e comandi come procedure | `agent-zero.ai`, `bash.agent-zero.ai`, `ps.agent-zero.ai`, sponsor, issue upstream, Discord, YouTube, LinkedIn, Warpcast, Skool, DeepWiki, Trendshift | Corpo invariato; prefazione aggiunta prima | Adattamento specifico di checkout, non riscrittura del prodotto |
| `AGENTS.md` sezioni preesistenti | Agenti di codice | Guida operativa | Safety, pattern, release, comandi da chiedere prima | `localhost:50001` come default scritto della guida | Sezioni invariate; sezione di ambito in testa | Gli obblighi vigenti non si declassano; lo stato unknown non li sostituisce |
| `CLAUDE.md` assente | Agenti di codice | Rinvio | Stessi obblighi di `AGENTS.md` | Nessuno nuovo | File nuovo di rinvio | Coerenza senza copia e senza memory sync |
| `docs/README.md` | Lettore della documentazione | Hub di prodotto | Link di community verso l’upstream | Discord, GitHub discussions, issue, YouTube | Una frase di rinvio a questa guida; hub invariato nel resto | Il lettore trova lo stato del fork senza una seconda mappa |
| `docs/guides/contribution.md` | Contributori del progetto Agent Zero | Guida di contributo upstream | PR verso `development`; PEP 8; Markdown | Il repository di progetto nominato dagli altri documenti | Invariato | La PR di questo mandato sta sul fork e non riscrive il contributo upstream |
| `docs/agents/AGENTS.*.md`, `docs/developer/plugins.md`, `plugins/README.md` | Chi estende il framework | Convenzioni tecniche | Layout plugin, store gate, modali impilati, due manifest, LICENSE per l’indice | `github.com/agent0ai/a0-plugins` | Invariati | Obblighi annidati ancora vigenti al loro rango |
| `docs/developer/contributing-skills.md` | Autori di skill | Guida di contributo skill | Originalità, licenza, `usr/skills/` in sviluppo | `github.com/agent0ai/agent-zero`, skillsmp.com, skills.sh | Invariato | Stesso criterio |
| `docs/setup/installation.md`, `docs/quickstart.md`, `docs/guides/usage.md`, `docs/guides/projects.md` | Chi segue le procedure di prodotto | Procedure e guide | Chiavi al sicuro; autenticazione prima del tunnel; non commitare `.a0proj/secrets.env`; backup da provare | Host di installazione e community già nel README | Invariati | Dettaglio sensibile omesso; procedure non eseguite |
| `docs/setup/vps-deployment.md` | Chi segue la procedura su un Linux generico | Procedura di prodotto, 21 dicembre 2025 | Prerequisiti generici letti nell’intestazione; auth, SSL e DNS non copiati | `127.0.0.1`, `a0.example.com`, `your-domain.com`, download Docker | Invariato | Procedura generica. Non è un VPS mappato di questo fork |
| `skills/*/SKILL.md` | Agente del framework a skill caricata | Istruzioni di skill | DO/DON’T di sviluppo, niente segreti hardcodati, una plugin per PR sull’indice | `agent0ai/a0-plugins` e URL di esempio nelle skill | Invariati | Non sono policy di sessione; gli obblighi interni restano |
| `prompts/`, prompt in `agents/` e `plugins/`, `agents/*/agent.yaml` | Agente a runtime | Prompt e profili di framework | Non letti, quindi non riformulati | Non raccolti dal contenuto | Invariati | Classe riconosciuta dai path. Contenuto escluso dalla policy di sessione |
| `knowledge/`, `usr/`, `conf/`, log, workflow YAML | — | Materiale non usato come fonte | Non letto, salvo l’attraversamento accidentale indicato sopra | Non raccolti | Invariati | Fuori dal perimetro di lettura |
| Esempi, commenti, roadmap | Lettore dell’esempio | Esempio o nota | Restano esempi | Quelli già nel testo d’origine | Invariati | Non promossi a mandato |

## Verifiche statiche

Controllo sul filesystem del clone, senza rete.

Link interni del README di prodotto che puntano a guide presenti: `docs/setup/installation.md` (esiste anche l’ancora «How to Update Agent Zero»), `docs/setup/dev-setup.md`, `docs/guides/usage.md`, `docs/guides/projects.md`, `docs/developer/websockets.md`, `docs/developer/extensions.md`, `docs/developer/connectivity.md`, `docs/developer/architecture.md`, `docs/guides/contribution.md`, `docs/guides/troubleshooting.md`.

Immagini citate dal README e presenti nell’albero: `docs/res/showcase-thumb.png`, `docs/res/install_guide.png`, `docs/res/ui_screen2.png`, `docs/res/usage/multi-agent.png`, `docs/res/profiles.png`, `docs/res/settings-page-ui1.png`, `docs/res/time_example.jpg`. Nel Markdown alcune usano il path dalla root del repository (`/docs/res/...`); il file c’è, l’URL remoto dell’immagine non è stato aperto. `docs/README.md` cita `res/header.png`, presente in `docs/res/header.png`.

Link interni aggiunti da questa modifica e presenti: `docs/checkout-guide.md`, `AGENTS.md`, `CLAUDE.md`, `LICENSE`, `docs/setup/vps-deployment.md`, `README.md`.

## Limiti

- I link esterni, compresi sito, script di installazione, issue upstream, community e Plugin Index, non sono stati aperti. La loro raggiungibilità è non verificata.
- `docs/guides/contribution.md` rimanda a `development.md` e a `websocket-infrastructure.md` nella stessa cartella. Quei file non ci sono. `../developer/extensions.md` c’è. `docs/developer/websockets.md` c’è con un altro path. I link rotti non sono stati corretti.
- `docs/setup/dev-setup.md` cita `./res/devguide_vid.png`, assente accanto a quel file. Il file `docs/res/devguide_vid.png` c’è. Il link non è stato corretto.
- `README.md` cita `prompts/default/agent.system.md`, assente. Non è stato corretto.
- `skills/a0-development/SKILL.md` cita `/a0/docs/contribution.md`, assente. Non è stato corretto.
- Le guide di installazione, tunnel, VPS, API e MCP contengono altro dettaglio operativo e, in alcuni punti, segnaposto di token. Quel dettaglio non è stato copiato.
- I README dei plugin bundled sono stati classificati dai titoli. Setup e pairing non sono descritti.
- Il contenuto di `knowledge/`, `conf/`, prompt, profili, workflow e dati utente non è fonte di questa guida, con l’eccezione già detta delle due righe attraversate dalla ricerca URL.
- Nessun comando di installazione, test, server, provider, API, SSH, sync, deploy o merge è stato eseguito.
- Questa guida non dichiara il checkout funzionante, integrato, allineato al remoto, né idoneo al PASS. Il PASS, anche solo documentale, spetta a una review indipendente.
