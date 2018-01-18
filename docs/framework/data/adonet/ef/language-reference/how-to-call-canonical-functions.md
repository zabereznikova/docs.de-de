---
title: 'Gewusst wie: Aufrufen von kanonischen Funktionen'
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
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 02cbcee218db310fdddc7f42d9b6f01a16a8314d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-call-canonical-functions"></a><span data-ttu-id="b8be9-102">Gewusst wie: Aufrufen von kanonischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="b8be9-102">How to: Call Canonical Functions</span></span>
<span data-ttu-id="b8be9-103">Die <xref:System.Data.Objects.EntityFunctions>-Klasse enthält Methoden, mit denen kanonische Funktionen in LINQ to Entities-Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b8be9-103">The <xref:System.Data.Objects.EntityFunctions> class contains methods that expose canonical functions to use in LINQ to Entities queries.</span></span> <span data-ttu-id="b8be9-104">Weitere Informationen zur kanonischen Funktionen finden Sie unter [Kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="b8be9-104">For information about canonical functions, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8be9-105">Die Methoden <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> und <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> der <xref:System.Data.Objects.EntityFunctions>-Klasse verfügen über keine kanonischen Funktionsentsprechungen.</span><span class="sxs-lookup"><span data-stu-id="b8be9-105">The <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> and <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> methods in the <xref:System.Data.Objects.EntityFunctions> class do not have canonical function equivalents.</span></span>  
  
 <span data-ttu-id="b8be9-106">Kanonische Funktionen, die eine Berechnung für einen Satz von Werten ausführen und einen einzelnen Wert (auch bekannt als aggregierte kanonische Funktionen) zurückgeben, können direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b8be9-106">Canonical functions that perform a calculation on a set of values and return a single value (also known as aggregate canonical functions) can be directly invoked.</span></span> <span data-ttu-id="b8be9-107">Andere kanonische Funktionen können nur als Teil einer LINQ to Entities-Abfrage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b8be9-107">Other canonical functions can only be called as part of a LINQ to Entities query.</span></span> <span data-ttu-id="b8be9-108">Zum direkten Aufrufen einer Aggregatfunktion muss eine <xref:System.Data.Objects.ObjectQuery%601> an die Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b8be9-108">To call an aggregate function directly, you must pass an <xref:System.Data.Objects.ObjectQuery%601> to the function.</span></span> <span data-ttu-id="b8be9-109">Weitere Informationen finden Sie unten im zweiten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="b8be9-109">For more information, see the second example below.</span></span>  
  
 <span data-ttu-id="b8be9-110">Sie können einige kanonische Funktionen mit Common Language Runtime (CLR)-Methoden in LINQ to Entities-Abfragen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b8be9-110">You can call some canonical functions by using common language runtime (CLR) methods in LINQ to Entities queries.</span></span> <span data-ttu-id="b8be9-111">Eine Liste der CLR-Methoden, die die kanonischen Funktionen zugeordnet sind, finden Sie unter [CLR-Methoden zu kanonischen Funktionszuordnung](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="b8be9-111">For a list of CLR methods that map to canonical functions, see [CLR Method to Canonical Function Mapping](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8be9-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8be9-112">Example</span></span>  
 <span data-ttu-id="b8be9-113">Im folgenden Beispiel wird die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="b8be9-113">The following example uses the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="b8be9-114">Im Beispiel wird eine die <xref:System.Data.Objects.EntityFunctions.DiffDays%2A>-Methode verwendende LINQ to Entities-Abfrage zum Zurückgeben aller Produkte ausgeführt, für die die Differenz zwischen `SellEndDate` und `SellStartDate` weniger als 365 Tage beträgt:</span><span class="sxs-lookup"><span data-stu-id="b8be9-114">The example executes a LINQ to Entities query that uses the <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> method to return all products for which the difference between `SellEndDate` and `SellStartDate` is less than 365 days:</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="b8be9-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8be9-115">Example</span></span>  
 <span data-ttu-id="b8be9-116">Im folgenden Beispiel wird die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="b8be9-116">The following example uses the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="b8be9-117">Im Beispiel wird die <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A>-Aggregatmethode aufgerufen, um die Standardabweichung von `SalesOrderHeader`-Teilergebnissen direkt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b8be9-117">The example calls the aggregate <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> method directly to return the standard deviation of `SalesOrderHeader` subtotals.</span></span> <span data-ttu-id="b8be9-118">Eine <xref:System.Data.Objects.ObjectQuery%601> wird an die Funktion übergeben, durch die sie aufgerufen werden kann, ohne Teil einer LINQ to Entities-Abfrage sein zu müssen.</span><span class="sxs-lookup"><span data-stu-id="b8be9-118">Note that an <xref:System.Data.Objects.ObjectQuery%601> is passed to the function, which allows it to be called without being part of a LINQ to Entities query.</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b8be9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8be9-119">See Also</span></span>  
 [<span data-ttu-id="b8be9-120">Aufrufen von Funktionen in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="b8be9-120">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [<span data-ttu-id="b8be9-121">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b8be9-121">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
