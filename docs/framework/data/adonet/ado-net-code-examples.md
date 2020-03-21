---
title: Codebeispiele
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 6e0c34e1db50030c78db295f26fcc25b431d3dde
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111802"
---
# <a name="adonet-code-examples"></a>ADO.NET Codebeispiele

Die Codelisten auf dieser Seite veranschaulichen, wie Daten aus einer Datenbank mithilfe der folgenden ADO.NET-Technologien abgerufen werden:

- ADO.NET-Datenanbieter:

  - [SqlClient](#sqlclient) `System.Data.SqlClient`( )

  - [OleDb](#oledb) `System.Data.OleDb`( )

  - [Odbc](#odbc) `System.Data.Odbc`( )

  - [OracleClient](#oracleclient) `System.Data.OracleClient`( )

- ADO.NET Entity Framework:

  - [LINQ to Entities](#linq-to-entities)

  - [Typisierte ObjectQuery](#typed-objectquery)

  - [EntityClient](#entityclient) `System.Data.EntityClient`( )

- [LINQ to SQL](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a>ADO.NET Datenanbieterbeispiele
In den folgenden Codeauflistungen wird veranschaulicht, wie Daten mit ADO.NET-Datenanbietern aus einer Datenbank abgerufen werden. Die Daten werden in einem `DataReader` zurückgegeben. Weitere Informationen finden Sie unter [Abrufen von Daten mit einem DataReader](retrieving-data-using-a-datareader.md).

### <a name="sqlclient"></a>SqlClient
Der Code in diesem Beispiel geht `Northwind` davon aus, dass Sie eine Verbindung mit der Beispieldatenbank auf Microsoft SQL Server herstellen können. Durch den Code wird ein <xref:System.Data.SqlClient.SqlCommand>-Objekt erstellt, um Zeilen aus Produkttabelle auszuwählen. Es wird ein <xref:System.Data.SqlClient.SqlParameter>-Objekt hinzugefügt, um die Ergebnisse auf Zeilen zu beschränken, in denen der Einzelpreis höher als der angegebene Parameterwert ist, in diesem Fall also 5. Der <xref:System.Data.SqlClient.SqlConnection> wird innerhalb `using` eines Blocks geöffnet, wodurch sichergestellt wird, dass Ressourcen geschlossen und verworfen werden, wenn der Code beendet wird. Im Code wird der Befehl mit einem <xref:System.Data.SqlClient.SqlDataReader>-Objekt ausgeführt. Die Ergebnisse werden im Konsolenfenster angezeigt.

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a>OLEDB
Beim Code in diesem Beispiel wird davon ausgegangen, dass Sie eine Verbindung mit der Microsoft Access-Northwind-Beispieldatenbank herstellen können. Durch den Code wird ein <xref:System.Data.OleDb.OleDbCommand>-Objekt erstellt, um Zeilen aus Produkttabelle auszuwählen. Es wird ein <xref:System.Data.OleDb.OleDbParameter>-Objekt hinzugefügt, um die Ergebnisse auf Zeilen zu beschränken, in denen der Einzelpreis höher als der angegebene Parameterwert ist, in diesem Fall also 5. Das <xref:System.Data.OleDb.OleDbConnection>-Objekt wird in einem `using`-Block geöffnet. Dadurch wird sichergestellt, dass Ressourcen geschlossen und freigegeben werden, wenn der Code beendet wird. Im Code wird der Befehl mit einem <xref:System.Data.OleDb.OleDbDataReader>-Objekt ausgeführt. Die Ergebnisse werden im Konsolenfenster angezeigt.

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a>ODBC
Beim Code in diesem Beispiel wird davon ausgegangen, dass Sie eine Verbindung mit der Microsoft Access-Northwind-Beispieldatenbank herstellen können. Durch den Code wird ein <xref:System.Data.Odbc.OdbcCommand>-Objekt erstellt, um Zeilen aus Produkttabelle auszuwählen. Es wird ein <xref:System.Data.Odbc.OdbcParameter>-Objekt hinzugefügt, um die Ergebnisse auf Zeilen zu beschränken, in denen der Einzelpreis höher als der angegebene Parameterwert ist, in diesem Fall also 5. Der <xref:System.Data.Odbc.OdbcConnection> wird innerhalb `using` eines Blocks geöffnet, wodurch sichergestellt wird, dass Ressourcen geschlossen und verworfen werden, wenn der Code beendet wird. Im Code wird der Befehl mit einem <xref:System.Data.Odbc.OdbcDataReader>-Objekt ausgeführt. Die Ergebnisse werden im Konsolenfenster angezeigt.

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)]
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)]

### <a name="oracleclient"></a>OracleClient
Der Code in diesem Beispiel setzt eine Verbindung mit DEMO.CUSTOMER auf einem Oracle-Server voraus. Sie müssen auch einen Verweis auf System.Data.OracleClient.dll hinzufügen. Der Code gibt die Daten in einem <xref:System.Data.OracleClient.OracleDataReader> zurück.

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a>Beispiele für Entity Framework
In den folgenden Codeauflistungen wird veranschaulicht, wie Daten aus einer Datenquelle abgerufen werden, indem Entitäten in einem Entity Data Model (EDM) abgefragt werden. In diesen Beispielen wird ein Modell verwendet, das auf der Northwind-Beispieldatenbank basiert. Weitere Informationen zu Entity Framework finden Sie unter [Entity Framework Overview](./ef/overview.md).

### <a name="linq-to-entities"></a>LINQ to Entities
Im Code zu diesem Beispiel werden Daten über eine LINQ-Abfrage als Kategorieobjekte zurückgegeben. Diese werden als anonymer Typ projiziert, der nur die CategoryID-Eigenschaft und die CategoryName-Eigenschaft enthält. Weitere Informationen finden Sie unter [Übersicht von LINQ to Entities](./ef/language-reference/linq-to-entities.md).

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

### <a name="typed-objectquery"></a>Typisierte ObjectQuery
Über den Code in diesem Beispiel werden Daten mithilfe von <xref:System.Data.Objects.ObjectQuery%601> als Kategorieobjekte zurückgegeben. Weitere Informationen finden Sie unter [Objektabfragen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).

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

### <a name="entityclient"></a>EntityClient
Über den Code in diesem Beispiel wird mithilfe eines <xref:System.Data.EntityClient.EntityCommand>-Objekts eine Entity SQL-Abfrage ausgeführt. Durch diese Abfrage wird eine Liste von Datensätzen zurückgegeben, die Instanzen des Kategorien-Entitätstyps darstellen. Für den Zugriff auf die Datensätze im Resultset werden <xref:System.Data.EntityClient.EntityDataReader>-Objekte verwendet. Weitere Informationen finden Sie unter [EntityClient-Anbieter für das Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).

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

## <a name="linq-to-sql"></a>LINQ to SQL
Im Code zu diesem Beispiel werden Daten über eine LINQ-Abfrage als Kategorieobjekte zurückgegeben. Diese werden als anonymer Typ projiziert, der nur die CategoryID-Eigenschaft und die CategoryName-Eigenschaft enthält. Dieses Beispiel basiert auf dem Northwind-Datenkontext. Weitere Informationen finden Sie unter [Erste Schritte](./sql/linq/getting-started.md).

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

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ADO.NET](ado-net-overview.md)
- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
- [Erstellen von Datenanwendungen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))
- [Abfragen eines Entity Data Model (Entity Framework-Aufgaben)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))
- [Gewusst wie: Ausführen einer Abfrage, die Objekte anonymer Typen zurückgibt](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))
