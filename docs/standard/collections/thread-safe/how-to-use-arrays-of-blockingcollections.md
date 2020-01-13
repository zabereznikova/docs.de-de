---
title: 'Vorgehensweise: Verwenden von Arrays mit BlockingCollections in einer Pipeline'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
ms.openlocfilehash: 397c438bacd1cfed1613efef61e9d7266d55ea47
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711258"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a><span data-ttu-id="64858-102">Vorgehensweise: Verwenden von Arrays mit BlockingCollections in einer Pipeline</span><span class="sxs-lookup"><span data-stu-id="64858-102">How to: Use Arrays of Blocking Collections in a Pipeline</span></span>
<span data-ttu-id="64858-103">Das folgende Beispiel zeigt die Verwendung von <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>-Objektarrays mit statischen Methoden wie <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> und <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, um eine schnelle und flexible Datenübertragung zwischen Komponenten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="64858-103">The following example shows how to use arrays of <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> objects with static methods such as <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> and <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> to implement fast and flexible data transfer between components.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64858-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64858-104">Example</span></span>  
 <span data-ttu-id="64858-105">Das folgende Beispiel veranschaulicht eine grundlegende Pipeline-Implementierung, in der alle Objekte gleichzeitig Daten aus der Eingabeauflistung entnehmen, sie transformieren und dann an die Ausgabeauflistung übergeben.</span><span class="sxs-lookup"><span data-stu-id="64858-105">The following example demonstrates a basic pipeline implementation in which each object is concurrently taking data from the input collection, transforming it, and passing it to the output collection.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a><span data-ttu-id="64858-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64858-106">See also</span></span>

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [<span data-ttu-id="64858-107">Threadsichere Sammlungen</span><span class="sxs-lookup"><span data-stu-id="64858-107">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
