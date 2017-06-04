---
title: "Verwenden eines asynchronen Serversockets | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Anwendungsprotokolle, Sockets"
  - "Senden von Daten, Sockets"
  - "Socketklasse, asynchrone Serversockets"
  - "Datenanforderungen, Sockets"
  - "Sockets, asynchrone Serversockets"
  - "Anfordern von Daten aus dem Internet, Sockets"
  - "Serversockets"
  - "Empfangen von Daten, Sockets"
  - "asynchrone Serversockets"
  - "Protokolle, Sockets"
  - "Internet, Sockets"
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Verwenden eines asynchronen Serversockets
Asynchrone Serversockets verwenden das asynchrone Programmiermodell .NET Framework, um Netzwerkdienstanforderungen zu verarbeiten.  Die <xref:System.Net.Sockets.Socket>\-Klasse folgt nach dem Standard\-asynchronen Benennungsmuster .NET Framework; entspricht beispielsweise die synchrone <xref:System.Net.Sockets.Socket.Accept%2A>\-Methode zu asynchronen <xref:System.Net.Sockets.Socket.BeginAccept%2A> und zu den <xref:System.Net.Sockets.Socket.EndAccept%2A>\-Methoden.  
  
 Ein asynchroner Serversocket erfordert eine Methode zu starten, Aufforderungen zum Aufbau einer Verbindung mit dem Netzwerk, von einer Rückrufmethode, die Aufforderungen zum Aufbau einer Verbindung zu behandeln und starten, Daten aus dem Netzwerk Empfangen von und von einer Rückrufmethode akzeptiert, um das empfangen der Daten zu beenden.  Alle diese Methoden werden weiter in diesem Abschnitt erläutert.  
  
 Im folgenden Beispiel zu starten, Aufforderungen zum Aufbau einer Verbindung vom Netzwerk akzeptiert, initialisiert die `StartListening`\-Methode den **Socket** und verwendet dann die **BeginAccept**\-Methode, um das Übernehmen von neuen Verbindungen zu starten.  Die akzeptierensrückrufmethode wird aufgerufen, wenn eine neue Aufforderung zum Aufbau einer Verbindung auf dem Socket empfangen wird.  Es ist für das Abrufen der **Socket**\-Instanz zuständig, die die Verbindung und dieses **Socket** an den Thread zu übergeben behandelt, der die Anforderung verarbeitet.  Die akzeptierensrückrufmethode implementiert den <xref:System.AsyncCallback> Delegaten; sie gibt void zurück und nimmt einen einzelnen Parameter vom Typ <xref:System.IAsyncResult>.  Im folgenden Beispiel ist die Shell einer akzeptierensrückrufmethode.  
  
```vb  
Sub acceptCallback(ar As IAsyncResult)  
    ' Add the callback code here.  
End Sub 'acceptCallback  
```  
  
```csharp  
void acceptCallback( IAsyncResult ar) {  
    // Add the callback code here.  
}  
```  
  
 Die **BeginAccept**\-Methode verwendet zwei Parameter, **AsyncCallback** einen Delegaten, der der akzeptierensrückrufmethode und auf ein Objekt verweist, das verwendet wird, um Zustandsinformationen an die Rückrufmethode zu übergeben.  Im folgenden Beispiel wird lauschende **Socket** an die Rückrufmethode durch den *Zustandsparameter* übergeben.  In diesem Beispiel wird ein **AsyncCallback** Delegaten und startet das Akzeptieren von Verbindungen vom Netzwerk.  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.acceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(  
    new AsyncCallback(SocketListener.acceptCallback),   
    listener);  
```  
  
 Asynchrone Sockets verwenden Threads vom Systemthreadpool, um eingehende Verbindungen zu verarbeiten.  Ein Thread ist zum Akzeptieren von Verbindungen verantwortlich, wird ein anderer Thread verwendet, um jede eingehende Verbindung zu behandeln, und ein anderer Thread ist zum Empfangen von Daten von der Verbindung zuständig.  Diese können vom selben Thread sein, abhängig von dem Thread aus dem Threadpool zugewiesen wird.  Im folgenden Beispiel enthält die <xref:System.Threading.ManualResetEvent?displayProperty=fullName>\-Klasse Ausführung des Hauptthreads und der Signale an, wenn die Ausführung fortgesetzt werden kann.  
  
 Im folgenden Beispiel wird eine asynchrone Methode, die einen asynchronen TCP\/IP\-Socket auf dem lokalen Computer erstellt und gestartet wird, Verbindungen akzeptiert.  Es wird davon ausgegangen, dass es globales **ManualResetEvent** gibt, das `allDone` genannt wird, dass die Methode ein Member einer Klasse ist, die `SocketListener` namens und dass eine Rückrufmethode, die `acceptCallback` genannt wird, definiert ist.  
  
```vb  
Public Sub StartListening()  
    Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
    Dim localEP = New IPEndPoint(ipHostInfo.AddressList(0), 11000)  
  
    Console.WriteLine("Local address and port : {0}", localEP.ToString())  
  
    Dim listener As New Socket(localEP.Address.AddressFamily, _  
       SocketType.Stream, ProtocolType.Tcp)  
  
    Try  
        listener.Bind(localEP)  
        listener.Listen(10)  
  
        While True  
            allDone.Reset()  
  
            Console.WriteLine("Waiting for a connection...")  
            listener.BeginAccept(New _  
                AsyncCallback(SocketListener.acceptCallback), _  
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
public void StartListening() {  
    IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
    IPEndPoint localEP = new IPEndPoint(ipHostInfo.AddressList[0],11000);  
  
    Console.WriteLine("Local address and port : {0}",localEP.ToString());  
  
    Socket listener = new Socket( localEP.Address.AddressFamily,  
        SocketType.Stream, ProtocolType.Tcp );  
  
    try {  
        listener.Bind(localEP);  
        listener.Listen(10);  
  
        while (true) {  
            allDone.Reset();  
  
            Console.WriteLine("Waiting for a connection...");  
            listener.BeginAccept(  
                new AsyncCallback(SocketListener.acceptCallback),   
                listener );  
  
            allDone.WaitOne();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
  
    Console.WriteLine( "Closing the listener...");  
}  
```  
  
 Die akzeptierensrückrufmethode \(`acceptCallback` im vorherigen Beispiel\) ist für das Auslösen des Hauptanwendungsthreads gestartet, um die Verarbeitung, das Einrichten der Verbindung mit dem Client und Starten der asynchronen Lesen von Daten vom Client fortzusetzen zuständig.  Im folgenden Beispiel ist der erste Teil einer Implementierung der `acceptCallback`\-Methode.  Dieser Abschnitt der Methode signalisiert den Hauptanwendungsthread, um die Verarbeitung fortgesetzt und legt die Verbindung an den Client fest.  Sie akzeptiert globales **ManualResetEvent** an, das `allDone` genannt wird.  
  
```vb  
Public Sub acceptCallback(ar As IAsyncResult)  
    allDone.Set()  
  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Additional code to read data goes here.  
End Sub 'acceptCallback  
```  
  
```csharp  
public void acceptCallback(IAsyncResult ar) {  
    allDone.Set();  
  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Additional code to read data goes here.    
}  
```  
  
 Das Lesen von Daten von einem Clientsocket erfordert ein Zustandsobjekt, das Werte zwischen asynchrone Aufrufe übergibt.  Im folgenden Beispiel implementiert ein Zustandsobjekt für den Empfang einer Zeichenfolge im Remoteclients.  Es enthält Felder für den Clientsocket, einen Datenpuffer für das Empfangen von Daten und <xref:System.Text.StringBuilder> zum Erstellen der Datenzeichenfolge, die vom Client gesendet wird.  Das Einfügen dieser Felder im Zustandsobjekt können ihre, um Daten über mehrere beibehalten werden Werte, im Clientsocket zu lesen.  
  
```vb  
Public Class StateObject  
    Public workSocket As Socket = Nothing  
    Public BufferSize As Integer = 1024  
    Public buffer(BufferSize) As Byte  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject {  
    public Socket workSocket = null;  
    public const int BufferSize = 1024;  
    public byte[] buffer = new byte[BufferSize];  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 Der Abschnitt der `acceptCallback`\-Methode, die die Daten vom Clientsocket zuerst empfangen beginnt, initialisiert eine Instanz der `StateObject`\-Klasse und ruft dann die <xref:System.Net.Sockets.Socket.BeginReceive%2A>\-Methode auf, um die Daten vom Clientsocket asynchron lesen zu starten.  
  
 Im folgenden Beispiel wird die vollständige Methode `acceptCallback` an.  Es wird davon ausgegangen, dass es globales **ManualResetEvent** gibt, das `allDone,` ", die die `StateObject`\-Klasse definiert ist, und dass die `readCallback`\-Methode in einer Klasse definiert wird, benannte `SocketListener`.  
  
```vb  
Public Shared Sub acceptCallback(ar As IAsyncResult)  
    ' Get the socket that handles the client request.  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Signal the main thread to continue.  
    allDone.Set()  
  
    ' Create the state object.  
    Dim state As New StateObject()  
    state.workSocket = handler  
    handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
        AddressOf AsynchronousSocketListener.readCallback, state)  
End Sub 'acceptCallback  
  
```  
  
```csharp  
public static void acceptCallback(IAsyncResult ar) {  
    // Get the socket that handles the client request.  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Signal the main thread to continue.  
    allDone.Set();  
  
    // Create the state object.  
    StateObject state = new StateObject();  
    state.workSocket = handler;  
    handler.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
        new AsyncCallback(AsynchronousSocketListener.readCallback), state);  
}  
```  
  
 Die fertige Methode, die für den asynchronen Socketserver implementiert werden muss, ist die Leserückrufmethode, die die Daten zurückgibt, die vom Client gesendet werden.  Wie die akzeptierensrückrufmethode ist die Leserückrufmethode ein **AsyncCallback** Delegat.  Diese Methode liest eine oder mehrere Bytes vom Clientsocket in den Datenpuffer und ruft dann die **BeginReceive**\-Methode erneut auf, bis die Daten, die vom Client gesendet werden, abgeschlossen sind.  Sobald die gesamte Meldung vom Client gelesen wurde, wird die Zeichenfolge in der Konsole angezeigt und der Serversocket, der die Verbindung an den Client behandelt, wird geschlossen.  
  
 Im folgenden Beispiel wird die `readCallback`\-Methode implementiert.  Es wird davon ausgegangen, dass die `StateObject`\-Klasse definiert ist.  
  
```vb  
Public Shared Sub readCallback(ar As IAsyncResult)  
    Dim state As StateObject = CType(ar.AsyncState, StateObject)  
    Dim handler As Socket = state.workSocket  
  
    ' Read data from the client socket.   
    Dim read As Integer = handler.EndReceive(ar)  
  
    ' Data was read from the client socket.  
    If read > 0 Then  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, read))  
        handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf readCallback, state)  
    Else  
        If state.sb.Length > 1 Then  
            ' All the data has been read from the client;  
            ' display it on the console.  
            Dim content As String = state.sb.ToString()  
            Console.WriteLine("Read {0} bytes from socket." + _  
                ControlChars.Cr + " Data : {1}", content.Length, content)  
        End If  
    End If  
End Sub 'readCallback  
  
```  
  
```csharp  
public static void readCallback(IAsyncResult ar) {  
    StateObject state = (StateObject) ar.AsyncState;  
    Socket handler = state.WorkSocket;  
  
    // Read data from the client socket.  
    int read = handler.EndReceive(ar);  
  
    // Data was read from the client socket.  
    if (read > 0) {  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,read));  
        handler.BeginReceive(state.buffer,0,StateObject.BufferSize, 0,  
            new AsyncCallback(readCallback), state);  
    } else {  
        if (state.sb.Length > 1) {  
            // All the data has been read from the client;  
            // display it on the console.  
            string content = state.sb.ToString();  
            Console.WriteLine("Read {0} bytes from socket.\n Data : {1}",  
               content.Length, content);  
        }  
        handler.Close();  
    }  
}  
```  
  
## Siehe auch  
 [Verwenden eines synchronen Serversockets](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [Asynchroner Serversocket, Beispiel](../../../docs/framework/network-programming/asynchronous-server-socket-example.md)   
 [Threading](../../../docs/standard/threading/index.md)   
 [Überwachen mit Sockets](../../../docs/framework/network-programming/listening-with-sockets.md)