---
title: Suchen des minimalen Werts in einer numerischen Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
ms.openlocfilehash: 9b55c0a188f7e5857ddc5021c820be847ce63600
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358829"
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a><span data-ttu-id="78356-102">Suchen des minimalen Werts in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="78356-102">Find the Minimum Value in a Numeric Sequence</span></span>
<span data-ttu-id="78356-103">Verwenden Sie den <xref:System.Linq.Enumerable.Min%2A>-Operator, um den minimalen Wert einer Sequenz numerischer Werte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="78356-103">Use the <xref:System.Linq.Enumerable.Min%2A> operator to return the minimum value from a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78356-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="78356-104">Example</span></span>  
 <span data-ttu-id="78356-105">Im folgenden Beispiel wird der niedrigste Einzelpreis aller Produkte gesucht.</span><span class="sxs-lookup"><span data-stu-id="78356-105">The following example finds the lowest unit price of any product.</span></span>  
  
 <span data-ttu-id="78356-106">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lautet die Ausgabe `2.5000`.</span><span class="sxs-lookup"><span data-stu-id="78356-106">If you run this query against the Northwind sample database, the output is: `2.5000`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="78356-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="78356-107">Example</span></span>  
 <span data-ttu-id="78356-108">Im folgenden Beispiel wird die niedrigste Frachtmenge aller Bestellungen gesucht.</span><span class="sxs-lookup"><span data-stu-id="78356-108">The following example finds the lowest freight amount for any order.</span></span>  
  
 <span data-ttu-id="78356-109">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lautet die Ausgabe `0.0200`.</span><span class="sxs-lookup"><span data-stu-id="78356-109">If you run this query against the Northwind sample database, the output is: `0.0200`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="78356-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="78356-110">Example</span></span>  
 <span data-ttu-id="78356-111">Im folgenden Beispiel werden mit Min die `Products` (Produkte) ermittelt, die in jeder Kategorie den geringsten Einzelpreis aufweisen.</span><span class="sxs-lookup"><span data-stu-id="78356-111">The following example uses Min to find the `Products` that have the lowest unit price in each category.</span></span> <span data-ttu-id="78356-112">Die Ausgabe wird nach Kategorie sortiert.</span><span class="sxs-lookup"><span data-stu-id="78356-112">The output is arranged by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 <span data-ttu-id="78356-113">Wenn Sie die vorherige Abfrage mit der Beispieldatenbank Northwind ausführen, sehen die Ergebnisse wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="78356-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## <a name="see-also"></a><span data-ttu-id="78356-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78356-114">See Also</span></span>  
 [<span data-ttu-id="78356-115">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="78356-115">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="78356-116">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="78356-116">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
