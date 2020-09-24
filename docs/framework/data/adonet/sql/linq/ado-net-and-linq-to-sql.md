---
title: ADO.NET und LINQ to SQL
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
ms.openlocfilehash: 5dc1796b7fb7036f68c2435325c6a29d381c59f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161580"
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="d1d5d-102">ADO.NET und LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d1d5d-102">ADO.NET and LINQ to SQL</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="d1d5d-103">ist Teil der ADO.NET-Technologie Familie.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-103">is part of the ADO.NET family of technologies.</span></span> <span data-ttu-id="d1d5d-104">Es basiert auf Diensten, die vom ADO.NET-Anbieter Modell bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-104">It is based on services provided by the ADO.NET provider model.</span></span> <span data-ttu-id="d1d5d-105">Daher können Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Code mit vorhandenen ADO.NET-Anwendungen kombinieren und aktuelle ADO.net-Lösungen zu migrieren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1d5d-105">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing ADO.NET applications and migrate current ADO.NET solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="d1d5d-106">Die folgende Abbildung stellt eine allgemeine Ansicht der Beziehung dar.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-106">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="d1d5d-107">![LINQ to SQL und ADO.NET](./media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="d1d5d-107">![LINQ to SQL and ADO.NET](./media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="d1d5d-108">Verbindungen</span><span class="sxs-lookup"><span data-stu-id="d1d5d-108">Connections</span></span>  

 <span data-ttu-id="d1d5d-109">Sie können eine vorhandene ADO.NET-Verbindung bereitstellen, wenn Sie einen erstellen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="d1d5d-109">You can supply an existing ADO.NET connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="d1d5d-110">Alle Vorgänge <xref:System.Data.Linq.DataContext> für (einschließlich Abfragen) verwenden diese angegebene Verbindung.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-110">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="d1d5d-111">Wenn die Verbindung bereits geöffnet ist, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bleibt sie unverändert, wenn Sie Sie fertiggestellt haben.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-111">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="d1d5d-112">Sie können stets auf die Verbindung zugreifen und diese selbst beenden, indem Sie die <xref:System.Data.Linq.DataContext.Connection%2A>-Eigenschaft wie im folgenden Code verwenden:</span><span class="sxs-lookup"><span data-stu-id="d1d5d-112">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="d1d5d-113">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="d1d5d-113">Transactions</span></span>  

 <span data-ttu-id="d1d5d-114">Sie können Ihren <xref:System.Data.Linq.DataContext> mit Ihrer eigenen Datenbanktransaktion ergänzen, wenn Ihre Anwendung die Transaktion bereits initiiert hat und Sie möchten, dass der <xref:System.Data.Linq.DataContext> berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-114">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="d1d5d-115">Die bevorzugte Methode zum Durchführen von Transaktionen mit dem .NET Framework ist die Verwendung des- <xref:System.Transactions.TransactionScope> Objekts.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-115">The preferred method of doing transactions with the .NET Framework is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="d1d5d-116">Mithilfe dieses Ansatzes können Sie verteilte Transaktionen erstellen, die über Datenbanken hinweg und in Verbindung mit anderen speicherresidenten Ressourcen-Managern funktionieren.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-116">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="d1d5d-117">Transaktionsbereiche erfordern zunächst wenige Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-117">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="d1d5d-118">Sie stufen sich selbst nur dann zu verteilten Transaktionen hoch, wenn mehrere Verbindungen innerhalb des Transaktionsbereichs vorliegen.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-118">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="d1d5d-119">Sie können diesen Ansatz nicht für alle Datenbanken verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-119">You cannot use this approach for all databases.</span></span> <span data-ttu-id="d1d5d-120">Beispielsweise kann die SqlClient-Verbindung keine System Transaktionen herauf Stufen, wenn Sie mit einem SQL Server 2000-Server funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-120">For example, the SqlClient connection cannot promote system transactions when it works against a SQL Server 2000 server.</span></span> <span data-ttu-id="d1d5d-121">Stattdessen wird automatisch eine vollständige, verteilte Transaktion erzeugt, wenn erkannt wird, dass ein Transaktionsbereich genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-121">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="d1d5d-122">Direkte SQL-Befehle</span><span class="sxs-lookup"><span data-stu-id="d1d5d-122">Direct SQL Commands</span></span>  

 <span data-ttu-id="d1d5d-123">Es kann zu Situationen kommen, in denen die Möglichkeiten des <xref:System.Data.Linq.DataContext> zum Abfragen oder zum Übergeben von Änderungen für die spezifische Aufgabe nicht ausreichen.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-123">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="d1d5d-124">In diesen Fällen können Sie die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode verwenden, um SQL-Befehle an die Datenbank zu übergeben und die Abfrageergebnisse in Objekte zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-124">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="d1d5d-125">Nehmen Sie zum Beispiel an, dass die Daten der `Customer`-Klasse auf zwei Tabellen (customer1 und customer2) verteilt sind.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-125">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="d1d5d-126">Die folgende Abfrage gibt eine Sequenz von `Customer`-Objekten zurück:</span><span class="sxs-lookup"><span data-stu-id="d1d5d-126">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="d1d5d-127">Solange die Spaltennamen im tabellarischen Ergebnis den Spalten Eigenschaften ihrer Entitäts Klasse entsprechen, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erstellt die Objekte aus einer beliebigen SQL-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-127">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="d1d5d-128">Parameter</span><span class="sxs-lookup"><span data-stu-id="d1d5d-128">Parameters</span></span>  

 <span data-ttu-id="d1d5d-129">Die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode akzeptiert Parameter.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-129">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="d1d5d-130">Der folgende Code führt eine parametrisierte Abfrage aus:</span><span class="sxs-lookup"><span data-stu-id="d1d5d-130">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="d1d5d-131">Parameter werden im Abfragetext mithilfe der gleichen verschachtelten Schreibweise wie in `Console.WriteLine()` und `String.Format()` ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-131">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="d1d5d-132">`String.Format()` ersetzt die verschachtelten Parameter der angegebenen Abfragezeichenfolge durch generierte Parameternamen, wie z. B. `@p0`, `@p1` …, `@p(n)`.</span><span class="sxs-lookup"><span data-stu-id="d1d5d-132">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1d5d-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d1d5d-133">See also</span></span>

- [<span data-ttu-id="d1d5d-134">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="d1d5d-134">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="d1d5d-135">Vorgehensweise: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem DataContext</span><span class="sxs-lookup"><span data-stu-id="d1d5d-135">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
