---
title: DataAdapter-Parameter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f21e6aba-b76d-46ad-a83e-2ad8e0af1e12
ms.openlocfilehash: 83fc3101b0eb428def6cbc446e634e9bb45de350
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785613"
---
# <a name="dataadapter-parameters"></a><span data-ttu-id="0096d-102">DataAdapter-Parameter</span><span class="sxs-lookup"><span data-stu-id="0096d-102">DataAdapter Parameters</span></span>
<span data-ttu-id="0096d-103">Der <xref:System.Data.Common.DbDataAdapter> verfügt über vier Eigenschaften, die zum Abrufen von Daten aus einer Datenquelle und zum Aktualisieren der Daten in der Datenquelle verwendet werden: die <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A>-Eigenschaft gibt die Daten aus der Datenquelle zurück, und die Eigenschaften <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> und <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> dienen zum Verwalten von Änderungen in der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="0096d-103">The <xref:System.Data.Common.DbDataAdapter> has four properties that are used to retrieve data from and update data to the data source: the <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> property returns data from the data source; and the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> , <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, and <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> properties are used to manage changes at the data source.</span></span> <span data-ttu-id="0096d-104">Die `SelectCommand`-Eigenschaft muss vor dem Aufrufen der `Fill`-Methode des `DataAdapter` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0096d-104">The `SelectCommand` property must be set before you call the `Fill` method of the `DataAdapter`.</span></span> <span data-ttu-id="0096d-105">Die Eigenschaft `InsertCommand`, `UpdateCommand` oder `DeleteCommand` (abhängig von der Art der Änderungen in der `Update`) muss vor dem Aufruf der `DataAdapter`-Methode des <xref:System.Data.DataTable> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0096d-105">The `InsertCommand`, `UpdateCommand`, or `DeleteCommand` properties must be set before the `Update` method of the `DataAdapter` is called, depending on what changes were made to the data in the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="0096d-106">Wenn beispielsweise Zeilen hinzugefügt wurden, muss vor dem Aufrufen von `InsertCommand` das `Update` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0096d-106">For example, if rows have been added, the `InsertCommand` must be set before you call `Update`.</span></span> <span data-ttu-id="0096d-107">Wenn `Update` eine eingefügte, aktualisierte oder gelöschte Zeile verarbeitet, verwendet der `DataAdapter` die entsprechende `Command`-Eigenschaft, um die Aktion zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0096d-107">When `Update` is processing an inserted, updated, or deleted row, the `DataAdapter` uses the respective `Command` property to process the action.</span></span> <span data-ttu-id="0096d-108">Aktuelle Informationen zur geänderten Zeile werden über die `Command`-Auflistung an das `Parameters`-Objekt übergeben.</span><span class="sxs-lookup"><span data-stu-id="0096d-108">Current information about the modified row is passed to the `Command` object through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="0096d-109">Wenn Sie eine Zeile in der Datenquelle aktualisieren, wird die Update-Anweisung aufgerufen, die einen eindeutigen Bezeichner verwendet, um die Zeile in der zu aktualisierenden Tabelle zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0096d-109">When you update a row at the data source, you call the UPDATE statement, which uses a unique identifier to identify the row in the table to be updated.</span></span> <span data-ttu-id="0096d-110">Der eindeutige Bezeichner ist im Allgemeinen der Wert eines Primärschlüsselfelds.</span><span class="sxs-lookup"><span data-stu-id="0096d-110">The unique identifier is typically the value of a primary key field.</span></span> <span data-ttu-id="0096d-111">Die UPDATE-Anweisung verwendet Parameter, die sowohl den eindeutigen Bezeichner als auch die Spalten und Werte enthalten, die aktualisiert werden sollen, wie in der folgenden Transact-SQL-Anweisung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0096d-111">The UPDATE statement uses parameters that contain both the unique identifier and the columns and values to be updated, as shown in the following Transact-SQL statement.</span></span>  
  
```sql
UPDATE Customers SET CompanyName = @CompanyName   
  WHERE CustomerID = @CustomerID  
```  
  
> [!NOTE]
> <span data-ttu-id="0096d-112">Die Syntax für Parameterplatzhalter ist abhängig von der jeweiligen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="0096d-112">The syntax for parameter placeholders depends on the data source.</span></span> <span data-ttu-id="0096d-113">Dieses Beispiel zeigt Platzhalter für eine SQL Server-Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="0096d-113">This example shows placeholders for a SQL Server data source.</span></span> <span data-ttu-id="0096d-114">Verwenden Sie Fragezeichenplatzhalter (?) für <xref:System.Data.OleDb>-Parameter und <xref:System.Data.Odbc>-Parameter.</span><span class="sxs-lookup"><span data-stu-id="0096d-114">Use question mark (?) placeholders for <xref:System.Data.OleDb> and <xref:System.Data.Odbc> parameters.</span></span>  
  
 <span data-ttu-id="0096d-115">In diesem Visual Basic Beispiel wird das `CompanyName` -Feld mit dem Wert `@CompanyName` des-Parameters für die Zeile aktualisiert `CustomerID` , in der dem Wert `@CustomerID` des-Parameters entspricht.</span><span class="sxs-lookup"><span data-stu-id="0096d-115">In this Visual Basic example, the `CompanyName` field is updated with the value of the `@CompanyName` parameter for the row where `CustomerID` equals the value of the `@CustomerID` parameter.</span></span> <span data-ttu-id="0096d-116">Die Parameter rufen Informationen mithilfe der <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> -Eigenschaft <xref:System.Data.SqlClient.SqlParameter> des-Objekts aus der geänderten Zeile ab.</span><span class="sxs-lookup"><span data-stu-id="0096d-116">The parameters retrieve information from the modified row using the <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> property of the <xref:System.Data.SqlClient.SqlParameter> object.</span></span> <span data-ttu-id="0096d-117">Im Folgenden finden Sie die Parameter für das vorherige Beispiel einer UPDATE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0096d-117">The following are the parameters for the previous sample UPDATE statement.</span></span> <span data-ttu-id="0096d-118">Der Code geht davon aus, dass die `adapter`-Variable für ein gültiges <xref:System.Data.SqlClient.SqlDataAdapter>-Objekt steht.</span><span class="sxs-lookup"><span data-stu-id="0096d-118">The code assumes that the variable `adapter` represents a valid <xref:System.Data.SqlClient.SqlDataAdapter> object.</span></span>  
  
```vb
adapter.Parameters.Add( _  
  "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
Dim parameter As SqlParameter = _  
  adapter.UpdateCommand.Parameters.Add("@CustomerID", _  
  SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
```  
  
 <span data-ttu-id="0096d-119">Die `Add`-Methode der `Parameters`-Auflistung nimmt den Namen des Parameters, den Datentyp, die Größe (wenn für den Typ zutreffend) und den Namen der <xref:System.Data.Common.DbParameter.SourceColumn%2A> aus der `DataTable` an.</span><span class="sxs-lookup"><span data-stu-id="0096d-119">The `Add` method of the `Parameters` collection takes the name of the parameter, the data type, the size (if applicable to the type), and the name of the <xref:System.Data.Common.DbParameter.SourceColumn%2A> from the `DataTable`.</span></span> <span data-ttu-id="0096d-120">Beachten Sie, dass der <xref:System.Data.Common.DbParameter.SourceVersion%2A>-Wert des `@CustomerID`-Parameters `Original` lautet.</span><span class="sxs-lookup"><span data-stu-id="0096d-120">Notice that the <xref:System.Data.Common.DbParameter.SourceVersion%2A> of the `@CustomerID` parameter is set to `Original`.</span></span> <span data-ttu-id="0096d-121">Dadurch wird sichergestellt, dass die vorhandene Zeile in der Datenquelle aktualisiert wird, wenn sich der Wert der ID-Spalte oder -Spalten in der geänderten <xref:System.Data.DataRow> geändert hat.</span><span class="sxs-lookup"><span data-stu-id="0096d-121">This guarantees that the existing row in the data source is updated if the value of the identifying column or columns has been changed in the modified <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="0096d-122">In diesem Fall stimmt der `Original`-Zeilenwert mit dem aktuellen Wert in der Datenquelle überein, und der `Current`-Zeilenwert enthält den aktualisierten Wert.</span><span class="sxs-lookup"><span data-stu-id="0096d-122">In that case, the `Original` row value would match the current value at the data source, and the `Current` row value would contain the updated value.</span></span> <span data-ttu-id="0096d-123">Die `SourceVersion` für den `@CompanyName`-Parameter ist nicht festgelegt, und es wird der Standardwert, nämlich der `Current`-Zeilenwert, verwendet.</span><span class="sxs-lookup"><span data-stu-id="0096d-123">The `SourceVersion` for the `@CompanyName` parameter is not set and uses the default, `Current` row value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0096d-124">Sowohl für die `Fill` `DataAdapter` -als`Get` auch die-Methode der-Methode wird der .NET Framework-Typ von dem Typ abgeleitet ,dervom.NETFrameworkDatenanbieterzurückgegebenwird.`DataReader`</span><span class="sxs-lookup"><span data-stu-id="0096d-124">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the .NET Framework type is inferred from the type returned from the .NET Framework data provider.</span></span> <span data-ttu-id="0096d-125">Die .NET Framework Typen und Accessormethoden für Microsoft SQL Server-, OLE DB-und ODBC-Datentypen werden unter [Datentyp Zuordnungen in ADO.net](data-type-mappings-in-ado-net.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0096d-125">The inferred .NET Framework types and accessor methods for Microsoft SQL Server, OLE DB, and ODBC data types are described in [Data Type Mappings in ADO.NET](data-type-mappings-in-ado-net.md).</span></span>  
  
## <a name="parametersourcecolumn-parametersourceversion"></a><span data-ttu-id="0096d-126">Parameter.SourceColumn, Parameter.SourceVersion</span><span class="sxs-lookup"><span data-stu-id="0096d-126">Parameter.SourceColumn, Parameter.SourceVersion</span></span>  
 <span data-ttu-id="0096d-127">Die `SourceColumn` und die `SourceVersion` können als Argumente an den `Parameter`-Konstruktor übergeben oder als Eigenschaften eines vorhandenen `Parameter` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0096d-127">The `SourceColumn` and `SourceVersion` may be passed as arguments to the `Parameter` constructor, or set as properties of an existing `Parameter`.</span></span> <span data-ttu-id="0096d-128">Die `SourceColumn` ist der Name der <xref:System.Data.DataColumn> aus der <xref:System.Data.DataRow>, aus der der Wert des `Parameter` abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0096d-128">The `SourceColumn` is the name of the <xref:System.Data.DataColumn> from the <xref:System.Data.DataRow> where the value of the `Parameter` will be retrieved.</span></span> <span data-ttu-id="0096d-129">Die `SourceVersion` gibt die `DataRow`-Version an, die der `DataAdapter` zum Abrufen des Werts verwendet.</span><span class="sxs-lookup"><span data-stu-id="0096d-129">The `SourceVersion` specifies the `DataRow` version that the `DataAdapter` uses to retrieve the value.</span></span>  
  
 <span data-ttu-id="0096d-130">Die folgende Tabelle zeigt die <xref:System.Data.DataRowVersion>-Enumerationswerte an, die für die Verwendung mit `SourceVersion` zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="0096d-130">The following table shows the <xref:System.Data.DataRowVersion> enumeration values available for use with `SourceVersion`.</span></span>  
  
|<span data-ttu-id="0096d-131">DataRowVersion-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0096d-131">DataRowVersion Enumeration</span></span>|<span data-ttu-id="0096d-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0096d-132">Description</span></span>|  
|--------------------------------|-----------------|  
|`Current`|<span data-ttu-id="0096d-133">Der Parameter verwendet den aktuellen Wert der Spalte.</span><span class="sxs-lookup"><span data-stu-id="0096d-133">The parameter uses the current value of the column.</span></span> <span data-ttu-id="0096d-134">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="0096d-134">This is the default.</span></span>|  
|`Default`|<span data-ttu-id="0096d-135">Der Parameter verwendet den `DefaultValue` der Spalte.</span><span class="sxs-lookup"><span data-stu-id="0096d-135">The parameter uses the `DefaultValue` of the column.</span></span>|  
|`Original`|<span data-ttu-id="0096d-136">Der Parameter verwendet den ursprünglichen Wert der Spalte.</span><span class="sxs-lookup"><span data-stu-id="0096d-136">The parameter uses the original value of the column.</span></span>|  
|`Proposed`|<span data-ttu-id="0096d-137">Der Parameter verwendet einen vorgeschlagenen Wert.</span><span class="sxs-lookup"><span data-stu-id="0096d-137">The parameter uses a proposed value.</span></span>|  
  
 <span data-ttu-id="0096d-138">Das `SqlClient`-Codebeispiel im nächsten Abschnitt definiert einen Parameter für einen <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, bei dem die `CustomerID`-Spalte als `SourceColumn` für die folgenden beiden Parameter verwendet wird: `@CustomerID` (`SET CustomerID = @CustomerID`) und `@OldCustomerID` (`WHERE CustomerID = @OldCustomerID`).</span><span class="sxs-lookup"><span data-stu-id="0096d-138">The `SqlClient` code example in the next section defines a parameter for an <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> in which the `CustomerID` column is used as a `SourceColumn` for two parameters: `@CustomerID` (`SET CustomerID = @CustomerID`), and `@OldCustomerID` (`WHERE CustomerID = @OldCustomerID`).</span></span> <span data-ttu-id="0096d-139">Der `@CustomerID` -Parameter wird verwendet, um die **CustomerID-** Spalte auf den aktuellen Wert `DataRow`in der zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0096d-139">The `@CustomerID` parameter is used to update the **CustomerID** column to the current value in the `DataRow`.</span></span> <span data-ttu-id="0096d-140">Folglich `CustomerID` wird der `SourceColumn` mit einer `SourceVersion` von `Current` verwendet.</span><span class="sxs-lookup"><span data-stu-id="0096d-140">As a result, the `CustomerID` `SourceColumn` with a `SourceVersion` of `Current` is used.</span></span> <span data-ttu-id="0096d-141">Der `@OldCustomerID` -Parameter wird verwendet, um die aktuelle Zeile in der Datenquelle zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0096d-141">The `@OldCustomerID` parameter is used to identify the current row in the data source.</span></span> <span data-ttu-id="0096d-142">Da sich der passende Spaltenwert in der `Original`-Version der Zeile befindet, wird die gleiche `SourceColumn` (`CustomerID`) mit einer `SourceVersion` von `Original` verwendet.</span><span class="sxs-lookup"><span data-stu-id="0096d-142">Because the matching column value is found in the `Original` version of the row, the same `SourceColumn` (`CustomerID`) with a `SourceVersion` of `Original` is used.</span></span>  
  
## <a name="working-with-sqlclient-parameters"></a><span data-ttu-id="0096d-143">Verwenden von "SqlClient"-Parametern</span><span class="sxs-lookup"><span data-stu-id="0096d-143">Working with SqlClient Parameters</span></span>  
 <span data-ttu-id="0096d-144">Im folgenden Beispiel wird gezeigt, wie Sie einen <xref:System.Data.SqlClient.SqlDataAdapter> erstellen und für die <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A><xref:System.Data.MissingSchemaAction.AddWithKey> festlegen können, um zusätzliche Schemainformationen aus der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0096d-144">The following example demonstrates how to create a <xref:System.Data.SqlClient.SqlDataAdapter> and set the <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A> to <xref:System.Data.MissingSchemaAction.AddWithKey> in order to retrieve additional schema information from the database.</span></span> <span data-ttu-id="0096d-145">Die Eigenschaften <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A> und <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> werden festgelegt, und die zugehörigen <xref:System.Data.SqlClient.SqlParameter>-Objekte werden der <xref:System.Data.SqlClient.SqlCommand.Parameters%2A>-Auflistung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0096d-145">The <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, and <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> properties set and their corresponding <xref:System.Data.SqlClient.SqlParameter> objects added to the <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection.</span></span> <span data-ttu-id="0096d-146">Die Methode gibt ein `SqlDataAdapter`-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="0096d-146">The method returns a `SqlDataAdapter` object.</span></span>  
  
 [!code-csharp[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/CS/source.cs#1)]
 [!code-vb[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/VB/source.vb#1)]  
  
## <a name="oledb-parameter-placeholders"></a><span data-ttu-id="0096d-147">"OleDb"-Parameterplatzhalter</span><span class="sxs-lookup"><span data-stu-id="0096d-147">OleDb Parameter Placeholders</span></span>  
 <span data-ttu-id="0096d-148">Für das <xref:System.Data.OleDb.OleDbDataAdapter>-Objekt und das <xref:System.Data.Odbc.OdbcDataAdapter>-Objekt müssen zum Identifizieren der Parameter Fragezeichenplatzhalter (?) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0096d-148">For the <xref:System.Data.OleDb.OleDbDataAdapter> and <xref:System.Data.Odbc.OdbcDataAdapter> objects, you must use question mark (?) placeholders to identify the parameters.</span></span>  
  
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
  
 <span data-ttu-id="0096d-149">Die parametrisierten Abfrageanweisungen definieren, welche Eingabe- und Ausgabeparameter erstellt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0096d-149">The parameterized query statements define which input and output parameters must be created.</span></span> <span data-ttu-id="0096d-150">Verwenden Sie zum Erstellen eines Parameters die `Parameters.Add`-Methode oder den `Parameter`-Konstruktor, um den Spaltennamen, den Datentyp und die Größe anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0096d-150">To create a parameter, use the `Parameters.Add` method or the `Parameter` constructor to specify the column name, data type, and size.</span></span> <span data-ttu-id="0096d-151">Für systeminterne Datentypen, wie `Integer`, muss die Größe nicht angegeben werden. Sie können auch die Standardgröße angeben.</span><span class="sxs-lookup"><span data-stu-id="0096d-151">For intrinsic data types, such as `Integer`, you do not have to include the size, or you can specify the default size.</span></span>  
  
 <span data-ttu-id="0096d-152">Das folgende Codebeispiel erstellt die Parameter für eine SQL-Anweisung und füllt dann ein `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="0096d-152">The following code example creates the parameters for a SQL statement and then fills a `DataSet`.</span></span>  
  
## <a name="oledb-example"></a><span data-ttu-id="0096d-153">OLE DB-Beispiel</span><span class="sxs-lookup"><span data-stu-id="0096d-153">OleDb Example</span></span>  
  
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
  
## <a name="odbc-parameters"></a><span data-ttu-id="0096d-154">ODBC-Parameter</span><span class="sxs-lookup"><span data-stu-id="0096d-154">Odbc Parameters</span></span>  
  
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
> <span data-ttu-id="0096d-155">Wenn für einen Parameter kein Parameter Name angegeben wird, erhält der Parameter den inkrementellen Standardnamen des Parameters*N* *,* beginnend mit "parameter1".</span><span class="sxs-lookup"><span data-stu-id="0096d-155">If a parameter name is not supplied for a parameter, the parameter is given an incremental default name of Parameter*N* *,* starting with "Parameter1".</span></span> <span data-ttu-id="0096d-156">Wenn Sie einen Parameternamen angeben, empfiehlt es sich, den Parameter*N* zu vermeiden, wenn Sie einen Parameternamen angeben, da der von Ihnen bereitgestellte Name möglicherweise `ParameterCollection`mit einem vorhandenen Standard Parameter Namen in in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="0096d-156">We recommend that you avoid the Parameter*N* naming convention when you supply a parameter name, because the name that you supply might conflict with an existing default parameter name in the `ParameterCollection`.</span></span> <span data-ttu-id="0096d-157">Wenn der angegebene Name bereits vorhanden ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0096d-157">If the supplied name already exists, an exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0096d-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0096d-158">See also</span></span>

- [<span data-ttu-id="0096d-159">DataAdapters und DataReaders</span><span class="sxs-lookup"><span data-stu-id="0096d-159">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="0096d-160">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="0096d-160">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="0096d-161">Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)</span><span class="sxs-lookup"><span data-stu-id="0096d-161">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="0096d-162">Ändern von Daten mit gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0096d-162">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)
- [<span data-ttu-id="0096d-163">Datentypzuordnungen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0096d-163">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="0096d-164">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0096d-164">ADO.NET Overview</span></span>](ado-net-overview.md)
