# Informativa privacy di TypoVox

Pagina pubblica servita da GitHub Pages su **privacy.typovox.app**.

Repo separata e pubblica di proposito: GitHub Pages sui piani gratuiti funziona solo da repo
pubbliche, e il codice di TypoVox deve restare privato. Qui c'è solo la pagina.

## Prima di considerarla valida

Nel file `index.html` ci sono due segnaposto evidenziati in giallo. **Finché ci sono,
l'informativa NON è conforme**: l'art. 13 GDPR richiede identità e contatti del titolare, e
Google Play verifica che la policy sia completa.

- `[NOME E COGNOME]` — il titolare del trattamento. Serve il nome reale.
- `[EMAIL]` — compare in due punti (sezione 1 e sezione 7).

Cerca `da-completare` nell'HTML per trovarli.

## Configurazione DNS su Cloudflare

Il dominio `typovox.app` è su Cloudflare. Per far funzionare `privacy.typovox.app`:

1. **DNS → Add record**
   - Type: `CNAME`
   - Name: `privacy`
   - Target: `pipp010.github.io`
   - Proxy status: **DNS only** (nuvoletta grigia, non arancione)

   ⚠️ Il proxy di Cloudflare va **disattivato**: con la nuvoletta arancione GitHub non riesce a
   emettere il certificato TLS e la pagina resta irraggiungibile in HTTPS.

2. **GitHub → Settings → Pages**
   - Source: `Deploy from a branch`, branch `main`, cartella `/ (root)`
   - Custom domain: `privacy.typovox.app`
   - Attendere la verifica, poi spuntare **Enforce HTTPS**

Il file `CNAME` in questa repo comunica già il dominio a GitHub: non va cancellato.

## Dopo la pubblicazione

L'URL `https://privacy.typovox.app` va inserito in **Play Console → Informativa sulla privacy**.
È un requisito bloccante: senza, l'app non entra nemmeno in revisione.

## Cosa manca ancora (fuori da questa repo)

Vedi `PRIVACY.md` nella repo principale:

- Data safety form in Play Console
- Chiarire con un legale il ruolo di OpenRouter (titolare autonomo o responsabile)
- Con l'arrivo dei crediti acquistabili: termini di servizio, Play Billing, e il fatto che
  l'obbligo fiscale di conservazione prevale sul diritto alla cancellazione
