# Alexia Core Chat

Šifrovaná četovacia aplikácia pre Android bez e-mailu, telefónneho čísla a hesla.
Namiesto účtu slúži 12-miestne ID, prístup chráni PIN.

**Aktuálna verzia: 1.6.1**

---

## V pláne

- [ ] Webová verzia pre telefóny bez Androidu
- [ ] Podpora starších Androidov (teraz je potrebný Android 13+)
- [ ] TURN server, ak by hovory cez mobilné dáta nespájali
- [ ] Skupinové chaty

---

## Hotové

### Šifrovanie a bezpečnosť

- [x] End-to-end šifrovanie správ (RSA-2048 + AES-256-GCM)
- [x] Opravená nefunkčná dešifrovacia funkcia (nesúlad MGF1 v Android Keystore)
- [x] Šifrovaná história správ aj kontakty v telefóne
- [x] Pripnuté kľúče kontaktov + bezpečnostný kód na overenie
- [x] Zmena kľúča kontaktu sa prijme a viditeľne oznámi
- [x] Nečitateľné správy sa zmažú a používateľ je upozornený
- [x] Firestore pravidlá – k správam sa dostane iba adresát
- [x] Súkromné kľúče v hardvérovom Android Keystore, telefón ich nikdy neopustia

### Zvuky a doručovanie

- [x] Používanie systémového zvonenia (melódie/skladby) nastaveného v telefóne pre prichádzajúce hovory
- [x] Používanie systémového zvuku upozornenia nastaveného v telefóne pre nové správy
- [x] Šifrované hlasové hovory (WebRTC, priame spojenie medzi telefónmi)
- [x] Zmeškaný hovor sa zobrazí priamo v chate s daným človekom
- [x] Záznam odmietnutých a uskutočnených hovorov vrátane trvania
- [x] Upozornenie na zmeškaný hovor
- [x] Neprijatý hovor sa ukončí sám po 30 sekundách
- [x] Adresa príjemcu sa overuje pri každom odoslaní
- [x] Upozornenie na zmeškaný hovor pri zastaralom kľúči
- [x] Kontrola všetkých kontaktov hneď po štarte
- [x] Notifikácie aj pri zavretej aplikácii

### Účet a PIN

- [x] Registrácia bez e-mailu – iba 12-miestne ID a PIN
- [x] Po 3 zlých PINoch sa účet zmaže a ID sa uvoľní na serveri
- [x] Vymazanie účtu s uvoľnením ID
- [x] Zmena PIN kódu v nastaveniach

### Nahlasovanie chýb

- [x] Nahlásenie chyby priamo z aplikácie (Profil → Systém)
- [x] K hláseniu sa priloží model telefónu, verzia Androidu a verzia aplikácie
- [x] Moje hlásenia – používateľ vidí odpoveď na svoje hlásenie
- [x] Samostatná správcovská aplikácia na čítanie hlásení a odpovedanie
- [x] Upozornenie pri novom hlásení
- [x] Hlásenia vidí iba ich autor a správca

### Vzhľad

- [x] ID je skryté, kým ho používateľ sám nezobrazí, a dá sa skopírovať
- [x] Logo – bublina so správou
- [x] Úvodná animácia pri spustení
- [x] Svetlá a tmavá téma vrátane prihlasovacej obrazovky
- [x] Téma ako rozbaľovacia položka v profile
- [x] Systémové voľby schované pod položkou Systém

### Aktualizácie

- [x] Automatické aktualizácie z GitHubu
- [x] Kontrola cez `version.json`, záloha cez Releases
- [x] Ručná kontrola v Profil → Systém
- [x] Nová verzia sa nájde aj pri návrate do aplikácie, nielen po úplnom vypnutí
- [x] Podpísaná release verzia vlastným kľúčom

---

## Vydané verzie

| Verzia | Čo prinesla | Stav |
|---|---|---|
| 1.0.0 | Prvé vydanie, automatické aktualizácie | vydané |
| 1.1.0 | Logo a animácia | zmazané – padala |
| 1.1.1 | Oprava pádu po spustení | vydané |
| 1.1.2 | Čistejšia prihlasovacia obrazovka | vydané |
| 1.2.0 | Zmena PIN kódu | vydané |
| 1.2.1 | Téma ako rozbaľovacia položka | vydané |
| 1.3.0 | Nahlasovanie chýb z aplikácie | vydané |
| 1.4.0 | Moje hlásenia, skryté ID | vydané |
| 1.5.0 | Systémové zvuky pre hovory a správy | vydané |
| 1.6.0 | Zmeškané hovory v chate | vydané |
| **1.6.1** | Oprava hľadania aktualizácií | **aktuálna** |

---

## Inštalácia

APK sa nachádza v sekcii [Releases](https://github.com/havetkin-cyber/AlexiaCoreChat/releases).

Súbor `AlexiaCoreChat.apk` je univerzálny – funguje na všetkých procesoroch.
Pri inštalácii treba povoliť inštaláciu z neznámych zdrojov.

**Požiadavka:** Android 13 alebo novší.

Aktualizácie si aplikácia hľadá sama a ponúkne ich pri spustení.

---

## Ako to funguje

Server nevidí obsah správ – prenáša iba zašifrované bloky.
Odosielateľ zašifruje správu verejným kľúčom príjemcu, rozlúštiť ju dokáže
jedine jeho telefón. Hovory idú priamo medzi telefónmi, signalizácia je
šifrovaná rovnakým spôsobom ako správy.

Prezývky kontaktov sú len lokálne – na server sa neposielajú.

Hlásenia chýb sú výnimka: tie šifrované nie sú, aby sa dali spracovať.
Aplikácia na to pri odosielaní upozorní.
