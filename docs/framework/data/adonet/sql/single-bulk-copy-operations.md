---
title: Einzelne Massenkopiervorgänge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: 05e3cf25352e731d320061001f08a835cd520b15
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780932"
---
# <a name="single-bulk-copy-operations"></a>Einzelne Massenkopiervorgänge

Ein SQL Server-Massenkopiervorgang wird am einfachsten durchgeführt, indem ein einzelner Vorgang für eine Datenbank ausgeführt wird. Ein Massenkopiervorgang wird in der Standardeinstellung als isolierter Vorgang durchgeführt. Der Kopiervorgang wird nicht transaktiv und ohne die Möglichkeit eines Rollbacks durchgeführt.

> [!NOTE]
> Wenn Sie beim Auftreten eines Fehler einen Rollback der gesamten Massenkopie oder eines Teils davon ausführen müssen, können Sie eine von <xref:System.Data.SqlClient.SqlBulkCopy> verwaltete Transaktion verwenden oder den Massenkopiervorgang innerhalb einer bestehenden Transaktion durchführen. **SqlBulkCopy** funktioniert auch mit <xref:System.Transactions> , wenn die Verbindung (implizit oder explizit) in eine **System. Transactions** -Transaktion eingetragen ist.
>
> Weitere Informationen finden Sie unter [Transaktionen und Massen Kopiervorgänge](transaction-and-bulk-copy-operations.md).

Im Allgemeinen müssen für einen Massenkopiervorgang folgende Schritte ausgeführt werden:

1. Stellen Sie eine Verbindung mit dem Quellserver her, und rufen Sie die zu kopierenden Daten ab. Daten können auch aus anderen Quellen stammen, wenn sie aus einem <xref:System.Data.IDataReader>-Objekt oder einem <xref:System.Data.DataTable>-Objekt abgerufen werden können.

2. Stellen Sie eine Verbindung mit dem Zielserver her (es sei denn, Sie möchten mit **SqlBulkCopy** eine Verbindung für Sie herstellen).

3. Erstellen Sie ein <xref:System.Data.SqlClient.SqlBulkCopy>-Objekt, und legen Sie die notwendigen Eigenschaften fest.

4. Legen Sie die **DestinationTableName** -Eigenschaft so fest, dass Sie die Ziel Tabelle für den Massen Einfügungs Vorgang angibt.

5. Ruft eine der Methoden " **Write-to-Server** " auf.

6. Aktualisieren Sie optional die Eigenschaften, und wenden Sie ggf. erneut " **Write-Server** " an.

7. Rufen Sie die <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>-Methode auf, oder betten Sie die Massenkopiervorgänge in eine `Using`-Anweisung ein.

> [!CAUTION]
> Es wird empfohlen, dass die Datentypen in der Quell- und Zielspalte übereinstimmen. Wenn die Datentypen nicht identisch sind, versucht **SqlBulkCopy** , jeden Quellwert mithilfe der von <xref:System.Data.SqlClient.SqlParameter.Value%2A>verwendeten Regeln in den Ziel Datentyp zu konvertieren. Konvertierungen können sich auf die Leistungsfähigkeit auswirken und zu unerwarteten Fehlern führen. Ein `Double`-Datentyp kann beispielsweise häufig, aber nicht immer in einen `Decimal`-Datentyp konvertiert werden.

## <a name="example"></a>Beispiel

In der folgenden Konsolenanwendung wird veranschaulicht, wie Daten mithilfe der <xref:System.Data.SqlClient.SqlBulkCopy>-Klasse geladen werden. In diesem Beispiel wird ein <xref:System.Data.SqlClient.SqlDataReader> zum Kopieren von Daten aus der **Production. Product** -Tabelle in der SQL Server **AdventureWorks** -Datenbank in eine ähnliche Tabelle in derselben Datenbank verwendet.

> [!IMPORTANT]
> Dieses Beispiel wird nur dann ausgeführt, wenn Sie die Arbeits Tabellen erstellt haben, wie unter [Beispiel für Massen Kopier](bulk-copy-example-setup.md)Vorgänge beschrieben. Dieser Code wird bereitgestellt, um die Syntax nur für die Verwendung von **SqlBulkCopy** zu veranschaulichen. Wenn sich die Quell- und die Zieltabelle in derselben SQL Server-Instanz befinden, lassen sich die Daten einfacher und schneller mit einer Transact-SQL-`INSERT … SELECT`-Anweisung kopieren.

[!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
[!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]

## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a>Durchführen eines Massenkopiervorgangs mithilfe von Transact-SQL und der Command-Klasse

Im folgenden Beispiel wird die <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>-Methode zum Ausführen der BULK INSERT-Anweisung veranschaulicht.

> [!NOTE]
> Der Dateipfad für die Datenquelle ist relativ zum Server. Der Serverprozess muss auf diesen Pfad zugreifen können, damit der Massenkopiervorgang erfolgreich ausgeführt werden kann.

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

## <a name="see-also"></a>Siehe auch

- [Massenkopiervorgänge in SQL Server](bulk-copy-operations-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
