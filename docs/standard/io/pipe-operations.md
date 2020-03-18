---
title: Pipevorgänge in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: 693dd1eb0b0b9bb87973eead26a344ed67641e34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75706555"
---
# <a name="pipe-operations-in-net"></a>Pipevorgänge in .NET
Pipes stellen eine Möglichkeit zur prozessübergreifenden Kommunikation dar. Es gibt zwei Arten von Pipes:  
  
- Anonyme Pipes.  
  
     Anonyme Pipes stellen prozessübergreifende Kommunikation auf einem lokalen Computer bereit. Anonyme Pipes erfordern weniger Mehraufwand als benannte Pipes, bieten jedoch nur begrenzte Dienste. Anonyme Pipes sind unidirektional und können nicht über ein Netzwerk verwendet werden. Sie unterstützen nur eine einzelne Serverinstanz. Anonyme Pipes eignen sich für die Kommunikation zwischen Threads oder über- und untergeordneten Prozessen, wobei die Pipehandles einfach an den untergeordneten Prozess übergeben werden können, wenn er erstellt wird.  
  
     In .NET implementieren Sie anonyme Pipes mithilfe der <xref:System.IO.Pipes.AnonymousPipeServerStream>- und <xref:System.IO.Pipes.AnonymousPipeClientStream>-Klasse.  
  
     Siehe [Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
- Benannte Pipes.  
  
     Benannte Pipes stellen prozessübergreifende Kommunikation zwischen einem Pipeserver und einem oder mehreren Pipeclients bereit. Benannte Pipes können unidirektional oder bidirektional sein. Sie unterstützen die meldungsbasierte Kommunikation und erlauben mehreren Clients, gleichzeitig mit dem gleichen Pipenamen eine Verbindung mit dem Serverprozess herzustellen. Benannte Pipes unterstützen zudem Identitätswechsel, sodass Verbindungen mit Prozessen hergestellt werden können, um ihre eigenen Berechtigungen auf Remoteservern zu verwenden.  
  
     In .NET implementieren Sie benannte Pipes mithilfe der <xref:System.IO.Pipes.NamedPipeServerStream>- und <xref:System.IO.Pipes.NamedPipeClientStream>-Klasse.  
  
     Siehe [Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
- [Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
