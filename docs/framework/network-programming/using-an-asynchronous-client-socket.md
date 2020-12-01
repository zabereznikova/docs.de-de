---
title: Verwenden von asynchronen Clientsockets
description: Dieses Beispiel zeigt einen asynchronen Clientsocket. Durch die asynchrone .NET Framework-Programmierung kann eine Anwendung weiterhin ausgeführt werden, während eine Verbindung verarbeitet wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- asynchronous client sockets
- Socket class, asynchronous client sockets
- requesting data from Internet, sockets
- sockets, asynchronous client sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: fd85bc88-e06c-467d-a30d-9fd7cffcfca1
ms.openlocfilehash: af5379533e51e7488d673359dc24268c6329c082
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265218"
---
# <a name="using-an-asynchronous-client-socket"></a><span data-ttu-id="4726e-104">Verwenden von asynchronen Clientsockets</span><span class="sxs-lookup"><span data-stu-id="4726e-104">Using an Asynchronous Client Socket</span></span>

<span data-ttu-id="4726e-105">Ein asynchroner Clientsocket hält die Anwendung nicht an, während darauf gewartet wird, dass Netzwerkvorgänge abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4726e-105">An asynchronous client socket does not suspend the application while waiting for network operations to complete.</span></span> <span data-ttu-id="4726e-106">Stattdessen wird das standardmäßige asynchrone Programmiermodell von .NET Framework verwendet, um die Netzwerkverbindung in einem Thread zu verarbeiten, während die Anwendung weiterhin auf dem ursprünglichen Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4726e-106">Instead, it uses the standard .NET Framework asynchronous programming model to process the network connection on one thread while the application continues to run on the original thread.</span></span> <span data-ttu-id="4726e-107">Asynchrone Sockets eignen sich für Anwendungen, die das Netzwerk stark nutzen, oder die nicht warten können, bis Netzwerkvorgänge vor dem Fortsetzen abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4726e-107">Asynchronous sockets are appropriate for applications that make heavy use of the network or that cannot wait for network operations to complete before continuing.</span></span>  
  
 <span data-ttu-id="4726e-108">Die <xref:System.Net.Sockets.Socket>-Klasse folgt dem Benennungsmuster von .NET Framework für asynchrone Methoden, z.B. entspricht die synchrone <xref:System.Net.Sockets.Socket.Receive%2A>-Methode den asynchronen <xref:System.Net.Sockets.Socket.BeginReceive%2A>- und <xref:System.Net.Sockets.Socket.EndReceive%2A>-Methoden.</span><span class="sxs-lookup"><span data-stu-id="4726e-108">The <xref:System.Net.Sockets.Socket> class follows the .NET Framework naming pattern for asynchronous methods; for example, the synchronous <xref:System.Net.Sockets.Socket.Receive%2A> method corresponds to the asynchronous <xref:System.Net.Sockets.Socket.BeginReceive%2A> and <xref:System.Net.Sockets.Socket.EndReceive%2A> methods.</span></span>  
  
 <span data-ttu-id="4726e-109">Asynchrone Vorgänge erfordern eine Rückrufmethode, die das Ergebnis des Vorgangs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4726e-109">Asynchronous operations require a callback method to return the result of the operation.</span></span> <span data-ttu-id="4726e-110">Wenn Ihre Anwendung das Ergebnis nicht wissen muss, ist keine Rückrufmethode erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4726e-110">If your application does not need to know the result, then no callback method is required.</span></span> <span data-ttu-id="4726e-111">Der Beispielcode in diesem Abschnitt veranschaulicht die Verwendung einer Methode zum Start einer Verbindung mit einem Netzwerkgerät und einer Rückrufmethode zum Abschließen der Verbindung, einer Methode zum Start des Datenversands und einer Rückrufmethode zum Abschließen des Versands, einer Methode zum Start des Datenempfangs und einer Rückrufmethode zum Abschließen des Datenempfangs.</span><span class="sxs-lookup"><span data-stu-id="4726e-111">The example code in this section demonstrates using a method to start connecting to a network device and a callback method to complete the connection, a method to start sending data and a callback method to complete the send, and a method to start receiving data and a callback method to end receiving data.</span></span>  
  
 <span data-ttu-id="4726e-112">Asynchrone Sockets verwenden mehrere Threads aus dem Systemthreadpool, um Netzwerkverbindungen zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4726e-112">Asynchronous sockets use multiple threads from the system thread pool to process network connections.</span></span> <span data-ttu-id="4726e-113">Ein Thread ist verantwortlich für das Initiieren des Datenversands oder Datenempfangs. Andere Threads schließen die Verbindung zum Netzwerkgerät ab und senden oder empfangen Daten.</span><span class="sxs-lookup"><span data-stu-id="4726e-113">One thread is responsible for initiating the sending or receiving of data; other threads complete the connection to the network device and send or receive the data.</span></span> <span data-ttu-id="4726e-114">In den folgenden Beispielen werden Instanzen der <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse verwendet, um die Ausführung des Hauptthreads anzuhalten und zu signalisieren, wann die Ausführung fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4726e-114">In the following examples, instances of the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class are used to suspend execution of the main thread and signal when execution can continue.</span></span>  
  
 <span data-ttu-id="4726e-115">Zur Verbindung eines asynchronen Sockets mit einem Netzwerkgerät initialisiert die `Connect`-Methode im folgenden Beispiel ein **Socket**, ruft dann die <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType>-Methode auf und übergibt einen Remoteendpunkt, der das Netzwerkgerät, die Rückrufmethode „Connect“ und ein Zustandsobjekt (der Client-**Socket**), darstellt. Dieses wird verwendet, um Zustandsinformationen zwischen asynchronen Aufrufen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="4726e-115">In the following example, to connect an asynchronous socket to a network device, the `Connect` method initializes a **Socket** and then calls the <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType> method, passing a remote endpoint that represents the network device, the connect callback method, and a state object (the client **Socket**), which is used to pass state information between asynchronous calls.</span></span> <span data-ttu-id="4726e-116">Das Beispiel implementiert die `Connect`-Methode zur Verbindung des angegebenen **Socket** mit dem angegebenen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="4726e-116">The example implements the `Connect` method to connect the specified **Socket** to the specified endpoint.</span></span> <span data-ttu-id="4726e-117">Es wird ein globales **ManualResetEvent** mit dem Namen `connectDone` vorausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4726e-117">It assumes a global **ManualResetEvent** named `connectDone`.</span></span>  
  
```vb  
Public Shared Sub Connect(remoteEP As EndPoint, client As Socket)  
    client.BeginConnect(remoteEP, _  
       AddressOf ConnectCallback, client)  
  
    connectDone.WaitOne()  
End Sub 'Connect  
```  
  
```csharp  
public static void Connect(EndPoint remoteEP, Socket client) {  
    client.BeginConnect(remoteEP,
        new AsyncCallback(ConnectCallback), client );  
  
   connectDone.WaitOne();  
}  
```  
  
 <span data-ttu-id="4726e-118">Die Rückrufmethode „Connect“ `ConnectCallback` implementiert den <xref:System.AsyncCallback>-Delegaten.</span><span class="sxs-lookup"><span data-stu-id="4726e-118">The connect callback method `ConnectCallback` implements the <xref:System.AsyncCallback> delegate.</span></span> <span data-ttu-id="4726e-119">Sie stellt eine Verbindung mit dem Remotegerät her, wenn das Remotegerät verfügbar ist, und signalisiert dem Thread der Anwendung, dass die Verbindung abgeschlossen ist, indem **ManualResetEvent** auf `connectDone` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4726e-119">It connects to the remote device when the remote device is available and then signals the application thread that the connection is complete by setting the **ManualResetEvent** `connectDone`.</span></span> <span data-ttu-id="4726e-120">Im folgenden Code wird die `ConnectCallback`-Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="4726e-120">The following code implements the `ConnectCallback` method.</span></span>  
  
```vb  
Private Shared Sub ConnectCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete the connection.  
        client.EndConnect(ar)  
  
        Console.WriteLine("Socket connected to {0}", _  
            client.RemoteEndPoint.ToString())  
  
        ' Signal that the connection has been made.  
        connectDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ConnectCallback  
```  
  
```csharp  
private static void ConnectCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete the connection.  
        client.EndConnect(ar);  
  
        Console.WriteLine("Socket connected to {0}",  
            client.RemoteEndPoint.ToString());  
  
        // Signal that the connection has been made.  
        connectDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="4726e-121">Die Beispielmethode `Send` codiert die angegebenen Zeichenfolgendaten im ASCII-Format und sendet sie asynchron an das Netzwerkgerät, dargestellt durch den angegebenen Socket.</span><span class="sxs-lookup"><span data-stu-id="4726e-121">The example method `Send` encodes the specified string data in ASCII format and sends it asynchronously to the network device represented by the specified socket.</span></span> <span data-ttu-id="4726e-122">Das folgende Beispiel implementiert die `Send`-Methode.</span><span class="sxs-lookup"><span data-stu-id="4726e-122">The following example implements the `Send` method.</span></span>  
  
```vb  
Private Shared Sub Send(client As Socket, data As [String])  
    ' Convert the string data to byte data using ASCII encoding.  
    Dim byteData As Byte() = Encoding.ASCII.GetBytes(data)  
  
    ' Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None, _  
        AddressOf SendCallback, client)  
End Sub 'Send  
```  
  
```csharp  
private static void Send(Socket client, String data) {  
    // Convert the string data to byte data using ASCII encoding.  
    byte[] byteData = Encoding.ASCII.GetBytes(data);  
  
    // Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None,  
        new AsyncCallback(SendCallback), client);  
}  
```  
  
 <span data-ttu-id="4726e-123">Die Rückrufmethode „Send“ `SendCallback` implementiert den <xref:System.AsyncCallback>-Delegaten.</span><span class="sxs-lookup"><span data-stu-id="4726e-123">The send callback method `SendCallback` implements the <xref:System.AsyncCallback> delegate.</span></span> <span data-ttu-id="4726e-124">Die Daten werden gesendet, wenn das Netzwerkgerät für den Empfang bereit ist.</span><span class="sxs-lookup"><span data-stu-id="4726e-124">It sends the data when the network device is ready to receive.</span></span> <span data-ttu-id="4726e-125">Im folgenden Beispiel wird eine Implementierung der `SendCallback`-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4726e-125">The following example shows the implementation of the `SendCallback` method.</span></span> <span data-ttu-id="4726e-126">Ein globales **ManualResetEvent** mit dem Namen `sendDone` wird vorausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4726e-126">It assumes a global **ManualResetEvent** named `sendDone`.</span></span>  
  
```vb  
Private Shared Sub SendCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete sending the data to the remote device.  
        Dim bytesSent As Integer = client.EndSend(ar)  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent)  
  
        ' Signal that all bytes have been sent.  
        sendDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'SendCallback  
```  
  
```csharp  
private static void SendCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete sending the data to the remote device.  
        int bytesSent = client.EndSend(ar);  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent);  
  
        // Signal that all bytes have been sent.  
        sendDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="4726e-127">Das Lesen von Daten aus einem Clientsocket erfordert ein Zustandsobjekt, das Werte zwischen asynchronen Aufrufen übergibt.</span><span class="sxs-lookup"><span data-stu-id="4726e-127">Reading data from a client socket requires a state object that passes values between asynchronous calls.</span></span> <span data-ttu-id="4726e-128">Die folgende Klasse ist ein Beispielstatusobjekt zum Empfangen von Daten von einem Clientsocket.</span><span class="sxs-lookup"><span data-stu-id="4726e-128">The following class is an example state object for receiving data from a client socket.</span></span> <span data-ttu-id="4726e-129">Sie enthält ein Feld für den Clientsocket, einen Puffer für die empfangenen Daten und eine <xref:System.Text.StringBuilder>, die die eingehende Datenzeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="4726e-129">It contains a field for the client socket, a buffer for the received data, and a <xref:System.Text.StringBuilder> to hold the incoming data string.</span></span> <span data-ttu-id="4726e-130">Wenn Sie diese Felder in das Statusobjekt platzieren, können ihre Werte über mehrere Aufrufe gespeichert werden, damit Daten aus dem Clientsocket gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="4726e-130">Placing these fields in the state object allows their values to be preserved across multiple calls to read data from the client socket.</span></span>  
  
```vb  
Public Class StateObject  
    ' Client socket.  
    Public workSocket As Socket = Nothing
    ' Size of receive buffer.  
    Public BufferSize As Integer = 256  
    ' Receive buffer.  
    Public buffer(256) As Byte
    ' Received data string.  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject {  
    // Client socket.  
    public Socket workSocket = null;  
    // Size of receive buffer.  
    public const int BufferSize = 256;  
    // Receive buffer.  
    public byte[] buffer = new byte[BufferSize];  
    // Received data string.  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 <span data-ttu-id="4726e-131">Die Beispielmethode `Receive` richtet das Statusobjekt ein, und ruft dann die **BeginReceive**-Methode auf, um die Daten asynchron aus dem Clientsocket zu lesen.</span><span class="sxs-lookup"><span data-stu-id="4726e-131">The example `Receive` method sets up the state object and then calls the **BeginReceive** method to read the data from the client socket asynchronously.</span></span> <span data-ttu-id="4726e-132">Das folgende Beispiel implementiert die `Receive`-Methode.</span><span class="sxs-lookup"><span data-stu-id="4726e-132">The following example implements the `Receive` method.</span></span>  
  
```vb  
Private Shared Sub Receive(client As Socket)  
    Try  
        ' Create the state object.  
        Dim state As New StateObject()  
        state.workSocket = client  
  
        ' Begin receiving the data from the remote device.  
        client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf ReceiveCallback, state)  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'Receive  
```  
  
```csharp  
private static void Receive(Socket client) {  
    try {  
        // Create the state object.  
        StateObject state = new StateObject();  
        state.workSocket = client;  
  
        // Begin receiving the data from the remote device.  
        client.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
            new AsyncCallback(ReceiveCallback), state);  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="4726e-133">Die Rückruffunktion „Receive“ `ReceiveCallback` implementiert den **AsyncCallback**-Delegaten.</span><span class="sxs-lookup"><span data-stu-id="4726e-133">The receive callback method `ReceiveCallback` implements the **AsyncCallback** delegate.</span></span> <span data-ttu-id="4726e-134">Sie erhält die Daten aus dem Netzwerkgerät und erstellt eine Meldungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4726e-134">It receives the data from the network device and builds a message string.</span></span> <span data-ttu-id="4726e-135">Diese Methode liest ein oder mehrere Bytes vom Netzwerk in den Datenpuffer und ruft dann die **BeginReceive**-Methode erneut auf, sobald die vom Client gesendeten Daten vollständig sind.</span><span class="sxs-lookup"><span data-stu-id="4726e-135">It reads one or more bytes of data from the network into the data buffer and then calls the **BeginReceive** method again until the data sent by the client is complete.</span></span> <span data-ttu-id="4726e-136">Nachdem alle Daten vom Client gelesen wurden, signalisiert `ReceiveCallback` dem Thread der Anwendung, dass die Daten vollständig sind, indem **ManualResetEvent** auf `sendDone` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="4726e-136">Once all the data is read from the client, `ReceiveCallback` signals the application thread that the data is complete by setting the **ManualResetEvent** `sendDone`.</span></span>  
  
 <span data-ttu-id="4726e-137">Der folgende Beispielcode implementiert die `ReceiveCallback`-Methode.</span><span class="sxs-lookup"><span data-stu-id="4726e-137">The following example code implements the `ReceiveCallback` method.</span></span> <span data-ttu-id="4726e-138">Es wird eine globale Zeichenfolge mit dem Namen `response` vorausgesetzt, die die empfangene Zeichenfolge und ein globales **ManualResetEvent** mit dem Namen `receiveDone` enthält.</span><span class="sxs-lookup"><span data-stu-id="4726e-138">It assumes a global string named `response` that holds the received string and a global **ManualResetEvent** named `receiveDone`.</span></span> <span data-ttu-id="4726e-139">Der Server muss den Clientsocket ordnungsgemäß beenden, um die Netzwerksitzung herunterzufahren.</span><span class="sxs-lookup"><span data-stu-id="4726e-139">The server must shut down the client socket gracefully to end the network session.</span></span>  
  
```vb  
Private Shared Sub ReceiveCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the state object and the client socket
        ' from the asynchronous state object.  
        Dim state As StateObject = CType(ar.AsyncState, StateObject)  
        Dim client As Socket = state.workSocket  
  
        ' Read data from the remote device.  
        Dim bytesRead As Integer = client.EndReceive(ar)  
  
        If bytesRead > 0 Then  
            ' There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, _  
                bytesRead))  
  
            '  Get the rest of the data.  
            client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
                AddressOf ReceiveCallback, state)  
        Else  
            ' All the data has arrived; put it in response.  
            If state.sb.Length > 1 Then  
                response = state.sb.ToString()  
            End If  
            ' Signal that all bytes have been received.  
            receiveDone.Set()  
        End If  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ReceiveCallback  
```  
  
```csharp  
private static void ReceiveCallback( IAsyncResult ar ) {  
    try {  
        // Retrieve the state object and the client socket
        // from the asynchronous state object.  
        StateObject state = (StateObject) ar.AsyncState;  
        Socket client = state.workSocket;  
        // Read data from the remote device.  
        int bytesRead = client.EndReceive(ar);  
        if (bytesRead > 0) {  
            // There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,bytesRead));  
                //  Get the rest of the data.  
            client.BeginReceive(state.buffer,0,StateObject.BufferSize,0,  
                new AsyncCallback(ReceiveCallback), state);  
        } else {  
            // All the data has arrived; put it in response.  
            if (state.sb.Length > 1) {  
                response = state.sb.ToString();  
            }  
            // Signal that all bytes have been received.  
            receiveDone.Set();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4726e-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4726e-140">See also</span></span>

- [<span data-ttu-id="4726e-141">Verwenden eines synchronen Clientsockets</span><span class="sxs-lookup"><span data-stu-id="4726e-141">Using a Synchronous Client Socket</span></span>](using-a-synchronous-client-socket.md)
- [<span data-ttu-id="4726e-142">Überwachen mit Sockets</span><span class="sxs-lookup"><span data-stu-id="4726e-142">Listening with Sockets</span></span>](listening-with-sockets.md)
- [<span data-ttu-id="4726e-143">Asynchrone Clientsockets - Beispiel</span><span class="sxs-lookup"><span data-stu-id="4726e-143">Asynchronous Client Socket Example</span></span>](asynchronous-client-socket-example.md)
