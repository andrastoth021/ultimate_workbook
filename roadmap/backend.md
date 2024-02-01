# [Backend Developer Roadmap](https://roadmap.sh/backend)
(3 - 1 sor különbségek)



## Tartalomjegyzék
  1. Internet
    - [Hogyan működik az internet? (How does the internet work?)](https://youtu.be/7_LPdttKXPc?si=NPFGNP27zXxdATW9)
    - Mi az a HTTP? - HyperText Transfer Protocol - (What is HTTP?)
    - HTTP kérések és válaszok (HTTP requests & responses)
    - Böngésző (Browser)



## Internet
> **Az internet egy olyan globális számítógépes hálózat, amelyen a számítógépek protokoll-halmazok segítségével kommunikálnak.**
> *The Internet is a global network of computers connected to each other which communicate through a standardized set of protocols.*

### Hogy működik az internet? (How does the internet work?)
> **A protokoll olyan szabályok és szabványok összessége, amelyek meghatározzák az eszközök és rendszerek közötti adatváltást.**
Az internetes kommunikáció során számos különböző protokollt alkalmazunk, mint például: `IP`, `TCP`, `DNS`, és még sok más.
Az `IP` azért felelős, hogy az adatcsomagok a megfelelő helyre legyenek továbbítva.
A `TCP` és `UDP` biztosít az adatcsomagok megbízható és hatékony továbbításáról.
A `DNS` a domain neveket alakítja IP-címekké.
A `HTTP` pedig a kliens és szerver közötti adatok továbbításáért felel.

Quick & easy [explanation](https://youtu.be/7_LPdttKXPc?si=NPFGNP27zXxdATW9).

> *A protocol is a set of rules and standards that define how information is exchanged between devices and systems.*
*There are many different protocols used in internet communication, including the Internet Protocol (IP), the Transmission Control Protocol (TCP), the User Datagram Protocol (UDP), the Domain Name System (DNS), and many others.*
*IP is responsible for routing packets of data to their correct destination.*
*TCP and UDP ensure that packets are transmitted reliably and efficiently.*
*DNS is used to translate domain names into IP addresses*
*HTTP is used to transfer data between clients and servers.*

### Mi az a HTTP? - HyperText Transfer Protocol - (What is HTTP?)
> **A `HTTP` egy `TCP/IP`-alapú kommunikációs protokoll, egy absztrakt réteg, ami szabványosítja a kliens és a szerver közötti kommunikációt.**
A `TCP/IP` továbbítja felé a kliens és szerver között zajló kéréseket és válaszokat. Tehát a `HTTP` függ a `TCP/IP`-től
Alapértelmezetten a 80-as (TCP) portot használja. A `HTTPS`-nek azonban 443 az alapértelmezett portja.

> *HTTP is a TCP/IP-based application layer communication protocol that standardizes how clients and servers communicate with each other.*
*HTTP itself depends on TCP/IP to get requests and responses between the client and server.*
*By default, TCP port 80 is used, but other ports can also be used. HTTPS, however, uses port 443.*

### HTTP kérések és válaszok (HTTP requests & responses)
- **Kérés**:
  1. HTTP method (például `GET`, `POST`, `PUT`, `DELETE`) ami definiálja a végrehajtandó műveletet.
  2. Fetchelni kívánt adat útvonala.
  3. HTTP protokoll verzió.
  4. Optional header-ök, amik extra információt szolgáltatnak a szervernek.
  5. Body (például `POST`-nál), ez tartalmazza a küldeni kívánt adatot.

- **Válasz**:
  1. HTTP protokoll verzió.
  2. Státusz kód, ami megállapítja a kérés sikerességét és annak indokát.
  3. Rövid leírás a státusz kódról.
  4. HTTP header-ök, mint a request-nél.
  5. (Opcionális) Body, ami tartalmazza a fetch-elt adatokat.

- *Request*:
  1. *An HTTP method (e.g., GET, POST, PUT, DELETE, etc.) that defines the operation the client wants to perform.*
  2. *The path of the resource to fetch.*
  3. *The version of the HTTP protocol.*
  4. *Optional headers that carry additional information for the servers.*
  5. *A body, for some methods like POST, which contains the resource sent.*

- *Response*:
  1. *The version of the HTTP protocol they follow.*
  2. *A status code, indicating if the request was successful or not, and why.*
  3. *A status message, a non-authoritative short description of the status code.*
  4. *HTTP headers, like those for requests.*
  5. *Optionally, a body containing the fetched resource.*

### Böngésző (Browser)
> **A böngésző egy szoftver, ami lehetővé teszi a felhasználók számára weboldalak - vagy más online kontentekhez - való hozzáférést grafikus felületen.**
> *A web browser is a software application that enables a user to access and display web pages or other online content through its graphical user interface.*


