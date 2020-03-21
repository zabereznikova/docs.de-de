---
title: "\"GetSchema\" und Schemaauflistungen"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: e18c23e9bbec97a64110aba6eb7241761ecece06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149556"
---
# <a name="getschema-and-schema-collections"></a>"GetSchema" und Schemaauflistungen
Die **Verbindungsklassen** in jedem der verwalteten .NET Framework-Anbieter implementieren eine **GetSchema-Methode,** die zum Abrufen von Schemainformationen über die aktuell verbundene <xref:System.Data.DataTable>Datenbank verwendet wird, und die von der **GetSchema-Methode** zurückgegebenen Schemainformationen werden in Form einer verwendet. Die **GetSchema-Methode** ist eine überladene Methode, die optionale Parameter zum Angeben der zurückzugebenden Schemaauflistung und zum Einschränken der Menge der zurückgegebenen Informationen bereitstellt.  
  
## <a name="specifying-the-schema-collections"></a>Angeben der Schemaauflistungen  
 Der erste optionale Parameter der **GetSchema-Methode** ist der Auflistungsname, der als Zeichenfolge angegeben wird. Es gibt zwei Arten von Schemaauflistungen: allgemeine Schemaauflistungen, die von allen Anbietern verwendet werden, und besondere Schemaauflistungen, die für jeden Anbieter spezifisch sind.  
  
 Sie können einen verwalteten .NET Framework-Anbieter abfragen, um die Liste der unterstützten Schemaauflistungen zu ermitteln, indem Sie die **GetSchema-Methode** ohne Argumente aufrufen, oder mit dem Schemasammlungsnamen "MetaDataCollections". Dadurch wird <xref:System.Data.DataTable> mit einer Liste der unterstützten Schemaauflistungen, der Anzahl der von diesen Schemaauflistungen unterstützten Einschränkungen und der Anzahl der von diesen Schemaauflistungen verwendeten Bezeichnerteilen zurückgegeben.  
  
### <a name="retrieving-schema-collections-example"></a>Beispiel zum Abrufen von Schemaauflistungen  
 In den folgenden Beispielen <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> wird veranschaulicht, wie die Methode <xref:System.Data.SqlClient.SqlConnection> des .NET Framework-Datenanbieters für die SQL Server-Klasse zum Abrufen von Schemainformationen zu allen Tabellen in der **AdventureWorks-Beispieldatenbank** verwendet wird:  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
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
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Abrufen von Datenbankschemainformationen](retrieving-database-schema-information.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
