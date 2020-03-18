---
title: 'Gewusst wie: Erstellen eines Sockets'
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
ms.openlocfilehash: e71e7e235048361580c65bdb551919fe3038130b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180824"
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
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Clientsockets](using-client-sockets.md)
- [Listening with Sockets (Überwachen mit Sockets)](listening-with-sockets.md)
