---
title: Auffüllen eines "DataSets" durch einen "DataAdapter"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fa0ac7d-e266-4954-bfac-3fbe2f913153
ms.openlocfilehash: ecfd2c3a31b42b380c593aef0bbc23775874cc7a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878201"
---
# <a name="populating-a-dataset-from-a-dataadapter"></a>Auffüllen eines "DataSets" durch einen "DataAdapter"
Das [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] von <xref:System.Data.DataSet> ist eine speicherresidente Datendarstellung, die ein konsistentes relationales und von der Datenquelle unabhängiges Programmiermodell bereitstellt. Das `DataSet` stellt eine vollständige Datengruppe einschließlich Tabellen, Einschränkungen und Beziehungen zwischen Tabellen dar. Da das `DataSet` von der Datenquelle unabhängig ist, kann ein `DataSet` sowohl lokale Daten einer Anwendung als auch Daten aus mehreren Datenquellen enthalten. Die Interaktion mit vorhandenen Datenquellen wird über den `DataAdapter`gesteuert.  
  
 Die `SelectCommand` -Eigenschaft des `DataAdapter` ist ein `Command` -Objekt, das Daten aus der Datenquelle abruft. Die `InsertCommand`-Eigenschaft, die `UpdateCommand`-Eigenschaft und die `DeleteCommand` -Eigenschaft des `DataAdapter` sind `Command` -Objekte, die Updates an den Daten in der Datenquelle entsprechend den Modifikationen an den Daten im `DataSet`verwalten. Diese Eigenschaften werden in ausführlicher behandelt [Aktualisieren von Datenquellen mit "DataAdapters"](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Mithilfe der `Fill` -Methode des `DataAdapter` wird ein `DataSet` mit den Ergebnissen vom `SelectCommand` des `DataAdapter`aufgefüllt. `Fill` verwendet als Argumente ein aufzufüllendes `DataSet` sowie ein `DataTable` -Objekt bzw. den Namen der `DataTable` , die mit den Zeilen gefüllt werden soll, die vom `SelectCommand`zurückgegeben werden.  
  
> [!NOTE]
>  Die Verwendung des `DataAdapter` zum Abrufen einer gesamten Tabelle kann einige Zeit in Anspruch nehmen, insbesondere, wenn die Tabelle viele Zeilen enthält. Der Grund hierfür ist, dass das Zugreifen auf die Datenbank und das Auffinden, Verarbeiten und Übertragen der Daten an den Client zeitaufwändig ist. Durch das Abrufen der gesamten Tabelle seitens des Clients werden außerdem alle ihre Zeilen auf dem Server gesperrt. Zur Verbesserung der Leistung können Sie die `WHERE` -Klausel verwenden, um die Anzahl der an den Client zurückgegebenen Zeilen deutlich zu reduzieren. Die Anzahl der an den Client zurückgegebenen Daten kann auch verringert werden, indem Sie in der `SELECT` -Anweisung nur die erforderlichen Spalten explizit auflisten. Eine weitere gute Möglichkeit, dieses Problem zu umgehen, besteht darin, die Zeilen in Stapeln (z. B. immer einige hundert Zeilen auf einmal) abzurufen, wobei der nächste Stapel erst dann abgerufen wird, wenn der Client mit dem aktuellen Stapel fertig ist.  
  
 Die `Fill` -Methode verwendet das `DataReader` -Objekt implizit, um die Spaltennamen und Spaltentypen zurückzugeben, mit denen die Tabellen im `DataSet`erstellt werden, sowie die Daten zum Füllen der Tabellenzeilen im `DataSet`. Tabellen und Spalten werden nur erstellt, wenn sie noch nicht vorhanden sind. Andernfalls verwendet die `Fill` -Methode das vorhandene `DataSet` -Schema. Spaltentypen werden als erstellt [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Typen entsprechend den Tabellen in [Datentypzuordnungen in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md). Primärschlüssel werden nur erstellt, wenn diese in der Datenquelle vorhanden sind und `DataAdapter`**gesteuert.**`MissingSchemaAction` auf `MissingSchemaAction`**gesteuert.**`AddWithKey`gesteuert. Wenn die `Fill` -Methode ermittelt, dass ein Primärschlüssel für eine Tabelle vorhanden ist, werden Daten im `DataSet` mit den Daten aus der Datenquelle überschrieben. Dies gilt für Zeilen, deren Werte in der Primärschlüsselspalte mit denen der Zeile übereinstimmen, die von der Datenquelle zurückgegeben wurde. Wurde kein Primärschlüssel gefunden, so werden die Daten an die Tabellen im `DataSet`angehängt. `Fill` verwendet Zuordnungen, die möglicherweise, beim Auffüllen bestehen der `DataSet` (finden Sie unter [DataAdapter DataTable- und DataColumn-Zuordnungen](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)).  
  
> [!NOTE]
>  Wenn vom `SelectCommand` die Ergebnisse eines OUTER JOIN zurückgegeben werden, wird vom `DataAdapter` kein `PrimaryKey` -Wert für die resultierende `DataTable`festgelegt. Sie müssen den `PrimaryKey` selbst definieren, um sicherzustellen, dass doppelte Zeilen ordnungsgemäß aufgelöst werden. Weitere Informationen finden Sie unter [Definieren von Primärschlüsseln](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 Im folgenden Codebeispiel wird eine Instanz eines <xref:System.Data.SqlClient.SqlDataAdapter> erstellt, die eine <xref:System.Data.SqlClient.SqlConnection> zur Microsoft SQL Server-Datenbank `Northwind` verwendet und eine <xref:System.Data.DataTable> in einem `DataSet` mit der Kundenliste füllt. Mit der SQL-Anweisung und den <xref:System.Data.SqlClient.SqlConnection> -Argumenten, die an den <xref:System.Data.SqlClient.SqlDataAdapter> -Konstruktor übergeben werden, wird die <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A> -Eigenschaft des <xref:System.Data.SqlClient.SqlDataAdapter>erstellt.  
  
## <a name="example"></a>Beispiel  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim queryString As String = _  
  "SELECT CustomerID, CompanyName FROM dbo.Customers"  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  queryString, connection)  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
string queryString =   
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
>  Der in diesem Beispiel dargestellte Code öffnet und schließt die `Connection`nicht explizit. Die `Fill` -Methode öffnet implizit die `Connection` , die vom `DataAdapter` verwendet wird, wenn die Verbindung nicht bereits geöffnet ist. Wenn die Verbindung durch `Fill` geöffnet wurde, wird sie nach dem `Fill` -Vorgang auch wieder geschlossen. Bei einzelnen Vorgängen wie `Fill` oder `Update`kann der Code auf diese Weise vereinfacht werden. Wenn Sie jedoch mehrere Vorgänge durchführen, für die eine geöffnete Verbindung erforderlich ist, können Sie die Leistung der Anwendung verbessern, indem Sie explizit die `Open` -Methode der `Connection`aufrufen, die Vorgänge für die Datenquelle durchführen und anschließend die `Close` -Methode der `Connection`aufrufen. Sie sollten die Verbindungen zur Datenquelle so kurz wie möglich geöffnet lassen, um die Ressourcen freizugeben, die von anderen Clientanwendungen verwendet werden.  
  
## <a name="multiple-result-sets"></a>Mehrere Resultsets  
 Wenn der `DataAdapter` mehrere Resultsets ermittelt, werden mehrere Tabellen im `DataSet`erstellt. Diesen Tabellen werden standardmäßig Namen nach dem Schema Table*N*, beginnend mit "Table" für Table0, zugewiesen, die jeweils um eins erhöht werden. Wenn der Tabellenname als Argument an die `Fill` -Methode übergeben wird, erhalten die Tabellen standardmäßig Namen nach dem Schema TableName*N*, beginnend mit "TableName" für TableName0, die jeweils um eins erhöht werden.  
  
## <a name="populating-a-dataset-from-multiple-dataadapters"></a>Auffüllen eines DataSets mit mehreren DataAdapter-Objekten  
 Eine beliebige Anzahl von `DataAdapter` Objekte können verwendet werden, mit einem `DataSet`. Mit jedem `DataAdapter` -Objekt können ein oder mehrere `DataTable` -Objekte gefüllt und Updates in die zugehörige Datenquelle übernommen werden. Das`DataRelation` -Objekt und das `Constraint` -Objekt können dem `DataSet` lokal hinzugefügt werden. Dadurch haben Sie die Möglichkeit, Daten aus mehreren unähnlichen Datenquellen zu verbinden. Ein `DataSet` kann beispielsweise Daten aus einer Microsoft SQL Server-Datenbank, einer über OLE DB verfügbar gemachten IBM DB2-Datenbank und einer XML-Datenquelle enthalten. Für die Kommunikation mit den einzelnen Datenquellen sind ein oder mehrere `DataAdapter` -Objekte zuständig.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Kundenliste aus der `Northwind` -Datenbank unter Microsoft SQL Server sowie eine Auftragsliste aus der in Microsoft Access 2000 gespeicherten `Northwind` -Datenbank aufgefüllt. Die gefüllten Tabellen werden mit einer `DataRelation`verbunden, und die Kundenliste wird anschließend mit Aufträgen für den jeweiligen Kunden angezeigt. Weitere Informationen zu `DataRelation` Objekten finden Sie [Hinzufügen von "DataRelations"](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md) und [Navigieren in DataRelations](../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md).  
  
```vb  
' Assumes that customerConnection is a valid SqlConnection object.  
' Assumes that orderConnection is a valid OleDbConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", customerConnection)  
  
Dim ordAdapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SELECT * FROM Orders", orderConnection)  
  
Dim customerOrders As DataSet = New DataSet()  
custAdapter.Fill(customerOrders, "Customers")  
ordAdapter.Fill(customerOrders, "Orders")  
  
Dim relation As DataRelation = _  
  customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustomerID"), _   
  customerOrders.Tables("Orders").Columns("CustomerID"))  
  
Dim pRow, cRow As DataRow  
For Each pRow In customerOrders.Tables("Customers").Rows  
  Console.WriteLine(pRow("CustomerID").ToString())  
  
  For Each cRow In pRow.GetChildRows(relation)  
    Console.WriteLine(vbTab & cRow("OrderID").ToString())  
  Next  
Next  
```  
  
```csharp  
// Assumes that customerConnection is a valid SqlConnection object.  
// Assumes that orderConnection is a valid OleDbConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", customerConnection);  
OleDbDataAdapter ordAdapter = new OleDbDataAdapter(  
  "SELECT * FROM Orders", orderConnection);  
  
DataSet customerOrders = new DataSet();  
  
custAdapter.Fill(customerOrders, "Customers");  
ordAdapter.Fill(customerOrders, "Orders");  
  
DataRelation relation = customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustomerID"],  
  customerOrders.Tables["Orders"].Columns["CustomerID"]);  
  
foreach (DataRow pRow in customerOrders.Tables["Customers"].Rows)  
{  
  Console.WriteLine(pRow["CustomerID"]);  
   foreach (DataRow cRow in pRow.GetChildRows(relation))  
    Console.WriteLine("\t" + cRow["OrderID"]);  
}  
```  
  
## <a name="sql-server-decimal-type"></a>SQL Server-Typ "decimal"  
 In der Standardeinstellung werden Daten des `DataSet` mithilfe von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datentypen gespeichert. Für die meisten Anwendungen sind diese sehr gut zur Darstellung der Informationen aus der Datenquelle geeignet. Diese Darstellung kann jedoch problematisch werden, wenn es sich bei dem Datentyp in der Datenquelle um den SQL Server-Datentyp „decimal“ oder um einen numerischen Datentyp handelt. Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] `decimal` data type allows a maximum of 28 significant digits, whereas the SQL Server `decimal` data type allows 38 significant digits. Wenn der `SqlDataAdapter` während eines `Fill` -Vorgangs feststellt, dass die Präzision eines SQL Server-Felds mit dem Datentyp `decimal` mehr als 28 Zeichen beträgt, wird der `DataTable`die aktuelle Zeile nicht hinzugefügt. Stattdessen tritt das `FillError` -Ereignis auf. Dadurch können Sie überprüfen, ob ein Präzisionsverlust eintritt, und Sie können entsprechend reagieren. Weitere Informationen zu den `FillError` Ereignis finden Sie unter [Behandeln von DataAdapter-Ereignissen](../../../../docs/framework/data/adonet/handling-dataadapter-events.md). Den SQL Server-Wert `decimal` erhalten Sie auch, indem Sie ein <xref:System.Data.SqlClient.SqlDataReader> -Objekt verwenden und die <xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A> -Methode aufrufen.  
  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 enthält erweiterte Unterstützung für <xref:System.Data.SqlTypes> im `DataSet`. Weitere Informationen finden Sie unter [SqlTypes and the DataSet](../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md).  
  
## <a name="ole-db-chapters"></a>OLE DB-Kapitel  
 Hierarchische Rowsets oder Kapitel (OLE DB-Typ `DBTYPE_HCHAPTER`, ADO-Typ `adChapter`) können zum Füllen des `DataSet`-Inhalts verwendet werden. Wenn das <xref:System.Data.OleDb.OleDbDataAdapter> -Objekt während eines `Fill` -Vorgangs eine in Kapitel unterteilte Spalte ermittelt, wird für diese Spalte eine `DataTable` erstellt, die mit den Spalten und Zeilen aus dem Kapitel gefüllt wird. Als Name der Tabelle, die für die in Kapitel unterteilte Spalte erstellt wird, werden der Name der übergeordneten Tabelle und der Name der in Kapitel unterteilten Spalte im folgenden Format verwendet: "*ParentTableNameChapteredColumnName*". Wenn im `DataSet` bereits eine Tabelle vorhanden ist, deren Name dem Namen der in Kapitel unterteilten Spalte entspricht, wird die aktuelle Tabelle mit den Kapiteldaten gefüllt. Wenn in einer vorhandenen Tabelle keine Spalte existiert, die einer Spalte im Kapitel entspricht, wird eine neue Spalte hinzugefügt.  
  
 Bevor die Tabellen im `DataSet` mit den Daten in den in Kapitel unterteilten Spalten gefüllt werden, wird eine Beziehung zwischen der übergeordneten und der untergeordneten Tabelle des hierarchischen Rowsets erstellt, indem sowohl der übergeordneten als auch der untergeordneten Tabelle eine Ganzzahlenspalte hinzugefügt wird. Für die übergeordnete Spalte wird die automatische Erhöhung festgelegt, und mit den hinzugefügten Spalten beider Tabellen wird eine `DataRelation` erstellt. Die hinzugefügte Beziehung wird unter Verwendung des Namens der übergeordneten Tabelle und des Namens der Kapitelspalte folgendermaßen benannt: "*ParentTableNameChapterColumnName*".  
  
 Beachten Sie, dass die entsprechende Spalte nur im `DataSet`vorhanden ist. Bei nachfolgenden Füllungen aus der Datenquelle werden den Tabellen möglicherweise neue Zeilen hinzugefügt, anstatt die Änderungen in vorhandene Zeilen zusammenzuführen.  
  
 Beachten Sie auch, dass bei Verwendung der `DataAdapter.Fill` -Überladung mit einer `DataTable`nur diese Tabelle gefüllt wird. Eine Ganzzahlenspalte mit automatischer Erhöhung wird der Tabelle ebenfalls hinzugefügt, es wird jedoch keine untergeordnete Tabelle erstellt oder gefüllt und keine Beziehung erstellt.  
  
 Im folgenden Beispiel wird mit dem MSDataShape-Anbieter eine Kapitelspalte von Bestellungen für jeden Kunden aus einer Kundenliste generiert. Anschließend wird ein `DataSet` mit den Daten gefüllt.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=northwind")  
  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
  
Dim customers As DataSet = New DataSet()  
  
adapter.Fill(customers, "Customers")  
End Using  
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection("Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=(local);Integrated Security=SSPI;Initial Catalog=northwind"))  
{  
OleDbDataAdapter adapter = new OleDbDataAdapter("SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
}  
```  
  
 Nach Abschluss des `Fill` -Vorgangs enthält das `DataSet` zwei Tabellen: `Customers` und `CustomersOrders`, wobei `CustomersOrders` die in Kapitel unterteilte Spalte darstellt. Eine weitere Spalte mit dem Namen `Orders` wird der Tabelle `Customers` hinzugefügt. Der Tabelle `CustomersOrders` wird eine zusätzliche Spalte mit dem Namen `CustomersOrders` hinzugefügt. Die Spalte `Orders` in der Tabelle `Customers` wird auf die automatische Erhöhung festgelegt. Eine `DataRelation`, nämlich `CustomersOrders`, wird mithilfe der Spalten erstellt, die den Tabellen mit `Customers` als übergeordnete Tabelle hinzugefügt wurden. In den folgenden Tabellen sind einige Beispiele dargestellt.  
  
### <a name="tablename-customers"></a>TableName: Kunden  
  
|CustomerID|CompanyName|Orders|  
|----------------|-----------------|------------|  
|ALFKI|Alfreds Futterkiste|0|  
|ANATR|Ana Trujillo Emparedados y helados|1|  
  
### <a name="tablename-customersorders"></a>TableName: CustomersOrders  
  
|CustomerID|OrderID|CustomersOrders|  
|----------------|-------------|---------------------|  
|ALFKI|10643|0|  
|ALFKI|10692|0|  
|ANATR|10308|1|  
|ANATR|10625|1|  
  
## <a name="see-also"></a>Siehe auch

- [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Datentypzuordnungen in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)
- [Ändern von Daten mit DbDataAdapter](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)
- [Multiple Active Result Sets (MARS)](../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
