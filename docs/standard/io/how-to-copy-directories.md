---
title: "Gewusst wie: Kopieren von Verzeichnissen | Microsoft Docs"
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
  - "Kopieren von Verzeichnissen"
  - "Verzeichnisse [.NET Framework], Kopieren"
  - "Kopieren eines Verzeichnisses"
  - "E/A [.NET Framework], Kopieren von Verzeichnissen"
  - "Kopieren eines Unterverzeichnisses"
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Kopieren von Verzeichnissen
Dieses Beispiel zeigt, wie E\/A\-Klassen zum synchronen Kopieren der Inhalte eines Verzeichnisses an einen anderen Speicherort verwendet werden. In diesem Beispiel kann der Benutzer angeben, ob auch die Unterverzeichnisse kopiert werden sollen. Wenn dies der Fall ist, werden die Unterverzeichnisse von der Methode in diesem Beispiel rekursiv kopiert, indem sie sich selbst so lange für jedes weitere Unterverzeichnis aufruft, bis alle kopiert wurden.  
  
 Ein Beispiel zum asynchronen Kopieren von Dateien finden Sie unter [Asynchrone Datei\-E\/A](../../../docs/standard/io/asynchrone-datei-e-a.md).  
  
## Beispiel  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## Siehe auch  
 <xref:System.IO.FileInfo>   
 <xref:System.IO.DirectoryInfo>   
 <xref:System.IO.FileStream>   
 [Datei\- und Stream\-E\/A](../../../docs/standard/io/index.md)   
 [Allgemeine E\/A\-Aufgaben](../../../docs/standard/io/commons-tasks.md)   
 [Asynchrone Datei\-E\/A](../../../docs/standard/io/asynchrone-datei-e-a.md)