---
title: "Gewusst wie: Verwenden von Arrays mit blockierenden Auflistungen in einer Pipeline | Microsoft Docs"
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
  - "threadsichere Auflistungen, blockierende Auflistungen in Pipeline"
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Verwenden von Arrays mit blockierenden Auflistungen in einer Pipeline
Das folgende Beispiel zeigt, wie Arrays von <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>\-Objekten mit statischen Methoden wie <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> und <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> zu verwenden sind, um schnelle und flexible Datenübertragung zwischen Komponenten zu implementieren.  
  
## Beispiel  
 Im folgenden Beispiel wird eine grundlegende Pipelineimplementierung veranschaulicht, in der jedes Objekt gleichzeitig Daten von der Eingabeauflistung übernimmt, diese transformiert und an die Ausgabeauflistung übergibt.  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Threadsichere Auflistungen](../../../../docs/standard/collections/thread-safe/index.md)