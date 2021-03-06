# The linguistic paradigm of (micro)services

This document defines the key elements of the linguistic paradigm of (micro)services.

This terminology is used in the Jolie website and documentation.

### Operation
A functionality exposed by a service.

### Interface
A machine-readable and -checkable declaration of a set of operations, which defines an API.
An interface acts as the contract between a service and its clients.

### Ports
Ports are endpoints used for sending and receiving messages.
There are two kind of ports:
- _input ports_ are used for receiving messages;
- and _output ports_ are used for sending messages.

A port includes at least three elements:
- the location at which the port is deployed, e.g., an IP address;
- the transport protocol used for communications through the port;
- the interface that the port makes accessible.

### Connection
We say that an output port is _connected to_ an input port when it is meant that messages sent through the former will reach the latter.

This typically happens when the output port has the same location and protocol as the target input port, but
network or container configurations might alter this. As such, knowing the connections in a system requires looking both at 
the definitions of the involved ports and how they are deployed in the system.

### Service (or microservice)
A service is a running software application that supplies APIs in the form of operations available at its input ports. It communicates with other services by message passing.

### Service definition
The code that, when executed, implements a service. When clear from the context, we simply use the word service interchangeably.

### Conversation
A conversation is a series of related message exchanges between two or more services.

During a conversation between a client and a service, the set of available operations offered by the service to the client might change over time (e.g., after successfully logging in the client might gain access to more operations).

A service is always willing to serve requests for its available API.

### Behaviour
The part of the service definition which defines the logics to be executed at runtime for implementing a service's API. Behaviours can send and/or receive messages, and perform internal computation.

### Process
A running instance of a behaviour, equipped with its own private state and message queues.

### Service dependency
When a service `A` has an output port that needs to be connected to another service `B` in order for the service `A` to function, we say that service `A` _depends on_ service `B`.

![](.gitbook/assets/definitions.png)

## Alternativa 1: service network (o composition)

**FM: nel momento in cui generalizziamo il concetto di frame a qualunque virtual network con private connections, non e' piu' vero che un frame puo' essere visto come un singolo servizio mi sa. O si'? In ogni caso mi piacerebbe togliere questo requisito. Inoltre dato un gruppo di servizi non e' detto che sia connesso. Ho provato a generalizzare tutte le def in service network (possiamo cambiare il nome network magari). La parola network e' gia' nella testa della gente, ed ammette composizioni di networks come un unico network (sfruttiamo il fatto che siano gia' abituati al concetto di networks of networks).**

### Service network, o Service composition, o Service circuit

A group of services and their connections.

Some networks allow for _private locations_: locations that are visible only to the services in the network.

The nature of a private location depends on the implementation, e.g., shared-memory channels, local sockets, virtual networks.

Networks can be composed into bigger networks (networks of networks), allowing for communication between services in different networks.

## Alternativa 2: service environment, frame, and circuit

### Service Environment
The execution context where one or more services can be executed

### Service Frame
A group of services running in the same service environment, which can communicate by using in-application shared-memory connections that cannot be accessed from outside the frame. A Service Frame can always be represented as a single service when hiding the internal connections.

### Service Circuit
A connected composition of services or frames.
