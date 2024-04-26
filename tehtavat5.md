---
layout: page
title: Viikko 5
inheader: no
permalink: /tehtavat5/
---

{% include miniprojekti_ilmo.md %}

{% include laskari_info.md part=5 %}

Tehtävät liittyvät materiaalin ohjelmistosuunnittelua käsittelevän [osan 4](/osa4/) niihin lukuihin, joihin on merkitty <span style="color:blue">[viikko 5]</span>.

### Typoja tai epäselvyyksiä tehtävissä?

{% include typo_instructions.md %}

{% include norppa.md %}

{% include poetry_ongelma.md %}

**Tehtävät palautetaan** jo edellisillä viikoilla käyttämääsi **palautusrepositorioon**, sinne tehtävän hakemiston _osa5_ sisälle.


### 3. Tenniksen pisteenlaskun refaktorointi

[Kurssirepositorion]({{site.python_exercise_repo_url}}) hakemistossa _viikko5/tennis_, löytyy ohjelma, joka on tarkoitettu tenniksen [pisteenlaskentaan](https://github.com/emilybache/Tennis-Refactoring-Kata#tennis-kata).
- Kopioi projekti palatusrepositorioosi, hakemiston viikko5 sisälle.

Pisteenlaskennan rajapinta on yksinkertainen. Metodi `get_score` kertoo voimassa olevan tilanteen tenniksessä käytetyn pisteenlaskennan määrittelemän tavan mukaan. Sitä mukaa kun jompi kumpi pelaajista voittaa palloja, kutsutaan metodia `won_point`, jossa parametrina on pallon voittanut pelaaja.

Esim. käytettäessä pisteenlaskentaa seuraavasti:

```python
game = TennisGame("player1", "player2")

print(game.get_score())

game.won_point("player1")
print(game.get_score())

game.won_point("player1")
print(game.get_score())

game.won_point("player2")
print(game.get_score())

game.won_point("player1")
print(game.get_score())

game.won_point("player1")
print(game.get_score())
```

tulostuu

```
Love-All
Fifteen-Love
Thirty-Love
Thirty-Fifteen
Forty-Fifteen
Win for player1
```

Tulostuksessa siis kerrotaan mikä on pelitilanne kunkin pallon jälkeen kun _player1_ voittaa ensimmäiset 2 palloa, _player2_ kolmannen pallon ja _player1_ loput 2 palloa.

Pisteenlaskentaohjelman koodi toimii ja sillä on erittäin kattavat testit. Koodi on kuitenkin sisäiseltä laadultaan kelvotonta.

Tehtävänä on refaktoroida koodi luettavuudeltaan mahdollisimman ymmärrettäväksi. Koodissa tulee välttää ["taikanumeroita"](<https://en.wikipedia.org/wiki/Magic_number_(programming)>) ja huonosti nimettyjä muuttujia. Koodi kannattaa jakaa moniin pieniin metodeihin, jotka nimennällään paljastavat oman toimintalogiikkansa.

Etene refaktoroinnissa _todella pienin askelin_. Suorita testejä mahdollisimman usein. Yritä pitää ohjelma koko ajan toimintakunnossa, eli älä hajota testejä. Testeihin ohjelmassa ei tarvitse eikä edes saa koskea.

Jos haluat käyttää jotain muuta kieltä kuin Pythonia, löytyy koodista ja testeistä versioita useilla eri kielillä osoitteesta [https://github.com/emilybache/Tennis-Refactoring-Kata](https://github.com/emilybache/Tennis-Refactoring-Kata).

Tehtävä on kenties hauskinta tehdä pariohjelmoiden. Itse tutustuin tehtävään kesällä 2013 Extreme Programming -konferenssissa järjestetyssä Coding Dojossa, jossa tehtävä tehtiin satunnaisesti valitun parin kanssa pariohjelmoiden.

Lisää samantapaisia refaktorointitehtäviä löytyy Emily Bachen [GitHubista](https://github.com/emilybache).

### 4. Laskin ja komento-oliot

> **HUOM** jos olet käyttänyt kontainerisoitua Poetry-ympäristöä, tämä tehtävä tulee tuottamaan haasteta, sillä sovelluksella on graafinen käyttöliittymä. Googlaa esim. hakusanoilla [linux docker gui apps](https://www.google.com/search?q=linux+docker+gui+apps) jos haluat saada tehtävän tehtyä kontainerissa. Toinen vaihtoehto on esim. pajaan meneminen...

[Kurssirepositorion]({{site.python_exercise_repo_url}}) hakemistossa _viikko5/laskin_ löytyy yksinkertaisen laskimen toteutus. Laskimelle on toteutettu graafinen käyttöliittymä [Tkinter](https://docs.python.org/3/library/tkinter.html)-kirjaston avulla. 
- Kopioi projekti palatusrepositorioosi, hakemiston viikko5 sisälle.

Jos tarvitsee, lue ensin kurssin Ohjelmistotekniikka [materiaalissa](https://ohjelmistotekniikka-hy.github.io/python/tkinter) oleva tkinter-tutoriaali.

Asenna projektin riippuvuudet komennolla `poetry install` ja käynnistä laskin virtuaaliympäristössä komennolla `python3 src/index.py`. Komennon suorittamisen tulisi avata ikkuna, jossa on laskimen käyttöliittymä.

Sovelluksen avulla pystyy tällä hetkellä tekemään yhteen- ja vähennyslaskuja, sekä nollaamaan laskimen arvon. Laskutoimituksen kumoamista varten on lisätty jo painike "Kumoa", joka ei vielä toistaiseksi tee mitään. Sovelluksen varsinainen toimintalogiikka on luokassa `Kayttoliittyma`. Koodissa on tällä hetkellä hieman ikävä `if`-hässäkkä:

```python
def _suorita_komento(self, komento):
    arvo = 0

    try:
        arvo = int(self._syote_kentta.get())
    except Exception:
        pass

    if komento == Komento.SUMMA:
        self._sovelluslogiikka.plus(arvo)
    elif komento == Komento.EROTUS:
        self._sovelluslogiikka.miinus(arvo)
    elif komento == Komento.NOLLAUS:
        self._sovelluslogiikka.nollaa()
    elif komento == Komento.KUMOA:
        pass

    self._kumoa_painike["state"] = constants.NORMAL

    if self._sovelluslogiikka.arvo() == 0:
        self._nollaus_painike["state"] = constants.DISABLED
    else:
        self._nollaus_painike["state"] = constants.NORMAL

    self._syote_kentta.delete(0, constants.END)
    self._arvo_var.set(self._sovelluslogiikka.arvo())
```

Refaktoroi koodi niin, ettei `_suorita_komento`-metodi sisällä pitkää `if`-hässäkkää. Hyödynnä kurssimateriaalin osassa 4 esiteltyä suunnittelumallia [command](/osa4#laskin-ja-komento-olio-viikko-5).

Tässä tehtävässä ei tarvitse vielä toteuttaa kumoa-komennon toiminnallisuutta!

Luokka `Kayttoliittyma` voi näyttää refaktoroituna esimerkiksi seuraavalta:

```python
class Komento(Enum):
    SUMMA = 1
    EROTUS = 2
    NOLLAUS = 3
    KUMOA = 4


class Kayttoliittyma:
    def __init__(self, sovelluslogiikka, root):
        self._sovelluslogiikka = sovelluslogiikka
        self._root = root

        self._komennot = {
            Komento.SUMMA: Summa(sovelluslogiikka, self._lue_syote),
            Komento.EROTUS: Erotus(sovelluslogiikka, self._lue_syote),
            Komento.NOLLAUS: Nollaus(sovelluslogiikka, self._lue_syote),
            Komento.KUMOA: Kumoa(sovelluslogiikka, self._lue_syote) # ei ehkä tarvita täällä...
        }

    # ...

    def _lue_syote(self):
        return self._syote_kentta.get()

    def _suorita_komento(self, komento):
        komento_olio = self._komennot[komento]
        komento_olio.suorita()
        self._kumoa_painike["state"] = constants.NORMAL

        if self._sovelluslogiikka.arvo() == 0:
            self._nollaus_painike["state"] = constants.DISABLED
        else:
            self._nollaus_painike["state"] = constants.NORMAL

        self._syote_kentta.delete(0, constants.END)
        self._arvo_var.set(self._sovelluslogiikka.arvo())
```

Komennoilla on nyt siis metodi `suorita` ja ne saavat konstruktorin kautta `Sovelluslogiikka`-olion ja funktion, jota kutsumalla syötteen voi lukea.

### 5. Komentojen kumoaminen

Toteuta laskimeen myös kumoa-toiminnallisuus. Periaatteena on siis toteuttaa jokaiseen komento-olioon metodi `kumoa`. Olion tulee myös muistaa mikä oli tuloksen arvo ennen komennon suoritusta, jotta se osaa palauttaa laskimen suoritusta edeltävään tilaan.

Jos kumoa-nappia painetaan, suoritetaan sitten edelliseksi suoritetun komento-olion metodi `kumoa`.

Riittää, että ohjelma muistaa edellisen tuloksen, eli kumoa-toimintoa ei tarvitse osata suorittaa kahta tai useampaa kertaa peräkkäin. Tosin tämänkään toiminallisuuden toteutus ei olisi kovin hankalaa, jos edelliset tulokset tallennettaisiin esimerkiksi listaan.

### Vapaaehtoinen bonus-tehtävä

Laajenna ohjelmaasi siten, että se mahdollistaa mielivaltaisen määrän peräkkäisiä kumoamisia. Eli jos olet esim. laskenut summan 1+2+3+4+5 (jonka tulos 16), napin _kumoa_ peräkkäinen painelu vie laskimen tilaan missä tulos on ensin 10 sitten 6, 3, 2, 1 ja lopulta 0.

Myös esim. seuraavanlaisen monimutkaisemman operaatiosarjan pitää toimia oikein: Summa 10, Erotus 6, Erotus 2, Kumoa (kumoaa komennon Erotus 2), Summa 4, Kumoa (Kumoaa komennon Summa 4), Kumoa (kumoaa komennon Erotus 6), Kumoa (kumoaa komennon Summa 10)

### Tehtävien palauttaminen

Pushaa kaikki tekemäsi tehtävät ja GitHubiin palautusrepositorioosi ja merkkaa tekemäsi tehtävät [Timiin](https://tim.jyu.fi/view/kurssit/tie/tjta330/ohjelmistotuotanto-k2024/tehtavat/konfigurointitehtavat-osa-5)

