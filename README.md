Dimitri Stojanovski 223083

2. ![image](https://github.com/Dimitri-jpg/SI_2024_lab2_223083/assets/78219844/e87bdc06-fbcc-4995-894f-4918dcc5c760)
Sekoj red go staviv da bide poseben jazel i taka dobiv 40 jazli cij control flow e daden na grafot na slikata

3. Citogenska kompleksnost e 10

Formula 1: E-N+2 -> E=34, N=26 -> 34-26+2 = 10

Formula 2: 9 Regioni -> 9+1 = 10

Formula 3: Predikatni jazli se 7 od if i 2 od for -> 7+2+1 = 10

4. Every branch kriterium
   ![image](https://github.com/Dimitri-jpg/SI_2024_lab2_223083/assets/78219844/237d2118-60da-4869-97b7-35a2f5b9a92a)

So prvite tri test cases gi dobivam exceptions, dodeka cetvrtiot i pettiot test case se za true i false rezultati od kodot. Dokolku nekoi argumenti se izostaveni ili se ednakvi na anything, togas oni mozat da bidat ednakvi na bilo koja vrednost, dodeka tie argumenti koi se napisani so vrednosti se praveni so takvi kombinacii za site redovi da se izminat so 5 test cases.

5. Multiple condition kriterium

   ![image](https://github.com/Dimitri-jpg/SI_2024_lab2_223083/assets/78219844/7f30b150-34d5-4ee0-947b-9c2d00dd5875)


   Potrebno e cenata da e pogolema od 300, popustot da e pogolem od 0 i barkodot da pocnuva na 0

   Dokolku cenata e pogolema od 300, popustot e pogolem od 0 i barkodot pocnuva na 0, togas od sumata se odzemaat 30 denari
   
   Dokolku cenata e pogolema od 300, popustot e pogolem od 0 i barkodot ne pocnuva na 0, togas od sumata ne se odzemaat 30 denari
   
   Dokolku cenata e pogolema od 300, popustot ne e pogolem od 0 i barkodot ne pocnuva na 0, togas od sumata ne se odzemaat 30 denari
   
   Dokolku cenata e pogolema od 300, popustot ne e pogolem od 0 i barkodot pocnuva na 0, togas od sumata ne se odzemaat 30 denari
   
   Dokolku cenata ne e pogolema od 300, popustot ne e pogolem od 0 i barkodot ne pocnuva na 0, togas od sumata ne se odzemaat 30 denari
   
   Dokolku cenata ne e pogolema od 300, popustot ne e pogolem od 0 i barkodot pocnuva na 0, togas od sumata ne se odzemaat 30 denari
   
   Dokolku cenata ne e pogolema od 300, popustot e pogolem od 0 i barkodot pocnuva na 0, togas od sumata ne se odzemaat 30 denari
   
   Dokolku cenata ne e pogolema od 300, popustot e pogolem od 0 i barkodot ne pocnuva na 0, togas od sumata ne se odzemaat 30 denari

6. Objasnuvanje za test cases po kriteriumite

-Every branch

item1 ne postoi bidejki za prviot test case all items treba da se null. Vo toj slucaj se dava exception i toa e 3-40 patot.
ex = assertThrows(RuntimeException.class, () -> SILab2.checkCart(null, 10));
assertTrue(ex.getMessage().contains("allItems list can't be null!"));

Preku item2 go dobivam vtoriot exception "Invalid character in item barcode!" bidejki bakrodot sodrzi bukva.
private Item item2 = new Item("Dimitri", "a", 100, 0);
ex = assertThrows(RuntimeException.class, () -> SILab2.checkCart(createList(item2), 10));
assertTrue(ex.getMessage().contains("Invalid character in item barcode!"));

Preku item3 vleguvam vo 9tiot jazol bidejki imeto e null i go dobivam tretiot exception bidejki i barkodot e null.
private Item item3 = new Item(null, null, 100, 0);
ex = assertThrows(RuntimeException.class, () -> SILab2.checkCart(createList(item3), 10));
assertTrue(ex.getMessage().contains("No barcode!"));

So golem price vo item4 i mal payment i ostanati validni argumenti, nie proveruvame deka programata ke vrati false vo jazol 38.
private Item item4 = new Item("Dimitri", "0123", 500, 0.5F);
assertFalse(SILab2.checkCart(createList(item4), 10));

So mal price vo item5 i golem payment i ostanati validni argumenti, nie proveruvame deka programata ke vrati true vo jazol 35.
private Item item5 = new Item("Dimitri", "0123", 30, 0);
assertTrue(SILab2.checkCart(createList(item5), 1000));

-Multiple conditions

Koga gledame multiple conditions, bitno e da proverime test cases za true i za false. Za true edinstvena varijanta za uslovite e TTT, dodeka za false moze bilo koja od drugite 7 varijanti pa jas odbrav FFF.

So item6 cenata ni e pogolema od 300, barkodot pocnuva na 0 i popustot ni e pogolem od 0, pa zatoa ke vleze vo if loopot koj go proveruvame.
private Item item6 = new Item("Dimitri", "0123", 400, 0.7F);

So item7 cenata e pomala od 300, barkodot ne pocnuva na 0 i popustot ne e pogolem od 0, pa zatoa nema da vleze vo if loopot koj go proveruvame.
private Item item7 = new Item("Dimitri", "1978", 10, 0);
