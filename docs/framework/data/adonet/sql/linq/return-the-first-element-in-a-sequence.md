---
title: Zurückgeben des ersten Elements in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: 4506ef1a79c8f7e77160df4d55d0f93ee79f5a41
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200341"
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="8c1bd-102">Zurückgeben des ersten Elements in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="8c1bd-102">Return the First Element in a Sequence</span></span>

<span data-ttu-id="8c1bd-103">Verwenden Sie den <xref:System.Linq.Enumerable.First%2A>-Operator, um das erste Element in einer Sequenz zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="8c1bd-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="8c1bd-104">Abfragen, die <xref:System.Linq.Enumerable.First%2A> verwenden, werden sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8c1bd-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="8c1bd-105">unterstützt den <xref:System.Linq.Enumerable.Last%2A>-Operator nicht.</span><span class="sxs-lookup"><span data-stu-id="8c1bd-105">does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c1bd-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c1bd-106">Example</span></span>  

 <span data-ttu-id="8c1bd-107">Im folgenden Code wird der erste `Shipper` (Spediteur) in einer Tabelle gesucht:</span><span class="sxs-lookup"><span data-stu-id="8c1bd-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="8c1bd-108">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lauten die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="8c1bd-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="8c1bd-109">`ID = 1, Company = Speedy Express`.</span><span class="sxs-lookup"><span data-stu-id="8c1bd-109">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="8c1bd-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c1bd-110">Example</span></span>  

 <span data-ttu-id="8c1bd-111">Der folgende Code ermittelt den einzigen `Customer` (Kunden) mit `CustomerID`-BONAP.</span><span class="sxs-lookup"><span data-stu-id="8c1bd-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="8c1bd-112">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lauten die Ergebnisse `ID = BONAP, Contact = Laurence Lebihan`.</span><span class="sxs-lookup"><span data-stu-id="8c1bd-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="8c1bd-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c1bd-113">See also</span></span>

- [<span data-ttu-id="8c1bd-114">Abfrage Beispiele</span><span class="sxs-lookup"><span data-stu-id="8c1bd-114">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="8c1bd-115">Herunterladen von Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="8c1bd-115">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
