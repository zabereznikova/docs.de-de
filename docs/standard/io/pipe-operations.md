---
title: "Pipeoperationen in .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Pipes [.NET Framework]"
  - "Pipeoperationen [.NET Framework]"
  - "Prozessübergreifende Kommunikation [.NET Framework], Pipes"
  - "E/A [.NET Framework], Pipes"
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Pipeoperationen in .NET Framework
Pipes stellen ein Mittel zur prozessübergreifenden Kommunikation bereit.  Es gibt zwei Arten von Pipes:  
  
-   Anonyme Pipes.  
  
     Anonyme Pipes stellen prozessübergreifende Kommunikation auf einem lokalen Computer bereit.  Anonyme Pipes erfordern weniger Mehraufwand als benannte Pipes, bieten jedoch eingeschränkte Dienste.  Anonyme Pipes sind unidirektional und können nicht in einem Netzwerk verwendet werden.  Sie unterstützen nur eine einzige Serverinstanz.  Anonyme Pipes erleichtern die Kommunikation zwischen Threads oder zwischen über\- und untergeordneten Prozessen, bei denen die Pipehandles mühelos an den untergeordneten Prozess übergeben werden können, wenn dieser erstellt wird.  
  
     In .NET Framework implementieren Sie anonyme Pipes, indem Sie die <xref:System.IO.Pipes.AnonymousPipeServerStream> und <xref:System.IO.Pipes.AnonymousPipeClientStream>\-Klassen verwenden.  
  
     Siehe [Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).  
  
-   Benannte Pipes.  
  
     Benannte Pipes stellen prozessübergreifende Kommunikation zwischen einem Pipeserver und einem oder mehreren Pipeclients bereit.  Benannte Pipes können unidirektional oder bidirektional sein.  Sie unterstützen die meldungsbasierte Kommunikation und ermöglichen unter Verwendung des gleichen Pipenamens die gleichzeitige Verbindung mehrerer Clients mit dem Serverprozess.  Benannte Pipes unterstützen zudem Identitätswechsel, die verbindenden Prozessen die Verwendung ihrer eigenen Berechtigungen auf Remoteservern ermöglichen.  
  
     In .NET Framework implementieren Sie benannte Pipes, indem Sie die <xref:System.IO.Pipes.NamedPipeServerStream> und <xref:System.IO.Pipes.NamedPipeClientStream>\-Klassen verwenden.  
  
     Siehe [Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).  
  
## Siehe auch  
 [Datei\- und Stream\-E\/A](../../../docs/standard/io/index.md)   
 [Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)   
 [Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)