---
title: Überwachen mit Sockets
description: Hier erfahren Sie, wie Sie einen Remotedienst erstellen, bei dem ein Serversocket einen Port im Netzwerk öffnet und darauf wartet, dass ein Client eine Verbindung mit diesem Port herstellt.
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
ms.openlocfilehash: 0b6de67772bae397373e307ec02ce69a71b0542e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502313"
---
# <a name="listening-with-sockets"></a><span data-ttu-id="1ec08-103">Überwachen mit Sockets</span><span class="sxs-lookup"><span data-stu-id="1ec08-103">Listening with Sockets</span></span>
<span data-ttu-id="1ec08-104">Listener oder Serversockets öffnen einen Port auf dem Netzwerk und warten dann darauf, dass ein Client eine Verbindung zu diesem Port herstellt.</span><span class="sxs-lookup"><span data-stu-id="1ec08-104">Listener or server sockets open a port on the network and then wait for a client to connect to that port.</span></span> <span data-ttu-id="1ec08-105">Obwohl andere Netzwerkadressfamilien und -protokolle vorhanden sind, zeigt dieses Beispiel, wie ein Remotedienst für ein TCP/IP-Netzwerk erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1ec08-105">Although other network address families and protocols exist, this example shows how to create remote service for a TCP/IP network.</span></span>  
  
 <span data-ttu-id="1ec08-106">Die eindeutige Adresse eines TCP/IP-Diensts wird definiert, indem die IP-Adresse des Hosts mit der Portnummer des Diensts kombiniert wird, um einen Endpunkt für den Dienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1ec08-106">The unique address of a TCP/IP service is defined by combining the IP address of the host with the port number of the service to create an endpoint for the service.</span></span> <span data-ttu-id="1ec08-107">Die Klasse <xref:System.Net.Dns> enthält Methoden, die Informationen über die Netzwerkadressen zurückgeben, die vom lokalen Netzwerkgerät unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1ec08-107">The <xref:System.Net.Dns> class provides methods that return information about the network addresses supported by the local network device.</span></span> <span data-ttu-id="1ec08-108">Wenn das lokale Netzwerkgerät über mehr als eine Netzwerkadresse verfügt, oder wenn das lokale System mehr als ein Netzwerkgerät unterstützt, gibt die **Dns**-Klasse Informationen über alle Netzwerkadressen zurück. Die Anwendung muss dann die richtige Adresse für den Dienst auswählen.</span><span class="sxs-lookup"><span data-stu-id="1ec08-108">When the local network device has more than one network address, or if the local system supports more than one network device, the **Dns** class returns information about all network addresses, and the application must choose the proper address for the service.</span></span> <span data-ttu-id="1ec08-109">Die Internet Assigned Numbers Authority (Iana) definiert Portnummern für gemeinsame Dienste. Weitere Informationen finden Sie unter [Service Name and Transport Protocol Port Number Registry (Registrierung von Portnummern für Dienstnamen und Transportprotokolle)](https://www.iana.org/assignments/port-numbers).</span><span class="sxs-lookup"><span data-stu-id="1ec08-109">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services; for more information, see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/port-numbers).</span></span> <span data-ttu-id="1ec08-110">Andere Dienste haben registrierte Portnummern im Bereich von 1024 bis 65.535.</span><span class="sxs-lookup"><span data-stu-id="1ec08-110">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span>  
  
 <span data-ttu-id="1ec08-111">Das folgende Beispiel erstellt eine <xref:System.Net.IPEndPoint> für einen Server, indem die erste IP-Adresse, die die**Dns** für den Hostcomputer zurückgegeben hat, mit einer Portnummer kombiniert wird, die aus dem Bereich der registrierten Portnummern ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="1ec08-111">The following example creates an <xref:System.Net.IPEndPoint> for a server by combining the first IP address returned by **Dns** for the host computer with a port number chosen from the registered port numbers range.</span></span>  
  
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
  
 <span data-ttu-id="1ec08-112">Wenn der lokale Endpunkt bestimmt ist, muss <xref:System.Net.Sockets.Socket> mit diesem Endpunkt mithilfe der <xref:System.Net.Sockets.Socket.Bind%2A>-Methode verknüpft und darauf festgelegt werden, mithilfe der <xref:System.Net.Sockets.Socket.Listen%2A>-Methode dem Endpunkt zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="1ec08-112">After the local endpoint is determined, the <xref:System.Net.Sockets.Socket> must be associated with that endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> method and set to listen on the endpoint using the <xref:System.Net.Sockets.Socket.Listen%2A> method.</span></span> <span data-ttu-id="1ec08-113">**Bind** löst eine Ausnahme aus, wenn die spezifische Kombination aus Adresse und Port bereits verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ec08-113">**Bind** throws an exception if the specific address and port combination is already in use.</span></span> <span data-ttu-id="1ec08-114">Das folgende Beispiel veranschaulicht das Zuordnen eines **Sockets** zu einem **IPEndPoint**.</span><span class="sxs-lookup"><span data-stu-id="1ec08-114">The following example demonstrates associating a **Socket** with an **IPEndPoint**.</span></span>  
  
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
  
 <span data-ttu-id="1ec08-115">Die **Listener**-Methode verwendet einen einzigen Parameter, der angibt, wie viele ausstehende Verbindungen zum **Socket** zugelassen sind, bevor der Fehler „Server ausgelastet“ an den verbindenden Client zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1ec08-115">The **Listen** method takes a single parameter that specifies how many pending connections to the **Socket** are allowed before a server busy error is returned to the connecting client.</span></span> <span data-ttu-id="1ec08-116">In diesem Fall werden bis zu 100 Clients in der Verbindungswarteschlange platziert, bevor die Antwort „Server ausgelastet“ an den 101. Client zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1ec08-116">In this case, up to 100 clients are placed in the connection queue before a server busy response is returned to client number 101.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ec08-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ec08-117">See also</span></span>

- [<span data-ttu-id="1ec08-118">Verwenden eines synchronen Serversockets</span><span class="sxs-lookup"><span data-stu-id="1ec08-118">Using a Synchronous Server Socket</span></span>](using-a-synchronous-server-socket.md)
- [<span data-ttu-id="1ec08-119">Verwenden eines asynchronen Serversockets</span><span class="sxs-lookup"><span data-stu-id="1ec08-119">Using an Asynchronous Server Socket</span></span>](using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="1ec08-120">Verwenden von Clientsockets</span><span class="sxs-lookup"><span data-stu-id="1ec08-120">Using Client Sockets</span></span>](using-client-sockets.md)
- [<span data-ttu-id="1ec08-121">How to: Erstellen eines Sockets</span><span class="sxs-lookup"><span data-stu-id="1ec08-121">How to: Create a Socket</span></span>](how-to-create-a-socket.md)
- [<span data-ttu-id="1ec08-122">Sockets</span><span class="sxs-lookup"><span data-stu-id="1ec08-122">Sockets</span></span>](sockets.md)
