---
title: 'Vorgehensweise: Aufrufen von Datenbankfunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: a4cf77000af56ed2a6445beaef2d7856486b85db
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173665"
---
# <a name="how-to-call-database-functions"></a><span data-ttu-id="8d81a-102">Vorgehensweise: Aufrufen von Datenbankfunktionen</span><span class="sxs-lookup"><span data-stu-id="8d81a-102">How to: Call Database Functions</span></span>

<span data-ttu-id="8d81a-103">Die <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse enthält Methoden, mit denen SQL Server-Funktionen in LINQ to Entities-Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8d81a-103">The <xref:System.Data.Objects.SqlClient.SqlFunctions> class contains methods that expose SQL Server functions to use in LINQ to Entities queries.</span></span> <span data-ttu-id="8d81a-104">Beim Verwenden von <xref:System.Data.Objects.SqlClient.SqlFunctions>-Methoden in LINQ to Entities-Abfragen werden die entsprechenden Datenbankfunktionen in der Datenbank ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8d81a-104">When you use <xref:System.Data.Objects.SqlClient.SqlFunctions> methods in LINQ to Entities queries, the corresponding database functions are executed in the database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d81a-105">Datenbankfunktionen, die eine Berechnung für einen Satz von Werten ausführen und einen einzelnen Wert (auch bekannt als aggregierte Datenbankfunktionen) zurückgeben, können direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8d81a-105">Database functions that perform a calculation on a set of values and return a single value (also known as aggregate database functions) can be directly invoked.</span></span> <span data-ttu-id="8d81a-106">Andere kanonische Funktionen können nur als Teil einer LINQ to Entities-Abfrage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8d81a-106">Other canonical functions can only be called as part of a LINQ to Entities query.</span></span> <span data-ttu-id="8d81a-107">Zum direkten Aufrufen einer Aggregatfunktion muss eine <xref:System.Data.Objects.ObjectQuery%601> an die Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="8d81a-107">To call an aggregate function directly, you must pass an <xref:System.Data.Objects.ObjectQuery%601> to the function.</span></span> <span data-ttu-id="8d81a-108">Weitere Informationen finden Sie unten im zweiten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="8d81a-108">For more information, see the second example below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d81a-109">Die Methoden in der <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse sind spezifisch für SQL Server-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="8d81a-109">The methods in the <xref:System.Data.Objects.SqlClient.SqlFunctions> class are specific to SQL Server functions.</span></span> <span data-ttu-id="8d81a-110">Ähnliche Klassen, die Datenbankfunktionen verfügbar machen, sind möglicherweise über andere Anbieter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8d81a-110">Similar classes that expose database functions may be available through other providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d81a-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d81a-111">Example</span></span>  

 <span data-ttu-id="8d81a-112">Im folgenden Beispiel wird das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)verwendet.</span><span class="sxs-lookup"><span data-stu-id="8d81a-112">The following example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="8d81a-113">Im Beispiel wird eine LINQ to Entities-Abfrage ausgeführt, die die <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A>-Methode zur Rückgabe aller Kontakte verwendet, deren Nachname mit "Si" beginnt:</span><span class="sxs-lookup"><span data-stu-id="8d81a-113">The example executes a LINQ to Entities query that uses the <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> method to return all contacts whose last name starts with "Si":</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="8d81a-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8d81a-114">Example</span></span>  

 <span data-ttu-id="8d81a-115">Im folgenden Beispiel wird das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)verwendet.</span><span class="sxs-lookup"><span data-stu-id="8d81a-115">The following example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="8d81a-116">Im Beispiel wird die aggregierte <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>-Methode direkt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8d81a-116">The example calls the aggregate <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> method directly.</span></span> <span data-ttu-id="8d81a-117">Eine <xref:System.Data.Objects.ObjectQuery%601> wird an die Funktion übergeben, durch die sie aufgerufen werden kann, ohne Teil einer LINQ to Entities-Abfrage sein zu müssen.</span><span class="sxs-lookup"><span data-stu-id="8d81a-117">Note that an <xref:System.Data.Objects.ObjectQuery%601> is passed to the function, which allows it to be called without being part of a LINQ to Entities query.</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8d81a-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d81a-118">See also</span></span>

- [<span data-ttu-id="8d81a-119">Aufrufen von Funktionen in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="8d81a-119">Calling Functions in LINQ to Entities Queries</span></span>](calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="8d81a-120">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8d81a-120">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
