---
title: 'Gewusst wie: Erstellen eines Objektpools mittels ConcurrentBag'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bc0c6bebbab6e84c165f41300a4cb16c8746a07
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2018
ms.locfileid: "47202666"
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="cb589-102">Gewusst wie: Erstellen eines Objektpools mittels ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="cb589-102">How to: Create an Object Pool by Using a ConcurrentBag</span></span>
<span data-ttu-id="cb589-103">Dieses Beispiel zeigt, wie Sie einen parallelen Behälter verwenden, um einen Objektpool zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="cb589-103">This example shows how to use a concurrent bag to implement an object pool.</span></span> <span data-ttu-id="cb589-104">Objektpools können die Anwendungsleistung in Situationen verbessern, in denen Sie mehrere Instanzen einer Klasse benötigen und es teuer ist, die Klasse zu erstellen oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="cb589-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="cb589-105">Wenn ein Clientprogramm ein neues Objekt benötigt, versucht der Objektpool zunächst, ein Objekt bereitzustellen, das bereits erstellt und an den Pool zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cb589-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="cb589-106">Nur wenn kein Objekt verfügbar ist, wird ein neues erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb589-106">If none is available, only then is a new object created.</span></span>  
  
 <span data-ttu-id="cb589-107">Zum Speichern der Objekte wird ein <xref:System.Collections.Concurrent.ConcurrentBag%601>-Objekt verwendet, da es ein schnelles Einfügen und Entfernen unterstützt, besonders dann, wenn der gleiche Thread Elemente hinzufügt und entfernt.</span><span class="sxs-lookup"><span data-stu-id="cb589-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="cb589-108">Dieses Beispiel kann noch bereitgestellt werden, um es auf eine <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> aufzubauen, die von der Behälterdatenstruktur implementiert wird, so wie <xref:System.Collections.Concurrent.ConcurrentQueue%601> und <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="cb589-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb589-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb589-109">Example</span></span>  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="cb589-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb589-110">See also</span></span>

- [<span data-ttu-id="cb589-111">Threadsichere Sammlungen</span><span class="sxs-lookup"><span data-stu-id="cb589-111">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
