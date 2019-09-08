---
title: Suchen des minimalen Werts in einer numerischen Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
ms.openlocfilehash: d8aee43f13ec92f649b4df20505ac56c336fe07a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793833"
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a><span data-ttu-id="8547a-102">Suchen des minimalen Werts in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="8547a-102">Find the Minimum Value in a Numeric Sequence</span></span>
<span data-ttu-id="8547a-103">Verwenden Sie den <xref:System.Linq.Enumerable.Min%2A>-Operator, um den minimalen Wert einer Sequenz numerischer Werte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="8547a-103">Use the <xref:System.Linq.Enumerable.Min%2A> operator to return the minimum value from a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8547a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8547a-104">Example</span></span>  
 <span data-ttu-id="8547a-105">Im folgenden Beispiel wird der niedrigste Einzelpreis aller Produkte gesucht.</span><span class="sxs-lookup"><span data-stu-id="8547a-105">The following example finds the lowest unit price of any product.</span></span>  
  
 <span data-ttu-id="8547a-106">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lautet die Ausgabe `2.5000`.</span><span class="sxs-lookup"><span data-stu-id="8547a-106">If you run this query against the Northwind sample database, the output is: `2.5000`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="8547a-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8547a-107">Example</span></span>  
 <span data-ttu-id="8547a-108">Im folgenden Beispiel wird die niedrigste Frachtmenge aller Bestellungen gesucht.</span><span class="sxs-lookup"><span data-stu-id="8547a-108">The following example finds the lowest freight amount for any order.</span></span>  
  
 <span data-ttu-id="8547a-109">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lautet die Ausgabe `0.0200`.</span><span class="sxs-lookup"><span data-stu-id="8547a-109">If you run this query against the Northwind sample database, the output is: `0.0200`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="8547a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8547a-110">Example</span></span>  
 <span data-ttu-id="8547a-111">Im folgenden Beispiel werden mit Min die `Products` (Produkte) ermittelt, die in jeder Kategorie den geringsten Einzelpreis aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8547a-111">The following example uses Min to find the `Products` that have the lowest unit price in each category.</span></span> <span data-ttu-id="8547a-112">Die Ausgabe wird nach Kategorie sortiert.</span><span class="sxs-lookup"><span data-stu-id="8547a-112">The output is arranged by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 <span data-ttu-id="8547a-113">Wenn Sie die vorherige Abfrage mit der Beispieldatenbank Northwind ausführen, sehen die Ergebnisse wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="8547a-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8547a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8547a-114">See also</span></span>

- [<span data-ttu-id="8547a-115">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="8547a-115">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="8547a-116">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="8547a-116">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
