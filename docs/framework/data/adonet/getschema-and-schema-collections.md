---
title: "&#39;GetSchema&#39; und Schemaauflistungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# &#39;GetSchema&#39; und Schemaauflistungen
Die **Connection**\-Klassen aller von .NET Framework verwalteten Anbieter implementieren eine **GetSchema**\-Methode, die zum Abrufen von Schemainformationen über die derzeit verbundene Datenbank verwendet wird und die von der **GetSchema**\-Methode zurückgegebenen Schemainformationen werden als <xref:System.Data.DataTable> abgerufen.  Bei der **GetSchema**\-Methode handelt es sich um eine überladene Methode, die optionale Parameter zum Angeben der zurückzugebenden Schemaauflistung und zum Einschränken der zurückzugebenden Informationsmenge bereitstellt.  
  
## Angeben der Schemaauflistungen  
 Bei dem ersten optionalen Parameter der **GetSchema**\-Methode handelt es sich um den Namen der Auflistung, der als Zeichenfolge angegeben wird.  Es gibt zwei Arten von Schemaauflistungen: allgemeine Schemaauflistungen, die von allen Anbietern verwendet werden, und besondere Schemaauflistungen, die für jeden Anbieter spezifisch sind.  
  
 Sie können einen verwalteten Anbieter für .NET Framework abfragen, um die Liste der unterstützten Schemaauflistungen zu ermitteln. Hierzu rufen Sie die **GetSchema**\-Methode ohne Argumente oder mit dem Schemaauflistungsnamen "MetaDataCollections" auf.  Dadurch wird <xref:System.Data.DataTable> mit einer Liste der unterstützten Schemaauflistungen, der Anzahl der von diesen Schemaauflistungen unterstützten Einschränkungen und der Anzahl der von diesen Schemaauflistungen verwendeten Bezeichnerteilen zurückgegeben.  
  
### Beispiel zum Abrufen von Schemaauflistungen  
 In den folgenden Beispielen wird die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>\-Methode des .NET Framework\-Datenanbieters für die SQL Server\-Klasse <xref:System.Data.SqlClient.SqlConnection> veranschaulicht, die Schemainformationen zu allen in der **AdventureWorks**\-Beispieldatenbank enthaltenen Tabellen abruft.  
  
 \[Visual Basic\]  
  
```  
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
  
 \[C\#\]  
  
```  
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
  
## Siehe auch  
 [Abrufen von Schemainformationen aus einer Datenbank](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)