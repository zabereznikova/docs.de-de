---
title: Verwenden eines synchronen Clientsockets
description: Dieses Beispiel zeigt einen synchronen Clientsocket im .NET Framework, der das Anwendungsprogramm anhält, während der Netzwerkvorgang abgeschlossen wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- synchronous client sockets
- Socket class, synchronous client sockets
- receiving data, sockets
- sockets, synchronous client sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
ms.openlocfilehash: ef682af33c10cf06ffc398c22e4a7dc1adf8290e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502066"
---
# <a name="using-a-synchronous-client-socket"></a>Verwenden eines synchronen Clientsockets
Ein synchroner Clientsocket hält das Anwendungsprogramm an, während der Netzwerkvorgang abgeschlossen wird. Synchrone Serversockets eignen sich nicht für Anwendungen, die das Netzwerk in ihrem Betrieb stark nutzen, aber sie können einfachen Zugang zu Netzwerkdiensten für andere Anwendungen ermöglichen.  
  
 Übergeben Sie zum Senden von Daten ein Byte-Array an eine der Methoden zur Datenversendung (<xref:System.Net.Sockets.Socket.Send%2A> und <xref:System.Net.Sockets.Socket.SendTo%2A>) der <xref:System.Net.Sockets.Socket>-Klasse. Im folgenden Beispiel wird eine Zeichenfolge in einen Puffer mit Byte-Array mit der <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>-Eigenschaft codiert, und anschließend wird der Puffer mit der **Senden**-Methode an das Netzwerkgerät übertragen. Die **Senden**-Methode gibt die Anzahl der Bytes zurück, die an das Netzwerkgerät gesendet werden.  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 Die **Senden**-Methode entfernt die Bytes aus dem Puffer und platziert sie mit der Netzwerkschnittstelle in die Warteschlange, um an das Netzwerkgerät gesendet zu werden. Die Netzwerkschnittstelle kann die Daten möglicherweise nicht sofort, aber letztendlich doch senden, solange die Verbindung mit der <xref:System.Net.Sockets.Socket.Shutdown%2A>-Methode normal geschlossen wird.  
  
 Um Daten von einem Netzwerkgerät zu empfangen, übergeben Sie einen Puffer an eine der Methoden zum Datenempfang (<xref:System.Net.Sockets.Socket.Receive%2A> und <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>) der **Socket**-Klasse. Synchrone Sockets werden die Anwendung anhalten, bis Bytes aus dem Netzwerk empfangen werden oder bis der Socket geschlossen wird. Im folgenden Beispiel werden Daten aus dem Netzwerk empfangen, und dann auf der Konsole angezeigt. Im Beispiel wird davon ausgegangen, dass die Daten, die aus dem Netzwerk stammen, aus ASCII-codiertem Text bestehen. Die **Empfangen**-Methode gibt die Anzahl der Bytes zurück, die vom Netzwerk empfangen werden.  
  
```vb  
Dim bytes(1024) As Byte  
Dim bytesRec = s.Receive(bytes)  
Console.WriteLine("Echoed text = {0}", _  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec))  
```  
  
```csharp  
byte[] bytes = new byte[1024];  
int bytesRec = s.Receive(bytes);  
Console.WriteLine("Echoed text = {0}",  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec));  
```  
  
 Wenn der Socket nicht mehr benötigt wird, müssen Sie ihn freigeben, indem Sie die <xref:System.Net.Sockets.Socket.Shutdown%2A>-Methode und anschließend die **Schließen**-Methode aufrufen. Das folgende Beispiel gibt ein **Socket** frei. Die <xref:System.Net.Sockets.SocketShutdown>-Enumeration definiert Konstanten, die angeben, ob der Socket zum Senden, Empfangen oder für beides geschlossen werden sollte.  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von asynchronen Clientsockets](using-an-asynchronous-client-socket.md)
- [Überwachen mit Sockets](listening-with-sockets.md)
- [Synchrone Clientsockets - Beispiel](synchronous-client-socket-example.md)
