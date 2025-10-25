# h1 Viisikko

## x) Lue ja tiivistä

### Karvinen 2025: Install Salt on Debian 13 Trixie

- Artikkelissa kerrotaan kuinka ladataan Salt-onfiguraationhallintatyökalu Debian 13-Trixieen. Salt:n avulla voidaan ylläpitää infrastruktuuria koodina (infra-as-code) ja näin hallita isoa määrää Windows- ja Linux-koneita helposti.
- Salt:n asennuksessa tehdään uusi apt-paketti, jonne tulee kaksi tiedostoa, jotka ovat:
  - PGP-julkinen avain: binäärien allekirjoituksen pitää vastata tätä avainta
  - sources.list: URL-osoite, jonne binäärit ladataan, täältä löytyy myös julkinen avain
- Päivitetään paketit ja ladataan wget. Tarkistetaan repositoryn tiedostot. Luotetaan ja asennetaan repository (tässä iso luotto, koska se on sama kuin asentaisimme ohjelmiston koneelle). Asennetaan Salt ja testataan, että se toimii.
- Oma huomio: Näin katsottuna asentaminen näyttäisi onnistuvan helposti, mutta katsotaan miten käytännössä. 

### Karvinen 2023: Run Salt Command Locally

- Saltin avulla voidaan suorittaa komentoja paikallisesti ja tulos nähdään heti. Tämäm takia se soveltuu hyvin harjoitteluun, testaukseen ja nopeaan asennukseen.
- On myös hyvä huomioida, että samat Salt-funktiot toimivat sekä Linuxissa että Windowsissa.
- Tärkeimmät funktiot ovat `pkg`, `file`, `service`, `user` ja `cmd`.
- Artikkelissa ladataan Salt Slave ja kerrotaan miten viisi erilaista komentoa toimivat:
  - `pkg.installed`: asennetaan aplikaatio
  - `file.managed`: tiedostot, Linuxissa ovat tekstitiedostoja
  - `service.running`: demoni on käynnissä eli tätä funktiota käytetään, kun asetuksia on muutettava ja demoni halutaan uudelleenkäynnistää automaattisesti
  -  `user.present`: kertoo käyttäjät
  -  `cmd.run`: komennon suorittaminen, suoritetaan vain silloin, kun muutoksia tarvitaan
- Ohjeet löytyvät komennolla `sudo salt-call --local sys.state_doc`.

### Karvinen 2018: Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux

- Salt:n avulla voidaan hallita tuhatta tietokonetta.
- Hallittavia tietokoneita kutsutaan orjiksi. Ne voivat sijaita missä tahansa: NAT:n tai palomuurin takana tai tuntemattomassa osoitteessa. Silti näitä voidaan hallita.
- Verkossa on yksi isäntä (_master_) ja useita orjia (_slave_ tai _minion_).
- Artikkelissa kerrotaan miten asennetaan isäntä ja orja. Orjan on tiedettävä missä isäntä sijaitsee. Orjalle voi antaa itse nimen (_id_) tai luoda se automaattisesti isäntänimen perusteella. Jokaisella orjalla on oltava eri id.  

### Karvinen 2006: Raportin kirjoittaminen

- Raportoinnissa kerrotaan täsmällisesti mitä teit ja mitä tapahtui. Sitä kirjoitetaan samalla, kun tehdään.
- Raportin on oltava:
  - toistettava: tuloksen pitäisi olla sama, kuka tahansa sen tekeekin, jos se tehdään samassa ympäristössä. Siksi on tärkeää raportoida myös ympäristö, jossa tehtävä ja raportti tehtiin
  - täsmällinen: kirjoita esimerkiksi minkä komennon annoit ja mitä klikkasit. Kellonajat ylös. Onnistuiko vai ei ja millä testillä sen totesit? Raportoi onnistumiset ja ongelmat. Kirjoitetaan imperfektissä
  - helppolukuinen: käytö väliotsikoita ja kirjoita huolellista kieltä
  - viittaa lähteisiin
- Älä sepitä, plagioi tai kopioi kuvia luvattomasti.





## Lähteet

- Karvinen, T. 20.10.2025. Install Salt on Debian 13 Trixie. Luettavissa: https://terokarvinen.com/install-salt-on-debian-13-trixie/. Luettu: 25.10.2025.
- Karvinen, T. 28.10.2021. Run Salt Command Locally. Luettavissa: https://terokarvinen.com/2021/salt-run-command-locally/. Luettu: 25.10.2025.
- Karvinen, T. 28.3.2018. Salt Quickstart – Salt Stack Master and Slave on Ubuntu Linux. Luettavissa: https://terokarvinen.com/2018/03/28/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/. Luettu: 25.10.2025.
- Karvinen, T. 4.6.2006. Raportin kirjoittaminen. Luettavissa: https://terokarvinen.com/2006/06/04/raportin-kirjoittaminen-4/. Luettu: 25.10.2025.
- Pohjana Tero Karvinen 2025: Palvelinten Hallinta. Luettavissa: https://terokarvinen.com/palvelinten-hallinta/. Luettu: 25.10.2025.
