---
title: TCP-UDP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- protocols, TCP/UDP
- network resources, TCP/UDP
- sending data, TCP/UDP
- TCP/UDP
- TcpClient class, about TcpClient class
- application protocols, TCP/UDP
- receiving data, TCP/UDP
- TcpListener class, about TcpListener class
- Socket class, about Socket class
- UDP
- data requests, TCP/UDP
- requesting data from Internet, TCP/UDP
- Internet, TCP/UDP
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 04a3bb1c7499a60175aaaa9715e780ea5ddceb31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="tcp-udp"></a><span data-ttu-id="14245-102">TCP-UDP</span><span class="sxs-lookup"><span data-stu-id="14245-102">TCP-UDP</span></span>
<span data-ttu-id="14245-103">Anwendungen können die Dienste Transmission Control Protocol (TCP) und User Datagram Protocol (UDP) mit den <xref:System.Net.Sockets.TcpClient>-, <xref:System.Net.Sockets.TcpListener>- und <xref:System.Net.Sockets.UdpClient>-Klassen verwenden.</span><span class="sxs-lookup"><span data-stu-id="14245-103">Applications can use Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) services with the <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes.</span></span> <span data-ttu-id="14245-104">Diese Protokollklassen bauen auf der <xref:System.Net.Sockets.Socket?displayProperty=nameWithType>-Klasse auf und kümmern sich um die Details der Datenübertragung.</span><span class="sxs-lookup"><span data-stu-id="14245-104">These protocol classes are built on top of the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class and take care of the details of transferring data.</span></span>  
  
 <span data-ttu-id="14245-105">Die Protokollklassen verwenden die synchronen Methoden der **Socket**-Klasse, um den einfachen und unkomplizierten Zugriff auf Netzwerkdienste bereitzustellen, ohne den Aufwand für die Verwaltung von Statusinformationen oder Kenntnisse der Details zum Einrichten der protokollspezifischen Sockets.</span><span class="sxs-lookup"><span data-stu-id="14245-105">The protocol classes use the synchronous methods of the **Socket** class to provide simple and straightforward access to network services without the overhead of maintaining state information or knowing the details of setting up protocol-specific sockets.</span></span> <span data-ttu-id="14245-106">Für die Verwendung der asynchronen **Socket**-Methoden können Sie die asynchronen Methoden nutzen, die von der <xref:System.Net.Sockets.NetworkStream>-Klasse bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="14245-106">To use asynchronous **Socket** methods, you can use the asynchronous methods supplied by the <xref:System.Net.Sockets.NetworkStream> class.</span></span> <span data-ttu-id="14245-107">Zum Zugriff auf Funktionen der **Socket**-Klasse, die nicht von den Protokollklassen verfügbar gemacht werden, müsse Sie die **Socket**-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="14245-107">To access features of the **Socket** class not exposed by the protocol classes, you must use the **Socket** class.</span></span>  
  
 <span data-ttu-id="14245-108">**TcpClient** und **TcpListener** stellen das Netzwerk mithilfe der **NetworkStream**-Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="14245-108">**TcpClient** and **TcpListener** represent the network using the **NetworkStream** class.</span></span> <span data-ttu-id="14245-109">Verwenden Sie die <xref:System.Net.Sockets.TcpClient.GetStream%2A>-Methode zum Zurückgeben des Netzwerkstreams, und rufen Sie anschließend die <xref:System.Net.Sockets.NetworkStream.Read%2A>- und <xref:System.Net.Sockets.NetworkStream.Write%2A>-Methoden des Streams auf.</span><span class="sxs-lookup"><span data-stu-id="14245-109">You use the <xref:System.Net.Sockets.TcpClient.GetStream%2A> method to return the network stream, and then call the stream's <xref:System.Net.Sockets.NetworkStream.Read%2A> and <xref:System.Net.Sockets.NetworkStream.Write%2A> methods.</span></span> <span data-ttu-id="14245-110">Der **NetworkStream** besitzt den den Protokollklassen zugrunde liegenden Socket nicht, sodass der Abschluss den Socket nicht betrifft.</span><span class="sxs-lookup"><span data-stu-id="14245-110">The **NetworkStream** does not own the protocol classes' underlying socket, so closing it does not affect the socket.</span></span>  
  
 <span data-ttu-id="14245-111">Die **UdpClient**-Klasse verwendet ein Array von Bytes zum Speichern des UDP-Datagramms.</span><span class="sxs-lookup"><span data-stu-id="14245-111">The **UdpClient** class uses an array of bytes to hold the UDP datagram.</span></span> <span data-ttu-id="14245-112">Verwenden Sie die <xref:System.Net.Sockets.UdpClient.Send%2A>-Methode, um die Daten an das Netzwerk zu senden, und die <xref:System.Net.Sockets.UdpClient.Receive%2A>-Methode, um ein eingehendes Datagramm zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="14245-112">You use the <xref:System.Net.Sockets.UdpClient.Send%2A> method to send the data to the network and the <xref:System.Net.Sockets.UdpClient.Receive%2A> method to receive an incoming datagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14245-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14245-113">See Also</span></span>  
 [<span data-ttu-id="14245-114">Mithilfe von TCP-Diensten</span><span class="sxs-lookup"><span data-stu-id="14245-114">Using TCP Services</span></span>](../../../docs/framework/network-programming/using-tcp-services.md)  
 [<span data-ttu-id="14245-115">Mithilfe von UDP-Diensten</span><span class="sxs-lookup"><span data-stu-id="14245-115">Using UDP Services</span></span>](../../../docs/framework/network-programming/using-udp-services.md)  
 [<span data-ttu-id="14245-116">Verwenden von Streams im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="14245-116">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="14245-117">Verwenden eines asynchronen Serversockets</span><span class="sxs-lookup"><span data-stu-id="14245-117">Using an Asynchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)  
 [<span data-ttu-id="14245-118">Verwenden von asynchronen Clientsockets</span><span class="sxs-lookup"><span data-stu-id="14245-118">Using an Asynchronous Client Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)  
 [<span data-ttu-id="14245-119">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="14245-119">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
