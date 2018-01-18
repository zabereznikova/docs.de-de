---
title: 'Gewusst wie: Aufrufen von Datenbankfunktionen'
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
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b442e1ca096b100e6d7c22303f8c5bcfa49f79d2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-call-database-functions"></a><span data-ttu-id="315a9-102">Gewusst wie: Aufrufen von Datenbankfunktionen</span><span class="sxs-lookup"><span data-stu-id="315a9-102">How to: Call Database Functions</span></span>
<span data-ttu-id="315a9-103">Die <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse enthält Methoden, mit denen SQL Server-Funktionen in LINQ to Entities-Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="315a9-103">The <xref:System.Data.Objects.SqlClient.SqlFunctions> class contains methods that expose SQL Server functions to use in LINQ to Entities queries.</span></span> <span data-ttu-id="315a9-104">Beim Verwenden von <xref:System.Data.Objects.SqlClient.SqlFunctions>-Methoden in LINQ to Entities-Abfragen werden die entsprechenden Datenbankfunktionen in der Datenbank ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="315a9-104">When you use <xref:System.Data.Objects.SqlClient.SqlFunctions> methods in LINQ to Entities queries, the corresponding database functions are executed in the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="315a9-105">Datenbankfunktionen, die eine Berechnung für einen Satz von Werten ausführen und einen einzelnen Wert (auch bekannt als aggregierte Datenbankfunktionen) zurückgeben, können direkt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="315a9-105">Database functions that perform a calculation on a set of values and return a single value (also known as aggregate database functions) can be directly invoked.</span></span> <span data-ttu-id="315a9-106">Andere kanonische Funktionen können nur als Teil einer LINQ to Entities-Abfrage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="315a9-106">Other canonical functions can only be called as part of a LINQ to Entities query.</span></span> <span data-ttu-id="315a9-107">Zum direkten Aufrufen einer Aggregatfunktion muss eine <xref:System.Data.Objects.ObjectQuery%601> an die Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="315a9-107">To call an aggregate function directly, you must pass an <xref:System.Data.Objects.ObjectQuery%601> to the function.</span></span> <span data-ttu-id="315a9-108">Weitere Informationen finden Sie unten im zweiten Beispiel.</span><span class="sxs-lookup"><span data-stu-id="315a9-108">For more information, see the second example below.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="315a9-109">Die Methoden in der <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse sind spezifisch für SQL Server-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="315a9-109">The methods in the <xref:System.Data.Objects.SqlClient.SqlFunctions> class are specific to SQL Server functions.</span></span> <span data-ttu-id="315a9-110">Ähnliche Klassen, die Datenbankfunktionen verfügbar machen, sind möglicherweise über andere Anbieter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="315a9-110">Similar classes that expose database functions may be available through other providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="315a9-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="315a9-111">Example</span></span>  
 <span data-ttu-id="315a9-112">Im folgenden Beispiel wird die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="315a9-112">The following example uses the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="315a9-113">Im Beispiel wird eine LINQ to Entities-Abfrage ausgeführt, die die <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A>-Methode zur Rückgabe aller Kontakte verwendet, deren Nachname mit "Si" beginnt:</span><span class="sxs-lookup"><span data-stu-id="315a9-113">The example executes a LINQ to Entities query that uses the <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> method to return all contacts whose last name starts with "Si":</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="315a9-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="315a9-114">Example</span></span>  
 <span data-ttu-id="315a9-115">Im folgenden Beispiel wird die [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span><span class="sxs-lookup"><span data-stu-id="315a9-115">The following example uses the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832).</span></span> <span data-ttu-id="315a9-116">Im Beispiel wird die aggregierte <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>-Methode direkt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="315a9-116">The example calls the aggregate <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> method directly.</span></span> <span data-ttu-id="315a9-117">Eine <xref:System.Data.Objects.ObjectQuery%601> wird an die Funktion übergeben, durch die sie aufgerufen werden kann, ohne Teil einer LINQ to Entities-Abfrage sein zu müssen.</span><span class="sxs-lookup"><span data-stu-id="315a9-117">Note that an <xref:System.Data.Objects.ObjectQuery%601> is passed to the function, which allows it to be called without being part of a LINQ to Entities query.</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="315a9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="315a9-118">See Also</span></span>  
 [<span data-ttu-id="315a9-119">Aufrufen von Funktionen in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="315a9-119">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [<span data-ttu-id="315a9-120">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="315a9-120">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
