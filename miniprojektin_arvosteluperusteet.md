---
layout: page
title: Miniprojektin arvosteluperusteet
inheader: no
permalink: /miniprojektin_arvosteluperusteet/
---

- [Ensimmäisen sprintin arvosteluperusteet](/miniprojektin_arvosteluperusteet#ensimmäisen-sprintin-arvosteluperusteet)


Miniprojektista saa maksimissaan 11 kurssipistettä seuraavien kriteereiden ja periaatteiden mukaan (kurssin eri osioista saatavat pisteet skaalataan ennen kokonaisarvosanan muodostamista)

- Jokaisesta sprintistä on jaossa **ryhmälle** 2.5 kurssipistettä, eli maksimissaan neljästä sprintistä ryhmä voi saada 10 pistettä
  - Ensisijainen arvostelukriteeri on prosessin seuraaminen, tasainen eteneminen ja ohjelmaan toteutettujen ominaisuuksien laatu
  - Toteutettujen ominaisuuksien määrän merkitys arvostelussa on aika pieni mutta ei toki nolla, eli jotain koodiakin tulee tehdä
  - Tarkemmat sprinttikohtaiset arvosteluperusteet alla
- Henkilökohtainen suoriutumisesta on jaossa -1p ... 1, poikkeustapauksissa -2p tai 2p on mahdollinen
  - Henkilökohtaisen suoriutumisen pisteet perustuvat lopussa tehtävään vertaisarvioon sekä ryhmän repositoriosta ja backlogeilta näkyvään "digitaaliseen jalanjälkeen"
  - Henkilökohtaista suoriutumista arvioidessa arvostetaan seuraavia asioita:
    - Fyysistä ja henkistä läsnäoloa
    - Aktiivista otetta
    - Luotettavuutta
    - Ryhmätyön sujuvuutta
    - Työskentelyn tasaisuutta
    - Kontribuutiota ryhmän tuotoksiin (koodi, testit, deployment pipeline, backlogit)
      - [varmista, että committisi näkyvät githubissa oikein](/miniprojektin_arvosteluperusteet#varmista-että-commitisi-näkyvät-githubissa-oikein)
  - **Sankarikoodauksella ei voi kompensoida muuten puutteellista ryhmätyöskentelyä**
  - Kannattaa myös ottaa tosissaan noin 6 tunnin sprinteittäinen työaika. Työajan reilu ylitys ei tuo "lisäpisteitä" vaan pikemminkin päinvastoin.

Perusteeton osallistumattomuus johonkin sprinttiin johtaa miniprojektisuorituksen hylkäämiseen.

### Ensimmäisen sprintin arvosteluperusteet

Projekti tulee olla rekisteröity Timiin. **Tämän lisätään linkki rekisteröintisivulle** Jokaisen ryhmäläisen on oltava rekisteröitynyt projektiin viimeistään ensimmäisen sprintin lopuksi pidettävässä asiakastapaamisessa.

Linkit projektin backlogeihin ja muihin dokumentteihin, ja GitHub Actionsiin (tai muuhun käytössä olevaan CI-palveluun) tulee laittaa projektin GitHub-repositorion README:hen!

Pisteitä kertyy seuraavista asioista:

- (0.25p) product backlog
  - Backlog on DEEP (storyjä ei tarvitse estimoida)
- (0.5p) sprintin 1 backlog
  - Sprintiin valitut user storyt jaettu teknisen tason taskeiksi
  - Päivittäinen jäljellä oleva työmäärä arvioitu taskeittain
  - Sprintin burndown-käyrä olemassa
  - Jokaiseen taskiin on merkitty sen tekijä(t)
  - Taskin status on näkyvissä (esim. todo, doing, done)
- (0.25p) sprintiin 1 valittujen user storyjen hyväksymiskriteerit kirjattu
- (0.25p) testaus
  - Toteutettua koodia on yksikkötestattu kohtuullisella tasolla
- (0.25p) jatkuva integraatio
  - Koodi GitHubissa
  - GitHub Actions (tai jokin muu CI-palvelu) suorittaa yksikkötestit ja ne menevät läpi
- (0.25p) toteutus
  - Ainakin _yksi_ sprintin tavoitteeseen sovituista storyista toteutettu _definition of donen_ mukaisella tasolla
- (0.25p) työtä tehty tasaisesti
  - Kaikki työ ei saa olla yhtenä päivänä tehty
- (0.25p) GitHub README:
  - README:sta löytyy linkki backlogeihin (ja niihin on _kaikilla_ lukuoikeudet)
  - Definition of done kirjattu eksplisiittisesti
  - Linkki sovellukseen jos kyse web-sovelluksesta
  - Jos kyse työpöytäsovelluksesta: ohjelman asennus- ja käyttöohje
- (0.25p) sprintin katselmointiin on valmistauduttu asiallisesti
  - Katselmoinnin pitäjä on sovittu ja tarvittavat esivalmistelut on tehty etukäteen
  - Katselmoinnin aikana asiakkaalle demonstroidaan ne sprinttiin valitut user storyt jotka on toteutettu hyväksymiskriteerien mukaisesti

Sprintin maksimi on 2.5 pistettä.
### Toisen sprintin arvosteluperusteet
TODO
### Toisen sprintin arvosteluperusteet
TODO
### Neljännen sprintin arvosteluperusteet
TODO

### Lopputoimenpiteet

#### Loppudemo ja sprintin 4 päättyminen

Loppudemot pidetään perjantain 24.5. luennolla. Demossa on aikaa max 15 minuuttia per ryhmä. Demon lopussa ryhmä kertoo lyhyesti kokemuksistaan: mikä onnistui hyvin ja mihin jäi parantamisen varaa.


#### Vertaispalaute

- Arvosteluperusteiden alussa mainittu henkilökohtainen pisteytys perustuu mm. vertaispalautteeseen
- Jokaisen ryhmäläisen tulee antaa **vertaispalaute viimeistään perjantaina 24.5. klo 23:59**
  - Vertaispalautteen antaminen on _pakollista_. Jos vertaispalaute puuttuu, ovat miniprojektin henkilökohtaiset pisteet -1.5p
- Vertaispalautteen antaminen tapahtuu Timin kautta **TODO: linkki**
  - Ryhmäläiset eivät näe toistensa vertaispalautteita

#### Raportti

Vertaispalautteen lisäksi ryhmä laatii projektin kulusta pienen raportin (noin 2 sivua)

- Kerrataan jokaisen sprintin aikana kohdatut ongelmat (prosessiin-, projektityöskentelyyn- ja teknisiin asioihin liittyvät)
- Mikä sujui projektissa hyvin, mitä pitäisi parantaa seuraavaa kertaa varten
- Mitä asioita opitte, mitä asioita olisitte halunneet oppia, mikä tuntui turhalta
- Jos raportti puuttuu, vähennetään ryhmältä 2 pistettä
- Raportti palautetaan lisäämällä raporttiin linkki projektin GitHubin README:hen
- Raportista tulee ilmetä jokaisen projektiin osallistuneen nimi
- **Raportin deadline maanantaina 27.5. klo 23:59** Raportin voi kuitenkin palauttaa jo 4. sprintin aikana, kurssin viineisellä viikolla

### Varmista, että commitisi näkyvät GitHubissa oikein

Koska Githubiin tehtävien commitien määrä (ja laatu) vaikuttaa henkilökohtaisiin pisteisiin, varmista, että olet konfiguroinit email-osoitteesi Gitiin (ks. [viikon 1 laskareiden tehtävä 2](/tehtavat1#2-githubiin-versionhallinta)), ja että commitatessasi ryhmäsi repositorioon tunnuksesi näkyy oikein repositorion commit-listalla. On suositeltavaa, että jokainen tekee (omalta koneeltaan) heti alussa yhden testicommitin ja tarkastaa, että Git on konfiguroitu oikein.

### Pariohjelmointi ja commitit

Jos pariohjelmoit (se kannattaa!) saat commitit näkyviin molemmille
[tämän ohjeen](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/creating-a-commit-with-multiple-authors) mukaan.

### Commitit kadoksissa

Jos committisi yhteydessä näkyy (Gitin email-osoitteen konfiguroinnista huolimatta) harmaa symbooli kuten seuraavista alempi

![](https://raw.githubusercontent.com/mluukkai/ohtu2017/master/images/commit1.png)

Klikkaa harmaan commitin nimeä katso mikä on email-osoite, joka commitiin liittyy mutta mitä GitHub ei tunnista osoitteeksesi.

![](https://raw.githubusercontent.com/mluukkai/ohtu2017/master/images/commit2.png)

Lisää osoite _settings_-valikosta:

![](https://raw.githubusercontent.com/mluukkai/ohtu2017/master/images/commit3.png)
