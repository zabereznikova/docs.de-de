---
title: "ADO.NET-Codebeispiele | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# ADO.NET-Codebeispiele
In den Codeauflistungen in diesem Thema wird veranschaulicht, wie Daten mithilfe der folgenden ADO.NET-Technologien aus einer Datenbank abgerufen werden:  
  
-   ADO.NET-Datenanbieter:  
  
    -   [SqlClient](#_SqlClient) (`System.Data.SqlClient`)  
  
    -   [OleDb](#_OleDb) (`System.Data.OleDb`)  
  
    -   [Odbc](#_Odbc) (`System.Data.Odbc`)  
  
    -   [OracleClient](#_OracleClient) (`System.Data.OracleClient`)  
  
-   ADO.NET Entity Framework:  
  
    -   [LINQ to Entities](#_LINQ)  
  
    -   [Typisierte ObjectQuery](#_QBM)  
  
    -   [EntityClient](#_EntityClient) (`System.Data.EntityClient`)  
  
-   [LINQ to SQL](#_LINQ2SQL)  
  
## <a name="adonet-data-provider-examples"></a>ADO.NET-Datenanbieterbeispiele  
 In den folgenden Codeauflistungen wird veranschaulicht, wie Daten mit ADO.NET-Datenanbietern aus einer Datenbank abgerufen werden. Die Daten werden in einem `DataReader` zurückgegeben. Weitere Informationen finden Sie unter [Abrufen von Daten mit einem DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).  
  
<a name="_SqlClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 Beim Code in diesem Beispiel wird davon ausgegangen, dass Sie eine Verbindung mit der `Northwind`-Beispieldatenbank unter Microsoft [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] herstellen können. Der Code erstellt ein <xref:System.Data.SqlClient.SqlCommand> zum Auswählen von Zeilen aus der Tabelle Products, Hinzufügen einer <xref:System.Data.SqlClient.SqlParameter> um die Ergebnisse mit der Einzelpreis höher als der angegebene Parameterwert in diesem Fall 5 Zeilen zu beschränken. Die <xref:System.Data.SqlClient.SqlConnection> wird geöffnet, in der eine `using` Block, der sicherstellt, dass Ressourcen geschlossen und freigegeben werden, wenn der Code beendet wird. Der Code führt den Befehl mit einem <xref:System.Data.SqlClient.SqlDataReader>, und die Ergebnisse im Konsolenfenster angezeigt.  
  
  [DataWorks SampleApp.SqlClient#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient#1)]  
  
 [[Nach oben]](#_TOP)  
  
<a name="_OleDb"></a>   
### <a name="oledb"></a>OleDb  
 Beim Code in diesem Beispiel wird davon ausgegangen, dass Sie eine Verbindung mit der Microsoft Access-Northwind-Beispieldatenbank herstellen können. Der Code erstellt ein <xref:System.Data.OleDb.OleDbCommand> zum Auswählen von Zeilen aus der Tabelle Products, Hinzufügen einer <xref:System.Data.OleDb.OleDbParameter> um die Ergebnisse mit der Einzelpreis höher als der angegebene Parameterwert in diesem Fall 5 Zeilen zu beschränken. Die <xref:System.Data.OleDb.OleDbConnection> wird geöffnet, in der eine `using` Block, der sicherstellt, dass Ressourcen geschlossen und freigegeben werden, wenn der Code beendet wird. Der Code führt den Befehl mit einem <xref:System.Data.OleDb.OleDbDataReader>, und die Ergebnisse im Konsolenfenster angezeigt.  
  
  [DataWorks SampleApp.OleDb#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb#1)]  
  
 [[Nach oben]](#_TOP)  
  
<a name="_Odbc"></a>   
### <a name="odbc"></a>Odbc  
 Beim Code in diesem Beispiel wird davon ausgegangen, dass Sie eine Verbindung mit der Microsoft Access-Northwind-Beispieldatenbank herstellen können. Der Code erstellt ein <xref:System.Data.Odbc.OdbcCommand> zum Auswählen von Zeilen aus der Tabelle Products, Hinzufügen einer <xref:System.Data.Odbc.OdbcParameter> um die Ergebnisse mit der Einzelpreis höher als der angegebene Parameterwert in diesem Fall 5 Zeilen zu beschränken. Die <xref:System.Data.Odbc.OdbcConnection> wird geöffnet, in der eine `using` Block, der sicherstellt, dass Ressourcen geschlossen und freigegeben werden, wenn der Code beendet wird. Das führt den Befehl mit einem <xref:System.Data.Odbc.OdbcDataReader>, und die Ergebnisse im Konsolenfenster angezeigt.  
  
<!-- TODO: review snippet reference  [!CODE [DataWorksSampleApp.Odbc#1](DataWorksSampleApp.Odbc#1)]  -->  
  
 [[Nach oben]](#_TOP)  
  
<a name="_OracleClient"></a>   
### <a name="oracleclient"></a>OracleClient  
 Der Code in diesem Beispiel setzt eine Verbindung mit DEMO.CUSTOMER auf einem Oracle-Server voraus. Sie müssen auch einen Verweis auf System.Data.OracleClient.dll hinzufügen. Der Code gibt die Daten in einer <xref:System.Data.OracleClient.OracleDataReader>.  
  
  [DataWorks SampleApp.Oracle#1](../CodeSnippet/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle#1)]  
  
 [[Nach oben]](#_TOP)  
  
## <a name="entity-framework-examples"></a>Entity Framework-Beispiele  
 In den folgenden Codeauflistungen wird veranschaulicht, wie Daten aus einer Datenquelle abgerufen werden, indem Entitäten in einem Entity Data Model (EDM) abgefragt werden. Diese Beispiele verwenden die [Northwind-Modell](http://msdn.microsoft.com/de-de/74521f8c-e974-48cb-8858-c08deff52638). Weitere Informationen finden Sie unter [Übersicht über Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).  
  
<a name="_LINQ"></a>   
### <a name="linq-to-entities"></a>LINQ to Entities  
 Im Code zu diesem Beispiel werden Daten über eine LINQ-Abfrage als Kategorieobjekte zurückgegeben. Diese werden als anonymer Typ projiziert, der nur die CategoryID-Eigenschaft und die CategoryName-Eigenschaft enthält. Weitere Informationen finden Sie unter [LINQ to Entities-Übersicht](http://msdn.microsoft.com/de-de/86d87a27-c17a-45ac-b28d-72c8500333c6).  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
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
  
 In C#:  
  
```  
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
  
 [[Nach oben]](#_TOP)  
  
<a name="_QBM"></a>   
### <a name="typed-objectquery"></a>Typisierte ObjectQuery  
 Der Code in diesem Beispiel verwendet ein <xref:System.Data.Objects.ObjectQuery%601> Daten als kategorieobjekte zurückgegeben. Weitere Informationen finden Sie unter [Objektabfragen](http://msdn.microsoft.com/de-de/0768033c-876f-471d-85d5-264884349276).  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
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
  
 In C#:  
  
```  
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
  
 [[Nach oben]](#_TOP)  
  
<a name="_EntityClient"></a>   
### <a name="entityclient"></a>EntityClient  
 Der Code in diesem Beispiel verwendet ein <xref:System.Data.EntityClient.EntityCommand> um eine Entity SQL-Abfrage auszuführen. Durch diese Abfrage wird eine Liste von Datensätzen zurückgegeben, die Instanzen des Kategorien-Entitätstyps darstellen. Ein <xref:System.Data.EntityClient.EntityDataReader> wird verwendet, um die Datensätze im Resultset zugreifen. Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
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
  
 In C#"  
  
```  
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
  
 [[Nach oben]](#_TOP)  
  
<a name="_LINQ2SQL"></a>   
## <a name="linq-to-sql"></a>LINQ to SQL  
 Im Code zu diesem Beispiel werden Daten über eine LINQ-Abfrage als Kategorieobjekte zurückgegeben. Diese werden als anonymer Typ projiziert, der nur die CategoryID-Eigenschaft und die CategoryName-Eigenschaft enthält. Dieses Beispiel basiert auf dem Northwind-Datenkontext. Weitere Informationen finden Sie unter [Getting Started](../../../../docs/framework/data/adonet/sql/linq/getting-started.md).  
  
```  
Option Explicit On  
Option Strict On  
  
Imports System  
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
  
 In C#:  
  
```  
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
  
 [[Nach oben]](#_TOP)  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Erstellen von Datenanwendungen](../Topic/Creating%20Data%20Applications.md)   
 [Abfragen einer Entity Data Model (Entity Framework-Aufgaben)](http://msdn.microsoft.com/de-de/187f1caa-e4d3-4e31-bd99-5d5c2b329c77)   
 [Gewusst wie: Ausführen eine Abfrage, die Objekte anonymer Typen zurückgibt](http://msdn.microsoft.com/de-de/3b264025-e911-4d73-90ce-992d2b9d189d)   
 [ADO.NET verwaltete Anbieter und DataSet-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)