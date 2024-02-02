# [React Developer Roadmap](https://roadmap.sh/react)
(3 - 1 sor különbségek)



## Tartalomjegyzék (Table of contents)
  1. [Komponensek](##Komponensek)
    - [Függvény komponensek](###Függvény-komponensek)
    - [Komponens alapok](###Komponens-alapok)
      - [JSX](####JSX)
      - [Prop vs State](####Prop-vs-State)
      - [Conditional Rendering](####Conditional-Rendering)
  2. Rendering
    - Component Life Cycle
    - Lists and Keys
    - Refs
    - Events
  3. Hooks
    - Basic Hooks
      - useState
      - useEffect
    - Common Hooks
      - useRef
      - useContext
      - useCallback
    - Custom Hooks
  4. Routers
    - React Router
  5. State Management
    - Context
  6. API Calls
    - REST
      - react-query
      - Axios
  7. Testing
  8. Forms
    - React Hook Form



## Komponensek
> **A komponensek a React applikációk alapkövei. Lehetővé teszik, hogy a UI-t különálló, és újrafelhasználható darabokra válasszuk szét.**
A UI (User Interface) egy weboldal - vagy applikáció - elemei, amikkel a felhasználó kommunikál miközben használja/vezérli a programot.

> *Components are the building blocks of React applications. They let us split the UI into independent, reusable pieces, and think about each piece in isolation.*
*UI stands for "User Interface". It refers to the elements of a website or app that the user interacts with as they navigate the page or program.*

### Függvény komponensek
> **A függvény komponensek egyszerűen JavaScript függvények. Egy JavaScript függvény megírásával tudunk létrehozni egy függvény komponenst Reactben.**
**Ezek a függvények nem minden esetben várnak paramétert.**
**Egy függvény komponensnek a visszatérési értéke egy JSX code, amit a React a DOM fába renderel.**
**Valamint a függvény komponenseknek lehet State-je is, aminek a kezelését React Hookok végzik.**

> *Functional components are simply JavaScript functions. We can create a functional component to React by writing a JavaScript function.*
*These functions may or may not receive data as parameters.*
*In the functional Components, the return value is the JSX code to render to the DOM tree.*
*Functional components can also have state which is managed using React hooks.*

### Komponens alapok
#### JSX
> **A JSX (JavaScript XML) lehetővé teszi HTML kód írását JavaScriptben, majd a HTML tag-eket React elemekké konvertálja.**
> *JSX stands for JavaScript XML. It allows writing HTML in JavaScript and converts the HTML tags into React elements.*

#### Prop vs State
> **A propok olyan adatokat képviselnek, amiket a szülő továbbít a gyerek komponensnek, és ezzel lehetővé teszi adatok továbbítását a komponensek hierarchiájában.**
> *Props (properties) are passed from parent to child components, allowing data to be shared across the component hierarchy.*

> **A state-et komponensek olyan belső adatainak tárolásához használjuk, amiket renderelni, megjeleníteni szeretnénk.**
**Egy komponens state-je idő közben változhat felhasználó vagy rendszer által előidézett változás miatt. A React újrarendereli azt a komponenst amiben egy ilyen state változás bekövetkezik.**
> *A state is used to store the data of the components that have to be rendered to the view. In React we use the useState React hook for this.*
*The state of a component can change over time due to user actions or system-generated events. These changes trigger a re-render of the component.*

**Míg a propok és state-ekben közös, hogy olyan információt tárolnak, ami befolyásolja a komponens kimeneti renderét, egy fontos dologban eltérnek: míg a propok adatok továbbítására, a state komponensen belüli adatok tárolására szolgál. Mint például egy függvény paraméter (prop), vagy függvényen belüli változók (state).**
*While both hold information that influences the output of component render, they are different in one important way: props get passed to the component (similar to function parameters) whereas state is managed within the component (similar to variables declared within a function).*

#### Conditional Rendering
> **Reactben a feltételes renderelés egy olyan technika, amely lehetővé teszi a fejlesztők számára, hogy dinamikusan/feltételekhez kötve szabályozzák a képernyőn megjelenítendő tartalmat.**
> *Conditional rendering in React is a technique that allows developers to dynamically control what content is displayed on the screen.*

**Ez például akkor lehet hasznos, hogyha bizonyos UI elemeket megjeleníteni/elrejteni szeretnénk, vagy egyszerűem más tartalmat szeretnénk megjeleníteni.**
*This is particularly useful when you want to show or hide certain UI elements, change the layout of a page, or render different content.*
*Use `if`, `logical operators` (&&) or `ternary operator` to create elements representing the current state, and let React update the UI to match them.*


