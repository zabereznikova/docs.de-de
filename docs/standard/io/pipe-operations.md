---
title: Pipevorgänge in .NET
description: 'In diesem Artikel werden Pipevorgänge in .NET erläutert. Pipes stellen eine Möglichkeit zur prozessübergreifenden Kommunikation dar. Es gibt zwei Arten von Pipes: anonyme sowie benannte Pipes.'
ms.date: 03/30/2017
helpviewer_keywords:
- pipes [.NET]
- pipe operations [.NET]
- interprocess communication [.NET], pipes
- I/O [.NET], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: bb8804c32b9f2b54b05298779bddae117c10dcf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734802"
---
# <a name="pipe-operations-in-net"></a>Pipevorgänge in .NET

Pipes stellen eine Möglichkeit zur prozessübergreifenden Kommunikation dar. Es gibt zwei Arten von Pipes:  
  
- Anonyme Pipes.  
  
     Anonyme Pipes stellen prozessübergreifende Kommunikation auf einem lokalen Computer bereit. Anonyme Pipes erfordern weniger Mehraufwand als benannte Pipes, bieten jedoch nur begrenzte Dienste. Anonyme Pipes sind unidirektional und können nicht über ein Netzwerk verwendet werden. Sie unterstützen nur eine einzelne Serverinstanz. Anonyme Pipes eignen sich für die Kommunikation zwischen Threads oder über- und untergeordneten Prozessen, wobei die Pipehandles einfach an den untergeordneten Prozess übergeben werden können, wenn er erstellt wird.  
  
     In .NET implementieren Sie anonyme Pipes mithilfe der <xref:System.IO.Pipes.AnonymousPipeServerStream>- und <xref:System.IO.Pipes.AnonymousPipeClientStream>-Klasse.  
  
     Weitere Informationen finden Sie unter [How to: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
- Benannte Pipes.  
  
     Benannte Pipes stellen prozessübergreifende Kommunikation zwischen einem Pipeserver und einem oder mehreren Pipeclients bereit. Benannte Pipes können unidirektional oder bidirektional sein. Sie unterstützen die meldungsbasierte Kommunikation und erlauben mehreren Clients, gleichzeitig mit dem gleichen Pipenamen eine Verbindung mit dem Serverprozess herzustellen. Benannte Pipes unterstützen zudem Identitätswechsel, sodass Verbindungen mit Prozessen hergestellt werden können, um ihre eigenen Berechtigungen auf Remoteservern zu verwenden.  
  
     In .NET implementieren Sie benannte Pipes mithilfe der <xref:System.IO.Pipes.NamedPipeServerStream>- und <xref:System.IO.Pipes.NamedPipeClientStream>-Klasse.  
  
     Weitere Informationen finden Sie unter [How to: Verwenden von Named Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk](how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datei- und Stream-E/A](index.md)
- [How to: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [How to: Verwenden von Named Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk](how-to-use-named-pipes-for-network-interprocess-communication.md)
