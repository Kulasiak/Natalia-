# Gestionale Tabaccheria

Gestionale completo per una tabaccheria italiana, in un unico file HTML. Nessuna
installazione, nessun server, nessuna dipendenza: si apre in qualsiasi browser e
funziona anche senza connessione. I dati restano sul dispositivo, nel browser.

## Sezioni

| Sezione | Cosa fa |
| --- | --- |
| **Oggi** | Incasso, scontrini, aggio maturato e contanti in cassa. Andamento a 7 giorni, ripartizione per reparto, più venduti, avvisi su scorte e mazzette. |
| **Cassa** | Punto vendita: griglia prodotti per reparto, ricerca per nome o codice a barre, carrello con quantità, importo libero per i servizi, pagamento contanti/carta/Satispay con calcolo del resto e scontrino. |
| **Prodotti** | Listino completo: prezzo, aggio o margine, giacenza, scorta minima, codice a barre. Ricerca, filtro per reparto e ordinamento. |
| **Magazzino** | Articoli da riordinare, registro dei movimenti (carico, scarico, rettifica) e inventario valorizzato. |
| **Gratta e Vinci** | Mazzette per taglio e serie, biglietti venduti e residui, chiusura con reso dei residui, aggio sul venduto. |
| **Clienti** | Anagrafica, punti fedeltà, conti aperti (sospesi) con registrazione del pagamento. |
| **Fornitori** | Rubrica dei referenti per rifornimenti e ordini. |
| **Prima nota** | Entrate e uscite di cassa, contanti attesi e chiusura giornaliera con differenza. |
| **Report** | Periodi a 1, 7, 14 e 30 giorni: incasso, aggio, scontrino medio, incasso e aggio per reparto, modalità di pagamento, classifica prodotti, esportazione CSV. |
| **Impostazioni** | Dati della rivendita, aggi e parametri, tema chiaro/scuro/automatico, backup e ripristino, ricarica dei dati dimostrativi. |

## Come si usa

Apri `index.html` con un doppio clic, oppure servi la cartella:

```sh
python3 -m http.server 8000
```

e vai su `http://localhost:8000`.

Su iPhone o iPad, da Safari: **Condividi → Aggiungi a Home**. L'app si apre a
schermo intero come un'applicazione nativa.

Al primo avvio il gestionale si popola con un catalogo realistico di circa 50
articoli e tre settimane di storico, così ogni schermata è già leggibile. Da
**Impostazioni → Azzera vendite e movimenti** si parte dai dati reali mantenendo
il listino.

## Scorciatoie

- `⌘K` o `F2` — apre la cassa
- `Invio` nel campo di ricerca della cassa — aggiunge il prodotto trovato
- `Esc` — chiude la finestra aperta

## Dati e backup

Tutto è salvato in `localStorage`, sotto la chiave `tabaccheria_antonio_v1`. I
dati non escono mai dal dispositivo e non vengono inviati a nessun server.
Poiché sono legati a quel browser, conviene esportare un backup con una certa
regolarità: **Impostazioni → Esporta backup** produce un JSON da copiare e
conservare, **Ripristina backup** lo rilegge.

## Note

Gli aggi impostati (10% sui tabacchi lavorati, 8% sui Gratta e Vinci) sono
quelli di riferimento per le rivendite ordinarie e si modificano da
Impostazioni. Il documento prodotto dalla cassa è un promemoria interno: non
sostituisce il documento commerciale del registratore telematico.

## Struttura

Un solo file, `index.html`, con dentro tutto: design system in stile iOS,
icone SVG, logica e dati. Nessun build step. `vercel.json` serve solo se lo
pubblichi su Vercel.

## Altro in questo repository

`ristorante/` contiene un secondo gestionale, indipendente da questo: un
**sistema completo per ristorante, bar e servizio agli hotel** — sala e piantina
tavoli, comande, monitor cucina, magazzino, personale e turni, colazioni per gli
hotel vicini, briefing giornaliero, slogan, volantini e schermo LED, in sei
lingue (italiano, inglese, francese, spagnolo, tedesco, arabo). Anche quello è un
unico file HTML senza dipendenze: si apre da `ristorante/index.html`. La
documentazione è in [`ristorante/README.md`](ristorante/README.md).
