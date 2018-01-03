---
title: "Gewusst wie: Direktes Ausführen von SQL-Abfragen"
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
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e8bbeb0d7ce040387b263486b947e793eca39d29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="a9de7-102">Gewusst wie: Direktes Ausführen von SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="a9de7-102">How to: Directly Execute SQL Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a9de7-103"> übersetzt die Abfragen, die von Ihnen (in Textform) in parametrisierte SQL-Abfragen geschrieben wurden, und sendet diese zur Verarbeitung an den SQL-Server.</span><span class="sxs-lookup"><span data-stu-id="a9de7-103"> translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="a9de7-104">SQL kann nicht alle lokal für Ihre Anwendung verfügbaren Varianten ausführen.</span><span class="sxs-lookup"><span data-stu-id="a9de7-104">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a9de7-105"> versucht, diese lokalen Methoden in äquivalente Operationen und Funktionen zu konvertieren, die in der SQL-Umgebung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a9de7-105"> tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="a9de7-106">Die meisten Methoden und die Operatoren in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]-internen Datentypen verfügen über direkte Übersetzungen zu SQL-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="a9de7-106">Most methods and operators on [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="a9de7-107">Einige können von den verfügbaren Funktionen erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="a9de7-107">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="a9de7-108">Jene, die nicht erzeugt werden können, generieren Laufzeitausnahmen.</span><span class="sxs-lookup"><span data-stu-id="a9de7-108">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="a9de7-109">Weitere Informationen finden Sie unter [SQL-CLR-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="a9de7-109">For more information, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="a9de7-110">In Fällen, in denen eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage für spezielle Aufgaben nicht ausreicht, können Sie die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode zur Ausführung einer SQL-Abfrage verwenden und das Ergebnis anschließend direkt in Objekte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a9de7-110">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9de7-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9de7-111">Example</span></span>  
 <span data-ttu-id="a9de7-112">Nehmen Sie im folgenden Beispiel an, dass die Daten für die `Customer`-Klasse auf zwei Tabellen (Customer1 und Customer2) verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="a9de7-112">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="a9de7-113">Die Abfrage gibt eine Sequenz von `Customer`-Objekten zurück.</span><span class="sxs-lookup"><span data-stu-id="a9de7-113">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="a9de7-114">Solange die Spaltennamen im tabellarischen Ergebnis den Spalteneigenschaften Ihrer Entitätsklasse entsprechen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erstellt die Objekte aus einer SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="a9de7-114">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9de7-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9de7-115">Example</span></span>  
 <span data-ttu-id="a9de7-116">Die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode berücksichtigt auch Parameter.</span><span class="sxs-lookup"><span data-stu-id="a9de7-116">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="a9de7-117">Verwenden Sie Code wie den folgenden, um eine parametrisierte Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a9de7-117">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="a9de7-118">Die Parameter werden im Abfragetext mithilfe der gleichen verschachtelten Schreibweise wie in `Console.WriteLine()` und `String.Format()` ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="a9de7-118">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="a9de7-119">In der Tat `String.Format()` aufgerufen wird in der Abfragezeichenfolge, die Sie bereitstellen, ersetzen die Parameter durch erzeugte Parameternamen wie z. B. @p0, @p1 ..., @p(n).</span><span class="sxs-lookup"><span data-stu-id="a9de7-119">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9de7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9de7-120">See Also</span></span>  
 [<span data-ttu-id="a9de7-121">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="a9de7-121">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="a9de7-122">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="a9de7-122">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
