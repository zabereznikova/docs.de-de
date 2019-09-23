---
title: TCP-UDP
ms.date: 03/30/2017
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
ms.openlocfilehash: d35278ab7feb42453b5a0adbc86c47b7ac3ff5ca
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71047113"
---
# <a name="tcp-udp"></a><span data-ttu-id="260ef-102">TCP-UDP</span><span class="sxs-lookup"><span data-stu-id="260ef-102">TCP-UDP</span></span>
<span data-ttu-id="260ef-103">Anwendungen können die Dienste Transmission Control Protocol (TCP) und User Datagram Protocol (UDP) mit den <xref:System.Net.Sockets.TcpClient>-, <xref:System.Net.Sockets.TcpListener>- und <xref:System.Net.Sockets.UdpClient>-Klassen verwenden.</span><span class="sxs-lookup"><span data-stu-id="260ef-103">Applications can use Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) services with the <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes.</span></span> <span data-ttu-id="260ef-104">Diese Protokollklassen bauen auf der <xref:System.Net.Sockets.Socket?displayProperty=nameWithType>-Klasse auf und kümmern sich um die Details der Datenübertragung.</span><span class="sxs-lookup"><span data-stu-id="260ef-104">These protocol classes are built on top of the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class and take care of the details of transferring data.</span></span>  
  
 <span data-ttu-id="260ef-105">Die Protokollklassen verwenden die synchronen Methoden der **Socket**-Klasse, um den einfachen und unkomplizierten Zugriff auf Netzwerkdienste bereitzustellen, ohne den Aufwand für die Verwaltung von Statusinformationen oder Kenntnisse der Details zum Einrichten der protokollspezifischen Sockets.</span><span class="sxs-lookup"><span data-stu-id="260ef-105">The protocol classes use the synchronous methods of the **Socket** class to provide simple and straightforward access to network services without the overhead of maintaining state information or knowing the details of setting up protocol-specific sockets.</span></span> <span data-ttu-id="260ef-106">Für die Verwendung der asynchronen **Socket**-Methoden können Sie die asynchronen Methoden nutzen, die von der <xref:System.Net.Sockets.NetworkStream>-Klasse bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="260ef-106">To use asynchronous **Socket** methods, you can use the asynchronous methods supplied by the <xref:System.Net.Sockets.NetworkStream> class.</span></span> <span data-ttu-id="260ef-107">Zum Zugriff auf Funktionen der **Socket**-Klasse, die nicht von den Protokollklassen verfügbar gemacht werden, müsse Sie die **Socket**-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="260ef-107">To access features of the **Socket** class not exposed by the protocol classes, you must use the **Socket** class.</span></span>  
  
 <span data-ttu-id="260ef-108">**TcpClient** und **TcpListener** stellen das Netzwerk mithilfe der **NetworkStream**-Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="260ef-108">**TcpClient** and **TcpListener** represent the network using the **NetworkStream** class.</span></span> <span data-ttu-id="260ef-109">Verwenden Sie die <xref:System.Net.Sockets.TcpClient.GetStream%2A>-Methode zum Zurückgeben des Netzwerkstreams, und rufen Sie anschließend die <xref:System.Net.Sockets.NetworkStream.Read%2A>- und <xref:System.Net.Sockets.NetworkStream.Write%2A>-Methoden des Streams auf.</span><span class="sxs-lookup"><span data-stu-id="260ef-109">You use the <xref:System.Net.Sockets.TcpClient.GetStream%2A> method to return the network stream, and then call the stream's <xref:System.Net.Sockets.NetworkStream.Read%2A> and <xref:System.Net.Sockets.NetworkStream.Write%2A> methods.</span></span> <span data-ttu-id="260ef-110">Der **NetworkStream** besitzt den den Protokollklassen zugrunde liegenden Socket nicht, sodass der Abschluss den Socket nicht betrifft.</span><span class="sxs-lookup"><span data-stu-id="260ef-110">The **NetworkStream** does not own the protocol classes' underlying socket, so closing it does not affect the socket.</span></span>  
  
 <span data-ttu-id="260ef-111">Die **UdpClient**-Klasse verwendet ein Array von Bytes zum Speichern des UDP-Datagramms.</span><span class="sxs-lookup"><span data-stu-id="260ef-111">The **UdpClient** class uses an array of bytes to hold the UDP datagram.</span></span> <span data-ttu-id="260ef-112">Verwenden Sie die <xref:System.Net.Sockets.UdpClient.Send%2A>-Methode, um die Daten an das Netzwerk zu senden, und die <xref:System.Net.Sockets.UdpClient.Receive%2A>-Methode, um ein eingehendes Datagramm zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="260ef-112">You use the <xref:System.Net.Sockets.UdpClient.Send%2A> method to send the data to the network and the <xref:System.Net.Sockets.UdpClient.Receive%2A> method to receive an incoming datagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="260ef-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="260ef-113">See also</span></span>

- [<span data-ttu-id="260ef-114">Verwenden von TCP-Diensten</span><span class="sxs-lookup"><span data-stu-id="260ef-114">Using TCP Services</span></span>](using-tcp-services.md)
- [<span data-ttu-id="260ef-115">Verwenden von UDP-Diensten</span><span class="sxs-lookup"><span data-stu-id="260ef-115">Using UDP Services</span></span>](using-udp-services.md)
- [<span data-ttu-id="260ef-116">Verwenden von Datenströmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="260ef-116">Using Streams on the Network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="260ef-117">Verwenden eines asynchronen Serversockets</span><span class="sxs-lookup"><span data-stu-id="260ef-117">Using an Asynchronous Server Socket</span></span>](using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="260ef-118">Verwenden von asynchronen Clientsockets</span><span class="sxs-lookup"><span data-stu-id="260ef-118">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="260ef-119">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="260ef-119">Using Application Protocols</span></span>](using-application-protocols.md)
