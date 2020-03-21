---
title: DataAdapter-Parameter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f21e6aba-b76d-46ad-a83e-2ad8e0af1e12
ms.openlocfilehash: 9954570dcf33c5eea4dcccf880de2c307de0aeca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151545"
---
# <a name="dataadapter-parameters"></a>DataAdapter-Parameter
Der <xref:System.Data.Common.DbDataAdapter> verfügt über vier Eigenschaften, die zum Abrufen von Daten aus einer Datenquelle und zum Aktualisieren der Daten in der Datenquelle verwendet werden: die <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A>-Eigenschaft gibt die Daten aus der Datenquelle zurück, und die Eigenschaften <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> und <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> dienen zum Verwalten von Änderungen in der Datenquelle. Die `SelectCommand`-Eigenschaft muss vor dem Aufrufen der `Fill`-Methode des `DataAdapter` festgelegt werden. Die Eigenschaft `InsertCommand`, `UpdateCommand` oder `DeleteCommand` (abhängig von der Art der Änderungen in der `Update`) muss vor dem Aufruf der `DataAdapter`-Methode des <xref:System.Data.DataTable> festgelegt werden. Wenn beispielsweise Zeilen hinzugefügt wurden, muss vor dem Aufrufen von `InsertCommand` das `Update` festgelegt werden. Wenn `Update` eine eingefügte, aktualisierte oder gelöschte Zeile verarbeitet, verwendet der `DataAdapter` die entsprechende `Command`-Eigenschaft, um die Aktion zu verarbeiten. Aktuelle Informationen zur geänderten Zeile werden über die `Command`-Auflistung an das `Parameters`-Objekt übergeben.  
  
 Wenn Sie eine Zeile in der Datenquelle aktualisieren, rufen Sie die UPDATE-Anweisung auf, die einen eindeutigen Bezeichner verwendet, um die Zeile in der zu aktualisierenden Tabelle zu identifizieren. Der eindeutige Bezeichner ist im Allgemeinen der Wert eines Primärschlüsselfelds. Die UPDATE-Anweisung verwendet Parameter, die sowohl den eindeutigen Bezeichner als auch die Spalten und Werte enthalten, die aktualisiert werden sollen, wie in der folgenden Transact-SQL-Anweisung dargestellt.  
  
```sql
UPDATE Customers SET CompanyName = @CompanyName
  WHERE CustomerID = @CustomerID  
```  
  
> [!NOTE]
> Die Syntax für Parameterplatzhalter ist abhängig von der jeweiligen Datenquelle. Dieses Beispiel zeigt Platzhalter für eine SQL Server-Datenquelle. Verwenden Sie Fragezeichenplatzhalter (?) für <xref:System.Data.OleDb>-Parameter und <xref:System.Data.Odbc>-Parameter.  
  
 In diesem Visual Basic-Beispiel wird `CompanyName` das Feld `@CompanyName` mit dem `CustomerID` Wert des Parameters `@CustomerID` für die Zeile aktualisiert, wobei der Wert des Parameters gleich ist. Die Parameter rufen Informationen aus <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> der geänderten Zeile mithilfe der Eigenschaft des <xref:System.Data.SqlClient.SqlParameter> Objekts ab. Im Folgenden finden Sie die Parameter für das vorherige Beispiel einer UPDATE-Anweisung. Der Code geht davon aus, dass die `adapter`-Variable für ein gültiges <xref:System.Data.SqlClient.SqlDataAdapter>-Objekt steht.  
  
```vb
adapter.Parameters.Add( _  
  "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
Dim parameter As SqlParameter = _  
  adapter.UpdateCommand.Parameters.Add("@CustomerID", _  
  SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
```  
  
 Die `Add`-Methode der `Parameters`-Auflistung nimmt den Namen des Parameters, den Datentyp, die Größe (wenn für den Typ zutreffend) und den Namen der <xref:System.Data.Common.DbParameter.SourceColumn%2A> aus der `DataTable` an. Beachten Sie, dass der <xref:System.Data.Common.DbParameter.SourceVersion%2A>-Wert des `@CustomerID`-Parameters `Original` lautet. Dadurch wird sichergestellt, dass die vorhandene Zeile in der Datenquelle aktualisiert wird, wenn sich der Wert der ID-Spalte oder -Spalten in der geänderten <xref:System.Data.DataRow> geändert hat. In diesem Fall stimmt der `Original`-Zeilenwert mit dem aktuellen Wert in der Datenquelle überein, und der `Current`-Zeilenwert enthält den aktualisierten Wert. Die `SourceVersion` für den `@CompanyName`-Parameter ist nicht festgelegt, und es wird der Standardwert, nämlich der `Current`-Zeilenwert, verwendet.  
  
> [!NOTE]
> Sowohl für `Fill` die `DataAdapter` Vorgänge `Get` der als `DataReader`auch für die Methoden des wird der .NET Framework-Typ aus dem vom .NET Framework-Datenanbieter zurückgegebenen Typ abgeleitet. Die abgeleiteten .NET Framework-Typen und Accessormethoden für Microsoft SQL Server-, OLE DB- und ODBC-Datentypen werden in [Datentypzuordnungen in ADO.NET](data-type-mappings-in-ado-net.md)beschrieben.  
  
## <a name="parametersourcecolumn-parametersourceversion"></a>Parameter.SourceColumn, Parameter.SourceVersion  
 Die `SourceColumn` und die `SourceVersion` können als Argumente an den `Parameter`-Konstruktor übergeben oder als Eigenschaften eines vorhandenen `Parameter` festgelegt werden. Die `SourceColumn` ist der Name der <xref:System.Data.DataColumn> aus der <xref:System.Data.DataRow>, aus der der Wert des `Parameter` abgerufen wird. Die `SourceVersion` gibt die `DataRow`-Version an, die der `DataAdapter` zum Abrufen des Werts verwendet.  
  
 Die folgende Tabelle zeigt die <xref:System.Data.DataRowVersion>-Enumerationswerte an, die für die Verwendung mit `SourceVersion` zur Verfügung stehen.  
  
|DataRowVersion-Enumeration|Beschreibung|  
|--------------------------------|-----------------|  
|`Current`|Der Parameter verwendet den aktuellen Wert der Spalte. Dies ist die Standardoption.|  
|`Default`|Der Parameter verwendet den `DefaultValue` der Spalte.|  
|`Original`|Der Parameter verwendet den ursprünglichen Wert der Spalte.|  
|`Proposed`|Der Parameter verwendet einen vorgeschlagenen Wert.|  
  
 Das `SqlClient`-Codebeispiel im nächsten Abschnitt definiert einen Parameter für einen <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, bei dem die `CustomerID`-Spalte als `SourceColumn` für die folgenden beiden Parameter verwendet wird: `@CustomerID` (`SET CustomerID = @CustomerID`) und `@OldCustomerID` (`WHERE CustomerID = @OldCustomerID`). Der `@CustomerID` Parameter wird verwendet, um die **CustomerID-Spalte** auf den aktuellen Wert im zu `DataRow`aktualisieren. Als Ergebnis wird `CustomerID` `SourceColumn` die `SourceVersion` `Current` mit a verwendet. Der `@OldCustomerID` Parameter wird verwendet, um die aktuelle Zeile in der Datenquelle zu identifizieren. Da sich der passende Spaltenwert in der `Original`-Version der Zeile befindet, wird die gleiche `SourceColumn` (`CustomerID`) mit einer `SourceVersion` von `Original` verwendet.  
  
## <a name="working-with-sqlclient-parameters"></a>Verwenden von "SqlClient"-Parametern  
 Im folgenden Beispiel wird gezeigt, wie Sie einen <xref:System.Data.SqlClient.SqlDataAdapter> erstellen und für die <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A><xref:System.Data.MissingSchemaAction.AddWithKey> festlegen können, um zusätzliche Schemainformationen aus der Datenbank abzurufen. Die Eigenschaften <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A> und <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> werden festgelegt, und die zugehörigen <xref:System.Data.SqlClient.SqlParameter>-Objekte werden der <xref:System.Data.SqlClient.SqlCommand.Parameters%2A>-Auflistung hinzugefügt. Die Methode gibt ein `SqlDataAdapter`-Objekt zurück.  
  
 [!code-csharp[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/CS/source.cs#1)]
 [!code-vb[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/VB/source.vb#1)]  
  
## <a name="oledb-parameter-placeholders"></a>"OleDb"-Parameterplatzhalter  
 Für das <xref:System.Data.OleDb.OleDbDataAdapter>-Objekt und das <xref:System.Data.Odbc.OdbcDataAdapter>-Objekt müssen zum Identifizieren der Parameter Fragezeichenplatzhalter (?) verwendet werden.  
  
```vb  
Dim selectSQL As String = _  
  "SELECT CustomerID, CompanyName FROM Customers " & _  
  "WHERE CountryRegion = ? AND City = ?"  
Dim insertSQL AS String = _  
  "INSERT INTO Customers (CustomerID, CompanyName) VALUES (?, ?)"  
Dim updateSQL AS String = _  
  "UPDATE Customers SET CustomerID = ?, CompanyName = ? " & _  
  WHERE CustomerID = ?"  
Dim deleteSQL As String = "DELETE FROM Customers WHERE CustomerID = ?"  
```  
  
```csharp  
string selectSQL =
  "SELECT CustomerID, CompanyName FROM Customers " +  
  "WHERE CountryRegion = ? AND City = ?";  
string insertSQL =
  "INSERT INTO Customers (CustomerID, CompanyName) " +  
  "VALUES (?, ?)";  
string updateSQL =
  "UPDATE Customers SET CustomerID = ?, CompanyName = ? " +  
  "WHERE CustomerID = ? ";  
string deleteSQL = "DELETE FROM Customers WHERE CustomerID = ?";  
```  
  
 Die parametrisierten Abfrageanweisungen definieren, welche Eingabe- und Ausgabeparameter erstellt werden müssen. Verwenden Sie zum Erstellen eines Parameters die `Parameters.Add`-Methode oder den `Parameter`-Konstruktor, um den Spaltennamen, den Datentyp und die Größe anzugeben. Für systeminterne Datentypen, wie `Integer`, muss die Größe nicht angegeben werden. Sie können auch die Standardgröße angeben.  
  
 Das folgende Codebeispiel erstellt die Parameter für eine SQL-Anweisung und füllt dann ein `DataSet`.  
  
## <a name="oledb-example"></a>OLE DB-Beispiel  
  
```vb  
' Assumes that connection is a valid OleDbConnection object.  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter
  
Dim selectCMD AS OleDbCommand = New OleDbCommand(selectSQL, connection)  
adapter.SelectCommand = selectCMD  
  
' Add parameters and set values.  
selectCMD.Parameters.Add( _  
  "@CountryRegion", OleDbType.VarChar, 15).Value = "UK"  
selectCMD.Parameters.Add( _  
  "@City", OleDbType.VarChar, 15).Value = "London"  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid OleDbConnection object.  
OleDbDataAdapter adapter = new OleDbDataAdapter();  
  
OleDbCommand selectCMD = new OleDbCommand(selectSQL, connection);  
adapter.SelectCommand = selectCMD;  
  
// Add parameters and set values.  
selectCMD.Parameters.Add(  
  "@CountryRegion", OleDbType.VarChar, 15).Value = "UK";  
selectCMD.Parameters.Add(  
  "@City", OleDbType.VarChar, 15).Value = "London";  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
## <a name="odbc-parameters"></a>ODBC-Parameter  
  
```vb  
' Assumes that connection is a valid OdbcConnection object.  
Dim adapter As OdbcDataAdapter = New OdbcDataAdapter  
  
Dim selectCMD AS OdbcCommand = New OdbcCommand(selectSQL, connection)  
adapter.SelectCommand = selectCMD  
  
' Add Parameters and set values.  
selectCMD.Parameters.Add("@CountryRegion", OdbcType.VarChar, 15).Value = "UK"  
selectCMD.Parameters.Add("@City", OdbcType.VarChar, 15).Value = "London"  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid OdbcConnection object.  
OdbcDataAdapter adapter = new OdbcDataAdapter();  
  
OdbcCommand selectCMD = new OdbcCommand(selectSQL, connection);  
adapter.SelectCommand = selectCMD;  
  
//Add Parameters and set values.  
selectCMD.Parameters.Add("@CountryRegion", OdbcType.VarChar, 15).Value = "UK";  
selectCMD.Parameters.Add("@City", OdbcType.VarChar, 15).Value = "London";  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
> Wenn für einen Parameter kein Parametername angegeben wird, erhält der Parameter einen inkrementellen Standardnamen des Parameters*N* *,* beginnend mit "Parameter1". Es wird empfohlen, die Namenskonvention des Parameters*N* zu vermeiden, wenn Sie einen Parameternamen angeben, da der von Ihnen angegebene Name möglicherweise mit einem vorhandenen Standardparameternamen im in Konflikt `ParameterCollection`steht. Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.  
  
## <a name="see-also"></a>Weitere Informationen

- [DataAdapters und DataReaders](dataadapters-and-datareaders.md)
- [Befehle und Parameter](commands-and-parameters.md)
- [Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)](updating-data-sources-with-dataadapters.md)
- [Ändern von Daten mit gespeicherten Prozeduren](modifying-data-with-stored-procedures.md)
- [Datentypzuordnungen in ADO.NET](data-type-mappings-in-ado-net.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
