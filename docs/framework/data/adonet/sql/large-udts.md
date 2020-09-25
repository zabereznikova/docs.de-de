---
title: Große UDTs
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: 032093244f51893cd3b0cf50ad81c79413aaa32e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194543"
---
# <a name="large-udts"></a>Große UDTs

Benutzerdefinierte Typen (UDTs) gestatten Entwicklern, das Skalartypsystem durch das Speichern von CLR-Objekten (Common Language Runtime) in einer SQL Server-Datenbank zu erweitern. UDTs können mehrere Elemente enthalten und Verhalten aufweisen, die sich von den herkömmlichen Aliasdatentypen unterscheiden, die aus einem einzigen SQL Server-Systemdatentyp bestehen.  
  
> [!NOTE]
> Sie müssen .NET Framework 3.5 SP1 (oder höher) installieren, um die Vorteile der erweiterten SqlClient-Unterstützung für große UDTs nutzen zu können.  
  
 Vorher waren UDTs auf eine Dateigröße von maximal 8 Kilobyte beschränkt. In SQL Server 2008 besteht diese Beschränkung für UDTs mit dem <xref:Microsoft.SqlServer.Server.Format.UserDefined>-Format nicht mehr.  
  
 Eine vollständige Dokumentation zu benutzerdefinierten Typen finden Sie in der SQL Server-Onlinedokumentation für die von Ihnen verwendete SQL Server-Version.  
  
 **SQL Server-Dokumentation**  
  
1. [Benutzerdefinierte CLR-Typen](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a>Abrufen von UDT-Schemas mit 'GetSchema'  

 Die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>-Methode von <xref:System.Data.SqlClient.SqlConnection> gibt in einer <xref:System.Data.DataTable>Informationen zum Datenbankschema zurück. Weitere Informationen finden Sie unter [SQL Server Schema](../sql-server-schema-collections.md)Auflistungen.  
  
### <a name="getschematable-column-values-for-udts"></a>'GetSchemaTable'-Spaltenwerte für UDTs  

 Die <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>-Methode von <xref:System.Data.SqlClient.SqlDataReader> gibt eine <xref:System.Data.DataTable> zurück, die Spaltenmetadaten beschreibt. In der folgenden Tabelle werden die Unterschiede bei SQL Server 2005 und SQL Server 2008 bei den Spaltenmetadaten für große UDTs beschrieben.  
  
|Spalte SqlDataReader|SQL Server 2005|SQL Server 2008 und höher|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|Varies|Varies|  
|`NumericPrecision`|255|255|  
|`NumericScale`|255|255|  
|`DataType`|`Byte[]`|UDT-Instanz|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|UDT-Instanz|  
|`ProviderType`|21 (`SqlDbType.VarBinary`)|29 (`SqlDbType.Udt`)|  
|`NonVersionedProviderType`|29 (`SqlDbType.Udt`)|29 (`SqlDbType.Udt`)|  
|`DataTypeName`|`SqlDbType.VarBinary`|Der dreiteilige, als *Database.SchemaName.TypeName* angegebene Name.|  
|`IsLong`|Varies|Varies|  
  
## <a name="sqldatareader-considerations"></a>Überlegungen zu "SqlDataReader"  

 Der <xref:System.Data.SqlClient.SqlDataReader> wurde beginnend in SQL Server 2008 erweitert und unterstützt nun das Abrufen großer UDT-Werte. Wie große UDT-Werte von <xref:System.Data.SqlClient.SqlDataReader> verarbeitet werden, hängt von der verwendeten SQL Server-Version sowie von der in der Verbindungszeichenfolge angegebenen `Type System Version` ab. Weitere Informationen finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 Die folgenden Methoden von <xref:System.Data.SqlClient.SqlDataReader> geben <xref:System.Data.SqlTypes.SqlBinary> anstelle eines UDT zurück, wenn `Type System Version` auf SQL Server 2005 festgelegt ist:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 Die folgenden Methoden geben eine Array von `Byte[]` anstelle eines UDT zurück, wenn `Type System Version` auf SQL Server 2005 festgelegt ist:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 Beachten Sie, dass für die aktuelle Version von ADO.NET keine Konvertierungen erfolgen.  
  
## <a name="specifying-sqlparameters"></a>Angeben von SqlParameters  

 Die folgenden <xref:System.Data.SqlClient.SqlParameter>-Eigenschaften wurden für das Arbeiten mit großen UDTs erweitert.  
  
|SqlParameter-Eigenschaft|Beschreibung|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Ruft ein Objekt ab oder legt es fest, das den Wert des Parameters darstellt. Der Standardwert ist NULL. Die Eigenschaft kann `SqlBinary`, `Byte[]` oder ein verwaltetes Objekt sein.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Ruft ein Objekt ab oder legt es fest, das den Wert des Parameters darstellt. Der Standardwert ist NULL. Die Eigenschaft kann `SqlBinary`, `Byte[]` oder ein verwaltetes Objekt sein.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Ruft die Größe des aufzulösenden Parameterwerts ab oder legt sie fest. Der Standardwert ist 0. Die Eigenschaft kann eine ganze Zahl sein, die die Größe des Parameterwerts darstellt. Bei großen UDTs kann es sich um die tatsächliche Größe des UDT handeln, bei unbekannter Größe lautet der Wert -1.|  
  
## <a name="retrieving-data-example"></a>Abrufen eines Datenbeispiels  

 Das folgende Codefragment zeigt, wie große UDT-Daten abgerufen werden können. Die Variable `connectionString` setzt eine gültige Verbindung mit einer SQL Server-Datenbank voraus. Die Variable `commandString` setzt eine gültige SELECT-Anweisung mit an erster Stelle aufgeführter Primärschlüsselspalte voraus.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Konfigurieren von Parametern und Parameterdatentypen](../configuring-parameters-and-parameter-data-types.md)
- [Abrufen von Datenbankschemainformationen](../retrieving-database-schema-information.md)
- [SQL Server-Datentypzuordnungen](../sql-server-data-type-mappings.md)
- [SQL Server von Binärdaten und Daten mit umfangreichen Werten](sql-server-binary-and-large-value-data.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
