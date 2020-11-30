---
title: 'Gewusst wie: Verwenden von Arrays mit blockierenden Sammlungen in einer Pipeline'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
ms.openlocfilehash: 55dc3e9934efa153c61322f63b7dde8077442fd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733463"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a><span data-ttu-id="a1ccd-102">Gewusst wie: Verwenden von Arrays mit blockierenden Sammlungen in einer Pipeline</span><span class="sxs-lookup"><span data-stu-id="a1ccd-102">How to: Use Arrays of Blocking Collections in a Pipeline</span></span>

<span data-ttu-id="a1ccd-103">Das folgende Beispiel zeigt die Verwendung von <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>-Objektarrays mit statischen Methoden wie <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> und <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, um eine schnelle und flexible Datenübertragung zwischen Komponenten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-103">The following example shows how to use arrays of <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> objects with static methods such as <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> to implement fast and flexible data transfer between components.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1ccd-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1ccd-104">Example</span></span>  

 <span data-ttu-id="a1ccd-105">Das folgende Beispiel veranschaulicht eine grundlegende Pipeline-Implementierung, in der alle Objekte gleichzeitig Daten aus der Eingabeauflistung entnehmen, sie transformieren und dann an die Ausgabeauflistung übergeben.</span><span class="sxs-lookup"><span data-stu-id="a1ccd-105">The following example demonstrates a basic pipeline implementation in which each object is concurrently taking data from the input collection, transforming it, and passing it to the output collection.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a><span data-ttu-id="a1ccd-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1ccd-106">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="a1ccd-107">Threadsichere Sammlungen</span><span class="sxs-lookup"><span data-stu-id="a1ccd-107">Thread-Safe Collections</span></span>](index.md)
