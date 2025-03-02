---
title: Pagine GitLab con Sphinx
teaching: 0
exercises: 0
---

::::::::::::::::::::::::::::::::::::::: objectives

- Publish reStructuredText files as HTML on the web with GitHub Pages

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How do I publish web pages through GitLab and Sphinx?

::::::::::::::::::::::::::::::::::::::::::::::::::

[Sphinx](https://www.sphinx-doc.org/en/master/) è uno strumento per generare pagine web
o PDF, progettato principalmente per creare la documentazione di un progetto. È stato
originariamente creato per la documentazione di Python, ma dispone di ottime strutture
per la documentazione di progetti software in una serie di lingue. I sistemi di
documentazione poliglotta potrebbero essere molto utili nel caso in cui il vostro
progetto aumenti di complessità o di numero di collaboratori, quindi prendete nota di
questo aspetto.

In questo capitolo della lezione utilizzeremo il linguaggio di programmazione Python.
Anche se non è strettamente necessario, vi suggeriamo di familiarizzare con Python,
poiché la sua spiegazione esula dallo scopo di questa lezione. Si può scegliere di farlo
seguendo la lezione di The Carpentries [Programming with
Python](https://swcarpentry.github.io/python-novice-inflammation/).

:::::::::::::::::::::::::::::::::::::::  challenge

## Esercizio: Documentazione

In un gruppo, ogni membro deve aprire la documentazione di uno dei seguenti pacchetti

- [pytest](https://docs.pytest.org/en/latest/)
- [seaborn](https://seaborn.pydata.org/)
- [numpy](https://docs.scipy.org/doc/numpy/reference/)
- [scipy-cookbook](https://scipy-cookbook.readthedocs.io/)
- [scikit-learn](https://scikit-learn.org/stable/)

Discutere quali sono i componenti comuni, cosa c'è di utile in questi siti di
documentazione, come affrontano i concetti generali sulla documentazione, come sono
simili e come sono diversi.

::::::::::::::::::::::::::::::::::::::::::::::::::

Mentre Jekyll converte i file Markdown (`.md`) in HTML, Sphinx converte i file
reStructureText (`.rts`). Sebbene questi due formati possano sembrare molto simili a
prima vista, sono stati creati per due scopi diversi: Markdown per scrivere per il web,
reStructuredText per scrivere documentazione. [Questo post sul
blog](https://www.zverovich.net/2016/06/16/rst-vs-markdown.html) fornisce ulteriori
approfondimenti su cosa significa in pratica, il punto più importante che vorremmo
sottolineare in questo contesto è che reStructuredText è adatto anche alla conversione
in PDF. Questo lo rende uno strumento utile anche per lo sviluppo di documenti che
possono essere necessari sia online che in copia cartacea, ad esempio materiali di
formazione o l'agenda di una riunione.

:::::::::::::::::::::::::::::::::::::::::  callout

## Avvio rapido di Sphinx

Per chiarezza, i prossimi passi di questo capitolo si concentreranno solo sui file di
Sphinx che sono rilevanti per la generazione dei file HTML. Tuttavia, installando
Sphinx in locale, è possibile eseguire il comando quickstart per avviare un progetto
Sphinx di base. Si consiglia vivamente questa opzione se si desidera approfondire la
conoscenza di come documentare con Sphinx. A questo scopo, riportiamo di seguito i
passi necessari.

Probabilmente il vostro sistema ha già installato Sphinx. Verificate se è così
digitando nel vostro terminale:

```bash 
sphinx-build --version
```

Se non lo è, si potrà installare digitando:

```bash 
pip install -U sphinx
```

Oppure consultare istruzioni più dettagliate per l'installazione [qui]
(<https://www.sphinx-doc.org/en/master/usage/installation.html>). Una volta installato
Sphinx, si può eseguire il comando quickstart per avere una panoramica dell'insieme
minimo di file necessari per costruire la documentazione. Il comando seguente creerà
un repository vuoto e vi eseguirà questo comando:

```bash 
mkdir sphinx-quickstart-test
cd sphinx-quickstart-test
sphinx-quickstart
...
Separate source and build directories (y/n) [n]:
...
Project name: My project
Author name(s): <Your name>
Project release []:
...
Project language [en]:
```

Verranno generati diversi documenti. Ecco una panoramica:

![](fig/sphinx-quickstart.png){alt='Sphinx quickstart' .image-with-shadow width="600px"
}

I file rilevanti in questo contesto sono il file `index.rst` - che è l'equivalente del
nostro file `index.md` nell'esempio con Jekyll - e il file `conf.py`. Per questo
motivo la lezione si sofferma solo su di essi.

::::::::::::::::::::::::::::::::::::::::::::::::::

Creare una cartella di progetto vuota. Inizializziamo il nostro file `index.rst` nella
cartella principale del progetto.

```markdown 
.. this is a comment, it is not rendered

Sphinx Example Project's documentation
======================================

Contents:

.. toctree::
    :maxdepth: 2
```

> 
riporta l'intestazione principale del progetto e poi l'indice dei contenuti attraverso
l'"albero TOC". Si può dare un'opzione numerica maxdepth (noi l'abbiamo initalizzata a
2\) per indicare la profondità dell'albero; per impostazione predefinita, tutti i livelli
sono inclusi. Per saperne di più sull'albero Toc consultare [questo
link](https://www.sphinx-doc.org/en/master/usage/restructuredtext/directives.html). In
breve, quando si aggiungono file \*.rst alla nostra tabella dei contenuti, questi devono
essere elencati qui. Aggiungiamo un file per vedere come funziona.

Creare un file `about.rst`, sempre nella cartella principale, con il contenuto:

```markdown 
About
=====

Hello, this is the about page of my project.
```

> 
Ora aggiungiamo questo file all'albero TOC modificando il file `index.rst`:

```markdown 
.. this is a comment, it is not rendered

Sphinx Example Project's documentation
======================================

Contents:

.. toctree::
    :maxdepth: 2

    about.rst
```

> 
Ecco fatto: la nostra home page (generata con il file `index.rst`) ora rimanda alla
pagina About (`about.rst`). Quindi, scriviamo un file minimo `conf.py`, sempre nella
cartella principale.

```bash 
# -- Project information -----------------------------------------------------

project = 'My project'
copyright = '2021, <Your name>'
author = '<Your name>'
release = '1.0'

# -- Options for HTML output -------------------------------------------------

html_theme = 'alabaster'
```

> 
Per un elenco completo delle opzioni che possono essere specificate in questo file,
consultare la
[documentazione](https://www.sphinx-doc.org/en/master/usage/configuration.html).

:::::::::::::::::::::::::::::::::::::::::  callout

## Avvio rapido di Sphinx

Ancora una volta, avere Sphinx installato localmente vi aiuterà nelle fasi successive.
Infatti, è possibile costruire il proprio sito web di documentazione localmente
attraverso il comando `sphinx-build . build/`, da eseguire nella cartella principale.
Una volta eseguito, genererà il sito web di output nella cartella `build/`. È
possibile visualizzarlo semplicemente aprendo il file `index.html` con il proprio
browser preferito.

::::::::::::::::::::::::::::::::::::::::::::::::::

Anche in questo caso, il file `.gitlab-ci.yml` è necessario per specificare le
istruzioni per la distribuzione in GitLab. Compilarlo con:

```yaml 
pages:
  stage: deploy
  image: python:3.6
  script:
    - pip install -U sphinx
    - sphinx-build -b html . public
  artifacts:
    paths:
      - public
```

> 
Questo script: specifica il contenitore per la nostra pipeline (Python, versione 3.6),
installa Sphinx tramite [Pip](https://pypi.org/project/pip/), esegue il comando
`sphinx-build` - che costruisce i file HTML nella cartella principale (`.`) in una
cartella `public`, anch'essa creata. Infine, specifica dove trovare gli artefatti HTML
(nella cartella `public` appunto).

È tutto pronto. Ora dovremmo seguire ancora una volta "Impostazione di un progetto"
nell'[introduzione](https://grp-bio-it-workshops.embl-community.io/building-websites-with-gitlab/01-introduction/index.html)
per impostare un progetto remoto in GitLab, impostandolo come remoto per la nostra
cartella locale con `git remote add origin <git URL>`, `git add . && git commit -m <message>` e poi `git push -u`. Infine, monitorare l'esecuzione della pipeline e
verificare il risultato finale.



:::::::::::::::::::::::::::::::::::::::: keypoints

- Through Sphinx, GitLab serves pages are generated from `.rst` files

::::::::::::::::::::::::::::::::::::::::::::::::::


