---
title: 'Gewusst wie: Verwenden von Arrays mit blockierenden Sammlungen in einer Pipeline | Microsoft-Dokumentation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
caps.latest.revision: 8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 234dfa6a3a905b9db53ae8699bbe1c62f3411184
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
<a id="how-to-use-arrays-of-blocking-collections-in-a-pipeline" class="xliff"></a>

# Gewusst wie: Verwenden von Arrays mit blockierenden Sammlungen in einer Pipeline
Das folgende Beispiel zeigt die Verwendung von <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>-Objektarrays mit statischen Methoden wie <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> und <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, um eine schnelle und flexible Datenübertragung zwischen Komponenten zu implementieren.  
  
<a id="example" class="xliff"></a>

## Beispiel  
 Das folgende Beispiel veranschaulicht eine grundlegende Pipeline-Implementierung, in der alle Objekte gleichzeitig Daten aus der Eingabeauflistung entnehmen, sie transformieren und dann an die Ausgabeauflistung übergeben.  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)] [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
<a id="see-also" class="xliff"></a>

## Siehe auch  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [threadsichere Auflistungen](../../../../docs/standard/collections/thread-safe/index.md)
