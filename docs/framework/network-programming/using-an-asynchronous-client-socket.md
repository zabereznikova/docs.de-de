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
ms.openlocfilehash: 9cf46e9519bcecf4d7a20ff99b86fa5f66af2087
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502040"
---
# <a name="using-an-asynchronous-client-socket"></a>Verwenden von asynchronen Clientsockets
Ein asynchroner Clientsocket hält die Anwendung nicht an, während darauf gewartet wird, dass Netzwerkvorgänge abgeschlossen werden. Stattdessen wird das standardmäßige asynchrone Programmiermodell von .NET Framework verwendet, um die Netzwerkverbindung in einem Thread zu verarbeiten, während die Anwendung weiterhin auf dem ursprünglichen Thread ausgeführt wird. Asynchrone Sockets eignen sich für Anwendungen, die das Netzwerk stark nutzen, oder die nicht warten können, bis Netzwerkvorgänge vor dem Fortsetzen abgeschlossen werden.  
  
 Die <xref:System.Net.Sockets.Socket>-Klasse folgt dem Benennungsmuster von .NET Framework für asynchrone Methoden, z.B. entspricht die synchrone <xref:System.Net.Sockets.Socket.Receive%2A>-Methode den asynchronen <xref:System.Net.Sockets.Socket.BeginReceive%2A>- und <xref:System.Net.Sockets.Socket.EndReceive%2A>-Methoden.  
  
 Asynchrone Vorgänge erfordern eine Rückrufmethode, die das Ergebnis des Vorgangs zurückgibt. Wenn Ihre Anwendung das Ergebnis nicht wissen muss, ist keine Rückrufmethode erforderlich. Der Beispielcode in diesem Abschnitt veranschaulicht die Verwendung einer Methode zum Start einer Verbindung mit einem Netzwerkgerät und einer Rückrufmethode zum Abschließen der Verbindung, einer Methode zum Start des Datenversands und einer Rückrufmethode zum Abschließen des Versands, einer Methode zum Start des Datenempfangs und einer Rückrufmethode zum Abschließen des Datenempfangs.  
  
 Asynchrone Sockets verwenden mehrere Threads aus dem Systemthreadpool, um Netzwerkverbindungen zu bearbeiten. Ein Thread ist verantwortlich für das Initiieren des Datenversands oder Datenempfangs. Andere Threads schließen die Verbindung zum Netzwerkgerät ab und senden oder empfangen Daten. In den folgenden Beispielen werden Instanzen der <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>-Klasse verwendet, um die Ausführung des Hauptthreads anzuhalten und zu signalisieren, wann die Ausführung fortgesetzt werden kann.  
  
 Zur Verbindung eines asynchronen Sockets mit einem Netzwerkgerät initialisiert die `Connect`-Methode im folgenden Beispiel ein **Socket**, ruft dann die <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType>-Methode auf und übergibt einen Remoteendpunkt, der das Netzwerkgerät, die Rückrufmethode „Connect“ und ein Zustandsobjekt (der Client-**Socket**), darstellt. Dieses wird verwendet, um Zustandsinformationen zwischen asynchronen Aufrufen zu übergeben. Das Beispiel implementiert die `Connect`-Methode zur Verbindung des angegebenen **Socket** mit dem angegebenen Endpunkt. Es wird ein globales **ManualResetEvent** mit dem Namen `connectDone` vorausgesetzt.  
  
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
  
 Die Rückrufmethode „Connect“ `ConnectCallback` implementiert den <xref:System.AsyncCallback>-Delegaten. Sie stellt eine Verbindung mit dem Remotegerät her, wenn das Remotegerät verfügbar ist, und signalisiert dem Thread der Anwendung, dass die Verbindung abgeschlossen ist, indem **ManualResetEvent** auf `connectDone` festgelegt wird. Im folgenden Code wird die `ConnectCallback`-Methode implementiert.  
  
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
  
 Die Beispielmethode `Send` codiert die angegebenen Zeichenfolgendaten im ASCII-Format und sendet sie asynchron an das Netzwerkgerät, dargestellt durch den angegebenen Socket. Das folgende Beispiel implementiert die `Send`-Methode.  
  
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
  
 Die Rückrufmethode „Send“ `SendCallback` implementiert den <xref:System.AsyncCallback>-Delegaten. Die Daten werden gesendet, wenn das Netzwerkgerät für den Empfang bereit ist. Im folgenden Beispiel wird eine Implementierung der `SendCallback`-Methode veranschaulicht. Ein globales **ManualResetEvent** mit dem Namen `sendDone` wird vorausgesetzt.  
  
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
  
 Das Lesen von Daten aus einem Clientsocket erfordert ein Zustandsobjekt, das Werte zwischen asynchronen Aufrufen übergibt. Die folgende Klasse ist ein Beispielstatusobjekt zum Empfangen von Daten von einem Clientsocket. Sie enthält ein Feld für den Clientsocket, einen Puffer für die empfangenen Daten und eine <xref:System.Text.StringBuilder>, die die eingehende Datenzeichenfolge enthält. Wenn Sie diese Felder in das Statusobjekt platzieren, können ihre Werte über mehrere Aufrufe gespeichert werden, damit Daten aus dem Clientsocket gelesen werden können.  
  
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
  
 Die Beispielmethode `Receive` richtet das Statusobjekt ein, und ruft dann die **BeginReceive**-Methode auf, um die Daten asynchron aus dem Clientsocket zu lesen. Das folgende Beispiel implementiert die `Receive`-Methode.  
  
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
  
 Die Rückruffunktion „Receive“ `ReceiveCallback` implementiert den **AsyncCallback**-Delegaten. Sie erhält die Daten aus dem Netzwerkgerät und erstellt eine Meldungszeichenfolge. Diese Methode liest ein oder mehrere Bytes vom Netzwerk in den Datenpuffer und ruft dann die **BeginReceive**-Methode erneut auf, sobald die vom Client gesendeten Daten vollständig sind. Nachdem alle Daten vom Client gelesen wurden, signalisiert `ReceiveCallback` dem Thread der Anwendung, dass die Daten vollständig sind, indem **ManualResetEvent** auf `sendDone` festgelegt wurde.  
  
 Der folgende Beispielcode implementiert die `ReceiveCallback`-Methode. Es wird eine globale Zeichenfolge mit dem Namen `response` vorausgesetzt, die die empfangene Zeichenfolge und ein globales **ManualResetEvent** mit dem Namen `receiveDone` enthält. Der Server muss den Clientsocket ordnungsgemäß beenden, um die Netzwerksitzung herunterzufahren.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines synchronen Clientsockets](using-a-synchronous-client-socket.md)
- [Überwachen mit Sockets](listening-with-sockets.md)
- [Asynchrone Clientsockets - Beispiel](asynchronous-client-socket-example.md)
