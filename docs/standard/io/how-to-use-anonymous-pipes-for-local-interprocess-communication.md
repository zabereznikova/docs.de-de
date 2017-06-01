---
title: "Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozess&#252;bergreifenden Kommunikation | Microsoft Docs"
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
  - "Anonyme Pipes [.NET Framework]"
  - "Kommunikation auf lokalem Computer [.NET Framework], Pipes"
  - "Unidirektionale Kommunikation [.NET Framework]"
  - "Kommunikation zwischen über- und untergeordneten Elementen [.NET Framework]"
  - "Pipes [.NET Framework]"
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozess&#252;bergreifenden Kommunikation
Anonyme Pipes stellen prozessübergreifende Kommunikation auf einem lokalen Computer bereit.  Sie bieten zwar weniger Funktionen als benannte Pipes, erfordern aber auch weniger Mehraufwand.  Sie können anonyme Pipes verwenden, um die prozessübergreifende Kommunikation auf einem lokalen Computer zu vereinfachen.  Anonyme Pipes können nicht zur Kommunikation über ein Netzwerk verwendet werden.  
  
 Um anonyme Pipes zu implementieren, verwenden Sie die <xref:System.IO.Pipes.AnonymousPipeServerStream>\- und <xref:System.IO.Pipes.AnonymousPipeClientStream>\-Klassen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine Zeichenfolge mithilfe von anonymen Pipes von einem übergeordneten Prozess an einen untergeordneten Prozess gesendet werden kann.  In diesem Beispiel wird ein <xref:System.IO.Pipes.AnonymousPipeServerStream>\-Objekt in einem übergeordneten Prozess mit dem <xref:System.IO.Pipes.PipeDirection>\-Wert <xref:System.IO.Pipes.PipeDirection> erstellt.  Anschließend wird vom übergeordneten Prozess ein untergeordneter Prozess erstellt, indem ein Clienthandle zur Erstellung eines <xref:System.IO.Pipes.AnonymousPipeClientStream>\-Objekts verwendet wird.  Der untergeordnete Prozess hat den <xref:System.IO.Pipes.PipeDirection>\-Wert <xref:System.IO.Pipes.PipeDirection>.  
  
 Der übergeordnete Prozess sendet daraufhin eine vom Benutzer bereitgestellte Zeichenfolge an den untergeordneten Prozess.  Die Zeichenfolge wird im untergeordneten Prozess auf der Konsole angezeigt.  
  
 Das folgende Codebeispiel zeigt den Serverprozess:  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  
  
## Beispiel  
 Das folgende Codebeispiel zeigt den Clientprozess:  Der Serverprozess startet den Clientprozess und übergibt ein Clienthandle an diesen Prozess.  Die resultierende ausführbare Datei aus dem Clientcode sollte `pipeClient.exe` genannt und in dasselbe Verzeichnis kopiert werden wie die ausführbare Datei des Servers, bevor der Serverprozess ausgeführt wird.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## Siehe auch  
 [Pipes](../../../docs/standard/io/pipe-operations.md)   
 [Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)