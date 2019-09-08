---
title: Suchen des maximalen Werts in einer numerischen Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70d7c058-0280-4815-a008-6f290093591a
ms.openlocfilehash: ebef8cb373da4021fd68fd7ce38de8cb06eb81ec
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782175"
---
# <a name="find-the-maximum-value-in-a-numeric-sequence"></a><span data-ttu-id="08dbc-102">Suchen des maximalen Werts in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="08dbc-102">Find the Maximum Value in a Numeric Sequence</span></span>
<span data-ttu-id="08dbc-103">Verwenden Sie den <xref:System.Linq.Enumerable.Max%2A>-Operator, um den höchsten Wert in einer Sequenz numerischer Werte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="08dbc-103">Use the <xref:System.Linq.Enumerable.Max%2A> operator to find the highest value in a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08dbc-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08dbc-104">Example</span></span>  
 <span data-ttu-id="08dbc-105">Im folgenden Beispiel wird das letzte Datum des Arbeitsverhältnisses aller Mitarbeiter gesucht.</span><span class="sxs-lookup"><span data-stu-id="08dbc-105">The following example finds the latest date of hire for any employee.</span></span>  
  
 <span data-ttu-id="08dbc-106">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lautet die Ausgabe `11/15/1994 12:00:00 AM`.</span><span class="sxs-lookup"><span data-stu-id="08dbc-106">If you run this query against the sample Northwind database, the output is: `11/15/1994 12:00:00 AM`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#6)]
 [!code-vb[DLinqQueryExamples#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="08dbc-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08dbc-107">Example</span></span>  
 <span data-ttu-id="08dbc-108">Im folgenden Beispiel wird der höchste Lagerbestand für jedes Produkt gesucht.</span><span class="sxs-lookup"><span data-stu-id="08dbc-108">The following example finds the most units in stock for any product.</span></span>  
  
 <span data-ttu-id="08dbc-109">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lautet die Ausgabe `125`.</span><span class="sxs-lookup"><span data-stu-id="08dbc-109">If you run this example against the sample Northwind database, the output is: `125`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#7)]
 [!code-vb[DLinqQueryExamples#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#7)]  
  
## <a name="example"></a><span data-ttu-id="08dbc-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08dbc-110">Example</span></span>  
 <span data-ttu-id="08dbc-111">Im folgenden Beispiel werden mit Max die `Products` (Produkte) ermittelt, die in jeder Kategorie den höchsten Einzelpreis aufweisen.</span><span class="sxs-lookup"><span data-stu-id="08dbc-111">The following example uses Max to find the `Products` that have the highest unit price in each category.</span></span> <span data-ttu-id="08dbc-112">Die Ausgabe führt dann die Ergebnisse nach Kategorie auf.</span><span class="sxs-lookup"><span data-stu-id="08dbc-112">The output then lists the results by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#8)]
 [!code-vb[DLinqQueryExamples#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#8)]  
  
 <span data-ttu-id="08dbc-113">Wenn Sie die vorherige Abfrage mit der Beispieldatenbank Northwind ausführen, sehen die Ergebnisse wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="08dbc-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `2`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `4`  
  
 `Raclette Courdavault`  
  
 `5`  
  
 `Gnocchi di nonna Alice`  
  
 `6`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Carnarvon Tigers`  
  
## <a name="see-also"></a><span data-ttu-id="08dbc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08dbc-114">See also</span></span>

- [<span data-ttu-id="08dbc-115">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="08dbc-115">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="08dbc-116">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="08dbc-116">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
