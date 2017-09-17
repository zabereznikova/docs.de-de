---
title: Verwenden eines synchronen Serversockets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
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
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c4ecba2d6c5026a3b2f7d65540fcf40dd71ba3d7
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="using-a-synchronous-server-socket"></a>Verwenden eines synchronen Serversockets
Synchrone Serversockets halten die Ausführung der Anwendung an, bis eine Verbindungsanforderung für den Socket empfangen wird. Synchrone Serversockets eignen sich nicht für Anwendungen, die das Netzwerk in ihrem Betrieb stark nutzen, aber sie können für einfache Netzwerkanwendungen geeignet sein.  
  
 Nachdem <xref:System.Net.Sockets.Socket> zum Lauschen an einem Endpunkt mithilfe der <xref:System.Net.Sockets.Socket.Bind%2A>- und <xref:System.Net.Sockets.Socket.Listen%2A>-Methoden festgelegt wurde, sind sie bereit zur Annahme von eingehenden Verbindungsanforderungen, die die <xref:System.Net.Sockets.Socket.Accept%2A>-Methode verwenden. Die Anwendung wird angehalten, bis eine Verbindungsanforderung beim Aufruf der **Accept**-Methode empfangen wird.  
  
 Wenn eine Verbindungsanforderung eingeht, gibt **Accept** eine neue **Socket**-Instanz zurück, die dem verbundenen Client zugeordnet ist. Das folgende Beispiel liest Daten aus dem Client, zeigt sie auf der Konsole an und gibt sie an den Client zurück. Der **Socket** gibt kein Messaging-Protokoll an, sodass die Zeichenfolge "\<EOF>" das Ende der Nachrichtendaten signalisiert. Es wird vorausgesetzt, dass ein **Socket** mit dem Namen `listener` initialisiert und an einen Endpunkt gebunden wurde.  
  
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
 [Using an Asynchronous Server Socket (Verwenden eines asynchronen Serversockets)](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Synchroner Serversocket, Beispiel](../../../docs/framework/network-programming/synchronous-server-socket-example.md)   
 [Überwachen mit Sockets](../../../docs/framework/network-programming/listening-with-sockets.md)

