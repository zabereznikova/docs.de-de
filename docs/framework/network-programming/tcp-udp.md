---
title: "TCP/UDP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Protokolle, TCP/UDP"
  - "Netzwerkressourcen, TCP/UDP"
  - "Senden von Daten, TCP/UDP"
  - "TCP/UDP"
  - "TcpClient-Klasse, Informationen zur TcpClient-Klasse"
  - "Anwendungsprotokolle, TCP/UDP"
  - "Empfangen von Daten, TCP/UDP"
  - "TcpListener-Klasse, Informationen zur TcpListener-Klasse"
  - "Socket-Klasse, Informationen zur Socket-Klasse"
  - "UDP"
  - "Datenanforderungen, TCP/UDP"
  - "Anfordern von Daten aus dem Internet, TCP/UDP"
  - "Internet, TCP/UDP"
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# TCP/UDP
Anwendungen können Dienste des TCP \(Transmission Control Protocol\) und UDP \(User Datagram Protocol\) mit <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> und <xref:System.Net.Sockets.UdpClient>\-Klassen verwenden.  Diese Protokollklassen werden auf die <xref:System.Net.Sockets.Socket?displayProperty=fullName>\-Klasse erstellt und um den Details des Übertragens von Daten kümmern.  
  
 Die Protokollklassen verwenden die synchronen Methoden der Klasse **Socket**, um einfachen und einfachen Zugriff auf den Netzwerkdiensten ohne den Mehraufwand von Wartungszustandsinformationen oder von Verständnis der Details der Einrichtung von protokollspezifischen Sockets zu ermöglichen.  Um **Socket** asynchrone Methoden zu verwenden, können Sie die asynchronen Methoden verwenden, die von der <xref:System.Net.Sockets.NetworkStream>\-Klasse angegeben werden.  Um auf Funktionen **Socket** auf eine Sie nicht verfügbar gemachte durch die Protokollklassen, müssen Sie die **Socket**\-Klasse verwenden.  
  
 **TcpClient** und **TcpListener** stellen das Netzwerk mithilfe der **NetworkStream**\-Klasse dar.  Sie verwenden die <xref:System.Net.Sockets.TcpClient.GetStream%2A>\-Methode, um den Netzwerkstream zurückzugeben und dann die <xref:System.Net.Sockets.NetworkStream.Read%2A> und <xref:System.Net.Sockets.NetworkStream.Write%2A>\-Methoden des Streams auf.  **NetworkStream** besitzt nicht den zugrunde liegenden Socket der Protokollklassen und so schließt die, wirkt sich nicht auf den Socket.  
  
 Die **UdpClient**\-Klasse verwendet ein Bytearray, um das UDP\-Datagramm aufzunehmen.  Sie verwenden die <xref:System.Net.Sockets.UdpClient.Send%2A>\-Methode, um die Daten mit dem Netzwerk und zur <xref:System.Net.Sockets.UdpClient.Receive%2A>\-Methode zu senden, um ein eingehendes Datagramm zu empfangen.  
  
## Siehe auch  
 [Verwenden von TCP\-Diensten](../../../docs/framework/network-programming/using-tcp-services.md)   
 [Verwenden von UDP\-Diensten](../../../docs/framework/network-programming/using-udp-services.md)   
 [Verwenden von Streams im Netzwerk](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [Verwenden eines asynchronen Serversockets](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)   
 [Verwenden von asynchronen Clientsockets](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)   
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)