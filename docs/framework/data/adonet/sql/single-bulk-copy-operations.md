---
title: "Einzelne Massenkopiervorg&#228;nge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Einzelne Massenkopiervorg&#228;nge
Ein SQL Server\-Massenkopiervorgang wird am einfachsten durchgeführt, indem ein einzelner Vorgang für eine Datenbank ausgeführt wird.  Ein Massenkopiervorgang wird in der Standardeinstellung als isolierter Vorgang durchgeführt. Der Kopiervorgang wird nicht transaktiv und ohne die Möglichkeit eines Rollbacks durchgeführt.  
  
> [!NOTE]
>  Wenn Sie beim Auftreten eines Fehler einen Rollback der gesamten Massenkopie oder eines Teils davon ausführen müssen, können Sie eine von <xref:System.Data.SqlClient.SqlBulkCopy> verwaltete Transaktion verwenden oder den Massenkopiervorgang innerhalb einer bestehenden Transaktion durchführen.  **SqlBulkCopy** funktioniert auch mit <xref:System.Transactions>, wenn die Verbindung \(implizit oder explizit\) in eine **System.Transactions**\-Transaktion eingetragen wurde.  
>   
>  Weitere Informationen finden Sie unter [Transaktionen und Massenkopiervorgänge](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).  
  
 Im Allgemeinen müssen für einen Massenkopiervorgang folgende Schritte ausgeführt werden:  
  
1.  Stellen Sie eine Verbindung mit dem Quellserver her, und rufen Sie die zu kopierenden Daten ab.  Daten können auch aus anderen Quellen stammen, wenn sie aus einem <xref:System.Data.IDataReader>\-Objekt oder einem <xref:System.Data.DataTable>\-Objekt abgerufen werden können.  
  
2.  Stellen Sie eine Verbindung mit dem Zielserver her \(sofern die Verbindung nicht von **SqlBulkCopy** hergestellt werden soll\).  
  
3.  Erstellen Sie ein <xref:System.Data.SqlClient.SqlBulkCopy>\-Objekt, und legen Sie die notwendigen Eigenschaften fest.  
  
4.  Legen Sie die **DestinationTableName**\-Eigenschaft fest, um die Zieltabelle für den Masseneinfügevorgang anzugeben.  
  
5.  Rufen Sie eine der **WriteToServer**\-Methoden auf.  
  
6.  Optional können Sie Eigenschaften aktualisieren und **WriteToServer** bei Bedarf erneut aufrufen.  
  
7.  Rufen Sie die <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>\-Methode auf, oder betten Sie die Massenkopiervorgänge in eine `Using`\-Anweisung ein.  
  
> [!CAUTION]
>  Es wird empfohlen, dass die Datentypen in der Quell\- und Zielspalte übereinstimmen.  Wenn die Datentypen nicht übereinstimmen, versucht **SqlBulkCopy**, die einzelnen Quellwerte anhand der vom <xref:System.Data.SqlClient.SqlParameter.Value%2A> angewendeten Regeln in den Zieldatentyp zu konvertieren.  Konvertierungen können sich auf die Leistungsfähigkeit auswirken und zu unerwarteten Fehlern führen.  Ein `Double`\-Datentyp kann beispielsweise häufig, aber nicht immer in einen `Decimal`\-Datentyp konvertiert werden.  
  
## Beispiel  
 In der folgenden Konsolenanwendung wird veranschaulicht, wie Daten mithilfe der <xref:System.Data.SqlClient.SqlBulkCopy>\-Klasse geladen werden.  In diesem Beispiel werden mit <xref:System.Data.SqlClient.SqlDataReader> Daten aus der **Production.Product**\-Tabelle in der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] **AdventureWorks**\-Datenbank in eine ähnliche Tabelle in derselben Datenbank kopiert.  
  
> [!IMPORTANT]
>  Dieses Beispiel wird nur ausgeführt, wenn Sie die Arbeitstabellen, wie in [Beispiel für die Massenkopiereinrichtung](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md) beschrieben, erstellt haben.  Der angegebene Code dient nur zur Demonstration der Syntax für die Verwendung von **SqlBulkCopy**.  Wenn sich die Quell\- und die Zieltabelle in derselben SQL Server\-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact\-SQL\-`INSERT … SELECT`\-Anweisung kopieren.  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## Durchführen eines Massenkopiervorgangs mithilfe von Transact\-SQL und der Command\-Klasse  
 Im folgenden Beispiel wird die <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>\-Methode zum Ausführen der BULK INSERT\-Anweisung veranschaulicht.  
  
> [!NOTE]
>  Der Dateipfad für die Datenquelle ist relativ zum Server.  Der Serverprozess muss auf diesen Pfad zugreifen können, damit der Massenkopiervorgang erfolgreich ausgeführt werden kann.  
  
```vb  
Using connection As SqlConnection = New SqlConnection(connectionString)  
Dim queryString As String = _  
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _  
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"  
connection.Open()  
SqlCommand command = New SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery()  
End Using  
```  
  
```csharp  
using (SqlConnection connection = New SqlConnection(connectionString))  
{  
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +  
    "FROM 'f:\mydata\data.tbl' " +  
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";  
connection.Open();  
SqlCommand command = new SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery();  
}  
```  
  
## Siehe auch  
 [Massenkopiervorgänge in SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)