---
title: Zählen der Anzahl von Elementen in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 928cfd33a187637c6d18da3cccefb22bb2950acf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353833"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="60e3c-102">Zählen der Anzahl von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="60e3c-102">Count the Number of Elements in a Sequence</span></span>
<span data-ttu-id="60e3c-103">Verwenden Sie den <xref:System.Linq.Enumerable.Count%2A>-Operator, um die Anzahl von Elementen in einer Sequenz zu zählen.</span><span class="sxs-lookup"><span data-stu-id="60e3c-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="60e3c-104">Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, wird eine Ausgabe von `91` erzeugt.</span><span class="sxs-lookup"><span data-stu-id="60e3c-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60e3c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60e3c-105">Example</span></span>  
 <span data-ttu-id="60e3c-106">Im folgenden Beispiel wird die Anzahl von `Customers` (Kunden) in der Datenbank gezählt.</span><span class="sxs-lookup"><span data-stu-id="60e3c-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="60e3c-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60e3c-107">Example</span></span>  
 <span data-ttu-id="60e3c-108">Im folgenden Beispiel wird die Anzahl von Produkten in der Datenbank gezählt, die nicht eingestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="60e3c-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="60e3c-109">Wenn Sie dieses Beispiel mit der Beispieldatenbank Northwind ausführen, wird eine Ausgabe von `69` erzeugt.</span><span class="sxs-lookup"><span data-stu-id="60e3c-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="60e3c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60e3c-110">See Also</span></span>  
 [<span data-ttu-id="60e3c-111">Aggregatabfragen</span><span class="sxs-lookup"><span data-stu-id="60e3c-111">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="60e3c-112">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="60e3c-112">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
