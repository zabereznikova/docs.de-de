---
title: Transaktionen und Parallelität
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: ba857031a54374ee295c2bfd724e7fb8651b7c1f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174693"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="78ccb-102">Transaktionen und Parallelität</span><span class="sxs-lookup"><span data-stu-id="78ccb-102">Transactions and Concurrency</span></span>
<span data-ttu-id="78ccb-103">Eine Transaktion besteht aus einem einzelnen Befehl oder einer Gruppe von Befehlen, die als Paket ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="78ccb-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="78ccb-104">Mit Transaktionen können Sie mehrere Operationen in einem Arbeitsschritt zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="78ccb-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="78ccb-105">Wenn an einer Stelle in der Transaktion ein Fehler auftritt, kann für alle Updates ein Rollback zum Zustand vor der Transaktion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="78ccb-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="78ccb-106">Eine Transaktion muss zur Gewährleistung der Datenkonsistenz die folgenden vier Kriterien, die so genannten ACID-Kriterien, erfüllen: Atomicity (Atomarität), Consistency (Konsistenz), Isolation und Durability (Dauerhaftigkeit).</span><span class="sxs-lookup"><span data-stu-id="78ccb-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="78ccb-107">Die meisten relationalen Datenbanksysteme (z. B. Microsoft SQL Server) unterstützen Transaktionen, indem sie für Update-, Einfüge- oder Löschvorgänge, die durch eine Clientanwendung ausgeführt werden, entsprechende Sperr-, Protokollierungs- und Transaktionsverwaltungsfunktionen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="78ccb-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78ccb-108">Transaktionen, an denen mehrere Ressourcen beteiligt sind, können die Parallelität senken, wenn Sperren zu lang gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="78ccb-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="78ccb-109">Halten Sie Transaktionen daher so kurz wie möglich.</span><span class="sxs-lookup"><span data-stu-id="78ccb-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="78ccb-110">Wenn an einer Transaktion mehrere Tabellen in derselben Datenbank oder auf demselben Server beteiligt sind, bieten explizite Transaktionen in gespeicherten Prozeduren oft eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="78ccb-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="78ccb-111">Transaktionen in gespeicherten SQL Server-Prozeduren können Sie mithilfe der Transact-SQL-Anweisungen `BEGIN TRANSACTION`, `COMMIT TRANSACTION` und `ROLLBACK TRANSACTION` erstellen.</span><span class="sxs-lookup"><span data-stu-id="78ccb-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="78ccb-112">Weitere Informationen dazu finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="78ccb-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="78ccb-113">Transaktionen, die im Zusammenhang mit anderen Ressourcen-Manager, z. B. Transaktionen zwischen SQL Server und Oracle, erfordern eine verteilte Transaktion.</span><span class="sxs-lookup"><span data-stu-id="78ccb-113">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78ccb-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="78ccb-114">In This Section</span></span>  
 [<span data-ttu-id="78ccb-115">Lokale Transaktionen</span><span class="sxs-lookup"><span data-stu-id="78ccb-115">Local Transactions</span></span>](../../../../docs/framework/data/adonet/local-transactions.md)  
 <span data-ttu-id="78ccb-116">Zeigt, wie Transaktionen für eine Datenbank ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="78ccb-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="78ccb-117">Verteilte Transaktionen</span><span class="sxs-lookup"><span data-stu-id="78ccb-117">Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 <span data-ttu-id="78ccb-118">Beschreibt die Ausführung von verteilten Transaktionen in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="78ccb-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="78ccb-119">System.Transactions-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="78ccb-119">System.Transactions Integration with SQL Server</span></span>](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="78ccb-120">Beschreibt <xref:System.Transactions> Integration in SQL Server für die Arbeit mit verteilten Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="78ccb-120">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="78ccb-121">Optimistische Nebenläufigkeit</span><span class="sxs-lookup"><span data-stu-id="78ccb-121">Optimistic Concurrency</span></span>](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 <span data-ttu-id="78ccb-122">Beschreibt die vollständige und die eingeschränkte Parallelität und wie Sie auf Parallelitätsverletzungen testen können.</span><span class="sxs-lookup"><span data-stu-id="78ccb-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78ccb-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78ccb-123">See also</span></span>

- [<span data-ttu-id="78ccb-124">Transaktionsgrundlagen</span><span class="sxs-lookup"><span data-stu-id="78ccb-124">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)
- [<span data-ttu-id="78ccb-125">Aufbauen der Verbindung zu einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="78ccb-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [<span data-ttu-id="78ccb-126">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="78ccb-126">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="78ccb-127">"DataAdapters" und "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="78ccb-127">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="78ccb-128">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="78ccb-128">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)
- [<span data-ttu-id="78ccb-129">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="78ccb-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
