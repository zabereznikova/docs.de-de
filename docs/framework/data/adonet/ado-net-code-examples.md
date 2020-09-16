---
title: Codebeispiele
description: Diese Beispiele zeigen .NET Framework Programmierer, wie Daten mithilfe von ADO.NET-Datenanbietern und ADO.NET-Entity Framework aus einer Datenbank abgerufen werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 9d12c7c7dcbc3a24cf51ade5481f59715c4c4d88
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555106"
---
# <a name="adonet-code-examples"></a><span data-ttu-id="8b0c1-103">ADO.NET-Codebeispiele</span><span class="sxs-lookup"><span data-stu-id="8b0c1-103">ADO.NET code examples</span></span>

<span data-ttu-id="8b0c1-104">Die Code Auflistungen auf dieser Seite veranschaulichen das Abrufen von Daten aus einer Datenbank mithilfe der folgenden ADO.NET-Technologien:</span><span class="sxs-lookup"><span data-stu-id="8b0c1-104">The code listings on this page demonstrate how to retrieve data from a database by using the following ADO.NET technologies:</span></span>

- <span data-ttu-id="8b0c1-105">ADO.NET-Datenanbieter:</span><span class="sxs-lookup"><span data-stu-id="8b0c1-105">ADO.NET data providers:</span></span>

  - <span data-ttu-id="8b0c1-106">[SqlClient](#sqlclient) ( `System.Data.SqlClient` )</span><span class="sxs-lookup"><span data-stu-id="8b0c1-106">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span></span>

  - <span data-ttu-id="8b0c1-107">[OleDb](#oledb) ( `System.Data.OleDb` )</span><span class="sxs-lookup"><span data-stu-id="8b0c1-107">[OleDb](#oledb) (`System.Data.OleDb`)</span></span>

  - <span data-ttu-id="8b0c1-108">[ODBC](#odbc) ( `System.Data.Odbc` )</span><span class="sxs-lookup"><span data-stu-id="8b0c1-108">[Odbc](#odbc) (`System.Data.Odbc`)</span></span>

  - <span data-ttu-id="8b0c1-109">[OracleClient](#oracleclient) ( `System.Data.OracleClient` )</span><span class="sxs-lookup"><span data-stu-id="8b0c1-109">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span></span>

- <span data-ttu-id="8b0c1-110">ADO.NET Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="8b0c1-110">ADO.NET Entity Framework:</span></span>

  - [<span data-ttu-id="8b0c1-111">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8b0c1-111">LINQ to Entities</span></span>](#linq-to-entities)

  - [<span data-ttu-id="8b0c1-112">Typisierte ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="8b0c1-112">Typed ObjectQuery</span></span>](#typed-objectquery)

  - <span data-ttu-id="8b0c1-113">[EntityClient](#entityclient) ( `System.Data.EntityClient` )</span><span class="sxs-lookup"><span data-stu-id="8b0c1-113">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span></span>

- [<span data-ttu-id="8b0c1-114">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8b0c1-114">LINQ to SQL</span></span>](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a><span data-ttu-id="8b0c1-115">ADO.NET-Datenanbieter Beispiele</span><span class="sxs-lookup"><span data-stu-id="8b0c1-115">ADO.NET data provider examples</span></span>
<span data-ttu-id="8b0c1-116">In den folgenden Codeauflistungen wird veranschaulicht, wie Daten mit ADO.NET-Datenanbietern aus einer Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-116">The following code listings demonstrate how to retrieve data from a database using ADO.NET data providers.</span></span> <span data-ttu-id="8b0c1-117">Die Daten werden in einem `DataReader` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-117">The data is returned in a `DataReader`.</span></span> <span data-ttu-id="8b0c1-118">Weitere Informationen finden Sie unter [Abrufen von Daten mit einem DataReader](retrieving-data-using-a-datareader.md).</span><span class="sxs-lookup"><span data-stu-id="8b0c1-118">For more information, see [Retrieving Data Using a DataReader](retrieving-data-using-a-datareader.md).</span></span>

### <a name="sqlclient"></a><span data-ttu-id="8b0c1-119">SqlClient</span><span class="sxs-lookup"><span data-stu-id="8b0c1-119">SqlClient</span></span>
<span data-ttu-id="8b0c1-120">Bei dem Code in diesem Beispiel wird davon ausgegangen, dass Sie auf Microsoft SQL Server eine Verbindung mit der- `Northwind` Beispieldatenbank herstellen können.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-120">The code in this example assumes that you can connect to the `Northwind` sample database on Microsoft SQL Server.</span></span> <span data-ttu-id="8b0c1-121">Durch den Code wird ein <xref:System.Data.SqlClient.SqlCommand>-Objekt erstellt, um Zeilen aus Produkttabelle auszuwählen. Es wird ein <xref:System.Data.SqlClient.SqlParameter>-Objekt hinzugefügt, um die Ergebnisse auf Zeilen zu beschränken, in denen der Einzelpreis höher als der angegebene Parameterwert ist, in diesem Fall also 5.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-121">The code creates a <xref:System.Data.SqlClient.SqlCommand> to select rows from the Products table, adding a <xref:System.Data.SqlClient.SqlParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="8b0c1-122">Der <xref:System.Data.SqlClient.SqlConnection> wird innerhalb eines- `using` Blocks geöffnet, wodurch sichergestellt wird, dass Ressourcen geschlossen und freigegeben werden, wenn der Code beendet wird.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-122">The <xref:System.Data.SqlClient.SqlConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="8b0c1-123">Im Code wird der Befehl mit einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt ausgeführt. Die Ergebnisse werden im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-123">The code executes the command by using a <xref:System.Data.SqlClient.SqlDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a><span data-ttu-id="8b0c1-124">OLEDB</span><span class="sxs-lookup"><span data-stu-id="8b0c1-124">OleDb</span></span>
<span data-ttu-id="8b0c1-125">Beim Code in diesem Beispiel wird davon ausgegangen, dass Sie eine Verbindung mit der Microsoft Access-Northwind-Beispieldatenbank herstellen können.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-125">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="8b0c1-126">Durch den Code wird ein <xref:System.Data.OleDb.OleDbCommand>-Objekt erstellt, um Zeilen aus Produkttabelle auszuwählen. Es wird ein <xref:System.Data.OleDb.OleDbParameter>-Objekt hinzugefügt, um die Ergebnisse auf Zeilen zu beschränken, in denen der Einzelpreis höher als der angegebene Parameterwert ist, in diesem Fall also 5.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-126">The code creates a <xref:System.Data.OleDb.OleDbCommand> to select rows from the Products table, adding a <xref:System.Data.OleDb.OleDbParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="8b0c1-127">Das <xref:System.Data.OleDb.OleDbConnection>-Objekt wird in einem `using`-Block geöffnet. Dadurch wird sichergestellt, dass Ressourcen geschlossen und freigegeben werden, wenn der Code beendet wird.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-127">The <xref:System.Data.OleDb.OleDbConnection> is opened inside of a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="8b0c1-128">Im Code wird der Befehl mit einem <xref:System.Data.OleDb.OleDbDataReader>-Objekt ausgeführt. Die Ergebnisse werden im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-128">The code executes the command by using a <xref:System.Data.OleDb.OleDbDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a><span data-ttu-id="8b0c1-129">ODBC</span><span class="sxs-lookup"><span data-stu-id="8b0c1-129">Odbc</span></span>
<span data-ttu-id="8b0c1-130">Beim Code in diesem Beispiel wird davon ausgegangen, dass Sie eine Verbindung mit der Microsoft Access-Northwind-Beispieldatenbank herstellen können.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-130">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="8b0c1-131">Durch den Code wird ein <xref:System.Data.Odbc.OdbcCommand>-Objekt erstellt, um Zeilen aus Produkttabelle auszuwählen. Es wird ein <xref:System.Data.Odbc.OdbcParameter>-Objekt hinzugefügt, um die Ergebnisse auf Zeilen zu beschränken, in denen der Einzelpreis höher als der angegebene Parameterwert ist, in diesem Fall also 5.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-131">The code creates a <xref:System.Data.Odbc.OdbcCommand> to select rows from the Products table, adding a <xref:System.Data.Odbc.OdbcParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="8b0c1-132">Der <xref:System.Data.Odbc.OdbcConnection> wird innerhalb eines- `using` Blocks geöffnet, wodurch sichergestellt wird, dass Ressourcen geschlossen und freigegeben werden, wenn der Code beendet wird.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-132">The <xref:System.Data.Odbc.OdbcConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="8b0c1-133">Im Code wird der Befehl mit einem <xref:System.Data.Odbc.OdbcDataReader>-Objekt ausgeführt. Die Ergebnisse werden im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-133">The code executes the command by using a <xref:System.Data.Odbc.OdbcDataReader>, and displays the results in the console window.</span></span>

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)]
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)]

### <a name="oracleclient"></a><span data-ttu-id="8b0c1-134">OracleClient</span><span class="sxs-lookup"><span data-stu-id="8b0c1-134">OracleClient</span></span>
<span data-ttu-id="8b0c1-135">Der Code in diesem Beispiel setzt eine Verbindung mit DEMO.CUSTOMER auf einem Oracle-Server voraus.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-135">The code in this example assumes a connection to DEMO.CUSTOMER on an Oracle server.</span></span> <span data-ttu-id="8b0c1-136">Sie müssen auch einen Verweis auf System.Data.OracleClient.dll hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-136">You must also add a reference to the System.Data.OracleClient.dll.</span></span> <span data-ttu-id="8b0c1-137">Der Code gibt die Daten in einem <xref:System.Data.OracleClient.OracleDataReader> zurück.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-137">The code returns the data in an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a><span data-ttu-id="8b0c1-138">Entity Framework Beispiele</span><span class="sxs-lookup"><span data-stu-id="8b0c1-138">Entity Framework examples</span></span>
<span data-ttu-id="8b0c1-139">In den folgenden Codeauflistungen wird veranschaulicht, wie Daten aus einer Datenquelle abgerufen werden, indem Entitäten in einem Entity Data Model (EDM) abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-139">The following code listings demonstrate how to retrieve data from a data source by querying entities in an Entity Data Model (EDM).</span></span> <span data-ttu-id="8b0c1-140">In diesen Beispielen wird ein Modell verwendet, das auf der Beispieldatenbank Northwind basiert.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-140">These examples use a model based on the Northwind sample database.</span></span> <span data-ttu-id="8b0c1-141">Weitere Informationen zu Entity Framework finden Sie unter [Entity Framework Übersicht](./ef/overview.md).</span><span class="sxs-lookup"><span data-stu-id="8b0c1-141">For more information about Entity Framework, see [Entity Framework Overview](./ef/overview.md).</span></span>

### <a name="linq-to-entities"></a><span data-ttu-id="8b0c1-142">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8b0c1-142">LINQ to Entities</span></span>
<span data-ttu-id="8b0c1-143">Im Code zu diesem Beispiel werden Daten über eine LINQ-Abfrage als Kategorieobjekte zurückgegeben. Diese werden als anonymer Typ projiziert, der nur die CategoryID-Eigenschaft und die CategoryName-Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-143">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="8b0c1-144">Weitere Informationen finden Sie unter [LINQ to Entities Übersicht](./ef/language-reference/linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="8b0c1-144">For more information, see [LINQ to Entities Overview](./ef/language-reference/linq-to-entities.md).</span></span>

```csharp
using System;
using System.Linq;
using System.Data.Objects;
using NorthwindModel;

class LinqSample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            try
            {
                var query = from category in context.Categories
                            select new
                            {
                                categoryID = category.CategoryID,
                                categoryName = category.CategoryName
                            };

                foreach (var categoryInfo in query)
                {
                    Console.WriteLine("\t{0}\t{1}",
                        categoryInfo.categoryID, categoryInfo.categoryName);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Linq
Imports System.Data.Objects
Imports NorthwindModel

Class LinqSample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Try
                Dim query = From category In context.Categories _
                            Select New With _
                            { _
                                .categoryID = category.CategoryID, _
                                .categoryName = category.CategoryName _
                            }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                        categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

### <a name="typed-objectquery"></a><span data-ttu-id="8b0c1-145">Typisierte ObjectQuery</span><span class="sxs-lookup"><span data-stu-id="8b0c1-145">Typed ObjectQuery</span></span>
<span data-ttu-id="8b0c1-146">Über den Code in diesem Beispiel werden Daten mithilfe von <xref:System.Data.Objects.ObjectQuery%601> als Kategorieobjekte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-146">The code in this example uses an <xref:System.Data.Objects.ObjectQuery%601> to return data as Categories objects.</span></span> <span data-ttu-id="8b0c1-147">Weitere Informationen finden Sie unter [Objekt Abfragen](/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8b0c1-147">For more information, see [Object Queries](/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).</span></span>

```csharp
using System;
using System.Data.Objects;
using NorthwindModel;

class ObjectQuerySample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            ObjectQuery<Categories> categoryQuery = context.Categories;

            foreach (Categories category in
                categoryQuery.Execute(MergeOption.AppendOnly))
            {
                Console.WriteLine("\t{0}\t{1}",
                    category.CategoryID, category.CategoryName);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Data.Objects
Imports NorthwindModel

Class ObjectQuerySample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Dim categoryQuery As ObjectQuery(Of Categories) = context.Categories

            For Each category As Categories In _
                categoryQuery.Execute(MergeOption.AppendOnly)
                Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                    category.CategoryID, category.CategoryName)
            Next
        End Using
    End Sub
End Class
```

### <a name="entityclient"></a><span data-ttu-id="8b0c1-148">EntityClient</span><span class="sxs-lookup"><span data-stu-id="8b0c1-148">EntityClient</span></span>
<span data-ttu-id="8b0c1-149">Über den Code in diesem Beispiel wird mithilfe eines <xref:System.Data.EntityClient.EntityCommand>-Objekts eine Entity SQL-Abfrage ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-149">The code in this example uses an <xref:System.Data.EntityClient.EntityCommand> to execute an Entity SQL query.</span></span> <span data-ttu-id="8b0c1-150">Durch diese Abfrage wird eine Liste von Datensätzen zurückgegeben, die Instanzen des Kategorien-Entitätstyps darstellen.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-150">This query returns a list of records that represent instances of the Categories entity type.</span></span> <span data-ttu-id="8b0c1-151">Für den Zugriff auf die Datensätze im Resultset werden <xref:System.Data.EntityClient.EntityDataReader>-Objekte verwendet.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-151">An <xref:System.Data.EntityClient.EntityDataReader> is used to access data records in the result set.</span></span> <span data-ttu-id="8b0c1-152">Weitere Informationen finden Sie unter [EntityClient-Anbieter für das Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="8b0c1-152">For more information, see [EntityClient Provider for the Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).</span></span>

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.EntityClient;
using NorthwindModel;

class EntityClientSample
{
    public static void ExecuteQuery()
    {
        string queryString =
            @"SELECT c.CategoryID, c.CategoryName
                FROM NorthwindEntities.Categories AS c";

        using (EntityConnection conn =
            new EntityConnection("name=NorthwindEntities"))
        {
            try
            {
                conn.Open();
                using (EntityCommand query = new EntityCommand(queryString, conn))
                {
                    using (DbDataReader rdr =
                        query.ExecuteReader(CommandBehavior.SequentialAccess))
                    {
                        while (rdr.Read())
                        {
                            Console.WriteLine("\t{0}\t{1}", rdr[0], rdr[1]);
                        }
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Data
Imports System.Data.Common
Imports System.Data.EntityClient
Imports NorthwindModel

Class EntityClientSample
    Public Shared Sub ExecuteQuery()
        Dim queryString As String = _
            "SELECT c.CategoryID, c.CategoryName " & _
                "FROM NorthwindEntities.Categories AS c"

        Using conn As EntityConnection = _
            New EntityConnection("name=NorthwindEntities")

            Try
                conn.Open()
                Using query As EntityCommand = _
                New EntityCommand(queryString, conn)
                    Using rdr As DbDataReader = _
                        query.ExecuteReader(CommandBehavior.SequentialAccess)
                        While rdr.Read()
                            Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                                              rdr(0), rdr(1))
                        End While
                    End Using
                End Using
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

## <a name="linq-to-sql"></a><span data-ttu-id="8b0c1-153">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8b0c1-153">LINQ to SQL</span></span>
<span data-ttu-id="8b0c1-154">Im Code zu diesem Beispiel werden Daten über eine LINQ-Abfrage als Kategorieobjekte zurückgegeben. Diese werden als anonymer Typ projiziert, der nur die CategoryID-Eigenschaft und die CategoryName-Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-154">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="8b0c1-155">Dieses Beispiel basiert auf dem Northwind-Datenkontext.</span><span class="sxs-lookup"><span data-stu-id="8b0c1-155">This example is based on the Northwind data context.</span></span> <span data-ttu-id="8b0c1-156">Weitere Informationen finden Sie unter [Erste Schritte](./sql/linq/getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="8b0c1-156">For more information, see [Getting Started](./sql/linq/getting-started.md).</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Northwind;

    class LinqSqlSample
    {
        public static void ExecuteQuery()
        {
            using (NorthwindDataContext db = new NorthwindDataContext())
            {
                try
                {
                    var query = from category in db.Categories
                                select new
                                {
                                    categoryID = category.CategoryID,
                                    categoryName = category.CategoryName
                                };

                    foreach (var categoryInfo in query)
                    {
                        Console.WriteLine("vbTab {0} vbTab {1}",
                            categoryInfo.categoryID, categoryInfo.categoryName);
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine(ex.Message);
                }
            }
        }
    }
```

```vb
Option Explicit On
Option Strict On

Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports Northwind

Class LinqSqlSample
    Public Shared Sub ExecuteQuery()
        Using db As NorthwindDataContext = New NorthwindDataContext()
            Try
                Dim query = From category In db.Categories _
                                Select New With _
                                { _
                                    .categoryID = category.CategoryID, _
                                    .categoryName = category.CategoryName _
                                }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                            categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
            End Using
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="8b0c1-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b0c1-157">See also</span></span>

- [<span data-ttu-id="8b0c1-158">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8b0c1-158">ADO.NET Overview</span></span>](ado-net-overview.md)
- [<span data-ttu-id="8b0c1-159">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8b0c1-159">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- <span data-ttu-id="8b0c1-160">[Erstellen von Datenanwendungen](/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="8b0c1-160">[Creating Data Applications](/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span></span>
- <span data-ttu-id="8b0c1-161">[Abfragen eines Entity Data Model (Entity Framework-Aufgaben)](/previous-versions/bb738455(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8b0c1-161">[Querying an Entity Data Model (Entity Framework Tasks)](/previous-versions/bb738455(v=vs.90))</span></span>
- <span data-ttu-id="8b0c1-162">[Gewusst wie: Ausführen einer Abfrage, die Objekte anonymer Typen zurückgibt](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8b0c1-162">[How to: Execute a Query that Returns Anonymous Type Objects](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>
