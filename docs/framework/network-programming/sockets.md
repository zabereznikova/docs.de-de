---
title: Sockets
description: Informationen zur .NET Framework-Klasse „Socket“, bei der es sich um eine verwaltete Codeversion von Socketdiensten handelt, die von der Winsock32-API bereitgestellt wird
ms.date: 03/30/2017
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
ms.openlocfilehash: e00d04164f7ce5251b7f30b5abd16c14643f6862
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263125"
---
# <a name="sockets"></a>Sockets

Der <xref:System.Net.Sockets>-Namespace enthält eine verwaltete Implementierung der Windows Sockets-Schnittstelle. Alle anderen Netzwerkzugriffsklassen im <xref:System.Net>-Namespace sind auf dieser Implementierung von Sockets aufgebaut.  
  
 Die .NET Framework-Klasse <xref:System.Net.Sockets.Socket> ist eine verwaltete Codeversion von Socket-Diensten, die von der Winsock32-API bereitgestellt wird. In den meisten Fällen marshallen die **Socket**-Klassenmethoden einfach Daten in die nativen Win32-Entsprechungen und bearbeiten alle erforderlichen Überprüfungen.  
  
 Die **Socket**-Klasse unterstützt zwei grundlegende Modi: synchron und asynchron. Im synchronen Modus werden Funktionen, die Netzwerkvorgänge ausführen (z.B. <xref:System.Net.Sockets.Socket.Send%2A> und <xref:System.Net.Sockets.Socket.Receive%2A>), erst aufgerufen, wenn der Vorgang abgeschlossen ist, bevor die Steuerung an das aufrufende Programm zurückgegeben wird. Im asynchronen Modus werden diese Aufrufe sofort zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch

- [How to: Erstellen eines Sockets](how-to-create-a-socket.md)

- [Verwenden von Anwendungsprotokollen](using-application-protocols.md)
