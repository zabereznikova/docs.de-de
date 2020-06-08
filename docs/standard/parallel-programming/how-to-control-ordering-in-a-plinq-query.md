---
title: 'Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
ms.openlocfilehash: 80e199d75471eba219f1f3da12d307b6cd1d90cf
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84285455"
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a><span data-ttu-id="26677-102">Gewusst wie: Steuern der Sortierung in einer PLINQ-Abfrage</span><span class="sxs-lookup"><span data-stu-id="26677-102">How to: Control Ordering in a PLINQ Query</span></span>
<span data-ttu-id="26677-103">Diese Beispiele zeigen die Steuerung der Reihenfolge in einer PLINQ-Abfrage mithilfe der <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>-Erweiterungsmethode.</span><span class="sxs-lookup"><span data-stu-id="26677-103">These examples show how to control the ordering in a PLINQ query by using the <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> extension method.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="26677-104">Diese Beispiele sollen primär die Nutzung darstellen und werden möglicherweise nicht schneller ausgeführt als die entsprechenden sequenziellen LINQ to Objects-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="26677-104">These examples are primarily intended to demonstrate usage, and may or may not run faster than the equivalent sequential LINQ to Objects queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26677-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26677-105">Example</span></span>  
 <span data-ttu-id="26677-106">Im folgenden Beispiel wird die Reihenfolge der Quellsequenz beibehalten.</span><span class="sxs-lookup"><span data-stu-id="26677-106">The following example preserves the ordering of the source sequence.</span></span> <span data-ttu-id="26677-107">Dies ist manchmal notwendig. Beispielsweise erfordern einige Abfrageoperatoren eine geordnete Quellsequenz, um richtige Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="26677-107">This is sometimes necessary; for example some query operators require an ordered source sequence to produce correct results.</span></span>  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="26677-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26677-108">Example</span></span>  
 <span data-ttu-id="26677-109">Das folgende Beispiel zeigt einige Abfrageoperatoren, bei denen wahrscheinlich eine sortierte Quellsequenz zu erwarten ist.</span><span class="sxs-lookup"><span data-stu-id="26677-109">The following example shows some query operators whose source sequence is probably expected to be ordered.</span></span> <span data-ttu-id="26677-110">Diese Operatoren funktionieren bei ungeordneten Sequenzen, aber sie können zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="26677-110">These operators will work on unordered sequences, but they might produce unexpected results.</span></span>  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 <span data-ttu-id="26677-111">Um diese Methode auszuführen, fügen Sie sie im [PLINQ-Datenbeispiel](plinq-data-sample.md)-Projekt in die PLINQDataSample-Klasse ein, und drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="26677-111">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26677-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26677-112">Example</span></span>  
 <span data-ttu-id="26677-113">Im folgenden Beispiel werden das Beibehalten der Reihenfolge für den ersten Teil einer Abfrage, dann das Entfernen der Reihenfolge zur Steigerung der Leistung einer Join-Klausel sowie das erneute Anwenden der Reihenfolge für die endgültige Ergebnissequenz gezeigt.</span><span class="sxs-lookup"><span data-stu-id="26677-113">The following example shows how to preserve ordering for the first part of a query, then remove the ordering to increase the performance of a join clause, and then reapply ordering to the final result sequence.</span></span>  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 <span data-ttu-id="26677-114">Um diese Methode auszuführen, fügen Sie sie im [PLINQ-Datenbeispiel](plinq-data-sample.md)-Projekt in die PLINQDataSample-Klasse ein, und drücken Sie F5.</span><span class="sxs-lookup"><span data-stu-id="26677-114">To run this method, paste it into the PLINQDataSample class in the [PLINQ Data Sample](plinq-data-sample.md) project and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26677-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26677-115">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="26677-116">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="26677-116">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
