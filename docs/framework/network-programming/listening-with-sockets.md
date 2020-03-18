---
title: Überwachen mit Sockets
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- sockets, listening with sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- protocols, sockets
- listening with sockets
- Internet, sockets
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
ms.openlocfilehash: cf8316ede6888b99a8b0c87cfa3426b33be18b7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180742"
---
# <a name="listening-with-sockets"></a>Überwachen mit Sockets
Listener oder Serversockets öffnen einen Port auf dem Netzwerk und warten dann darauf, dass ein Client eine Verbindung zu diesem Port herstellt. Obwohl andere Netzwerkadressfamilien und -protokolle vorhanden sind, zeigt dieses Beispiel, wie ein Remotedienst für ein TCP/IP-Netzwerk erstellt wird.  
  
 Die eindeutige Adresse eines TCP/IP-Diensts wird definiert, indem die IP-Adresse des Hosts mit der Portnummer des Diensts kombiniert wird, um einen Endpunkt für den Dienst zu erstellen. Die Klasse <xref:System.Net.Dns> enthält Methoden, die Informationen über die Netzwerkadressen zurückgeben, die vom lokalen Netzwerkgerät unterstützt werden. Wenn das lokale Netzwerkgerät über mehr als eine Netzwerkadresse verfügt, oder wenn das lokale System mehr als ein Netzwerkgerät unterstützt, gibt die **Dns**-Klasse Informationen über alle Netzwerkadressen zurück. Die Anwendung muss dann die richtige Adresse für den Dienst auswählen. Die Internet Assigned Numbers Authority (Iana) definiert Portnummern für gemeinsame Dienste. Weitere Informationen finden Sie unter [Service Name and Transport Protocol Port Number Registry (Registrierung von Portnummern für Dienstnamen und Transportprotokolle)](https://www.iana.org/assignments/port-numbers). Andere Dienste haben registrierte Portnummern im Bereich von 1024 bis 65.535.  
  
 Das folgende Beispiel erstellt eine <xref:System.Net.IPEndPoint> für einen Server, indem die erste IP-Adresse, die die**Dns** für den Hostcomputer zurückgegeben hat, mit einer Portnummer kombiniert wird, die aus dem Bereich der registrierten Portnummern ausgewählt wird.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.GetHostEntry(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.GetHostEntry(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 Wenn der lokale Endpunkt bestimmt ist, muss <xref:System.Net.Sockets.Socket> mit diesem Endpunkt mithilfe der <xref:System.Net.Sockets.Socket.Bind%2A>-Methode verknüpft und darauf festgelegt werden, mithilfe der <xref:System.Net.Sockets.Socket.Listen%2A>-Methode dem Endpunkt zu überwachen. **Bind** löst eine Ausnahme aus, wenn die spezifische Kombination aus Adresse und Port bereits verwendet wird. Das folgende Beispiel veranschaulicht das Zuordnen eines **Sockets** zu einem **IPEndPoint**.  
  
```vb  
Dim listener As New Socket(ipAddress.AddressFamily, _  
    SocketType.Stream, ProtocolType.Tcp)
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
Socket listener = new Socket(ipAddress.AddressFamily,
    SocketType.Stream, ProtocolType.Tcp);
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 Die **Listener**-Methode verwendet einen einzigen Parameter, der angibt, wie viele ausstehende Verbindungen zum **Socket** zugelassen sind, bevor der Fehler „Server ausgelastet“ an den verbindenden Client zurückgegeben wird. In diesem Fall werden bis zu 100 Clients in der Verbindungswarteschlange platziert, bevor die Antwort „Server ausgelastet“ an den 101. Client zurückgegeben wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden eines synchronen Serversockets](using-a-synchronous-server-socket.md)
- [Verwenden eines asynchronen Serversockets](using-an-asynchronous-server-socket.md)
- [Verwenden von Clientsockets](using-client-sockets.md)
- [Vorgehensweise: Erstellen eines Sockets](how-to-create-a-socket.md)
- [Sockets](sockets.md)
