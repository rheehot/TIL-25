# Abstract

디자인 패턴은 간접 경험을 할 수 있어서 좋다. 가끔은 이런 걸 굳이
패턴화 할 필요가 있나 할 정도로 당연한 얘기도 있다. 때로는 이 패턴과
저 패턴의 차이는 뭘까 하는 의문이 생기게 하는 것 들도 많다. 무엇보다
다양한 관점에서 문제를 바라 볼 수 있게 방아쇠를 당겨주는 것은 디자인
패턴의 이유라고 할 수 있다.

# Materials

* [패턴으로 가는길, 손영수](http://www.devpia.com/MAEUL/Contents/Detail.aspx?BoardID=70&MAEULNO=28&no=187&page=1)
  *  패턴 공부 로드맵
* [GOF pattern]()
* [POSA]()
* [PLoPD, pattern language of program design](http://wiki.c2.com/?PatternLanguagesOfProgramDesign)
  * 패턴에 관련된 컨퍼런스인 PLoP의 논문들을 정리한 책
* [Pattern-Oriented Analysis and Design: Composing Patterns to Design Software Systems](http://www.kangcom.com/sub/view.asp?sku=200309010011)
* [Remoting Patterns: Foundations of Enterprise, Internet and Realtime Distributed Object Middleware](http://www.kangcom.com/sub/view.asp?sku=200410040309)
* [Xunit Test Patterns: Refactoring Test Code](http://www.kangcom.com/sub/view.asp?sku=200612280010)
* [Patterns for Fault Tolerant Software](http://www.kangcom.com/sub/view.asp?sku=200712160009)
* [Patterns of Enterprise Application Architecture, Martin Fowler](http://www.kangcom.com/sub/view.asp?sku=200212100028)
* [Enterprise Integration Patterns : Designing, Building, and Deploying Messaging Solutions](http://www.kangcom.com/sub/view.asp?sku=200310160006)
* [Real-Time Design Patterns: Robust Scalable Architecture for Real-Time Systems](http://www.kangcom.com/sub/view.asp?sku=200403300020)
* [Refactoring to Patterns](http://www.kangcom.com/sub/view.asp?sku=200406140003)
* [Architecting Enterprise Solutions: Patterns for High-Capability Internet-Based Systems](http://www.kangcom.com/sub/view.asp?sku=200410040307)
* [PLoP papers](http://www.hillside.net/index.php/past-plop-conferences)
* [클로저 디자인 패턴](http://clojure.or.kr/docs/clojure-and-gof-design-patterns.html)
  * java로 표현한 디자인 패턴은 clojure로 이렇게 간단히 된다.

# References

* [Design patterns implemented in Java](http://java-design-patterns.com/)
* [.NET Design Patterns](http://dofactory.com/net/design-patterns)

---

# [GOF Pattern](http://www.dofactory.com/net/design-patterns)
  
- Creational Pattern
  - Abstract Factory	(Creates an instance of several families of classes)
    - strategy of related creating object
  - Builder	(Separates object construction from its representation)
    - selective arguments
  - Factory Method	(Creates an instance of several derived classes)
    - strategy of creating object
  - Prototype	(A fully initialized instance to be copied or cloned)
  - Singleton	(A class of which only a single instance can exist)    

- Structural Pattern
  - Adapter	(Match interfaces of different classes)
    - wrapper, various type, same feature
  - Bridge	(Separates an object’s interface from its implementation)
  - Composite	(A tree structure of simple and composite objects)
    - tree
  - Decorator	(Add responsibilities to objects dynamically)
    - wrapper with same type, new feature
  - Facade	(A single class that represents an entire subsystem)
  - Flyweight	(A fine-grained instance used for efficient sharing)
    - cache
  - Proxy	(An object representing another object)
    - wrapper, composition of function

- Behaviorial Pattern
  - Chain of Resp.	(A way of passing a request between a chain of objects)
    - composition of function
  - Command	(Encapsulate a command request as an object)
    - function
  - Interpreter	(A way to include language elements in a program)
    - functions which process tree
  - Iterator	(Sequentially access the elements of a collection)
    - sequence
  - Mediator	(Defines simplified communication between classes)
  - Memento	(Capture and restore an object's internal state)
    - save and restore
  - Observer	(A way of notifying change to a number of classes)
    - a function which is called after other function is called
  - State	(Alter an object's behavior when its state changes)
    - Strategy pattern which depends on states
  - Strategy	(Encapsulates an algorithm inside a class)
    - a function which receives arguments
  - Template (Method	Defer the exact steps of an algorithm to a subclass)
    - Stategy pattern which includes default values
  - Visitor	(Defines a new operation to a class without change)
    - multi dispath
    
---

# [Game Programming Pattern](http://gameprogrammingpatterns.com/contents.html)

- Sequencing Pattern
  - Double Buffer
  - Game Loop
  - Update Method
- Behavioral Pattern
  - Bytecode
  - Subclass Sandbox
  - Type Object
- Decoupling Pattern
  - Component
  - Event Queue
  - Service Locator
- Optimization Pattern
  - Data Locality
  - Dirty Flag
  - Object Pool
  - Spatial Partition

---

# [Design patterns implemented in Java](http://java-design-patterns.com/)

## Architectural

- API Gateway
  - Aggregate calls to microservices in a single location: the API
    Gateway. The user makes a single call to the API Gateway, and the
    API Gateway then calls each relevant microservice.
  - similar to Aggregator Microservices

- Aggregator Microservices
  - The user makes a single call to the Aggregator, and the aggregator
    then calls each relevant microservice and collects the data, apply
    business logic to it, and further publish is as a REST
    Endpoint. More variations of the aggregator are: - Proxy
    Microservice Design Pattern: A different microservice is called
    upon the business need. - Chained Microservice Design Pattern: In
    this case each microservice is dependent/ chained to a series of
    other microservices.
  - similar to APIGateway

- CQRS (command query responsibility segregation
  - CQRS Command Query Responsibility Segregation - Separate the query
    side from the command side.

- Data Bus
  - Allows send of messages/events between components of an
    application without them needing to know about each other. They
    only need to know about the type of the message/event being sent.
  - similar to mediator, observer, publish/subscribe pattern

- Data Transfer Object

  - Pass data with multiple attributes in one shot from client to
    server, to avoid multiple calls to remote server.

- Event Driven Architecture

  - Send and notify state changes of your objects to other
    applications using an Event-driven Architecture.

- Event Sourcing

  - Instead of storing just the current state of the data in a domain,
    use an append-only store to record the full series of actions
    taken on that data. The store acts as the system of record and can
    be used to materialize the domain objects. This can simplify tasks
    in complex domains, by avoiding the need to synchronize the data
    model and the business domain, while improving performance,
    scalability, and responsiveness. It can also provide consistency
    for transactional data, and maintain full audit trails and history
    that can enable compensating actions.
  - [eventsourcing & cqrs demo project for springcamp 2017](https://github.com/jaceshim/springcamp2017)

- Hexagonal Architecture

  - Allow an application to equally be driven by users, programs,
    automated test or batch scripts, and to be developed and tested in
    isolation from its eventual run-time devices and databases.
  - ???

- Layers

  - Layers is an architectural style where software responsibilities
    are divided among the different layers of the application.

- Naked Objects

  - The Naked Objects architectural pattern is well suited for rapid
    prototyping. Using the pattern, you only need to write the domain
    objects, everything else is autogenerated by the framework.

- Partial Response

  - Send partial response from server to client on need basis. Client
    will specify the the fields that it need to server, instead of
    serving all details for resource.

- Service Layer

  - Service Layer is an abstraction over domain logic. Typically
    applications require multiple kinds of interfaces to the data they
    store and logic they implement: data loaders, user interfaces,
    integration gateways, and others. Despite their different
    purposes, these interfaces often need common interactions with the
    application to access and manipulate its data and invoke its
    business logic. The Service Layer fulfills this role.

## [Behavioral](#gof-pattern)

## Business Tier

- Business Delegate

  - The Business Delegate pattern adds an abstraction layer between
    presentation and business tiers. By using the pattern we gain
    loose coupling between the tiers and encapsulate knowledge about
    how to locate, connect to, and interact with the business objects
    that make up the application.

## Concurrency

- Async Method Invocation

  - Asynchronous method invocation is pattern where the calling thread
    is not blocked while waiting results of tasks. The pattern
    provides parallel processing of multiple independent tasks and
    retrieving the results via callbacks or waiting until everything
    is done.

- Balking

  - Balking Pattern is used to prevent an object from executing
    certain code if it is an incomplete or inappropriate state

- Double Checked Locking

  - Reduce the overhead of acquiring a lock by first testing the
    locking criterion (the "lock hint") without actually acquiring the
    lock. Only if the locking criterion check indicates that locking
    is required does the actual locking logic proceed.

- Event Queue

  - Event Queue is a good pattern if You have a limited accessibility
    resource (for example: Audio or Database), but You need to handle
    all the requests that want to use that. It puts all the requests
    in a queue and process them asynchronously. Gives the resource for
    the event when it is the next in the queue and in same time
    removes it from the queue.

- Event-based Asynchronous

  - The Event-based Asynchronous Pattern makes available the
    advantages of multithreaded applications while hiding many of the
    complex issues inherent in multithreaded design. Using a class
    that supports this pattern can allow you to:

    - Perform time-consuming tasks, such as downloads and database operations, "in the background," without interrupting your application.
    - Execute multiple operations simultaneously, receiving notifications when each completes.
    - Wait for resources to become available without stopping ("hanging") your application.
    - Communicate with pending asynchronous operations using the familiar events-and-delegates model.

- Guarded Suspension

  - Use Guarded suspension pattern to handle a situation when you want
    to execute a method on object which is not in a proper state.

- Half-Sync/Half-Async

  - The Half-Sync/Half-Async pattern decouples synchronous I/O from
    asynchronous I/O in a system to simplify concurrent programming
    effort without degrading execution efficiency.

- Mutex

  - Mutual Exclusion Lock Binary Semaphore

- Producer Consumer

  - Producer Consumer Design pattern is a classic concurrency pattern
    which reduces coupling between Producer and Consumer by separating
    Identification of work with Execution of Work.

- Promise

  - A Promise represents a proxy for a value not necessarily known
    when the promise is created. It allows you to associate dependent
    promises to an asynchronous action's eventual success value or
    failure reason. Promises are a way to write async code that still
    appears as though it is executing in a synchronous way.

- Reactor

  - The Reactor design pattern handles service requests that are
    delivered concurrently to an application by one or more
    clients. The application can register specific handlers for
    processing which are called by reactor on specific
    events. Dispatching of event handlers is performed by an
    initiation dispatcher, which manages the registered event
    handlers. Demultiplexing of service requests is performed by a
    synchronous event demultiplexer.

- Reader Writer Lock

  - Suppose we have a shared memory area with the basic constraints
    detailed above. It is possible to protect the shared data behind a
    mutual exclusion mutex, in which case no two threads can access
    the data at the same time. However, this solution is suboptimal,
    because it is possible that a reader R1 might have the lock, and
    then another reader R2 requests access. It would be foolish for R2
    to wait until R1 was done before starting its own read operation;
    instead, R2 should start right away. This is the motivation for
    the Reader Writer Lock pattern.

- Semaphore

  - Create a lock which mediates access to a pool of resources. Only a
    limited number of threads, specified at the creation of the
    semaphore, can access the resources at any given time. A semaphore
    which only allows one concurrent access to a resource is called a
    binary semaphore.

- Thread Local Storage

  - Securing variables global to a thread against being spoiled by
    other threads. That is needed if you use class variables or static
    variables in your Callable object or Runnable object that are not
    read-only.

- Thread Pool

  - It is often the case that tasks to be executed are short-lived and
    the number of tasks is large. Creating a new thread for each task
    would make the system spend more time creating and destroying the
    threads than executing the actual tasks. Thread Pool solves this
    problem by reusing existing threads and eliminating the latency of
    creating new threads.

## [Creational](#gof-pattern)

## Integration

- Message Channel

 - When two applications communicate using a messaging system they do
   it by using logical addresses of the system, so called Message
   Channels.
 
- Publish Subscribe

  - Broadcast messages from sender to all the interested receivers.
  - similar to observer pattern

- Tolerant Reader

  - Tolerant Reader is an integration pattern that helps creating
    robust communication systems. The idea is to be as tolerant as
    possible when reading data from another service. This way, when
    the communication schema changes, the readers must not break.

## Persistence Tier

- Data Access Object

  - Object provides an abstract interface to some type of database or
    other persistence mechanism.

- Data Mapper

  - A layer of mappers that moves data between objects and a database
    while keeping them independent of each other and the mapper itself

- Repository

  - Repository layer is added between the domain and data mapping
    layers to isolate domain objects from details of the database
    access code and to minimize scattering and duplication of query
    code. The Repository pattern is especially useful in systems where
    number of domain classes is large or heavy querying is utilized.

## Presentation Tier

- Flux

  - Flux eschews MVC in favor of a unidirectional data flow. When a
    user interacts with a view, the view propagates an action through
    a central dispatcher, to the various stores that hold the
    application's data and business logic, which updates all of the
    views that are affected.

- Front Controller

  - Introduce a common handler for all requests for a web site. This
    way we can encapsulate common functionality such as security,
    internationalization, routing and logging in a single place.

- Model-View-Controller

  - Separate the user interface into three interconnected components:
    the model, the view and the controller. Let the model manage the
    data, the view display the data and the controller mediate
    updating the data and redrawing the display.

- Model-View-Presenter

  - Apply a "Separation of Concerns" principle in a way that allows
    developers to build and test user interfaces.
  - [안드로이드의 MVC, MVP, MVVM 종합 안내서](https://academy.realm.io/kr/posts/eric-maxwell-mvc-mvp-and-mvvm-on-android/)

## [Structural](#gof-pattern)

## Testing

- Page Object

  - Page Object encapsulates the UI, hiding the underlying UI widgetry
    of an application (commonly a web application) and providing an
    application-specific API to allow the manipulation of UI
    components required for tests.
  
## Other

- Caching

  - To avoid expensive re-acquisition of resources by not releasing
    the resources immediately after their use. The resources retain
    their identity, are kept in some fast-access storage, and are
    re-used to avoid having to acquire them again.

- Callback

  - Callback is a piece of executable code that is passed as an
    argument to other code, which is expected to call back (execute)
    the argument at some convenient time.

- Double Dispatch

  - Double Dispatch pattern is a way to create maintainable dynamic
    behavior based on receiver and parameter types.

- Execute Around

  - Execute Around idiom frees the user from certain actions that
    should always be executed before and after the business method. A
    good example of this is resource allocation and deallocation
    leaving the user to specify only what to do with the resource.

- Fluent Interface

  - A fluent interface provides an easy-readable, flowing interface,
    that often mimics a domain specific language. Using this pattern
    results in code that can be read nearly as human language.

- Lazy Loading

  - Lazy loading is a design pattern commonly used to defer
    initialization of an object until the point at which it is
    needed. It can contribute to efficiency in the program's operation
    if properly and appropriately used.

- Monad

  - Monad pattern based on monad from linear algebra represents the
    way of chaining operations together step by step. Binding
    functions can be described as passing one's output to another's
    input basing on the 'same type' contract. Formally, monad consists
    of a type constructor M and two operations: bind - that takes
    monadic object and a function from plain object to monadic value
    and returns monadic value return - that takes plain type object
    and returns this object wrapped in a monadic value.

- Mute Idiom

  - Provide a template to suppress any exceptions that either are
    declared but cannot occur or should only be logged; while
    executing some business logic. The template removes the need to
    write repeated try-catch blocks.

- Poison Pill

  - Poison Pill is known predefined data item that allows to provide
    graceful shutdown for separate distributed consumption process.

- Private Class Data

  - Private Class Data design pattern seeks to reduce exposure of
    attributes by limiting their visibility. It reduces the number of
    class attributes by encapsulating them in single Data object.

- Queue based load leveling

  - Use a queue that acts as a buffer between a task and a service
    that it invokes in order to smooth intermittent heavy loads that
    may otherwise cause the service to fail or the task to time
    out. This pattern can help to minimize the impact of peaks in
    demand on availability and responsiveness for both the task and
    the service.

- Resource Acquisition is Initialization

  - Resource Acquisition Is Initialization pattern can be used to
    implement exception safe resource management.
  - similar to execute around pattern