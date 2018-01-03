---
title: 'Gewusst wie: Erstellen eines Sockets'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 24ec39798f5f31cf20cc5c84714efaae6ccbed52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-socket"></a>Gewusst wie: Erstellen eines Sockets
Bevor Sie einen Socket verwenden können, um mit einem Remotegerät zu kommunizieren, muss der Socket mit Informationen zu Protokoll und Netzwerkadresse initialisiert werden. Der Konstruktor für die Klasse <xref:System.Net.Sockets.Socket> besitzt Parameter, die die Adressfamilie, den Sockettyp und den Protokolltyp, den der Socket zum Aufbauen von Verbindungen verwendet, angeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Socket erstellt, der verwendet werden kann, um mit einem TCP/IP-basierten Netzwerk (z.B. das Internet) zu kommunizieren.  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
```  
  
 Ändern Sie den Protokolltyp wie im folgenden Beispiel, um UDP statt TCP zu verwenden:  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,   
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
```  
  
 Die Enumeration <xref:System.Net.Sockets.AddressFamily> gibt die Standardadressfamilien an, die von der **Socket**-Klasse verwendet werden, um Netzwerkadressen aufzulösen. Beispielsweise gibt der Member **AddressFamily.InterNetwork** die Adressfamilie „IP-Version 4“ an.  
  
 Die Enumeration <xref:System.Net.Sockets.SocketType> gibt den Sockettyp an. Beispielsweise gibt der Member **SocketType.Stream** einen Standardsocket zum Senden und Empfangen von Daten mit Flusssteuerung an.  
  
 Die Enumeration <xref:System.Net.Sockets.ProtocolType> gibt das Netzwerkprotokoll an, das bei der Kommunikation auf dem **Socket** verwendet wird. Beispielsweise gibt **ProtocolType.Tcp** an, dass der Socket TCP verwendet, während **ProtocolType.Udp** angibt, dass der Socket UDP verwendet.  
  
 Nachdem ein **Socket** erstellt wurde, kann dieser entweder eine Verbindung zu einem Remoteendpunkt initiieren oder Verbindungen von Remotegeräten empfangen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Clientsockets](../../../docs/framework/network-programming/using-client-sockets.md)  
 [Überwachen mit Sockets](../../../docs/framework/network-programming/listening-with-sockets.md)
