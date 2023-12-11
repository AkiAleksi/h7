# h7

# x

Karvinen 2022: Cracking Passwords with Hashcat

-Hashcatin ja hashid:n asennus
-Hashid:n käyttö. Sen avulla voidaan tunnistaa käytetty algoritmi
-Sitten käytiin läpi hashcatin käyttö

Karvinen 2023: Crack File Password With John

-John the Ripperin Jumbo version asennus
-Johnin käyttöohjeet


# a

- Katsoin video ohjeen hascatin lataamisesta ja käytöstä: https://www.youtube.com/watch?v=KLry7bf51QQ.
  Latasin hashcatin sivuilta hashcat binaries: https://hashcat.net/hashcat/.
  Unzippasin tiedoston. Loin kansioon kaksi eri txt fileä hash.txt (murretava) ja cracked.txt (murrettu salasana).

- Loin MD5-hashin salasanasta ja laitoin hashin hash.txt fileen.
- Sen jälkeen ajoin komennon hashcat -m0 -a3 -o cracked.txt hash.txt
- Salasana murrettiin.
 


<img width="353" alt="ratkaistu" src="https://github.com/AkiAleksi/h7/assets/112399816/db710314-2716-47e1-9d4a-50b87124dfdb">


# b

  Löysin youtube videon, jossa neuvotaan John The Ripperin käyttö: https://www.youtube.com/watch?v=yyIoX0QT6QM

  Asensin tarvittavat työkalut ja kirjastot. Sen jälkeen kloonasin John the Ripperin repon.

  $ sudo apt-get install build-essential zlib1g zlib1g-dev libbz2-1.0 libbz2-dev

  $ git clone --depth=1 https://github.com/openwall/john.git 

  Sen jälkeen john/src kansioon, latasin OpenSSL headersit ja ./configure

  $ cd john/src

  $ sudo apt-get install libssl-dev  

  $ ./configure

  John on konfiguroitu. Sitten komento:

  $ make -s clean && make -sj4   
   
  Latasin https://terokarvinen.com/2023/crack-file-password-with-john/ zip tiedoston.
  Tein zip tiedostosta hashin omaan tiedostoon ja ajoin johnin.

  cd Desktop

  zip2john tero.zip > tero.txt

  cat tero.txt

  john tero.txt

  
  <img width="424" alt="Screenshot 2023-12-09 at 17 22 53" src="https://github.com/AkiAleksi/h7/assets/112399816/7e5b5873-d96e-4705-95af-a9236f959219">

 



Löytyi sana butterfly. Menin tero.zip tiedostoon ja kokeilin syöttää salasanan SECRET.md.
Tämä avautui. 


<img width="533" alt="Screenshot 2023-12-09 at 17 24 07" src="https://github.com/AkiAleksi/h7/assets/112399816/f99af1d3-595d-4a00-b980-8fe5b6a5dac1">

  
  
  
  # c

  -Tarkistin Hashid:llä f5bc7fcc7f5b3b6af7ff79e0feafad6d1a948b6a2c18de414993c1226be48c1f 
  -Sain nämä algoritmit vastaukseksi. 
  -SHA-256 oikea algoritmi
  

<img width="362" alt="Screenshot 2023-12-08 at 10 59 18" src="https://github.com/AkiAleksi/h7/assets/112399816/c605006a-b779-4544-8077-15dd9ae2c872">


- Asensin Cewl sovelluksen, jotta saan sanalistan sivun sanoista. https://github.com/digininja/CeWL
- sudo apt-get update
- sudo apt-get install cewl

Ajoin komennon cewl -d 0 -m 5 -with-numbers https://terokarvinen.com/2023/eettinen-hakkerointi-2023/ -w lista.txt
Komento kerää osoitteesta kaikki sanat, jotka ovat yli viisi merkkiä pitkiä. 




<img width="333" alt="Screenshot 2023-12-09 at 19 01 03" src="https://github.com/AkiAleksi/h7/assets/112399816/498add68-78ed-499d-a905-82691bc7bbe3">


- Sen jälkeen ajetaan hashcatilla lista -a 0 vastaan. Kyseessä on sanakirjahyökkäys -m 1400. Algoritmi SHA2-256.
   Komennon loppuun sanakirja. hashcat -a 0 -m 1400 -o asddas.txt 'f5bc7fcc7f5b3b6af7ff79e0feafad6d1a948b6a2c18de414993c1226be48c1f' lista.txt


<img width="366" alt="Screenshot 2023-12-09 at 19 03 55" src="https://github.com/AkiAleksi/h7/assets/112399816/73e83e4f-d1bb-4359-a5e5-6a65a465f3d9">

# d


Porttiskannaus: https://github.com/Viktorialissa/PenTest/blob/main/h2.md

-Cheatsheet

Nmap on laajasti käytetty porttiskannaustyökalu. Voit käyttää sitä komentoriviltä seuraavasti:
nmap [kohde]

Esimerkiksi: nmap 192.168.1.1

Komennosta eri versioita:

nmap TCP connect scan -sT: sudo nmap -sT 127.0.0.2
nmap TCP SYN "used to be stealth" scan, -sS: sudo nmap -sS -p 22 127.0.0.2
nmap ping sweep -sn: sudo nmap -sn 127.0.0.2
nmap don't ping -Pn: sudo nmap -Pn 127.0.0.2
nmap version detection -sV: sudo nmap -sV -p 22 127.0.0.2
nmap output files -oA foo: sudo nmap -oA foo -p 22 127.0.0.2





# e

Tarkistettu


# Lähteet

https://www.youtube.com/watch?v=KLry7bf51QQ

https://hashcat.net/hashcat/.

https://terokarvinen.com/2023/crack-file-password-with-john/

https://terokarvinen.com/2022/cracking-passwords-with-hashcat/

https://github.com/Viktorialissa/PenTest/blob/main/h2.md

https://www.youtube.com/watch?v=yyIoX0QT6QM

