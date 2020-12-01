---
title: Verwenden eines asynchronen Serversockets
description: Dieses Beispiel zeigt einen asynchronen Serversocket. Die Socket-Klasse verwendet die asynchrone .NET Framework-Programmierung, um Netzwerkdienstanforderungen zu verarbeiten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- Socket class, asynchronous server sockets
- data requests, sockets
- sockets, asynchronous server sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- asynchronous server sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
ms.openlocfilehash: 6800a1973d9eb65bbb7520f9db7a8f431656c685
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265205"
---
# <a name="using-an-asynchronous-server-socket"></a><span data-ttu-id="6d03e-104">Verwenden eines asynchronen Serversockets</span><span class="sxs-lookup"><span data-stu-id="6d03e-104">Using an Asynchronous Server Socket</span></span>

<span data-ttu-id="6d03e-105">Asynchrone Serversockets verwenden das asynchrone Programmiermodell von .NET Framework, um Dienstanforderungen über das Netzwerk zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6d03e-105">Asynchronous server sockets use the .NET Framework asynchronous programming model to process network service requests.</span></span> <span data-ttu-id="6d03e-106">Die <xref:System.Net.Sockets.Socket>-Klasse folgt dem asynchronen Standardbenennungsmuster von .NET Framework, z.B. entspricht die synchrone <xref:System.Net.Sockets.Socket.Accept%2A>-Methode den asynchronen <xref:System.Net.Sockets.Socket.BeginAccept%2A>- und <xref:System.Net.Sockets.Socket.EndAccept%2A>-Methoden.</span><span class="sxs-lookup"><span data-stu-id="6d03e-106">The <xref:System.Net.Sockets.Socket> class follows the standard .NET Framework asynchronous naming pattern; for example, the synchronous <xref:System.Net.Sockets.Socket.Accept%2A> method corresponds to the asynchronous <xref:System.Net.Sockets.Socket.BeginAccept%2A> and <xref:System.Net.Sockets.Socket.EndAccept%2A> methods.</span></span>  
  
 <span data-ttu-id="6d03e-107">Ein asynchroner Serversocket erfordert, dass eine Methode damit beginnt, Verbindungsanforderungen über das Netzwerk und eine Rückrufmethode anzunehmen, um die Verbindungsanforderungen zu verarbeiten und ebenfalls damit beginnt, Daten aus dem Netzwerk und eine Rückrufmethode zu empfangen, um den Datenempfang zu beenden.</span><span class="sxs-lookup"><span data-stu-id="6d03e-107">An asynchronous server socket requires a method to begin accepting connection requests from the network, a callback method to handle the connection requests and begin receiving data from the network, and a callback method to end receiving the data.</span></span> <span data-ttu-id="6d03e-108">Alle diese Methoden werden in diesem Abschnitt weiter erläutert.</span><span class="sxs-lookup"><span data-stu-id="6d03e-108">All these methods are discussed further in this section.</span></span>  
  
 <span data-ttu-id="6d03e-109">Im folgenden Beispiel initialisiert die `StartListening`-Methode den **Socket**, um mit der Annahme der Verbindungsanforderungen über das Netzwerk zu beginnen, und verwendet dann die **BeginAccept**-Methode, um neue Verbindungen anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="6d03e-109">In the following example, to begin accepting connection requests from the network, the method `StartListening` initializes the **Socket** and then uses the **BeginAccept** method to start accepting new connections.</span></span> <span data-ttu-id="6d03e-110">Die Accept-Rückrufmethode wird aufgerufen, wenn eine neue Verbindungsanforderung für den Socket empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="6d03e-110">The accept callback method is called when a new connection request is received on the socket.</span></span> <span data-ttu-id="6d03e-111">Dient zum Abrufen der **Socket**-Instanz, die die Verbindung verarbeitet, und den **Socket** an den Thread übergibt, der die Anforderung verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6d03e-111">It is responsible for getting the **Socket** instance that will handle the connection and handing that **Socket** off to the thread that will process the request.</span></span> <span data-ttu-id="6d03e-112">Der Accept-Rückrufmethode implementiert den <xref:System.AsyncCallback>-Delegaten. Sie gibt „void“ zurück und nimmt einen einzelnen Parameter vom Typ <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="6d03e-112">The accept callback method implements the <xref:System.AsyncCallback> delegate; it returns a void and takes a single parameter of type <xref:System.IAsyncResult>.</span></span> <span data-ttu-id="6d03e-113">Das folgende Beispiel ist die Shell einer Accept-Rückrufmethode.</span><span class="sxs-lookup"><span data-stu-id="6d03e-113">The following example is the shell of an accept callback method.</span></span>  
  
```vb  
Sub AcceptCallback(ar As IAsyncResult)  
    ' Add the callback code here.  
End Sub 'AcceptCallback  
```  
  
```csharp  
void AcceptCallback(IAsyncResult ar)
{  
    // Add the callback code here.  
}  
```  
  
 <span data-ttu-id="6d03e-114">Die **BeginAccept**-Methode akzeptiert zwei Parameter: einen **AsyncCallback**-Delegaten, der auf die Accept-Rückrufmethode verweist, und ein Objekt, das verwendet wird, um Statusinformationen an die Rückrufmethode zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="6d03e-114">The **BeginAccept** method takes two parameters, an **AsyncCallback** delegate that points to the accept callback method and an object that is used to pass state information to the callback method.</span></span> <span data-ttu-id="6d03e-115">Im folgenden Beispiel wird der überwachende **Socket** durch den *State*-Parameter an die Rückrufmethode übergeben.</span><span class="sxs-lookup"><span data-stu-id="6d03e-115">In the following example, the listening **Socket** is passed to the callback method through the *state* parameter.</span></span> <span data-ttu-id="6d03e-116">In diesem Beispiel wird ein **AsyncCallback**-Delegat erstellt und Verbindungen werden aus dem Netzwerk angenommen.</span><span class="sxs-lookup"><span data-stu-id="6d03e-116">This example creates an **AsyncCallback** delegate and starts accepting connections from the network.</span></span>  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.AcceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(new AsyncCallback(SocketListener.AcceptCallback), listener);  
```  
  
 <span data-ttu-id="6d03e-117">Asynchrone Sockets können Threads aus dem Systemthreadpool verwenden, um eingehende Verbindungen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6d03e-117">Asynchronous sockets use threads from the system thread pool to process incoming connections.</span></span> <span data-ttu-id="6d03e-118">Ein Thread ist verantwortlich für das Akzeptieren von Verbindungen, ein anderer Thread wird verwendet, um alle eingehenden Verbindungen zu behandeln, und ein anderer Thread ist verantwortlich für den Empfang von Daten aus der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="6d03e-118">One thread is responsible for accepting connections, another thread is used to handle each incoming connection, and another thread is responsible for receiving data from the connection.</span></span> <span data-ttu-id="6d03e-119">Diese können im selben Thread vorhanden sein, je nachdem, welcher Thread vom Threadpool zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6d03e-119">These could be the same thread, depending on which thread is assigned by the thread pool.</span></span> <span data-ttu-id="6d03e-120">Im folgenden Beispiel hält die <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse die Ausführung des Hauptthreads an und signalisiert, wann die Ausführung fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6d03e-120">In the following example, the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class suspends execution of the main thread and signals when execution can continue.</span></span>  
  
 <span data-ttu-id="6d03e-121">Das folgende Beispiel zeigt eine asynchrone Methode, die einen asynchronen TCP/IP-Socket auf dem lokalen Computer erstellt und beginnt, Verbindungen zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="6d03e-121">The following example shows an asynchronous method that creates an asynchronous TCP/IP socket on the local computer and begins accepting connections.</span></span> <span data-ttu-id="6d03e-122">Es wird davon ausgegangen, dass ein globaler **ManualResetEvent** mit dem Namen `allDone` existiert, dass die Methode ein Member einer Klasse mit dem Namen `SocketListener` ist, und eine Rückrufmethode namens `AcceptCallback` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6d03e-122">It assumes that there is a global **ManualResetEvent** named `allDone`, that the method is a member of a class named `SocketListener`, and that a callback method named `AcceptCallback` is defined.</span></span>  
  
```vb  
Public Sub StartListening()  
    Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
    Dim localEP = New IPEndPoint(ipHostInfo.AddressList(0), 11000)  
  
    Console.WriteLine($"Local address and port : {localEP.ToString()}")  
  
    Dim listener As New Socket(localEP.Address.AddressFamily, _  
       SocketType.Stream, ProtocolType.Tcp)  
  
    Try  
        listener.Bind(localEP)  
        listener.Listen(10)  
  
        While True  
            allDone.Reset()  
  
            Console.WriteLine("Waiting for a connection...")  
            listener.BeginAccept(New _  
                AsyncCallback(SocketListener.AcceptCallback), _  
                listener)  
  
            allDone.WaitOne()  
        End While  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
    Console.WriteLine("Closing the listener...")  
End Sub 'StartListening  
```  
  
```csharp  
public void StartListening()
{  
    IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
    IPEndPoint localEP = new IPEndPoint(ipHostInfo.AddressList[0], 11000);  
  
    Console.WriteLine($"Local address and port : {localEP.ToString()}");  
  
    Socket listener = new Socket(localEP.Address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);  
  
    try
    {  
        listener.Bind(localEP);  
        listener.Listen(10);  
  
        while (true)
        {  
            allDone.Reset();  
  
            Console.WriteLine("Waiting for a connection...");  
            listener.BeginAccept(new AsyncCallback(SocketListener.AcceptCallback), listener);  
  
            allDone.WaitOne();  
        }  
    }
    catch (Exception e)
    {  
        Console.WriteLine(e.ToString());  
    }  
  
    Console.WriteLine("Closing the listener...");  
}  
```  
  
 <span data-ttu-id="6d03e-123">Die Accept-Rückrufmethode (`AcceptCallback` im vorherigen Beispiel) ist verantwortlich dafür, dass dem Thread der Hauptanwendung signalisiert wird, den Vorgang fortzusetzen, die Verbindung mit dem Client herzustellen, und das asynchrone Lesen der Datenmengen vom Client zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="6d03e-123">The accept callback method (`AcceptCallback` in the preceding example) is responsible for signaling the main application thread to continue processing, establishing the connection with the client, and starting the asynchronous read of data from the client.</span></span> <span data-ttu-id="6d03e-124">Das folgende Beispiel ist der erste Teil einer Implementierung der `AcceptCallback`-Methode.</span><span class="sxs-lookup"><span data-stu-id="6d03e-124">The following example is the first part of an implementation of the `AcceptCallback` method.</span></span> <span data-ttu-id="6d03e-125">Dieser Abschnitt der Methode signalisiert dem Hauptanwendungsthread, dass die Verarbeitung fortgesetzt wird, und stellt die Verbindung mit dem Client her.</span><span class="sxs-lookup"><span data-stu-id="6d03e-125">This section of the method signals the main application thread to continue processing and establishes the connection to the client.</span></span> <span data-ttu-id="6d03e-126">Es wird ein globales **ManualResetEvent** mit dem Namen `allDone` vorausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="6d03e-126">It assumes a global **ManualResetEvent** named `allDone`.</span></span>  
  
```vb  
Public Sub AcceptCallback(ar As IAsyncResult)  
    allDone.Set()  
  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Additional code to read data goes here.  
End Sub 'AcceptCallback  
```  
  
```csharp  
public void AcceptCallback(IAsyncResult ar)
{  
    allDone.Set();  
  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Additional code to read data goes here.
}  
```  
  
 <span data-ttu-id="6d03e-127">Das Lesen von Daten aus einem Clientsocket erfordert ein Zustandsobjekt, das Werte zwischen asynchronen Aufrufen übergibt.</span><span class="sxs-lookup"><span data-stu-id="6d03e-127">Reading data from a client socket requires a state object that passes values between asynchronous calls.</span></span> <span data-ttu-id="6d03e-128">Das folgende Beispiel implementiert ein Zustandsobjekt für den Empfang einer Zeichenfolge vom Remoteclient.</span><span class="sxs-lookup"><span data-stu-id="6d03e-128">The following example implements a state object for receiving a string from the remote client.</span></span> <span data-ttu-id="6d03e-129">Es enthält Felder für den Clientsocket, einen Datenpuffer zum Empfangen von Daten, und ein <xref:System.Text.StringBuilder> für die Erstellung einer Datenzeichenfolge, die vom Client gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6d03e-129">It contains fields for the client socket, a data buffer for receiving data, and a <xref:System.Text.StringBuilder> for creating the data string sent by the client.</span></span> <span data-ttu-id="6d03e-130">Wenn Sie diese Felder in das Statusobjekt platzieren, können ihre Werte über mehrere Aufrufe gespeichert werden, damit Daten aus dem Clientsocket gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="6d03e-130">Placing these fields in the state object allows their values to be preserved across multiple calls to read data from the client socket.</span></span>  
  
```vb  
Public Class StateObject  
    Public workSocket As Socket = Nothing  
    Public BufferSize As Integer = 1024  
    Public buffer(BufferSize) As Byte  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject
{  
    public Socket workSocket = null;  
    public const int BufferSize = 1024;  
    public byte[] buffer = new byte[BufferSize];  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 <span data-ttu-id="6d03e-131">Der Abschnitt der `AcceptCallback`-Methode, der den Datenempfang aus dem Clientsocket beginnt, initialisiert zunächst eine Instanz der `StateObject`-Klasse und ruft dann die <xref:System.Net.Sockets.Socket.BeginReceive%2A>-Methode zum asynchronen Lesen von Daten aus dem Clientsocket auf.</span><span class="sxs-lookup"><span data-stu-id="6d03e-131">The section of the `AcceptCallback` method that starts receiving the data from the client socket first initializes an instance of the `StateObject` class and then calls the <xref:System.Net.Sockets.Socket.BeginReceive%2A> method to start reading the data from the client socket asynchronously.</span></span>  
  
 <span data-ttu-id="6d03e-132">Das folgende Beispiel zeigt die vollständige `AcceptCallback`-Methode.</span><span class="sxs-lookup"><span data-stu-id="6d03e-132">The following example shows the complete `AcceptCallback` method.</span></span> <span data-ttu-id="6d03e-133">Es wird davon ausgegangen, dass ein globales **ManualResetEvent** mit dem Namen `allDone,` existiert, dass die `StateObject`-Klasse definiert und die `ReadCallback`-Methode in einer Klasse mit dem Namen `SocketListener` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6d03e-133">It assumes that there is a global **ManualResetEvent** named `allDone,` that the `StateObject` class is defined, and that the `ReadCallback` method is defined in a class named `SocketListener`.</span></span>  
  
```vb  
Public Shared Sub AcceptCallback(ar As IAsyncResult)  
    ' Get the socket that handles the client request.  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Signal the main thread to continue.  
    allDone.Set()  
  
    ' Create the state object.  
    Dim state As New StateObject()  
    state.workSocket = handler  
    handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
        AddressOf AsynchronousSocketListener.ReadCallback, state)  
End Sub 'AcceptCallback  
```  
  
```csharp  
public static void AcceptCallback(IAsyncResult ar)
{  
    // Get the socket that handles the client request.  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Signal the main thread to continue.  
    allDone.Set();  
  
    // Create the state object.  
    StateObject state = new StateObject();  
    state.workSocket = handler;  
    handler.BeginReceive(state.buffer, 0, StateObject.BufferSize, 0,  
        new AsyncCallback(AsynchronousSocketListener.ReadCallback), state);  
}  
```  
  
 <span data-ttu-id="6d03e-134">Die letzte Methode, die für den asynchronen Socketserver implementiert werden muss, ist die Read-Rückrufmethode, die vom Client gesendete Daten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6d03e-134">The final method that needs to be implemented for the asynchronous socket server is the read callback method that returns the data sent by the client.</span></span> <span data-ttu-id="6d03e-135">Wie die Accept-Rückrufmethode, ist die Read-Rückrufmethode ein **AsyncCallback**-Delegat.</span><span class="sxs-lookup"><span data-stu-id="6d03e-135">Like the accept callback method, the read callback method is an **AsyncCallback** delegate.</span></span> <span data-ttu-id="6d03e-136">Diese Methode liest ein oder mehrere Bytes vom Clientsocket in den Datenpuffer und ruft dann die **BeginReceive**-Methode erneut auf, sobald die vom Client gesendeten Daten vollständig sind.</span><span class="sxs-lookup"><span data-stu-id="6d03e-136">This method reads one or more bytes from the client socket into the data buffer and then calls the **BeginReceive** method again until the data sent by the client is complete.</span></span> <span data-ttu-id="6d03e-137">Nachdem die gesamte Nachricht vom Client gelesen wurde, wird die Zeichenfolge in der Konsole angezeigt und der Serversocket, der die Verbindung mit dem Client verarbeitet, wird geschlossen.</span><span class="sxs-lookup"><span data-stu-id="6d03e-137">Once the entire message has been read from the client, the string is displayed on the console and the server socket handling the connection to the client is closed.</span></span>  
  
 <span data-ttu-id="6d03e-138">Das folgende Beispiel implementiert die `ReadCallback`-Methode.</span><span class="sxs-lookup"><span data-stu-id="6d03e-138">The following sample implements the `ReadCallback` method.</span></span> <span data-ttu-id="6d03e-139">Es wird vorausgesetzt, dass die `StateObject`-Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6d03e-139">It assumes that the `StateObject` class is defined.</span></span>  
  
```vb  
Public Shared Sub ReadCallback(ar As IAsyncResult)  
    Dim state As StateObject = CType(ar.AsyncState, StateObject)  
    Dim handler As Socket = state.workSocket  
  
    ' Read data from the client socket.
    Dim read As Integer = handler.EndReceive(ar)  
  
    ' Data was read from the client socket.  
    If read > 0 Then  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, read))  
        handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf ReadCallback, state)  
    Else  
        If state.sb.Length > 1 Then  
            ' All the data has been read from the client;  
            ' display it on the console.  
            Dim content As String = state.sb.ToString()  
            Console.WriteLine($"Read {content.Length} bytes from socket. {ControlChars.Cr} Data : {content}")  
        End If  
    End If  
End Sub 'ReadCallback  
```  
  
```csharp  
public static void ReadCallback(IAsyncResult ar)
{  
    StateObject state = (StateObject) ar.AsyncState;  
    Socket handler = state.WorkSocket;  
  
    // Read data from the client socket.  
    int read = handler.EndReceive(ar);  
  
    // Data was read from the client socket.  
    if (read > 0)
    {  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,read));  
        handler.BeginReceive(state.buffer, 0, StateObject.BufferSize, 0,  
            new AsyncCallback(ReadCallback), state);  
    }
    else
    {  
        if (state.sb.Length > 1)
        {  
            // All the data has been read from the client;  
            // display it on the console.  
            string content = state.sb.ToString();  
            Console.WriteLine($"Read {content.Length} bytes from socket.\n Data : {content}");
        }  
        handler.Close();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d03e-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d03e-140">See also</span></span>

- [<span data-ttu-id="6d03e-141">Verwenden eines synchronen Serversockets</span><span class="sxs-lookup"><span data-stu-id="6d03e-141">Using a Synchronous Server Socket</span></span>](using-a-synchronous-server-socket.md)
- [<span data-ttu-id="6d03e-142">Asynchroner Serversocket, Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d03e-142">Asynchronous Server Socket Example</span></span>](asynchronous-server-socket-example.md)
- [<span data-ttu-id="6d03e-143">Threading</span><span class="sxs-lookup"><span data-stu-id="6d03e-143">Threading</span></span>](../../standard/threading/index.md)
- [<span data-ttu-id="6d03e-144">Überwachen mit Sockets</span><span class="sxs-lookup"><span data-stu-id="6d03e-144">Listening with Sockets</span></span>](listening-with-sockets.md)
