# Informativa privacy di TypoVox

Pagina pubblica servita da GitHub Pages su **privacy.typovox.app**.

Repo separata e pubblica di proposito: GitHub Pages sui piani gratuiti funziona solo da repo
pubbliche, e il codice di TypoVox deve restare privato. Qui c'è solo la pagina.

## ⚠️ Il nome del titolare è volutamente omesso

L'informativa indica come titolare "lo sviluppatore di TypoVox" con l'email di contatto, senza
nome e cognome. **È una scelta consapevole, non una dimenticanza**, presa il 02/08 in attesa di
una consulenza legale quando il progetto crescerà.

Il quadro, per chi la riprenderà in mano:

- L'art. 13(1)(a) GDPR chiede "l'identità e i dati di contatto del titolare" **senza specificare
  il formato**: non dice "nome e cognome", né lo esclude. La norma lascia l'interpretazione alle
  autorità.
- La funzione della norma — che l'interessato sappia a chi rivolgersi e possa farlo — è assolta
  da un'email monitorata.
- L'argomento contrario, che resta serio: davanti a un reclamo il Garante deve poter identificare
  il titolare, e la sola email non è ciò che la norma immagina.
- Fatto pratico: su Google Play il nome dello sviluppatore compare comunque nella scheda dell'app,
  perché Google richiede la verifica dell'identità per gli account personali.

**Quando arriverà la consulenza**, la formula più solida è: `TypoVox — progetto di [Nome Cognome]`.
Si cambia in un punto solo, nella sezione 1.

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
