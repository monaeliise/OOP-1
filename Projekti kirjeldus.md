# "Timukas"

Kursuse "Objektorienteeritud programmeerimine" raames valminud projekt "Timukas" ehk "Hangman" kirjeldus:

Autor: Mona Eliise Mumm



Projekti kirjeldus: 

Projektiks on võetud mäng “Timukas”, inglise keeles tuntud kui “Hangman”. Mängu saab mängida korraga üks mängija. Programmile on etteantud sõnad failis “OOP tekstifail.txt”, kust võetaksegi suvalisi sõnu, mida mängija peab ära arvama. Sõnad on näiteks “vanapaganatagavara”, “kass”, “paradigma”. Eksimise võimalusi on 4, iga vale tähe pakkumisel joonistatakse kriipsujuku osad (pea, käed, keha, jalad). Peale iga tähe arvamist on ka võimalus terve sõna ära arvata, kuid kui tervet sõna õigesti ära ei arvata, siis seda valeks ei loeta ning mäng jätkub. Programmi alguses prinditakse ette lünk “_” nii mitu korda, kui mitu tähte sõnas on. Õige tähe pakkumisel muutuvad kõik lüngad, kus täht peaks olema, selleks täheks. Õige sõna äraarvamisel on mäng võidetud. 



Meetodite eesmärgid:

public static void Programm(String failinimi) throws Exception
 - Selles meetodis toimub programmi peamine töö. Esmalt loetakse sisse argumendina antav fail “OOP tekstifail.txt”, ning asutakse while tsükliga mängu teostama. 
- While tsüklis kasutatakse meetodit SõnaSeis, et jooksvalt näha seda, mis seisus äraarvatav sõna on (mitu tähte on ära arvatud, mitu lünka veel sees on). 
- While tsüklis kasutatakse meetodit Pakkumine, et hallata mängija pakutavaid tähti.
- While tsüklis kasutatakse meetodit prindiMees, et valede vasuste korral hakata kriipsujukut joonistama.

public static boolean Pakkumine(Scanner klaviatuuriInput, String sõna, List<Character> mängijaarvab) 
- Selles meetodis hallatakse mängija pakkumisi. Argumentidena kasutatakse mängija klaviatuuri sisestusi, sõna, ja listi milles sõna tähed on.
- Kui mängija sisestab rohkem kui ühe tähe, näiteks “la”, loetakse vaid esimest tähte, ehk “l”.
- Kui sõnas on pakutav täht, tagastatakse true.

public static boolean SõnaSeis(String sõna, List<Character> mängijaarvab)
- Selles meetodis kontrollitakse, mis seisus sõna on, mitu tähte on ära arvatud, asendatakse tähti lünkadesse.
- Kui mängija on mingi sõnas oleva tähe indeksil i oleva tähe ära arvanud, siis prindime selle tähe välja sellel indeksil kus see täht on lünga “_” asemel.
- Õigel äraarvamisel liidetakse õigete vastuste loendurile (mille pikkus on võrdne tähe pikkusega) üks.
- Kui õigete vastuste loendur on sama väärtusega, mis sõna pikkus, tagastatakse true ja mäng on võidetud.
- Kui tähepakkumine polnud õige, siis sõnas midagi ei muudeta, jääb ikka lünk “_”.

public static void prindiMees(int valeVastuseLoendur)
- Selles meetodis hakatakse välja printima "pootud meest", argumendiks on võetud valede vastuste arv.
- Valel vastamisel tuleb automaatselt kaasa “võll”, mille alla kriipsujukut hakatakse kujutama.
- Kui valesid vastuseid on 1, prinditakse kriipsujuku pea.
- Kui valesid vastuseid on 2, prinditakse kriipsujuku käed.
- Kui valesid vastuseid on 3, prinditakse kriipsujuku keha.
- Kui valesid vastuseid on 4, prinditakse kriipsujuku jalad ja mäng on kaotatud.



Protsessi kirjeldus:

Protsess algas inspiratsiooni otsimisega. Programmi üldise struktuuri ja loogika paikapanemisel aitas see video: https://www.youtube.com/watch?v=_FEdpNUD9M4&ab_channel=CodingwithJohn
Kõigepealt kirjutasin faili “OOP tekstifail.txt” erinevate sõnadega. Video ja OOP-i Zulipi kanalis leiduvate lahenduste abil programmeerisin siis failist lugemise, siis üldise kere programmi töö jaoks, võitmise ja kaotamise tingimused. 



Iga rühmaliikme panus (sh tehtud klassid/meetodid) ja ajakulu (orienteeruvalt):

Tegin projekti üksi, ajakulu oli umbes viis tundi. 



Tegemise mured (nt millistest teadmistest/oskustest tundsite projekti tegemisel puudust):

Mureks tekkis alguses see, et kuidas üldse tuleks realiseerida tähtede äraarvamine (kuidas see terminalis välja nägema peaks, kas kasutada suuri tähti koos väikeste tähtedega või mitte, mida teha kui mängija pakub rohkem kui ühe tähe, kas kasutada õ-sid ä-sid jms). Tundsin puudust listide käsitlemise oskusest. Mureks oli ka see, et programm pole piisavalt keeruline ja originaalne, pole kasutatud erinevaid klasse et tööd põnevamaks muuta. Ajapuudusel valmis siis selline pigem lihtne programm.



Hinnang oma töö lõpptulemusele (millega saite hästi hakkama ja mis vajab arendamist):

Lõpptulemus on rahuldav, mäng töötab. Kuigi prinditavad read on asjalikud, läheb vahel silmapilt veidi kirjuks. Arendada saaks programmi nii, et selle asemel et mängija üksi kuskilt failist sõnu ära arvab, saaks sisse tuua teise mängija kes ise sõna ette annab.



Selgitus ja/või näited, kuidas programmi osi eraldi ja programmi tervikuna testisite ehk kuidas veendusite, et programm töötab korrektselt:

Failist andmete lugemisel testisin, et programm pääseb juurde kõikidele sõnadele mis etteantavas failis on, siis testisin juurdepääsu esimesele sõnale, ja siis suvalisele sõnale.
Meetodi prindiMees kirjutamisel testisin jooksvalt, milline kriipsujuku välja näeb kui vale sisend sisestada, kohendasin tühikuid ja prinditavaid ridu.
Programmi jooksutamisel ja kirjutamisel hoidsin alles rea, mis terminalis koguaeg näitaks äraarvatavat sõna. Lõpus kommenteerisin selle rea välja, jätsin välja kommenteeritud kujul ta koodi sisse, et vajadusel oleks mugavam koodi testida.
Programmi iga tsükli alguses (ehk iga kord kui programm palub mängijal täht sisestada), kujutatakse SõnaSeis.
