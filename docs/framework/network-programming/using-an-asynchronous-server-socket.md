---
title: Verwenden eines asynchronen Serversockets
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
ms.openlocfilehash: 467804e685d800643c421ed1aad040a842b42886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180631"
---
# <a name="using-an-asynchronous-server-socket"></a>Verwenden eines asynchronen Serversockets
Asynchrone Serversockets verwenden das asynchrone Programmiermodell von .NET Framework, um Dienstanforderungen über das Netzwerk zu verarbeiten. Die <xref:System.Net.Sockets.Socket>-Klasse folgt dem asynchronen Standardbenennungsmuster von .NET Framework, z.B. entspricht die synchrone <xref:System.Net.Sockets.Socket.Accept%2A>-Methode den asynchronen <xref:System.Net.Sockets.Socket.BeginAccept%2A>- und <xref:System.Net.Sockets.Socket.EndAccept%2A>-Methoden.  
  
 Ein asynchroner Serversocket erfordert, dass eine Methode damit beginnt, Verbindungsanforderungen über das Netzwerk und eine Rückrufmethode anzunehmen, um die Verbindungsanforderungen zu verarbeiten und ebenfalls damit beginnt, Daten aus dem Netzwerk und eine Rückrufmethode zu empfangen, um den Datenempfang zu beenden. Alle diese Methoden werden in diesem Abschnitt weiter erläutert.  
  
 Im folgenden Beispiel initialisiert die `StartListening`-Methode den **Socket**, um mit der Annahme der Verbindungsanforderungen über das Netzwerk zu beginnen, und verwendet dann die **BeginAccept**-Methode, um neue Verbindungen anzunehmen. Die Accept-Rückrufmethode wird aufgerufen, wenn eine neue Verbindungsanforderung für den Socket empfangen wird. Dient zum Abrufen der **Socket**-Instanz, die die Verbindung verarbeitet, und den **Socket** an den Thread übergibt, der die Anforderung verarbeitet. Der Accept-Rückrufmethode implementiert den <xref:System.AsyncCallback>-Delegaten. Sie gibt „void“ zurück und nimmt einen einzelnen Parameter vom Typ <xref:System.IAsyncResult>. Das folgende Beispiel ist die Shell einer Accept-Rückrufmethode.  
  
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
  
 Die **BeginAccept**-Methode akzeptiert zwei Parameter: einen **AsyncCallback**-Delegaten, der auf die Accept-Rückrufmethode verweist, und ein Objekt, das verwendet wird, um Statusinformationen an die Rückrufmethode zu übergeben. Im folgenden Beispiel wird der überwachende **Socket** durch den *State*-Parameter an die Rückrufmethode übergeben. In diesem Beispiel wird ein **AsyncCallback**-Delegat erstellt und Verbindungen werden aus dem Netzwerk angenommen.  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.AcceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(new AsyncCallback(SocketListener.AcceptCallback), listener);  
```  
  
 Asynchrone Sockets können Threads aus dem Systemthreadpool verwenden, um eingehende Verbindungen zu bearbeiten. Ein Thread ist verantwortlich für das Akzeptieren von Verbindungen, ein anderer Thread wird verwendet, um alle eingehenden Verbindungen zu behandeln, und ein anderer Thread ist verantwortlich für den Empfang von Daten aus der Verbindung. Diese können im selben Thread vorhanden sein, je nachdem, welcher Thread vom Threadpool zugewiesen wird. Im folgenden Beispiel hält die <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse die Ausführung des Hauptthreads an und signalisiert, wann die Ausführung fortgesetzt werden kann.  
  
 Das folgende Beispiel zeigt eine asynchrone Methode, die einen asynchronen TCP/IP-Socket auf dem lokalen Computer erstellt und beginnt, Verbindungen zu akzeptieren. Es wird davon ausgegangen, dass ein globaler **ManualResetEvent** mit dem Namen `allDone` existiert, dass die Methode ein Member einer Klasse mit dem Namen `SocketListener` ist, und eine Rückrufmethode namens `AcceptCallback` definiert ist.  
  
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
  
 Die Accept-Rückrufmethode (`AcceptCallback` im vorherigen Beispiel) ist verantwortlich dafür, dass dem Thread der Hauptanwendung signalisiert wird, den Vorgang fortzusetzen, die Verbindung mit dem Client herzustellen, und das asynchrone Lesen der Datenmengen vom Client zu beginnen. Das folgende Beispiel ist der erste Teil einer Implementierung der `AcceptCallback`-Methode. Dieser Abschnitt der Methode signalisiert dem Hauptanwendungsthread, dass die Verarbeitung fortgesetzt wird, und stellt die Verbindung mit dem Client her. Ein globales **ManualResetEvent** mit dem Namen `allDone` wird vorausgesetzt.  
  
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
  
 Das Lesen von Daten aus einem Clientsocket erfordert ein Zustandsobjekt, das Werte zwischen asynchronen Aufrufen übergibt. Das folgende Beispiel implementiert ein Zustandsobjekt für den Empfang einer Zeichenfolge vom Remoteclient. Es enthält Felder für den Clientsocket, einen Datenpuffer zum Empfangen von Daten, und ein <xref:System.Text.StringBuilder> für die Erstellung einer Datenzeichenfolge, die vom Client gesendet wurde. Wenn Sie diese Felder in das Statusobjekt platzieren, können ihre Werte über mehrere Aufrufe gespeichert werden, damit Daten aus dem Clientsocket gelesen werden können.  
  
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
  
 Der Abschnitt der `AcceptCallback`-Methode, der den Datenempfang aus dem Clientsocket beginnt, initialisiert zunächst eine Instanz der `StateObject`-Klasse und ruft dann die <xref:System.Net.Sockets.Socket.BeginReceive%2A>-Methode zum asynchronen Lesen von Daten aus dem Clientsocket auf.  
  
 Das folgende Beispiel zeigt die vollständige `AcceptCallback`-Methode. Es wird davon ausgegangen, dass ein globales **ManualResetEvent** mit dem Namen `allDone,` existiert, dass die `StateObject`-Klasse definiert und die `ReadCallback`-Methode in einer Klasse mit dem Namen `SocketListener` definiert ist.  
  
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
  
 Die letzte Methode, die für den asynchronen Socketserver implementiert werden muss, ist die Read-Rückrufmethode, die vom Client gesendete Daten zurückgibt. Wie die Accept-Rückrufmethode, ist die Read-Rückrufmethode ein **AsyncCallback**-Delegat. Diese Methode liest ein oder mehrere Bytes vom Clientsocket in den Datenpuffer und ruft dann die **BeginReceive**-Methode erneut auf, sobald die vom Client gesendeten Daten vollständig sind. Nachdem die gesamte Nachricht vom Client gelesen wurde, wird die Zeichenfolge in der Konsole angezeigt und der Serversocket, der die Verbindung mit dem Client verarbeitet, wird geschlossen.  
  
 Das folgende Beispiel implementiert die `ReadCallback`-Methode. Es wird vorausgesetzt, dass die `StateObject`-Klasse definiert ist.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden eines synchronen Serversockets](using-a-synchronous-server-socket.md)
- [Asynchroner Serversocket, Beispiel](asynchronous-server-socket-example.md)
- [Threading](../../standard/threading/index.md)
- [Listening with Sockets (Überwachen mit Sockets)](listening-with-sockets.md)
