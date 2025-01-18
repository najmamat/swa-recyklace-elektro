# Zadání seminární práce z předmětu 4IT575 - Softwarové Architektury

**Autoři:** Štěpán Beran, Matouš Najman, Josef Fiedler a Michael Veis

## Úkoly
1. Na základě níže popsaných požadavků navrhněte dvě architektury vhodné pro implementaci dané aplikace.
2. Navržené architektury zdokumentujte.
3. V závěru zhodnoťte, která z vybraných architektur je vhodnější a proč.

## Poznámka
Pokud ze zadání přímo nevyplyne nějaká skutečnost, kterou potřebujete znát, domluvte se ve skupině, a sami ji dodefinujte, tak jako byste se na ni doptali zákazníka.

## Popis aplikace
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