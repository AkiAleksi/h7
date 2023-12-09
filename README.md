# h7

# a

- Katsoin video ohjeen hascatin lataamisesta ja käytöstä https://www.youtube.com/watch?v=KLry7bf51QQ.
  Latasin hashcatin sivuilta hashcat binaries https://hashcat.net/hashcat/.
  Unzippasin tiedoston. Loin kansioon kaksi eri txt fileä hash.txt (murretava) ja cracked.txt (murrettu salasana).

- Loin MD5-hashin salasanasta ja laitoin hashin hash.txt fileen.
- Sen jälkeen ajoin komennon hashcat -m0 -a3 -o cracked.txt hash.txt
- Salasana murrettiin.
 


<img width="353" alt="ratkaistu" src="https://github.com/AkiAleksi/h7/assets/112399816/db710314-2716-47e1-9d4a-50b87124dfdb">


# b

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

  $ $HOME/john/run/zip2john tero.zip >tero.zip.hash  

  $ $HOME/john/run/john tero.zip.hash  
  
  
<img width="424" alt="Screenshot 2023-12-09 at 17 22 53" src="https://github.com/AkiAleksi/h7/assets/112399816/084a3739-e120-4d49-9ce8-2aa1e03c5b83">


Löytyi sana butterfly. Menin tero.zip tiedostoon ja kokeilin syöttää salasanan SECRET.md.
Tämä avautui. 


<img width="533" alt="Screenshot 2023-12-09 at 17 24 07" src="https://github.com/AkiAleksi/h7/assets/112399816/f99af1d3-595d-4a00-b980-8fe5b6a5dac1">

  
  
  
  # c
  

<img width="333" alt="Screenshot 2023-12-09 at 19 01 03" src="https://github.com/AkiAleksi/h7/assets/112399816/498add68-78ed-499d-a905-82691bc7bbe3">



<img width="362" alt="Screenshot 2023-12-08 at 10 59 18" src="https://github.com/AkiAleksi/h7/assets/112399816/c605006a-b779-4544-8077-15dd9ae2c872">
