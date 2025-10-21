---
permalink: index.html
site: sandpaper::sandpaper_site
---

:::::::::::::::::::::::::::::::::::::::::  prereq

## Prerequisiti

Prima di seguire questa lezione, gli studenti dovrebbero idealmente essere in grado
di:

1. creare un progetto su [GitLab][gitlab].
2. clonare una copia locale di un progetto con Git, aggiungere e fare il commit dei
  file modificati e fare il push/pull delle modifiche tra i repository locali e
  remoti.
3. eseguire comandi nella shell.

Nessuno dei prerequisiti sopra elencati è assolutamente necessario per seguire la
lezione. Tuttavia, saranno necessari per gestire in modo efficiente lo sviluppo del
sito web dal proprio portatile e per testarne l'aspetto prima di creare versioni
ufficiali.

Se volete imparare una qualsiasi delle abilità elencate sopra, le lezioni di [Software
Carpentry][swc] su [the Shell][swc-shell] e [Git][swc-git] sono un buon punto di
partenza.

::::::::::::::::::::::::::::::::::::::::::::::::::

Per coloro che hanno già familiarità con i modi in cui Git e una piattaforma online come
GitLab o GitHub possono aiutare a tracciare e confrontare le modifiche ai file di testo
e a collaborare con altri progetti, **GitLab** (e GitHub) **Pages** forniscono un modo
gratuito per costruire e ospitare pagine web. Questo approccio è comunemente usato per
fornire documentazione sui progetti software e per creare blog e siti web per individui
e organizzazioni già abituati a lavorare con gli strumenti Git per i loro altri
progetti. Tuttavia, per coloro che muovono i primi passi verso la creazione di siti di
questo tipo, il processo può risultare confuso e intimidatorio. Questo tutorial si
propone di risolvere questo problema

1. fornisce una guida passo-passo alla creazione di una raccolta di pagine,
2. mostra esempi multipli di come strutturarli in un sito coerente,
3. dimostrazione di come usare diversi framework per lo sviluppo di pagine web, dal
  semplice *HTML* a *Jekyll* e *Sphinx*.

Verrà anche discussa brevemente la differenza tra lo sviluppo di pagine GitLab e GitHub.

::::::::::::::::::::::::::::::::::::::::  callout

## Schermate non aggiornate

In questa lezione utilizzeremo e mostreremo contenuti e schermate di
[git.embl.de][embl-gitlab]. Essendo una piattaforma in continua evoluzione,
GitLab aggiunge sempre nuove funzionalità e nuovi elementi visivi al suo sito web.
**Le schermate** della lezione potrebbero quindi risultare non sincronizzate, fare
riferimento o mostrare contenuti che non esistono più.

Se durante la lezione si trovano **screenshot** che non corrispondono più a ciò che si
vede nel browser, si prega di [segnalare un
problema](https://git.embl.de/grp-bio-it-workshops/building-websites-with-gitlab/-/issues)
descrivendo ciò che si vede e come differisce dal contenuto della lezione. Sentitevi
liberi di aggiungere tutte le schermate necessarie per chiarire la discrepanza.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::  objectives

## Obiettivi di apprendimento

Dopo aver seguito questa lezione, gli studenti saranno in grado di:

- **creare** contenuti di pagina formattati con *HTML* o *Markdown*
- **configurare** il proprio progetto per costruire e servire pagine su GitLab
- **costruire** un semplice sito per ospitare contenuti in semplice *HTML*
- **costruire** un sito coerente con più pagine usando il framework *Jekyll* o
  *Sphinx*
- \_\_personalizzare il layout e lo stile delle pagine del loro sito

::::::::::::::::::::::::::::::::::::::::::::::::::



[gitlab]: https://gitlab.com/
[swc]: https://software-carpentry.org/
[swc-shell]: https://swcarpentry.github.io/shell-novice/
[swc-git] : https://swcarpentry.github.io/git-novice/ 





