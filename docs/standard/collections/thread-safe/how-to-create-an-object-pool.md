---
title: Erstellen eines Objektpools mittels ConcurrentBag
ms.date: 05/01/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
ms.openlocfilehash: 64d91162b27eba80fba63761d0a926e441b63440
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287860"
---
# <a name="create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="1fcf4-102">Erstellen eines Objektpools mittels ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="1fcf4-102">Create an object pool by using a ConcurrentBag</span></span>

<span data-ttu-id="1fcf4-103">Dieses Beispiel zeigt, wie Sie einen <xref:System.Collections.Concurrent.ConcurrentBag%601> verwenden, um einen Objektpool zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="1fcf4-103">This example shows how to use a <xref:System.Collections.Concurrent.ConcurrentBag%601> to implement an object pool.</span></span> <span data-ttu-id="1fcf4-104">Objektpools können die Anwendungsleistung in Situationen verbessern, in denen Sie mehrere Instanzen einer Klasse benötigen und es teuer ist, die Klasse zu erstellen oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="1fcf4-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="1fcf4-105">Wenn ein Clientprogramm ein neues Objekt benötigt, versucht der Objektpool zunächst, ein Objekt bereitzustellen, das bereits erstellt und an den Pool zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1fcf4-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="1fcf4-106">Nur wenn kein Objekt verfügbar ist, wird ein neues erstellt.</span><span class="sxs-lookup"><span data-stu-id="1fcf4-106">If none is available, only then is a new object created.</span></span>

<span data-ttu-id="1fcf4-107">Zum Speichern der Objekte wird ein <xref:System.Collections.Concurrent.ConcurrentBag%601>-Objekt verwendet, da es ein schnelles Einfügen und Entfernen unterstützt, besonders dann, wenn der gleiche Thread Elemente hinzufügt und entfernt.</span><span class="sxs-lookup"><span data-stu-id="1fcf4-107">The <xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="1fcf4-108">Dieses Beispiel kann noch bereitgestellt werden, um es auf eine <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> aufzubauen, die von der Behälterdatenstruktur implementiert wird, so wie <xref:System.Collections.Concurrent.ConcurrentQueue%601> und <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="1fcf4-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>

> [!TIP]
> <span data-ttu-id="1fcf4-109">In diesem Artikel wird beschrieben, wie Sie Ihre eigene Implementierung eines Objektpools mit einem zugrunde liegenden gleichzeitigen Typ („concurrent“) schreiben, um Objekte zur Wiederverwendung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1fcf4-109">This article defines how to write your own implementation of an object pool with an underlying concurrent type to store objects for reuse.</span></span> <span data-ttu-id="1fcf4-110">Der Typ <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> ist jedoch bereits unter dem Namespace <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1fcf4-110">However, the <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> type already exists under the <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="1fcf4-111">Sie sollten den verfügbaren Typ verwenden, bevor Sie eine eigene Implementierung erstellen, die viele zusätzliche Features umfasst.</span><span class="sxs-lookup"><span data-stu-id="1fcf4-111">Consider using the available type before creating your own implementation, which includes many additional features.</span></span>

## <a name="example"></a><span data-ttu-id="1fcf4-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1fcf4-112">Example</span></span>

[!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
[!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]

## <a name="see-also"></a><span data-ttu-id="1fcf4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fcf4-113">See also</span></span>

- [<span data-ttu-id="1fcf4-114">Threadsichere Sammlungen</span><span class="sxs-lookup"><span data-stu-id="1fcf4-114">Thread-Safe Collections</span></span>](index.md)
