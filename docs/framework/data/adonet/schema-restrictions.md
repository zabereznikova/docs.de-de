---
title: Schemaeinschränkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: c0a3cafef45341cd95fa0a4f65c818129e120e44
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147823"
---
# <a name="schema-restrictions"></a>Schemaeinschränkungen

Der zweite optionale Parameter der **GetSchema** -Methode sind die Einschränkungen, die verwendet werden, um die Menge der zurückgegebenen Schema Informationen einzuschränken, und Sie werden als Zeichen folgen Array an die **GetSchema** -Methode übergeben. Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.  
  
 In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework-Datenanbieters für SQL Server unterstützt werden. Zusätzliche Einschränkungen für SQL Server-Schemaauflistungen werden am Ende dieses Themas aufgeführt.  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1|  
|Besitzer|@Owner|TABLE_SCHEMA|2|  
|Tabelle|@Name|table_name|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
## <a name="specifying-restriction-values"></a>Angeben der Einschränkungswerte  

 Wenn Sie eine der Einschränkungen der Tables-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt. Um beispielsweise die von der **GetSchema** -Methode zurückgegebenen Tabellen nur auf die Tabellen im "Sales"-Schema zu beschränken, legen Sie das zweite Element des Arrays auf "Sales" fest, bevor Sie es an die **GetSchema** -Methode übergeben.  
  
> [!NOTE]
> Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`-Spalte. Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert. Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL-Injection-Angriffs beim Angeben der Einschränkungswerte zu minimieren.  
  
> [!NOTE]
> Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird. Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein. Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL (uneingeschränkt) sind.  
  
 Sie können einen .NET Framework verwalteten Anbieter Abfragen, um die Liste der unterstützten Einschränkungen zu ermitteln, indem Sie die **GetSchema** -Methode mit dem Namen der Einschränkungs Schema Auflistung aufrufen. Dies ist "Einschränkungen". Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.  
  
### <a name="example"></a>Beispiel  

 In den folgenden Beispielen wird veranschaulicht, wie die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> -Methode der .NET Framework Datenanbieter für die SQL Server- <xref:System.Data.SqlClient.SqlConnection> Klasse zum Abrufen von Schema Informationen zu allen in der **AdventureWorks** -Beispieldatenbank enthaltenen Tabellen und zum Einschränken der zurückgegebenen Informationen auf die Tabellen im "Sales"-Schema verwendet wird:  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a>SQL Server-Schemabeschränkungen  

 In den folgenden Tabellen sind die Beschränkungen für SQL Server-Schemaauflistungen aufgeführt.  
  
### <a name="users"></a>Benutzer  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|User_Name|@Name|name|1|  
  
### <a name="databases"></a>Datenbanken  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Name|@Name|Name|1|  
  
### <a name="tables"></a>Tabellen  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1|  
|Besitzer|@Owner|TABLE_SCHEMA|2|  
|Tabelle|@Name|table_name|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
### <a name="columns"></a>Spalten  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1|  
|Besitzer|@Owner|TABLE_SCHEMA|2|  
|Tabelle|@Table|table_name|3|  
|Column|@Column|COLUMN_NAME|4|  
  
### <a name="structuredtypemembers"></a>StructuredTypeMembers  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1|  
|Besitzer|@Owner|TABLE_SCHEMA|2|  
|Tabelle|@Table|table_name|3|  
|Column|@Column|COLUMN_NAME|4|  
  
### <a name="views"></a>Sichten  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1|  
|Besitzer|@Owner|TABLE_SCHEMA|2|  
|Tabelle|@Table|table_name|3|  
  
### <a name="viewcolumns"></a>ViewColumns  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|VIEW_CATALOG|1|  
|Besitzer|@Owner|VIEW_SCHEMA|2|  
|Tabelle|@Table|VIEW_NAME|3|  
|Column|@Column|COLUMN_NAME|4|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|SPECIFIC_CATALOG|1|  
|Besitzer|@Owner|SPECIFIC_SCHEMA|2|  
|Name|@Name|SPECIFIC_NAME|3|  
|Parameter|@Parameter|PARAMETER_NAME|4|  
  
### <a name="procedures"></a>Prozeduren  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|SPECIFIC_CATALOG|1|  
|Besitzer|@Owner|SPECIFIC_SCHEMA|2|  
|Name|@Name|SPECIFIC_NAME|3|  
|Typ|@Type|ROUTINE_TYPE|4|  
  
### <a name="indexcolumns"></a>IndexColumns  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|db_name()|1|  
|Besitzer|@Owner|user_name()|2|  
|Tabelle|@Table|o.name|3|  
|ConstraintName|@ConstraintName|x.name|4|  
|Column|@Column|c.name|5|  
  
### <a name="indexes"></a>Indizes  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|db_name()|1|  
|Besitzer|@Owner|user_name()|2|  
|Tabelle|@Table|o.name|3|  
  
### <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|assembly_name|@AssemblyName|assemblies.name|1|  
|udt_name|@UDTName|types.assembly_class|2|  
  
### <a name="foreignkeys"></a>ForeignKeys  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|CONSTRAINT_CATALOG|1|  
|Besitzer|@Owner|CONSTRAINT_SCHEMA|2|  
|Tabelle|@Table|table_name|3|  
|Name|@Name|CONSTRAINT_NAME|4|  
  
## <a name="sql-server-2008-schema-restrictions"></a>SQL Server 2008-Schemabeschränkungen  

 In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008-Schemaauflistungen aufgeführt. Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008. Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.  
  
### <a name="columnsetcolumns"></a>ColumnSetColumns  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1|  
|Besitzer|@Owner|TABLE_SCHEMA|2|  
|Tabelle|@Table|table_name|3|  
  
### <a name="allcolumns"></a>AllColumns  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|----------------------|--------------------|-------------------------|------------------------|  
|Katalog|@Catalog|TABLE_CATALOG|1|  
|Besitzer|@Owner|TABLE_SCHEMA|2|  
|Tabelle|@Table|table_name|3|  
|Column|@Column|COLUMN_NAME|4|  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über ADO.NET](ado-net-overview.md)
