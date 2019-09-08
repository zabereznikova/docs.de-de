---
title: Sortieren von Elementen in einer Sequenz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d59b93a9-50c8-4770-a114-d902f6a0ea76
ms.openlocfilehash: 21fa2f9e1dc2f255fe94f2420ba90a809ab5b05e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792660"
---
# <a name="sort-elements-in-a-sequence"></a><span data-ttu-id="4d95e-102">Sortieren von Elementen in einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="4d95e-102">Sort Elements in a Sequence</span></span>
<span data-ttu-id="4d95e-103">Verwenden Sie den <xref:System.Linq.Enumerable.OrderBy%2A>-Operator, um eine Sequenz nach einem oder mehreren Schlüsseln zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="4d95e-103">Use the <xref:System.Linq.Enumerable.OrderBy%2A> operator to sort a sequence according to one or more keys.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4d95e-104">ist so konzipiert, dass die Reihenfolge `string`von einfachen primitiven Typen wie, `int`usw. unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="4d95e-104">is designed to support ordering by simple primitive types, such as `string`, `int`, and so on.</span></span> <span data-ttu-id="4d95e-105">Sortierungen für komplexe, mehrwertige Klassen, z. B. anonyme Typen, werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4d95e-105">It does not support ordering for complex multi-valued classes, such as anonymous types.</span></span> <span data-ttu-id="4d95e-106">Außerdem werden keine `byte`-Datentypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4d95e-106">It also does not support `byte` datatypes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d95e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d95e-107">Example</span></span>  
 <span data-ttu-id="4d95e-108">Das folgende Beispiel sortiert `Employees` nach dem Einstellungsdatum.</span><span class="sxs-lookup"><span data-stu-id="4d95e-108">The following example sorts `Employees` by date of hire.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#20](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#20)]
 [!code-vb[DLinqQueryExamples#20](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#20)]  
  
## <a name="example"></a><span data-ttu-id="4d95e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d95e-109">Example</span></span>  
 <span data-ttu-id="4d95e-110">Das folgende Beispiel verwendet `where`, um `Orders`, die nach `London` ausgeliefert wurden, nach Fracht zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="4d95e-110">The following example uses `where` to sort `Orders` shipped to `London` by freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#21](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#21)]
 [!code-vb[DLinqQueryExamples#21](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#21)]  
  
## <a name="example"></a><span data-ttu-id="4d95e-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d95e-111">Example</span></span>  
 <span data-ttu-id="4d95e-112">Im folgenden Beispiel wird `Products` absteigend nach Einzelpreis sortiert.</span><span class="sxs-lookup"><span data-stu-id="4d95e-112">The following example sorts `Products` by unit price from highest to lowest.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#22](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#22)]
 [!code-vb[DLinqQueryExamples#22](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="4d95e-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d95e-113">Example</span></span>  
 <span data-ttu-id="4d95e-114">Im folgenden Beispiel wird ein zusammengesetztes `OrderBy` verwendet, um `Customers` nach Ort und dann nach Kontaktnamen zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="4d95e-114">The following example uses a compound `OrderBy` to sort `Customers` by city and then by contact name.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#24](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#24)]
 [!code-vb[DLinqQueryExamples#24](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#24)]  
  
## <a name="example"></a><span data-ttu-id="4d95e-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d95e-115">Example</span></span>  
 <span data-ttu-id="4d95e-116">Im folgenden Beispiel werden die Bestel `EmployeeID 1` Lungen `ShipCountry`von nach und dann von der höchsten zur niedrigsten Fracht sortiert.</span><span class="sxs-lookup"><span data-stu-id="4d95e-116">The following example sorts Orders from `EmployeeID 1` by `ShipCountry`, and then by highest to lowest freight.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#25](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#25)]
 [!code-vb[DLinqQueryExamples#25](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="4d95e-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d95e-117">Example</span></span>  
 <span data-ttu-id="4d95e-118">Das folgende Beispiel kombiniert die Operatoren <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A> und <xref:System.Linq.Enumerable.GroupBy%2A>, um jene `Products` zu ermitteln, die in den einzelnen Kategorien die höchsten Einzelpreise aufweisen. Anschließend wird die Gruppe nach Kategorie-ID sortiert.</span><span class="sxs-lookup"><span data-stu-id="4d95e-118">The following example combines <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Max%2A>, and <xref:System.Linq.Enumerable.GroupBy%2A> operators to find the `Products` that have the highest unit price in each category, and then sorts the group by category id.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#26](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#26)]
 [!code-vb[DLinqQueryExamples#26](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#26)]  
  
 <span data-ttu-id="4d95e-119">Wenn Sie die vorherige Abfrage mit der Beispieldatenbank Northwind ausführen, sehen die Ergebnisse wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="4d95e-119">If you run the previous query against the Northwind sample database, the results will resemble the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d95e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d95e-120">See also</span></span>

- [<span data-ttu-id="4d95e-121">Abfragebeispiele</span><span class="sxs-lookup"><span data-stu-id="4d95e-121">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="4d95e-122">Downloading Sample Databases (Herunterladen von Beispieldatenbanken)</span><span class="sxs-lookup"><span data-stu-id="4d95e-122">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
