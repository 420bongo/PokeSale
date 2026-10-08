# PokeSale v2

En full-stack prototype til en dansk Pokémon-kortmarkedsplads.

## Med i v2

- Registrering og login
- Session-baseret brugerprofil
- Redigér profil
- Produktkort/listings med pris, stand, sæt og beskrivelse
- Upload af egne kortbilleder
- Sælgerprofil på hvert kort
- Favoritter
- Intern chat mellem køber og sælger
- Køb-flow med ordrestatus
- Sælger kan markere ordre som sendt
- Køber kan markere modtaget
- SQLite-database
- Responsive UI
- Seed-data med demo-brugere og kort

## Start lokalt

Kræver Node.js 18+.

```bash
npm install
npm start
```

Åbn derefter:

http://localhost:3000

Demo-login:
- `demo@pokesale.dk`
- `Demo1234!`

## Vigtigt om betaling

Køb-flowet i denne version opretter en rigtig ordre i databasen, men der er **ikke koblet en rigtig betalingsgateway på endnu**. Beløbet reserveres ikke hos en bank, og der trækkes ikke penge.

Til produktion bør næste trin være:
- Stripe Checkout eller MobilePay
- rigtig e-mailverificering og password reset
- cloud image storage (S3/Cloudinary)
- PostgreSQL
- rate limiting + CSRF protection
- moderation/reporting
- shipping/integrations
- production session store
- GDPR/cookie/handelsbetingelser

## Arkitektur

`server.js` indeholder API, auth, database og upload-flow. `public/` er frontend. SQLite bruges for at gøre projektet nemt at starte uden ekstern database.
