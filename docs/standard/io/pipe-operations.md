---
title: Pipeoperationen in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 879e5a73417f9347224bc22b397814b83972751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="pipe-operations-in-the-net-framework"></a>Pipeoperationen in .NET Framework
Pipes stellen eine Möglichkeit für die prozessübergreifende Kommunikation. Es gibt zwei Arten von Pipes:  
  
-   Anonyme Pipes.  
  
     Anonyme Pipes stellen prozessübergreifende Kommunikation auf einem lokalen Computer bereit. Anonyme Pipes erfordern weniger Mehraufwand als benannte Pipes, jedoch begrenzte Diensten bieten. Anonyme Pipes sind unidirektionale und können nicht über ein Netzwerk verwendet werden. Außerdem unterstützen Sie nur eine einzelne Serverinstanz. Anonyme Pipes eignen sich für die Kommunikation zwischen Threads oder zwischen über- und untergeordnete Prozesse, in denen die Pipehandles einfach an den untergeordneten Prozess übergeben werden können während der Erstellung.  
  
     In .NET Framework, implementieren Sie anonyme Pipes mithilfe der <xref:System.IO.Pipes.AnonymousPipeServerStream> und <xref:System.IO.Pipes.AnonymousPipeClientStream> Klassen.  
  
     Finden Sie unter [wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
-   Benannte Pipes.  
  
     Benannte Pipes stellen prozessübergreifende Kommunikation zwischen einem Pipeserver und einem oder mehreren Pipeclients bereit. Benannte Pipes können unidirektional oder bidirektional sein. Sie unterstützen die meldungsbasierte Kommunikation und Zulassen von mehreren Clients gleichzeitig an den Serverprozess mit dem gleichen Pipenamen zu verbinden. Benannte Pipes unterstützen zudem Identitätswechsel, durch den verbindende Prozessen die Verwendung ihrer eigenen Berechtigungen auf Remoteservern verwenden zu können.  
  
     In .NET Framework, implementieren Sie named Pipes mithilfe der <xref:System.IO.Pipes.NamedPipeServerStream> und <xref:System.IO.Pipes.NamedPipeClientStream> Klassen.  
  
     Finden Sie unter [wie: Verwenden von benannten Pipes zur prozessübergreifenden Netzwerkkommunikation](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datei- und Stream-E/A](../../../docs/standard/io/index.md)  
 [Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
