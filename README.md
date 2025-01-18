# swa-recyklace-elektro

## TODO
- [ ] Zadání, popis aplikace, požadavky, další souvislosti
- [ ] UseCase diagram
- [ ] Uživatelské role

### Event oriented architektura
- [ ] Návrh architektury
- [ ] Dokumentace architektury (Component diagram, Deployment diagram)
- [ ] ADR (alespoň 3)
- [ ] Výhody a nevýhody

### Service oriented architektura (SOA)  
- [ ] Návrh architektury
- [ ] Dokumentace architektury (Component diagram, Deployment diagram)
- [ ] ADR (alespoň 3)
- [ ] Výhody a nevýhody

### Zhodnocení
- [ ] Porovnání architektur
- [ ] Výběr vhodnější architektury
- [ ] Zdůvodnění výběru

# Seminární práce
Tento repozitář obsahuje řešení semestrální práce z předmětu `4IT575 Softwarové architektury`.

## Řešitelé
- [Najman Matouš](https://github.com/najmamat) [najmamat]
- [Veis Michael](https://github.com/michaelveis) []
- [Fiedler Josef](https://github.com/fiedler256) [fiedler256]
- [Beran Štěpán](https://github.com/sberan1) [sberan1]

## Zadání
Velký obchod s elektronikou chce začít podnikat v oblasti recyklace elektroniky a potřebuje k tomu nový systém. Zákazníci mohou poslat svá drobná osobní elektronická zařízení nebo využívat místní kiosky v obchodním centru a případně získat peníze za své použité zařízení, pokud je ve funkčním stavu.

### Uživatelé
Stovky, snad tisíce až miliony...

### Požadavky
- Zákazníci mohou získat nabídku na použité osobní elektronické vybavení (telefony, fotoaparáty atd.) buď prostřednictvím webu, nebo kiosku v obchodním centru.
- Zákazníci obdrží poštou krabici, pošlou své elektronické zařízení, a pokud je v dobrém stavu, dostanou zaplaceno.
- Po obdržení zařízení se posoudí/zkontroluje, zda je lze recyklovat/bezpečně zlikvidovat nebo prodat (eBay atd.).
- Společnost předpokládá, že každý měsíc přibude 5-10 nových typů elektroniky, které bude přijímat.

### Další souvislosti
- Jedná se o vysoce konkurenční činnost a je to pro nás nový obor podnikání.
- Pokud jsme určitý typ elektronického zařízení nepřijali za poslední rok ani jednou, odstraníme jej z našeho systému.
- Musíme vést seznam elektronických zařízení, které jsme ochotni přijmout, protože se často mění.
- Každé zařízení má svá vlastní pravidla pro posuzování/kontrolu.
- Máme právo změnit původní cenovou nabídku zákazníkovi, pokud výrobek není v takovém stavu, v jakém byl zákazníkem deklarován.

### Uživatelské role a případy užití

#### Neregistrovaný zákazník
- Může si prohlížet katalog přijímaných zařízení
- Může získat předběžnou cenovou nabídku za své zařízení
- Může se zaregistrovat
- Může využít kiosek v obchodním centru pro získání nabídky

#### Registrovaný zákazník
- Může spravovat své osobní údaje
- Může požádat o zaslání přepravní krabice
- Může sledovat stav své zásilky přes integraci se Zásilkovnou a PPL
- Může přijmout nebo odmítnout upravenou cenovou nabídku
- Může spravovat své platební údaje
- Může hodnotit službu a proces recyklace
- Může komunikovat se zákaznickou podporou

#### Administrátor systému
- Může spravovat katalog přijímaných zařízení
- Může přidávat/upravovat pravidla pro posuzování zařízení
- Může spravovat uživatelské účty a role
- Může generovat reporty a statistiky
- Může nastavovat cenové politiky
- Může spravovat integrace s dopravci

#### Technik (Kontrolor zařízení)
- Může posuzovat přijatá zařízení podle stanovených pravidel
- Může upravovat cenové nabídky na základě skutečného stavu zařízení
- Může označit zařízení jako vhodné k recyklaci/prodeji
- Může iniciovat proces vyplacení zákazníka
- Může dokumentovat stav přijatého zařízení (fotografie, poznámky)

#### Správce prodeje
- Může spravovat nabídky na prodejních platformách (eBay, Aukro)
- Může stanovovat prodejní ceny zařízení
- Může sledovat úspěšnost prodeje na různých platformách
- Může spravovat komunikaci s kupujícími na prodejních platformách
- Může generovat reporty o prodejích

#### Zákaznická podpora
- Může odpovídat na dotazy zákazníků
- Může řešit reklamace a stížnosti
- Může upravovat základní údaje zákazníků
- Může sledovat stav zásilek a informovat zákazníky

