---
title: Sockets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
caps.latest.revision: 8
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9ddf506ee82d90c8a4d363c1ecc3abd1a8f9dbca
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="sockets"></a>Sockets
Der <xref:System.Net.Sockets>-Namespace enthält eine verwaltete Implementierung der Windows Sockets-Schnittstelle. Alle anderen Netzwerkzugriffsklassen im <xref:System.Net>-Namespace sind auf dieser Implementierung von Sockets aufgebaut.  
  
 Die .NET Framework-Klasse <xref:System.Net.Sockets.Socket> ist eine verwaltete Codeversion von Socket-Diensten, die von der Winsock32-API bereitgestellt wird. In den meisten Fällen marshallen die **Socket**-Klassenmethoden einfach Daten in die nativen Win32-Entsprechungen und bearbeiten alle erforderlichen Überprüfungen.  
  
 Die **Socket**-Klasse unterstützt zwei grundlegende Modi: synchron und asynchron. Im synchronen Modus werden Funktionen, die Netzwerkvorgänge ausführen (z.B. <xref:System.Net.Sockets.Socket.Send%2A> und <xref:System.Net.Sockets.Socket.Receive%2A>), erst aufgerufen, wenn der Vorgang abgeschlossen ist, bevor die Steuerung an das aufrufende Programm zurückgegeben wird. Im asynchronen Modus werden diese Aufrufe sofort zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines Sockets](../../../docs/framework/network-programming/how-to-create-a-socket.md)   
    
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)

