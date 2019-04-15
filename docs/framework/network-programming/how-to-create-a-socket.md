---
title: 'Vorgehensweise: Erstellen eines Sockets'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- Networking
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- Socket class, creating sockets
- Network Resources
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- sockets, creating
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
ms.openlocfilehash: 0bbdab11201171bf8d730276c7f94cbc5317acdd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101119"
---
# <a name="how-to-create-a-socket"></a><span data-ttu-id="6e065-102">Vorgehensweise: Erstellen eines Sockets</span><span class="sxs-lookup"><span data-stu-id="6e065-102">How to: Create a Socket</span></span>
<span data-ttu-id="6e065-103">Bevor Sie einen Socket verwenden können, um mit einem Remotegerät zu kommunizieren, muss der Socket mit Informationen zu Protokoll und Netzwerkadresse initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e065-103">Before you can use a socket to communicate with remote devices, the socket must be initialized with protocol and network address information.</span></span> <span data-ttu-id="6e065-104">Der Konstruktor für die Klasse <xref:System.Net.Sockets.Socket> besitzt Parameter, die die Adressfamilie, den Sockettyp und den Protokolltyp, den der Socket zum Aufbauen von Verbindungen verwendet, angeben.</span><span class="sxs-lookup"><span data-stu-id="6e065-104">The constructor for the <xref:System.Net.Sockets.Socket> class has parameters that specify the address family, socket type, and protocol type that the socket uses to make connections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e065-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e065-105">Example</span></span>  
 <span data-ttu-id="6e065-106">Im folgenden Beispiel wird ein Socket erstellt, der verwendet werden kann, um mit einem TCP/IP-basierten Netzwerk (z.B. das Internet) zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="6e065-106">The following example creates a Socket that can be used to communicate on a TCP/IP-based network, such as the Internet.</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
```  
  
 <span data-ttu-id="6e065-107">Ändern Sie den Protokolltyp wie im folgenden Beispiel, um UDP statt TCP zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="6e065-107">To use UDP instead of TCP, change the protocol type, as in the following example:</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
```  
  
 <span data-ttu-id="6e065-108">Die Enumeration <xref:System.Net.Sockets.AddressFamily> gibt die Standardadressfamilien an, die von der **Socket**-Klasse verwendet werden, um Netzwerkadressen aufzulösen. Beispielsweise gibt der Member **AddressFamily.InterNetwork** die Adressfamilie „IP-Version 4“ an.</span><span class="sxs-lookup"><span data-stu-id="6e065-108">The <xref:System.Net.Sockets.AddressFamily> enumeration specifies the standard address families used by the **Socket** class to resolve network addresses (for example, the **AddressFamily.InterNetwork** member specifies the IP version 4 address family).</span></span>  
  
 <span data-ttu-id="6e065-109">Die Enumeration <xref:System.Net.Sockets.SocketType> gibt den Sockettyp an. Beispielsweise gibt der Member **SocketType.Stream** einen Standardsocket zum Senden und Empfangen von Daten mit Flusssteuerung an.</span><span class="sxs-lookup"><span data-stu-id="6e065-109">The <xref:System.Net.Sockets.SocketType> enumeration specifies the type of socket (for example, the **SocketType.Stream** member indicates a standard socket for sending and receiving data with flow control).</span></span>  
  
 <span data-ttu-id="6e065-110">Die Enumeration <xref:System.Net.Sockets.ProtocolType> gibt das Netzwerkprotokoll an, das bei der Kommunikation auf dem **Socket** verwendet wird. Beispielsweise gibt **ProtocolType.Tcp** an, dass der Socket TCP verwendet, während **ProtocolType.Udp** angibt, dass der Socket UDP verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e065-110">The <xref:System.Net.Sockets.ProtocolType> enumeration specifies the network protocol to use when communicating on the **Socket** (for example, **ProtocolType.Tcp** indicates that the socket uses TCP; **ProtocolType.Udp** indicates that the socket uses UDP).</span></span>  
  
 <span data-ttu-id="6e065-111">Nachdem ein **Socket** erstellt wurde, kann dieser entweder eine Verbindung zu einem Remoteendpunkt initiieren oder Verbindungen von Remotegeräten empfangen.</span><span class="sxs-lookup"><span data-stu-id="6e065-111">After a **Socket** is created, it can either initiate a connection to a remote endpoint or receive connections from remote devices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e065-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e065-112">See also</span></span>

- [<span data-ttu-id="6e065-113">Verwenden von Clientsockets</span><span class="sxs-lookup"><span data-stu-id="6e065-113">Using Client Sockets</span></span>](../../../docs/framework/network-programming/using-client-sockets.md)
- [<span data-ttu-id="6e065-114">Überwachen mit Sockets</span><span class="sxs-lookup"><span data-stu-id="6e065-114">Listening with Sockets</span></span>](../../../docs/framework/network-programming/listening-with-sockets.md)
