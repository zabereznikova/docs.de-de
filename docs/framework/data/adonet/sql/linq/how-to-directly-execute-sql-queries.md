---
title: 'Vorgehensweise: Direktes Ausführen von SQL-Abfragen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 04353361f8356b1d2b2aa3b930bb9b5ab88b9c0b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583690"
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="7badc-102">Vorgehensweise: Direktes Ausführen von SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="7badc-102">How to: Directly Execute SQL Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7badc-103">übersetzt die Abfragen, die von Ihnen (in Textform) in parametrisierte SQL-Abfragen geschrieben wurden, und sendet diese zur Verarbeitung an den SQL-Server.</span><span class="sxs-lookup"><span data-stu-id="7badc-103">translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="7badc-104">SQL kann nicht alle lokal für Ihre Anwendung verfügbaren Varianten ausführen.</span><span class="sxs-lookup"><span data-stu-id="7badc-104">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7badc-105">versucht, diese lokalen Methoden in äquivalente Operationen und Funktionen zu konvertieren, die in der SQL-Umgebung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7badc-105">tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="7badc-106">Die meisten Methoden und Operatoren auf .NET Framework integrierten Typen über direkte Übersetzungen zu SQL-Befehle verfügen.</span><span class="sxs-lookup"><span data-stu-id="7badc-106">Most methods and operators on .NET Framework built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="7badc-107">Einige können von den verfügbaren Funktionen erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="7badc-107">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="7badc-108">Jene, die nicht erzeugt werden können, generieren Laufzeitausnahmen.</span><span class="sxs-lookup"><span data-stu-id="7badc-108">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="7badc-109">Weitere Informationen finden Sie unter [SQL-CLR-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="7badc-109">For more information, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="7badc-110">In Fällen, in denen eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage für spezielle Aufgaben nicht ausreicht, können Sie die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode zur Ausführung einer SQL-Abfrage verwenden und das Ergebnis anschließend direkt in Objekte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7badc-110">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7badc-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7badc-111">Example</span></span>  
 <span data-ttu-id="7badc-112">Nehmen Sie im folgenden Beispiel an, dass die Daten für die `Customer`-Klasse auf zwei Tabellen (Customer1 und Customer2) verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="7badc-112">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="7badc-113">Die Abfrage gibt eine Sequenz von `Customer`-Objekten zurück.</span><span class="sxs-lookup"><span data-stu-id="7badc-113">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="7badc-114">Solange die Spaltennamen im tabellarischen Ergebnis den Spalteneigenschaften Ihrer Entitätsklasse entsprechen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Objekte aus einer SQL-Abfrage erstellt.</span><span class="sxs-lookup"><span data-stu-id="7badc-114">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7badc-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7badc-115">Example</span></span>  
 <span data-ttu-id="7badc-116">Die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode berücksichtigt auch Parameter.</span><span class="sxs-lookup"><span data-stu-id="7badc-116">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="7badc-117">Verwenden Sie Code wie den folgenden, um eine parametrisierte Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7badc-117">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="7badc-118">Die Parameter werden im Abfragetext mithilfe der gleichen verschachtelten Schreibweise wie in `Console.WriteLine()` und `String.Format()` ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="7badc-118">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="7badc-119">In der Tat `String.Format()` aufgerufen wird in der Abfragezeichenfolge, die Sie angeben, und Ersetzen Sie dabei die Parameter durch erzeugte Parameternamen wie z. B. @p0, @p1 ..., @p(n).</span><span class="sxs-lookup"><span data-stu-id="7badc-119">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7badc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7badc-120">See also</span></span>

- [<span data-ttu-id="7badc-121">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="7badc-121">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="7badc-122">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="7badc-122">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
