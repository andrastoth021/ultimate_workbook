# Ultimate workbook

## WEB Basics

### REpresentational State Transfer (REST)
> REST is an architectural style for providing standards between computer systems on the web, making it easier for systems to communicate with each other.

REST is a set of architectural constraints (set of guidelines), not a protocol or a standard.

In the REST architectural style, **the implementation of the client and the implementation of the server can be done independently without each knowing about the other**. This means that the code on the client side can be changed at any time without affecting the operation of the server, and the code on the server side can be changed without affecting the operation of the client.

**As long as each side knows what format of messages to send to the other, they can be kept modular and separate.**
Separating the user interface concerns from the data storage concerns, we **improve the flexibility** of the interface across platforms and **improve scalability** by simplifying the server components.

**Headers** and parameters are also important in the HTTP methods of a RESTful API HTTP request, as they contain important identifier information as to the request's **metadata, authorization, uniform resource identifier (URI), caching, cookies, etc**. There are request headers and response headers, each with their own HTTP connection information and status codes.

> By using a REST interface, different clients hit the same REST endpoints, perform the same actions, and receive the same responses.


### Application Programming Interface (API)
> An API is a set of definitions and protocols for building and integrating application software. It’s sometimes referred to as a contract between an information provider and an information user—establishing the content required from the consumer (the **call**/**request**) and the content required by the producer (the **response**).

If you want to interact with a computer or system to retrieve information or perform a function, an API helps you communicate what you want to that system so it can understand and fulfill the request.

Think of an API as a mediator between the users or clients and the resources or web services they want to get. It’s also a way for an organization to share resources and information while maintaining security, control, and authentication—determining who gets access to what. 

Advantage of an API is that you don’t have to know the specifics of caching—how your resource is retrieved or where it comes from.


### RESTful API (extra)
> In contrast, REST is a set of guidelines that can be implemented as needed, making REST APIs faster and more lightweight, with increased scalablity—perfect for Internet of Things (IoT) and mobile app development.

In order for an API to be considered RESTful, it has to conform to these criteria:

1. A client-server architecture made up of clients, servers, and resources, with requests managed through HTTP.
2. Stateless client-server communication, meaning no client information is stored between get requests and each request is separate and unconnected.
3. Cacheable data that streamlines client-server interactions.
4. A uniform interface between components so that information is transferred in a standard form. This requires that:
  - resources requested are identifiable and separate from the representations sent to the client.
  - resources can be manipulated by the client via the representation they receive because the representation contains enough information to do so.
  - self-descriptive messages returned to the client have enough information to describe how the client should process it.
  - hypertext/hypermedia is available, meaning that after accessing a resource the client should be able to use hyperlinks to find all other currently available actions they can take.
5. A layered system that organizes each type of server (those responsible for security, load-balancing, etc.) involved the retrieval of requested information into hierarchies, invisible to the client.
6. Code-on-demand (optional): the ability to send executable code from the server to the client when requested, extending client functionality.


### Node.js & npm
> **Node.js is an open-source and cross-platform JavaScript runtime environment.**

Developers use Node. js to create server-side web applications, and it is perfect for data-intensive applications since it uses an asynchronous, event-driven model.
A Node.js app runs in a single process, without creating a new thread for every request.

- Why?
Node.js is a cross-platform runtime, perfect for a wide range of use cases. Its huge community makes it easy to get started. It uses the V8 engine to compile JavaScript and runs at lightning-fast speeds. Node.js applications are very scalable and maintainable.

> **npm is the standard package manager for Node.js.**

It is two things: first and foremost, it is an online repository for the publishing of open-source Node.js projects; second, it is a command-line utility for interacting with said repository that aids in package installation, version management, and dependency management.


### Fetch
> The Fetch API provides a JavaScript interface for accessing and manipulating parts of the protocol, such as requests and responses. It also provides a global `fetch()` method that provides an **easy**, **logical** way to fetch resources **asynchronously** across the network.

> The `Promise` object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

Important about Promise:
  - then
  - catch
  - finally: The `finally()` method of `Promise` instances schedules a function to be called when **the promise is settled (either fulfilled or rejected)**

Unlike XMLHttpRequest that is a callback-based API, Fetch is promise-based and provides a better alternative that can be easily used in service workers. Fetch also integrates advanced HTTP concepts such as **CORS** and other extensions to HTTP.


### React
> React is the most popular **front-end JavaScript library** for building user interfaces. React can also render on the server using Node and power mobile apps using React Native.


### React hooks
> Hooks let us use React’s features-like managing your component’s state and or performing an after effect when certain changes occur in state(s) without writing a class. (were introduced in React 16.8)

A few important React Hooks:
  - useState: lets you add a state variable to your component.
  - useEffect: lets you synchronize a component with an external system.
  - useCallback: lets you cache a function definition between re-renders.
  - useRef: lets you reference a value that’s not needed for rendering.
  - useContext: lets you read and subscribe to context from your component.

> **Context** lets the parent component make some information available to any component in the tree below it—no matter how deep—without passing it explicitly through props.


> Building **Custom Hooks** (your own Hooks) lets you extract component logic into reusable functions.


## Spring, Spring Boot, ORM, Spring Security

