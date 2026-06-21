# 1-bit ALU

Dette repoet inneholder filer brukt i prosjektet for å utvikle, simulere og teste en enkel proof-of-concept 1-bit ALU. ALU-en kan utføre addisjon og subtraksjon ved hjelp av XOR- og AND-logikk.

## Innhold

### `ALU-testbilder/`

Inneholder bilder fra fysisk testing av ALU-en. Bildene dokumenterer ulike inngangskombinasjoner for addisjon og subtraksjon:

- `add00.jpeg` til `add11.jpeg`: test av addisjon
- `sub00.jpeg` til `sub11.jpeg`: test av subtraksjon
- `V_B_10k.jpeg`: test der 10 kΩ pull-down på B ga ustabil/logisk feil oppførsel
- `V_B_1k.jpeg`: test etter at pull-down på B ble endret til 1 kΩ

### `DEMO_avkoblingskondensator/`

Inneholder demonstrasjon video av hvordan avkoblingskondensatorer stabiliserer strømforsyningen:

- `DEMO_AVC.mp4`: video som viser oscilloskopmåling av strømforsyningen uten og med avkoblingskondensatorer, og hvordan det påvirker stabiliteten i kretsen.

### `litteratur/`

Inneholder relevante dokumenter brukt som støtte i rapporten:

- `Dmor_logisk_algebra.pdf`: relevante regler for De Morgans lover og boolsk algebra
- `Laboppgave_V04_transistors2.pdf`: tidligere labarbeid om transistorer
- `MJ04_ABAY.pdf`: tidligere rapport/labmateriale brukt som bakgrunn

### `simulation/`

Inneholder simuleringsfiler brukt i prosjektet.

- `ALU_PCB_SIM/`: simulering og PCB-relaterte filer for ALU-en
- `GATE OSCILLATOR/`: simulering av astabil multivibrator/klokkesignal

## Prosjektbeskrivelse

Målet med prosjektet var å vise hvordan grunnleggende logiske porter kan kombineres til en enkel aritmetisk-logisk enhet. Kretsen ble først analysert teoretisk, deretter simulert i Proteus og til slutt implementert og testet fysisk på PCB.

Den ferdige ALU-en bruker:

- CD4070BE XOR-port
- SN74LS08N AND-port
- DIP-switcher for inngangene A og B
- knapp for SUB-signal
- LED-er for resultatbit R og carry/borrow C
- pull-down-motstander for stabile innganger
- avkoblingskondensatorer for stabil strømforsyning

## Viktig observasjon

Under fysisk testing fungerte 10 kΩ pull-down for A og SUB, men ikke stabilt for B. Årsaken var at B også var koblet til SN74LS08N, som er en LS-TTL-krets og trekker mer inngangsstrøm enn CMOS-inngangene på CD4070BE. Pull-down-motstanden på B ble derfor endret til 1 kΩ, noe som ga stabil oppførsel.

## Rapport

Repoet brukes som vedlegg/dokumentasjon til prosjektrapporten. Det inneholder testbilder, simuleringsfiler, støttelitteratur og designfiler som dokumenterer arbeidet.
