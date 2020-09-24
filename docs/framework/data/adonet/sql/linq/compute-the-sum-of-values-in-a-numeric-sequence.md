---
title: Berechnen der Summe von Werten in einer numerischen Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
ms.openlocfilehash: 3d160e2cce5f3e0a7eea305657260b6fa4ded7fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164440"
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a><span data-ttu-id="717f8-102">Berechnen der Summe von Werten in einer numerischen Sequenz</span><span class="sxs-lookup"><span data-stu-id="717f8-102">Compute the Sum of Values in a Numeric Sequence</span></span>

<span data-ttu-id="717f8-103">Verwenden Sie den <xref:System.Linq.Enumerable.Sum%2A>-Operator, um die Summe numerischer Werte in einer Sequenz zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="717f8-103">Use the <xref:System.Linq.Enumerable.Sum%2A> operator to compute the sum of numeric values in a sequence.</span></span>  
  
 <span data-ttu-id="717f8-104">Beachten Sie die folgenden Merkmale des `Sum`-Operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="717f8-104">Note the following characteristics of the `Sum` operator in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="717f8-105">Der `Sum`-Operator für Standardabfragen führt bei einer leeren Sequenz oder bei einer aus Nullen bestehenden Sequenz zum Ergebnis NULL.</span><span class="sxs-lookup"><span data-stu-id="717f8-105">The Standard Query Operator aggregate operator `Sum` evaluates to zero for an empty sequence or a sequence that contains only nulls.</span></span> <span data-ttu-id="717f8-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bleibt die SQL-Semantik unverändert.</span><span class="sxs-lookup"><span data-stu-id="717f8-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged.</span></span> <span data-ttu-id="717f8-107">Aus diesem Grund ergibt `Sum` bei einer leeren Sequenz oder bei einer aus Nullen bestehenden Sequenz den Wert NULL an Stelle von 0.</span><span class="sxs-lookup"><span data-stu-id="717f8-107">For this reason, `Sum` evaluates to null instead of to zero for an empty sequence or for a sequence that contains only nulls.</span></span>  
  
- <span data-ttu-id="717f8-108">SQL-Einschränkungen für Zwischenergebnisse gelten in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] für Summen.</span><span class="sxs-lookup"><span data-stu-id="717f8-108">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="717f8-109">Die Summe von ganzzahligen 32-Bit-Mengen wird nicht mit 64-Bit-Ergebnissen berechnet, und ein Überlauf kann für die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Übersetzung von auftreten `Sum` .</span><span class="sxs-lookup"><span data-stu-id="717f8-109">Sum of 32-bit integer quantities is not computed by using 64-bit results, and overflow can occur for the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of `Sum`.</span></span> <span data-ttu-id="717f8-110">Dies kann ggf. auch eintreten, wenn die standardmäßige Implementierung des Abfrageoperators bei der entsprechenden Sequenz im Arbeitsspeicher nicht zu einem Überlauf führt.</span><span class="sxs-lookup"><span data-stu-id="717f8-110">This possibility exists even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="717f8-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="717f8-111">Example</span></span>  

 <span data-ttu-id="717f8-112">Im folgenden Beispiel wird die gesamte Fracht zu allen Bestellungen in der Tabelle `Order` ermittelt.</span><span class="sxs-lookup"><span data-stu-id="717f8-112">The following example finds the total freight of all orders in the `Order` table.</span></span>  
  
 <span data-ttu-id="717f8-113">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lautet die Ausgabe `64942.6900`.</span><span class="sxs-lookup"><span data-stu-id="717f8-113">If you run this query against the Northwind sample database, the output is: `64942.6900`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="717f8-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="717f8-114">Example</span></span>  

 <span data-ttu-id="717f8-115">Im folgenden Beispiel wird die Gesamtzahl von bestellen Einheiten für alle Produkte ermittelt.</span><span class="sxs-lookup"><span data-stu-id="717f8-115">The following example finds the total number of units on order for all products.</span></span>  
  
 <span data-ttu-id="717f8-116">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, lautet die Ausgabe `780`.</span><span class="sxs-lookup"><span data-stu-id="717f8-116">If you run this query against the Northwind sample database, the output is: `780`.</span></span>  
  
 <span data-ttu-id="717f8-117">Beachten Sie, dass Sie `short`-Typen (z. B. `UnitsOnOrder`) verwenden müssen, da `Sum` nicht über einen Überlauf für diese Typen verfügt.</span><span class="sxs-lookup"><span data-stu-id="717f8-117">Note that you must cast `short` types (for example, `UnitsOnOrder`) because `Sum` has no overload for short types.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="717f8-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="717f8-118">See also</span></span>

- [<span data-ttu-id="717f8-119">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="717f8-119">Aggregate Queries</span></span>](aggregate-queries.md)
- [<span data-ttu-id="717f8-120">Herunterladen von Beispieldatenbanken</span><span class="sxs-lookup"><span data-stu-id="717f8-120">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
