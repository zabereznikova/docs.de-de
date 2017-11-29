---
title: Sortieren von Elementen in einer Sequenz
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2f4f89c1391b6582d77acccb8b256bef617ecff3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sort-elements-in-a-sequence"></a><span data-ttu-id="97bff-102">Sortieren von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="97bff-102">Sort Elements in a Sequence</span></span>
<span data-ttu-id="97bff-103">Verwenden Sie den <xref:System.Linq.Enumerable.OrderBy%2A>-Operator, um eine Sequenz nach einem oder mehreren Schlüsseln zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="97bff-103">Use the <xref:System.Linq.Enumerable.OrderBy%2A> operator to sort a sequence according to one or more keys.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="97bff-104">Dient zur Sortierung mithilfe einfacher, primitiver Typen wie z. B. `string`, `int`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="97bff-104"> is designed to support ordering by simple primitive types, such as `string`, `int`, and so on.</span></span> <span data-ttu-id="97bff-105">Sortierungen für komplexe, mehrwertige Klassen, z. B. anonyme Typen, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="97bff-105">It does not support ordering for complex multi-valued classes, such as anonymous types.</span></span> <span data-ttu-id="97bff-106">Außerdem werden keine `byte`-Datentypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="97bff-106">It also does not support `byte` datatypes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97bff-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97bff-107">Example</span></span>  
 <span data-ttu-id="97bff-108">Das folgende Beispiel sortiert `Employees` nach dem Einstellungsdatum.</span><span class="sxs-lookup"><span data-stu-id="97bff-108">The following example sorts `Employees` by date of hire.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a><span data-ttu-id="97bff-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97bff-109">Example</span></span>  
 <span data-ttu-id="97bff-110">Das folgende Beispiel verwendet `where`, um `Orders`, die nach `London` ausgeliefert wurden, nach Fracht zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="97bff-110">The following example uses `where` to sort `Orders` shipped to `London` by freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a><span data-ttu-id="97bff-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97bff-111">Example</span></span>  
 <span data-ttu-id="97bff-112">Im folgenden Beispiel wird `Products` absteigend nach Einzelpreis sortiert.</span><span class="sxs-lookup"><span data-stu-id="97bff-112">The following example sorts `Products` by unit price from highest to lowest.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="97bff-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97bff-113">Example</span></span>  
 <span data-ttu-id="97bff-114">Im folgenden Beispiel wird ein zusammengesetztes `OrderBy` verwendet, um `Customers` nach Ort und dann nach Kontaktnamen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="97bff-114">The following example uses a compound `OrderBy` to sort `Customers` by city and then by contact name.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="97bff-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97bff-115">Example</span></span>  
 <span data-ttu-id="97bff-116">Im folgenden Beispiel werden Bestellungen von `EmployeeID 1` nach Lieferland und dann absteigend nach Fracht sortiert.</span><span class="sxs-lookup"><span data-stu-id="97bff-116">The following example sorts Orders from `EmployeeID 1` by ship-to country, and then by highest to lowest freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="97bff-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97bff-117">Example</span></span>  
 <span data-ttu-id="97bff-118">Das folgende Beispiel kombiniert die Operatoren <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> und <xref:System.Linq.Enumerable.GroupBy%2A>, um jene `Products` zu ermitteln, die in den einzelnen Kategorien die höchsten Einzelpreise aufweisen. Anschließend wird die Gruppe nach Kategorie-ID sortiert.</span><span class="sxs-lookup"><span data-stu-id="97bff-118">The following example combines <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, and <xref:System.Linq.Enumerable.GroupBy%2A> operators to find the `Products` that have the highest unit price in each category, and then sorts the group by category id.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 <span data-ttu-id="97bff-119">Wenn Sie die vorherige Abfrage mit der Beispieldatenbank Northwind ausführen, sehen die Ergebnisse wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="97bff-119">If you run the previous query against the Northwind sample database, the results will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97bff-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97bff-120">See Also</span></span>  
 [<span data-ttu-id="97bff-121">Beispiele für Abfragen</span><span class="sxs-lookup"><span data-stu-id="97bff-121">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="97bff-122">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="97bff-122">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
