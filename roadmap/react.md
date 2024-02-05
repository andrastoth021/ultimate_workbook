# [React Developer Roadmap](https://roadmap.sh/react)
(3 - 1 sor különbségek)



## Tartalomjegyzék (Table of contents)
  1. [Komponensek](##Komponensek)
    - [Függvény komponensek](###Függvény-komponensek)
    - [Komponens alapok](###Komponens-alapok)
      - [JSX](####JSX)
      - [Prop vs State](####Prop-vs-State)
      - [Conditional Rendering](####Conditional-Rendering)
  2. [Rendering](#Rendering)
    - [Component Life Cycle](###Component-Life-Cycle)
    - [Lists and Keys](###Lists-and-Keys)
    - [Refs](###Refs)
    - [Events](###Events)
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

## Rendering
**A React deklaratív megközelítéssel renderel komponenseket, ami azt jelenti, hogy a fejlesztő specifikálja a komponenst, és ennek képernyőre renderelését a React intézi el.**
**Ez ellentéte az imperatív megközelítésnek, ami azt jelenti, hogy a fejlesztő manuálisan (kóddal) manipulálja a DOM-ot, és ezzel frissíti a UI-t.**
**A Virtuális DOM (VDOM) egy fontos tényező a React működésében. Ez egy könnyen tárolható memóriában lévő reprezentálása a DOM-nak.**
**A rendelés lépései a következők:**
1. **A komponens meg van írva, és JSX szintakszis használatával a render metódus visszatér a komponens leírásával.**
2. **A komponens renderelve van, a React készít egy VDOM reprezentációt a komponensről.**
3. **Ezután a React összehasonlítja a VDOM-ot az eggyel előtti verziójával (ha létezik). Ha van köztük különbség, a két VDOM között, akkor a React kiszámolja, hogy mennyi DOM update-re van szükség, hogy a DOM megegyezzem a VDOM-mal.**
4. **Az aktuális DOM frissítése a lehető legkevesebb DOM update-tel.**

*React follows a declarative approach to rendering components, which means that developers specify what a component should look like, and React takes care of rendering the component to the screen.*
*This is in contrast to an imperative approach, where developers would write code to manually manipulate the DOM (Document Object Model) to update the UI.*
*The virtual DOM (VDOM) is an important aspect of how React works. It is a lightweight in-memory representation of the DOM (Document Object Model), and it is used to optimize the rendering of components in a React application.*

*Steps of rendering:*
1. *Components are written, the render method returns a description of what the component should look like, using JSX syntax.*
2. *The component is rendered, now React creates a virtual DOM (VDOM) representation of the component. (The VDOM is a lightweight in-memory representation of the DOM, and it is used to optimize the rendering of components.)*
3. *React compares the VDOM representation of the component with the previous VDOM representation (if it exists). If there are differences between the two VDOMs, React calculates the minimum number of DOM updates needed to bring the actual DOM into line with the new VDOM.*
4. *React updates the actual DOM with the minimum number of DOM updates needed to reflect the changes in the VDOM.*

### Component Life Cycle
**A React komponenseknek 3 életciklusuk van: Mounting, Updating, Unmounting.**
*React components have a lifecycle consisting of three phases: Mounting, Updating, and Unmounting.*

### Lists and Keys
**Amikor Reactben listákat renderelünk, a `key` propot szoktuk használni, hogy egy egyéni kulcsot adjunk minden elemnek. Amikor kifejezetten egy elemet szeretnénk frissíteni, akkor használjuk az elem beazonosításához.**
*When you render lists in React, you can use the key prop to specify a unique key for each item. This key is used to identify which item to update when you want to update a specific item.*

### Refs
> **A Ref-ek a render metódusban létrehozott DOM node-ok vagy React elementek elérését biztosítja.**
> *Refs provide a way to access DOM nodes or React elements created in the render method.*
**Reactben a tipikus módszer a szülő-gyerek kommunikációra a propok. Azonban vannak olyan esete ahol imperatív módot szeretnénk módosítani a gyerek komponenst. Erre jók a referenciák.**
*In the typical React dataflow, props are the only way that parent components interact with their children. To modify a child, you re-render it with new props. However, there are a few cases where you need to imperatively modify a child outside of the typical dataflow.*

### Events
*Handling events with React elements is very similar to handling events on DOM elements. There are some syntax differences:*
  - *React events are named using camelCase, rather than lowercase.*
  - *With JSX you pass a function as the event handler, rather than a string.*


