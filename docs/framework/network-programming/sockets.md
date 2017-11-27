---
title: Sockets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: de5778e398a9a7205e99cc810d0b672ac247da08
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sockets"></a>Sockets
Der <xref:System.Net.Sockets>-Namespace enthält eine verwaltete Implementierung der Windows Sockets-Schnittstelle. Alle anderen Netzwerkzugriffsklassen im <xref:System.Net>-Namespace sind auf dieser Implementierung von Sockets aufgebaut.  
  
 Die .NET Framework-Klasse <xref:System.Net.Sockets.Socket> ist eine verwaltete Codeversion von Socket-Diensten, die von der Winsock32-API bereitgestellt wird. In den meisten Fällen marshallen die **Socket**-Klassenmethoden einfach Daten in die nativen Win32-Entsprechungen und bearbeiten alle erforderlichen Überprüfungen.  
  
 Die **Socket**-Klasse unterstützt zwei grundlegende Modi: synchron und asynchron. Im synchronen Modus werden Funktionen, die Netzwerkvorgänge ausführen (z.B. <xref:System.Net.Sockets.Socket.Send%2A> und <xref:System.Net.Sockets.Socket.Receive%2A>), erst aufgerufen, wenn der Vorgang abgeschlossen ist, bevor die Steuerung an das aufrufende Programm zurückgegeben wird. Im asynchronen Modus werden diese Aufrufe sofort zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines Sockets](../../../docs/framework/network-programming/how-to-create-a-socket.md)  
    
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)
