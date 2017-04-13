---
title: "Gewusst wie: Erstellen eines Objektpools mittels ConcurrentBag | Microsoft Docs"
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
  - "Objektpool, in .NET Framework"
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Erstellen eines Objektpools mittels ConcurrentBag
Dieses Beispiel zeigt, wie Sie mit einer parallelen Sammlung einen Objektpool implementieren können.  Objektpools können die Anwendungsleistung in Situationen verbessern, in denen mehrere Instanzen einer Klasse benötigt werden und das Erstellen und Zerstören der Klasse aufwändig ist.  Wenn ein Clientprogramm ein neues Objekt anfordert, versucht der Objektpool zunächst, ein bereits erstelltes und an den Pool zurückgegebenes Objekt bereitzustellen.  Nur wenn kein Objekt verfügbar ist, wird ein neues erstellt.  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601> wird verwendet, um die Objekte zu speichern, da es ein schnelles Einfügen und Entfernen ermöglicht, insbesondere wenn Elemente vom selben Thread hinzugefügt und entfernt werden.  Dieses Beispiel könnte erweitert werden, um eine <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> zu erstellen, die von der Sammlungsdatenstruktur implementiert wird, wie z. B. bei <xref:System.Collections.Concurrent.ConcurrentQueue%601> und <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
## Beispiel  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## Siehe auch  
 [Threadsichere Auflistungen](../../../../docs/standard/collections/thread-safe/index.md)