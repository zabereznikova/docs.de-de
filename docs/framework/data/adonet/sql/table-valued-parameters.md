---
title: Tabellenwertparameter
description: Erfahren Sie, wie Sie mithilfe von Tabellenwert Parametern mehrere Daten Zeilen aus einer Client Anwendung in SQL Server Mars Hallen.
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: ea063b333ea0680071b880f26753bfd74b71d80f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91188875"
---
# <a name="table-valued-parameters"></a>Tabellenwertparameter

Tabellenwertparameter bieten eine einfache Möglichkeit zum Marshallen mehrerer Datenzeilen aus einer Clientanwendung nach SQL Server, ohne dass mehrere Roundtrips oder eine spezielle serverseitige Logik für die Verarbeitung der Daten erforderlich sind. Sie können Tabellenwertparameter verwenden, um Datenzeilen in einer Clientanwendung zu kapseln und die Daten in einem einzigen parametrisierten Befehl an den Server zu senden. Die eingehenden Datenzeilen werden in einer Tabellenvariablen gespeichert, die Sie dann mithilfe von Transact-SQL bearbeiten können.  
  
 Für den Zugriff auf Spaltenwerte in Tabellenwertparametern können Standard-SELECT-Anweisungen in Transact-SQL verwendet werden. Tabellenwertparameter sind stark typisiert, und ihre Struktur wird automatisch validiert. Die Größe von Tabellenwertparametern ist lediglich durch den Arbeitsspeicher des Servers beschränkt.  
  
> [!NOTE]
> In Tabellenwertparametern können keine Daten zurückgegeben werden. Tabellenwertparameter sind reine Eingabeparameter. Das Schlüsselwort OUTPUT wird nicht unterstützt.  
  
 Weitere Informationen zu Tabellenwertparametern finden Sie in den folgenden Ressourcen.  
  
|Resource|BESCHREIBUNG|  
|--------------|-----------------|  
|[Verwenden von Tabellenwertparameter (Datenbank-Engine)](/sql/relational-databases/tables/use-table-valued-parameters-database-engine)|Beschreibt, wie Sie Tabellenwertparameter erstellen und verwenden.|  
|[Benutzerdefinierte Tabellentypen](/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))|Beschreibt die benutzerdefinierten Tabellentypen, die zum Deklarieren von Tabellenwertparametern verwendet werden.|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a>Übergeben von mehreren Zeilen in älteren Versionen von SQL Server  

 Vor der Einführung von Tabellenwertparametern in SQL Server 2008 bestanden nur eingeschränkte Möglichkeiten zum Übergeben mehrerer Datenzeilen an eine gespeicherte Prozedur oder einen parametrisierten SQL-Befehl. Entwickler hatten folgende Möglichkeiten, um mehrere Zeilen an den Server zu übergeben:  
  
- Verwenden von mehreren Einzelparametern zur Darstellung der Werte in mehreren Datenspalten und -zeilen. Die Menge der Daten, die mit dieser Methode übergeben werden können, ist aufgrund der maximal zulässigen Anzahl von Parametern beschränkt. SQL Server-Prozeduren können höchstens über 2100 Parameter verfügen. Um diese Einzelwerte zur Verarbeitung in einer Tabellenvariable oder einer temporären Tabelle zusammenzusetzen, ist serverseitige Logik erforderlich.  
  
- Bündeln mehrerer Datenwerte in Zeichenfolgen mit Trennzeichen oder XML-Dokumenten und Übergeben dieser Textwerte an eine Prozedur oder Anweisung. Bei dieser Vorgehensweise muss die Prozedur oder Anweisung die erforderliche Logik zum Überprüfen der Datenstrukturen und Entbündeln der Werte enthalten.  
  
- Erstellen einer Reihe von SQL-Einzelanweisungen für Datenänderungen, die sich auf mehrere Zeilen auswirken (z.B. durch den Aufruf der `Update`-Methode einer <xref:System.Data.SqlClient.SqlDataAdapter>-Klasse). Änderungen können einzeln an den Server übermittelt oder in Gruppen zusammengefasst werden. Auch wenn sie in Batches übermittelt werden, die mehrere Anweisungen enthalten, wird jede Anweisung einzeln auf dem Server ausgeführt.  
  
- Verwenden des `bcp`-Hilfsprogramms oder des <xref:System.Data.SqlClient.SqlBulkCopy>-Objekts, um eine Vielzahl von Datenzeilen in eine Tabelle zu laden. Wenngleich dieses Verfahren sehr effizient ist, wird die serverseitige Verarbeitung nur dann unterstützt, wenn die Daten in eine temporäre Tabelle oder Tabellenvariable geladen werden.  
  
## <a name="creating-table-valued-parameter-types"></a>Erstellen von Tabellenwertparameter-Typen  

 Tabellenwert Parameter basieren auf stark typisierten Tabellenstrukturen, die mithilfe von Transact-SQL-Anweisungen zum Erstellen von Typen definiert werden. Sie müssen einen Tabellentyp erstellen und die Struktur in SQL Server definieren, bevor Sie Tabellenwertparameter in Ihren Clientanwendungen verwenden können. Weitere Informationen zum Erstellen von Tabellentypen finden Sie unter [Benutzerdefinierte Tabellentypen](/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).  
  
 Mit der folgenden Anweisung wird ein Tabellentyp namens „CategoryTableType“ erstellt, der aus den Spalten „CategoryID“ und „CategoryName“ besteht:  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 Nachdem Sie einen Tabellentyp erstellt haben, können Sie Tabellenwertparameter basierend auf diesem Typ deklarieren. Das folgende Transact-SQL-Fragment veranschaulicht, wie ein Tabellenwertparameter in der Definition einer gespeicherten Prozedur deklariert wird. Beachten Sie, dass das Schlüsselwort READONLY erforderlich ist, um einen Tabellenwertparameter zu deklarieren.  
  
```sql
CREATE PROCEDURE usp_UpdateCategories
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a>Ändern von Daten mit Tabellenwertparametern (Transact-SQL)  

 Um Tabellenwertparameter bei Datenänderungen zu verwenden, die auf Sätzen basieren und sich auf mehrere Zeilen auswirken, kann eine einzelne Anweisung ausgeführt werden. Beispielsweise können Sie alle Zeilen in einem Tabellenwertparameter auswählen und in eine Datenbanktabelle einfügen, oder Sie können eine update-Anweisung erstellen, indem Sie einen Tabellenwertparameter mit der Tabelle verbinden, die Sie aktualisieren möchten.  
  
 Mit der folgenden UPDATE-Anweisung in Transact-SQL wird veranschaulicht, wie ein Tabellenwertparameter durch einen Join mit der Categories-Tabelle verwendet wird. Wenn Sie einen Tabellenwertparameter mit einem JOIN in einer FROM-Klausel verwenden, müssen Sie auch einen Alias angeben, wie in diesem Beispiel gezeigt (der Alias des Tabellenwertparameters lautet „ec“):  
  
```sql
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 Dieses Transact-SQL-Beispiel veranschaulicht, wie Zeilen aus einem Tabellenwertparameter ausgewählt werden, um einen INSERT-Vorgang in einem einzelnen mengenbasierten Vorgang auszuführen.  
  
```sql
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a>Einschränkungen von Tabellenwertparametern  

 Bei Verwendung von Tabellenwertparametern müssen eine Reihe von Einschränkungen berücksichtigt werden:  
  
- Tabellenwertparameter können nicht an [benutzerdefinierte CLR-Funktionen](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions) übergeben werden.  
  
- Tabellenwertparameter können nur für die Unterstützung der UNIQUE- oder PRIMARY KEY-Einschränkungen indiziert werden. SQL Server verwaltet keine Statistiken für Tabellenwertparameter.  
  
- Tabellenwertparameter sind in Transact-SQL-Code schreibgeschützt. Sie können die Spaltenwerte in den Zeilen eines Tabellenwertparameters nicht aktualisieren, und Sie können keine Zeilen einfügen oder löschen. Um die Daten zu ändern, die an eine gespeicherte Prozedur oder eine parametrisierte Anweisung in einem Tabellenwertparameter übergeben werden, müssen Sie die Daten in eine temporäre Tabelle oder in eine Tabellenvariable einfügen.  
  
- Der Aufbau von Tabellenwertparametern kann nicht mithilfe von ALTER TABLE-Anweisungen geändert werden.  
  
## <a name="configuring-a-sqlparameter-example"></a>Konfigurieren eines SqlParameter-Beispiels  

 <xref:System.Data.SqlClient> unterstützt das Auffüllen von Tabellenwertparametern aus <xref:System.Data.DataTable>-, <xref:System.Data.Common.DbDataReader>- und <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord>-Objekten. Sie müssen mit der <xref:System.Data.SqlClient.SqlParameter.TypeName%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlParameter> einen Typnamen für den Tabellenwertparameter angeben. `TypeName` muss dem Namen eines kompatiblen Typs entsprechen, der zuvor auf dem Server erstellt wurde. Das folgende Codefragment zeigt, wie <xref:System.Data.SqlClient.SqlParameter> für das Einfügen von Daten konfiguriert wird.  

Im folgenden Beispiel enthält die Variable `addedCategories` eine <xref:System.Data.DataTable>. Weitere Informationen zum Füllen der Variable finden Sie in den Beispielen im nächsten Abschnitt [Übergeben eines Tabellenwertparameters an eine gespeicherte Prozedur](#passing).

```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```  
  
```vb  
' Configure the command and parameter.  
Dim insertCommand As New SqlCommand(sqlInsert, connection)  
Dim tvpParam As SqlParameter = _  
   insertCommand.Parameters.AddWithValue( _  
  "@tvpNewCategories", addedCategories)  
tvpParam.SqlDbType = SqlDbType.Structured  
tvpParam.TypeName = "dbo.CategoryTableType"  
```  
  
 Sie können auch jedes von <xref:System.Data.Common.DbDataReader> abgeleitete Objekt verwenden, um Datenzeilen per Streaming in einen Tabellenwertparameter zu übertragen, wie im folgenden Fragment dargestellt:  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
```vb  
' Configure the SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  dataReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
```  
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a><a name="passing"></a> Übergeben eines Tabellenwert Parameters an eine gespeicherte Prozedur  

 In diesem Beispiel wird veranschaulicht, wie Daten aus Tabellenwertparametern an eine gespeicherte Prozedur übergeben werden. Der Code extrahiert hinzugefügte Zeilen mithilfe der <xref:System.Data.DataTable>-Methode in eine neue <xref:System.Data.DataTable.GetChanges%2A>. Im Code wird dann ein <xref:System.Data.SqlClient.SqlCommand> definiert, wobei für die Eigenschaft <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> der Wert <xref:System.Data.CommandType.StoredProcedure> festgelegt wird. Der <xref:System.Data.SqlClient.SqlParameter> wird mit der <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A>-Methode aufgefüllt und für <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> wird `Structured` festgelegt. Anschließend wird der <xref:System.Data.SqlClient.SqlCommand> mit der Methode <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> ausgeführt.  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection object.  
Using connection  
   '  Create a DataTable with the modified rows.  
   Dim addedCategories As DataTable = _  
     CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Configure the SqlCommand and SqlParameter.  
   Dim insertCommand As New SqlCommand( _  
     "usp_InsertCategories", connection)  
   insertCommand.CommandType = CommandType.StoredProcedure  
   Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
     "@tvpNewCategories", addedCategories)  
   tvpParam.SqlDbType = SqlDbType.Structured  
  
   '  Execute the command.  
   insertCommand.ExecuteNonQuery()  
End Using  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a>Übergeben eines Tabellenwertparameters an eine parametrisierte SQL-Anweisung  

 Im folgenden Beispiel wird veranschaulicht, wie Daten in die Tabelle „dbo.Categories“ eingefügt werden. Dazu wird eine INSERT-Anweisung mit einer SELECT-Unterabfrage verwendet, die einen Tabellenwertparameter als Datenquelle nutzt. Wenn Sie einen Tabellenwertparameter an eine parametrisierte SQL-Anweisung übergeben, müssen Sie mithilfe der neuen Eigenschaft <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> eines <xref:System.Data.SqlClient.SqlParameter> einen Typnamen für den Tabellenwertparameter angeben. `TypeName` muss dem Namen eines kompatiblen Typs entsprechen, der zuvor auf dem Server erstellt wurde. Der Code in diesem Beispiel verwendet die Eigenschaft `TypeName`, um auf die in „dbo.CategoryTableType“ definierte Typstruktur zu verweisen.  
  
> [!NOTE]
> Wenn Sie einen Wert für eine Identitätsspalte in einem Tabellenwertparameter angeben, muss die SET IDENTITY_INSERT-Anweisung für die Sitzung verwendet werden.  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
Using connection  
  ' Create a DataTable with the modified rows.  
  Dim addedCategories As DataTable = _  
    CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Define the INSERT-SELECT statement.  
  Dim sqlInsert As String = _  
  "INSERT INTO dbo.Categories (CategoryID, CategoryName)" _  
  & " SELECT nc.CategoryID, nc.CategoryName" _  
  & " FROM @tvpNewCategories AS nc;"  
  
  ' Configure the command and parameter.  
  Dim insertCommand As New SqlCommand(sqlInsert, connection)  
  Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
    "@tvpNewCategories", addedCategories)  
  tvpParam.SqlDbType = SqlDbType.Structured  
  tvpParam.TypeName = "dbo.CategoryTableType"  
  
  ' Execute the query  
  insertCommand.ExecuteNonQuery()  
End Using  
```  
  
## <a name="streaming-rows-with-a-datareader"></a>Streaming von Zeilen mit einem DataReader  

 Sie können auch jedes von <xref:System.Data.Common.DbDataReader> abgeleitete Objekt verwenden, um Datenzeilen per Streaming in einen Tabellenwertparameter zu übertragen. Das folgende Codefragment zeigt, wie Daten mithilfe von <xref:System.Data.OracleClient.OracleCommand> und <xref:System.Data.OracleClient.OracleDataReader> aus einer Oracle-Datenbank abgerufen werden. Anschließend wird mit dem Code ein <xref:System.Data.SqlClient.SqlCommand> konfiguriert, um eine gespeicherte Prozedur mit einem einzigen Eingabeparameter aufzurufen. Für die Eigenschaft <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> des <xref:System.Data.SqlClient.SqlParameter> wird der Wert `Structured` festgelegt. Mithilfe von <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> wird das Resultset `OracleDataReader` als Tabellenwertparameter an die gespeicherte Prozedur übergeben.  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
' Retrieve data from Oracle.  
Dim selectCommand As New OracleCommand( _  
  "Select CategoryID, CategoryName FROM Categories;", _  
  oracleConnection)  
Dim oracleReader As OracleDataReader = _  
  selectCommand.ExecuteReader(CommandBehavior.CloseConnection)  
  
' Configure SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  oracleReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
  
' Execute the command.  
insertCommand.ExecuteNonQuery()  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Konfigurieren von Parametern und Parameterdatentypen](../configuring-parameters-and-parameter-data-types.md)
- [Befehle und Parameter](../commands-and-parameters.md)
- [DataAdapter-Parameter](../dataadapter-parameters.md)
- [SQL Server von Daten Vorgängen in ADO.net](sql-server-data-operations.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
