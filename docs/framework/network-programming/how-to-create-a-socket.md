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
ms.openlocfilehash: 9746b814188a4dc92463399542a6044501d0da12
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287396"
---
# <a name="how-to-create-a-socket"></a>Vorgehensweise: Erstellen eines Sockets

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

- [Verwenden von Clientsockets](using-client-sockets.md)
- [Überwachen mit Sockets](listening-with-sockets.md)
