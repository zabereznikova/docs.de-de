---
title: Große UDTs
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: 015ce896e49b3a6a932c36db867271b4ac4c64c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59303478"
---
# <a name="large-udts"></a><span data-ttu-id="72594-102">Große UDTs</span><span class="sxs-lookup"><span data-stu-id="72594-102">Large UDTs</span></span>
<span data-ttu-id="72594-103">Mithilfe benutzerdefinierter Typen (User-Defined Types, UDTs) können Entwickler das Skalartypsystem des Servers erweitern, indem sie CLR (Common Language Runtime)-Objekte in einer SQL Server-Datenbank speichern.</span><span class="sxs-lookup"><span data-stu-id="72594-103">User-defined types (UDTs) allow a developer to extend the server's scalar type system by storing common language runtime (CLR) objects in a SQL Server database.</span></span> <span data-ttu-id="72594-104">UDTs können mehrere Elemente enthalten und Verhaltensweisen aufweisen, wodurch sie sich von den herkömmlichen Aliasdatentypen unterscheiden, die nur aus einem SQL Server-Systemdatentyp bestehen.</span><span class="sxs-lookup"><span data-stu-id="72594-104">UDTs can contain multiple elements and can have behaviors, unlike the traditional alias data types, which consist of a single SQL Server system data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72594-105">Sie müssen .NET Framework 3.5 SP1 (oder höher) installieren, um die Vorteile der erweiterten SqlClient-Unterstützung für große UDTs nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="72594-105">You must install the .NET Framework 3.5 SP1 (or later) to take advantage of the enhanced SqlClient support for large UDTs.</span></span>  
  
 <span data-ttu-id="72594-106">Bisher waren UDTs auf eine maximale Größe von 8 Kilobytes beschränkt.</span><span class="sxs-lookup"><span data-stu-id="72594-106">Previously, UDTs were restricted to a maximum size of 8 kilobytes.</span></span> <span data-ttu-id="72594-107">In SQL Server 2008 besteht diese Beschränkung für UDTs mit dem <xref:Microsoft.SqlServer.Server.Format.UserDefined>-Format nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="72594-107">In SQL Server 2008, this restriction has been removed for UDTs that have a format of <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span></span>  
  
 <span data-ttu-id="72594-108">Eine vollständige Dokumentation zu benutzerdefinierten Typen finden Sie in der SQL Server-Onlinedokumentation für die von Ihnen verwendete SQL Server-Version.</span><span class="sxs-lookup"><span data-stu-id="72594-108">For the complete documentation for user-defined types, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="72594-109">**SQL Server Books Online (SQL Server-Onlinedokumentation)**</span><span class="sxs-lookup"><span data-stu-id="72594-109">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="72594-110">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="72594-110">CLR User-Defined Types</span></span>](https://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a><span data-ttu-id="72594-111">Abrufen von UDT-Schemas mit 'GetSchema'</span><span class="sxs-lookup"><span data-stu-id="72594-111">Retrieving UDT Schemas Using GetSchema</span></span>  
 <span data-ttu-id="72594-112">Die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>-Methode von <xref:System.Data.SqlClient.SqlConnection> gibt Informationen zum Datenbankschema in einer <xref:System.Data.DataTable> zurück.</span><span class="sxs-lookup"><span data-stu-id="72594-112">The <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of <xref:System.Data.SqlClient.SqlConnection> returns database schema information in a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="72594-113">Weitere Informationen finden Sie unter [SQL Server-Schemaauflistungen](../../../../../docs/framework/data/adonet/sql-server-schema-collections.md).</span><span class="sxs-lookup"><span data-stu-id="72594-113">For more information, see [SQL Server Schema Collections](../../../../../docs/framework/data/adonet/sql-server-schema-collections.md).</span></span>  
  
### <a name="getschematable-column-values-for-udts"></a><span data-ttu-id="72594-114">'GetSchemaTable'-Spaltenwerte für UDTs</span><span class="sxs-lookup"><span data-stu-id="72594-114">GetSchemaTable Column Values for UDTs</span></span>  
 <span data-ttu-id="72594-115">Die <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>-Methode eines <xref:System.Data.SqlClient.SqlDataReader> gibt eine <xref:System.Data.DataTable> mit Beschreibungen der Spaltenmetadaten zurück.</span><span class="sxs-lookup"><span data-stu-id="72594-115">The <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> method of a <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.DataTable> that describes column metadata.</span></span> <span data-ttu-id="72594-116">In der folgenden Tabelle werden die Unterschiede bezüglich der Spaltenmetadaten für große UDTs zwischen SQL Server 2005 und SQL Server 2008 erläutert.</span><span class="sxs-lookup"><span data-stu-id="72594-116">The following table describes the differences in the column metadata for large UDTs between SQL Server 2005 and SQL Server 2008.</span></span>  
  
|<span data-ttu-id="72594-117">SqlDataReader-Spalte</span><span class="sxs-lookup"><span data-stu-id="72594-117">SqlDataReader column</span></span>|<span data-ttu-id="72594-118">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="72594-118">SQL Server 2005</span></span>|<span data-ttu-id="72594-119">SQL Server 2008 und höher</span><span class="sxs-lookup"><span data-stu-id="72594-119">SQL Server 2008 and later</span></span>|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|<span data-ttu-id="72594-120">Unterschiedlich</span><span class="sxs-lookup"><span data-stu-id="72594-120">Varies</span></span>|<span data-ttu-id="72594-121">Unterschiedlich</span><span class="sxs-lookup"><span data-stu-id="72594-121">Varies</span></span>|  
|`NumericPrecision`|<span data-ttu-id="72594-122">255</span><span class="sxs-lookup"><span data-stu-id="72594-122">255</span></span>|<span data-ttu-id="72594-123">255</span><span class="sxs-lookup"><span data-stu-id="72594-123">255</span></span>|  
|`NumericScale`|<span data-ttu-id="72594-124">255</span><span class="sxs-lookup"><span data-stu-id="72594-124">255</span></span>|<span data-ttu-id="72594-125">255</span><span class="sxs-lookup"><span data-stu-id="72594-125">255</span></span>|  
|`DataType`|`Byte[]`|<span data-ttu-id="72594-126">UDT-Instanz</span><span class="sxs-lookup"><span data-stu-id="72594-126">UDT instance</span></span>|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|<span data-ttu-id="72594-127">UDT-Instanz</span><span class="sxs-lookup"><span data-stu-id="72594-127">UDT instance</span></span>|  
|`ProviderType`|<span data-ttu-id="72594-128">21 (`SqlDbType.VarBinary`)</span><span class="sxs-lookup"><span data-stu-id="72594-128">21 (`SqlDbType.VarBinary`)</span></span>|<span data-ttu-id="72594-129">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="72594-129">29 (`SqlDbType.Udt`)</span></span>|  
|`NonVersionedProviderType`|<span data-ttu-id="72594-130">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="72594-130">29 (`SqlDbType.Udt`)</span></span>|<span data-ttu-id="72594-131">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="72594-131">29 (`SqlDbType.Udt`)</span></span>|  
|`DataTypeName`|`SqlDbType.VarBinary`|<span data-ttu-id="72594-132">Der dreiteilige Name als *Database.SchemaName.TypeName*.</span><span class="sxs-lookup"><span data-stu-id="72594-132">The three part name specified as *Database.SchemaName.TypeName*.</span></span>|  
|`IsLong`|<span data-ttu-id="72594-133">Unterschiedlich</span><span class="sxs-lookup"><span data-stu-id="72594-133">Varies</span></span>|<span data-ttu-id="72594-134">Unterschiedlich</span><span class="sxs-lookup"><span data-stu-id="72594-134">Varies</span></span>|  
  
## <a name="sqldatareader-considerations"></a><span data-ttu-id="72594-135">Überlegungen zu "SqlDataReader"</span><span class="sxs-lookup"><span data-stu-id="72594-135">SqlDataReader Considerations</span></span>  
 <span data-ttu-id="72594-136"><xref:System.Data.SqlClient.SqlDataReader> wurde ab SQL Server 2008 erweitert und unterstützt nun das Abrufen großer UDT-Werte.</span><span class="sxs-lookup"><span data-stu-id="72594-136">The <xref:System.Data.SqlClient.SqlDataReader> has been extended beginning in SQL Server 2008 to support retrieving large UDT values.</span></span> <span data-ttu-id="72594-137">Die Verarbeitung großer UDT-Werte durch einen <xref:System.Data.SqlClient.SqlDataReader> ist von der verwendeten SQL Server-Version sowie der in der Verbindungszeichenfolge angegebenen `Type System Version` abhängig.</span><span class="sxs-lookup"><span data-stu-id="72594-137">How large UDT values are processed by a <xref:System.Data.SqlClient.SqlDataReader> depends on the version of SQL Server you are using, as well as on the `Type System Version` specified in the connection string.</span></span> <span data-ttu-id="72594-138">Weitere Informationen finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="72594-138">For more information, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="72594-139">Die folgenden <xref:System.Data.SqlClient.SqlDataReader>-Methoden geben anstelle eines UDTs <xref:System.Data.SqlTypes.SqlBinary> zurück, wenn `Type System Version` auf SQL Server 2005 festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="72594-139">The following methods of <xref:System.Data.SqlClient.SqlDataReader> will return a <xref:System.Data.SqlTypes.SqlBinary> instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 <span data-ttu-id="72594-140">Die folgenden Methoden geben anstelle eines UDTs ein `Byte[]`-Array zurück, wenn `Type System Version` auf SQL Server 2005 festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="72594-140">The following methods will return an array of `Byte[]` instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 <span data-ttu-id="72594-141">Beachten Sie, dass für die aktuelle Version von ADO.NET keine Konvertierungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="72594-141">Note that no conversions are made for the current version of ADO.NET.</span></span>  
  
## <a name="specifying-sqlparameters"></a><span data-ttu-id="72594-142">Angeben von 'SqlParameters'</span><span class="sxs-lookup"><span data-stu-id="72594-142">Specifying SqlParameters</span></span>  
 <span data-ttu-id="72594-143">Die folgenden <xref:System.Data.SqlClient.SqlParameter>-Eigenschaften wurden für die Verwendung mit großen UDTs erweitert.</span><span class="sxs-lookup"><span data-stu-id="72594-143">The following <xref:System.Data.SqlClient.SqlParameter> properties have been extended to work with large UDTs.</span></span>  
  
|<span data-ttu-id="72594-144">SqlParameter-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="72594-144">SqlParameter Property</span></span>|<span data-ttu-id="72594-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72594-145">Description</span></span>|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="72594-146">Ruft ein Objekt ab, das den Wert des Parameters darstellt, oder legt dieses fest.</span><span class="sxs-lookup"><span data-stu-id="72594-146">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="72594-147">Der Standardwert ist NULL.</span><span class="sxs-lookup"><span data-stu-id="72594-147">The default is null.</span></span> <span data-ttu-id="72594-148">Die Eigenschaft kann `SqlBinary`, `Byte[]` oder ein verwaltetes Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="72594-148">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="72594-149">Ruft ein Objekt ab, das den Wert des Parameters darstellt, oder legt dieses fest.</span><span class="sxs-lookup"><span data-stu-id="72594-149">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="72594-150">Der Standardwert ist NULL.</span><span class="sxs-lookup"><span data-stu-id="72594-150">The default is null.</span></span> <span data-ttu-id="72594-151">Die Eigenschaft kann `SqlBinary`, `Byte[]` oder ein verwaltetes Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="72594-151">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="72594-152">Ruft die Größe des aufzulösenden Parameterwerts ab oder legt diese Größe fest.</span><span class="sxs-lookup"><span data-stu-id="72594-152">Gets or sets the size of the parameter value to resolve.</span></span> <span data-ttu-id="72594-153">Der Standardwert ist 0.</span><span class="sxs-lookup"><span data-stu-id="72594-153">The default value is 0.</span></span> <span data-ttu-id="72594-154">Die Eigenschaft kann eine ganze Zahl sein, die für die Größe des Parameterwerts steht.</span><span class="sxs-lookup"><span data-stu-id="72594-154">The property can be an integer that represents the size of the parameter value.</span></span> <span data-ttu-id="72594-155">Bei großen UDTs kann es sich um die tatsächliche Größe des UDT handeln. Ist die Größe unbekannt, lautet der Wert "-1".</span><span class="sxs-lookup"><span data-stu-id="72594-155">For large UDTs, it can be the actual size of the UDT, or -1 for unknown.</span></span>|  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="72594-156">Abrufen eines Datenbeispiels</span><span class="sxs-lookup"><span data-stu-id="72594-156">Retrieving Data Example</span></span>  
 <span data-ttu-id="72594-157">Im folgenden Codefragment wird gezeigt, wie Daten großer UDTs abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="72594-157">The following code fragment demonstrates how to retrieve large UDT data.</span></span> <span data-ttu-id="72594-158">Die `connectionString`-Variable setzt eine gültige Verbindung mit einer SQL Server-Datenbank voraus. Die `commandString`-Variable setzt eine gültige SELECT-Anweisung voraus, in der die Primärschlüsselspalte zuerst aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="72594-158">The `connectionString` variable assumes a valid connection to a SQL Server database and the `commandString` variable assumes a valid SELECT statement with the primary key column listed first.</span></span>  
  
```csharp  
using (SqlConnection connection = new SqlConnection(   
    connectionString, commandString))  
{  
  connection.Open();  
  SqlCommand command = new SqlCommand(commandString);  
  SqlDataReader reader = command.ExecuteReader();  
  while (reader.Read())  
  {  
    // Retrieve the value of the Primary Key column.  
    int id = reader.GetInt32(0);  
  
    // Retrieve the value of the UDT.  
    LargeUDT udt = (LargeUDT)reader[1];  
  
    // You can also use GetSqlValue and GetValue.  
    // LargeUDT udt = (LargeUDT)reader.GetSqlValue(1);  
    // LargeUDT udt = (LargeUDT)reader.GetValue(1);  
  
    Console.WriteLine(  
     "ID={0} LargeUDT={1}", id, udt);  
  }  
reader.close  
}  
```  
  
```vb  
Using connection As New SqlConnection( _  
    connectionString, commandString)  
    connection.Open()  
    Dim command As New SqlCommand(commandString, connection)  
    Dim reader As SqlDataReader  
    reader = command.ExecuteReader  
  
    While reader.Read()  
      ' Retrieve the value of the Primary Key column.  
      Dim id As Int32 = reader.GetInt32(0)  
  
      ' Retrieve the value of the UDT.  
      Dim udt As LargeUDT = CType(reader(1), LargeUDT)  
  
     ' You can also use GetSqlValue and GetValue.  
     ' Dim udt As LargeUDT = CType(reader.GetSqlValue(1), LargeUDT)  
     ' Dim udt As LargeUDT = CType(reader.GetValue(1), LargeUDT)  
  
      ' Print values.  
      Console.WriteLine("ID={0} LargeUDT={1}", id, udt)  
    End While  
    reader.Close()  
End Using  
```  
  
## <a name="see-also"></a><span data-ttu-id="72594-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72594-159">See also</span></span>

- [<span data-ttu-id="72594-160">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="72594-160">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="72594-161">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="72594-161">Retrieving Database Schema Information</span></span>](../../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="72594-162">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="72594-162">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [<span data-ttu-id="72594-163">SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)</span><span class="sxs-lookup"><span data-stu-id="72594-163">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="72594-164">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="72594-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
