# gRPC

gRPC, which stands for **gRPC Remote Procedure Calls**, is a **modern, open-source, high-performance framework** that allows applications to communicate with each other as if they were local, even when they are running on different machines.

It essentially enables developers to **make remote procedure calls (RPCs)**, meaning a client application can "call" a method on a server application just like it would call a method on a local object.

**Features:**

- **Cross-platform:**
  - gRPC can be used in various environments and can connect services written in different programming languages like **Go, Python, Java, C#, C++**, and more.
- **High performance:**
  - gRPC utilizes **HTTP/2** for transport, which is faster and more efficient than traditional HTTP/1.1, making it ideal for high-volume communication between services.
- **Protocol Buffers:**
  - gRPC uses **Protocol Buffers** as the interface definition language. This helps define the data format for communication, ensuring consistent data exchange between clients and servers.
- **Advanced features:**
  - gRPC offers additional features like **authentication, bidirectional streaming, flow control, blocking or non-blocking bindings, cancellation, and timeouts**, making it suitable for complex communication needs.

**Benefits and reasons for using gRPC:**

- **Simplifies building distributed systems:**
  - gRPC allows developers to focus on the core functionality of their applications without worrying about the complexities of network communication.
- **Improved performance:**
  - Due to its efficient transport and data format, gRPC offers significantly better performance compared to traditional methods.
- **Increased developer productivity:**
  - gRPC simplifies communication between services and reduces development time.
- **Scalability:**
  - gRPC is well-suited for building scalable systems as it can efficiently handle large volumes of data and connections.
- **Wide adoption:**
  - gRPC is used by many organizations, including Google, making it a reliable and well-supported technology.

However, it's important to note that due to its complexity with HTTP/2, **implementing gRPC clients directly in web browsers is not feasible**. Instead, a proxy server is often required for browser-based communication with gRPC services.

Overall, gRPC is a powerful tool for building high-performance, scalable, and efficient distributed systems. Its ease of use, rich features, and widespread adoption make it a popular choice for developers working on building modern applications.

## Diagrams:

![](/images/grpc-01.svg)

![](/images/grpc-02.png)

## Links

https://medium.com/@lchang1994/deep-dive-grpc-protobuf-http-2-0-74e6295f1d38
