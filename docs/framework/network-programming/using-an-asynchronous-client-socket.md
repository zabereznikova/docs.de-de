---
title: "Verwenden von asynchronen Clientsockets | Microsoft Docs"
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
  - "Datenanforderungen, Sockets"
  - "Asynchrone Clientsockets"
  - "Socket-Klasse, Asynchrone Clientsockets"
  - "Anfordern von Daten aus dem Internet, Sockets"
  - "Sockets, Asynchrone Clientsockets"
  - "Empfangen von Daten, Sockets"
  - "Protokolle, Sockets"
  - "Internet, Sockets"
  - "Clientsockets"
ms.assetid: fd85bc88-e06c-467d-a30d-9fd7cffcfca1
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Verwenden von asynchronen Clientsockets
Ein asynchroner Clientsocket enthält nicht die Anwendung während des Wartens auf Netzwerkoperationen an abzuschließen.  Stattdessen wird das Standard\-asynchrone Programmiermodell .NET Framework, um die Netzwerkverbindung auf einem Thread zu verarbeiten, während die Anwendung wird, sie auf den ursprünglichen Thread ausgeführt werden.  Asynchrone Sockets sind für Anwendungen geeignet, die umfangreichen Gebrauch von Netzwerk ausführen, oder die nicht auf Netzwerkoperationen warten können, um abzuschließen, bevor sie weiterhin.  
  
 Die <xref:System.Net.Sockets.Socket>\-Klasse folgt dem .NET Framework\-Benennungsmuster für asynchrone Methoden; entspricht beispielsweise die synchrone <xref:System.Net.Sockets.Socket.Receive%2A>\-Methode zu asynchronen <xref:System.Net.Sockets.Socket.BeginReceive%2A> und zu den <xref:System.Net.Sockets.Socket.EndReceive%2A>\-Methoden.  
  
 Asynchrone Vorgänge erfordern eine Rückrufmethode, das Ergebnis des Vorgangs zurückzugeben.  Wenn die Anwendung ist nicht erforderlich, um das Ergebnis zu kennen, ist keine Rückrufmethode erforderlich.  Der Beispielcode in diesem Abschnitt werden mit einer Methode, um die Verbindung zu beginnen, an ein Netzwerkgerät und eine Rückrufmethode, um die Verbindung, die Methode, um das Senden von Daten und der Rückrufmethode zu starten, um das übertragene abzuschließen und der Methode zu vervollständigen, um das Empfangen von Daten und der Rückrufmethode zu starten, um das Empfangen von Daten zu beenden.  
  
 Asynchrone Sockets verwenden mehrere Threads vom Systemthreadpool, um Netzwerkverbindungen zu verarbeiten.  Ein Thread ist zum Initiieren des Senden oder Empfangen von Daten verantwortlich; andere Threads schließen die Verbindung zum Netzwerkgerät ab und senden oder empfangen die Daten.  In den folgenden Beispielen werden Instanzen der <xref:System.Threading.ManualResetEvent?displayProperty=fullName>\-Klasse verwendet, um die Ausführung des Hauptthreads angehalten und an, wenn die Ausführung fortgesetzt werden kann.  
  
 Im folgenden Beispiel einen asynchronen Socket an ein Netzwerkgerät herzustellen, initialisiert die `Connect`\-Methode **Socket** und ruft dann die [BeginConnect](frlrfsystemnetsocketssocketclassconnecttopic)\-Methode auf und übergibt einen Remoteendpunkt, der das Netzwerkgerät, die Verbindungsrückrufmethode und ein Zustandsobjekt \(Clients **Socket**\) darstellt, die verwendet wird, um Zustandsinformationen zwischen asynchrone Aufrufe zu übergeben.  Das Beispiel implementiert die `Connect`\-Methode, um angegebene **Socket** an angegebenen Endpunkt herzustellen.  Sie akzeptiert globales **ManualResetEvent** an, das `connectDone` genannt wird.  
  
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
  
 Die Verbindungsrückrufmethode `ConnectCallback` implementiert den <xref:System.AsyncCallback> Delegaten.  Es wird an das Remotegerät, wenn das Remotegerät verfügbar ist an und signalisieren das Anwendungsthread, dass die Verbindung abgeschlossen ist, indem **ManualResetEvent**`connectDone` festgelegt wird.  Der folgende Code implementiert die `ConnectCallback`\-Methode.  
  
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
  
 Die Beispielmethode zeigt `Send` codiert die angegebenen Zeichenfolgendaten in ASCII\-Format und sendet es asynchron zum Netzwerkgerät, das durch den angegebenen Socket dargestellt wird.  Im folgenden Beispiel wird die `Send`\-Methode implementiert.  
  
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
  
 Die sendensrückrufmethode `SendCallback` implementiert den <xref:System.AsyncCallback> Delegaten.  Sie sendet die Daten, wenn das Netzwerkgerät bereit ist zu empfangen.  Im folgenden Beispiel wird die Implementierung der `SendCallback`\-Methode veranschaulicht.  Sie akzeptiert globales **ManualResetEvent** an, das `sendDone` genannt wird.  
  
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
  
 Das Lesen von Daten von einem Clientsocket erfordert ein Zustandsobjekt, das Werte zwischen asynchrone Aufrufe übergibt.  Die folgende Klasse ist ein Beispielszustandsobjekt zum Empfangen von Daten von einem Clientsocket.  Sie enthält ein Feld, um den Clientsocket, einen Puffer für die empfangenen Daten und <xref:System.Text.StringBuilder> die Zeichenfolge der eingehenden Daten enthält.  Das Einfügen dieser Felder im Zustandsobjekt können ihre, um Daten über mehrere beibehalten werden Werte, im Clientsocket zu lesen.  
  
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
  
 Die `Receive`\-Beispielmethode richtet das Zustandsobjekt ein und ruft dann die **BeginReceive**\-Methode auf, um die Daten vom Clientsocket asynchron zu lesen.  Im folgenden Beispiel wird die `Receive`\-Methode implementiert.  
  
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
  
 Die empfangensrückrufmethode `ReceiveCallback` implementiert den **AsyncCallback** Delegaten.  Sie werden die Daten vom Netzwerkgerät und erstellt eine Meldungszeichenfolge.  Es wird eine oder mehrere Bytes Daten vom Netzwerk in den Datenpuffer und ruft dann die **BeginReceive**\-Methode erneut auf, bis die Daten, die vom Client gesendet werden, abgeschlossen sind.  Sobald alle Daten vom Client gelesen werden, signalisiert `ReceiveCallback` Anwendungsthread, dass die Daten vollständig sind, indem **ManualResetEvent** `sendDone` festlegen.  
  
 Im folgenden Beispielcode wird `ReceiveCallback`\-Methode implementiert.  Es wird eine globale Zeichenfolge an, die `response` genannt wird, die die empfangene Zeichenfolge und globales **ManualResetEvent** mit `receiveDone` enthält.  Der Server muss den Clientsocket ordnungsgemäß beenden, um die Netzwerksitzung zu beenden.  
  
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
  
## Siehe auch  
 [Verwenden eines synchronen Clientsockets](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)   
 [Überwachen mit Sockets](../../../docs/framework/network-programming/listening-with-sockets.md)   
 [Asynchrone Clientsockets \- Beispiel](../../../docs/framework/network-programming/asynchronous-client-socket-example.md)