---
title: Tabellenwertparameter
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: d99cea1641dc61c1cae6d6b1634359211ce788ae
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452304"
---
# <a name="table-valued-parameters"></a>Tabellenwertparameter
Tabellenwertparameter bieten eine einfache Möglichkeit zum Marshallen mehrerer Datenzeilen aus einer Clientanwendung nach SQL Server, ohne dass mehrere Roundtrips oder eine spezielle serverseitige Logik für die Verarbeitung der Daten erforderlich sind. Sie können Tabellenwertparameter verwenden, um Datenzeilen in einer Clientanwendung zu kapseln und die Daten in einem einzigen parametrisierten Befehl an den Server zu senden. Die eingehenden Datenzeilen werden in einer Tabellenvariablen gespeichert, die anschließend mit Transact-SQL verarbeitet werden kann.  
  
 Für den Zugriff auf Spaltenwerte in Tabellenwertparametern können Standard-SELECT-Anweisungen in Transact-SQL verwendet werden. Tabellenwertparameter sind stark typisiert, und ihre Struktur wird automatisch validiert. Die Größe der Tabellenwertparameter wird nur vom Serverarbeitsspeicher beschränkt.  
  
> [!NOTE]
> Daten in einem Tabellenwertparameter können nicht zurückgegeben werden. Tabellenwertparameter sind reine Eingabeparameter; das OUTPUT-Schlüsselwort wird nicht unterstützt.  
  
 Weitere Informationen über Tabellenwertparameter finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Verwenden von Tabellenwertparameter (Datenbank-Engine)](/sql/relational-databases/tables/use-table-valued-parameters-database-engine)|Beschreibt das Erstellen und Verwenden von Tabellenwertparametern.|  
|[Benutzerdefinierte Tabellentypen](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))|Beschreibt die benutzerdefinierten Tabellentypen, die zum Deklarieren von Tabellenwertparametern verwendet werden.|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a>Übergeben von mehreren Zeilen in älteren Versionen von SQL Server  
 Vor der Einführung von Tabellenwertparametern in SQL Server 2008 bestanden nur eingeschränkte Möglichkeiten zum Übergeben mehrerer Datenzeilen an eine gespeicherte Prozedur oder einen parametrisierten SQL-Befehl. Ein Entwickler konnte aus den folgenden Optionen zum Übergeben mehrerer Zeilen an den Server auswählen:  
  
- Er hatte die Möglichkeit, eine Reihe einzelner Parameter zu verwenden, um die Werte in mehreren Spalten und Zeilen von Daten darzustellen. Die Datenmenge, die mithilfe dieser Methode übergeben werden kann, ist durch die Anzahl der zulässigen Parameter beschränkt. SQL Server-Prozeduren können höchstens über 2100 Parameter verfügen. Eine Zusammenstellung zur Verarbeitung dieser einzelnen Werte in einer Tabellenvariablen oder einer temporären Tabelle erfordert serverseitige Logik.  
  
- Ein Entwickler hatte weiterhin die Möglichkeit, mehrere Datenwerte in voneinander getrennten Zeichenfolgen oder in XML-Dokumenten zu bündeln und diese Textwerte anschließend an eine Prozedur oder Anweisung zu übergeben. Bei dieser Methode muss die Prozedur oder Anweisung die erforderliche Logik zum Überprüfen der Datenstrukturen sowie zum Entbündeln der Werte beinhalten.  
  
- Ein Entwickler konnte weiterhin eine Reihe einzelner SQL-Datenänderungsanweisungen erstellen, die mehrere Zeilen betreffen, wie beispielsweise Anweisungen, die durch den Aufruf der `Update`-Methode eines <xref:System.Data.SqlClient.SqlDataAdapter> erstellt werden. Die Änderungen können dabei einzeln oder in Gruppen gestapelt an den Server gesendet werden. Jede Anweisung wird jedoch auf dem Server einzeln ausgeführt, auch wenn die Anweisungen in Stapeln übermittelt werden.  
  
- Das `bcp`-Hilfsprogramm und das <xref:System.Data.SqlClient.SqlBulkCopy>-Objekt bieten ebenfalls die Möglichkeit, mehrere Datenzeilen in eine Tabelle zu laden. Obwohl diese Technik sehr effizient ist, bietet sie keine Unterstützung für serverseitige Verarbeitung, wenn die Daten nicht in eine temporäre Tabelle oder Tabellenvariable geladen werden.  
  
## <a name="creating-table-valued-parameter-types"></a>Erstellen von Tabellenwertparameter-Typen  
 Tabellenwertparameter basieren auf stark typisierten Tabellenstrukturen, die mit CREATE TYPE-Anweisungen in Transact-SQL definiert werden. Sie müssen einen Tabellentyp erstellen und die Struktur in SQL Server definieren, bevor Sie Tabellenwertparameter in Ihren Clientanwendungen verwenden können. Weitere Informationen zum Erstellen von Tabellentypen finden Sie unter [Benutzerdefinierte Tabellentypen](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).  
  
 Die folgende Anweisung erstellt einen Tabellentyp mit dem Namen &lt;legacyBold&gt;CategoryTableType&lt;/legacyBold&gt;, der aus den Spalten &lt;legacyBold&gt;CategoryID&lt;/legacyBold&gt; und &lt;legacyBold&gt;CategoryName&lt;/legacyBold&gt; besteht:  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 Nach der Erstellung eines Tabellentyps können Tabellenwertparameter auf Grundlage dieses Typs deklariert werden. Das folgende Transact-SQL-Fragment veranschaulicht, wie ein Tabellenwertparameter in der Definition einer gespeicherten Prozedur deklariert wird. Beachten Sie, dass das READONLY-Schlüsselwort zum Deklarieren eines Tabellenwertparameters erforderlich ist.  
  
```sql
CREATE PROCEDURE usp_UpdateCategories   
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a>Ändern von Daten mit Tabellenwertparametern (Transact-SQL)  
 Tabellenwertparameter können in mengenbasierten Datenänderungen verwendet werden, die mehrere Zeilen mit der Ausführung einer einzelnen Anweisung beeinflussen können. So können Sie z. B. alle Zeilen in einem Tabellenwertparameter auswählen und diese in eine Datenbanktabelle einfügen, oder Sie können eine Updateanweisung erstellen, indem Sie einen Tabellenwertparameter mit der zu aktualisierenden Tabelle verknüpfen.  
  
 Mit der folgenden UPDATE-Anweisung in Transact-SQL wird veranschaulicht, wie ein Tabellenwertparameter durch einen Join mit der Categories-Tabelle verwendet wird. Wenn Sie einen Tabellenwertparameter mit einem JOIN in einer FROM-Klausel verwenden, müssen Sie diesen ebenfalls mit einem Alias versehen. Dies ist im folgenden Beispiel dargestellt, in dem der Tabellenwertparameter mit dem Alias "ec" versehen ist:  
  
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
 Es gibt mehrere Einschränkungen bei Tabellenwertparametern:  
  
- Tabellenwertparameter können nicht an [benutzerdefinierte CLR-Funktionen](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions) übergeben werden.  
  
- Tabellenwertparameter können nur zur Unterstützung von UNIQUE- und PRIMARY KEY-Einschränkungen indiziert werden. SQL Server verwaltet keine Statistiken für Tabellenwertparameter.  
  
- Tabellenwertparameter sind in Transact-SQL-Code schreibgeschützt. Die Spaltenwerte in den Zeilen eines Tabellenwertparameters können nicht aktualisiert werden, und Zeilen können nicht eingefügt oder gelöscht werden. Um die Daten zu ändern, die in einem Tabellenwertparameter an eine gespeicherte Prozedur oder eine parametrisierte Anweisung übergeben werden, müssen die Daten in eine temporäre Tabelle oder eine Tabellenvariable eingefügt werden.  
  
- Es können keine ALTER TABLE-Anweisungen zum Ändern des Entwurfs von Tabellenwertparametern verwendet werden.  
  
## <a name="configuring-a-sqlparameter-example"></a>Konfigurieren eines SqlParameter-Beispiels  
 <xref:System.Data.SqlClient> unterstützt das Auffüllen von Tabellenwertparametern aus <xref:System.Data.DataTable>-, <xref:System.Data.Common.DbDataReader>- und <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord>-Objekten. Sie müssen mit der <xref:System.Data.SqlClient.SqlParameter.TypeName%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlParameter> einen Typnamen für den Tabellenwertparameter angeben. Der `TypeName` muss dem Namen eines kompatiblen Typs entsprechen, der zuvor auf dem Server erstellt wurde. Das folgende Codefragment zeigt, wie <xref:System.Data.SqlClient.SqlParameter> konfiguriert werden kann, um Daten einzufügen:  
 
Im folgenden Beispiel enthält die Variable `addedCategories` eine <xref:System.Data.DataTable>. Informationen zum Füllen der Variablen finden Sie in den Beispielen im nächsten Abschnitt [übergeben eines Tabellenwert Parameters an eine gespeicherte Prozedur](#passing).

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
  
## <a name="passing"></a>Übergeben eines Tabellenwert Parameters an eine gespeicherte Prozedur  
 In diesem Beispiel wird veranschaulicht, wie Daten eines Tabellenwertparameters an eine gespeicherte Prozedur übergeben werden. Der Code ruft hinzugefügte Zeilen mithilfe der <xref:System.Data.DataTable>-Methode in eine neue <xref:System.Data.DataTable.GetChanges%2A> ab. Anschließend definiert der Code einen <xref:System.Data.SqlClient.SqlCommand>, mit dem die <xref:System.Data.SqlClient.SqlCommand.CommandType%2A>-Eigenschaft auf <xref:System.Data.CommandType.StoredProcedure> festgelegt wird. Der <xref:System.Data.SqlClient.SqlParameter> wird mit der <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A>-Methode aufgefüllt, und der <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> wird auf `Structured` festgelegt. Der <xref:System.Data.SqlClient.SqlCommand> wird dann mithilfe der <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>-Methode ausgeführt.  
  
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
 Im folgenden Beispiel wird veranschaulicht, wie Daten unter Verwendung einer INSERT-Anweisung mit einer SELECT-Unterabfrage, die über einen Tabellenwertparameter als Datenquelle verfügt, in die {1}dbo.Categories{2}-Tabelle eingefügt werden. Beim Übergeben eines Tabellenwertparameters an eine parametrisierte SQL-Anweisung muss ein Typname für den Tabellenwertparameter angegeben werden, indem die neue <xref:System.Data.SqlClient.SqlParameter.TypeName%2A>-Eigenschaft eines <xref:System.Data.SqlClient.SqlParameter> verwendet wird. Dieser `TypeName` muss dem Namen eines kompatiblen Typs entsprechen, der zuvor auf dem Server erstellt wurde. Im Code in diesem Beispiel wird die `TypeName`-Eigenschaft verwendet, um auf die in &lt;legacyBold&gt;dbo.CategoryTableType&lt;/legacyBold&gt; definierte Typstruktur zu verweisen.  
  
> [!NOTE]
> Wenn ein Wert für eine Identitätsspalte in einem Tabellenwertparameter angegeben wird, muss die SET IDENTITY_INSERT-Anweisung für die Sitzung ausgegeben werden.  
  
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
 Sie können auch jedes von <xref:System.Data.Common.DbDataReader> abgeleitete Objekt verwenden, um Datenzeilen per Streaming in einen Tabellenwertparameter zu übertragen. Im folgenden Codefragment wird veranschaulicht, wie Daten mithilfe eines <xref:System.Data.OracleClient.OracleCommand> und eines <xref:System.Data.OracleClient.OracleDataReader> aus einer Oracle-Datenbank abgerufen werden. Im Code wird dann ein <xref:System.Data.SqlClient.SqlCommand> konfiguriert, um eine gespeicherte Prozedur mit einem einzelnen Eingabeparameter aufzurufen. Die <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A>-Eigenschaft von <xref:System.Data.SqlClient.SqlParameter> wird auf `Structured` festgelegt. Die <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A>-Methode übergibt das `OracleDataReader`-Resultset als Tabellenwertparameter an die gespeicherte Prozedur.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren von Parametern und Parameterdatentypen](../configuring-parameters-and-parameter-data-types.md)
- [Befehle und Parameter](../commands-and-parameters.md)
- [DataAdapter-Parameter](../dataadapter-parameters.md)
- [SQL Server Data Operations in ADO.NET (SQL Server-Datenvorgänge in ADO.NET)](sql-server-data-operations.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
