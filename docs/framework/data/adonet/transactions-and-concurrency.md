---
title: Transaktionen und Parallelität
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: 049e402345e1abbb46739e48c89101207a43bb27
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191670"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="305f2-102">Transaktionen und Parallelität</span><span class="sxs-lookup"><span data-stu-id="305f2-102">Transactions and Concurrency</span></span>

<span data-ttu-id="305f2-103">Eine Transaktion besteht aus einem einzelnen Befehl oder einer Gruppe von Befehlen, die als Paket ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="305f2-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="305f2-104">Mit Transaktionen können Sie mehrere Operationen in einem Arbeitsschritt zusammenfassen.</span><span class="sxs-lookup"><span data-stu-id="305f2-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="305f2-105">Wenn an einer Stelle in der Transaktion ein Fehler auftritt, kann für alle Updates ein Rollback zum Zustand vor der Transaktion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="305f2-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="305f2-106">Eine Transaktion muss zur Gewährleistung der Datenkonsistenz die folgenden vier Kriterien, die so genannten ACID-Kriterien, erfüllen: Atomicity (Atomarität), Consistency (Konsistenz), Isolation und Durability (Dauerhaftigkeit).</span><span class="sxs-lookup"><span data-stu-id="305f2-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="305f2-107">Die meisten relationalen Datenbanksysteme (z. B. Microsoft SQL Server) unterstützen Transaktionen, indem sie für Update-, Einfüge- oder Löschvorgänge, die durch eine Clientanwendung ausgeführt werden, entsprechende Sperr-, Protokollierungs- und Transaktionsverwaltungsfunktionen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="305f2-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="305f2-108">Transaktionen, an denen mehrere Ressourcen beteiligt sind, können die Parallelität senken, wenn Sperren zu lang gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="305f2-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="305f2-109">Halten Sie Transaktionen daher so kurz wie möglich.</span><span class="sxs-lookup"><span data-stu-id="305f2-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="305f2-110">Wenn an einer Transaktion mehrere Tabellen in derselben Datenbank oder auf demselben Server beteiligt sind, bieten explizite Transaktionen in gespeicherten Prozeduren oft eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="305f2-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="305f2-111">Transaktionen in gespeicherten SQL Server-Prozeduren können Sie mithilfe der Transact-SQL-Anweisungen `BEGIN TRANSACTION`, `COMMIT TRANSACTION` und `ROLLBACK TRANSACTION` erstellen.</span><span class="sxs-lookup"><span data-stu-id="305f2-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="305f2-112">Weitere Informationen finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="305f2-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="305f2-113">Transaktionen, die verschiedene Ressourcen-Manager betreffen, wie z. b. eine Transaktion zwischen SQL Server und Oracle, erfordern eine verteilte Transaktion.</span><span class="sxs-lookup"><span data-stu-id="305f2-113">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="305f2-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="305f2-114">In This Section</span></span>  

 [<span data-ttu-id="305f2-115">Lokale Transaktionen</span><span class="sxs-lookup"><span data-stu-id="305f2-115">Local Transactions</span></span>](local-transactions.md)  
 <span data-ttu-id="305f2-116">Zeigt, wie Transaktionen für eine Datenbank ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="305f2-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 <span data-ttu-id="305f2-117">[Distributed Transactions](distributed-transactions.md) (Verteilte Transaktionen)</span><span class="sxs-lookup"><span data-stu-id="305f2-117">[Distributed Transactions](distributed-transactions.md)</span></span>  
 <span data-ttu-id="305f2-118">Beschreibt die Ausführung von verteilten Transaktionen in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="305f2-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="305f2-119">System.Transactions-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="305f2-119">System.Transactions Integration with SQL Server</span></span>](system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="305f2-120">Beschreibt die <xref:System.Transactions> Integration in SQL Server zum Arbeiten mit verteilten Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="305f2-120">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="305f2-121">Optimistische Nebenläufigkeit</span><span class="sxs-lookup"><span data-stu-id="305f2-121">Optimistic Concurrency</span></span>](optimistic-concurrency.md)  
 <span data-ttu-id="305f2-122">Beschreibt die vollständige und die eingeschränkte Parallelität und wie Sie auf Parallelitätsverletzungen testen können.</span><span class="sxs-lookup"><span data-stu-id="305f2-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305f2-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="305f2-123">See also</span></span>

- [<span data-ttu-id="305f2-124">Transaktionsgrundlagen</span><span class="sxs-lookup"><span data-stu-id="305f2-124">Transaction Fundamentals</span></span>](../transactions/transaction-fundamentals.md)
- [<span data-ttu-id="305f2-125">Herstellen der Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="305f2-125">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="305f2-126">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="305f2-126">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="305f2-127">"DataAdapters" und "DataReaders"</span><span class="sxs-lookup"><span data-stu-id="305f2-127">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="305f2-128">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="305f2-128">DbProviderFactories</span></span>](dbproviderfactories.md)
- [<span data-ttu-id="305f2-129">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="305f2-129">ADO.NET Overview</span></span>](ado-net-overview.md)
