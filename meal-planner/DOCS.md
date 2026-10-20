# Meal Planner til Home Assistant

Meal Planner giver familien en fælles madplan, opskrifter, brugerprofiler og indkøbslister. AI-forslag og administrationsændringer gemmes først efter din godkendelse.

## Installation
Appen kræver Home Assistant OS med Apps og en aarch64/ARM64-enhed, f.eks. Raspberry Pi 5 med 64-bit Home Assistant OS.
Tilføj https://github.com/clausjuul/home-assistant-apps i Indstillinger → Apps → Installér app → ⋮ → Repositories.
Når første udgivelse er færdig, vises Meal Planner (Development). Installér, start, og vælg Åbn webbrugerflade.

## Flyt fra den lokale ZIP-installation
1. Tag en fuld Home Assistant-backup.
2. Åbn den eksisterende Meal Planner → Indstillinger → Eksportér backup (JSON). Gem filen privat.
3. Installér repository-udgaven ved siden af den lokale app. Afinstallér ikke den gamle endnu.
4. Indtast dine API-nøgler i den nye apps Konfiguration. Nøgler kopieres ikke via madplanens JSON-backup.
5. Start den nye app. Åbn Indstillinger → Gendan en tidligere JSON-backup, og vælg filen.
6. Kontrollér madplan, brugerprofiler, egne opskrifter, indkøbslister og indstillinger. Brug fremover kun den nye app.
7. Behold den gamle installation stoppet, indtil data er kontrolleret og en ny backup er taget.
SQLite-filer og interne snapshots flyttes ikke automatisk mellem de to app-installationer.

## Opdateringer
Nye versioner bliver synlige efter repository-opdatering i Home Assistant. En GitHub-PR eller en ZIP-testpakke er ikke en app-udgivelse.
Vælg Opdater på appens informationsside, når Home Assistant viser en ny version. Slå eventuelt Automatisk opdatering til, hvis funktionen er tilgængelig.
Ved normale opdateringer af samme repository-app bevares /data. Afinstallation er ikke en opdatering.

## Konfiguration
- openai_api_key: din egen OpenAI API-nøgle, hvis du vil bruge OpenAI. API-forbrug kan koste penge.
- prej_api_key: din egen Prej API-nøgle til tilbud.
- Home Assistant-samtaleagent vælges inde i appen, når en kompatibel agent er tilgængelig.
Familiens profiler er lokale madpræferencer, ikke Home Assistant-login. Tekstbaserede kostfiltre er ikke allergencertificering.

## Privatliv
Madplan og profiler ligger i SQLite i appens /data. Ved AI- og tilbudsopslag sendes relevante forespørgsler til de valgte tjenester.
Dette offentlige repository indeholder installationsoplysninger og dokumentation. Docker-imaget er offentligt tilgængeligt og indeholder den kørbare app; personlige madplaner og API-nøgler fra din installation medfølger ikke.
