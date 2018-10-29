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
ms.openlocfilehash: 987a8aa789d8c4585a58a031c9d920ee5cab45aa
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50191874"
---
# <a name="tcp-udp"></a>TCP-UDP
Anwendungen können die Dienste Transmission Control Protocol (TCP) und User Datagram Protocol (UDP) mit den <xref:System.Net.Sockets.TcpClient>-, <xref:System.Net.Sockets.TcpListener>- und <xref:System.Net.Sockets.UdpClient>-Klassen verwenden. Diese Protokollklassen bauen auf der <xref:System.Net.Sockets.Socket?displayProperty=nameWithType>-Klasse auf und kümmern sich um die Details der Datenübertragung.  
  
 Die Protokollklassen verwenden die synchronen Methoden der **Socket**-Klasse, um den einfachen und unkomplizierten Zugriff auf Netzwerkdienste bereitzustellen, ohne den Aufwand für die Verwaltung von Statusinformationen oder Kenntnisse der Details zum Einrichten der protokollspezifischen Sockets. Für die Verwendung der asynchronen **Socket**-Methoden können Sie die asynchronen Methoden nutzen, die von der <xref:System.Net.Sockets.NetworkStream>-Klasse bereitgestellt werden. Zum Zugriff auf Funktionen der **Socket**-Klasse, die nicht von den Protokollklassen verfügbar gemacht werden, müsse Sie die **Socket**-Klasse verwenden.  
  
 **TcpClient** und **TcpListener** stellen das Netzwerk mithilfe der **NetworkStream**-Klasse dar. Verwenden Sie die <xref:System.Net.Sockets.TcpClient.GetStream%2A>-Methode zum Zurückgeben des Netzwerkstreams, und rufen Sie anschließend die <xref:System.Net.Sockets.NetworkStream.Read%2A>- und <xref:System.Net.Sockets.NetworkStream.Write%2A>-Methoden des Streams auf. Der **NetworkStream** besitzt den den Protokollklassen zugrunde liegenden Socket nicht, sodass der Abschluss den Socket nicht betrifft.  
  
 Die **UdpClient**-Klasse verwendet ein Array von Bytes zum Speichern des UDP-Datagramms. Verwenden Sie die <xref:System.Net.Sockets.UdpClient.Send%2A>-Methode, um die Daten an das Netzwerk zu senden, und die <xref:System.Net.Sockets.UdpClient.Receive%2A>-Methode, um ein eingehendes Datagramm zu empfangen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von TCP-Diensten](../../../docs/framework/network-programming/using-tcp-services.md)  
 [Verwenden von UDP-Diensten](../../../docs/framework/network-programming/using-udp-services.md)  
 [Verwenden von Datenströmen im Netzwerk](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [Verwenden eines asynchronen Serversockets](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)  
 [Verwenden von asynchronen Clientsockets](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)  
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)
