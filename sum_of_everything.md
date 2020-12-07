# Pohyb v terminálu

 Ctrl + a Skok na začátek řádku (Home)
 
 Ctrl + e Skok na konec řádku (End)
 
 Ctrl + p Předchozí příkaz (Up arrow)
 
 Ctrl + n Následující příkaz (Down arrow)
 
 Ctrl + f Vpřed o jeden znak (Right arrow)
 
 Ctrl + b Vzad o jeden znak (Left arrow)
 
 Ctrl + xx Přepínání mezi začátkem řádku a aktuální pozicí kurzoru
 
 Ctrl + r Vyhledávání v historii příkazů
 
 Ctrl + Shift + c Kopírování
 
 Ctrl + Shift + v Vkládání
 

# Adresáře 

    // Vytiskne na obrazovku aktuální adresář
    michal@virtual ~ $ pwd
    /home/michal

    // Zobrazení obsahu adresáře
    michal@virtual ~ $ ls
    Desktop  Documents  Downloads  fontconfig  Music  Pictures  Public  Templates  Videos

    // Obsah adrešáře s podrobnějšími informacemi (velikost, datum, jméno)
    michal@virtual ~ $ ls -l
    total 36
    drwxr-xr-x 2 michal michal 4096 Jan 29 19:08 Desktop
    drwxr-xr-x 2 michal michal 4096 Jan 29 18:46 Documents
    drwxr-xr-x 2 michal michal 4096 Jan 29 18:50 Downloads
    drwxrwxr-x 2 michal michal 4096 Feb 10 21:32 fontconfig
    drwxr-xr-x 2 michal michal 4096 Jan 29 18:46 Music
    drwxr-xr-x 2 michal michal 4096 Jan 29 18:46 Pictures
    drwxr-xr-x 2 michal michal 4096 Jan 29 18:46 Public
    drwxr-xr-x 2 michal michal 4096 Jan 29 18:46 Templates
    drwxr-xr-x 2 michal michal 4096 Jan 29 18:46 Videos

    // Zobrazení všech souborů a adresářů
    michal@virtual ~ $ ls -a
    .              .cache     Downloads    .kde        Pictures                   Templates
    ..             .config    fontconfig   .local      .profile                   Videos
    .bash_history  .dbus      .fontconfig  .mozilla    Public                     .Xauthority
    .bash_logout   Desktop    .gconf       Music       .ssh                       .xsession-errors
    .bashrc        Documents  .gtkrc-2.0   .parallels  .sudo_as_admin_successful

    // Kombinace přepinačů -l -a
    michal@virtual ~ $ ls -la
    total 200
    drwxr-xr-x 21 michal michal  4096 Feb 11 10:35 .
    drwxr-xr-x  3 root  root   4096 Jan 29 18:43 ..
    -rw-------  1 michal michal    89 Jan 29 19:16 .bash_history
    -rw-r--r--  1 michal michal   220 Jan 29 18:43 .bash_logout
    -rw-r--r--  1 michal michal  4000 Jan 29 18:43 .bashrc
    drwxrwxr-x 11 michal michal  4096 Feb 11 10:40 .cache
    drwxr-xr-x 14 michal michal  4096 Feb 10 21:37 .config
    drwx------  3 michal michal  4096 Jan 29 18:46 .dbus
    drwxr-xr-x  2 michal michal  4096 Jan 29 19:08 Desktop
    drwxr-xr-x  2 michal michal  4096 Jan 29 18:46 Documents
    drwxr-xr-x  2 michal michal  4096 Jan 29 18:50 Downloads
    drwxrwxr-x  2 michal michal  4096 Feb 10 21:32 fontconfig
    drwxrwxr-x  2 michal michal  4096 Jan 29 18:47 .fontconfig

    // Změna adresáře
    michal@virtual ~ $ cd public_html/

    michal@virtual ~/public_html $

    // Speciální adresáře

    // . Aktuální adresář
    michal@virtual ~/public_html $ ls .
    index.html

    // .. Nadřazený adresář
    michal@virtual ~/public_html $ ls ..
    Desktop  Documents  Downloads  fontconfig  Music  Pictures  Public  public_html  Templates  Videos

    // Vytvoření složky
    michal@virtual ~ $ mkdir pokusy

    michal@virtual ~ $ cd pokusy

# Obsah souborů

    // Vytvoření souboru
    michal@virtual ~/pokusy $ touch text.txt

    michal@virtual ~/pokusy $ ls -l
    total 0
    -rw-rw-r-- 1 roman roman 0 Feb 11 11:53 text.txt // nulová velikost

    // Typ souboru
    michal@virtual ~/pokusy $ file text.txt
    text.txt: empty

    // Otevření souboru v programu gedit a vložení textu "Hello World"
    michal@virtual ~/pokusy $ gedit text.txt

    roman@virtual ~/pokusy $ ls -l
    total 4
    -rw-rw-r-- 1 roman roman 14 Feb 11 11:57 text.txt

    roman@virtual ~/pokusy $ file text.txt
    text.txt: ASCII text

    // Výpis obsahu souboru do konzole
    roman@virtual ~/pokusy $ cat text.txt
    Hello world!!

    less text.txt

# Manipulace se soubory

    // Kopírování
    michal@virtual ~/pokusy $ cp text.txt kopie.txt

    // Přesun (přejmenování)
    michal@virtual ~/pokusy $ mv kopie.txt copy.txt

    // Smazání souboru
    michal@virtual ~/pokusy $ rm copy.txt

    michal@virtual ~/pokusy $ rm copy.txt
    rm: cannot remove 'copy.txt': No such file or directory

    // Potlačení chybových hlášek
    michal@virtual ~/pokusy $ rm -f copy.txt

    // Kopírování adresáře
    michal@virtual ~ $ cp pokusy pokusy2
    cp: omitting directory 'pokusy'

    michal@virtual ~ $ cp -r pokusy pokusy2

    michal@virtual ~ $ rm pokusy2
    rm: cannot remove 'pokusy2': Is a directory

    michal@virtual ~ $ rm -r pokusy2

    michal@virtual ~ $ rm -rf pokusy2

# Symbolický odkaz

    michal@virtual ~/pokusy $ cp text.txt kopie.txt

    // Vytvoří symbolický odkaz mezi soubory
    michal@virtual ~/pokusy $ ln -s kopie.txt odkaz.txt
    michal@virtual ~/pokusy $ ls -l // Odkaz

    michal@virtual ~/pokusy $ rm kopie.txt
    michal@virtual ~/pokusy $ ls -l  // Rozbitý odkaz

    michal@virtual ~/pokusy $ cp text.txt kopie.txt
    michal@virtual ~/pokusy $ ls -l

    michal@virtual ~/pokusy $ rm odkaz.txt
    michal@virtual ~/pokusy $ ls -l
# Přístupová práva

    // Zjístění práv
    michal@virtual ~/pokusy $ ls -l
    total 4
    -rw-rw-r-- 1 michal michal 14 Feb 11 11:57 text.txt // (práva, vlastník, skupina)

    // Odebrání práva zápisu
    michal@virtual ~/pokusy $ chmod u-w text.txt
    michal@virtual ~/pokusy $ gedit text.txt // Nelze uložit

    // Odebrání práva na čtení
    michal@virtual ~/pokusy $ chmod u-r text.txt

    michal@virtual ~/pokusy $ cat text.txt
    cat: text.txt: Permission denied

    // Vrácení práv zpět
    michal@virtual ~/pokusy $ chmod u+rw text.txt

    // Odebrání práva spouštění adresáři
    michal@virtual ~ $ chmod u-x pokusy

    michal@virtual ~ $ ls pokusy/
    ls: cannot access 'pokusy/text.txt': Permission denied
    text.txt

    michal@virtual ~ $ cd pokusy/
    bash: cd: pokusy/: Permission denied

    michal@virtual ~ $ touch pokusy/soubor.txt
    touch: cannot touch 'pokusy/soubor.txt': Permission denied

    michal@virtual ~ $ chmod u-r pokusy

    michal@virtual ~ $  ls pokusy
    ls: cannot open directory 'pokusy': Permission denied

    michal@virtual ~ $ chmod u+x pokusy

    michal@virtual ~ $ cd pokusy
    michal@virtual ~/pokusy $ ls
    ls: cannot open directory '.': Permission denied

    michal@virtual ~/pokusy $ cat text.txt
    Hello world!!

    michal@virtual ~/pokusy $ cd ..

    // Přiřazení práv pro čtení a spuštění
    michal@virtual ~ $ chmod u=rx pokusy/
    michal@virtual ~ $ touch pokusy/soubor.txt
    touch: cannot touch 'pokusy/soubor.txt': Permission denied

    // Přidání práva zápisu
    michal@virtual ~ $ chmod u+w pokusy/
    michal@virtual ~ $ touch pokusy/soubor.txt

    // hodnota	právo
    // 0	---
    // 1	--x
    // 2	-w-
    // 3	-wx
    // 4	r--
    // 5	r-x
    // 6	rw-
    // 7	rwx

# Výpis procesů

    michal@virtual ~ $ chmod 721 soubor.txt
    michal@virtual ~ $ chmod 711 public_html

    // UNIX přepínače, -e
    // BSD přepínače, aux

    // Vypíše procesy které ovládá terminál
    michal@virtual ~ $ ps

    // Vypíše procesy vlastněné uživatelem
    michal@virtual ~ $ ps x

    // Procesy vlastněné uživatelem hajny
    michal@virtual ~ $ ps -u hajny

    // Procesy vlastněné uživatelem hajny se zobrazenými sloupci pid, s, cmd
    michal@virtual ~ $ ps -u hajny -o pid,s,cmd

    // Vypíše všechny procesy
    michal@virtual ~ $ ps ax/ps -e

    // Všechny procesy v užitelsky přívětivém formátu
    michal@virtual ~ $ ps aux/ps -ef/ps -eF ()

    // Vypíše všechny procesy ve stromové struktuře
    michal@virtual ~ $ ps auxf/ps -efH

    // Vypíše jen určité sloupce
    michal@virtual ~ $ ps axo pid
    michal@virtual ~ $ ps -eo pid

    // Vypíše proces na základě jména
    michal@virtual ~ $ ps -C bash

    // Vypíše strom procesu
    michal@virtual ~ $ pstree

    // Vypíše strom společně s argumenty
    michal@virtual ~ $ pstree -a

    // Vypíše strom společně s PID
    michal@virtual ~ $ pstree -p
    

# Ukončení procesu
    

    // Spustíme libovolný program
    michal@virtual ~ $ gedit

    // Získáme PID
    michal@virtual ~ $ ps x

    // Ukončí aplikaci
    michal@virtual ~ $ kill pid (TERM)

    // Znovu spustíme aplikaci gedit
    michal@virtual ~ $ gedit

    // Zastaví aplikaci
    michal@virtual ~ $ kill -STOP pid

    // Probudí aplikaci
    michal@virtual ~ $ kill -CONT pid

    // Ukončí proces okamžitě
    michal@virtual ~ $ kill -KILL pid

    // Seznam všech signálů
    michal@virtual ~ $ kill -l

    // Znovu spustíme aplikaci gedit
    michal@virtual ~ $ gedit

    // Ukončí všechny instance programu gedit
    michal@virtual ~ $ killall gedit

    // Ukončí terminál i se všemi potomky
    michal@virtual ~ $ kill -KILL pid_terminalu
    

# Řízení úloh
    

    // Spuštění úlohy na pozadí
    michal@virtual ~ $ gnome-calculator &
    [1] 4468

    // Vypíše bežící procesy
    michal@virtual ~ $ jobs
    [1]+  Running                 gnome-calculator &

    // Vypíše běžící procesy společně s PID
    michal@virtual ~ $ jobs -l
    [1]+  4468 Running                 gnome-calculator &

    // Spustíme program gucharmap
    michal@virtual ~ $ gucharmap

    // Pomocí Ctrl + z jej zastavíme
    ^Z
    [2]+  Stopped                 gucharmap

    // Přenesení na pozadí
    michal@virtual ~ $ bg
    [2]+ gucharmap &

    // Přenesení posledního programu na popředí
    michal@virtual ~ $ fg
    gucharmap

    // Přeneseme gucharmap na pozadí
    // Přeneseme gnome-calculator na popředí
    michal@virtual ~ $ fg 1
    gnome-calculator

    // Pomocí Ctrl + c ukončíme gnome-calculator
    // Pomocí Ctrl + d ukončíme terminál a gucharmap stále běží
    

# Expanze jmen souborů a adresářů
    

    michal@virtual ~ $ echo ~
    /home/michal

    michal@virtual ~ $ echo *
    Desktop Documents Downloads fontconfig Music passwords
    Pictures pokusy Public public_html Templates Videos

    michal@virtual ~ $ echo p*
    passwords pokusy public_html

    michal@virtual ~ $ ls p*
    passwords

    pokusy:
    soubor.txt  text.txt

    public_html:
    index.html

    michal@virtual ~ $ echo pokus?
    pokusy

    michal@virtual ~ $ echo p[a-o]*
    passwords pokusy

    michal@virtual ~ $ echo \*
    *

    michal@virtual ~ $ echo '*'
    *

    michal@virtual ~ $ echo "*"
    *

    michal@virtual ~ $ echo \'
    '

    michal@virtual ~ $ echo \\
    \

    michal@virtual ~ $ echo &
    [1] 8389

    michal@virtual ~ $ echo \&
    &

    michal@virtual ~ $ echo    a
    a

    michal@virtual ~ $ echo '   a'
       a
       
# Příkaz head

    // Vypíše prvních 10 řádků souboru
    head procesy.txt

    // Vypíše prvních 10 řádků z každého souboru
    head procesy.txt procesy2.txt

    // Udělá to samé co předchozí ale nevypisuje hlavičku
    head -q procesy.txt procesy2.txt

    // Vypíše 2 řádky od začátku souboru
    head -n 2  procesy.txt
    head -2 procesy.txt

    // Vrátí prvních n bajtů
    head -c 5 procesy.txt

    // Přesměrování do souboru
    head -n 2 procesy.txt > qux.txt

    // Použití roury
    ls | head

    // Presměrování na konec souboru
    ls | head >> baz.txt
    
# Příkaz tail

    // Vypíše posledních 10 řádků souboru
    tail procesy.txt

    // Vypíše posledních 10 řádků z každého souboru
    tail procesy.txt procesy2.txt

    // Udělá to samé co předchozí ale nevypisuje hlavičku
    tail -q procesy.txt procesy2.txt

    // Vypíše 2 řádky od konce souboru
    tail -n 2  procesy.txt
    tail -2 procesy.txt

    // Vrátí posledních n bajtů
    tail -c 5 procesy.txt

    // Přesměrování do souboru
    tail -n 2 procesy.txt > qux.txt

    // Použití roury
    ls | tail

    // Presměrování na konec souboru
    ls | tail >> baz.txt
   
# Příkaz wc

    // Vrátí počet řádků, slov a bitů v souboru
    wc procesy.txt

    // Vrátí počet řádků
    wc -l procesy.txt

    // Vrátí počet znaku
    wc -m procesy.txt

    // Vrátí počet slov
    wc -w procesy.txt
    
# Příkaz tac

Zobrazí obsah souboru na std výstupu ale v opačném pořadí. 

    tac file.txt

# Příkaz rev

Obrátí pořadí znaků v řetězci.

    echo "Hello" | rev

# Příkaz sort

Setřídí řádky textového souboru.

    // Setřídí řádky podle abecedy
    sort fruit.txt

    // Setřídí řádky podle abecedy a výsledek uloží do souboru output.txt
    sort fruit.txt > output.txt
    sort -o output.txt fruit.txt

    // Setřídí řádky v opačném pořadí
    sort -r fruit.txt

    // Zkontroluje jestli je soubor setřízený pokud ne vrací první špatně umístěný řádek
    sort -c fruit.txt

    cat columns.txt
    01 Joe
    02 Marie
    03 Albert
    04 Dave

    // Soubor se třídí podle prvního sloupce
    sort columns.txt

    // Soubor se třídí podle druhého sloupce
    sort -k 2 columns.txt
    
# Příkaz unique

Odstraní opakující se řádky.

    uniq unique.txt

    // Vypíše počet opakování
    uniq -c unique.txt

    // Vypíše pouze opakující se řádky
    uniq -d unique.txt

    // Vypíše neopakující se řádky
    uniq -u unique.txt
    

# Příkaz cut

Odebere nebo vyjme část souboru.    

    // Vybere 3. sloupec
    cut -f 3 cut.txt

    //  Vybere 2 az 4 sloupec
    cut -f 2-4 cut.txt

    // Vybere 1. až 2. a 4. až 5. sloupec
    cut -f 1-2,4-5 cut.txt

    // Vybere 3. sloupec a dále
    cut -f 3- cut.txt

    // Vybere 3. znak na každém řádku
    cut -c 3 cut.txt

    // Vybere 3. až 12. znak na každém řádku
    cut -c 3-12 cut.txt

    // Vybere 3. až 12. Byte
    cut -b 3-12 cut.txt

    // Pomocí -d změníme oddělovač sloupců
    cut -f 1 -d ':' /etc/passwd
  
# Příkaz paste

Vypíše obsah souborů vedle sebe.

    // Paralelně
    paste paste.txt paste2.txt

    // Sériově
    paste -s paste.txt paste2.txt

    // Změní oddělovač sloupců
    paste -d "-"  paste.txt paste2.txt

    // Spojí dva soubory a oddělí je tabulátorem
    paste fruit.txt fruitLarge.txt

    // Spojí dva soubory ale oddělí je znakem =
    paste -d =  fruit.txt fruitLarge.txt

# Příkaz grep

Nástroj pro filtrování řádků na základě regularního výrazu.

    // Vybere řádky obsahující dané slovo
    grep parallels /etc/passwd
    grep "Feb 26 17:0" /var/log/kern.log

    // Rekurzivní procházení adresáře
    grep -r "banana" pokus

    // Vypíše řádky obsahující slovo
    grep -w "ps" procesy.txt

    // Vypíše počet nalezených řádků
    grep -cw "ps" procesy.txt

    // Řádky začínající znakem c
    grep "^c" file.txt

    // Řádky obsahující číslo
    grep "[0-9]" file.txt

    // Řádky obsahující slovo proces nebo file
    grep 'proces\|file' file.txt

    // Radky obsahujici slova o delce 7 - 8 znaku
    grep -E "[[:alpha:]]{7,8}" file.txt
    

# Příkaz tr
Konvertuje nebo smaže znaky.

    // Preloží malá písmena na velká
    tr "[:lower:]" "[:upper:]" < fruit.txt

    // Odebere číslice
    echo "Abc123d56E" | tr -d '[[:digit:]]'

    // Nahradí znaky které nejsou A znakem t
    echo "Abc123d56E" | tr -c 'A' 't'

    // Nahradí mezery znakem /
    echo "Can you see how tr command can be wonderful?" | tr -s " " "/"

    // Nahradí více mezer jdoucí po sobě jednou
    echo "Can you                 see how tr          command can be wonderful?" | tr -s " "
    
# Basics
man -> manuálová stránka

pwd -> vytiskne adresář, ve kterém se nacházíš

touch -> vytvoření souboru

cat -> umožńuje vytvořit soubor, nebo vytiskne obsah souboru na standartní výstup (čtení)

rmdir -> maže adresáře (musí být prázdné)

rm -r -> smaže i adresáře, ve kterých něco je

mv - přesouvání a přejmenování zároveň

ctrl + d -> ukončení procesu (nebo zadávání například pokud tvoříte soubor pomcí cat)

ctrl + alt + číslo -> přepínání mezi konzolami, pokud používáte grafické rozhraní

alt + číslo -> přepínání mezi konzolami, pokud nepoužíváte grafické rozhraní

ctrl + c -> ukončení procesu

ctrl + z -> zastavení procesu

ps -> status procesů (má několik přepínačů)

ps -ef -> úplný výpis statusu všech procesů (má několik přepínačů)

ls -> výpis obsahu adresáře (má několik přepínačů)

whereis -> zjištění odkud se program spuští (má několik parametrů)

ctrl + w -> dojde ke smazání slova při špatně napsaném příkazu

ctrl + u -> dojde ke smazání řádku při špatně napsaném příkazu

man - a -> zaborazení všech manuálových stránek k nějákému příkazu, který napíšeš jako parametr

příkazy, které nemají manuálové stránky na ty se díváme pomocí "info"

echo "čau"-> vypsání textu na standartní výstup konzole

echo "čau" | pokus.txt -> vypsání textu do souboru


