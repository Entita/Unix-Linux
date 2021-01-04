# Napište příkazy, které vytvoří soubor s názvem me.txt, který bude vypadat následovně:

        Domovsky adresar:
        /home/PRFAD/kuhrtoma
        Obsah domovskeho adresare:
        total 95772
        -rw-r--r-- 1 kuhrtoma Domain Users 49 Sep 24 16:08 me.txt
        drwxr-xr-x 2 kuhrtoma Domain Users 4096 Feb 22 2018 public_html/
        drwxr-xr-x 22 kuhrtoma Domain Users 4096 Jan 30 2014 rozvrh/
        drwxr-xr-x 39 kuhrtoma Domain Users 4096 Apr 19 2013 science/
        drwxr-xr-x 35 kuhrtoma Domain Users 4096 Nov 22 2017 teaching/
        Aktualne bezici procesy:
        PID TTY TIME CMD
        30630 pts/1 00:00:00 bash
        32361 pts/1 00:00:00 ps

        $ echo "Domovský adresar: " > prvniukol.txt

        $ pwd >> prvniukol.txtTT

        $ echo "  " >> prvniukol.txt

        $ echo "Obsah domovského adresare: " >> prvniukol.txt

        $ ls -l >> prvniukol.txt

        $ echo "  " >> prvniukol.txt

        $ echo "Aktualně běžící procesy:  " >> prvniukol.txt

        $ ps >> prvniukol.txt

# V adresáři /etc najděte všechny soubory s příponou „conf“ a zjistěte, který z nich má nejvíce řádek.

# Vypište seznam uživatelů ve tvaru "login_jmeno=JMENO PRIJMENI". Seznam uživatelů naleznete v souboru /etc/passwd.
        $ touch tretiuloha.txt
        $ cat /etc/passwd > tretiuloha.txt
        $ cut -f 1,5 -d : tretiuloha.txt | cat > temp.txt
        $ cut -f 1 -d : tretiuloha.txt | cat > temporary.txt
        $ cat temporary.txt > tretiuloha.txt
        $ rm temporary.txt
        $ cut -f 2 -d : temp.txt | cat > temporary.txt
        $ rm temp.txt
        $ paste -d "=" tretiuloha.txt temporary.txt
