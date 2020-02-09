*Tento problém sa ku mne dostal cez kolegu na fóre - mal ho na interview pre pozíciu "Ruby-on-Rails" 
web-vývojára a bol trošku zmätený.* 

Asi si spomínate na úlohu so zátvorkami, [Matching Brackets](./matching-brackets). Táto je tiež so zátvorkami, akurát
jedného typu - povedzme, že okrúhle zátvorky.

Reťazec (string) zátvoriek je správny, ak platia nasledovné podmienky:

- počet otváracích zátvoriek je rovnaký ako počet uzatvárajúcich;
- pre každý "prefix" (t.j podreťazec [substring] od začiatku reťazca) počet otvárajúcich zátvoriek je
  väčší alebo rovný počtu uzatvárajúcich zátvoriek.

Napríklad:

    (()(()(())))	 - správna sekvencia
	)()()( 			 - nesprávne, substring(0, 1) obsahuje 1 zatváraciu zátvorku a žiadnu otváraciu
	()(()(())		 - nesprávne, jedna otvárajúca zátvorka je navyše.

###Problémový Výrok

Pre dané `N` je vašou úlohou určiť, koľko správnych zátvoriek by sa dalo spraviť z reťazca dlhého `2N`.

Tu je iba jeden variant pre `N=1`:

    ()

Dve varianty pre `N=2`:

    (())	()()

Päť pre `N=3`:

    ((())) 	(())()	()(())	(()())	()()()

A tak ďalej.

**Vstupné dáta** obsahujú jedinú hodnotu `N`, nie väčšiu ako `400`.  
**Odpoveď** by mala obsahovať presne (aj keď asi veľmi veľký) počet možných variantov..

Príklad:

	vstupné dáta:
	10
	
	odpoveď:
	16796
