---
title: Große UDTs
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: 012bddc0b4c29a0b50abc3a0df5c3cd34dc4725a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452395"
---
# <a name="large-udts"></a><span data-ttu-id="1dcce-102">Große UDTs</span><span class="sxs-lookup"><span data-stu-id="1dcce-102">Large UDTs</span></span>
<span data-ttu-id="1dcce-103">Benutzerdefinierte Typen (UDTs) gestatten Entwicklern, das Skalartypsystem durch das Speichern von CLR-Objekten (Common Language Runtime) in einer SQL Server-Datenbank zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="1dcce-103">User-defined types (UDTs) allow a developer to extend the server's scalar type system by storing common language runtime (CLR) objects in a SQL Server database.</span></span> <span data-ttu-id="1dcce-104">UDTs können mehrere Elemente enthalten und Verhalten aufweisen, die sich von den herkömmlichen Aliasdatentypen unterscheiden, die aus einem einzigen SQL Server-Systemdatentyp bestehen.</span><span class="sxs-lookup"><span data-stu-id="1dcce-104">UDTs can contain multiple elements and can have behaviors, unlike the traditional alias data types, which consist of a single SQL Server system data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1dcce-105">Sie müssen .NET Framework 3.5 SP1 (oder höher) installieren, um die Vorteile der erweiterten SqlClient-Unterstützung für große UDTs nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="1dcce-105">You must install the .NET Framework 3.5 SP1 (or later) to take advantage of the enhanced SqlClient support for large UDTs.</span></span>  
  
 <span data-ttu-id="1dcce-106">Vorher waren UDTs auf eine Dateigröße von maximal 8 Kilobyte beschränkt.</span><span class="sxs-lookup"><span data-stu-id="1dcce-106">Previously, UDTs were restricted to a maximum size of 8 kilobytes.</span></span> <span data-ttu-id="1dcce-107">In SQL Server 2008 besteht diese Beschränkung für UDTs mit dem <xref:Microsoft.SqlServer.Server.Format.UserDefined>-Format nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="1dcce-107">In SQL Server 2008, this restriction has been removed for UDTs that have a format of <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span></span>  
  
 <span data-ttu-id="1dcce-108">Eine vollständige Dokumentation zu benutzerdefinierten Typen finden Sie in der SQL Server-Onlinedokumentation für die von Ihnen verwendete SQL Server-Version.</span><span class="sxs-lookup"><span data-stu-id="1dcce-108">For the complete documentation for user-defined types, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="1dcce-109">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="1dcce-109">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="1dcce-110">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="1dcce-110">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a><span data-ttu-id="1dcce-111">Abrufen von UDT-Schemas mit 'GetSchema'</span><span class="sxs-lookup"><span data-stu-id="1dcce-111">Retrieving UDT Schemas Using GetSchema</span></span>  
 <span data-ttu-id="1dcce-112">Die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>-Methode von <xref:System.Data.SqlClient.SqlConnection> gibt Informationen zum Datenbankschema in einer <xref:System.Data.DataTable> zurück.</span><span class="sxs-lookup"><span data-stu-id="1dcce-112">The <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of <xref:System.Data.SqlClient.SqlConnection> returns database schema information in a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="1dcce-113">Weitere Informationen finden Sie unter [SQL Server Schema](../sql-server-schema-collections.md)Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="1dcce-113">For more information, see [SQL Server Schema Collections](../sql-server-schema-collections.md).</span></span>  
  
### <a name="getschematable-column-values-for-udts"></a><span data-ttu-id="1dcce-114">'GetSchemaTable'-Spaltenwerte für UDTs</span><span class="sxs-lookup"><span data-stu-id="1dcce-114">GetSchemaTable Column Values for UDTs</span></span>  
 <span data-ttu-id="1dcce-115">Die <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>-Methode eines <xref:System.Data.SqlClient.SqlDataReader> gibt eine <xref:System.Data.DataTable> mit Beschreibungen der Spaltenmetadaten zurück.</span><span class="sxs-lookup"><span data-stu-id="1dcce-115">The <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> method of a <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.DataTable> that describes column metadata.</span></span> <span data-ttu-id="1dcce-116">In der folgenden Tabelle werden die Unterschiede bezüglich der Spaltenmetadaten für große UDTs zwischen SQL Server 2005 und SQL Server 2008 erläutert.</span><span class="sxs-lookup"><span data-stu-id="1dcce-116">The following table describes the differences in the column metadata for large UDTs between SQL Server 2005 and SQL Server 2008.</span></span>  
  
|<span data-ttu-id="1dcce-117">SqlDataReader-Spalte</span><span class="sxs-lookup"><span data-stu-id="1dcce-117">SqlDataReader column</span></span>|<span data-ttu-id="1dcce-118">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="1dcce-118">SQL Server 2005</span></span>|<span data-ttu-id="1dcce-119">SQL Server 2008 und höher</span><span class="sxs-lookup"><span data-stu-id="1dcce-119">SQL Server 2008 and later</span></span>|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|<span data-ttu-id="1dcce-120">Variiert</span><span class="sxs-lookup"><span data-stu-id="1dcce-120">Varies</span></span>|<span data-ttu-id="1dcce-121">Variiert</span><span class="sxs-lookup"><span data-stu-id="1dcce-121">Varies</span></span>|  
|`NumericPrecision`|<span data-ttu-id="1dcce-122">255</span><span class="sxs-lookup"><span data-stu-id="1dcce-122">255</span></span>|<span data-ttu-id="1dcce-123">255</span><span class="sxs-lookup"><span data-stu-id="1dcce-123">255</span></span>|  
|`NumericScale`|<span data-ttu-id="1dcce-124">255</span><span class="sxs-lookup"><span data-stu-id="1dcce-124">255</span></span>|<span data-ttu-id="1dcce-125">255</span><span class="sxs-lookup"><span data-stu-id="1dcce-125">255</span></span>|  
|`DataType`|`Byte[]`|<span data-ttu-id="1dcce-126">UDT-Instanz</span><span class="sxs-lookup"><span data-stu-id="1dcce-126">UDT instance</span></span>|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|<span data-ttu-id="1dcce-127">UDT-Instanz</span><span class="sxs-lookup"><span data-stu-id="1dcce-127">UDT instance</span></span>|  
|`ProviderType`|<span data-ttu-id="1dcce-128">21 (`SqlDbType.VarBinary`)</span><span class="sxs-lookup"><span data-stu-id="1dcce-128">21 (`SqlDbType.VarBinary`)</span></span>|<span data-ttu-id="1dcce-129">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="1dcce-129">29 (`SqlDbType.Udt`)</span></span>|  
|`NonVersionedProviderType`|<span data-ttu-id="1dcce-130">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="1dcce-130">29 (`SqlDbType.Udt`)</span></span>|<span data-ttu-id="1dcce-131">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="1dcce-131">29 (`SqlDbType.Udt`)</span></span>|  
|`DataTypeName`|`SqlDbType.VarBinary`|<span data-ttu-id="1dcce-132">Der dreiteilige, als *Database.SchemaName.TypeName* angegebene Name.</span><span class="sxs-lookup"><span data-stu-id="1dcce-132">The three part name specified as *Database.SchemaName.TypeName*.</span></span>|  
|`IsLong`|<span data-ttu-id="1dcce-133">Variiert</span><span class="sxs-lookup"><span data-stu-id="1dcce-133">Varies</span></span>|<span data-ttu-id="1dcce-134">Variiert</span><span class="sxs-lookup"><span data-stu-id="1dcce-134">Varies</span></span>|  
  
## <a name="sqldatareader-considerations"></a><span data-ttu-id="1dcce-135">Überlegungen zu "SqlDataReader"</span><span class="sxs-lookup"><span data-stu-id="1dcce-135">SqlDataReader Considerations</span></span>  
 <span data-ttu-id="1dcce-136">Der <xref:System.Data.SqlClient.SqlDataReader> wurde beginnend in SQL Server 2008 erweitert und unterstützt nun das Abrufen großer UDT-Werte.</span><span class="sxs-lookup"><span data-stu-id="1dcce-136">The <xref:System.Data.SqlClient.SqlDataReader> has been extended beginning in SQL Server 2008 to support retrieving large UDT values.</span></span> <span data-ttu-id="1dcce-137">Die Verarbeitung großer UDT-Werte durch einen <xref:System.Data.SqlClient.SqlDataReader> ist von der verwendeten SQL Server-Version sowie der in der Verbindungszeichenfolge angegebenen `Type System Version` abhängig.</span><span class="sxs-lookup"><span data-stu-id="1dcce-137">How large UDT values are processed by a <xref:System.Data.SqlClient.SqlDataReader> depends on the version of SQL Server you are using, as well as on the `Type System Version` specified in the connection string.</span></span> <span data-ttu-id="1dcce-138">Weitere Informationen finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="1dcce-138">For more information, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="1dcce-139">Die folgenden <xref:System.Data.SqlClient.SqlDataReader>-Methoden geben anstelle eines UDTs <xref:System.Data.SqlTypes.SqlBinary> zurück, wenn `Type System Version` auf SQL Server 2005 festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="1dcce-139">The following methods of <xref:System.Data.SqlClient.SqlDataReader> will return a <xref:System.Data.SqlTypes.SqlBinary> instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 <span data-ttu-id="1dcce-140">Die folgenden Methoden geben anstelle eines UDTs ein `Byte[]`-Array zurück, wenn `Type System Version` auf SQL Server 2005 festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="1dcce-140">The following methods will return an array of `Byte[]` instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 <span data-ttu-id="1dcce-141">Beachten Sie, dass für die aktuelle Version von ADO.NET keine Konvertierungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="1dcce-141">Note that no conversions are made for the current version of ADO.NET.</span></span>  
  
## <a name="specifying-sqlparameters"></a><span data-ttu-id="1dcce-142">Angeben von 'SqlParameters'</span><span class="sxs-lookup"><span data-stu-id="1dcce-142">Specifying SqlParameters</span></span>  
 <span data-ttu-id="1dcce-143">Die folgenden <xref:System.Data.SqlClient.SqlParameter>-Eigenschaften wurden für die Verwendung mit großen UDTs erweitert.</span><span class="sxs-lookup"><span data-stu-id="1dcce-143">The following <xref:System.Data.SqlClient.SqlParameter> properties have been extended to work with large UDTs.</span></span>  
  
|<span data-ttu-id="1dcce-144">SqlParameter-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1dcce-144">SqlParameter Property</span></span>|<span data-ttu-id="1dcce-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1dcce-145">Description</span></span>|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="1dcce-146">Ruft ein Objekt ab, das den Wert des Parameters darstellt, oder legt dieses fest.</span><span class="sxs-lookup"><span data-stu-id="1dcce-146">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="1dcce-147">Der Standardwert ist null.</span><span class="sxs-lookup"><span data-stu-id="1dcce-147">The default is null.</span></span> <span data-ttu-id="1dcce-148">Die Eigenschaft kann `SqlBinary`, `Byte[]` oder ein verwaltetes Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="1dcce-148">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="1dcce-149">Ruft ein Objekt ab, das den Wert des Parameters darstellt, oder legt dieses fest.</span><span class="sxs-lookup"><span data-stu-id="1dcce-149">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="1dcce-150">Der Standardwert ist null.</span><span class="sxs-lookup"><span data-stu-id="1dcce-150">The default is null.</span></span> <span data-ttu-id="1dcce-151">Die Eigenschaft kann `SqlBinary`, `Byte[]` oder ein verwaltetes Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="1dcce-151">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="1dcce-152">Ruft die Größe des aufzulösenden Parameterwerts ab oder legt diese Größe fest.</span><span class="sxs-lookup"><span data-stu-id="1dcce-152">Gets or sets the size of the parameter value to resolve.</span></span> <span data-ttu-id="1dcce-153">Der Standardwert ist 0.</span><span class="sxs-lookup"><span data-stu-id="1dcce-153">The default value is 0.</span></span> <span data-ttu-id="1dcce-154">Die Eigenschaft kann eine ganze Zahl sein, die für die Größe des Parameterwerts steht.</span><span class="sxs-lookup"><span data-stu-id="1dcce-154">The property can be an integer that represents the size of the parameter value.</span></span> <span data-ttu-id="1dcce-155">Bei großen UDTs kann es sich um die tatsächliche Größe des UDT handeln, bei unbekannter Größe lautet der Wert -1.</span><span class="sxs-lookup"><span data-stu-id="1dcce-155">For large UDTs, it can be the actual size of the UDT, or -1 for unknown.</span></span>|  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="1dcce-156">Abrufen eines Datenbeispiels</span><span class="sxs-lookup"><span data-stu-id="1dcce-156">Retrieving Data Example</span></span>  
 <span data-ttu-id="1dcce-157">Im folgenden Codefragment wird gezeigt, wie Daten großer UDTs abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="1dcce-157">The following code fragment demonstrates how to retrieve large UDT data.</span></span> <span data-ttu-id="1dcce-158">Die `connectionString`-Variable setzt eine gültige Verbindung mit einer SQL Server-Datenbank voraus. Die `commandString`-Variable setzt eine gültige SELECT-Anweisung voraus, in der die Primärschlüsselspalte zuerst aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="1dcce-158">The `connectionString` variable assumes a valid connection to a SQL Server database and the `commandString` variable assumes a valid SELECT statement with the primary key column listed first.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1dcce-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1dcce-159">See also</span></span>

- [<span data-ttu-id="1dcce-160">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="1dcce-160">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="1dcce-161">Abrufen von Datenbankschemainformationen</span><span class="sxs-lookup"><span data-stu-id="1dcce-161">Retrieving Database Schema Information</span></span>](../retrieving-database-schema-information.md)
- [<span data-ttu-id="1dcce-162">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="1dcce-162">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="1dcce-163">SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1dcce-163">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="1dcce-164">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1dcce-164">ADO.NET Overview</span></span>](../ado-net-overview.md)
