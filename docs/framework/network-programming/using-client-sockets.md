---
title: Verwenden von Clientsockets
description: In diesem Beispiel wird gezeigt, wie eine TCP/IP-Verbindung mit einem Remotedienst mithilfe eines Sockets im .NET Framework erstellt wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- Socket class, client sockets
- protocols, sockets
- Internet, sockets
- sockets, client sockets
- client sockets
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
ms.openlocfilehash: 6982d09c20cd0d7e9d27fc63880b39e0982c86ef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265192"
---
# <a name="using-client-sockets"></a>Verwenden von Clientsockets

Bevor Sie eine Konversation über <xref:System.Net.Sockets.Socket> initiieren können, müssen Sie eine Datenpipeline zwischen Ihrer Anwendung und dem Remotegerät erstellen. Obwohl andere Netzwerkadressfamilien und -protokolle vorhanden sind, zeigt dieses Beispiel, wie eine TCP/IP-Verbindung mit einem Remotedienst erstellt wird.  
  
 TCP/IP verwendet eine Netzwerkadresse und eine Dienstportnummer zur eindeutigen Identifizierung eines Diensts. Die Netzwerkadresse identifiziert ein bestimmtes Gerät im Netzwerk. Die Portnummer identifiziert den bestimmten Dienst auf diesem Gerät für die Verbindung. Die Kombination von Netzwerkadresse und Dienstport wird Endpunkt genannt. Dieser wird in .NET Framework durch die <xref:System.Net.EndPoint>-Klasse dargestellt. Ein Nachfolger des **EndPoint** wird für jede unterstützte Adressfamilie definiert. Die Klasse für die IP-Adressfamilie ist <xref:System.Net.IPEndPoint>.  
  
 Die <xref:System.Net.Dns>-Klasse stellt Dienste des Domänennamen für Anwendungen zur Verfügung, die TCP/IP-Internetdienste verwenden. Die <xref:System.Net.Dns.Resolve%2A>-Methode fordert einen DNS-Server auf, einen benutzerfreundlichen Domänennamen (z.B. „host.contoso.com“) einer numerischen Internetadresse (z.B. 192.168.1.1) zuzuordnen. **Resolve** gibt <xref:System.Net.IPHostEntry> zurück. Dies enthält eine Liste der Adressen und Aliase für den angeforderten Namen. In den meisten Fällen können Sie die erste Adresse verwenden, die im <xref:System.Net.IPHostEntry.AddressList%2A>-Array zurückgegeben wurde. Der folgende Code ruft <xref:System.Net.IPAddress> auf. Dies enthält die IP-Adresse für den Server host.contoso.com.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 Die Internet Assigned Numbers Authority (IANA) definiert Portnummern für gemeinsame Dienste. Weitere Informationen finden Sie unter [Registrierung von Portnummern für Dienstnamen und Transportprotokolle](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (in englischer Sprache). Andere Dienste haben registrierte Portnummern im Bereich von 1024 bis 65.535. Der folgende Code kombiniert die IP-Adresse für host.contoso.com mit einer Portnummer, um einen Remoteendpunkt für eine Verbindung zu erstellen.  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 Nach der Ermittlung der Adresse des Remotegeräts und der Auswahl eines Ports für die Verbindung, kann die Anwendung versuchen, eine Verbindung mit dem Remotegerät herzustellen. Im folgenden Beispiel wird ein vorhandener **IPEndPoint** für die Verbindung zu einem Remotegerät und die Ermittlung aller ausgelösten Ausnahmen verwendet.  
  
```vb  
Try  
    s.Connect(ipe)  
Catch ae As ArgumentNullException  
    Console.WriteLine("ArgumentNullException : {0}", _  
        ae.ToString())  
Catch se As SocketException  
    Console.WriteLine("SocketException : {0}", se.ToString())  
Catch e As Exception  
    Console.WriteLine("Unexpected exception : {0}", e.ToString())  
End Try  
```  
  
```csharp  
try {  
    s.Connect(ipe);  
} catch(ArgumentNullException ae) {  
    Console.WriteLine("ArgumentNullException : {0}", ae.ToString());  
} catch(SocketException se) {  
    Console.WriteLine("SocketException : {0}", se.ToString());  
} catch(Exception e) {  
    Console.WriteLine("Unexpected exception : {0}", e.ToString());  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines synchronen Clientsockets](using-a-synchronous-client-socket.md)
- [Verwenden von asynchronen Clientsockets](using-an-asynchronous-client-socket.md)
- [How to: Erstellen eines Sockets](how-to-create-a-socket.md)
- [Sockets](sockets.md)
