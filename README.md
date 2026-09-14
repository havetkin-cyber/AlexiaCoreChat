# 💬 Alexia Core Chat

Súkromný chat pre Android s koncovým šifrovaním správ aj hovorov. Bez e-mailu, bez telefónneho čísla.

**Aktuálna verzia: 1.2.1**

[⬇️ Stiahnuť najnovšiu verziu](https://github.com/havetkin-cyber/AlexiaCoreChat/releases/latest)

---

## Čo aplikácia vie

### Šifrovanie a bezpečnosť
- ✅ Koncové šifrovanie správ (RSA-2048 + AES-256-GCM)
- ✅ Šifrovaná história správ aj kontakty priamo v telefóne
- ✅ Pripnuté kľúče kontaktov a bezpečnostný kód na overenie
- ✅ Zmena kľúča kontaktu sa viditeľne oznámi
- ✅ Nečitateľné správy sa zmažú a upozornia ťa
- ✅ Správy putujú cez súkromnú databázu, nie cez služby tretích strán
- ✅ Nikto vrátane prevádzkovateľa nevidí, kto komu čo píše
- ✅ K správam sa dostane iba adresát – nikto iný
- ✅ Súkromné kľúče uložené v hardvérovom trezore telefónu

### Doručovanie a hovory
- ✅ Šifrované hlasové hovory
- ✅ Adresa príjemcu sa overuje pri každom odoslaní
- ✅ Upozornenie na zmeškaný hovor pri zastaralom kľúči
- ✅ Kontrola všetkých kontaktov hneď po spustení
- ✅ Notifikácie aj pri zavretej aplikácii

### Účet a PIN
- ✅ Registrácia bez e-mailu – stačí 12-miestne ID a PIN
- ✅ Po troch zlých PINoch sa účet zmaže a ID sa uvoľní
- ✅ Vymazanie účtu aj s uvoľnením ID
- ✅ Zmena PIN kódu v nastaveniach

### Vzhľad
- ✅ Logo v podobe bubliny so správou
- ✅ Úvodná animácia pri spustení
- ✅ Svetlá a tmavá téma vrátane prihlasovacej obrazovky
- ✅ Voľba témy priamo v profile
- ✅ Systémové nastavenia prehľadne pod jednou položkou

### Aktualizácie
- ✅ Automatické aktualizácie priamo v aplikácii
- ✅ Ručná kontrola v Profil → Systém
- ✅ Aktualizácie bez straty správ a kontaktov

---

## Pripravujeme

- ⬜ Mazanie správ zo servera hneď po doručení (najviac 24 hodín čakania)
- ⬜ Nahlasovanie chýb priamo z aplikácie
- ⬜ Webová verzia pre telefóny bez Androidu
- ⬜ Podpora starších Androidov
- ⬜ Spoľahlivejšie spájanie hovorov cez mobilné dáta
- ⬜ Skupinové chaty

---

## Vydané verzie

| Verzia | Čo priniesla | Stav |
|--------|--------------|------|
| 1.0.0 | Prvé vydanie, automatické aktualizácie | vydané |
| 1.1.1 | Oprava pádu po spustení | vydané |
| 1.1.2 | Čistejšia prihlasovacia obrazovka | vydané |
| 1.2.0 | Zmena PIN kódu | vydané |
| **1.2.1** | Voľba témy priamo v profile | **aktuálna** |

---

## Inštalácia

1. Stiahni si súbor `.apk` zo sekcie [Releases](https://github.com/havetkin-cyber/AlexiaCoreChat/releases/latest)
2. V telefóne ho otvor cez **Súbory**
3. Ak sa objaví upozornenie, povoľ **inštaláciu z tohto zdroja**
4. Ťukni na **Inštalovať**

> Ďalšie aktualizácie ti aplikácia ponúkne sama – správy ani kontakty sa pritom nestratia.

---

## Ako to funguje

Pri registrácii dostaneš **12-miestne ID**. To je jediné, čo o sebe komukoľvek prezradíš – žiadny e-mail, žiadne telefónne číslo.

Správy sa zašifrujú priamo v tvojom telefóne a rozšifrovať ich dokáže **iba príjemca**. Kľúč na ich prečítanie neopustí zariadenie.

Všetko beží na **súkromnej databáze** – žiadne cudzie služby.

V databáze nie sú žiadne mená, e-maily ani telefónne čísla – iba náhodné ID a zašifrované správy.

**Ani ja ako prevádzkovateľ nevidím, kto komu píše, ani čo si píšete.** Bez kľúča, ktorý máš v telefóne, je to len nezmyselná zmes znakov. A keďže o tebe neexistuje jediný osobný údaj, nedá sa zistiť, komu tie ID patria.

---

## Požiadavky

- Android 13 alebo novší
- Pripojenie na internet
