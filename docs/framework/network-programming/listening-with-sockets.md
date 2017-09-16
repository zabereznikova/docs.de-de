---
title: "Überwachen mit Sockets"
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
- sending data, sockets
- sockets, listening with sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- protocols, sockets
- listening with sockets
- Internet, sockets
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
caps.latest.revision: 10
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 66c3a64a12e791cedbd4e978de2c1b6e06eabb98
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="listening-with-sockets"></a>Überwachen mit Sockets
Listener oder Serversockets öffnen einen Port auf dem Netzwerk und warten dann darauf, dass ein Client eine Verbindung zu diesem Port herstellt. Obwohl andere Netzwerkadressfamilien und -protokolle vorhanden sind, zeigt dieses Beispiel, wie ein Remotedienst für ein TCP/IP-Netzwerk erstellt wird.  
  
 Die eindeutige Adresse eines TCP/IP-Diensts wird definiert, indem die IP-Adresse des Hosts mit der Portnummer des Diensts kombiniert wird, um einen Endpunkt für den Dienst zu erstellen. Die Klasse <xref:System.Net.Dns> enthält Methoden, die Informationen über die Netzwerkadressen zurückgeben, die vom lokalen Netzwerkgerät unterstützt werden. Wenn das lokale Netzwerkgerät über mehr als eine Netzwerkadresse verfügt, oder wenn das lokale System mehr als ein Netzwerkgerät unterstützt, gibt die **Dns**-Klasse Informationen über alle Netzwerkadressen zurück. Die Anwendung muss dann die richtige Adresse für den Dienst auswählen. Internet Assigned Numbers Authority (Iana) definiert die Portnummern für gemeinsame Dienste (weitere Informationen finden Sie unter www.iana.org/assignments/port-numbers). Andere Dienste haben registrierte Portnummern im Bereich von 1024 bis 65.535.  
  
 Das folgende Beispiel erstellt eine <xref:System.Net.IPEndPoint> für einen Server, indem die erste IP-Adresse, die die**Dns** für den Hostcomputer zurückgegeben hat, mit einer Portnummer kombiniert wird, die aus dem Bereich der registrierten Portnummern ausgewählt wird.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 Wenn der lokale Endpunkt bestimmt ist, muss <xref:System.Net.Sockets.Socket> mit diesem Endpunkt mithilfe der <xref:System.Net.Sockets.Socket.Bind%2A>-Methode verknüpft und darauf festgelegt werden, mithilfe der <xref:System.Net.Sockets.Socket.Listen%2A>-Methode dem Endpunkt zu überwachen. **Bind** löst eine Ausnahme aus, wenn die spezifische Kombination aus Adresse und Port bereits verwendet wird. Das folgende Beispiel veranschaulicht das Zuordnen eines **Sockets** zu einem **IPEndPoint**.  
  
```vb  
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 Die **Listener**-Methode verwendet einen einzigen Parameter, der angibt, wie viele ausstehende Verbindungen zum **Socket** zugelassen sind, bevor der Fehler „Server ausgelastet“ an den verbindenden Client zurückgegeben wird. In diesem Fall werden bis zu 100 Clients in der Verbindungswarteschlange platziert, bevor die Antwort „Server ausgelastet“ an den 101. Client zurückgegeben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Using a Synchronous Server Socket (Verwenden eines synchronen Serversockets)](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [Using an Asynchronous Server Socket (Verwenden eines asynchronen Serversockets)](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Using Client Sockets (Verwenden von Clientsockets)](../../../docs/framework/network-programming/using-client-sockets.md)   
 [How to: Create a Socket (Vorgehensweise: Erstellen eines Sockets)](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)

