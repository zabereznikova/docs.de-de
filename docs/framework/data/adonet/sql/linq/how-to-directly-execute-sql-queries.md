---
title: 'Vorgehensweise: Direktes Ausführen von SQL-Abfragen'
description: Erfahren Sie, wie Sie mithilfe von ExecuteQuery eine Abfrage ausführen und die Ergebnisse in Fällen, in denen eine LINQ to SQL Abfrage unzureichend ist, direkt in Objekte konvertieren.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 59bd404e41f6be1181d6a625c31ee23358db0df3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286364"
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="ff469-103">Vorgehensweise: Direktes Ausführen von SQL-Abfragen</span><span class="sxs-lookup"><span data-stu-id="ff469-103">How to: Directly Execute SQL Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ff469-104">übersetzt die Abfragen, die von Ihnen (in Textform) in parametrisierte SQL-Abfragen geschrieben wurden, und sendet diese zur Verarbeitung an den SQL-Server.</span><span class="sxs-lookup"><span data-stu-id="ff469-104">translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="ff469-105">SQL kann nicht alle lokal für Ihre Anwendung verfügbaren Varianten ausführen.</span><span class="sxs-lookup"><span data-stu-id="ff469-105">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ff469-106">versucht, diese lokalen Methoden in äquivalente Operationen und Funktionen zu konvertieren, die in der SQL-Umgebung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ff469-106">tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="ff469-107">Die meisten Methoden und Operatoren in .NET Framework integrierten Typen weisen direkte Übersetzungen in SQL-Befehle auf.</span><span class="sxs-lookup"><span data-stu-id="ff469-107">Most methods and operators on .NET Framework built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="ff469-108">Einige können von den verfügbaren Funktionen erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="ff469-108">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="ff469-109">Jene, die nicht erzeugt werden können, generieren Laufzeitausnahmen.</span><span class="sxs-lookup"><span data-stu-id="ff469-109">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="ff469-110">Weitere Informationen finden Sie unter [SQL-CLR-Typzuordnung](sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="ff469-110">For more information, see [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="ff469-111">In Fällen, in denen eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Abfrage für spezielle Aufgaben nicht ausreicht, können Sie die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode zur Ausführung einer SQL-Abfrage verwenden und das Ergebnis anschließend direkt in Objekte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ff469-111">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff469-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff469-112">Example</span></span>  
 <span data-ttu-id="ff469-113">Nehmen Sie im folgenden Beispiel an, dass die Daten für die `Customer`-Klasse auf zwei Tabellen (Customer1 und Customer2) verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="ff469-113">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="ff469-114">Die Abfrage gibt eine Sequenz von `Customer`-Objekten zurück.</span><span class="sxs-lookup"><span data-stu-id="ff469-114">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="ff469-115">Solange die Spaltennamen im tabellarischen Ergebnis den Spalten Eigenschaften ihrer Entitäts Klasse entsprechen, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erstellt die Objekte aus einer beliebigen SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="ff469-115">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff469-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff469-116">Example</span></span>  
 <span data-ttu-id="ff469-117">Die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode berücksichtigt auch Parameter.</span><span class="sxs-lookup"><span data-stu-id="ff469-117">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="ff469-118">Verwenden Sie Code wie den folgenden, um eine parametrisierte Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ff469-118">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="ff469-119">Die Parameter werden im Abfragetext mithilfe der gleichen verschachtelten Schreibweise wie in `Console.WriteLine()` und `String.Format()` ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="ff469-119">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="ff469-120">Tatsächlich `String.Format()` wird tatsächlich für die von Ihnen bereitgestellte Abfrage Zeichenfolge aufgerufen, wobei die Parameter mit den geschweiften Klammern durch generierte Parameternamen ersetzt werden, wie z. b @p0 @p1 .,..., @p (n).</span><span class="sxs-lookup"><span data-stu-id="ff469-120">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff469-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff469-121">See also</span></span>

- [<span data-ttu-id="ff469-122">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="ff469-122">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="ff469-123">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="ff469-123">Querying the Database</span></span>](querying-the-database.md)
