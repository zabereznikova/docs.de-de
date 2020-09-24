---
title: Zählen der Anzahl von Elementen in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: d983bc14f4fda04bda0a6f363db4c11f062c4c48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164349"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="e43f9-102">Zählen der Anzahl von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="e43f9-102">Count the Number of Elements in a Sequence</span></span>

<span data-ttu-id="e43f9-103">Verwenden Sie den <xref:System.Linq.Enumerable.Count%2A>-Operator, um die Anzahl von Elementen in einer Sequenz zu zählen.</span><span class="sxs-lookup"><span data-stu-id="e43f9-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="e43f9-104">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, wird eine Ausgabe von `91` erzeugt.</span><span class="sxs-lookup"><span data-stu-id="e43f9-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e43f9-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e43f9-105">Example</span></span>  

 <span data-ttu-id="e43f9-106">Im folgenden Beispiel wird die Anzahl von `Customers` (Kunden) in der Datenbank gezählt.</span><span class="sxs-lookup"><span data-stu-id="e43f9-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="e43f9-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e43f9-107">Example</span></span>  

 <span data-ttu-id="e43f9-108">Im folgenden Beispiel wird die Anzahl von Produkten in der Datenbank gezählt, die nicht eingestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e43f9-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="e43f9-109">Wenn Sie dieses Beispiel mit der Beispieldatenbank Northwind ausführen, wird eine Ausgabe von `69` erzeugt.</span><span class="sxs-lookup"><span data-stu-id="e43f9-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e43f9-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e43f9-110">See also</span></span>

- [<span data-ttu-id="e43f9-111">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="e43f9-111">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="e43f9-112">Herunterladen von Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="e43f9-112">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
