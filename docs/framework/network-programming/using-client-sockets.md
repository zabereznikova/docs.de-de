---
title: Verwenden von Clientsockets
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
ms.openlocfilehash: fe2ad55c3f60347369c0e92bc834d81d98f3870e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71046958"
---
# <a name="using-client-sockets"></a><span data-ttu-id="fb127-102">Verwenden von Clientsockets</span><span class="sxs-lookup"><span data-stu-id="fb127-102">Using Client Sockets</span></span>
<span data-ttu-id="fb127-103">Bevor Sie eine Konversation über <xref:System.Net.Sockets.Socket> initiieren können, müssen Sie eine Datenpipeline zwischen Ihrer Anwendung und dem Remotegerät erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb127-103">Before you can initiate a conversation through a <xref:System.Net.Sockets.Socket>, you must create a data pipe between your application and the remote device.</span></span> <span data-ttu-id="fb127-104">Obwohl andere Netzwerkadressfamilien und -protokolle vorhanden sind, zeigt dieses Beispiel, wie eine TCP/IP-Verbindung mit einem Remotedienst erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fb127-104">Although other network address families and protocols exist, this example shows how to create a TCP/IP connection to a remote service.</span></span>  
  
 <span data-ttu-id="fb127-105">TCP/IP verwendet eine Netzwerkadresse und eine Dienstportnummer zur eindeutigen Identifizierung eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="fb127-105">TCP/IP uses a network address and a service port number to uniquely identify a service.</span></span> <span data-ttu-id="fb127-106">Die Netzwerkadresse identifiziert ein bestimmtes Gerät im Netzwerk. Die Portnummer identifiziert den bestimmten Dienst auf diesem Gerät für die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="fb127-106">The network address identifies a specific device on the network; the port number identifies the specific service on that device to connect to.</span></span> <span data-ttu-id="fb127-107">Die Kombination von Netzwerkadresse und Dienstport wird Endpunkt genannt. Dieser wird in .NET Framework durch die <xref:System.Net.EndPoint>-Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fb127-107">The combination of network address and service port is called an endpoint, which is represented in the .NET Framework by the <xref:System.Net.EndPoint> class.</span></span> <span data-ttu-id="fb127-108">Ein Nachfolger des **EndPoint** wird für jede unterstützte Adressfamilie definiert. Die Klasse für die IP-Adressfamilie ist <xref:System.Net.IPEndPoint>.</span><span class="sxs-lookup"><span data-stu-id="fb127-108">A descendant of **EndPoint** is defined for each supported address family; for the IP address family, the class is <xref:System.Net.IPEndPoint>.</span></span>  
  
 <span data-ttu-id="fb127-109">Die <xref:System.Net.Dns>-Klasse stellt Dienste des Domänennamen für Anwendungen zur Verfügung, die TCP/IP-Internetdienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb127-109">The <xref:System.Net.Dns> class provides domain-name services to applications that use TCP/IP Internet services.</span></span> <span data-ttu-id="fb127-110">Die <xref:System.Net.Dns.Resolve%2A>-Methode fordert einen DNS-Server auf, einen benutzerfreundlichen Domänennamen (z.B. „host.contoso.com“) einer numerischen Internetadresse (z.B. 192.168.1.1) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="fb127-110">The <xref:System.Net.Dns.Resolve%2A> method queries a DNS server to map a user-friendly domain name (such as "host.contoso.com") to a numeric Internet address (such as 192.168.1.1).</span></span> <span data-ttu-id="fb127-111">**Resolve** gibt <xref:System.Net.IPHostEntry> zurück. Dies enthält eine Liste der Adressen und Aliase für den angeforderten Namen.</span><span class="sxs-lookup"><span data-stu-id="fb127-111">**Resolve** returns an <xref:System.Net.IPHostEntry> that contains a list of addresses and aliases for the requested name.</span></span> <span data-ttu-id="fb127-112">In den meisten Fällen können Sie die erste Adresse verwenden, die im <xref:System.Net.IPHostEntry.AddressList%2A>-Array zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="fb127-112">In most cases, you can use the first address returned in the <xref:System.Net.IPHostEntry.AddressList%2A> array.</span></span> <span data-ttu-id="fb127-113">Der folgende Code ruft <xref:System.Net.IPAddress> auf. Dies enthält die IP-Adresse für den Server host.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fb127-113">The following code gets an <xref:System.Net.IPAddress> containing the IP address for the server host.contoso.com.</span></span>  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 <span data-ttu-id="fb127-114">Die Internet Assigned Numbers Authority (IANA) definiert Portnummern für gemeinsame Dienste. Weitere Informationen finden Sie unter [Registrierung von Portnummern für Dienstnamen und Transportprotokolle](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (in englischer Sprache).</span><span class="sxs-lookup"><span data-stu-id="fb127-114">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (for more information, see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="fb127-115">Andere Dienste haben registrierte Portnummern im Bereich von 1024 bis 65.535.</span><span class="sxs-lookup"><span data-stu-id="fb127-115">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span> <span data-ttu-id="fb127-116">Der folgende Code kombiniert die IP-Adresse für host.contoso.com mit einer Portnummer, um einen Remoteendpunkt für eine Verbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb127-116">The following code combines the IP address for host.contoso.com with a port number to create a remote endpoint for a connection.</span></span>  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 <span data-ttu-id="fb127-117">Nach der Ermittlung der Adresse des Remotegeräts und der Auswahl eines Ports für die Verbindung, kann die Anwendung versuchen, eine Verbindung mit dem Remotegerät herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fb127-117">After determining the address of the remote device and choosing a port to use for the connection, the application can attempt to establish a connection with the remote device.</span></span> <span data-ttu-id="fb127-118">Im folgenden Beispiel wird ein vorhandener **IPEndPoint** für die Verbindung zu einem Remotegerät und die Ermittlung aller ausgelösten Ausnahmen verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb127-118">The following example uses an existing **IPEndPoint** to connect to a remote device and catches any exceptions that are thrown.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fb127-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb127-119">See also</span></span>

- [<span data-ttu-id="fb127-120">Verwenden eines synchronen Clientsockets</span><span class="sxs-lookup"><span data-stu-id="fb127-120">Using a Synchronous Client Socket</span></span>](using-a-synchronous-client-socket.md)
- [<span data-ttu-id="fb127-121">Verwenden von asynchronen Clientsockets</span><span class="sxs-lookup"><span data-stu-id="fb127-121">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="fb127-122">Vorgehensweise: Erstellen eines Sockets</span><span class="sxs-lookup"><span data-stu-id="fb127-122">How to: Create a Socket</span></span>](how-to-create-a-socket.md)
- [<span data-ttu-id="fb127-123">Sockets</span><span class="sxs-lookup"><span data-stu-id="fb127-123">Sockets</span></span>](sockets.md)
