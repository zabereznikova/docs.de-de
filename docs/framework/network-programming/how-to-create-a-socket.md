---
title: 'Vorgehensweise: Erstellen eines Sockets'
description: Hier erfahren Sie, wie Sie einen Socket für die Kommunikation mit Remotegeräten initialisieren. Verwenden Sie die Socket-Klasse, um die Adressfamilie, den Sockettyp und den Protokolltyp anzugeben.
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
ms.openlocfilehash: 1d56ddea721b54192a7dd47d144b6c41bbb9a5d7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502547"
---
# <a name="how-to-create-a-socket"></a><span data-ttu-id="54774-104">Vorgehensweise: Erstellen eines Sockets</span><span class="sxs-lookup"><span data-stu-id="54774-104">How to: Create a Socket</span></span>
<span data-ttu-id="54774-105">Bevor Sie einen Socket verwenden können, um mit einem Remotegerät zu kommunizieren, muss der Socket mit Informationen zu Protokoll und Netzwerkadresse initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="54774-105">Before you can use a socket to communicate with remote devices, the socket must be initialized with protocol and network address information.</span></span> <span data-ttu-id="54774-106">Der Konstruktor für die Klasse <xref:System.Net.Sockets.Socket> besitzt Parameter, die die Adressfamilie, den Sockettyp und den Protokolltyp, den der Socket zum Aufbauen von Verbindungen verwendet, angeben.</span><span class="sxs-lookup"><span data-stu-id="54774-106">The constructor for the <xref:System.Net.Sockets.Socket> class has parameters that specify the address family, socket type, and protocol type that the socket uses to make connections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54774-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="54774-107">Example</span></span>  
 <span data-ttu-id="54774-108">Im folgenden Beispiel wird ein Socket erstellt, der verwendet werden kann, um mit einem TCP/IP-basierten Netzwerk (z.B. das Internet) zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="54774-108">The following example creates a Socket that can be used to communicate on a TCP/IP-based network, such as the Internet.</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
```  
  
 <span data-ttu-id="54774-109">Ändern Sie den Protokolltyp wie im folgenden Beispiel, um UDP statt TCP zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="54774-109">To use UDP instead of TCP, change the protocol type, as in the following example:</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
```  
  
 <span data-ttu-id="54774-110">Die Enumeration <xref:System.Net.Sockets.AddressFamily> gibt die Standardadressfamilien an, die von der **Socket**-Klasse verwendet werden, um Netzwerkadressen aufzulösen. Beispielsweise gibt der Member **AddressFamily.InterNetwork** die Adressfamilie „IP-Version 4“ an.</span><span class="sxs-lookup"><span data-stu-id="54774-110">The <xref:System.Net.Sockets.AddressFamily> enumeration specifies the standard address families used by the **Socket** class to resolve network addresses (for example, the **AddressFamily.InterNetwork** member specifies the IP version 4 address family).</span></span>  
  
 <span data-ttu-id="54774-111">Die Enumeration <xref:System.Net.Sockets.SocketType> gibt den Sockettyp an. Beispielsweise gibt der Member **SocketType.Stream** einen Standardsocket zum Senden und Empfangen von Daten mit Flusssteuerung an.</span><span class="sxs-lookup"><span data-stu-id="54774-111">The <xref:System.Net.Sockets.SocketType> enumeration specifies the type of socket (for example, the **SocketType.Stream** member indicates a standard socket for sending and receiving data with flow control).</span></span>  
  
 <span data-ttu-id="54774-112">Die Enumeration <xref:System.Net.Sockets.ProtocolType> gibt das Netzwerkprotokoll an, das bei der Kommunikation auf dem **Socket** verwendet wird. Beispielsweise gibt **ProtocolType.Tcp** an, dass der Socket TCP verwendet, während **ProtocolType.Udp** angibt, dass der Socket UDP verwendet.</span><span class="sxs-lookup"><span data-stu-id="54774-112">The <xref:System.Net.Sockets.ProtocolType> enumeration specifies the network protocol to use when communicating on the **Socket** (for example, **ProtocolType.Tcp** indicates that the socket uses TCP; **ProtocolType.Udp** indicates that the socket uses UDP).</span></span>  
  
 <span data-ttu-id="54774-113">Nachdem ein **Socket** erstellt wurde, kann dieser entweder eine Verbindung zu einem Remoteendpunkt initiieren oder Verbindungen von Remotegeräten empfangen.</span><span class="sxs-lookup"><span data-stu-id="54774-113">After a **Socket** is created, it can either initiate a connection to a remote endpoint or receive connections from remote devices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54774-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54774-114">See also</span></span>

- [<span data-ttu-id="54774-115">Verwenden von Clientsockets</span><span class="sxs-lookup"><span data-stu-id="54774-115">Using Client Sockets</span></span>](using-client-sockets.md)
- [<span data-ttu-id="54774-116">Überwachen mit Sockets</span><span class="sxs-lookup"><span data-stu-id="54774-116">Listening with Sockets</span></span>](listening-with-sockets.md)
