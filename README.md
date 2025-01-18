# swa-recyklace-elektro

## TODO
- [ ] Zadání, popis aplikace, požadavky, další souvislosti
- [ ] UseCase diagram
- [ ] Uživatelské role

### Architektura 1
- [ ] Návrh architektury
- [ ] Dokumentace architektury (Component diagram, Deployment diagram)
- [ ] ADR (alespoň 3)
- [ ] Výhody a nevýhody

### Architektura 2  
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
- [Najman Matouš](https://github.com/matousnajman) [najmamat]
- [Veis Michael](https://github.com/michaelveis) []
- [Fiedler Josef](https://github.com/josef-fiedler) [fiedler256]
- [Beran Štěpán](https://github.com/stepanberan) [sberan1]

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
