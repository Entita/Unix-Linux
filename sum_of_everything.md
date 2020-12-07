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
    drwxr-xr-x 21 roman roman  4096 Feb 11 10:35 .
    drwxr-xr-x  3 root  root   4096 Jan 29 18:43 ..
    -rw-------  1 roman roman    89 Jan 29 19:16 .bash_history
    -rw-r--r--  1 roman roman   220 Jan 29 18:43 .bash_logout
    -rw-r--r--  1 roman roman  4000 Jan 29 18:43 .bashrc
    drwxrwxr-x 11 roman roman  4096 Feb 11 10:40 .cache
    drwxr-xr-x 14 roman roman  4096 Feb 10 21:37 .config
    drwx------  3 roman roman  4096 Jan 29 18:46 .dbus
    drwxr-xr-x  2 roman roman  4096 Jan 29 19:08 Desktop
    drwxr-xr-x  2 roman roman  4096 Jan 29 18:46 Documents
    drwxr-xr-x  2 roman roman  4096 Jan 29 18:50 Downloads
    drwxrwxr-x  2 roman roman  4096 Feb 10 21:32 fontconfig
    drwxrwxr-x  2 roman roman  4096 Jan 29 18:47 .fontconfig

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

    michal@virtual ~ $ chmod 721 soubor.txt
    michal@virtual ~ $ chmod 711 public_html
    
# Basics
man -> manuálová stránka

pwd -> vytiskne adresář, ve kterém se nacházíš

touch -> vytvoření souboru
cat -> umožńuje vytvořit soubor, nebo vytiskne obsah souboru na standartní výstup (čtení)

rmdir -> maže adresáře (musí být prázdné)

rm -r -> smaže i adresáře, ve kterých něco je

mv - přesouvání a přejmenování zároveň

ctrl + d -> ukončení procesu

ctrl + c -> ukončení procesu

ctrl + z -> zastavení procesu

ps -> status procesů (má několik přepínačů)

ps -ef -> úplný výpis statusu všech procesů (má několik přepínačů)

ls -> výpis obsahu adresáře (má několik přepínačů)


