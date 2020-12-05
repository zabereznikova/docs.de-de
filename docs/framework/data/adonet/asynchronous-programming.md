---
title: Asynchrone Programmierung
description: Erfahren Sie mehr über die asynchrone Programmierung in den .NET Framework Datenanbieter für SQL Server, einschließlich der in .NET Framework 4,5 eingeführten Erweiterungen.
ms.date: 10/18/2018
ms.assetid: 85da7447-7125-426e-aa5f-438a290d1f77
ms.openlocfilehash: fe3551d8c7bea9c9218656bd6ae5047a7920f384
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739927"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="63f9f-103">Asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="63f9f-103">Asynchronous Programming</span></span>

<span data-ttu-id="63f9f-104">In diesem Thema wird die Unterstützung der asynchronen Programmierung in der .NET Framework Datenanbieter für SQL Server (SqlClient) erläutert, einschließlich der Erweiterungen, die zur Unterstützung der asynchronen Programmier Funktionalität in .NET Framework 4,5 eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="63f9f-104">This topic discusses support for asynchronous programming in the .NET Framework Data Provider for SQL Server (SqlClient) including enhancements made to support asynchronous programming functionality that was introduced in .NET Framework 4.5.</span></span>

## <a name="legacy-asynchronous-programming"></a><span data-ttu-id="63f9f-105">Asynchrone Programmierung (Legacy)</span><span class="sxs-lookup"><span data-stu-id="63f9f-105">Legacy Asynchronous Programming</span></span>

<span data-ttu-id="63f9f-106">Vor .NET Framework 4,5 wurde die asynchrone Programmierung mit SqlClient mit den folgenden Methoden und der Connection- `Asynchronous Processing=true` Eigenschaft durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="63f9f-106">Prior to .NET Framework 4.5, asynchronous programming with SqlClient was done with the following methods and the `Asynchronous Processing=true` connection property:</span></span>

1. <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A?displayProperty=nameWithType>

2. <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A?displayProperty=nameWithType>

3. <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A?displayProperty=nameWithType>

<span data-ttu-id="63f9f-107">Diese Funktion verbleibt in SqlClient in .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="63f9f-107">This functionality remains in SqlClient in .NET Framework 4.5.</span></span>

> [!TIP]
> <span data-ttu-id="63f9f-108">Ab der .NET Framework 4,5 benötigen diese Legacy Methoden nicht mehr `Asynchronous Processing=true` in der Verbindungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="63f9f-108">Beginning in the .NET Framework 4.5, these legacy methods no longer require `Asynchronous Processing=true` in the connection string.</span></span>

## <a name="asynchronous-programming-features-added-in-net-framework-45"></a><span data-ttu-id="63f9f-109">In .NET Framework 4,5 hinzugefügte Funktionen für die asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="63f9f-109">Asynchronous Programming Features Added in .NET Framework 4.5</span></span>

<span data-ttu-id="63f9f-110">Die neue Funktion für asynchrone Programmierung bietet eine einfache Möglichkeit, Code asynchron ausführen.</span><span class="sxs-lookup"><span data-stu-id="63f9f-110">The new asynchronous programming feature provides a simple technique to make code asynchronous.</span></span>

<span data-ttu-id="63f9f-111">Weitere Informationen zum asynchronen Programmier Feature, das in .NET Framework 4,5 eingeführt wurde, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="63f9f-111">For more information about the asynchronous programming feature that was introduced in .NET Framework 4.5, see:</span></span>

- [<span data-ttu-id="63f9f-112">Asynchrone Programmierung in C#</span><span class="sxs-lookup"><span data-stu-id="63f9f-112">Asynchronous programming in C#</span></span>](../../../csharp/async.md)

- [<span data-ttu-id="63f9f-113">Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63f9f-113">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)

- [<span data-ttu-id="63f9f-114">Verwenden der neuen Async-Methoden von SqlDataReader in .NET Framework 4,5 (Teil 1)</span><span class="sxs-lookup"><span data-stu-id="63f9f-114">Using SqlDataReader’s new async methods in .NET Framework 4.5 (Part 1)</span></span>](/archive/blogs/adonet/using-sqldatareaders-new-async-methods-in-net-4-5)

- [<span data-ttu-id="63f9f-115">Verwenden der neuen Async-Methoden von SqlDataReader in .NET Framework 4,5 (Teil 2)</span><span class="sxs-lookup"><span data-stu-id="63f9f-115">Using SqlDataReader’s new async methods in .NET Framework 4.5 (Part 2)</span></span>](/archive/blogs/adonet/using-sqldatareaders-new-async-methods-in-net-4-5-part-2-examples)

<span data-ttu-id="63f9f-116">Wenn die Benutzeroberfläche nicht mehr reagiert oder der Server nicht skaliert, ist es wahrscheinlich, dass Sie den Code asynchroner programmieren müssen.</span><span class="sxs-lookup"><span data-stu-id="63f9f-116">When your user interface is unresponsive or your server does not scale, it is likely that you need your code to be more asynchronous.</span></span> <span data-ttu-id="63f9f-117">Das Schreiben von asynchronem Code umfasste üblicherweise die Installation eines Rückrufs (auch als Fortsetzung bekannt), um die Logik auszudrücken, die nach Ende des asynchronen Vorgangs ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="63f9f-117">Writing asynchronous code has traditionally involved installing a callback (also called continuation) to express the logic that occurs after the asynchronous operation finishes.</span></span> <span data-ttu-id="63f9f-118">Dadurch wird die Struktur des asynchronen Codes im Vergleich zu synchronem Code komplizierter.</span><span class="sxs-lookup"><span data-stu-id="63f9f-118">This complicates the structure of asynchronous code as compared with synchronous code.</span></span>

<span data-ttu-id="63f9f-119">Sie können nun Aufrufe in asynchrone Methoden ohne Rückrufe ausführen, und ohne Code auf mehrere Methoden oder Lambdaausdrücke zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="63f9f-119">You can now call into asynchronous methods without using callbacks, and without splitting your code across multiple methods or lambda expressions.</span></span>

<span data-ttu-id="63f9f-120">Der `async`-Modifizierer gibt an, dass eine Methode asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="63f9f-120">The `async` modifier specifies that a method is asynchronous.</span></span> <span data-ttu-id="63f9f-121">Wenn eine `async`-Methode aufgerufen wird, wird eine Aufgabe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="63f9f-121">When calling an `async` method, a task is returned.</span></span> <span data-ttu-id="63f9f-122">Wenn der- `await` Operator auf eine Aufgabe angewendet wird, wird die aktuelle Methode sofort beendet.</span><span class="sxs-lookup"><span data-stu-id="63f9f-122">When the `await` operator is applied to a task, the current method exits immediately.</span></span> <span data-ttu-id="63f9f-123">Nach Beendigung der Aufgabe wird die Ausführung in derselben Methode fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="63f9f-123">When the task finishes, execution resumes in the same method.</span></span>

> [!WARNING]
> <span data-ttu-id="63f9f-124">Asynchrone Aufrufe werden nicht unterstützt, wenn eine Anwendung auch das `Context Connection`-Schlüsselwort für Verbindungszeichenfolgen verwendet.</span><span class="sxs-lookup"><span data-stu-id="63f9f-124">Asynchronous calls are not supported if an application also uses the `Context Connection` connection string keyword.</span></span>

<span data-ttu-id="63f9f-125">Durch den Aufruf einer `async`-Methode werden keine weiteren Threads zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="63f9f-125">Calling an `async` method does not allocate any additional threads.</span></span> <span data-ttu-id="63f9f-126">Der vorhandene E/A-Abschlussthread wird möglicherweise kurz am Ende verwendet.</span><span class="sxs-lookup"><span data-stu-id="63f9f-126">It may use the existing I/O completion thread briefly at the end.</span></span>

<span data-ttu-id="63f9f-127">Die folgenden Methoden wurden in .NET Framework 4,5 hinzugefügt, um die asynchrone Programmierung zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="63f9f-127">The following methods were added in .NET Framework 4.5 to support asynchronous programming:</span></span>

- <xref:System.Data.Common.DbConnection.OpenAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteDbDataReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteNonQueryAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteScalarAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbDataReader.GetFieldValueAsync%2A>

- <xref:System.Data.Common.DbDataReader.IsDBNullAsync%2A>

- <xref:System.Data.Common.DbDataReader.NextResultAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbDataReader.ReadAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlConnection.OpenAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQueryAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteScalarAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteXmlReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlDataReader.NextResultAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlDataReader.ReadAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType>

 <span data-ttu-id="63f9f-128">Andere asynchrone Member wurden zur Unterstützung der [SqlClient-Streamingunterstützung](sqlclient-streaming-support.md)hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63f9f-128">Other asynchronous members were added to support [SqlClient Streaming Support](sqlclient-streaming-support.md).</span></span>

> [!TIP]
> <span data-ttu-id="63f9f-129">Die neuen asynchronen Methoden erfordern nicht `Asynchronous Processing=true` in der Verbindungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="63f9f-129">The new asynchronous methods don't require `Asynchronous Processing=true` in the connection string.</span></span>

### <a name="synchronous-to-asynchronous-connection-open"></a><span data-ttu-id="63f9f-130">„Synchron-zu-Asynchron-Verbindung“ geöffnet</span><span class="sxs-lookup"><span data-stu-id="63f9f-130">Synchronous to Asynchronous Connection Open</span></span>

<span data-ttu-id="63f9f-131">Sie können eine vorhandene Anwendung für die Verwendung der neuen asynchronen Funktion aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="63f9f-131">You can upgrade an existing application to use the new asynchronous feature.</span></span> <span data-ttu-id="63f9f-132">Angenommen, eine Anwendung verfügt über einen synchronen Verbindungsalgorithmus und blockiert den Benutzeroberflächenthread bei jeder Verbindung mit der Datenbank. Außerdem ruft die Anwendung, sobald sie verbunden ist, eine gespeicherte Prozedur auf, die anderen Benutzern den gerade angemeldeten Benutzer signalisiert.</span><span class="sxs-lookup"><span data-stu-id="63f9f-132">For example, assume an application has a synchronous connection algorithm and blocks the UI thread every time it connects to the database and, once connected, the application calls a stored procedure that signals other users of the one who just signed in.</span></span>

```csharp
using SqlConnection conn = new SqlConnection("…");
{
   conn.Open();
   using (SqlCommand cmd = new SqlCommand("StoredProcedure_Logon", conn))
   {
      cmd.ExecuteNonQuery();
   }
}
```

<span data-ttu-id="63f9f-133">Das für die Verwendung der neuen asynchronen Funktionalität konvertierte Programm sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="63f9f-133">When converted to use the new asynchronous functionality, the program would look like:</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;

class A {

   static async Task<int> Method(SqlConnection conn, SqlCommand cmd) {
      await conn.OpenAsync();
      await cmd.ExecuteNonQueryAsync();
      return 1;
   }

   public static void Main() {
      using (SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI")) {
         SqlCommand command = new SqlCommand("select top 2 * from orders", conn);

         int result = A.Method(conn, command).Result;

         SqlDataReader reader = command.ExecuteReader();
         while (reader.Read())
            Console.WriteLine(reader[0]);
      }
   }
}
```

### <a name="adding-the-new-asynchronous-feature-in-an-existing-application-mixing-old-and-new-patterns"></a><span data-ttu-id="63f9f-134">Hinzufügen der neuen asynchronen Funktion in einer vorhandenen Anwendung (Mischen alter und neuer Muster)</span><span class="sxs-lookup"><span data-stu-id="63f9f-134">Adding the New Asynchronous Feature in an Existing Application (Mixing Old and New Patterns)</span></span>

<span data-ttu-id="63f9f-135">Es ist auch möglich, neue asynchrone Funktionen (SqlConnection::OpenAsync) hinzuzufügen, ohne die vorhandene asynchrone Logik zu ändern.</span><span class="sxs-lookup"><span data-stu-id="63f9f-135">It is also possible to add new asynchronous capability (SqlConnection::OpenAsync) without changing the existing asynchronous logic.</span></span> <span data-ttu-id="63f9f-136">Wenn eine Anwendung derzeit beispielsweise folgenden Code verwendet...</span><span class="sxs-lookup"><span data-stu-id="63f9f-136">For example, if an application currently uses:</span></span>

```csharp
AsyncCallback productList = new AsyncCallback(ProductList);
SqlConnection conn = new SqlConnection("…");
conn.Open();
SqlCommand cmd = new SqlCommand("SELECT * FROM [Current Product List]", conn);
IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);
```

<span data-ttu-id="63f9f-137">...können Sie das neue asynchrone Muster direkt verwenden, ohne den vorhandenen Algorithmus erheblich zu ändern.</span><span class="sxs-lookup"><span data-stu-id="63f9f-137">You can begin to use the new asynchronous pattern without substantially changing the existing algorithm.</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;

class A {
   static void ProductList(IAsyncResult result) { }

   public static void Main() {
      // AsyncCallback productList = new AsyncCallback(ProductList);
      // SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI");
      // conn.Open();
      // SqlCommand cmd = new SqlCommand("select top 2 * from orders", conn);
      // IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);

      AsyncCallback productList = new AsyncCallback(ProductList);
      SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI");
      conn.OpenAsync().ContinueWith((task) => {
         SqlCommand cmd = new SqlCommand("select top 2 * from orders", conn);
         IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);
      }, TaskContinuationOptions.OnlyOnRanToCompletion);
   }
}
```

### <a name="using-the-base-provider-model-and-the-new-asynchronous-feature"></a><span data-ttu-id="63f9f-138">Verwenden des Basisanbietermodells und der neuen asynchronen Funktion</span><span class="sxs-lookup"><span data-stu-id="63f9f-138">Using the Base Provider Model and the New Asynchronous Feature</span></span>

<span data-ttu-id="63f9f-139">Möglicherweise müssen Sie ein Tool erstellen, das eine Verbindung mit verschiedenen Datenbanken herstellen und Abfragen ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="63f9f-139">You may need to create a tool that is able to connect to different databases and execute queries.</span></span> <span data-ttu-id="63f9f-140">Sie können das Basisanbietermodell und die neue asynchrone Funktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="63f9f-140">You can use the base provider model and the new asynchronous feature.</span></span>

<span data-ttu-id="63f9f-141">Microsoft Distributed Transaction Controller (MSDTC) muss auf dem Server aktiviert sein, damit verteilte Transaktionen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="63f9f-141">The Microsoft Distributed Transaction Controller (MSDTC) must be enabled on the server to use distributed transactions.</span></span> <span data-ttu-id="63f9f-142">Informationen zum Aktivieren von MSDTC finden Sie unter [Aktivieren von MSDTC auf einem Webserver](/previous-versions/commerce-server/dd327979(v=cs.90)).</span><span class="sxs-lookup"><span data-stu-id="63f9f-142">For information on how to enable MSDTC, see [How to Enable MSDTC on a Web Server](/previous-versions/commerce-server/dd327979(v=cs.90)).</span></span>

```csharp
using System;
using System.Data.Common;
using System.Data.SqlClient;
using System.Threading.Tasks;

class A {
   static async Task PerformDBOperationsUsingProviderModel(string connectionString, string providerName) {
      DbProviderFactory factory = DbProviderFactories.GetFactory(providerName);
      using (DbConnection connection = factory.CreateConnection()) {
         connection.ConnectionString = connectionString;
         await connection.OpenAsync();

         DbCommand command = connection.CreateCommand();
         command.CommandText = "SELECT * FROM AUTHORS";

         using (DbDataReader reader = await command.ExecuteReaderAsync()) {
            while (await reader.ReadAsync()) {
               for (int i = 0; i < reader.FieldCount; i++) {
                  // Process each column as appropriate
                  object obj = await reader.GetFieldValueAsync<object>(i);
                  Console.WriteLine(obj);
               }
            }
         }
      }
   }

   public static void Main()
   {
       SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder();
       // replace these with your own values
       builder.DataSource = "your_server";
       builder.InitialCatalog = "pubs";
       builder.IntegratedSecurity = true;
       string provider = "System.Data.SqlClient";

       Task task = PerformDBOperationsUsingProviderModel(builder.ConnectionString, provider);
       task.Wait();
   }
}
```

### <a name="using-sql-transactions-and-the-new-asynchronous-feature"></a><span data-ttu-id="63f9f-143">Verwenden von SQL-Transaktionen und der neuen asynchronen Funktion</span><span class="sxs-lookup"><span data-stu-id="63f9f-143">Using SQL Transactions and the New Asynchronous Feature</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;

class Program {
   static void Main() {
      string connectionString =
          "Persist Security Info=False;Integrated Security=SSPI;database=Northwind;server=(local)";
      Task task = ExecuteSqlTransaction(connectionString);
      task.Wait();
   }

   static async Task ExecuteSqlTransaction(string connectionString) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         await connection.OpenAsync();

         SqlCommand command = connection.CreateCommand();
         SqlTransaction transaction = null;

         // Start a local transaction.
         transaction = await Task.Run<SqlTransaction>(
             () => connection.BeginTransaction("SampleTransaction")
             );

         // Must assign both transaction object and connection
         // to Command object for a pending local transaction
         command.Connection = connection;
         command.Transaction = transaction;

         try {
            command.CommandText =
                "Insert into Region (RegionID, RegionDescription) VALUES (555, 'Description')";
            await command.ExecuteNonQueryAsync();

            command.CommandText =
                "Insert into Region (RegionID, RegionDescription) VALUES (556, 'Description')";
            await command.ExecuteNonQueryAsync();

            // Attempt to commit the transaction.
            await Task.Run(() => transaction.Commit());
            Console.WriteLine("Both records are written to database.");
         }
         catch (Exception ex) {
            Console.WriteLine("Commit Exception Type: {0}", ex.GetType());
            Console.WriteLine("  Message: {0}", ex.Message);

            // Attempt to roll back the transaction.
            try {
               transaction.Rollback();
            }
            catch (Exception ex2) {
               // This catch block will handle any errors that may have occurred
               // on the server that would cause the rollback to fail, such as
               // a closed connection.
               Console.WriteLine("Rollback Exception Type: {0}", ex2.GetType());
               Console.WriteLine("  Message: {0}", ex2.Message);
            }
         }
      }
   }
}
```

### <a name="using-sql-transactions-and-the-new-asynchronous-feature"></a><span data-ttu-id="63f9f-144">Verwenden von SQL-Transaktionen und der neuen asynchronen Funktion</span><span class="sxs-lookup"><span data-stu-id="63f9f-144">Using SQL Transactions and the New Asynchronous Feature</span></span>

<span data-ttu-id="63f9f-145">In einer Unternehmensanwendung müssen Sie in einigen Szenarien möglicherweise verteilte Transaktionen hinzufügen, um Transaktionen zwischen mehreren Datenbankservern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="63f9f-145">In an enterprise application, you may need to add distributed transactions in some scenarios, to enable transactions between multiple database servers.</span></span> <span data-ttu-id="63f9f-146">Sie können den System.Transactions-Namespace verwenden und wie folgt eine verteilte Transaktion eintragen:</span><span class="sxs-lookup"><span data-stu-id="63f9f-146">You can use the System.Transactions namespace and enlist a distributed transaction, as follows:</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Transactions;

class Program {
   public static void Main()
   {
       SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder();
       // replace these with your own values
       builder.DataSource = "your_server";
       builder.InitialCatalog = "your_data_source";
       builder.IntegratedSecurity = true;

       Task task = ExecuteDistributedTransaction(builder.ConnectionString, builder.ConnectionString);
       task.Wait();
   }

   static async Task ExecuteDistributedTransaction(string connectionString1, string connectionString2) {
      using (SqlConnection connection1 = new SqlConnection(connectionString1))
      using (SqlConnection connection2 = new SqlConnection(connectionString2)) {
         using (CommittableTransaction transaction = new CommittableTransaction()) {
            await connection1.OpenAsync();
            connection1.EnlistTransaction(transaction);

            await connection2.OpenAsync();
            connection2.EnlistTransaction(transaction);

            try {
               SqlCommand command1 = connection1.CreateCommand();
               command1.CommandText = "Insert into RegionTable1 (RegionID, RegionDescription) VALUES (100, 'Description')";
               await command1.ExecuteNonQueryAsync();

               SqlCommand command2 = connection2.CreateCommand();
               command2.CommandText = "Insert into RegionTable2 (RegionID, RegionDescription) VALUES (100, 'Description')";
               await command2.ExecuteNonQueryAsync();

               transaction.Commit();
            }
            catch (Exception ex) {
               Console.WriteLine("Exception Type: {0}", ex.GetType());
               Console.WriteLine("  Message: {0}", ex.Message);

               try {
                  transaction.Rollback();
               }
               catch (Exception ex2) {
                  Console.WriteLine("Rollback Exception Type: {0}", ex2.GetType());
                  Console.WriteLine("  Message: {0}", ex2.Message);
               }
            }
         }
      }
   }
}
```

### <a name="cancelling-an-asynchronous-operation"></a><span data-ttu-id="63f9f-147">Abbrechen eines asynchronen Vorgangs</span><span class="sxs-lookup"><span data-stu-id="63f9f-147">Cancelling an Asynchronous Operation</span></span>

<span data-ttu-id="63f9f-148">Sie können eine asynchrone Anforderung mithilfe von <xref:System.Threading.CancellationToken> abbrechen.</span><span class="sxs-lookup"><span data-stu-id="63f9f-148">You can cancel an asynchronous request by using the <xref:System.Threading.CancellationToken>.</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Threading;
using System.Threading.Tasks;

namespace Samples {
   class CancellationSample {
      public static void Main(string[] args) {
         CancellationTokenSource source = new CancellationTokenSource();
         source.CancelAfter(2000); // give up after 2 seconds
         try {
            Task result = CancellingAsynchronousOperations(source.Token);
            result.Wait();
         }
         catch (AggregateException exception) {
            if (exception.InnerException is SqlException) {
               Console.WriteLine("Operation canceled");
            }
            else {
               throw;
            }
         }
      }

      static async Task CancellingAsynchronousOperations(CancellationToken cancellationToken) {
         using (SqlConnection connection = new SqlConnection("Server=(local);Integrated Security=true")) {
            await connection.OpenAsync(cancellationToken);

            SqlCommand command = new SqlCommand("WAITFOR DELAY '00:10:00'", connection);
            await command.ExecuteNonQueryAsync(cancellationToken);
         }
      }
   }
}
```

### <a name="asynchronous-operations-with-sqlbulkcopy"></a><span data-ttu-id="63f9f-149">Asynchrone Vorgänge mit SqlBulkCopy</span><span class="sxs-lookup"><span data-stu-id="63f9f-149">Asynchronous Operations with SqlBulkCopy</span></span>

<span data-ttu-id="63f9f-150"><xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType> wurden mit <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType> auch asynchrone Funktionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63f9f-150">Asynchronous capabilities were also added to <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType> with <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType>.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Data;
using System.Data.Odbc;
using System.Data.SqlClient;
using System.Linq;
using System.Text;
using System.Threading;
using System.Threading.Tasks;

namespace SqlBulkCopyAsyncCodeSample {
   class Program {
      static string selectStatement = "SELECT * FROM [pubs].[dbo].[titles]";
      static string createDestTableStatement =
          @"CREATE TABLE {0} (
            [title_id] [varchar](6) NOT NULL,
            [title] [varchar](80) NOT NULL,
            [type] [char](12) NOT NULL,
            [pub_id] [char](4) NULL,
            [price] [money] NULL,
            [advance] [money] NULL,
            [royalty] [int] NULL,
            [ytd_sales] [int] NULL,
            [notes] [varchar](200) NULL,
            [pubdate] [datetime] NOT NULL)";

      // Replace the connection string if needed, for instance to connect to SQL Express: @"Server=(local)\SQLEXPRESS;Database=Demo;Integrated Security=true"
      // static string connectionString = @"Server=(localdb)\V11.0;Database=Demo";
      static string connectionString = @"Server=(local);Database=Demo;Integrated Security=true";

      // static string odbcConnectionString = @"Driver={SQL Server};Server=(localdb)\V11.0;UID=oledb;Pwd=[PLACEHOLDER];Database=Demo";
      static string odbcConnectionString = @"Driver={SQL Server};Server=(local);Database=Demo;Integrated Security=true";

      // static string marsConnectionString = @"Server=(localdb)\V11.0;Database=Demo;MultipleActiveResultSets=true;";
      static string marsConnectionString = @"Server=(local);Database=Demo;MultipleActiveResultSets=true;Integrated Security=true";

      // Replace the Server name with your actual sql azure server name and User ID/Password
      static string azureConnectionString = @"Server=SqlAzure;User ID=myUserID;Password=myPassword;Database=Demo";

      static void Main(string[] args) {
         SynchronousSqlBulkCopy();
         AsyncSqlBulkCopy().Wait();
         MixSyncAsyncSqlBulkCopy().Wait();
         AsyncSqlBulkCopyNotifyAfter().Wait();
         AsyncSqlBulkCopyDataRows().Wait();
         // AsyncSqlBulkCopySqlServerToSqlAzure().Wait();
         // AsyncSqlBulkCopyCancel().Wait();
         AsyncSqlBulkCopyMARS().Wait();
      }

      // 3.1.1 Synchronous bulk copy in .NET Framework 4.5
      private static void SynchronousSqlBulkCopy() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            conn.Open();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               cmd.ExecuteNonQuery();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  bcp.WriteToServer(dt);
               }
            }
         }

      }

      // 3.1.2 Asynchronous bulk copy in .NET Framework 4.5
      private static async Task AsyncSqlBulkCopy() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            await conn.OpenAsync();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               await cmd.ExecuteNonQueryAsync();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  await bcp.WriteToServerAsync(dt);
               }
            }
         }
      }

      // 3.2 Add new Async.NET capabilities in an existing application (Mixing synchronous and asynchronous calls)
      private static async Task MixSyncAsyncSqlBulkCopy() {
         using (OdbcConnection odbcconn = new OdbcConnection(odbcConnectionString)) {
            odbcconn.Open();
            using (OdbcCommand odbccmd = new OdbcCommand(selectStatement, odbcconn)) {
               using (OdbcDataReader odbcreader = odbccmd.ExecuteReader()) {
                  using (SqlConnection conn = new SqlConnection(connectionString)) {
                     await conn.OpenAsync();
                     string temptable = "temptable";//"[#" + Guid.NewGuid().ToString("N") + "]";
                     SqlCommand createCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), conn);
                     await createCmd.ExecuteNonQueryAsync();
                     using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                        bcp.DestinationTableName = temptable;
                        await bcp.WriteToServerAsync(odbcreader);
                     }
                  }
               }
            }
         }
      }

      // 3.3 Using the NotifyAfter property
      private static async Task AsyncSqlBulkCopyNotifyAfter() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            await conn.OpenAsync();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               await cmd.ExecuteNonQueryAsync();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  bcp.NotifyAfter = 5;
                  bcp.SqlRowsCopied += new SqlRowsCopiedEventHandler(OnSqlRowsCopied);
                  await bcp.WriteToServerAsync(dt);
               }
            }
         }
      }

      private static void OnSqlRowsCopied(object sender, SqlRowsCopiedEventArgs e) {
         Console.WriteLine("Copied {0} so far...", e.RowsCopied);
      }

      // 3.4 Using the new SqlBulkCopy Async.NET capabilities with DataRow[]
      private static async Task AsyncSqlBulkCopyDataRows() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            await conn.OpenAsync();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);
               DataRow[] rows = dt.Select();

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               await cmd.ExecuteNonQueryAsync();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  await bcp.WriteToServerAsync(rows);
               }
            }
         }
      }

      // 3.5 Copying data from SQL Server to SQL Azure in .NET Framework 4.5
      //private static async Task AsyncSqlBulkCopySqlServerToSqlAzure() {
      //   using (SqlConnection srcConn = new SqlConnection(connectionString))
      //   using (SqlConnection destConn = new SqlConnection(azureConnectionString)) {
      //      await srcConn.OpenAsync();
      //      await destConn.OpenAsync();
      //      using (SqlCommand srcCmd = new SqlCommand(selectStatement, srcConn)) {
      //         using (SqlDataReader reader = await srcCmd.ExecuteReaderAsync()) {
      //            string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
      //            using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {
      //               await destCmd.ExecuteNonQueryAsync();
      //               using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {
      //                  bcp.DestinationTableName = temptable;
      //                  await bcp.WriteToServerAsync(reader);
      //               }
      //            }
      //         }
      //      }
      //   }
      //}

      // 3.6 Cancelling an Asynchronous Operation to SQL Azure
      //private static async Task AsyncSqlBulkCopyCancel() {
      //   CancellationTokenSource cts = new CancellationTokenSource();
      //   using (SqlConnection srcConn = new SqlConnection(connectionString))
      //   using (SqlConnection destConn = new SqlConnection(azureConnectionString)) {
      //      await srcConn.OpenAsync(cts.Token);
      //      await destConn.OpenAsync(cts.Token);
      //      using (SqlCommand srcCmd = new SqlCommand(selectStatement, srcConn)) {
      //         using (SqlDataReader reader = await srcCmd.ExecuteReaderAsync(cts.Token)) {
      //            string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
      //            using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {
      //               await destCmd.ExecuteNonQueryAsync(cts.Token);
      //               using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {
      //                  bcp.DestinationTableName = temptable;
      //                  await bcp.WriteToServerAsync(reader, cts.Token);
      //                  //Cancel Async SqlBulCopy Operation after 200 ms
      //                  cts.CancelAfter(200);
      //               }
      //            }
      //         }
      //      }
      //   }
      //}

      // 3.7 Using Async.Net and MARS
      private static async Task AsyncSqlBulkCopyMARS() {
         using (SqlConnection marsConn = new SqlConnection(marsConnectionString)) {
            await marsConn.OpenAsync();

            SqlCommand titlesCmd = new SqlCommand("SELECT * FROM [pubs].[dbo].[titles]", marsConn);
            SqlCommand authorsCmd = new SqlCommand("SELECT * FROM [pubs].[dbo].[authors]", marsConn);
            //With MARS we can have multiple active results sets on the same connection
            using (SqlDataReader titlesReader = await titlesCmd.ExecuteReaderAsync())
            using (SqlDataReader authorsReader = await authorsCmd.ExecuteReaderAsync()) {
               await authorsReader.ReadAsync();

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               using (SqlConnection destConn = new SqlConnection(connectionString)) {
                  await destConn.OpenAsync();
                  using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {
                     await destCmd.ExecuteNonQueryAsync();
                     using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {
                        bcp.DestinationTableName = temptable;
                        await bcp.WriteToServerAsync(titlesReader);
                     }
                  }
               }
            }
         }
      }
   }
}
```

## <a name="asynchronously-using-multiple-commands-with-mars"></a><span data-ttu-id="63f9f-151">Asynchrone Verwendung mehrerer Befehle mit MARS</span><span class="sxs-lookup"><span data-stu-id="63f9f-151">Asynchronously Using Multiple Commands with MARS</span></span>

<span data-ttu-id="63f9f-152">Im Beispiel wird eine einzelne Verbindung mit der **AdventureWorks**-Datenbank geöffnet.</span><span class="sxs-lookup"><span data-stu-id="63f9f-152">The example opens a single connection to the **AdventureWorks** database.</span></span> <span data-ttu-id="63f9f-153">Wenn Sie ein <xref:System.Data.SqlClient.SqlCommand>-Objekt verwenden, wird ein <xref:System.Data.SqlClient.SqlDataReader> erstellt.</span><span class="sxs-lookup"><span data-stu-id="63f9f-153">Using a <xref:System.Data.SqlClient.SqlCommand> object, a <xref:System.Data.SqlClient.SqlDataReader> is created.</span></span> <span data-ttu-id="63f9f-154">Bei Verwenden des Readers wird ein zweiter <xref:System.Data.SqlClient.SqlDataReader> geöffnet, wobei die Daten aus dem ersten <xref:System.Data.SqlClient.SqlDataReader> als Eingabe in die WHERE-Klausel für den zweiten Reader verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="63f9f-154">As the reader is used, a second <xref:System.Data.SqlClient.SqlDataReader> is opened, using data from the first <xref:System.Data.SqlClient.SqlDataReader> as input to the WHERE clause for the second reader.</span></span>

> [!NOTE]
> <span data-ttu-id="63f9f-155">Im folgenden Beispiel wird die in SQL Server enthaltene **AdventureWorks**-Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="63f9f-155">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="63f9f-156">Bei der im Beispielcode bereitgestellten Verbindungszeichenfolge wird davon ausgegangen, dass die Datenbank auf dem lokalen Computer installiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="63f9f-156">The connection string provided in the sample code assumes that the database is installed and available on the local computer.</span></span> <span data-ttu-id="63f9f-157">Ändern Sie die Verbindungszeichenfolge nach Bedarf für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="63f9f-157">Modify the connection string as necessary for your environment.</span></span>

```csharp
using System;
using System.Data;
using System.Data.SqlClient;
using System.Threading.Tasks;

class Class1 {
   static void Main() {
      Task task = MultipleCommands();
      task.Wait();
   }

   static async Task MultipleCommands() {
      // By default, MARS is disabled when connecting to a MARS-enabled.
      // It must be enabled in the connection string.
      string connectionString = GetConnectionString();

      int vendorID;
      SqlDataReader productReader = null;
      string vendorSQL =
        "SELECT VendorId, Name FROM Purchasing.Vendor";
      string productSQL =
        "SELECT Production.Product.Name FROM Production.Product " +
        "INNER JOIN Purchasing.ProductVendor " +
        "ON Production.Product.ProductID = " +
        "Purchasing.ProductVendor.ProductID " +
        "WHERE Purchasing.ProductVendor.VendorID = @VendorId";

      using (SqlConnection awConnection =
        new SqlConnection(connectionString)) {
         SqlCommand vendorCmd = new SqlCommand(vendorSQL, awConnection);
         SqlCommand productCmd =
           new SqlCommand(productSQL, awConnection);

         productCmd.Parameters.Add("@VendorId", SqlDbType.Int);

         await awConnection.OpenAsync();
         using (SqlDataReader vendorReader = await vendorCmd.ExecuteReaderAsync()) {
            while (await vendorReader.ReadAsync()) {
               Console.WriteLine(vendorReader["Name"]);

               vendorID = (int)vendorReader["VendorId"];

               productCmd.Parameters["@VendorId"].Value = vendorID;
               // The following line of code requires a MARS-enabled connection.
               productReader = await productCmd.ExecuteReaderAsync();
               using (productReader) {
                  while (await productReader.ReadAsync()) {
                     Console.WriteLine("  " +
                       productReader["Name"].ToString());
                  }
               }
            }
         }
      }
   }

   private static string GetConnectionString() {
      // To avoid storing the connection string in your code, you can retrieve it from a configuration file.
      return "Data Source=(local);Integrated Security=SSPI;Initial Catalog=AdventureWorks;MultipleActiveResultSets=True";
   }
}
```

## <a name="asynchronously-reading-and-updating-data-with-mars"></a><span data-ttu-id="63f9f-158">Asynchrones Lesen und Aktualisieren von Daten mit MARS</span><span class="sxs-lookup"><span data-stu-id="63f9f-158">Asynchronously Reading and Updating Data with MARS</span></span>

<span data-ttu-id="63f9f-159">MARS ermöglicht die Verwendung einer Verbindung sowohl für Lese- als auch für DML-Vorgänge (Data Manipulation Language, Datenbearbeitungssprache) mit mehr als einem ausstehenden Vorgang.</span><span class="sxs-lookup"><span data-stu-id="63f9f-159">MARS allows a connection to be used for both read operations and data manipulation language (DML) operations with more than one pending operation.</span></span> <span data-ttu-id="63f9f-160">Dieses Feature macht eine Anwendung zur Behandlung von Fehlern im Zusammenhang mit der Verbindungsauslastung überflüssig.</span><span class="sxs-lookup"><span data-stu-id="63f9f-160">This feature eliminates the need for an application to deal with connection-busy errors.</span></span> <span data-ttu-id="63f9f-161">Darüber hinaus kann MARS die Verwendung serverseitiger Cursor ersetzen, die im Allgemeinen mehr Ressourcen benötigen.</span><span class="sxs-lookup"><span data-stu-id="63f9f-161">In addition, MARS can replace the user of server-side cursors, which generally consume more resources.</span></span> <span data-ttu-id="63f9f-162">Da außerdem mehrere Vorgänge über eine einzelne Verbindung ausgeführt werden können, kann ein gemeinsamer Transaktionskontext verwendet werden. Dadurch ist die Verwendung der gespeicherten Systemprozeduren **sp_getbindtoken** und **sp_bindsession** nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="63f9f-162">Finally, because multiple operations can operate on a single connection, they can share the same transaction context, eliminating the need to use **sp_getbindtoken** and **sp_bindsession** system stored procedures.</span></span>

<span data-ttu-id="63f9f-163">Die folgende Konsolenanwendung veranschaulicht die Verwendung zweier <xref:System.Data.SqlClient.SqlDataReader>-Objekte mit drei <xref:System.Data.SqlClient.SqlCommand>-Objekten und einem einzelnen <xref:System.Data.SqlClient.SqlConnection>-Objekt bei aktiviertem MARS.</span><span class="sxs-lookup"><span data-stu-id="63f9f-163">The following Console application demonstrates how to use two <xref:System.Data.SqlClient.SqlDataReader> objects with three <xref:System.Data.SqlClient.SqlCommand> objects and a single <xref:System.Data.SqlClient.SqlConnection> object with MARS enabled.</span></span> <span data-ttu-id="63f9f-164">Das erste Befehlsobjekt ruft eine Liste von Anbietern ab, deren Bonitätsbewertung 5 ist.</span><span class="sxs-lookup"><span data-stu-id="63f9f-164">The first command object retrieves a list of vendors whose credit rating is 5.</span></span> <span data-ttu-id="63f9f-165">Das zweite Befehlsobjekt verwendet die von einem <xref:System.Data.SqlClient.SqlDataReader> bereitgestellte Anbieter-ID, um den zweiten <xref:System.Data.SqlClient.SqlDataReader> mit allen Produkten für den bestimmten Anbieter zu laden.</span><span class="sxs-lookup"><span data-stu-id="63f9f-165">The second command object uses the vendor ID provided from a <xref:System.Data.SqlClient.SqlDataReader> to load the second <xref:System.Data.SqlClient.SqlDataReader> with all of the products for the particular vendor.</span></span> <span data-ttu-id="63f9f-166">Jeder Produktdatensatz wird vom zweiten <xref:System.Data.SqlClient.SqlDataReader> besucht.</span><span class="sxs-lookup"><span data-stu-id="63f9f-166">Each product record is visited by the second <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="63f9f-167">Es wird eine Berechnung ausgeführt, um den neuen Wert für **OnOrderQty** zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="63f9f-167">A calculation is performed to determine what the new **OnOrderQty** should be.</span></span> <span data-ttu-id="63f9f-168">Anschließend wird mithilfe des dritten Befehlsobjekts die **ProductVendor**-Tabelle mit dem neuen Wert aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="63f9f-168">The third command object is then used to update the **ProductVendor** table with the new value.</span></span> <span data-ttu-id="63f9f-169">Der gesamte Prozess findet innerhalb einer einzelnen Transaktion statt, für die am Ende ein Rollback erfolgt.</span><span class="sxs-lookup"><span data-stu-id="63f9f-169">This entire process takes place within a single transaction, which is rolled back at the end.</span></span>

> [!NOTE]
> <span data-ttu-id="63f9f-170">Im folgenden Beispiel wird die in SQL Server enthaltene **AdventureWorks**-Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="63f9f-170">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="63f9f-171">Bei der im Beispielcode bereitgestellten Verbindungszeichenfolge wird davon ausgegangen, dass die Datenbank auf dem lokalen Computer installiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="63f9f-171">The connection string provided in the sample code assumes that the database is installed and available on the local computer.</span></span> <span data-ttu-id="63f9f-172">Ändern Sie die Verbindungszeichenfolge nach Bedarf für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="63f9f-172">Modify the connection string as necessary for your environment.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.Data;
using System.Data.SqlClient;
using System.Threading.Tasks;

class Program {
   static void Main() {
      Task task = ReadingAndUpdatingData();
      task.Wait();
   }

   static async Task ReadingAndUpdatingData() {
      // By default, MARS is disabled when connecting to a MARS-enabled host.
      // It must be enabled in the connection string.
      string connectionString = GetConnectionString();

      SqlTransaction updateTx = null;
      SqlCommand vendorCmd = null;
      SqlCommand prodVendCmd = null;
      SqlCommand updateCmd = null;

      SqlDataReader prodVendReader = null;

      int vendorID = 0;
      int productID = 0;
      int minOrderQty = 0;
      int maxOrderQty = 0;
      int onOrderQty = 0;
      int recordsUpdated = 0;
      int totalRecordsUpdated = 0;

      string vendorSQL =
          "SELECT VendorID, Name FROM Purchasing.Vendor " +
          "WHERE CreditRating = 5";
      string prodVendSQL =
          "SELECT ProductID, MaxOrderQty, MinOrderQty, OnOrderQty " +
          "FROM Purchasing.ProductVendor " +
          "WHERE VendorID = @VendorID";
      string updateSQL =
          "UPDATE Purchasing.ProductVendor " +
          "SET OnOrderQty = @OrderQty " +
          "WHERE ProductID = @ProductID AND VendorID = @VendorID";

      using (SqlConnection awConnection =
        new SqlConnection(connectionString)) {
         await awConnection.OpenAsync();
         updateTx = await Task.Run(() => awConnection.BeginTransaction());

         vendorCmd = new SqlCommand(vendorSQL, awConnection);
         vendorCmd.Transaction = updateTx;

         prodVendCmd = new SqlCommand(prodVendSQL, awConnection);
         prodVendCmd.Transaction = updateTx;
         prodVendCmd.Parameters.Add("@VendorId", SqlDbType.Int);

         updateCmd = new SqlCommand(updateSQL, awConnection);
         updateCmd.Transaction = updateTx;
         updateCmd.Parameters.Add("@OrderQty", SqlDbType.Int);
         updateCmd.Parameters.Add("@ProductID", SqlDbType.Int);
         updateCmd.Parameters.Add("@VendorID", SqlDbType.Int);

         using (SqlDataReader vendorReader = await vendorCmd.ExecuteReaderAsync()) {
            while (await vendorReader.ReadAsync()) {
               Console.WriteLine(vendorReader["Name"]);

               vendorID = (int)vendorReader["VendorID"];
               prodVendCmd.Parameters["@VendorID"].Value = vendorID;
               prodVendReader = await prodVendCmd.ExecuteReaderAsync();

               using (prodVendReader) {
                  while (await prodVendReader.ReadAsync()) {
                     productID = (int)prodVendReader["ProductID"];

                     if (prodVendReader["OnOrderQty"] == DBNull.Value) {
                        minOrderQty = (int)prodVendReader["MinOrderQty"];
                        onOrderQty = minOrderQty;
                     }
                     else {
                        maxOrderQty = (int)prodVendReader["MaxOrderQty"];
                        onOrderQty = (int)(maxOrderQty / 2);
                     }

                     updateCmd.Parameters["@OrderQty"].Value = onOrderQty;
                     updateCmd.Parameters["@ProductID"].Value = productID;
                     updateCmd.Parameters["@VendorID"].Value = vendorID;

                     recordsUpdated = await updateCmd.ExecuteNonQueryAsync();
                     totalRecordsUpdated += recordsUpdated;
                  }
               }
            }
         }
         Console.WriteLine("Total Records Updated: ", totalRecordsUpdated.ToString());
         await Task.Run(() => updateTx.Rollback());
         Console.WriteLine("Transaction Rolled Back");
      }
   }

   private static string GetConnectionString() {
      // To avoid storing the connection string in your code, you can retrieve it from a configuration file.
      return "Data Source=(local);Integrated Security=SSPI;Initial Catalog=AdventureWorks;MultipleActiveResultSets=True";
   }
}
```

## <a name="see-also"></a><span data-ttu-id="63f9f-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63f9f-173">See also</span></span>

- [<span data-ttu-id="63f9f-174">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="63f9f-174">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
