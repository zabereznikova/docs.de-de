---
title: Verwenden eines synchronen Serversockets
description: Dieses Beispiel zeigt einen synchronen Serversocket im .NET Framework, der eine Anwendung anhält, bis eine Verbindungsanforderung für den Socket eingeht.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
ms.openlocfilehash: 305feaa71304bef749f999a078b0b5f4fa7be3cc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278153"
---
# <a name="using-a-synchronous-server-socket"></a>Verwenden eines synchronen Serversockets

Synchrone Serversockets halten die Ausführung der Anwendung an, bis eine Verbindungsanforderung für den Socket empfangen wird. Synchrone Serversockets eignen sich nicht für Anwendungen, die das Netzwerk in ihrem Betrieb stark nutzen, aber sie können für einfache Netzwerkanwendungen geeignet sein.  
  
 Nachdem <xref:System.Net.Sockets.Socket> zum Lauschen an einem Endpunkt mithilfe der <xref:System.Net.Sockets.Socket.Bind%2A>- und <xref:System.Net.Sockets.Socket.Listen%2A>-Methoden festgelegt wurde, sind sie bereit zur Annahme von eingehenden Verbindungsanforderungen, die die <xref:System.Net.Sockets.Socket.Accept%2A>-Methode verwenden. Die Anwendung wird angehalten, bis eine Verbindungsanforderung beim Aufruf der **Accept**-Methode empfangen wird.  
  
 Wenn eine Verbindungsanforderung eingeht, gibt **Accept** eine neue **Socket**-Instanz zurück, die dem verbundenen Client zugeordnet ist. Das folgende Beispiel liest Daten aus dem Client, zeigt sie auf der Konsole an und gibt sie an den Client zurück. Der **Socket** gibt kein Messagingprotokoll an, sodass die Zeichenfolge \<EOF> das Ende der Nachrichtendaten signalisiert. Es wird vorausgesetzt, dass ein **Socket** mit dem Namen `listener` initialisiert und an einen Endpunkt gebunden wurde.  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines asynchronen Serversockets](using-an-asynchronous-server-socket.md)
- [Synchroner Serversocket, Beispiel](synchronous-server-socket-example.md)
- [Überwachen mit Sockets](listening-with-sockets.md)
