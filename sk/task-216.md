_**Varovanie:** táto úloha je v testovacom móde a preto môže obsahovať chyby :) neváhajte ich nahlásiť!_

_Nápad na tento problém vychádza z [diskusie s Radovanom Markušom](https://www.codeabbey.com/index/forum_topic/9acb6da256ea0b21d79da93dd5931189#lastPost)._

Tak už sme videli a aj použili [Lineárny Kongruenciálny Generátor](./linear-congruential-generator) pre náhodné čísla.

Doposiaľ je používaný ako predvolený generátor v niektorých jazykoch a platformách, napríklad v jazyku Java
(viz. dokumentácia `java.util.Random`). Bohužiaľ tento generátor nie je dobrý, pokiaľ potrebujeme nejakú
úroveň ochrany. Napríklad ak si vytvoríme online kasíno a použijeme LKG pre generovanie náhodných čísel
v nejakej hre, niekto by ho mohol "hacknúť" - t.j  pozorovať niekoľko hodnôt a predvídať všetky nasledujúce sekvencie!

Existuje mnoho prípadov takejto úlohy založenej na tom, ako sú konečné hodnoty vytvorené z výstupu LKG čísel,
ale poďme si vyskúšať také hackovanie sami s veľmi jednoduchou konfiguráciou.

### Problémový Výrok

Máme LKG a pre každý aktuálnu náhodnú hodnotu `Xcur` vytvára ďalšiu `Xnext` podľa vzorca:

	Xnext = (A * Xcur + C) % M
	
	(kde M je 2^64)

V tejto úlohe je známe `M`, zatiaľ čo  `A` a `C` sú utajené.
V skutočnom živote by aj `M` mohlo byť neznáme, ale tiež by sa dalo uhádnuť hackerom, keby pozoroval viac
náhodných hodnôt, pričom by mal na pamäti, že podľa algoritmu existujú určité obmedzenia pre `M`.

Máme k dispozícií 3 po sebe idúce náhodné čísla a potrebujeme uhádnuť ďalšie.

**Vstupné dáta** obsahuje počet príkladov v prvom riadku. 
Každý príklad je na oddelenom riadku a pozostáva z 3 po sebe idúcich náhodných čísel.  
**Odpoveď** by mala byť nasledujúca hodnota pre každú trojicu.

Príklad:

    vstupné dáta:
	2
	1583335398591491603 4594626647299482044 5406677071358476037
	91747539843581256 16069457834793478749 9723492319865122198
	
	odpoveď:
	12537733515844291054 11832547052504454083

_Tip: Je to iba o riešení systému 2 lineárnych rovníc s 2 neznámymi, akurát v modulárnej aritmetike.
Uistite sa, že viete ako funguje [modulárna inverzia](./modular-inverse) pri delení._
