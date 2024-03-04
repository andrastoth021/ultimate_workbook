# [Backend Developer Roadmap](https://roadmap.sh/backend)
(3 - 1 sor különbségek)



## Tartalomjegyzék (Table of contents)
  1. [Internet](##Internet) (https://youtu.be/7_LPdttKXPc?si=NPFGNP27zXxdATW9)
    - [Hogyan működik az internet? (How does the internet work?)](###Hogy-működik-az-internet?-(How-does-the-internet-work?))
    - [Mi az a HTTP (HyperText Transfer Protocol)?](###Mi-az-a-HTTP-(HyperText-Transfer-Protocol)?)
    - [HTTP kérések és válaszok (HTTP requests & responses)](###HTTP-kérések-és-válaszok-(HTTP-requests-&-responses))
    - [Böngésző (Browser)](###Böngésző-(Browser))
  2. API
    - REST
    - JSON APIs
  3. Relációs adatbázisok
    - PostgreSQL
  4. Caching
    - Client Side
  5. Web Security
    - CORS
    - API Security Best Practices
  6. Tesztelés
    - Integration Testing
    - Unit Testing
    - Functional Testing
  7. Databases
    - Scaling databases
    - ORMs
    - Transactions



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

### Mi az a HTTP (HyperText Transfer Protocol)?
> **A `HTTP` egy `TCP/IP`-alapú kommunikációs protokoll, egy absztrakt réteg, ami szabványosítja a kliens és a szerver közötti kommunikációt.**
A `TCP/IP` továbbítja felé a kliens és szerver között zajló kéréseket és válaszokat. Tehát a `HTTP` függ a `TCP/IP`-től
Alapértelmezetten a 80-as (TCP) portot használja. A `HTTPS`-nek azonban 443 az alapértelmezett portja.

**A HTTP-t webböngésző és webszerverek közötti kommunikációhoz tervezték, de másra is fel lehet használni. A klasszikus kliens-szerver modelt követi/alkalmazza, amik közötti kommunikációt a kliens megnyitja egy kéréssel, majd vár egy válaszra. A HTTP egy stateless protokoll, ami azt jelenti, hogy a server nem tárol semmilyen adatot (state-et) két request között.**

> *HTTP is a TCP/IP-based application layer communication protocol that standardizes how clients and servers communicate with each other.*
*HTTP itself depends on TCP/IP to get requests and responses between the client and server.*
*By default, TCP port 80 is used, but other ports can also be used. HTTPS, however, uses port 443.*
*Hypertext Transfer Protocol (HTTP) is an application-layer protocol for transmitting hypermedia documents, such as HTML. It was designed for communication between web browsers and web servers, but it can also be used for other purposes. HTTP follows a classical client-server model, with a client opening a connection to make a request, then waiting until it receives a response. HTTP is a stateless protocol, meaning that the server does not keep any data (state) between two requests.*

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

## API
> **Az API (Application Programming Interface) egy szoftver közvetítő, ami lehetővé tesz két applikáció közötti kommunikációt.**
> *API is the acronym for Application Programming Interface, which is a software intermediary that allows two applications to talk to each other.*

*A web API is an API that can be accessed using the HTTP protocol. This is a broad category—really too broad to be very useful. Not all APIs are web APIs; some APIs are used only to communicate between two applications on the same computer, never making use of a web connection.*
API types: Public APIs, Private/Internal API, 
API protocols: for example REST API.

## API
> 
> *API is a way for two computers to talk to each others.*

Fogalom és nem implementáció
*Using an API is just like using a website browser. But instead of clicking buttons and filling out forms, you write code to request data from a server.*
*Example: We could visit NASA's website to look at pictures about astroids OR we could use their REST API to request raw json data.*

### REST

> *REST, or REpresentational State Transfer, is an architectural style for providing standards between computer systems on the web, making it easier for systems to communicate with each other.*

A RESTful API organizes data entities or resources into a bunch of unique URLs, or rather URIs (Uniform Resource Identifiers).
`http://api.com/v2/comet` --> `comet` is the resource, the rest of it is called network location.

A client can get data about a resource by making a request to that endpoint over http.
The request message has a very specific format: HTTP method, URI, headers, and body.
```
POST /dinosaur

Accept: application/json
Authorization: <token>
Connection: keep-alive

{
  "name": "dino"
}
```

The server will recieve the request message then execute some code, after that the a formatted response message gets sent back.
Response message contains: status code, headers, body.
```
200 OK

Server: nginx
Age: 2323
Connection: keep-alive

{
  "id": "2624626",
  "status": "success"
}
```

It's important about this architecture that its stateless. Which means the two parties don't need to store any information about each other, and every request-response cycle is independent from each other.

Benefits:
(IBM)
- Simple & Standardized, industry used
- Scalable & Stateless
- High performance, caching
OR
(AWS Amazon docs)
- Scalability: 
- Flexibility: 
- Independence: 

REST key standards:

 

### JSON APIs




