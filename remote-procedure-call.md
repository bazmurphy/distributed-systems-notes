# Remote Procedure Call (RPC)

In distributed computing **Remote Procedure Call (RPC)** acts as a bridge between programs residing on different computers.

It allows a program, called the **client**, to **execute code** on another program, called the **server**, while hiding the complexity of network communication from the programmer.

It allows a program on one computer (the client) to execute a function (procedure) on another computer (the server), all while appearing as if the function is running locally on the client's machine.

---

---

## How RPC works

- **Client-Server Model:**
  - RPC follows the client-server model, where the client initiates the call, providing necessary data, and waits for a response from the server.

1. **Initiating the call:**

   - The client program makes a call to a procedure as if it were any other local function within its own code. This call includes any necessary **parameters** (data) that the server needs to execute the procedure.

2. **Under the hood:**
   - An **RPC framework** takes over behind the scenes. It translates the local function call into a network message containing the procedure name, parameters, and other information. This message is then sent across the network to the server.
3. **Server in action:**
   - The server receives the message, understands the procedure call, and executes the requested function with the provided parameters.
4. **Sending the results:**
   - Once the execution is complete, the server sends a response message back to the client, which may contain the results of the procedure or an error message.
5. **Back to the client:**
   - Finally, the RPC framework on the client-side receives the response and translates it back into a format the client program understands. The client program then continues execution as if the procedure was executed locally.

---

## Why is RPC Used?

RPC offers several advantages that make it a popular choice for building distributed applications:

- **Simplified development:**

  - As mentioned before, RPC hides the network communication complexity, allowing developers to focus on the function's logic instead of dealing with low-level networking details. RPC makes it easier to develop distributed applications by **simplifying the communication process**. Programmers don't need to deal with the intricacies of network programming, allowing them to focus on the application logic.

- **Abstraction:**
  - It **hides the network communication details** from the programmer. You write the code as if you are calling a local function, making development easier and more intuitive.
- **Platform independence:**
  - RPC frameworks can be implemented on various platforms, allowing communication between programs running on different operating systems or hardware architectures. RPC can work across different **operating systems** and hardware architectures as long as both the client and server support the same RPC protocol. RPC frameworks can be designed to work across different operating systems and programming languages, facilitating communication between heterogeneous systems.
- **Code reusability:**
  - Functions designed for local execution can often be easily adapted to remote execution using RPC, promoting code reuse and reducing development time. Code written for local procedures can be easily **adapted** for remote procedures, reducing development time and effort.
- **Modular design:**
  - RPC encourages modularity by allowing different parts of an application to be distributed across different machines, making it easier to manage and scale applications.
- **Performance:**
  - RPC can be optimized for specific needs, balancing **efficiency** and **flexibility** depending on the application requirements.
- **Focus on functionality:**
  - Developers can concentrate on the application logic rather than the intricacies of network communication.
- **Code reuse:**
  - By allowing remote procedure calls, you can **reuse existing code** on different machines without significant modifications.

---

It's important to note that RPC also has some drawbacks, such as potential performance overhead due to network communication and the possibility of increased security risks when dealing with remote calls. It's also crucial to choose an appropriate RPC framework for secure and reliable communication between programs.

---

## Stubs

A **stub** is a piece of code that acts as an intermediary between the client and server, handling the conversion of parameters and communication details.

There are two main types of stubs:

- **Client stub:** This resides on the **client** side and acts as a proxy for the remote procedure. It receives the function call from the client program, converts the parameters into a format suitable for network transmission, and then sends them to the server. It also receives the response from the server, converts it back to the expected format, and returns it to the client program, making the entire process appear like a local function call for the client.

- **Server stub:** This resides on the **server** side and acts as a bridge between the network and the actual implementation of the remote procedure. It receives the message sent by the client stub, unpacks the parameters, and calls the actual procedure on the server. Once the procedure finishes, the server stub packs the return value and sends it back to the client stub.

Both client and server stubs play crucial roles in achieving **transparency** in RPC. They hide the underlying communication details and network complexities from the application code, making it appear as if the remote procedure is being executed locally. This allows developers to write code without worrying about the specifics of distributed communication.

---

## Diagrams:

![](/images/remote-procedure-call-01.png)

![](/images/remote-procedure-call-02.png)
