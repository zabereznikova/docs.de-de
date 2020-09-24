---
title: System.Transactions-Integration in SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b555544e-7abb-4814-859b-ab9cdd7d8716
ms.openlocfilehash: 5adf40f96854e08736cdef77300d69e452de5eea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191683"
---
# <a name="systemtransactions-integration-with-sql-server"></a><span data-ttu-id="10982-102">System.Transactions-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="10982-102">System.Transactions Integration with SQL Server</span></span>

<span data-ttu-id="10982-103">In der .NET Framework Version 2,0 wurde ein Transaktions Framework eingeführt, auf das über den-Namespace zugegriffen werden kann <xref:System.Transactions> .</span><span class="sxs-lookup"><span data-stu-id="10982-103">The .NET Framework version 2.0 introduced a transaction framework that can be accessed through the <xref:System.Transactions> namespace.</span></span> <span data-ttu-id="10982-104">Dieses Framework macht Transaktionen auf eine Weise verfügbar, die voll in das .NET Framework einschließlich ADO.NET integriert ist.</span><span class="sxs-lookup"><span data-stu-id="10982-104">This framework exposes transactions in a way that is fully integrated in the .NET Framework, including ADO.NET.</span></span>  
  
 <span data-ttu-id="10982-105">Zusätzlich zu den Verbesserungen der Programmierbarkeit <xref:System.Transactions> können und ADO.net zusammenarbeiten, um Optimierungen bei der Arbeit mit Transaktionen zu koordinieren.</span><span class="sxs-lookup"><span data-stu-id="10982-105">In addition to the programmability enhancements, <xref:System.Transactions> and ADO.NET can work together to coordinate optimizations when you work with transactions.</span></span> <span data-ttu-id="10982-106">Eine heraufstufbare Transaktion ist eine kompakte (lokale) Transaktion, die automatisch bei Bedarf auf eine vollverteilte Transaktion höhergestuft werden kann.</span><span class="sxs-lookup"><span data-stu-id="10982-106">A promotable transaction is a lightweight (local) transaction that can be automatically promoted to a fully distributed transaction on an as-needed basis.</span></span>  
  
 <span data-ttu-id="10982-107">Ab ADO.NET 2,0 <xref:System.Data.SqlClient> unterstützt heraufstufbare Transaktionen, wenn Sie mit SQL Server arbeiten.</span><span class="sxs-lookup"><span data-stu-id="10982-107">Starting with ADO.NET 2.0, <xref:System.Data.SqlClient> supports promotable transactions when you work with SQL Server.</span></span> <span data-ttu-id="10982-108">Eine heraufstufbare Transaktion ruft den zusätzlichen Aufwand einer verteilten Transaktion nur hervor, wenn dieser erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="10982-108">A promotable transaction does not invoke the added overhead of a distributed transaction unless the added overhead is required.</span></span> <span data-ttu-id="10982-109">Heraufstufbare Transaktionen erfolgen automatisch und erfordern keinen Eingriff des Entwicklers.</span><span class="sxs-lookup"><span data-stu-id="10982-109">Promotable transactions are automatic and require no intervention from the developer.</span></span>  
  
 <span data-ttu-id="10982-110">Heraufstufbare Transaktionen sind nur verfügbar, wenn Sie die .NET Framework Datenanbieter für SQL Server ( `SqlClient` ) mit SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="10982-110">Promotable transactions are only available when you use the .NET Framework Data Provider for SQL Server (`SqlClient`) with SQL Server.</span></span>  
  
## <a name="creating-promotable-transactions"></a><span data-ttu-id="10982-111">Erstellen heraufstufbarer Transaktionen</span><span class="sxs-lookup"><span data-stu-id="10982-111">Creating Promotable Transactions</span></span>  

 <span data-ttu-id="10982-112">Der .NET Framework-Anbieter für SQL Server bietet Unterstützung für heraufstufbare Transaktionen, die über die Klassen im .NET Framework <xref:System.Transactions>-Namespace behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="10982-112">The .NET Framework Provider for SQL Server provides support for promotable transactions, which are handled through the classes in the .NET Framework <xref:System.Transactions> namespace.</span></span> <span data-ttu-id="10982-113">Heraufstufbare Transaktionen optimieren verteilte Transaktionen, indem sie das Erstellen einer verteilten Transaktion verzögern, bis diese benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="10982-113">Promotable transactions optimize distributed transactions by deferring creating a distributed transaction until it is needed.</span></span> <span data-ttu-id="10982-114">Wenn nur ein Ressourcen-Manager erforderlich ist, erfolgt keine verteilte Transaktion.</span><span class="sxs-lookup"><span data-stu-id="10982-114">If only one resource manager is required, no distributed transaction occurs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10982-115">In einem teilweise vertrauenswürdigen Szenario wird die <xref:System.Transactions.DistributedTransactionPermission> benötigt, wenn eine Transaktion zu einer verteilten Transaktion heraufgestuft wird.</span><span class="sxs-lookup"><span data-stu-id="10982-115">In a partially trusted scenario, the <xref:System.Transactions.DistributedTransactionPermission> is required when a transaction is promoted to a distributed transaction.</span></span>  
  
## <a name="promotable-transaction-scenarios"></a><span data-ttu-id="10982-116">Szenarien für heraufstufbare Transaktionen</span><span class="sxs-lookup"><span data-stu-id="10982-116">Promotable Transaction Scenarios</span></span>  

 <span data-ttu-id="10982-117">Heraufstufbare Transaktionen beanspruchen normalerweise erhebliche Systemressourcen und werden von MS DTC (Microsoft Distributed Transaction Coordinator) verwaltet, der alle Ressourcen-Manager integriert, auf die in der Transaktion zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="10982-117">Distributed transactions typically consume significant system resources, being managed by Microsoft Distributed Transaction Coordinator (MS DTC), which integrates all the resource managers accessed in the transaction.</span></span> <span data-ttu-id="10982-118">Eine heraufstufbare Transaktion ist eine besondere Form einer <xref:System.Transactions> Transaktion, die die Arbeit effektiv an eine einfache SQL Server Transaktion delegiert.</span><span class="sxs-lookup"><span data-stu-id="10982-118">A promotable transaction is a special form of a <xref:System.Transactions> transaction that effectively delegates the work to a simple SQL Server transaction.</span></span> <span data-ttu-id="10982-119"><xref:System.Transactions>, <xref:System.Data.SqlClient> und SQL Server die bei der Verarbeitung der Transaktion beteiligten Arbeit koordinieren und bei Bedarf auf eine vollständig verteilte Transaktion herauf Stufen.</span><span class="sxs-lookup"><span data-stu-id="10982-119"><xref:System.Transactions>, <xref:System.Data.SqlClient>, and SQL Server coordinate the work involved in handling the transaction, promoting it to a full distributed transaction as needed.</span></span>  
  
 <span data-ttu-id="10982-120">Der Vorteil der Verwendung heraufstufbarer Transaktionen besteht darin, dass beim Öffnen einer Verbindung mit einer aktiven <xref:System.Transactions.TransactionScope> -Transaktion die Transaktion als kompakte Transaktion durchgeführt wird, wenn keine weiteren Verbindungen geöffnet sind und der zusätzliche Mehraufwand einer vollständig verteilten Transaktion vermieden werden kann.</span><span class="sxs-lookup"><span data-stu-id="10982-120">The benefit of using promotable transactions is that when a connection is opened by using an active <xref:System.Transactions.TransactionScope> transaction, and no other connections are opened, the transaction commits as a lightweight transaction, instead of incurring the additional overhead of a full distributed transaction.</span></span>  
  
### <a name="connection-string-keywords"></a><span data-ttu-id="10982-121">Schlüsselwörter für Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="10982-121">Connection String Keywords</span></span>  

 <span data-ttu-id="10982-122">Die <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> -Eigenschaft unterstützt ein Schlüsselwort, `Enlist`, das angibt, ob der <xref:System.Data.SqlClient> Transaktionskontexte erkennt, und die Verbindung automatisch in einer verteilten Transaktion einträgt.</span><span class="sxs-lookup"><span data-stu-id="10982-122">The <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property supports a keyword, `Enlist`, which indicates whether <xref:System.Data.SqlClient> will detect transactional contexts and automatically enlist the connection in a distributed transaction.</span></span> <span data-ttu-id="10982-123">Wenn `Enlist=true`, wird die Verbindung automatisch im aktuellen Transaktionskontext des öffnenden Threads eingetragen.</span><span class="sxs-lookup"><span data-stu-id="10982-123">If `Enlist=true`, the connection is automatically enlisted in the opening thread's current transaction context.</span></span> <span data-ttu-id="10982-124">Wenn `Enlist=false`, interagiert der `SqlClient` nicht mit einer verteilten Transaktion.</span><span class="sxs-lookup"><span data-stu-id="10982-124">If `Enlist=false`, the `SqlClient` connection does not interact with a distributed transaction.</span></span> <span data-ttu-id="10982-125">Der Standardwert für `Enlist` ist "true".</span><span class="sxs-lookup"><span data-stu-id="10982-125">The default value for `Enlist` is true.</span></span> <span data-ttu-id="10982-126">Wenn `Enlist` in der Verbindungszeichenfolge nicht angegeben ist, wird die Verbindung automatisch in einer verteilten Transaktion eingetragen, wenn eine solche zum Zeitpunkt des Öffnens der Verbindung erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="10982-126">If `Enlist` is not specified in the connection string, the connection is automatically enlisted in a distributed transaction if one is detected when the connection is opened.</span></span>  
  
 <span data-ttu-id="10982-127">Die `Transaction Binding` -Schlüsselwörter in einer <xref:System.Data.SqlClient.SqlConnection> -Verbindungszeichenfolge steuern die Zuordnung einer Verbindung mit einer eingetragenen `System.Transactions` -Transaktion.</span><span class="sxs-lookup"><span data-stu-id="10982-127">The `Transaction Binding` keywords in a <xref:System.Data.SqlClient.SqlConnection> connection string control the connection's association with an enlisted `System.Transactions` transaction.</span></span> <span data-ttu-id="10982-128">Diese ist auch verfügbar durch die <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> -Eigenschaft eines <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="10982-128">It is also available through the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> property of a <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span>  
  
 <span data-ttu-id="10982-129">In der folgenden Tabelle sind die möglichen Werte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="10982-129">The following table describes the possible values.</span></span>  
  
|<span data-ttu-id="10982-130">Stichwort</span><span class="sxs-lookup"><span data-stu-id="10982-130">Keyword</span></span>|<span data-ttu-id="10982-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="10982-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10982-132">Implicit Unbind</span><span class="sxs-lookup"><span data-stu-id="10982-132">Implicit Unbind</span></span>|<span data-ttu-id="10982-133">Der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="10982-133">The default.</span></span> <span data-ttu-id="10982-134">Die Verbindung wird von der Transaktion getrennt, wenn diese endet, und wechselt damit zurück in den Autocommit-Modus.</span><span class="sxs-lookup"><span data-stu-id="10982-134">The connection detaches from the transaction when it ends, switching back to autocommit mode.</span></span>|  
|<span data-ttu-id="10982-135">Explicit Unbind</span><span class="sxs-lookup"><span data-stu-id="10982-135">Explicit Unbind</span></span>|<span data-ttu-id="10982-136">Die Verbindung bleibt so lange an die Transaktion gebunden, bis die Transaktion geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="10982-136">The connection remains attached to the transaction until the transaction is closed.</span></span> <span data-ttu-id="10982-137">Die Verbindung schlägt fehl, wenn die zugehörige Transaktion nicht aktiv ist oder <xref:System.Transactions.Transaction.Current%2A>nicht entspricht.</span><span class="sxs-lookup"><span data-stu-id="10982-137">The connection will fail if the associated transaction is not active or does not match <xref:System.Transactions.Transaction.Current%2A>.</span></span>|  
  
## <a name="using-transactionscope"></a><span data-ttu-id="10982-138">Verwenden von "TransactionScope"</span><span class="sxs-lookup"><span data-stu-id="10982-138">Using TransactionScope</span></span>  

 <span data-ttu-id="10982-139">Die <xref:System.Transactions.TransactionScope>-Klasse bewirkt, dass ein Codeblock transaktional wird, indem sie Verbindungen implizit in einer verteilten Transaktion einträgt.</span><span class="sxs-lookup"><span data-stu-id="10982-139">The <xref:System.Transactions.TransactionScope> class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="10982-140">Sie müssen die <xref:System.Transactions.TransactionScope.Complete%2A> -Methode am Ende des <xref:System.Transactions.TransactionScope> -Blocks vor dem Verlassen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="10982-140">You must call the <xref:System.Transactions.TransactionScope.Complete%2A> method at the end of the <xref:System.Transactions.TransactionScope> block before leaving it.</span></span> <span data-ttu-id="10982-141">Beim Verlassen des Blocks wird die <xref:System.Transactions.TransactionScope.Dispose%2A> -Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="10982-141">Leaving the block invokes the <xref:System.Transactions.TransactionScope.Dispose%2A> method.</span></span> <span data-ttu-id="10982-142">Wenn eine Ausnahme aufgerufen wurde, die den Code veranlasst, den Bereich zu verlassen, wird die Transaktion als abgebrochen angesehen.</span><span class="sxs-lookup"><span data-stu-id="10982-142">If an exception has been thrown that causes the code to leave scope, the transaction is considered aborted.</span></span>  
  
 <span data-ttu-id="10982-143">Es wird empfohlen, einen `using` -Block zu verwenden, um sicherzustellen, dass <xref:System.Transactions.TransactionScope.Dispose%2A> für das <xref:System.Transactions.TransactionScope> -Objekt aufgerufen wird, wenn der verwendete Block beendet wird.</span><span class="sxs-lookup"><span data-stu-id="10982-143">We recommend that you use a `using` block to make sure that <xref:System.Transactions.TransactionScope.Dispose%2A> is called on the <xref:System.Transactions.TransactionScope> object when the using block is exited.</span></span> <span data-ttu-id="10982-144">Durch das Fehlschlagen von Commits oder Rollbacks ausstehender Transaktionen kann die Leistung entscheidend beeinträchtigt werden, da das Zeitlimit für <xref:System.Transactions.TransactionScope> eine Minute beträgt.</span><span class="sxs-lookup"><span data-stu-id="10982-144">Failure to commit or roll back pending transactions can significantly damage performance because the default time-out for the <xref:System.Transactions.TransactionScope> is one minute.</span></span> <span data-ttu-id="10982-145">Wenn Sie keine `using`-Anweisung verwenden, müssen Sie alle Arbeiten in einem `Try`-Block ausführen und die <xref:System.Transactions.TransactionScope.Dispose%2A>-Methode im `Finally`-Block explizit aufrufen.</span><span class="sxs-lookup"><span data-stu-id="10982-145">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the <xref:System.Transactions.TransactionScope.Dispose%2A> method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="10982-146">Wenn innerhalb des <xref:System.Transactions.TransactionScope>eine Ausnahme auftritt, wird die Transaktion als inkonsistent markiert und abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="10982-146">If an exception occurs in the <xref:System.Transactions.TransactionScope>, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="10982-147">Sie wird zurückgesetzt, wenn der <xref:System.Transactions.TransactionScope> verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="10982-147">It will be rolled back when the <xref:System.Transactions.TransactionScope> is disposed.</span></span> <span data-ttu-id="10982-148">Wenn keine Ausnahme auftritt, wird für teilnehmende Transaktionen ein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="10982-148">If no exception occurs, participating transactions commit.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10982-149">Die `TransactionScope`-Klasse erstellt <xref:System.Transactions.Transaction.IsolationLevel%2A> standardmäßig mit dem Wert `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="10982-149">The `TransactionScope` class creates a transaction with a <xref:System.Transactions.Transaction.IsolationLevel%2A> of `Serializable` by default.</span></span> <span data-ttu-id="10982-150">Je nach Ihrer Anwendung kann es vorteilhaft sein, die Isolationsstufe herabzusetzen, um ein hohes Konfliktpotenzial in der Anwendung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="10982-150">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10982-151">Es wird empfohlen, dass Sie nur Update-, Einfüge- und Löschvorgänge in verteilten Transaktionen durchführen, da diese erhebliche Datenbankressorcen beanspruchen.</span><span class="sxs-lookup"><span data-stu-id="10982-151">We recommend that you perform only updates, inserts, and deletes within distributed transactions because they consume significant database resources.</span></span> <span data-ttu-id="10982-152">Select-Anweisungen können Datenbankressourcen unnötigerweise blockieren, und in einigen Szenarien kann es erforderlich sein, Transaktionen für Select-Vorgänge zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="10982-152">Select statements may lock database resources unnecessarily, and in some scenarios, you may have to use transactions for selects.</span></span> <span data-ttu-id="10982-153">Arbeiten, die nicht mit der Datenbank zusammenhängen, sollten außerhalb des Bereichs der Transaktion durchgeführt werden, außer wenn andere transaktive Ressourcen-Manager verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10982-153">Any non-database work should be done outside the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="10982-154">Obwohl eine Ausnahme innerhalb des Bereichs der Transaktion dazu führt, dass die Transaktion keinen Commit ausführt, verfügt die <xref:System.Transactions.TransactionScope> -Klasse über keine Funktion zum Zurücksetzen von Änderungen, die vom Code außerhalb des Bereichs der Transaktion selbst durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="10982-154">Although an exception in the scope of the transaction prevents the transaction from committing, the <xref:System.Transactions.TransactionScope> class has no provision for rolling back any changes your code has made outside the scope of the transaction itself.</span></span> <span data-ttu-id="10982-155">Wenn Sie beim Zurücksetzen der Transaktion Maßnahmen ergreifen müssen, müssen Sie Ihre eigene Implementierung der <xref:System.Transactions.IEnlistmentNotification> -Schnittstelle schreiben und in der Transaktion explizit eintragen.</span><span class="sxs-lookup"><span data-stu-id="10982-155">If you have to take some action when the transaction is rolled back, you must write your own implementation of the <xref:System.Transactions.IEnlistmentNotification> interface and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10982-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10982-156">Example</span></span>  

 <span data-ttu-id="10982-157">Das Arbeiten mit <xref:System.Transactions> setzt einen Verweis auf "System.Transactions.dll" voraus.</span><span class="sxs-lookup"><span data-stu-id="10982-157">Working with <xref:System.Transactions> requires that you have a reference to System.Transactions.dll.</span></span>  
  
 <span data-ttu-id="10982-158">Die folgende Funktion zeigt das Erstellen einer heraufstufbaren Transaktion für zwei verschiedene SQL Server-Instanzen, die von zwei verschiedenen <xref:System.Data.SqlClient.SqlConnection> -Objekten dargestellt werden, die ihrerseits von einem <xref:System.Transactions.TransactionScope> -Block umschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="10982-158">The following function demonstrates how to create a promotable transaction against two different SQL Server instances, represented by two different <xref:System.Data.SqlClient.SqlConnection> objects, which are wrapped in a <xref:System.Transactions.TransactionScope> block.</span></span> <span data-ttu-id="10982-159">Der Code erstellt den <xref:System.Transactions.TransactionScope> -Block mit einer `using` -Anweisung und öffnet die erste Verbindung, durch die er automatisch im <xref:System.Transactions.TransactionScope>eingetragen wird.</span><span class="sxs-lookup"><span data-stu-id="10982-159">The code creates the <xref:System.Transactions.TransactionScope> block with a `using` statement and opens the first connection, which automatically enlists it in the <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="10982-160">Die Transaktion wird anfänglich als einfache Transaktion, nicht als vollständig verteilte Transaktion, eingetragen.</span><span class="sxs-lookup"><span data-stu-id="10982-160">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="10982-161">Die zweite Verbindung wird nur dann im <xref:System.Transactions.TransactionScope> eingetragen, wenn der Befehl in der ersten Verbindung keine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="10982-161">The second connection is enlisted in the <xref:System.Transactions.TransactionScope> only if the command in the first connection does not throw an exception.</span></span> <span data-ttu-id="10982-162">Wenn die zweite Verbindung geöffnet wird, wird die Transaktion automatisch auf eine vollständig verteilte Transaktion hochgestuft.</span><span class="sxs-lookup"><span data-stu-id="10982-162">When the second connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="10982-163">Es wird die <xref:System.Transactions.TransactionScope.Complete%2A> -Methode aufgerufen, die für die Transaktion nur dann einen Commit ausführt, wenn keine Ausnahmen ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="10982-163">The <xref:System.Transactions.TransactionScope.Complete%2A> method is invoked, which commits the transaction only if no exceptions have been thrown.</span></span> <span data-ttu-id="10982-164">Wenn an einem beliebigen Punkt im <xref:System.Transactions.TransactionScope> -Block eine Ausnahme ausgelöst wurde, wird `Complete` nicht aufgerufen, und die verteilte Transaktion wird zurückgenommen, sobald der <xref:System.Transactions.TransactionScope> am Ende seines `using` -Blocks verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="10982-164">If an exception has been thrown at any point in the <xref:System.Transactions.TransactionScope> block, `Complete` will not be called, and the distributed transaction will roll back when the <xref:System.Transactions.TransactionScope> is disposed at the end of its `using` block.</span></span>  
  
```csharp  
// This function takes arguments for the 2 connection strings and commands in order  
// to create a transaction involving two SQL Servers. It returns a value > 0 if the  
// transaction committed, 0 if the transaction rolled back. To test this code, you can
// connect to two different databases on the same server by altering the connection string,  
// or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
static public int CreateTransactionScope(  
    string connectString1, string connectString2,  
    string commandText1, string commandText2)  
{  
    // Initialize the return value to zero and create a StringWriter to display results.  
    int returnValue = 0;  
    System.IO.StringWriter writer = new System.IO.StringWriter();  
  
    // Create the TransactionScope in which to execute the commands, guaranteeing  
    // that both commands will commit or roll back as a single unit of work.  
    using (TransactionScope scope = new TransactionScope())  
    {  
        using (SqlConnection connection1 = new SqlConnection(connectString1))  
        {  
            try  
            {  
                // Opening the connection automatically enlists it in the
                // TransactionScope as a lightweight transaction.  
                connection1.Open();  
  
                // Create the SqlCommand object and execute the first command.  
                SqlCommand command1 = new SqlCommand(commandText1, connection1);  
                returnValue = command1.ExecuteNonQuery();  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue);  
  
                // if you get here, this means that command1 succeeded. By nesting  
                // the using block for connection2 inside that of connection1, you  
                // conserve server and network resources by opening connection2
                // only when there is a chance that the transaction can commit.
                using (SqlConnection connection2 = new SqlConnection(connectString2))  
                    try  
                    {  
                        // The transaction is promoted to a full distributed  
                        // transaction when connection2 is opened.  
                        connection2.Open();  
  
                        // Execute the second command in the second database.  
                        returnValue = 0;  
                        SqlCommand command2 = new SqlCommand(commandText2, connection2);  
                        returnValue = command2.ExecuteNonQuery();  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue);  
                    }  
                    catch (Exception ex)  
                    {  
                        // Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue);  
                        writer.WriteLine("Exception Message2: {0}", ex.Message);  
                    }  
            }  
            catch (Exception ex)  
            {  
                // Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue);  
                writer.WriteLine("Exception Message1: {0}", ex.Message);  
            }  
        }  
  
        // If an exception has been thrown, Complete will not
        // be called and the transaction is rolled back.  
        scope.Complete();  
    }  
  
    // The returnValue is greater than 0 if the transaction committed.  
    if (returnValue > 0)  
    {  
        writer.WriteLine("Transaction was committed.");  
    }  
    else  
    {  
        // You could write additional business logic here, notify the caller by  
        // throwing a TransactionAbortedException, or log the failure.  
        writer.WriteLine("Transaction rolled back.");  
    }  
  
    // Display messages.  
    Console.WriteLine(writer.ToString());  
  
    return returnValue;  
}  
```  
  
```vb  
' This function takes arguments for the 2 connection strings and commands in order  
' to create a transaction involving two SQL Servers. It returns a value > 0 if the  
' transaction committed, 0 if the transaction rolled back. To test this code, you can
' connect to two different databases on the same server by altering the connection string,  
' or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
Public Function CreateTransactionScope( _  
  ByVal connectString1 As String, ByVal connectString2 As String, _  
  ByVal commandText1 As String, ByVal commandText2 As String) As Integer  
  
    ' Initialize the return value to zero and create a StringWriter to display results.  
    Dim returnValue As Integer = 0  
    Dim writer As System.IO.StringWriter = New System.IO.StringWriter  
  
    ' Create the TransactionScope in which to execute the commands, guaranteeing  
    ' that both commands will commit or roll back as a single unit of work.  
    Using scope As New TransactionScope()  
        Using connection1 As New SqlConnection(connectString1)  
            Try  
                ' Opening the connection automatically enlists it in the
                ' TransactionScope as a lightweight transaction.  
                connection1.Open()  
  
                ' Create the SqlCommand object and execute the first command.  
                Dim command1 As SqlCommand = New SqlCommand(commandText1, connection1)  
                returnValue = command1.ExecuteNonQuery()  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue)  
  
                ' If you get here, this means that command1 succeeded. By nesting  
                ' the Using block for connection2 inside that of connection1, you  
                ' conserve server and network resources by opening connection2
                ' only when there is a chance that the transaction can commit.
                Using connection2 As New SqlConnection(connectString2)  
                    Try  
                        ' The transaction is promoted to a full distributed  
                        ' transaction when connection2 is opened.  
                        connection2.Open()  
  
                        ' Execute the second command in the second database.  
                        returnValue = 0  
                        Dim command2 As SqlCommand = New SqlCommand(commandText2, connection2)  
                        returnValue = command2.ExecuteNonQuery()  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue)  
  
                    Catch ex As Exception  
                        ' Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue)  
                        writer.WriteLine("Exception Message2: {0}", ex.Message)  
                    End Try  
                End Using  
  
            Catch ex As Exception  
                ' Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue)  
                writer.WriteLine("Exception Message1: {0}", ex.Message)  
            End Try  
        End Using  
  
        ' If an exception has been thrown, Complete will
        ' not be called and the transaction is rolled back.  
        scope.Complete()  
    End Using  
  
    ' The returnValue is greater than 0 if the transaction committed.  
    If returnValue > 0 Then  
        writer.WriteLine("Transaction was committed.")  
    Else  
        ' You could write additional business logic here, notify the caller by  
        ' throwing a TransactionAbortedException, or log the failure.  
       writer.WriteLine("Transaction rolled back.")  
     End If  
  
    ' Display messages.  
    Console.WriteLine(writer.ToString())  
  
    Return returnValue  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="10982-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10982-165">See also</span></span>

- [<span data-ttu-id="10982-166">Transaktionen und Parallelität</span><span class="sxs-lookup"><span data-stu-id="10982-166">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="10982-167">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="10982-167">ADO.NET Overview</span></span>](ado-net-overview.md)
