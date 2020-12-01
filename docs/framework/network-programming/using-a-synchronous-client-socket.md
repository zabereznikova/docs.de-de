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
ms.openlocfilehash: f198f283f2acfdcfbafed25baecb02a64e9d1e26
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236311"
---
# <a name="using-a-synchronous-client-socket"></a><span data-ttu-id="969e2-103">Verwenden eines synchronen Clientsockets</span><span class="sxs-lookup"><span data-stu-id="969e2-103">Using a Synchronous Client Socket</span></span>

<span data-ttu-id="969e2-104">Ein synchroner Clientsocket hält das Anwendungsprogramm an, während der Netzwerkvorgang abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="969e2-104">A synchronous client socket suspends the application program while the network operation completes.</span></span> <span data-ttu-id="969e2-105">Synchrone Serversockets eignen sich nicht für Anwendungen, die das Netzwerk in ihrem Betrieb stark nutzen, aber sie können einfachen Zugang zu Netzwerkdiensten für andere Anwendungen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="969e2-105">Synchronous sockets are not suitable for applications that make heavy use of the network for their operation, but they can enable simple access to network services for other applications.</span></span>  
  
 <span data-ttu-id="969e2-106">Übergeben Sie zum Senden von Daten ein Byte-Array an eine der Methoden zur Datenversendung (<xref:System.Net.Sockets.Socket.Send%2A> und <xref:System.Net.Sockets.Socket.SendTo%2A>) der <xref:System.Net.Sockets.Socket>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="969e2-106">To send data, pass a byte array to one of the <xref:System.Net.Sockets.Socket> class's send-data methods (<xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.SendTo%2A>).</span></span> <span data-ttu-id="969e2-107">Im folgenden Beispiel wird eine Zeichenfolge in einen Puffer mit Byte-Array mit der <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>-Eigenschaft codiert, und anschließend wird der Puffer mit der **Senden**-Methode an das Netzwerkgerät übertragen.</span><span class="sxs-lookup"><span data-stu-id="969e2-107">The following example encodes a string into a byte array buffer using the <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> property and then transmits the buffer to the network device using the **Send** method.</span></span> <span data-ttu-id="969e2-108">Die **Senden**-Methode gibt die Anzahl der Bytes zurück, die an das Netzwerkgerät gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="969e2-108">The **Send** method returns the number of bytes sent to the network device.</span></span>  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 <span data-ttu-id="969e2-109">Die **Senden**-Methode entfernt die Bytes aus dem Puffer und platziert sie mit der Netzwerkschnittstelle in die Warteschlange, um an das Netzwerkgerät gesendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="969e2-109">The **Send** method removes the bytes from the buffer and queues them with the network interface to be sent to the network device.</span></span> <span data-ttu-id="969e2-110">Die Netzwerkschnittstelle kann die Daten möglicherweise nicht sofort, aber letztendlich doch senden, solange die Verbindung mit der <xref:System.Net.Sockets.Socket.Shutdown%2A>-Methode normal geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="969e2-110">The network interface might not send the data immediately, but it will send it eventually, as long as the connection is closed normally with the <xref:System.Net.Sockets.Socket.Shutdown%2A> method.</span></span>  
  
 <span data-ttu-id="969e2-111">Um Daten von einem Netzwerkgerät zu empfangen, übergeben Sie einen Puffer an eine der Methoden zum Datenempfang (<xref:System.Net.Sockets.Socket.Receive%2A> und <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>) der **Socket**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="969e2-111">To receive data from a network device, pass a buffer to one of the **Socket** class's receive-data methods (<xref:System.Net.Sockets.Socket.Receive%2A> and <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>).</span></span> <span data-ttu-id="969e2-112">Synchrone Sockets werden die Anwendung anhalten, bis Bytes aus dem Netzwerk empfangen werden oder bis der Socket geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="969e2-112">Synchronous sockets will suspend the application until bytes are received from the network or until the socket is closed.</span></span> <span data-ttu-id="969e2-113">Im folgenden Beispiel werden Daten aus dem Netzwerk empfangen, und dann auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="969e2-113">The following example receives data from the network and then displays it on the console.</span></span> <span data-ttu-id="969e2-114">Im Beispiel wird davon ausgegangen, dass die Daten, die aus dem Netzwerk stammen, aus ASCII-codiertem Text bestehen.</span><span class="sxs-lookup"><span data-stu-id="969e2-114">The example assumes that the data coming from the network is ASCII-encoded text.</span></span> <span data-ttu-id="969e2-115">Die **Empfangen**-Methode gibt die Anzahl der Bytes zurück, die vom Netzwerk empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="969e2-115">The **Receive** method returns the number of bytes received from the network.</span></span>  
  
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
  
 <span data-ttu-id="969e2-116">Wenn der Socket nicht mehr benötigt wird, müssen Sie ihn freigeben, indem Sie die <xref:System.Net.Sockets.Socket.Shutdown%2A>-Methode und anschließend die **Schließen**-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="969e2-116">When the socket is no longer needed, you need to release it by calling the <xref:System.Net.Sockets.Socket.Shutdown%2A> method and then calling the **Close** method.</span></span> <span data-ttu-id="969e2-117">Das folgende Beispiel gibt ein **Socket** frei.</span><span class="sxs-lookup"><span data-stu-id="969e2-117">The following example releases a **Socket**.</span></span> <span data-ttu-id="969e2-118">Die <xref:System.Net.Sockets.SocketShutdown>-Enumeration definiert Konstanten, die angeben, ob der Socket zum Senden, Empfangen oder für beides geschlossen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="969e2-118">The <xref:System.Net.Sockets.SocketShutdown> enumeration defines constants that indicate whether the socket should be closed for sending, for receiving, or for both.</span></span>  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="969e2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="969e2-119">See also</span></span>

- [<span data-ttu-id="969e2-120">Verwenden von asynchronen Clientsockets</span><span class="sxs-lookup"><span data-stu-id="969e2-120">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="969e2-121">Überwachen mit Sockets</span><span class="sxs-lookup"><span data-stu-id="969e2-121">Listening with Sockets</span></span>](listening-with-sockets.md)
- [<span data-ttu-id="969e2-122">Synchrone Clientsockets - Beispiel</span><span class="sxs-lookup"><span data-stu-id="969e2-122">Synchronous Client Socket Example</span></span>](synchronous-client-socket-example.md)
