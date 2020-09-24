---
title: "\"GetSchema\" und Schemaauflistungen"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: cea9deb7fe019fea189a87fc08468d010929db9a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177448"
---
# <a name="getschema-and-schema-collections"></a>"GetSchema" und Schemaauflistungen

Die **Verbindungs** Klassen in den einzelnen .NET Framework verwalteten Anbietern implementieren eine **GetSchema** -Methode, die zum Abrufen von Schema Informationen über die derzeit verbundene Datenbank verwendet wird, und die Schema Informationen, die von der **GetSchema** -Methode zurückgegeben werden, werden in Form von angezeigt <xref:System.Data.DataTable> . Bei der **GetSchema** -Methode handelt es sich um eine überladene Methode, die optionale Parameter zum Angeben der zurück zugebende Schema Auflistung und zum Einschränken der zurückgegebenen Informationsmenge bereitstellt.  
  
## <a name="specifying-the-schema-collections"></a>Angeben der Schemaauflistungen  

 Der erste optionale Parameter der **GetSchema** -Methode ist der Sammlungs Name, der als Zeichenfolge angegeben wird. Es gibt zwei Arten von Schemaauflistungen: allgemeine Schemaauflistungen, die von allen Anbietern verwendet werden, und besondere Schemaauflistungen, die für jeden Anbieter spezifisch sind.  
  
 Sie können einen .NET Framework verwalteten Anbieter Abfragen, um die Liste der unterstützten Schema Auflistungen zu ermitteln, indem Sie die **GetSchema** -Methode ohne Argumente oder mit dem Schema Auflistungs Namen "MetaDataCollections" aufrufen. Dadurch wird <xref:System.Data.DataTable> mit einer Liste der unterstützten Schemaauflistungen, der Anzahl der von diesen Schemaauflistungen unterstützten Einschränkungen und der Anzahl der von diesen Schemaauflistungen verwendeten Bezeichnerteilen zurückgegeben.  
  
### <a name="retrieving-schema-collections-example"></a>Beispiel zum Abrufen von Schemaauflistungen  

 In den folgenden Beispielen wird veranschaulicht, wie die- <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> Methode der .NET Framework Datenanbieter für die SQL Server-Klasse verwendet wird <xref:System.Data.SqlClient.SqlConnection> , um Schema Informationen zu allen Tabellen abzurufen, die in der **AdventureWorks** -Beispieldatenbank enthalten sind:  
  
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
